---
title: Sor nettó összegének újraszámítása értékesítési rendelések és árajánlatok importálása esetén
description: Ez a témakör azt írja le, hogy a rendszer hogyan számítja újra a sorok nettó összegét az értékesítési rendelések és árajánlatok importálása során. Bemutatja azt is, hogyan lehet szabályozni a Microsoft különböző verzióinak viselkedését Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 08/05/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2022-06-08
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: edda0c016130e2a273adf8f3d3e00e2d3ae9d5c6
ms.sourcegitcommit: ce58bb883cd1b54026cbb9928f86cb2fee89f43d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/25/2022
ms.locfileid: "9719334"
---
# <a name="recalculate-line-net-amounts-when-importing-sales-orders-and-quotations"></a>Sor nettó összegének újraszámítása értékesítési rendelések és árajánlatok importálása esetén

[!include [banner](../includes/banner.md)]

Ez a témakör azt írja le, hogy a rendszer hogyan számítja újra a sorok nettó összegét az értékesítési rendelések és árajánlatok importálása során. Bemutatja azt is, hogyan lehet szabályozni a Microsoft különböző verzióinak viselkedését Dynamics 365 Supply Chain Management.

## <a name="how-updates-to-net-line-amounts-are-calculated-on-import"></a>A nettó sorösszegek frissítésének számítása importáláskor

Az Ellátásilánc-kezelés 10.0.23-as verziója egy [új 604418](https://fix.lcs.dynamics.com/issue/results/?q=604418). Ez a hibajavítás **módosította** azokat a feltételeket, amelyek teljesülése esetén egy sorban a Nettó összeg mező frissíthető vagy újraszámálható a meglévő értékesítési rendelések és ajánlatok frissítésének importálása során. A 10.0.29-es *verzióban ezt a hibajavítást az Importálás nettó összegének számítása funkcióval lecserélheti*. Ennek a funkciónak hasonló a hatása, de globális beállítást ad, amellyel szükség esetén visszatérhet a régi viselkedéshez. Bár az új viselkedés miatt a rendszer minél visszahatóbb módon működik, váratlan eredményekhez vezethet olyan helyzetekben, amikor az alábbi feltételek teljesülnek:

- *A meglévő rekordokat frissülő adatokat a rendszer a V2. értékesítésirendelés-sorokból,* a *V2* *·*. értékesítésiajánlat-sorokból vagy a Visszárurendelési sorok entitásból importálja az OData protokoll használatával, ahol kettős írású, excelen keresztüli importálási/exportálási helyzeteket, valamint külső fél integrációit használja.
- [A kereskedelmi megállapodás](/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper)**értékelési** kötvényei olyan módosítási házirendet hoznak létre, amely korlátozza az értékesítésirendelés-sorok, értékesítésiajánlat-sorok és/vagy visszárurendelés-sorok Nettó összeg mezőjének frissítését. Ne feledje, hogy visszárurendelés-soroknál a program mindig kiszámítja a Nettó összeg mezőt, **és** nem lehet manuálisan beállítani.
- Az importált **adatok** tartalmazzák a sorok Nettó összeg mezőjének módosításait, vagy olyan módosításokat (például egységár, mennyiség vagy engedmény), **amelyek** a sorok nettó összeg mezőjének értékét újraszámítják egy vagy több meglévő sorrekordban.

Ilyen konkrét helyzetekben a kereskedelmi megállapodás értékelési irányelvének az a **hatása**, hogy korlátozást hoz a sor Nettó összeg mezőjének frissítésére. Ezt a korlátozást módosítási irányelvnek *is nevezik*. A házirend miatt, amikor a felhasználói felület segítségével szerkeszti vagy újraszámálja a mezőt, a rendszer kéri, hogy erősítse meg, hogy szeretné-e módosítani a mezőt. A rekord importálása során azonban a rendszernek kell választania az Ön számára. A 10.0.23-as verzió előtt a rendszer mindig változatlanul hagyta a sor nettó összegét, hacsak a bejövő sor nettó összege nem 0 (nulla). Az újabb verziókban azonban a rendszer a szükséges módon mindig frissíti vagy újraszámálja a nettó összeget, hacsak kifejezetten rá nincs utasítva, hogy ne tegye meg. Bár az új viselkedés logikusabb, problémákat okozhat, ha már olyan folyamatokat vagy integrációkat futtat, amelyek a régebbi viselkedést feltételezik. Ez a témakör azt írja le, hogyan lehet visszatérés a régi viselkedéshez, ha kell.

## <a name="control-calculations-of-line-net-amounts-in-versions-10029-and-later"></a>A nettó sorok számításának ellenőrzése a 10.0.29-es és az újabb verziókban

Az Ellátásilánc-kezelés 10.0.29-es *verziója egy olyan funkciót bevezetett, amely az import sorának nettó összegének kiszámítása névvel rendelkezik*. Ez a funkció hozzáad egy Sort nettó összeg **számítása** **nevű beállítást a Kinnlevőségek paraméterei oldalhoz.** Ezzel a beállítással kiválaszthatja az importálás során kiszámított nettó sorok új és örökölt viselkedését.

### <a name="turn-the-calculate-line-net-amount-on-import-feature-on-or-off"></a>A Sor nettó összegének számítása importálási funkció be- és kikapcsolása

Ha a 10.0.29-es verzióra frissít, *akkor* az importálás sorának nettó összegének kiszámítása funkció alapértelmezés szerint be van kapcsolva, **·** *és az új Sor nettó összegének számítása beállítás kezdetben Igen*. Az *Igen* beállítás az új normál működésnek felel meg. A funkció kikapcsolása esetén megfelel a rendszer viselkedésének, [kivéve a CalculateLineAmount](#CalculateLineAmount) paraméter funkcióinak esetét, amint azt a jelen cikk későbbi része ismerteti. A *"Nincs* " beállítás megfelel a rendszer viselkedésének a 10.0.23-as verzió előtt, és elsősorban az örökölt integrációs helyzetek támogatására van rendelkezésre.

A rendszergazdák a Szolgáltatáskezelési munkaterületen be- *·*[és kikapcsolhatja a Sor nettó összegének számítása importálási funkciót.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)

### <a name="set-the-calculate-line-net-amount-option"></a>A Sor nettó összegének számítása beállítás beállítása

Ha az *Importálás sorának nettó* összegének számítása funkció be van kapcsolva, **a** következő lépések segítségével be lehet állítani a Sor nettó összegének számítása lehetőséget.

1. Lépjen a **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontra.
1. Az Árak **lap** Sor **nettó** **összegének** számítása integrációs gyorslapon állítsa a Sor nettó összegének kiszámítása lehetőséget a következő értékek egyikére:

    - *Igen* – a rendszer szükség esetén mindig újraszámálja és frissíti a sorösszegeket. (Figyelmen kívül hagyja a kereskedelmi megállapodás értékelési irányelvét.)
    - *Nem* – ha bármely sor meglévő vagy bejövő nettó összege 0 (nulla), akkor a sor értéke más értékek (például egységár, mennyiség és engedmény) alapján újra lesz számítva. Ha a meglévő vagy bejövő nettó összeg 0-tól (nulla) eltér, és a sor Nettó összeg mezőjében módosítási irányelv van beállítva, a mező nem lesz újraszámítva vagy frissítve, még akkor sem, ha a **sor** árának, mennyiségének és/vagy engedményének bejövő módosítása esetén a sorösszeg újraszámítása szükséges. Ez a viselkedés megegyezik a 10.0.22-es verzióval.

### <a name="how-the-calculate-line-net-amount-on-import-feature-affects-the-calculatelineamount-parameter"></a><a name="CalculateLineAmount"></a> Hogyan befolyásolja az Importálás sorának nettó összegének kiszámítása funkció a CalculateLineAmount paramétert

Ha az *Importálás sorának nettó összegének számítása* funkció be van kapcsolva, `CalculateLineAmount``SalesLine``SalesQuotationLine` a és a táblák paraméterértékének nincs hatása. Ehelyett a viselkedést **globálisan** az előző szakaszban ismertetett Nettó összeg számítása beállítás vezérli. Amikor tehát be van kapcsolva a funkció, nem szabad függnie az értéktől `CalculateLineAmount`.

*Ha* az Importálás sorának nettó összegének számítása funkció ki van kapcsolva, `CalculateLineAmount``SalesLine``SalesQuotationLine` az ellátásilánc-kezelés 10.0.23-tól 10.0.28-ig tart, ahogy azt a következő szakasz írja le.

## <a name="control-line-net-amount-calculations-in-versions-10028-and-earlier"></a>Ellenőrzősor nettó összegének számítása a 10.0.28-as és korábbi verziókban

[Amikor a 604418-es](https://fix.lcs.dynamics.com/issue/results/?q=604418) hibajavítást bevezették a 10.0.23-as verzióban, lehetővé vált, hogy kiválják, hogyan legyenek hasznosak az egyes adatentitások, amikor sor nettó összeget szerkeszttek vagy újra kellett számítanának más változások (például a frissített cikkár) miatt. Ezt a viselkedést az `CalculateLineAmount` importált fájl következő értékeinek egyikére adva lehet szabályozni:

- **`CalculateLineAmount` = *1*** – **a sor Nettó** összeg mezője mindig újra lesz számítva és frissül, függetlenül attól, hogy a mezőre be van-e állítva módosítási irányelv, és függetlenül a bejövő vagy a meglévő sor nettó összegétől.
- **`CalculateLineAmount` = *0*** – ha bármely sor meglévő vagy bejövő nettó összege 0 (nulla), akkor a program az adott sor értékét más értékek (például egységár, mennyiség és engedmény) alapján újraszámítja. Ha a meglévő vagy a bejövő nettó összeg 0-tól (nulla) eltér, és a sor Nettó összeg mezőjében módosítási irányelv van beállítva, akkor a **mező** nem lesz újraszámállítva vagy frissítve.  

A rendszer viselkedése az Ellátásilánc-kezelés adott verziójától függ:

- A 10.0.22-es `CalculateLineAmount`*és korábbi verziókban a rendszer mindig 0-ra* van állítva, `CalculateLineAmount`*és így nem lehet 1-ként* beállítani.
- A 10.0.23 és 10.0.28 verziókban a rendszer úgy viselkedik, mintha 1-re lenne állítva minden olyan sornál, `CalculateLineAmount`*ahol nem kifejezetten 0-ra van állítva* az importfájlban.*·*
