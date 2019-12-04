---
title: Projektbecslések közvetlen szinkronizálása a Project Service Automation alkalmazásból közvetlenül a Finance and Operations alkalmazásba
description: Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Project Service Automation projektóra becsléseinek és projektköltség becsléseinek közvetlenül a Microsoft Dynamics 365 Finance szolgáltatásba történő szinkronizálására használatosak.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: ebf0fce60ad006e798aa4f404fbffcf10a0b31f9
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770289"
---
# <a name="synchronize-project-estimates-directly-from-project-service-automation-to-finance-and-operations"></a>Projektbecslések közvetlen szinkronizálása a Project Service Automation alkalmazásból közvetlenül a Finance and Operations alkalmazásba

[!include[banner](../includes/banner.md)]

Ez a témakör bemutatja a sablonokat és a mögöttes feladatokat, amelyek a Dynamics 365 Project Service Automation projektóra becsléseinek és projektköltség becsléseinek közvetlenül a Dynamics 365 Finance szolgáltatásba történő szinkronizálására használatosak.

> [!NOTE]
> - Ha a 8.0-ás verzióját használja a projektfeladat integrációja, költségtranzakció-kategóriák, munkaóra-becslés, költségbecslések és a funkciók zárolása funkciókat is használhatja.
> - Tényleges integráció a 8.0.1 vagy újabb verzióiban érhető el.

## <a name="data-flow-for-project-service-automation-to-finance"></a>Adatáramlás a Project Service Automation és a Finance között

A Project Service Automation és a Finance közötti integrációs megoldás az adatintegrációs funkciót használja a Project Service Automation és Finance példányok közötti szinkronizáláshoz. Az integrációs sablonok, amelyek elérhetőek az adatintegrációs funkcióval lehetővé teszik a projekt becsült óráival és projektek becsült kiadásaival kapcsolatos adatáramlást a Project Service Automation és Finance alkalmazások között.

A következő ábra bemutatja a Project Service Automation és a Finance közötti adatszinkronizálást.

[![Adatáramlás a Project Service Automation és a Finance integrációjához](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)

## <a name="project-hour-estimates"></a>Projektórabecslések

### <a name="template-and-tasks"></a>Sablon és feladatok

A rendelkezésre álló sablonok eléréséhez a Microsoft Power Apps adminisztrációs központban válassza a **Projektek** lehetőséget, majd kattintson a jobb felső sarkában **Új projekt** lehetőségre a nyilvános sablonok kiválasztásához.

A következő sablon és alapul szolgáló feladatok használhatók a projekt becsült óráinak szinkronizálásához a Project Service Automation és Finance között:

- **Sablon neve az adatintegrációban:** Projekt becsült órái (PSA to Fin and Ops)
- **A projekt tevékenységeinek nevei:**

    - Tranzakciókapcsolatok
    - Költségbecslések

### <a name="entity-set"></a>Entitás beállítása

| Project Service Automation | Pénzügy                                       |
|----------------------------|-----------------------------------------------|
| Projektfeladatok              | Projekt becsült óráihoz tartozó integrációs entitás |

### <a name="entity-flow"></a>Entitás folyamata

A projekt becsült óráinak kezelése a Project Service Automation alkalmazásban történik, majd ezek szinkronizálva lesznek a Finance alkalmazásba projekt óra-előrejelzéseinek.

### <a name="prerequisites"></a>Előfeltételek

A projekt becsült óráinak szinkronizálása előtt, a projekteket, projektfeladatokat és projektköltésgtranzakció-kategóriákat szinkronizálni kell.

### <a name="power-query"></a>Power Query

A Microsoft Power Query for Excelt a következőkre kell használnia a becsült projektórák sablonban ezen feladatok elvégzéséhez:

- Állítsa az alapértelmezett lőrejelzési modell azonosítója elemet, ezt használja az integráció új óra-előrejelzések létrehozásakor.
- Szűrjön ki minden erőforrás-specifikus rekordot a feladatban, melyek miatt az óra-előrejelzésekbe integrálása sikertelen lesz.
- Szűrke ki az összes üres tranzakció kategóriasort. A feladat elvégzésének elmulasztása esetben ez hibás óra-előrejelzések eredményezhet.

#### <a name="set-the-default-forecast-model-id"></a>Az alapértelmezett előrejelzési modell beállítása.

A beszúrt alapértelmezett modellazonosító frissítéséhez a sablonban, kattintson a **Hozzárendelés** nyílra a hozzárendelés megnyitásához. Majd válassza ki a **Speciális lekérdezés és szűrés** hivatkozást.

- Ha az alapértelmezett becsült projektórák (PSA to Fin and Ops) sablont használ, jelölje be a **Beszúrt feltétel** elemet az **Alkalmazott lépések** listában. Az **Funkció** bejegyzésben, cseréje az **O\_forecast** elemet az lőrejelzési modell azonosítója elemre, melyet használni kell, hogy az integrációhoz. Az alapértelmezett sablon tartalmaz előrejelzési modellazonosítót a bemutató adatokból.
- Új sablon létrehozásakor, hozzá kell adnia ezt az oszlopot. A Power Queyben, jelölje be a **Feltételes oszlop hozzáadása**, elemet és adjon meg egy nevet az új oszlopnak, például **ModelID**. Adjon meg egy feltételt az oszlophoz: ha Projektfeladat nem nulla, akkor \<adja meg az előrejelzési modell azonosítóját\>; máskülönben nulla..

#### <a name="filter-out-resource-specific-records"></a>Erőforrásspecifikus rekordok kiszűrése

A Projekt becsült órái (PSA to Fin and Ops) sablonjának van egy alapértelmezett szűrője erőforrásspecifikus rekordok eltávolítására. Ha saját sablont hoz létre, hozzá kell adnia ezt a szűrőt. Jelölje be a **Speciális lekérdezési és szűrés** hivatkozást az **msdyn\_islinetask** oszlop a szűréséhez, hogy csak **Hamis** rekordokat tartalmazzon.

#### <a name="filter-out-empty-transaction-category-rows"></a>Az üres tranzakció kategóriasorok kiszűrése

Meg kell adnia egy szűrőt, hogy eltávolítsa az üres tranzakciókategóriákat tartalmazó sorokat. Ez a feladat szükséges, függetlenül attól, hogy alapértelmezett sablont használ vagy saját sablont hoz létre. Ezzel szűrővel eltávolít minden a Project Service Automation alkalmazásból érkező sort, melyek helytelen óra-előrejelzéseket okozhatnak a Finance alkalmazásban. A **Speciális lekérdezési és szűrési képernyőn** válassza ki, hogy szűrje a **msdyn\_transactioncategory\_value** oszlop nulla rekordjait.

### <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrán egy példát mutat a sablonfeladat hozzárendelésére az Adatintegrációban A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Project Service Automation – Finance irányban.

[![Sablon-hozzárendelés](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)

## <a name="project-expense-estimates"></a>Projektköltség-becslések

### <a name="template-and-tasks"></a>Sablon és feladatok

A következő sablon és alapul szolgáló feladatok használhatók a projekt becsült költségeinek szinkronizálásához a Project Service Automation és Finance között:

- **Sablon neve az adatintegrációban:** Projekt becsült kiadásai (PSA to Fin and Ops)
- **A projekt tevékenységeinek nevei:**

    - Tranzakciókapcsolatok 
    - Költségbecslések

### <a name="entity-set"></a>Entitás beállítása

| Project Service Automation | Pénzügy                                                  |
|----------------------------|----------------------------------------------------------|
| Tranzakciók kapcsolatai    | Projekttranzakció-kapcsolatok integrációs entitása |
| Becslési sorok             | Projekt becsült kiadásához tartozó integrációs entitás         |

### <a name="entity-flow"></a>Entitás folyamata

A projekt becsült kiadásainak kezelése a Project Service Automation alkalmazásban történik, majd ezek szinkronizálva lesznek a Finance alkalmazásba projektköltség-előrejelzésekként.

### <a name="prerequisites"></a>Előfeltételek

A projekt becsült kiadásai szinkronizálása előtt, a projekteket, projektfeladatokat és projektköltségtranzakció-kategóriákat szinkronizálni kell.

### <a name="power-query"></a>Power Query

A Microsoft Power Query-t kell használnia a Projekt becsült kiadásainak sablonjában a következő feladatok elvégzéséhez:

- Szürés, hogy csak költségbecslési sor rekordok kerüljenek bele.
- Állítsa az alapértelmezett lőrejelzési modell azonosítója elemet, ezt használja az integráció új óra-előrejelzések létrehozásakor.
- A számlázási típusok átalakítása.
- A tranzakciótípusok átalakítása.

#### <a name="filter-to-include-only-expense-estimate-lines"></a>Szürés, hogy csak költségbecslési sorok kerüljenek bele

A projekt becsült kiadásai (PSA to Fin and Ops) sablonjának van egy alapértelmezett szűrője, mellyel csak a kiadási sorok szerepelnek az integrációban. Ha saját sablont hoz létre, hozzá kell adnia ezt a szűrőt. Válassza ki a **Tranzakciókapcsolatok** feladatot, majd kattintson a **Hozzárendelés** nyílra a hozzárendelés megnyitásához. Válassza ki a **Speciális lekérdezés és szűrés** hivatkozást. Szűrje az **msdyn\_transactiontype1** oszlopot, hogy csak az **msdyn\_estimateline** elemet tartalmazza.

#### <a name="set-the-default-forecast-model-id"></a>Az alapértelmezett előrejelzési modell beállítása.

A beszúrt alapértelmezett modellazonosító frissítéséhez a sablonban válassza a **Költségbecslések** feladatot, majd kattintson a **Hozzárendelés** nyílra a hozzárendelés megnyitásához. Válassza ki a **Speciális lekérdezés és szűrés** hivatkozást.

- Ha az alapértelmezett Projekt becsült kiadásai (PSA to Fin and Ops) sablont használja, a Power Query-ben jelölje be az első **Beszúrt feltétel** elemet az **Alkalmazott lépések** szakaszból. Az **Funkció** bejegyzésben, cseréje az **O\_forecast** elemet az lőrejelzési modell azonosítója elemre, melyet használni kell, hogy az integrációhoz. Az alapértelmezett sablon tartalmaz előrejelzési modellazonosítót a bemutató adatokból.
- Új sablon létrehozásakor, hozzá kell adnia ezt az oszlopot. A Power Queyben, jelölje be a **Feltételes oszlop hozzáadása**, elemet és adjon meg egy nevet az új oszlopnak, például **ModelID**. Adjon meg egy feltételt az oszlophoz, ahol a Becslés sorazonosítója nem nulla, akkor \<adja meg az előrejelzési modell azonosítóját\>; máskülönben nulla..

#### <a name="transform-the-billing-types"></a>A számlázási típusok átalakítása

A projekt költség becslése (PSA to Fin and Ops) sablon tartalmaz egy feltételes oszlopot, mely átalakítja a Project Service Automation alkalmazásból kapott számlatípusokat az integráció során. Ha saját sablont hoz létre, hozzá kell adnia ezt a feltételes oszlopot. Válassza a **Speciális lekérdezési és szűrés** hivatkozást, majd válassza a **Feltételes oszlop hozzáadása** lehetőséget. Adjon meg egy nevet az új oszlopnak, például **BillingType**. Adja meg a következő feltételt:

If **msdyn\_billingtype** = 192350000, then **NonChargeable**  
else if **msdyn\_billingtype** = 192350001, then **Chargeable**  
else if **msdyn\_billingtype** = 192350002, then **Complimentary**  
else **NotAvailable**

#### <a name="transform-the-transaction-types"></a>A tranzakciótípusok átalakítása

A projekt költség becslése (PSA to Fin and Ops) sablon tartalmaz egy feltételes oszlopot, mely átalakítja a Project Service Automation alkalmazásból kapott tranzakciótípusokat az integráció során. Ha saját sablont hoz létre, hozzá kell adnia ezt a feltételes oszlopot. Válassza a **Speciális lekérdezési és szűrés** hivatkozást, majd válassza a **Feltételes oszlop hozzáadása** lehetőséget. Adjon meg egy nevet az új oszlopnak, például **TransactionType**. Adja meg a következő feltételt:

If **msdyn\_transactiontypecode** = 192350000, then **Cost**  
else if **msdyn\_transactiontypecode** = 192350005, then **Sales**  
else **null**

### <a name="template-mapping-in-data-integration"></a>Sablonleképezés az adatintegrátorban

Az alábbi ábrán példákat láthat sablonfeladatok hozzárendelésére az Adatintegrációban A leképezés mutatja, hogy melyik mezőadatok szinkronizálódnak a Project Service Automation – Finance irányban.

[![Sablon-hozzárendelés](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)

[![Sablon-hozzárendelés](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)
