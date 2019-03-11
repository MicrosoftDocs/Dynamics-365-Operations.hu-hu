---
title: Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. október 15.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 10/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 1d48bc4bad795611ce322b5f09b78886a50c415c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "304631"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-15-2018"></a>Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. október 15.)

[!include [banner](includes/banner.md)]

**Build 8.1.1056**

Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.


## <a name="changes"></a>Változások
Az egyéb javításokon kívül ebben a verzióban a következő frissítések történtek:
- Az Utolsó ledolgozott nap most beállításara kerül egy munkaviszony megszűnési dátumának megadásakor.
- Egyesült Államokbeli megfelelési hivatkozások eltávolítása ha a vállalat nem az Egyesült Államokban van (KTB ADA és I9).
- Az érvénytelen dátumok (1/1/1900) analitika lapokon el vannak rejtve.

## <a name="known-issue"></a>Ismert probléma

**Probléma:** Amikor új mellékletet ad egy dolgozóhoz, az **Új** és **Szerkesztés** gombok kiszürkítve jelennek meg. **Megoldás:** Mielőtt megnyitná a melléklet lapját, győződjön meg róla, hogy be vannak zárva a **Dolgozó** lap ténymezői. Ha a ténymezők be vannak zárva, amikor a **Dolgozó** lap be van töltve, akkor a mellékletek gombjai engedélyezettek. (Ezt a problémát kijavítjuk a következő platformfrissítéssel.)
