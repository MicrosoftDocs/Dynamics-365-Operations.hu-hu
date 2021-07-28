---
title: Termékszűrők konfigurálása raktári tranzakciókhoz
description: Ez a témakör bemutatja, hogyan tud termékszűrőket és szűrőkódokat beállítani a raktárban található készletcikkek csoportosításához. A szűrők használatával megadhatja, hogy mely vevők rendelhetnek meg egy adott cikket, valamint egy adott szállítótól mely cikkek szerezhetők be.
author: Mirzaab
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSFilters,WHSFilterGroupTable,EcoResProductDetailsExtended,WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 8c5574efeb1dee372a8ecf8ddb1d1710f63b73a7
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6345234"
---
# <a name="configure-product-filters-for-warehouse-transactions"></a>Termékszűrők konfigurálása raktári tranzakciókhoz

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan tud termékszűrőket és szűrőkódokat beállítani a raktárban található készletcikkek csoportosításához. A szűrők használatával megadhatja, hogy mely vevők rendelhetnek meg egy adott cikket, valamint egy adott szállítótól mely cikkek szerezhetők be.

Ezenkívül beállíthatja és a termékszűrők segítségével automatikusan kezelheti a készletcikkeket a raktárban, valamint szűrőcsoportokba egyesítheti a szűrt elemeket. A szűrők segítségével kategóriákba lehet sorolni a cikkeket kezelési, beszerzési és értékesítési folyamatokban. Előfordulhat, hogy csoportosítani szeretné a cikkeket, vagy elválasztani őket egymástól, ha a kezelés súly- vagy kezelési korlátozásokon alapul. Meghatározhatja azt is, hogy egy cikk mely vevők vagy szállítók által vásárolható meg vagy adható el egy cikk.

## <a name="prerequisites"></a>Előfeltételek

Az alábbi táblázat bemutatja a munka megkezdése előtt biztosítandó előfeltételeket.

| Előfeltételek | Utasítások |
|---|---|
| Mielőtt elkezdené konfigurálni a termékeket a **Kiadott termékek részletei** oldalon, be kell kapcsolnia a raktárfeldolgozást a termék tárolási dimenziócsoportja esetében. | Lépjen a **Termékinformáció-kezelés \> Beállítás \> Dimenzió- és változatcsoportok \> Tárolásidimenzió-csoportok** részre, és válasszon vagy hozzon létre egy olyan tárolásidimenzió-csoportot, amelyben a **Raktárkezelési folyamatok alkalmazása** beállítás *Igen* értékre van beállítva. |
| Ha vevőszűrőket és/vagy szállítószűrőket használ, engedélyeznie kell a használatukat a Raktárkezelési paraméterekben. | Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre. A **Termékszűrők** lapon állítsa a **Vevőszűrők engedélyezése** és/vagy a **Szállítószűrők engedélyezése** lehetőséget *Igen* beállításra. |

## <a name="set-up-product-filters"></a>Termékszűrő beállítása

A termékszűrők legfeljebb 10 **Szűrőcím** jellemzőt tartalmaznak, amelyek felsorolási (enum) értékek. Ezek az enumerációs értékek termékszűrők létrehozásakor állnak rendelkezésre kiválasztásra. Az *1. kód* és *10. kód* közötti enumerációs értékek rendszer által definiáltak, és egy cikk meghatározott jellemzőit vagy attribútumait képviselik. Az *1. kód* például a veszélyes anyagosztályozású cikkeket képviselheti. A *2. kód* olyan cikkeket jelenthet, amelyeket csak szállítók vásárolhatnak meg. A termékszűrők ezután a **Szűrőcím** értékéhez társított adott **Szűrőkód** értékét határozzák meg.

1. Lépjen a **Raktárkezelés \> Beállítás \> Termékszűrők \> Termékszűrők** részre.
1. A Művelet panelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy termékszűrőt a rácshoz.
1. Válasszon egy értéket a **Szűrőcím** mezőben.
1. Írjon be értéket a **Szűrőkód** mezőbe.

    ![Termékszűrő beállítása.](media/Product_Filters10.png "Termékszűrő beállítása")

1. A **Leírás** mezőbe írja be a kód nevét. A *2. kód* például a szállítókat jelentheti. Ezt követően termékszűrőt hozhat létre egy adott szállítóhoz vagy szállítócsoporthoz. További tudnivalókat a [Szállítói szűrőkódok beállítása](#vendor-product-filters) részben olvashat, a témakör későbbi részében.

    ![Termékszűrők készlete.](media/Product_Filters.png "Termékszűrők készlete")

## <a name="set-up-product-filter-groups"></a>Termékszűrőcsoportok beállítása

A szűrőcsoportok a csoportszűrőkóddal használhatók. Ez a képesség akkor hasznos, ha a csoportot egy helyutasításban használja egy lekérdezésben, és meg kívánja keresni a csoportot a kódsorozat helyett. Minden egyes szűrőcsoport egy cikkcsoporthoz van rendelve.

> [!IMPORTANT]
> Nem minden termékszűrő-csoport érhető el a kódoknál, amelyek magasabbak, mint a *4. kód* (azaz az *5. kód* – *10. kód*). Például a kiadott termékeknél annak ellenére nem frissül a szűrőkódok csoportosítása, hogy minden termékszűrőkódot hozzáadnak. Ez a viselkedés a későbbi verziókban lehet frissítve.

A szűrőcsoportok beállításához kövesse az alábbi lépéseket.

1. Lépjen a **Raktárkezelés \> Beállítás \> Termékszűrők \> Termékszűrőcsoportok** részre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az **1. csoport** és **2. csoport** mezőkben adja meg a cikkek kategorizálásához használt neveket.
1. A **Részletek** gyorslapon válassza ki az **Új** lehetőséget egy sor hozzáadásához.
1. A **Kezdő dátum/idő** és a **Záró dátum/idő** mezőkbe írja be a szűrőcsoport kezdő és záró dátumát.
1. A **Cikkcsoport** mezőben válassza ki azt a cikkcsoportot, amelyre a termékszűrőnek érvényesnek kell lennie.
1. Az **1. kód** – **10. kód** mezőben szükség szerint válassza ki a csoportba foglalni kívánt szűrőkódokat.

    ![Cikkcsoport.](media/ProdFilterGroup.png "Cikkcsoport")

> [!NOTE]
> Ha megjelenik egy hibaüzenet, amikor bezárja az oldalt, egy kódbeállítás hiányozhat. A **Cikkcsoportok** oldalon kötelezővé lehet tenni a kódokat egy cikkcsoporthoz az **1. szűrőkód hozzárendelése cikkcsoporthoz**, a **2. szűrőkód hozzárendelése cikkcsoporthoz** stb. jelölőnégyzetet kiválasztva.

## <a name="set-up-filter-codes-on-item-groups"></a>A cikkcsoportok szűrőkódjainak beállítása

Egy cikkcsoport szűrőkódjainak beállításával létrehozhatja a cikkcsoporthoz tartozó termékekhez szükséges kódokat.

A cikkcsoportok szűrőkódjainak beállításához kövesse az alábbi lépéseket.

1. Lépjen a **Készletgazdálkodás \> Beállítás \> Készlet \> Cikkcsoportok** pontra.
1. A cikkcsoport létrehozásához a műveleti ablaktáblán válassza ki az **Új** lehetőséget.
1. A **Cikkcsoport** mezőben adjon meg egy nevet.
1. A **Név** mezőbe adja meg a leírást.
1. A **Raktár** gyorslapon, a **Szükséges szűrő** részben jelölje ki a megfelelő jelölőnégyzeteket a cikkcsoporthoz tartozó termékekhez megadandó szűrőkódok meghatározásához.

    Egy kiadott termék frissítéséhez nyissa meg a **Kiadott termék részletei** oldalt, majd a Művelet panelen válassza a **Szerkesztés** lehetőséget. A kódokhoz társított szűrők ezután elérhetővé válnak a **Raktár** gyorslapon.

    ![Cikkcsoportok.](media/ItemGroup10.png "Cikkcsoportok")

1. Jelölje be a **Cikkcsoportszűrő** szakaszban azoknak a szűrőknek a jelölőnégyzeteit, amelyeknek meg kell egyeznie ahhoz, hogy a szűrőcsoport a cikk alapértelmezett szűrőcsoportja legyen.

    Például ha kiválasztja az **1. szűrőkód használata** és **2. szűrőkód használata** jelölőnégyzeteket, akkor a cikk 1. szűrőkódjának és 2. szűrókódjának is meg kell felelnie a cikkcsoport szűrőcsoportjának beállításainak, mielőtt kijelölhetne egy szűrőcsoportot. Új cikk létrehozásakor a kiválasztott szűrőcsoport lesz az alapértelmezett szűrőcsoport az **1. csoport** és a **2. csoport** mezőben a **Kiadott termékek részletei** oldal **Raktár** gyorslapján.

> [!IMPORTANT]
> A termékszűrők csak olyan cikkeknél engedélyezettek, amelyek speciális raktárkezelést használják.

## <a name="specify-filter-codes-for-released-products"></a>Kiadott termékek szűrőkódjainak megadása

A kiadott termékek szűrőkódjainak megadásához kövesse ezeket a lépéseket. Szűrőkódok használhatók például az olyan veszélyes termékek csoportosítására, amelyeket meghatározott szállítók vásárolnak.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Jelölje be a műveleti ablakban az **Új** lehetőséget a termék létrehozásához.
1. Az **Új kiadott termék** párbeszédpanelen írja be az új termék alapjának létrehozásához szükséges adatokat, majd válassza az **OK** lehetőséget.

    A termékszűrők csak akkor használhatók, ha a termékhez kapcsolt cikkcsoport be van állítva szűrőkódokhoz.

    További információ: [Új termék létrehozása](../pim/tasks/create-new-product.md).

1. A **Raktár** gyorslapon a **Termékszűrők** szakaszban szükség szerint válassza ki az **1. kód** – **10. kód** mezőket a termékre vonatkozó szűrőkódok megadásához.

## <a name="set-up-generally-available-items"></a>Általánosan elérhető cikkek beállítása

Adott készletcikkeket elérhetővé tehet csak a vevők vagy csak a szállítók számára, vagy a vevők és szállítók számára is.

> [!NOTE]
> Azokra a cikkekre, amelyeket általánosan elérhetőként ad meg, a vevői szűrők és a szállítószűrők nem vonatkoznak.

Az általánosan elérhető cikkek beállításához tegye a következőket.

1. Lépjen a **Raktárkezelés \> Beállítás \> Termékszűrők \> Általánosan elérhető termékek** részre.
1. Jelölje be a műveleti ablakban az **Új** lehetőséget a rekord létrehozásához.
1. A **Vevő vagy szállító** mezőben válassza a *Vevő*, a *Szállító* vagy a *Mind* lehetőséget, ha a cikkeket elérhetővé teszi a vevők, szállítók vagy mindkettő számára.
1. A **Kezdő dátum/idő** mezőbe írja be azt a dátumot és időpontot, amikor a cikk elérhetővé válik.
1. A **Cikkcsoport** mezőben válasszon ki egy elemcsoportot.
1. Az **1. kód** – **10. kód** mezőkben válassza ki az általánosan elérhető cikkek korlátozásához használt szűrőkódokat.

    Amikor kiválaszt egy cikkcsoportot, a cikkek e csoportját általánosan elérhetővé teszi. Az ezekben a mezőkben kiválasztott szűrőkódokkal az elérhető cikkeket korlátozza.

## <a name="set-up-customer-product-filters"></a>Vevői termékszűrők beállítása

Ezzel az opcionális eljárással megadhatja azokat a cikkeket, amelyek a vevő számára elérhetők azokon a cikkeken felül, amelyeket a szűrőbeállítás tett elérhetővé az **Általánosan elérhető cikkek** oldalon. Több szűrőkódot is beállíthat egyetlen vevőhöz.

A vevői szűrőkódok beállításához kövesse az alábbi lépéseket.

1. Lépjen az **Értékesítés és marketing \> Vevők \> Összes vevő** menüpontba.
1. Válasszon vevőt.
1. A Művelet panel **Vevő** lapján, a **Beállítás** csoportban válassza a **Termékszűrők** lehetőséget.
1. A **Termékszűrőkódok** lap műveleti paneljén válassza ki az **Új** elemet.
1. A **Kezdő dátum/idő** és a **Záró dátum/idő** mezőkbe írja be a kiválasztott cikkcsoport kezdő és záró dátumát.
1. A **Cikkcsoport** mezőben válasszon ki egy elemcsoportot.
1. Az **1. kód** – **10. kód** mezőkben válassza ki azokat a szűrőkódokat, amelyeket feltételként használ a kiválasztott cikkcsoport vevői számára elérhető cikkek korlátozására. Minden, a cikkcsoporthoz beállított szűrőkódhoz be kell állítania egy kiválasztást.

## <a name="set-up-vendor-product-filters"></a><a name="vendor-product-filters"></a>Szállítói termékszűrők beállítása

Ezzel az opcionális eljárással megadhatja azokat a cikkeket, amelyek a szállító számára elérhetők azokon a cikkeken felül, amelyeket a szűrőbeállítás tett elérhetővé az **Általánosan elérhető cikkek** oldalon. Több szűrőkódot is beállíthat egyetlen szállítóhoz.

A szállítói szűrőkódok beállításához kövesse az alábbi lépéseket.

1. Ugrás a **Beszerzés és forrás \> Beszállítók \> Minden szállító** pontra.
1. Válasszon ki egy szállítót.
1. A Művelet panel **Szállító** lapján, a **Beállítás** csoportban válassza a **Termékszűrők** lehetőséget.
1. A **Szűrőkódok** lap műveleti paneljén válassza ki az **Új** elemet.
1. A **Kezdő dátum/idő** és a **Záró dátum/idő** mezőkbe írja be a kiválasztott cikkcsoport kezdő és záró dátumát.
1. A **Cikkcsoport** mezőben válasszon ki egy elemcsoportot.
1. Az **1. kód** – **10. kód** mezőkben válassza ki azokat a szűrőkódokat, amelyeket feltételként használ a kiválasztott cikkcsoport szállítói számára elérhető cikkek korlátozására. Minden, a cikkcsoporthoz beállított szűrőkódhoz be kell állítania egy kiválasztást.

> [!NOTE]
> A szállítói termékszűrők beállítása azokra a kiadott termékekre vonatkozik, ahol engedélyezve vannak a raktárkezelési folyamatok a társított tárolásidimenzió-csoporthoz. A szűrőkódok annak meghatározására használhatók, hogy a rendszer lehetővé teszi-e a felhasználók számára, hogy egy adott cikket vásárolják egy adott szállítótól a beszerzésirendelés-sorok létrehozásakor. A Microsoft Dynamics 365 Supply Chain Management kétféle módszerrel rendelkezik a szállítói jóváhagyás kezelésére. Ha létezik egy vagy több olyan kiadott termék, ahol az **Engedélyezett szállítók ellenőrzési módszere** mező beállítása *Csak figyelmeztetés* vagy *Nem engedélyezett*, mindkét szállítói jóváhagyási módszer engedélyezhető ezeknél a cikkeknél. Ez a helyzet problémákat okozhat, amikor a felhasználók beszerzési rendelési sorokat hoznak létre.

## <a name="see-also"></a>Lásd még

[A további tudnivalókat lásd a WMS-raktári szűrőkódokra vonatkozó blogbejegyzésben](http://blog.dynamics-for-operations.com/2017/09/26/wms-warehouse-filter-codes/)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]