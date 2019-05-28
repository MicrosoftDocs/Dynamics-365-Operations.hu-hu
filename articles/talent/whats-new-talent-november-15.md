---
title: Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. november 15.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 11/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b90d4230fe1e666aba4075670f6df206e8df7ce9
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518195"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-november-15-2018"></a>Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. november 15.)

[!include [banner](includes/banner.md)]

**Build 8.1.2045**

Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.

## <a name="other-changesfixes"></a>Egyéb változtatások/javítások

### <a name="unable-to-change-employees-current-position-to-a-future-open-position"></a>Nem lehet módosítani az alkalmazott aktuális beosztását egy jövőbeli nyitott pozícióra

Módosítás történt a beosztástranszferek módosítása érdekében, amikor a beosztás csak a jövőben válik elérhetővé. 

### <a name="position-does-not-display-when-creating-a-new-employee"></a>A beosztás nem jelenik meg az új alkalmazott létrehozásakor

Módosítás történt, és ezentúl az összes nyitott pozíció megjelenik, amelyek társításra elérhetők, amikor új alkalmazottat vesznek fel a Talent alkalmazásban. Ez a korábbi beosztásokat is, és a jövőre dátumozott beosztásokat is tartalmazza. A beosztások most helyesen jelennek meg az alkalmazotti jogviszony kezdési dátum alapján. 

### <a name="termination-date-is-displaying-based-on-user-settings"></a>A munkaviszony megszűnésének dátuma a felhasználói beállításoktól függően jelenik meg

Módosítás történt, és ezentúl a múltbéli alkalmazottak listája tükrözni fogja a felhasználó előnyben részesített időzónájához való eltolódást a munkaviszony megszűnésének dátumának megtekintésekor.

### <a name="work-items-assigned-to-me-links-not-displaying-the-correct-information"></a>Hozzám rendelt munkaelemek hivatkozásai nem a helyes információt jelenítik meg

A módosítással után a listában található egyéni munkaelemek részleteire való navigáció a helyes információt jeleníti meg a kiválasztott elemhez. A probléma csak speciális biztonsági beállítások esetén fordult elő.


## <a name="known-issue"></a>Ismert probléma

- **Probléma**:Egy új csatolmány hozzáadásakor egy dolgozóhoz az **Új** és **Szerkesztés** gombok szürkén jelennek meg. 
- **Megoldás:** A melléklet lap megnyitása, előtt ellenőrizze, hogy az adatterületek a **Dolgozó** lapon le vannak-e zárva. Ha a ténymezők be vannak zárva, amikor a **Dolgozó** lap be van töltve, akkor a mellékletek gombjai engedélyezettek. (Ezt a problémát kijavítjuk a következő platformfrissítéssel.)
