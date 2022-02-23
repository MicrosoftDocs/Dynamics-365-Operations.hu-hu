---
title: Új vagy módosult elemek a Dynamics 365 Talent – Core HR szolgáltatásban (2018. október 15.)
description: Ez a témakör a Microsoft Dynamics 365 Talent – Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 10/15/2018
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
ms.search.validFrom: 2018-10-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 96f877ae284a0f914bae2d0f5e5f7caf49109511
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461378"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-october-15-2018"></a>Új vagy módosult elemek a Dynamics 365 Talent – Core HR szolgáltatásban (2018. október 15.)

**Build 8.1.1056**

Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.


## <a name="changes"></a>Változások
Az egyéb javításokon kívül ebben a verzióban a következő frissítések történtek:
- Az Utolsó ledolgozott nap most beállításara kerül egy munkaviszony megszűnési dátumának megadásakor.
- Egyesült Államokbeli megfelelési hivatkozások eltávolítása ha a vállalat nem az Egyesült Államokban van (KTB ADA és I9).
- Az érvénytelen dátumok (1/1/1900) analitika lapokon el vannak rejtve.

## <a name="known-issue"></a>Ismert probléma

**Probléma:** Amikor új mellékletet ad egy dolgozóhoz, az **Új** és **Szerkesztés** gombok kiszürkítve jelennek meg. **Megoldás:** Mielőtt megnyitná a melléklet lapját, győződjön meg róla, hogy be vannak zárva a **Dolgozó** lap ténymezői. Ha a ténymezők be vannak zárva, amikor a **Dolgozó** lap be van töltve, akkor a mellékletek gombjai engedélyezettek. (Ezt a problémát kijavítjuk a következő platformfrissítéssel.)
