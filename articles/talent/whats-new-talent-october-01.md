---
title: Új vagy módosult elemek a Dynamics 365 Talent – Core HR szolgáltatásban (2018. október 1.)
description: Ez a témakör a Microsoft Dynamics 365 Talent – Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 10/01/2018
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
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f872b0907e0f48e0b734c87f0b8fb1a4cfe20cb0
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2896681"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-core-hr-october-1-2018"></a>Új vagy módosult elemek a Dynamics 365 Talent: Core HR szolgáltatásban (2018. október 1.)

**Build 8.1.1035.0**

Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.

## <a name="turn-off-electronic-payment-validation"></a>Elektronikus kifizetések érvényesítésének kikapcsolása

Az elektronikus fizetés információinak ellenőrzése akkor fordul elő, ha a közvetlen beszedések kifizetéseit vagy a **Alkalmazotti önkiszolgáló rendszer** munkaterületén (ESS), vagy közvetlenül az alkalmazotti képernypn állítja be. Ez az opció rugalmasságot biztosít az ellenőrzés eltávolításához, ha Ön nem igényli az összegek és a fennmaradó értékek ellenőrzését. Ez a funkció akkor hasznos, ha olyan külső bérszámfejtési rendszerrel integrálódik, amelyiknél eltérőek a követelmények.

## <a name="manager-self-service---add-goals-for-team-members-through-the-team-performance-goals-tile"></a>Vezetői önkiszolgáló rendszer – Célok hozzáadása a csapattagokhoz a Csapatteljesítmény célok mozaikján keresztül

A mostani verziót megelőzően a vezetők az egyes alkalmazottakhoz kapcsolódó teljesítménycélok révén egyedi célokat adhattak meg az alkalmazottaiknál. A jelen frissítéstől kezdődően a vezetők hozzáférhetnek a **Csapat teljesítménycéljai** mozaikhoz, és új célokat hozhatnak létre valamelyik közvetett beosztottjuk kiválasztását követően.

## <a name="manager-self-service---add-reviews-for-team-members-through-the-team-performance-reviews-tile"></a>Vezetői önkiszolgáló rendszer – Vélemények hozzáadása a csapattagokhoz a Csapatteljesítmény vélemények mozaikján keresztül

A mostani verziót megelőzően a vezetők az egyes alkalmazottakhoz kapcsolódó vélemények révén egyedi véleményekeket adhattak meg az alkalmazottaiknál. A jelen frissítéstől kezdődően a vezetők hozzáférhetnek a **Csapat teljesítményvéleményei** mozaikhoz, és új véleményeket hozhatnak létre valamelyik közvetett beosztottjuk kiválasztását követően.

## <a name="configure-proration-options-by-leave-plan"></a>Arányosítási lehetőségek konfigurálása a szabadságterv szerint

A szervezetek eltérően ítélhetik oda a szabadságot attól függően, hogy mikor csatlakoznak az alkalmazottak a vállalathoz, illetve mikor hagyják el azt. Bizonyos szervezetek esetében az alkalmazottak, megkapják a teljes mennyiséget a kezdő dátumon, másoknál pedig ez arányosan történik. Ebben a verzióban új lehetőségek közül lehet választani az odaítélések arányosítását és könyvelését tekintve a szervezethez csatlakozók és az azt elhagyók tekintetében. A lehetőségek a következők: Arányosítva, Összes elhatárolás és Nincs elhatárolás.

## <a name="other-changes"></a>Egyéb változtatások

-   Alkalmazotti entitás frissítve – A **Személyes** cím mostantól frissíthető az Excel-bővítmény/-adatkezelés révén.

-   Biztonsági módosítás a **Törlés** és **Deaktiválás** gombok engedélyezéséhez az alkalmazotti önkiszolgáló rendszerben a fizetési információknál.

## <a name="known-issue"></a>Ismert probléma

-   **Probléma:** Amikor új mellékletet ad egy dolgozóhoz, az **Új** és **Szerkesztés** gombok kiszürkítve jelennek meg. **Megoldás:** Mielőtt megnyitná a melléklet lapját, győződjön meg róla, hogy be vannak zárva a **Dolgozó** lap ténymezői. Ha a ténymezők be vannak zárva, amikor a **Dolgozó** lap be van töltve, akkor a **Mellékletek** gombjai engedélyezettek. (Ezt a problémát kijavítjuk a következő platformfrissítéssel.)
