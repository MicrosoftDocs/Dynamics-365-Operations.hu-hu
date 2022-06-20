---
title: Minőségbiztosítási tesztcsoportok
description: Ez a témakör azt mutatja be, hogyan lehet tesztcsoportokat létrehozni, hogy a Microsoft minőségi rendelésekkel több teszt is használható legyen Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e7722bc92d8c2bf52d6a798a93f07af44037d4e0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857693"
---
# <a name="quality-management-test-groups"></a>Minőségbiztosítási tesztcsoportok

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet tesztcsoportokat létrehozni, hogy a Microsoft minőségi rendelésekkel több teszt is használható legyen Dynamics 365 Supply Chain Management.

A **Tesztcsoportok** oldalon lehet beállítani, módosítani és megtekinteni a tesztcsoportokat és a tesztcsoportokhoz rendelt különálló teszteket. Az oldal felső része jeleníti meg a tesztcsoportokat, míg az alsó részen láthatók a kiválasztott tesztcsoporthoz tartozó tesztek.

Egy tesztcsoporthoz több szabályt is hozzá lehet rendelni, beleértve a mintavételi tervet, elfogadható minőségi szintet, valamint a romboló teszt követelményét. Majd, amikor hozzárendel egy különálló tesztet egy tesztcsoporthoz, további adatokat definiálhat, például sorrendet, dokumentumokat és érvényességi dátumokat. Mennyiségi teszt esetén a megadott adatok az elfogadható mérési értékeket is tartalmazzák. Minőségi teszt esetén az adatok a tesztváltozót és az alapértelmezett eredményt tartalmazzák.

A minőségi rendelésekhez rendelt tesztcsoport meghatározza azokat az alapértelmezett teszteket, amelyeket az adott cikken végre kell hajtani. Azonban hozzáadhat, törölhet, vagy módosíthat adott minőségi rendelésre vonatkozó teszteket. A minőségi rendelés keretében végzett mindegyik tesztnél megtörténik a teszteredmények jelentése.

Tesztcsoport definiálása esetén lehetőség van a cikkmintavétel megadására is. A cikkmintavételek a termék tesztelni kívánt mennyiségének meghatározására használhatók. További információért lásd: [Minőségkezelési cikk mintavételezése](quality-item-sampling.md). Jelezheti azt is, hogy a tesztcsoportban végzett tesztek romboló hatásúak-e. Romboló teszt sorén a cikkminta megsemmisül, és a mennyiséget eltávolítják az aktuális készletből.

## <a name="example-of-a-test-group"></a>Példa egy tesztcsoportra

Egy gyártóvállalat minőségi irányelveinek minden variációjához meghatároz egy-egy tesztcsoportot. A különböző tesztcsoportok tükrözik a mintavételi tervek, az együttesen végrehajtandó tesztsorok, az elfogadható mérési értékek, az elfogadható minőségi szint és egyéb tényezők eltéréseit. Mennyiségi teszt esetén az elfogadható mérési értékekben is van különbség. A minőségi irányelvek betartatása érdekében a vállalat tesztcsoportot rendel minden olyan szabályhoz, amely a minőségi rendelések automatikus generálása során használatos a **Minőségi társítások** lapon. A manuálisan létrehozott minőségi rendelésekhez is hozzárendel egy tesztcsoportot.

## <a name="create-a-test-group"></a>Tesztcsoport létrehozása

Tesztcsoport létrehozásához kövesse az alábbi lépéseket.

1. Ugorjon a **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Tesztcsoportok** elemre.
1. A műveleti ablaktáblán válassza az **Új** elemet sor rácshoz adásához az oldal felső részén. Ezután új sorhoz állítsa be a következő mezőket:

    - **Tesztcsoport** – Adja meg a tesztcsoport egyedi azonosítóját vagy nevét.
    - **Leírás** – Adja meg a tesztcsoport részletes leírását.
    - **Elfogadható minőségi szint** – Adja meg az összes teszteredmény százalékos arányát, amely az megfeleltnek tekintendő tesztcsoport sikeres teljesítéséhez.
    - **Cikkmintavétel** – Egy cikkmintavétel kiválasztása. További információért lásd: [Minőségkezelési cikk mintavételezése](quality-item-sampling.md).
    - **Romboló** – Ennek a jelölőnégyzetnek a kiválasztásával jelezheti, hogy a tesztcsoport megsemmisíti a vizsgált cikkeket.

1. Amíg az új sor ki van választva, válassza az **Általános** lapot a lap felső részén. A rendszer az **Áttekintés** lapon kiválasztott tesztcsoport néhány beállítását itt is megismétli. Ezenkívül a következő mezőket lehet beállítani a csoporthoz:

    - **Készlet kötegattribútumának frissítése** – ha itt *Igen* beállítást ad meg, a rendszer automatikusan *Igen* értéket ad minden olyan új teszthez, amely a lap alsó részén található tesztcsoporthoz hozzáadódik.
    - **Kötegelt intézkedés frissítése** – ha *Igen* értékre állítja ezt a beállítást, ha a vizsgált cikk kötegvezérelt, a kötegintézkedés automatikusan frissül azzal az értékkel, amely a **SSikertelen minőségi rendelés kötegintézkedés** vagy a **Sikeres minőségi rendelés kötegintézkedés** mezőben ki van választva.
    - **Sikertelen minőségi rendelés kötegintézkedés** – válassza ki azt a kötegintézkedés-kódot, amely akkor lesz hozzárendelve, ha egy ezt a tesztcsoportot tartalmazó minőségi rendelés sikertelen, mert nem felel meg az elfogadható minőségi minőségi szintnek.
    - **Sikeres minőségi rendelés kötegintézkedés** – válassza ki azt a kötegintézkedés-kódot, amely akkor lesz hozzárendelve, ha egy ezt a tesztcsoportot tartalmazó minőségi rendelés sikeres, mert megfelel az elfogadható minőségi minőségi szintnek.
    - **Készletállapot frissítése** – ha *Igen* értékre állítja ezt a beállítást, ha a vizsgált cikk tárolásidimenzió-csoportjában engedélyezve van a **Készletállapot**, az állapot automatikusan a **Sikertelen minőségi rendelés** vagy a **Sikeres minőségi rendelési** mezőben kiválasztott állapottal frissül.
    - **Sikertelen minőségi rendelés állapota** – válassza ki azt a készletállapotot, amely akkor lesz hozzárendelve a cikkhez, ha egy ezt a tesztcsoportot tartalmazó minőségi rendelés sikertelen, mert nem felel meg az elfogadható minőségi minőségi szintnek.
    - **Sikeres minőségi rendelés állapota** – válassza ki azt a készletállapotot, amely akkor lesz hozzárendelve a cikkhez, ha egy ezt a tesztcsoportot tartalmazó minőségi rendelés sikeres, mert megfelel az elfogadható minőségi szintnek.

## <a name="add-a-qualitative-test-to-a-test-group"></a>Kvalitatív teszt hozzáadása tesztcsoporthoz

A következő lépésekkel lehet minőségi teszteket hozzáadni egy tesztcsoporthoz.

1. Ugorjon a **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Tesztcsoportok** elemre.
1. A lap felső részének **Áttekintés** lapján válassza ki azt a tesztcsoportot, amelybe teszteket szeretne hozzáadni.
1. A lap alsó részén, az **Áttekintés** lapon kattintson a **Hozzáadás** gombra az eszköztáron, és adjon hozzá egy sort a rácshoz. Ezután új sorhoz állítsa be a következő mezőket:

    - **Sorszám** – A tesztek sorrendjének megadásához egy egész számot kell megadni. A kisebb sorszámú tesztek a nagyobb sorszámú tesztek előtt futnak le.

        > [!NOTE]
        > Javasoljuk, hogy hagyjon ki értékeket a sorszámok között. Az első tesztnél állítsa például a **Sorszám** mező értékét *10*-re, majd minden további tesztnél tízesével növelje az értéket. Így később úgy adhat hozzá új teszteket, hogy nem kell törölnie, majd újra létre kell hoznia a sorokat, hogy a kívánt sorrendbe helyezze őket.

    - **Teszt** – A végrehajtani kívánt teszt kiválasztása. Kvalitatív teszt esetén válassza ki azt a tesztet, amelyben a **Típus** mező beállítása *Lehetőség*.
    - **Hatályos** Válassza ki az első dátumot, amikor a teszt érvényes. Ha üresen hagyja ezt a mezőt.. akkor nincs korlát.
    - **Lejárat** Válassza ki az utolsó dátumot, amikor a teszt érvényes. Ha üresen hagyja ezt a mezőt, vagy *Soha* értékre állítja, akkor nincs korlátozás.
    - **Tesztérték meghatározása** – Adja meg, hogyan kell meghatározni egy elfogadható minőségi szintet, amikor ugyanahhoz teszthez több eredményt rögzítenek. Kvalitatív teszt esetén csak a *Manuális* beállítás választható ki. Ha a többi érték (*Átlag*, *Minimum* vagy *Maximum*) valamelyikét választja, hibaüzenetet kap a tesztcsoport mentésekor.
    - **Attribútum** – Ha kötegattribútumon szeretné rögzíteni a teszteredményeket, jelölje ki itt az attribútumot, és jelölje be a **Készlet kötegattribútumának frissítése** jelölőnégyzetet.
    - **Készlet kötegattribútumának frissítése** – jelölje be ezt a jelölőnégyzetet azon kötegattribútum teszteredményeinek rögzítéséhez, amely ki van jelölve az **Attribútum** mezőben.

1. A lap alsó részén válassza az **Általános** lapot. Az **Áttekintés** lapon kiválasztott teszt néhány beállítását itt megismétli a program. Ezenkívül a következő mezőket lehet beállítani a teszthez:

    - **Elemzési tanúsítvány jelentés** – Az *Igen* beállítással jelezheti, hogy a teszteredményeket ki kell nyomtatni az elemzési tanúsítványra (CoA). Ez a jelentés a minőségi rendelésből generálható.
    - **Művelet hiba esetén** – az *Elfogadás* vagy a *Sikertelen* beállítás kiválasztásával jelezze, hogy a tesztnek sikeresnek vagy sikertelennek kell-e lennie, ha az Elfogadható minőségi szint nem teljesül.
    - **Elfogadható minőségi szint** – Adja meg az összes teszteredmény százalékos arányát, amely megfeleltnek tekintendő a teszt sikeres teljesítéséhez.

1. A lap alsó részén, a **Teszt** lapon állítsa be a következő mezőket:

    - **Változó** – Válassza ki a minőségi ellenőrzés teszteredményeinek rögzítésére szolgáló változót.
    - **Alapértelmezett eredmény** – válassza ki a teszteredmények esetén rögzíteni kívánt alapértelmezett eredményt.
    - **Tesztműszer** – a teszthez használt eszköz kiválasztása. Ha meg van adva tesztműszer, akkor az automatikusan bekerül a teszthez a tesztcsoportba.

1. Zárja be a lapot.

## <a name="add-a-quantitative-test-to-a-test-group"></a>Mennyiségi teszt hozzáadása tesztcsoporthoz

A következő lépésekkel lehet mennyiségi teszteket hozzáadni egy tesztcsoporthoz.

1. Ugorjon a **Készletkezelés \> Beállítás \> Minőség-ellenőrzés \> Tesztcsoportok** elemre.
1. A lap felső részének **Áttekintés** lapján válassza ki azt a tesztcsoportot, amelybe teszteket szeretne hozzáadni.
1. A lap alsó részén, az **Áttekintés** lapon kattintson a **Hozzáadás** gombra az eszköztáron, és adjon hozzá egy sort a rácshoz. Ezután új sorhoz állítsa be a következő mezőket:

    - **Sorszám** – A tesztek sorrendjének megadásához egy egész számot kell megadni. A kisebb sorszámú tesztek a nagyobb sorszámú tesztek előtt futnak le.

        > [!NOTE]
        > Javasoljuk, hogy hagyjon ki értékeket a sorszámok között. Az első tesztnél állítsa például a **Sorszám** mező értékét *10*-re, majd minden további tesztnél tízesével növelje az értéket. Így később úgy adhat hozzá új teszteket, hogy nem kell törölnie, majd újra létre kell hoznia a sorokat, hogy a kívánt sorrendbe helyezze őket.

    - **Teszt** – A végrehajtani kívánt teszt kiválasztása. Mennyiségi teszt esetén válassza ki azt a tesztet, amelyben a **Típus** mező beállítása *Tört* vagy *Egész szám*.
    - **Hatályos** Válassza ki az első dátumot, amikor a teszt érvényes. Ha üresen hagyja ezt a mezőt.. akkor nincs korlát.
    - **Lejárat** Válassza ki az utolsó dátumot, amikor a teszt érvényes. Ha üresen hagyja ezt a mezőt, vagy *Soha* értékre állítja, akkor nincs korlátozás.
    - **Tesztérték meghatározása** – Adja meg, hogyan kell meghatározni egy elfogadható minőségi szintet, amikor ugyanahhoz teszthez több eredményt rögzítenek. A következő lehetőségek érhetők el: *Átlag*, *Minimum*, *Maximum* és *Manuális*.
    - **Attribútum** – Ha kötegattribútumon szeretné rögzíteni a teszteredményeket, jelölje ki itt az attribútumot, és jelölje be a **Készlet kötegattribútumának frissítése** jelölőnégyzetet.
    - **Készlet kötegattribútumának frissítése** – jelölje be ezt a jelölőnégyzetet azon kötegattribútum teszteredményeinek rögzítéséhez, amely ki van jelölve az **Attribútum** mezőben.

1. A lap alsó részén válassza az **Általános** lapot. Az **Áttekintés** lapon kiválasztott teszt néhány beállítását itt megismétli a program. Ezenkívül a következő mezőket lehet beállítani a teszthez:

    - **Elemzési tanúsítvány jelentés** – Az *Igen* beállítással jelezheti, hogy a teszteredményeket ki kell nyomtatni az elemzési tanúsítványra. Ez a jelentés a minőségi rendelésből generálható.
    - **Művelet hiba esetén** – az *Elfogadás* vagy a *Sikertelen* beállítás kiválasztásával jelezze, hogy a tesztnek sikeresnek vagy sikertelennek kell-e lennie, ha az Elfogadható minőségi szint nem teljesül.
    - **Elfogadható minőségi szint** – Adja meg az összes teszteredmény százalékos arányát, amely megfeleltnek tekintendő a teszt sikeres teljesítéséhez.

1. A lap alsó részén, a **Teszt** lapon állítsa be a következő mezőket:

    - **Szabványos** – adja meg a teszteredményekhez várt mennyiséget (egész vagy tört). A beírt értéket a rendszer alapértelmezés szerint beírja a teszteredményekbe. Ezenkívül automatikusan be lesz állítva alapértelmezett értékként a **Min.** és a **Max.** mezőkbe.
    - **Min.** – Adja meg a teszteredmények minimálisan megengedett értékét. A megadott értéknek kisebbnek kell lennie a **Szabványos** mezőben beállított összegnél. A **Min.** mező frissítésekor a **Min. tűréshatár (%)** mező automatikusan frissül. Hasonlóan a **Min. tűrés (%)** mező frissítésekor a **Min.** mező automatikusan frissül.
    - **Max.** – Adja meg a teszteredmények maximálisan megengedett értékét. A megadott értéknek nagyobbnak kell lennie a **Szabványos** mezőben beállított összegnél. A **Max.** mező frissítésekor a **Max. tűréshatár (%)** mező automatikusan frissül. Hasonlóan a **Max. tűréshatár (%)** mező frissítésekor a **Max.** mező automatikusan frissül.
    - **Tesztműszer** – a teszthez használt eszköz kiválasztása. Ha meg van adva tesztműszer, akkor az automatikusan bekerül a teszthez a tesztcsoportba.

1. Zárja be a lapot.

## <a name="additional-resources"></a>További erőforrások

- [Minőségbiztosítási tesztműszerek](quality-management-processes.md)
- [Minőségkezelési tesztek](quality-management-processes.md)
- [Minőségbiztosítási tesztváltozók](quality-management-processes.md)
- [Minőségi társítások](quality-management-processes.md)
- [Kötegattribútumok](../production-control/batch-attributes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
