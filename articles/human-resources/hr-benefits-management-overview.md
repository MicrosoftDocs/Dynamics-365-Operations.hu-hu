---
title: Juttatáskezelés – áttekintés
description: A juttatáskezelés Dynamics 365 Human Resources szolgáltatásbeli előzetes funkciójának áttekintése. Az alkalmazottak számára kiterjesztett juttatási lehetőségeket kínálhat könnyen használható online felületen.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63db1b55bae9150dd87d9981136b96d72ffd0c59
ms.sourcegitcommit: 523049c363a999050c58d20695f1c7d151b3fd3e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029463"
---
# <a name="benefits-management-overview"></a>Juttatáskezelés – áttekintés

[!include [banner](includes/preview-feature.md)]

A versenyképesség megőrzéséhez juttatások széles választékát kell nyújtania, hogy felkeltse a legjobb alkalmazottak figyelmét, és meg is tudja tartani őket. A szokásos juttatások, például az orvosi és a fogászati biztosítás mellett kiterjesztett szolgáltatásokat is kínálhat, például bevezetési támogatást, rekreációs programokat és ruházati pótlékokat. A Microsoft Dynamics 365 Human Resources juttatáskezelésének előzetes funkciója rugalmas megoldást kínál, amely a juttatási lehetőségek széles választékát támogatja. A Human Resources szolgáltatás tartalmaz egy egyszerűen használható alkalmazotti felületet is, amelyen bemutathatja az ajánlatait.

- A bővített juttatási konstrukciók lehetővé teszik egyedi juttatási konstrukciók létrehozását és kezelését, valamint összetett juttatásmérték-táblázatok és beágyazott szintek támogatását. Az alkalmazotti élmény javításához könnyen készíthet juttatási programokat, csomagokat és automatikus igénylési szabályokat.

- A rugalmas jóváírási programok lehetővé teszik az arányosítást a nyugdíjazás és az egyéb élettartam-események támogatásához.

- A számos jogosultsági szabály biztosítja, hogy a megfelelő juttatásokat tudja szolgáltatni a megfelelő alkalmazottak számára.

- A juttatások online regisztrálása könnyen használható megoldást nyújt az alkalmazottaknak.

- A minősített élettartam-események feldolgozása együttműködik az alkalmazotti önkiszolgáló rendszerrel, és a jövőbeli élettartam-eseményeket is támogatja.

Ha szeretne hozzáférni a bemutató adatokhoz, újra kell telepítenie a tesztkörnyezetét.

Közvetlen visszajelzést vagy hibajelentést a következő címre küldhet: D365BenefitsPreview@microsoft.com.

## <a name="benefits-management-known-issues"></a>Juttatáskezelés – ismert problémák

### <a name="eligibility-processing"></a>Jogosultság feldolgozása

Ha jogosultságokat futtat olyan juttatásokra, amelyek 1–5x-ös fizetést, a fizetés százalékát és a fix összeg fedezeti összegét használják, akkor a **Juttatási részletek** beállítás dátumát az **Alkalmazott kezdési dátuma** értékre kell állítania az **Alkalmazási előzmények** között. Meg kell adnia a **Ledolgozott órák**, a **Fizetési gyakoriság** és a **Évi juttatások fizetési összege** értéket is. Ha a dolgozónak fix kompenzációja van, adja meg a **Ledolgozott órák** és a **Fizetési gyakoriság** értéket. A rendszer kiszámítja az éves fizetés összegét. Ha az alkalmazott bérezéses, akkor a **Ledolgozott órák** értéket nem kell megadni. Javasoljuk, hogy új dolgozók létrehozásakor először adja meg a fix kompenzációt. A juttatás részleteire vonatkozó rekord frissítéséhez lépjen a következőre: **Dolgozó > Dolgozói előzmények > Foglalkoztatás részletei**. Állítsa be a dátumot a dolgozó kezdési dátumára.

### <a name="employee-self-service"></a>Alkalmazotti önkiszolgáló rendszer

A rendszer nem számítja ki az alkalmazotti összeget az életbiztosítás fedezeti összegének frissítésekor. Például ha egy alkalmazottnak életbiztosítási csomagot ajánl fel, akkor egészen 50 000 dollár fedezeti összegig választhatnak 0,36 dollár/1000 dollár fedezeti költségen.  Amikor az alkalmazott frissíti a fedezet összegét, az alkalmazotthoz kapcsolódó költség nulla marad.

Olyan juttatási konstrukció esetében, amely csak az adott konstrukciótípus egyszeri kiválasztását teszi lehetővé, a felhasználó hibaüzenetet kap, ha a konstrukció kiválasztása után megpróbálja lemondani a konstrukciót. Például egy felhasználó kiválaszt egy egyészségügyi konstrukciót, és kosárba teszi. A felhasználó ezután kiválasztja a **Lemondás** lehetőséget, ezzel lemondva a másik egészségügyi konstrukciót. A felhasználó hibaüzenetet kap.

## <a name="enable-benefits-management"></a>Juttatáskezelés engedélyezése

A juttatáskezelés előzetes funkció, és csak **Teszt** környezetekben érhető el. Ezek a cikkek azt írják le, hogyan lehet bekapcsolni az előzetes funkciókat a Human Resources szolgáltatásban. Arról is tájékoztatást adnak, hogy a Human Resources szolgáltatásban melyik meglévő funkciók lesznek lecserélve vagy letiltva, amikor bekapcsolja a juttatáskezelést.

- [Szolgáltatások kezelése](hr-admin-manage-features.md)
- [Előzetes funkció: juttatások kezelése](hr-admin-manage-features.md?preview-feature-benefits-management)

## <a name="configure-benefits-management"></a>A juttatáskezelés konfigurálása

Az alkalmazottak juttatási konstrukcióinak létrehozása előtt konfigurálnia kell a konstrukciókhoz tartozó beállításokat.

- [A juttatáskezelés paramétereinek beállítása](hr-benefits-setup-parameters.md)
- [Jogosultsági szabályok és beállítások konfigurálása](hr-benefits-setup-eligibility-rules.md)
- [A személyes kapcsolattartó jogosultsági beállításainak konfigurálása](hr-benefits-setup-contact-eligibility-options.md)
- [Fedezeti beállítások létrehozása](hr-benefits-setup-coverage-options.md)
- [Fizetési gyakoriságok beállítása](hr-benefits-setup-payment-frequencies.md)
- [Élettartamesemény-típusok konfigurálása](hr-benefits-setup-life-event-types.md)
- [Konstrukciótípusok létrehozása](hr-benefits-setup-plan-types.md)
- [Okkódok beállítása](hr-benefits-setup-reason-codes.md)
- [Szintkódok beállítása](hr-benefits-setup-tier-codes.md)
- [Mértékek konfigurálása](hr-benefits-setup-rates.md)
- [Levonások konfigurálása](hr-benefits-setup-deductions.md)
- [Várakozási napok konfigurálása](hr-benefits-setup-waiting-days.md)
- [Várakozási időszakok konfigurálása](hr-benefits-setup-waiting-periods.md)
- [Kerekítési szabályok beállítása](hr-benefits-setup-rounding-rules.md)
- [Foglalkoztatási kategóriák létrehozása](hr-benefits-setup-employment-categories.md)
- [Foglalkoztatási típusok beállítása](hr-benefits-setup-employment-types.md)
- [Alkalmazotti önkiszolgáló rendszer konfigurálása](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a>Juttatási konstrukciók létrehozása

Ezek a cikkek a juttatási konstrukciók létrehozását ismertetik, beleértve a csomagokat és a rugalmas jóváírási programokat.

- [Juttatási konstrukciók beállítása](hr-benefits-plans-setup.md)
- [Dolgozói juttatási konstrukciók létrehozása](hr-benefits-plans-worker.md)
- [Rugalmas jóváírási programok beállítása](hr-benefits-plans-flex-credit-programs.md)
- [Jövőbeli élettartam-események konfigurálása](hr-benefits-plans-future-life-events.md)

## <a name="process-benefit-plans"></a>Juttatási konstrukciók feldolgozása

Néhány módosítását fel kell dolgoznia, hogy aktiválja azokat.

- [Felvételi jogosultság feldolgozása](hr-benefits-process-enrollment-eligibility.md)
- [Élettartam-események feldolgozása](hr-benefits-process-life-events.md)
- [Élettartam-események módosításainak feldolgozása](hr-benefits-process-life-event-changes.md)
- [Élettartam-eseményekre vonatkozó jogosultságok feldolgozása](hr-benefits-process-life-event-eligibility.md)
- [Mértékmódosítás feldolgozása](hr-benefits-process-rate-changes.md)

