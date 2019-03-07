---
title: Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. január 31.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 1/31/2019
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
ms.search.validFrom: 2019-01-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 5c9449e2bdec8c17cc2cf659ed68ac1d713a26ad
ms.sourcegitcommit: 1e32d78868098fd76124bb41363f15c4ec3ea15a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2019
ms.locfileid: "374734"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-january-31-2019"></a>Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. január 31.)

[!include [banner](includes/banner.md)]

Ez a témakör a Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.

**Build 8.1.2128**

## <a name="core-hr-changes"></a>Core HR módosításai

### <a name="time-off-taken-on-leave-people-card-doesnt-consider-leave-plan-dates"></a>Az emberek szabadsága kártyán kivett szabadság nem veszi figyelembe a szabadságterv dátumait
Azoknál akiknek szabadságterve nem naptári év szerinti a **Kivett** kártya megjeleníti a szabadságot, amely a tervben definiált szabadságévben lett kivéve. Például ha egy szervezet szabadságéve június 1. és május 30. között van és egy alkalmazottnak kivett 3 napot decemberben, a **Kivett** kártya január 15-én, 3 napot jelenít meg. 

### <a name="accrual-amounts-not-matching-tier-date-basis"></a>A könyvelési összegek nem egyeznek szintdátum alapjával
Új lehetőségek lettek hozzáadva szabadsághoz és távolléthez (**Emberierőforrás** paraméterek) , hogy az ügyfelek meghatározhassák, mikor legegyen érvényes a munkavállalók szolgálati hónap dátuma. Egyes szervezeteknél ez a dátum a hónap vége, de másoknál lehet a következő hónap kezdete. Például egy szervezet szabadságot ad ki December 31-én, míg a másik január 1-jén. Ez a beállítás lehetővé teszi, hogy kiválassza mikor legyen kiadva. 

### <a name="worker-hire-actions-are-stuck-in-workflow-complete-state"></a>Dolgozói felvételi műveletek elakadnak a "Munkafolyamat befejeződött" állapotban.
Módosítások történtek azon hiba javítása érdekében, ahol néhány munkafolyamat a „Munkafolyamat befejeződött” állapottal fejeződött be. Az munkafolyamatok most átkerülnek a „Befejeződött” állapotba, amikor a munkafolyamat befejeződik. Az összes munkafolyamat befejezve állapotú munkafolyamat hibaállapotba kerül, hogy lehetséges legyen a frissítés vagy eltávolítás. 
