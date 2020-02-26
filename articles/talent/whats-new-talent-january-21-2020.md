---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2020. január 21.)
description: Ez a cikk a Microsoft Dynamics 365 Talent új vagy módosított funkcióit írja le.
author: Darinkramer
manager: AnnBe
ms.date: 01/21/2020
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
ms.search.validFrom: 2020-01-21
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c0c303ec5d009fce0c975eb797f018b5e27a41eb
ms.sourcegitcommit: 4c60f5dccdf0b94ed110a657ef331546adc5424a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/23/2020
ms.locfileid: "2982407"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-21-2020"></a>Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2020. január 21.)

[!include [banner](includes/banner.md)]

Ez a cikk a Dynamics 365 Talent szolgáltatásban található új vagy módosított funkciókat írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

A kiadás a Dynamics 365 Talent: Attract apró hibáinak javításait is tartalmazza. Olyan funkciókat adtunk hozzá, amelyek támogatják a legutóbbi bejelentést, [és a Dynamics 365 Human Resources-szal sikeresebb munkaerőt építenek ki](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/12/06/building-a-more-successful-workforce-with-dynamics-365-human-resources/).

### <a name="download-environment-data"></a>Letöltött környezeti adatok

A rendszergazdák le tudják tölteni a környezetük adatait. A program az adatokat normál JSON formátumba exportálja egy zip-fájlba az összes feladattal, pályázóval és konfigurációval. A további információkért lásd: [Adatok exportálása az Attract és Onboard-ból](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data).

### <a name="restricting-access-to-environments-for-non-admin-users"></a>A környezethez való hozzáférés korlátozása a nem rendszergazdai felhasználók számára

A rendszergazdák mostantól korlátozhatják a környezethez történő hozzáférést a nem rendszergazda felhasználók számára. Ez a művelet nem vonható vissza. További információ: [Attract hozzáférésének korlátozása](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data#restrict-access-to-attract).

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

### <a name="exporting-onboarding-guides"></a>Felvételi útmutatók exportálása

A felhasználók most exportálhatják a saját felvételi útmutatóikat és felvételi sablonjaikat Word dokumentumformátumba. A további információkért lásd: [Adatok exportálása az Attract és Onboard-ból](https://docs.microsoft.com/dynamics365/talent/attract-onboard-export-data).

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2726-ös buildre vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az Microsoft Dynamics Lifecycle Services (LCS) támogatási számaira vonatkoznak.

### <a name="most-recent-annual-compensation-field-in-verify-employment-form-isnt-consistent-392092"></a>A legutóbbi éves kompenzációs mező a Foglalkoztatás ellenőrzése képernyőn nem konzisztens (392092)

Ez a kiadás egy olyan módosítást tartalmaz, amely a vállalatválasztó alapján folyamatosan megjeleníti a legfrissebb pénznemet a **Foglalkoztatás ellenőrzése** képernyőn.

### <a name="known-as-field-added-to-the-feedback-recipient-lookup-407789"></a>A visszajelzés címzettje számára történő kereséshez (407789) hozzáadott mező neve

A teljesítmény-visszajelzések esetében a dolgozói keresés nem szolgáltatott elegendő információt annak megállapításához, hogy a visszajelzések a megfelelő személyhez mennek-e. A **Más néven** oszlop hozzáadása segítségével lehet meghatározni az alkalmazott egyedi nevét.
 
### <a name="hcmworkerpayrollinfo-record-is-created-without-an-association-to-a-worker-394526"></a>A HcmWorkerPayrollInfo rekord egy dolgozóhoz való társítás nélkül jön létre (394526)

Ez a kiadás olyan módosítást tartalmaz, amely nem ír HCMWorkerPayrollInfo-rekordokat az alkalmazottra való hivatkozás nélkül.

### <a name="able-to-edit-department-when-navigating-from-position-hierarchy-341001"></a>Képes szerkeszteni a részleget a beosztás hierarchiájából történő navigáláskor (341001)

Amikor a biztonság beállításával meg van tagadva a szerkesztési osztályokhoz való hozzáférés, a szerkesztés le van tiltva, amikor a **Részlegek** űrlapra navigál minden forgatókönyvben.

## <a name="coming-soon"></a>Hamarosan

Az új Common Data Service megoldás hamarosan a következő változtatásokkal érhető el:

| Leírás | Visszajáró |
| --- | --- |
| **Feladat/pozíció** entitás módosításai | <ul><li>**Kompenzációs régió** hozzáadása</li><li>**Pénzügyi dimenziók** hozzáadása</li></ul> |
| **Dolgozó** entitás módosításai | <ul><li>**Névsorrend** hozzáadása</li><li>**Otthonról dolgozik** hozzáadása</li><li>**Nyelv** hozzáadása</li><li>**Szolgálati idő dátuma** hozzáadása</li><li>**Évforduló dátuma** hozzáadása</li><li>**Eredeti felvételi dátum** hozzáadása</li></ul> |
| **Foglalkoztatás** entitás módosításai | <ul><li>**Pénzügyi dimenziók** hozzáadása</li><li>**Felmondás oka** hozzáadása</li><li>**Megszűnés dátuma** az **Áttérési dátumtól** átnevezve</li><li>**Próbaidős dátum** hozzáadása</li></ul> |
| **Dolgozó címe** entitás módosításai | <ul><li>**Utca és házszám** hozzáadása</li><li>**1. címsor**, **2. címsor** és **3. címsor** megjelölve megszűnésre</li></ul> |
| Új változó kompenzációs beállítási entitások | <ul><li>**Változó kompenzációs konstrukció típusa**</li><li>**Változó kompenzációs konstrukció**</li><li>**Kilépési szabályok**</li><li>**Változó kompenzációs konstrukció szintje**</li></ul> |
| Új **Dolgozói naptár – foglalkoztatás** entitás | <ul><li>**Munkanaptár-entitás** hozzáadva</li></ul> |
