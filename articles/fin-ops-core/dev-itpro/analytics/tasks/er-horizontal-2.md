---
title: ER Vízszintesen bővíthető tartományok használata oszlopok Excel-kimutatásokba történő dinamikus hozzáadásához (2. rész – Formátum futtatása)
description: Ez a témakör azt mutatja be, hogyan kell konfigurálni egy elektronikus jelentésformátumot (ER), amely OPENXML-munkalapfájlként (Excel) formátumú jelentéseket hoz létre. (2. rész)
author: kfend
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERSolutionTable, SysQueryForm
ms.openlocfilehash: 08755eafa2a18993ba669f0deccd75477bfae410
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290394"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-2---run-format"></a>ER Vízszintesen bővíthető tartományok használata oszlopok Excel-kimutatásokba történő dinamikus hozzáadásához (2. rész – Formátum futtatása)

[!include [banner](../../includes/banner.md)]

Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat elektronikus jelentési (ER) formátumot jelentések létrehozásához OPENXML munkalap (Excel) fájlok formájában, amelyekben a szükséges oszlopok vízszintesen bővíthető tartományokként, dinamikusan hozhatók létre. Ezeket a lépéseket a DEMF vállalatban hajthatja végre.

Ezeknek a lépéseknek a végrehajtásához először hajtsa végre az „ER Vízszintesen bővíthető tartományok használata oszlopok Excel-kimutatásokba történő dinamikus hozzáadásához (1. rész: Formátum kialakítása)” eljárás lépéseit.

Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.


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
    * Tekintse át a létrehozott kimenetet. Fontos megjegyezni, hogy az újonnan létrehozott Excel-fájl a pénzügyi dimenzióknál kijelölttel azonos számú oszlopot tartalmaz. A jelentés fejléce az oszlopokban a pénzügyi dimenziók nevét jelöli. A tranzakciók sorai az oszlopokban a pénzügyi dimenziókat jelölik. Futtassa a jelentést, és válasszon ki különböző dimenziókat annak a megtekintéséhez, hogy a jelentés nem függ a kiválasztott dimenziók, vagy a példányhoz konfigurált dimenziók számától.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
