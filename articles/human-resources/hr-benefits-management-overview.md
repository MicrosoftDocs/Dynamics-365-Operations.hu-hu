---
title: Juttatáskezelés áttekintése
description: A juttatáskezelés funkció áttekintése a Dynamics 365 Human Resources alkalmazásban. Az alkalmazottak számára kiterjesztett juttatási lehetőségeket kínálhat könnyen használható online felületen.
author: andreabichsel
ms.date: 04/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4ad94d81d7e8bedd3622b3e073e431bc4abaafff
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924230"
---
# <a name="benefits-management-overview"></a>Juttatáskezelés – áttekintés

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A versenyképesség megőrzéséhez juttatások széles választékát kell nyújtania, hogy felkeltse a legjobb alkalmazottak figyelmét, és meg is tudja tartani őket. A szokásos juttatások, például az orvosi és a fogászati biztosítás mellett kiterjesztett szolgáltatásokat is kínálhat, például bevezetési támogatást, rekreációs programokat és ruházati pótlékokat. A Microsoft Dynamics 365 Human Resources juttatáskezelés funkciója rugalmas megoldást kínál, amely a juttatási lehetőségek széles választékát támogatja. A Human Resources szolgáltatás tartalmaz egy egyszerűen használható alkalmazotti felületet is, amelyen bemutathatja az ajánlatait.

- A bővített juttatási konstrukciók lehetővé teszik egyedi juttatási konstrukciók létrehozását és kezelését, valamint összetett juttatásmérték-táblázatok és beágyazott szintek támogatását. Az alkalmazotti élmény javításához könnyen készíthet juttatási programokat, csomagokat és automatikus igénylési szabályokat.

- A rugalmas jóváírási programok lehetővé teszik az arányosítást a nyugdíjazás és az egyéb élettartam-események támogatásához.

- A számos jogosultsági szabály biztosítja, hogy a megfelelő juttatásokat tudja szolgáltatni a megfelelő alkalmazottak számára.

- A juttatások online regisztrálása könnyen használható megoldást nyújt az alkalmazottaknak.

- A minősített életesemények feldolgozása támogatja a jövőbeli életeseményeket.

Ha szeretne hozzáférni a bemutató adatokhoz, újra kell telepítenie a tesztkörnyezetét.

>[!NOTE]
>Most már testre szabhatja a Juttatások kezelése űrlapot. A juttatási tervek **Fedezeti beállítás** űrlapjához mostantól a fedezeti díjakkal kapcsolatos egyéni mezőket is hozzáadhatja. További információkért az egyéni mezők felhasználásáról lásd: [Egyéni mezők](hr-developer-custom-fields.md).
>![Juttatások kezelésében egyéni mezők](media/hr-benefits-management-custom-fields.png)

## <a name="enable-benefits-management"></a>Juttatáskezelés engedélyezése

A témakör azt írja le, hogyan lehet bekapcsolni funkciókat a Human Resources szolgáltatásban. Arról is tájékoztat, hogy a Human Resources szolgáltatásban melyik meglévő funkciók lesznek lecserélve vagy letiltva, amikor bekapcsolja a juttatáskezelést.

> [!IMPORTANT]
> Miután engedélyezte a juttatások kezelését egy **Termelési** környezetben, azt nem lehet letiltani. Azt ajánljuk , hogy a **Termelési** környezetben történő engedélyezése előtt engedélyezze és tesztelje a juttatások kezelését egy **Teszt** környezetben. Jelentősen különböznek egymástól a korábbi Juttatási funkciók és az új Juttatáskezelés funkciók – ezek további beállításokat igényelnek, és a termelésbe történő helyezés előtt tesztelni kell azokat.

- [Szolgáltatások kezelése](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a>Alkalmazottak adatainak konfigurálása

Ahhoz, hogy az alkalmazottakat juttatásokhoz lehessen regisztrálni, meg kell adnia a szükséges adatokat. A **Fix kompenzációs konstrukcióban** egy alkalmazottat be kell regisztrálni a kezdő dátumra, és ki kell választania egy **Juttatásfizetési gyakoriságot** a **Foglalkoztatás részletei** részben a **Dolgozó** képernyőn.

Ha van olyan alkalmazottja, aki kiegészítő kompenzációt kap, mint a jutalékok, akkor az alkalmazotti rekordból származó **Juttatások évi fizetése** összegét veheti fel. Az emberi erőforrások a fix kompenzációs éves összeg helyett a fedezeti összegek meghatározásakor a **Juttatások évi fizetésének** összegét fogják használni. A **juttatások évi fizetésének** érvényesnek kell lennie az alkalmazott kezdő dátumától vagy a juttatási időszak kezdetével, amelyik a legújabb. Ha egy alkalmazottnál egy fix kompenzációs és juttatás éves fizetési összege is rögzítve van, akkor a juttatások évi fizetését használják a fedezeti összegek meghatározására.

Ha olyan juttatási tervet hoz létre, amely nemen vagy életkoron alapuló arányokat használ, akkor meg kell adnia a születési dátumot és a nemet az alkalmazott számára a juttatási költség kiszámításához.

## <a name="configure-benefits-management"></a>A juttatáskezelés konfigurálása

Az alkalmazottak juttatási konstrukcióinak létrehozása előtt konfigurálnia kell a konstrukciókhoz tartozó beállításokat.

- [A juttatáskezelés paramétereinek beállítása](hr-benefits-setup-parameters.md)
- [Jogosultsági szabályok és beállítások konfigurálása](hr-benefits-setup-eligibility-rules.md)
- [A személyes kapcsolattartó jogosultsági beállításainak konfigurálása](hr-benefits-setup-contact-eligibility-options.md)
- [Fedezeti lehetőségek létrehozása](hr-benefits-setup-coverage-options.md)
- [Fizetési gyakoriságok beállítása](hr-benefits-setup-payment-frequencies.md)
- [Életesemények típusának konfigurálása](hr-benefits-setup-life-event-types.md)
- [Költségvetési terv típusai](hr-benefits-setup-plan-types.md)
- [Okkódok beállítása](hr-benefits-setup-reason-codes.md)
- [Számkódok beállítása](hr-benefits-setup-tier-codes.md)
- [Díjak konfigurálása](hr-benefits-setup-rates.md)
- [Levonások konfigurálása](hr-benefits-setup-deductions.md)
- [Várakozási napok konfigurálása](hr-benefits-setup-waiting-days.md)
- [Várakozási időszakok konfigurálása](hr-benefits-setup-waiting-periods.md)
- [Kerekítési szabályok beállítása](hr-benefits-setup-rounding-rules.md)
- [Alkalmazási kategóriák létrehozása](hr-benefits-setup-employment-categories.md)
- [Foglalkoztatási típusok beállítása](hr-benefits-setup-employment-types.md)
- [Alkalmazotti önkiszolgáló rendszer konfigurálása](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a>Juttatási konstrukciók létrehozása

Ezek a cikkek a juttatási konstrukciók létrehozását ismertetik, beleértve a csomagokat és a rugalmas jóváírási programokat.

- [Juttatási tervek beállítása](hr-benefits-plans-setup.md)
- [Rugalmas hitelprogramok beállítása](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a>Juttatási tervek feldolgozása

Néhány módosítását fel kell dolgoznia, hogy aktiválja azokat.

- [Felvételi jogosultság feldolgozása](hr-benefits-process-enrollment-eligibility.md)
- [Élettartam-események feldolgozása](hr-benefits-process-life-events.md)
- [Élettartam-események módosításainak feldolgozása](hr-benefits-process-life-event-changes.md)
- [Élettartam-eseményekre vonatkozó jogosultságok feldolgozása](hr-benefits-process-life-event-eligibility.md)
- [Mértékmódosítás feldolgozása](hr-benefits-process-rate-changes.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]