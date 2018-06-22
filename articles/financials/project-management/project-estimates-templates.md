---
title: "Projektbecslések szinkronizálása a Project Service Automation alkalmazásból közvetlenül a Finance and Operations projekt-előrejelzéseibe"
description: "Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a projekt becsült óráinak és projektek becsült kiadásainak a Microsoft Dynamics 365 for Project Service Automation és a Microsoft Dynamics 365 for Finance and Operations közötti szinkronizálásra használhatók."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 90501f40da0fdc66ad087b3bd746c908cc25711b
ms.contentlocale: hu-hu
ms.lasthandoff: 05/29/2018

---
# <a name="synchronize-project-estimates-from-project-service-automation-directly-to-project-forecasts-in-finance-and-operations"></a>Projektbecslések szinkronizálása a Project Service Automation alkalmazásból közvetlenül a Finance and Operations projekt-előrejelzéseibe

Ez a témakör azokat a sablonokat és kapcsolódó feladatokat mutatja be, melyek a projekt becsült óráinak és projektek becsült kiadásainak a Microsoft Dynamics 365 for Project Service Automation és a Microsoft Dynamics 365 for Finance and Operations közötti szinkronizálásra használhatók.

> [!NOTE]
> Projektfeladatok integrációja, költségtranzakció-kategóriák, munkaóra-becslés, költségbecslések és a funkciók zárolása a Dynamics 365 for Finance and Operations 8.0-ás verziójában érhető el.


## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Adatáramlás a Project Service Automation és a Finance and Operations között

A Project Service Automation és Finance and Operations közötti integrációs megoldása az adatintegrációs funkciót használja a Project Service Automation and Finance és Operations példányok közötti szinkronizáláshoz. Az integrációs sablonok, amelyek elérhetőek az adatintegrációs funkcióval lehetővé teszik a projekt becsült óráival és projektek becsült kiadásaival kapcsolatos adatáramlást a Project Service Automation és Finance and Operations alkalmazások között.

A következő ábra bemutatja a Project Service Automation és a Finance and Operations közötti adatszinkronizálást.

[![Adatáramlás a Project Service Automation és a Finance and Operations integrációjához](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)


## <a name="templates-and-tasks"></a>Sablonok és feladatok

A rendelkezésre álló sablonok eléréséhez a Microsoft PowerApps Admin Centerben válassza a **Projektek** lehetőséget, majd ezután kattintson a jobb felső sarkában **Új projekt** lehetőségre a nyilvános sablonok kiválasztásához.

A következő sablon és alapul szolgáló feladatok használhatók a projekt becsült óráinak szinkronizálásához a Project Service Automation és Finance and Operations között:

-  **Sablon neve az adatintegrációban:** Projekt becsült órái (PSA to Fin and Ops)

-  **A projekt tevékenységeinek nevei:** 
    - Tranzakciókapcsolatok 
    - Költségbecslések

## <a name="entity-set"></a>Entitás beállítása

| Projekt szolgáltatásautomatizálása      | Finance and Operations                          |
|---------------------------------|-------------------------------------------------|
| Projektfeladatok                   | Projekt becsült óráihoz tartozó integrációs entitás   |

## <a name="entity-flow"></a>Entitás folyamata

A projekt becsült óráinak kezelése a Project Service Automation alkalmazásban történik, majd ezek szinkronizálva lesznek a Finance and Operations alkalmazásba projekt óra-előrejelzéseinek.

## <a name="preconditions"></a>Előfeltételek

A projekt becsült óráinak szinkronizálása előtt, a projekteket, projektfeladatokat és projektköltésgtranzakció-kategóriákat szinkronizálni kell.

## <a name="power-query"></a>Power Query

A Microsoft Power Query-t a következőkre kell használnia a becsült projektórák sablonban:
- Állítsa az **Előrejelzési modell azonosítója** elemet, ezt használja az integráció új óra-előrejelzések létrehozásakor.
- Szűrjön ki minden erőforrás-specifikus rekordot a feladatban, melyek miatt az óra-előrejelzésekbe integrálása sikertelen lesz.
- Szűrke ki az összes üres tranzakció kategóriasort. Ellenkező esetben ez hibás óra-előrejelzések eredményezhet.

### <a name="forecast-model-id"></a>Előrejelzési modell azonosítója
A beszúrt alapértelmezett modellazonosító frissítéséhez a sablonban, kattintson a **Hozzárendelés** nyílra a hozzárendelés megnyitásához. Válassza ki a Speciális lekérdezés és szűrés megnyitásához.
- Ha az alapértelmezett Microsoft becsült projektórák (PSA to Fin and Ops) sablont használ, jelölje be a **Beszúrt feltétel** elemet az **Alkalmazott lépések** szakaszban. Az **Funkció** bejegyzésben, cseréje az **O_forecast** elemet az **Előrejelzési modell azonosítója** elemre, melyet használni kell, hogy az integrációhoz. Az alapértelmezett sablon tartalmaz előrejelzési modellazonosítót a bemutató adatokból.
- Új sablon létrehozásakor, hozzá kell adnia ezt az oszlopot. Válassza a **Feltételes oszlop hozzáadása** elemet, és adjon egy nevet az oszlopnak, például ModelID. Adja meg a feltételt az oszlohoz: if Project task is not null, then<enter the forecast model ID>; else null.

### <a name="filter-out-resource-specific-records"></a>Erőforrásspecifikus rekordok kiszűrése
A Projekt becsült órái (PSA to Fin and Ops) sablonjának van egy alapértelmezett szűrője erőforrásspecifikus rekordok eltávolítására. Ha saját sablont hoz létre, hozzá kell adnia ezt a szűrőt. Speciális lekérdezési és szűrési képernyőn, jelölje be az **msdyn_islinetask** oszlop a szűrését, hogy csak **hamis** rekordokat tartalmazzon.

### <a name="filter-out-empty-transaction-category-rows"></a>Az üres tranzakció kategóriasorok kiszűrése
Meg kell adnia egy szűrőt, hogy eltávolítsa az üres tranzakciókategóriákat tartalmazó sorokat. Ez szükséges, függetlenül az alapértelmezett sablont használ vagy saját sablont hoz létre. Ezzel a szűrővel eltávolít minden a Project Service Automation alkalmazásból érkező sort, melyek helytelen óra-előrejelzéseket okozhatnak a Finance and Operations alkalmazásban. A speciális lekérdezési és szűrési képernyőn válassza ki, hogy szűrje a **msdyn_transactioncategory_value** oszlop nulla rekordjait.

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrán egy példát mutat a sablonfeladat hozzárendelésére az Adatintegrációban A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Project Service Automation – Finance and Operations irányban.

[![Sablon-hozzárendelés](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)

A következő sablon és alapul szolgáló feladat használható az aktuális projektköltség-becslések szinkronizálásához a Project Service Automation és a Finance and Operations között:

-  **Sablon neve az adatintegrációban:** Projekt becsült kiadásai (PSA to Fin and Ops)
-  **A projekt tevékenységeinek nevei:** 
     - Tranzakciókapcsolatok 
     - Költségbecslések

## <a name="entity-set"></a>Entitás beállítása

| Projekt szolgáltatásautomatizálása      | Finance and Operations                                     |
|---------------------------------|------------------------------------------------------------|
| Tranzakciók kapcsolatai         | Projekttranzakció-kapcsolatok integrációs entitása.   |
| Becslési sorok                  | Projekt becsült kiadásához tartozó integrációs entitás.           |

## <a name="entity-flow"></a>Entitás folyamata

A projekt becsült kiadásainak kezelése a Project Service Automation alkalmazásban történik, majd ezek szinkronizálva lesznek a Finance and Operations alkalmazásba projektköltség-előrejelzésekként.

## <a name="prerequisites"></a>Előfeltételek

A projekt becsült kiadásainak szinkronizálása előtt, a projekteket, projektfeladatokat és projektköltségtranzakció-kategóriákat szinkronizálni kell.

## <a name="power-query"></a>Power Query

A Microsoft Power Query-t a következőkre kell használnia a Projekt becsült kiadásainak sablonjában:
- Szürés, hogy csak költségbecslési sor rekordok kerüljenek bele
- Állítsa az **Előrejelzési modell azonosítója** elemet, ezt használja az integráció új óra-előrejelzések létrehozásakor.
- A számlázási típusok átalakítása.
- A tranzakciótípusok átalakítása.

### <a name="filter-to-include-only-expense-estimate-lines"></a>Szürés, hogy csak költségbecslési sorok kerüljenek bele
A projekt becsült kiadásai (PSA to Fin and Ops) sablonjának van egy alapértelmezett szűrője, hogy csak a kiadási sorok szerepeljenek az integrációban. Ha saját sablont hoz létre, hozzá kell adnia ezt a szűrőt. Válassza ki a Tranzakciókapcsolatok feladatot, majd kattintson a **Hozzárendelés** nyílra. Válassza **Speciális lekérdezés és szűrés** lehetőséget. Szűrje a **msdyn_transactiontype1** oszlopot, hogy csak a **msdyn_estimateline** elemet tartalmazza.

### <a name="forecast-model-id"></a>Előrejelzési modell azonosítója
A beszúrt alapértelmezett modellazonosító frissítéséhez a sablonban, a Költségbecslések feladatban, kattintson a **Hozzárendelés** nyílra a hozzárendelés megnyitásához. Válassza ki a Speciális lekérdezés és szűrés megnyitásához.
- Ha az alapértelmezett Microsoft Projekt becsült kiadásai (PSA to Fin and Ops) sablont használja , jelölje be az első **Beszúrt feltétel** elemet az **Alkalmazott lépések** szakaszban. Az **Funkció** bejegyzésben, cseréje az **O_forecast** elemet az **Előrejelzési modell azonosítója** elemre, melyet használni kell, hogy az integrációhoz. Az alapértelmezett sablon tartalmaz előrejelzési modellazonosítót a bemutató adatokból.
- Új sablon létrehozásakor, hozzá kell adnia ezt az oszlopot. Válassza a **Feltételes oszlop hozzáadása** elemet, és adjon egy nevet az oszlopnak, például ModelID. Adjon meg egy feltételt az oszlophoz: ha Becslés sorazonosítója nem nulla, akkor< adja meg az előrejelzési modell azonosítóját>; máskülönben nulla..

### <a name="transform-the-billing-types"></a>A számlázási típusok átalakítása
A projekt költség becslése (PSA to Fin and Ops) sablonhoz tartozik egy feltételes oszlop mely átalakítja a Project Service Automation alkalmazásból kapott számlatípusokat az integráció során.
- Ha saját sablont hoz létre, hozzá kell adnia ezt a feltételes oszlopot. A speciális lekérdezési és szűrési képernyőjén válassza a **Feltételes oszlop hozzáadása** lehetőséget. Adjon meg egy nevet az oszlopnak, például „BillingType”. A megadandó feltétel a következő:

    If **msdyn_billingtype** = 192350000, then **NonChargeable** else if **msdyn_billingtype** = 192350001, then **Chargeable** else if **msdyn_billingtype** = 192350002, then **Complimentary** else **NotAvailable**

### <a name="transform-the-transaction-types"></a>A tranzakciótípusok átalakítása
A projekt költség becslése (PSA to Fin and Ops) sablonhoz tartozik egy feltételes oszlop mely átalakítja a Project Service Automation alkalmazásból kapott tranzakciótípusokat az integráció során.
- Ha saját sablont hoz létre, hozzá kell adnia ezt a feltételes oszlopot. A speciális lekérdezési és szűrési képernyőjén válassza a **Feltételes oszlop hozzáadása** lehetőséget. Adjon meg egy nevet az új oszlopnak, például „TransactionType”. A megadandó feltétel a következő: If **msdyn_transactiontypecode** = 192350000, then **Cost** else if **msdyn_transactiontypecode** = 192350005, then **Sales** else **null**

## <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrán példákat láthat sablonfeladatok hozzárendelésére az Adatintegrációban A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Project Service Automation – Finance and Operations irányban.

[![Sablon-hozzárendelés](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)

[![Sablon-hozzárendelés](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)




