---
title: ER Pénzügyi dimenziók használata adatforrásként (4. rész – A jelentés futtatása)
description: A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője szerepkörhöz hozzárendelt felhasználó miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 917eae141bbb8792f02d3323054e2a4096dae551
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "345283"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4-run-the-report"></a>ER Pénzügyi dimenziók használata adatforrásként (4. rész: A jelentés futtatása)

[!include [task guide banner](../../includes/task-guide-banner.md)]

A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője szerepkörhöz hozzárendelt felhasználó miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként. Ezeket a lépéseket a DEMF vállalatban hajthatja végre.

A lépések végrehajtásához először hajtsa végre az „ER Pénzügyi dimenziók használata adatforrásként (3. rész: A jelentés megtervezése)” eljárás lépéseit. Emellett az alapértelmezett dokumentumtípusokat is meg kell adni az Elektronikus jelentési paraméterek lapon. Az alapértelmezett dokumentumtípusok beállítása bármely ER-konfiguráció letöltésekor és importálásakor is megtörténik. 


## <a name="run-report"></a>Futtassa a jelentést
1. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
2. A fastruktúrában bontsa ki a következőt: „Pénzügyi dimenziók mintamodell”.
3. A fastruktúrában válassza ki a következőt: „Pénzügyi dimenziók mintamodell\Főkönyvi naplójelentés”.
4. Kattintson a Futtatásra.
5. A Dimenzió neve mezőben adja meg vagy válasszon ki egy értéket.
    * Az aktuális vállalat összes dimenziójának kijelöléséhez írja be a következőt: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
6. Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.
7. Kattintson a Szűrő parancsra.
8. Jelölje ki a főkönyvi napló táblájának a sorát, és a Napló kötegszáma mezőt.
9. A Feltétel mezőbe írja be a „00057” értéket.
10. Kattintson az OK gombra.
11. Kattintson az OK gombra.
    * Tekintse át a létrehozott kimenetet. Fontos megjegyezni, hogy a kiválasztott köteg minden tranzakciójához a megfelelő dimenziók pénzügyi dimenziói jelennek meg. Futtassa a jelentést, és válasszon ki különböző dimenziókat annak a megtekintéséhez, hogy a jelentés nem függ a kiválasztott dimenziók, vagy a Dynamics 365 for Finance and Operations, Enterprise kiadás példányhoz konfigurált dimenziók számától.  

