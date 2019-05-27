---
title: Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. március 5.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 03/05/2019
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
ms.search.validFrom: 2019-03-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e4ad32ef71c87f52e59959d80c21ae7fcd6d6524
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518217"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-march-5-2019"></a>Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. március 5.)

[!include [banner](includes/banner.md)]

Ez a témakör a Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

### <a name="extending-option-sets-in-attract"></a>Beállításkészletek kiterjesztése az Attract alkalmazásban

Az Attract alkalmazásban, több mezők is van, amely beállításkészlet a Common Data Service szolgáltatásban. Új képességek lettek bevezetve a beállításkészletek kiterjesztésére, kezdve az **Elutasítás** okkód mezővel a **Foglalkoztatási típusa** mezővel, és **Szolgálati idő típusa** mezővel.

> [!IMPORTANT]
> Az álláshirdetés a LinkedIn funkcióhoz a **Foglalkoztatási típusa** és **Szolgálati idő típusa** mezők szükségesek az **Állás részletei** lapon. Ezen a mezők az alapértelmezett értékekeit a LinkedIn támogatja és meg lesznek jelenítve az állás feladásakor. Ha állásokat tesz közzé a LinkedIn-en, és ezen a mezők a meglévő beállításkészlet-értékeit módosítja, az állás továbbra is közzé lesz téve, de LinkedIn nem jeleníti meg az egyéni **Foglalkoztatási típusa** és **Szolgálati idő típusa** értékeket.

## <a name="changes-in-onboarding"></a>Változások az Onboarding alkalmazásban

### <a name="private-preview-for-onboard-teams"></a>Privát előnézet Onboard csoportoknak
Mostantól egyszerűen megoszthatja a teljes szervezeten belüli a sablonokat az együttműködéshez. További tudnivalókért lásd: [Bevált gyakorlatok megosztása a szervezetben az Onboard Teams használatával](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/share-best-practices-teams).

### <a name="private-preview-for-assignee-placeholders"></a>A megbízott helyőrzők privát előnézete
A tevékenységeket az egyes személyek helyett személyekhez rendelheti, így gazdagítva sablonjait. A Szerepkörök majd személyekhez lesznek rendelve az útmutató a létrehozásának időpontjában. További tudnivalókért lásd: [Az útmutatófelügyeleti tevékenységek egyszerűsítése tevékenységek hozzárendelésével a szerepkörökhöz](https://docs.microsoft.com/en-us/business-applications-release-notes/April19/dynamics365-talent/onboard/assign-activities-roles).

## <a name="changes-in-core-hr"></a>A Core HR módosításai
**Build 8.1.2178**

### <a name="configure-workflow-to-auto-approve-or-follow-workflow-when-an-hr-or-line-manager-submits-or-updates-time-off-requests"></a>Munkafolyamat konfigurálása a munkafolyamat automatikus jóváhagyásához vagy , amikor egy HR vezető vagy a vezető elküldi vagy frissíti a szabadságkérelmeket
Új munkafolyamat-feltételek lettek hozzáadva, amelyek megengedik a szabadságkérelmek automatikus jóváhagyását, ha azt az alkalmazott vezetője vagy a HR nyújtja be. Automatikus jóváhagyás elérésének a egyik módja a munkafolyamatban egy automatikus művelet engedélyezése a munkafolyamat jóváhagyása során.

A hozzáadott feltételek a következők:

- Beküldte - A rendszer felhasználója azonosítójának meghatározásához használható, aki beküldte a munkafolyamat iránti kérelmet.
- Beküldve a következő nevében – Annak meghatározásához, hogy a szabadságkérelmet a kérelemhez társított dolgozó nevében küldték-e be.
- Beküldte az emberi erőforrások – Annak meghatározására, hogy a munkafolyamat-kérelmet beküldő rendszerfelhasználó Emberi erőforrás szerepkörű e.
- Vezető küldte be – Annak meghatározásához, hogy a felhasználó aki beküldte a szabadságkérelmet a munkafolyamathoz kéréshez társított dolgozó vezetőeje-e.

### <a name="enable-employee-fixed-compensation-for-future-position-assignments"></a>Az alkalmazott fix kompenzációjánek engedélyezése jövőbeli beosztás-hozzárendelésekhez
Jellemző, hogy azon alkalmazottak, akik a szervezethez csatlakoznak jövőbeni kezdési dátummal rendelkeznek. Ez a módosítás lehetővé teszi fix kompenzáció meghatározását jövőbeni beosztás-hozzárendelésekkel rendelkező alkalmazottakhoz.

### <a name="position-payroll-fields-are-blank-when-editing-the-position"></a>A Beosztásbérlista mezők üresek a beosztás módosításakor.
Ezzel a módosítással a meglévő beosztások módosításának kérelme során a bérlista mezők most alapértelmezés szerint az aktuális értékeket tartalmazzák.

### <a name="other-miscellaneous-bug-fixes"></a>Egyéb vegyes hibajavítások
További kisebb hibajavítások ebben a verzióban.

### <a name="upgrade-to-common-data-service"></a>Frissítés Common Data Service megoldásra
A Common Data Service frissítés határideje gyorsan közeledik. Jelentkezzen be annak meghatározásához, hogy kell-e az adatbázist frissíteni kell PowerApps felügyeleti központba. Határidőkkel és frissítéséhez szükségesek további lépésekkel kapcsolatos tudnivalókat lásd: [Frissítés a Common Data Service](https://docs.microsoft.com/en-us/common-data-service/upgradecds/introduction-upgrade-cds) megoldásra.

## <a name="coming-soon"></a>Hamarosan

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Haladó kompenzációs biztonsági (fix és változó)
Számos vállalatnál a kompenzációkért és juttatásokért felelős vezetők csak bizonyos kompenzációs rekordokat érhetnek el, például a vezetők és a területi alapú alkalmazottak rekordjait. Ez a módosítás lehetővé teszi a kompenzációs tervek kezelését és karbantartását a szervezet különböző alkalmazottcsoportjaihoz. A fix és változó kompenzációs tervek, amelyek hozzárendelhetők biztonsági szerepkörökhöz, határozzák meg a hozzáférést ezekhez a tervekhez és a hozzájuk kapcsolódó alkalmazotti adatokhoz, például fizetés és bónuszrekordok. Csak a szerepkörök, amelyek rendelkeznek a meghatározott hozzáféréssel tudnak kompenzációt feldolgozni azokhoz az alkalmazottakhoz.

###  <a name="platform-update-24"></a>24-as platformfrissítés
A 24-es platformfrissítéssel kapcsolatos részleteket lásd a [jdonságok és változások a Dynamics 365 for Finance and Operations 24. platformfrissítésében (2019. március)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).
