--- 
title: "Vízszintesen bővíthető tartományokat használó formátum futtatása oszlopok Excel-kimutatásokba történő dinamikus hozzáadásához az elektronikus jelentéskészítéshez (ER)"
description: "Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat elektronikus jelentési (ER) formátumot jelentések létrehozásához OPENXML munkalap (Excel) fájlok formájában, amelyekben a szükséges oszlopok vízszintesen bővíthető tartományokként, dinamikusan hozhatók létre."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 4b859151edd28e39c1f97b2f600da6e304b1d065
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="run-a-format-that-uses-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-for-electronic-reporting-er"></a>Vízszintesen bővíthető tartományokat használó formátum futtatása oszlopok Excel-kimutatásokba történő dinamikus hozzáadásához az elektronikus jelentéskészítéshez (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat elektronikus jelentési (ER) formátumot jelentések létrehozásához OPENXML munkalap (Excel) fájlok formájában, amelyekben a szükséges oszlopok vízszintesen bővíthető tartományokként, dinamikusan hozhatók létre. Ezeket a lépéseket a DEMF vállalatban hajthatja végre.

Ezeknek a lépéseknek a végrehajtásához először hajtsa végre az „ER Vízszintesen bővíthető tartományok használata oszlopok Excel-kimutatásokba történő dinamikus hozzáadásához (1. rész: Formátum kialakítása)” eljárás lépéseit.

Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.


## <a name="find-created-format"></a>Létrehozott formátum keresése
1. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
2. A fastruktúrában bontsa ki a következőt: „Pénzügyi dimenziók mintamodell”.
3. A fastruktúrában válassza ki a következőt: „Pénzügyi dimenziók mintamodell\Mintajelentés vízszintesen bővíthető tartományokkal”.

## <a name="execute-format-to-create-excel-output"></a>Formátum végrehajtása Excel-kimenet létrehozásához
1. Kattintson a Futtatás elemre.
2. A Dimenzió neve mezőbe írja be a következőt: „BusinessUnit;CostCenter;Osztály”.
    * A Dimenzió mezőben adjon meg vagy válasszon ki egy értéket.  Az aktuális vállalat összes dimenziójának kijelöléséhez írja be a következőt: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
3. Bontsa ki a Szerepeltetni kívánt rekordok szakaszt.
4. Kattintson a Szűrő parancsra.
5. Jelölje ki a főkönyvi napló táblájának a sorát, és a Napló kötegszáma mezőt.
6. A Feltétel mezőbe írja be a következőt: „00057..00058”.
    * 00057..00058  
7. Kattintson az OK gombra.
8. Kattintson az OK gombra.
    * Tekintse át a létrehozott kimenetet. Fontos megjegyezni, hogy az újonnan létrehozott Excel-fájl a pénzügyi dimenzióknál kijelölttel azonos számú oszlopot tartalmaz. A jelentés fejléce az oszlopokban a pénzügyi dimenziók nevét jelöli. A tranzakciók sorai az oszlopokban a pénzügyi dimenziókat jelölik. Futtassa a jelentést, és válasszon ki különböző dimenziókat annak a megtekintéséhez, hogy a jelentés nem függ a kiválasztott dimenziók, vagy a Dynamics 365 for Finance and Operations Enterprise kiadás példányhoz konfigurált dimenziók számától.  


