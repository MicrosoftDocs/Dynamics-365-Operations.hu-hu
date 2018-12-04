---
title: "Termelési rendelés költségelemzése"
description: "Ez a cikk a befejezett és az aktuális termelési rendelésekhez tartozó elvégezhető költségelemzéssel kapcsolatban tartalmaz tájékoztatást. Az Árkalkuláció lap vagy a Költségbecslés és kalkulációk jelentés használatával elemezheti a becsült költségeket és a tényleges költségeket. A becsült és tényleges költségekkel (és mennyiségekkel) kapcsolatos információkat tekinthet meg minden összetevő cikknél, az útvonalműveletnél, és a közvetett költségnél."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 79634
ms.assetid: ded5da04-f787-49f7-b5e5-75c2a2b92930
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 40ac5108216fd6d9eb5cd6e76fefd66828a7da84
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="production-order-cost-analysis"></a>Termelési rendelés költségelemzése

[!include [banner](../includes/banner.md)]

Ez a cikk a befejezett és az aktuális termelési rendelésekhez tartozó elvégezhető költségelemzéssel kapcsolatban tartalmaz tájékoztatást. Az Árkalkuláció lap vagy a Költségbecslés és kalkulációk jelentés használatával elemezheti a becsült költségeket és a tényleges költségeket. A becsült és tényleges költségekkel (és mennyiségekkel) kapcsolatos információkat tekinthet meg minden összetevő cikknél, az útvonalműveletnél, és a közvetett költségnél.

A termelési rendelések tényleges költségeinek a jelentett anyag és útvonalművelet-felhasználás az alapja. A termelési rendelések jelentett anyag-, útvonalművelet- és közvetett költség-felhasználásával kapcsolatos részletes tranzakcióit **Termelés feladása** oldalon érheti el.

## <a name="variance-analysis-for-a-completed-production-order"></a>Befejezett termelési rendelés különbözet-elemzése
A különbözetek a jelentett termelési tevékenységek és a termelési cikkre vonatkozó elszámolóár-számítás összehasonlítását mutatják. A különbözetek nem a termelési rendelés becsült költségeivel való összehasonlítást tükrözik. A jelentett termelési tevékenységek közé tartozik az anyagfelhasználás, az útvonalműveletek (és a kapcsolódó közvetett költségek), a készként jelentett mennyiséggel együtt. A következő négy különbözettípus kiszámítása megy végbe:

-   Adagméret különbözete
-   Termelési mennyiségi különbözet
-   Termelési árkülönbözet
-   Termeléshelyettesítési különbözet

A következő ábra bemutatja a négyféle különbözetet, amelyek a termelési rendelés tényleges költségei, illetve a cikk költségrekordján belüli számított költségek között fellépő eltéréseket okozzák a termelési rendelés befejezésekor. 

![A termelési rendelés eltéréseit okozó különbözetek](./media/control.jpg) 

A **Különbözet** lapon vagy a **Termelési különbözet** jelentésben elemezheti a termelési különbözeteket. A megjelenítési beállítások használatával a részletes különbözetek cikkenként, üzemi erőforrásonként vagy költségcsoportonként jeleníthetők meg. A készletparaméterekben szereplő költség-alábontási szabály határozza meg, hogy a különbözetek nyomon-követése költségcsoportok szerint történik-e. Használhatja még az **egyszeres**, **többszörös**, és **teljes** megjelenítési beállításokat az összesített különbözetek megjelenítéséhez. A részletes különbözetekről szóló információk a segítségére lehetnek a különbözetek okának megértésében. Az eltérések előrejelzéséhez a termelési rendelés befejezése előtt elemezze a **Költségbecslés és kalkulációk** jelentésben található részletes információkat.

## <a name="cost-analysis-for-current-production-orders"></a>Az aktuális termelési rendelések költségelemzése
Különálló jelentések nyújtanak információt az egyes tranzakciótípusokkal kapcsolatban. A jelentett termelési tevékenységek költségeinek elemzésére használja ezeket a jelentéseket. Csak azon aktuális termelési rendelések adatai jelennek meg, amelyek állapota **Elindított** vagy**Készként jelentett**.

-   **Feldolgozás alatt lévő anyagok**− Ez a jelentés felsorolja azokat a kitárolásilista-tranzakciókat, amelyeket az aktuális termelési rendelések ellenében egy adott tranzakciódátumra jelentettek. A jelentés kimutatja egy kiadott összetevő mennyiségét és az egyes tranzakciók költségösszegét. Használja a kiválasztási feltételeket egy adott összetevő cikk eléréséhez. Például a kinyomtathatja a megfelelő termelési rendelések ellenében egy összetevő kiadott mennyiségének adatait. A kiadott mennyiség nem frissül a szülőcikkhez készként jelentett mennyiségek által. Emiatt a folyamatban lévő tényleges nyersanyagok mennyisége túlbecsült lehet.
-   **Folyamatban lévő munka**− Ez a jelentés felsorolja azokat az útvonal-tranzakciókat (vagy feladat-tranzakciókat) amelyeket az aktuális termelési rendelések ellenében egy adott tranzakciódátumra jelentettek. A jelentés kimutatja az egyes tranzakciókhoz jelentett órákat, összeget és mennyiséget (mind a helyes, mind a hibás mennyiséget). Tartalmaz továbbá olyan információkat, mint a műveletszám, művelet azonosító és üzemi erőforrás. Továbbá ez a jelentés megjeleníti a termelési rendelés ellenében létrehozott összes tranzakció teljes idejét és összegét, valamint a készként jelentett mennyiséget.
-   **Folyamatban lévő közvetett költségek**− Ez a jelentés felsorolja azokat a közvetett költségeket, amelyek a termelési rendelések ellenében felmerültek. Ezek az adatok az útvonalműveletek és összetevők jelentett felhasználásán alapulnak egy adott tranzakciódátumra vonatkozóan. Látható rajta a közvetett költség típusa (pótdíj vagy költségszorzó), a közvetett költség költségszámításitáblázat-kódja és az egyes tranzakciók költségösszege. Ez a jelentés nem szolgáltat információt arról, hogy melyik útvonalkártya vagy kitárolásilista-tranzakció generálta a közvetett költséget.
-   **Folyamatban lévő termelés költségképzése**− Ez a jelentés felsorolja a kombinált anyagfelhasználást, az útvonalműveleteket és közvetett költségeket a termelési rendelések ellenében egy adott tranzakciódátumra vonatkozóan.
-   **Feldolgozás alatt lévő késztermékek**– Ez a jelentés felsorolja az aktuális termelési rendeléseket és a készként jelentett tranzakciókat egy adott tranzakciódátumra vonatkozóan.


<a name="additional-resources"></a>További erőforrások
--------

[A termelési különbözetek gyakori okai](common-sources-of-production-variances.md)




