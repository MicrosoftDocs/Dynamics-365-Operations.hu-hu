---
title: Új vagy módosult elemek a Dynamics 365 Talent – Core HR szolgáltatásban (2018. szeptember 10.)
description: Ez a témakör a Microsoft Dynamics 365 Talent – Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 09/12/2018
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
ms.search.validFrom: 2018-09-06
ms.dyn365.ops.version: Talent September 10, 2018 update
ms.openlocfilehash: ff5d21a8a71b068a276bedaf6e4b9964adcb4027
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2896750"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-september-10-2018"></a>Új vagy módosult elemek a Dynamics 365 Talent – Core HR szolgáltatásban (2018. szeptember 10.)

**Build 8.1.138.0**

Ez a témakör a Microsoft Dynamics 365 Talent: Core HR új vagy módosított szolgáltatásait írja le.

## <a name="allow-specific-time-of-day-on-time-off-requests-half-days"></a>Pontos idő megadása a szabadságkérelmekben (fél nap)

Ha a szabadság és a távollét beállítása úgy történik, hogy a szabadság megadása napokban történjen, akkor lehetőség van félnapos meghatározásra is. Ezután, amikor a felhasználók szabadságkérelmet nyújtanak be, megadhatják, hogy a nap első felét vagy második felét kérik-e.

Ez a beállítás alapértelmezés szerint ki van kapcsolva. Azoknál az alkalmazottaknál, akik a nap első vagy második felét szeretné kivenni, be kell kapcsolnia ezt a lehetőséget az Emberi erőforrások paramétereinek **Szabadság és eltávolítás** területén.

A szolgáltatás biztonsági jogosultsága a Humánerőforrás-paraméterek karbantartása.

## <a name="validation-of-leave-and-absence-entries"></a>A szabadság- és távollétbejegyzések ellenőrzése

Attól függően, hogy a távollét beállítása milyen módon történik, az alkalmazottak figyelmeztető üzenetet kapnak, amennyiben a munkanapnál hosszabb időre vonatkozó szabadságkérelmet nyújtanak be. Más szóval figyelmeztetést kapnak, ha egy adott napon többet szeretnének kivenni egy teljes napnál.

Ez az ellenőrzés mindig be van kapcsolva. Minden olyan alkalommal, amikor a munkavállalók meghaladják a meghatározott napi küszöbértéket, figyelmeztetést kapnak a szabadságkérelmükben.

## <a name="additional-fields-for-conditional-statements-in-workflows"></a>További mezők a feltételes működési utasításokhoz a munkafolyamatokban

A feltételes működési utasításokhoz és helyőrzőkhöz további mezőket adtunk a Core HR számos munkafolyamatánál.

A következő mezőket adtuk hozzá a kompenzáció, elbocsátás és átmozgatás munkafolyamataihoz:

- EmploymentType
- LegalEntity
- AdjustedWorkerStartDate
- EmployerNoticeAmount
- EmployerUnitOfNotice
- TransitionDate
- WorkerNoticeAmount
- WorkerStartDate
- WorkerUnitOfNotice
- ProbationEndDate
- Pozíció
- Unió
- Osztály
- PositionType
- CompLocation
- Beosztás
- Beosztás
- JobType
- JobFamily
- JobFunction

A következő mezőket adtuk hozzá a beosztás munkafolyamatához:

- Pozíció
- Unió
- Osztály
- PositionType
- CompLocation
- Beosztás
- Beosztás
- JobType
- JobFamily
- JobFunction

A feltételes működési utasítások és helyőrzők minden olyan felhasználó számára elérhetők, akik hozzáférnek a korábban említett munkafolyamatok konfigurálásához.

## <a name="navigation-to-attract-from-personnel-management"></a>Navigáció az Attract szolgáltatásba a személyzetkezelésből

Ha nincs beállítva az Attract a személyzetkezelésnél, a **Foglalkoztatható jelöltek** szakasza az Attract kezdő lépéseihez irányítja a felhasználókat ahelyett, hogy a „Nem találtunk megjelenítendő elemeket” üzenetet adná.

## <a name="other-changes"></a>Egyéb változások

Ebben a verzióban számos további hibajavítás is található:

- Alvállalkozó megbízásakor a **Kompenzálás** lapnak nem szabad elérhetőnek lennie a kérelem/művelet lapján.
- A kérelem megszüntetési folyamata alatt nem folytathatja a műveletet addig, amíg az összes kötelező mező adatot tartalmaz.
- Kijavítottuk a rendelés- és dátummegjelenítési problémákat a Személyzetkezelés analitikájában.
