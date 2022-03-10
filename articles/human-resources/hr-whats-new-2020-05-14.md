---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. május 14.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. május 14-i kiadásban.
author: andreabichsel
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cb4693f3c856e7abcc39cbd658183d01ec98a066
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8063747"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-14-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. május 14.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Ez a témakör a Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le. A változtatások a 8.1.3244-es buildszámra vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok tájékoztatásként a Lifecycle Services (LCS) támogatási számaira vonatkoznak.

## <a name="platform-changes"></a>Platformok módosításai

Ez a heti kiadás tartalmazza a platform változásait. További információkért lásd [Platformfrissítések a Finance and Operations alkalmazások 10.0.10-es verziójához (2020. május)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-34.md). Ez a kiadás hibajavításokat és a mentett nézetek módosításait tartalmazza.
 
## <a name="ensure-dataverse-picklists-are-consistent-with-leave-enums-436343"></a>Biztosítja, hogy a Dataverse választási listák megfelelnek a Szabadság felsorolásainak (436343)

A Dataverse választási listák most már megfelelnek a Szabadság felsorolásainak.

## <a name="allow-users-to-configure-leave-request-workflow-based-on-the-request-amount-300044"></a>A felhasználók számára lehetővé teszi a szabadságkérelmi folyamat kérelem mennyisége alapján történő konfigurálását (300044).

A felhasználók konfigurálhatják a szabadságkérelmi folyamatokat a kérelem mennyiségei alapján.
 
## <a name="new-worker-form-exposes-data-through-the-view-menu-when-advanced-security-is-enabled-403185"></a>Az új dolgozói űrlap elérhetővé teszi az adatokat a Nézet menün keresztül, amikor a speciális biztonság engedélyezve van (403185).

Ez a kiadás javítja azt, hogy hogyan jeleníti meg a dolgozókat a jogi személyek között a speciális hozzáférés engedélyezése esetén, és amikor más vállalatok dolgozói is hozzáférhetők.

## <a name="allow-running-leave-accruals-for-a-single-plan-or-a-single-company-318844"></a>Csak egy terv vagy egy vállalat esetében teszi lehetővé a szabadságkönyvelések futtatását (318844).

Ezzel a módosítással egy vállalat vagy egy terv esetében futtathat könyveléseket.
 
## <a name="show-the-positions-full-time-equivalent-fte-in-the-enrolled-workers-form-414658"></a>A beosztás teljes munkaidős egyenértékét (FTE) jeleníti meg a Kedvezményezett dolgozók űrlapon (414658)

A dolgozó beosztásának FTE-értéke határozza meg a dolgozói könyvelési rátát, ha a szabadságtípuson az FTE beállítás engedélyezve van. Ez a mező most szerepel a **Kedvezményezett dolgozók** űrlapon és a **Tömeges bejelentkezés** párbeszédpanelen.

## <a name="add-leave-balance-expiration-batch-job-431266"></a>Szabadságegyenleg lejáratára vonatkozó kötegelt feladat hozzáadása (431266)

Egy új, naponta futtatható feladat érhető most már el. A program csökkenti a hátralévő szabadság egyenlegét, ha a lejárati dátumok aktuálissá válnak.

## <a name="exporting-personal-contacts-for-an-employee-using-the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-the-parent-relationship-type-345893"></a>Egy alkalmazott személyes kapcsolattartóinak exportálása a Dolgozó személyes kapcsolattartója entitással nem exportálja a Szülő kapcsolattípussal rendelkező személyes kapcsolattartókat (345893).

A **Dolgozó személyes kapcsolattartója** adatentitás (a **HcmPersonalContactPersonEntity** a DMF-ben és a **PersonalContactPerson** az OData típusban) nem tudta exportálni a **Szülő** kapcsolattípussal rendelkező kapcsolattartókat. Ez a hiba a módosítást követően létrejövő személyes kapcsolattartók esetében javítva lett. A meglévő **Szülő** típusú személyes kapcsolattartók egy későbbi kiadásban kerülnek javításra.

## <a name="reason-codes-display-across-different-scenarios-when-theyre-marked-as-leave-and-absence-and-the-streamlined-employee-form-is-enabled-434163"></a>Okkódok a különböző esetekben jelennek meg, ha Szabadság és távollétként vannak megjelölve és engedélyezve van az egyszerűsített dolgozói űrlap (434163)

Ez a módosítás csak a Szabadság és távollét kódokra korlátozza az okkódokat, amikor engedélyezi az egyszerűsített dolgozói űrlapot.

## <a name="the-preview-feature-assign-a-leave-plan-to-employees-in-the-future-displays-error-433555"></a>A Jövőbeli szabadságterv hozzárendelése az alkalmazottakhoz előzetes funkció hibát jelez (433555)

Ez a módosítás kijavít egy hibát, amikor egy szabadságtervhez két szabadságtípus van hozzárendelve, és megpróbál hozzárendelni egy alkalmazottat.

## <a name="getting-started-banner-appears-for-all-users-441731"></a>A kezdeti lépések banner minden felhasználó számára megjelenik (441731)

Ezzel a módosítással a Kezdeti lépések banner olyan felhasználók esetében rejtett, akik nem rendszergazdák vagy az adatkezelési rendszergazdák. 

## <a name="the-dataverse-worker-address-entity-works-differently-in-terms-of-date-time-effective-dates-in-human-resources-425071"></a>A Dataverse Dolgozó címe entitás dátum és idő tekintetében eltérően működik a Human Resources érvényességi dátumaitól (425071)

Ez a módosítás a címadatokat a címek dátumai alapján bizonyos helyzetekben egymáshoz igazítja.

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-425407"></a>Nem adható hozzá melléklet egy jóváhagyott szabadságkérelemhez (425407)

Az e heti kiadással a szabadságkérelem módosítása nélkül is hozzáadhat mellékleteket a jóváhagyott szabadságkérelmekhez.

## <a name="in-preview"></a>Előnézetben

## <a name="leave-suspension"></a>Szabadság felfüggesztése

Egy alkalmazottra vonatkozóan felfüggesztheti a szabadságokat és a távollétet. A szabadság felfüggesztése kiválasztott távolléti típusoknál leállítja az elhatárolást. Ha a felfüggesztés a könyvelés feldolgozását követően következik be, akkor a szabadság felfüggesztése az alkalmazott szabadságának egyenlegéhez egy arányosan korrigált kiigazítást hoz létre. További információ: [Szabadság felfüggesztése](hr-leave-and-absence-suspend-leave.md).

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>Felhasználói élmény frissítése annak jelzésére, hogy az elhatárolás fel van függesztve (429550)

A felhasználói élmény immár jelzi, hogy az elhatárolás fel van függesztve egy tervhez.

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a>Felfüggeszti a távollét elhatárolását a megadott szabadság-típusokhoz (272447)

Ebben a kiadásban a HR olyan szabályt hozhat létre, amely felfüggeszti a távolléti elhatárolásokat a fizetés nélküli szabadságokhoz megadott szabadságkérelmekhez. A fizetetlen szabadság lehet egy típus, de ez nem kötelező. Bármilyen szabadságot egy másik szabadság típus alapján fel lehet függeszteni.

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a>A DMF entitás elérhető az elhatárolás-felfüggesztésekhez (429549)

A DMF entitás immár elérhető az elhatárolás-felfüggesztésekhez.

## <a name="add-reason-code-to-accrual-suspensions-429547"></a>Okkódhozzáadása az elhatárolás-felfüggesztésekhez (429547)

Okkódok kerültek hozzáadásra az elhatárolás-felfüggesztéshez.

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a>Az átállás megkezdése a humánerőforrás-paraméterektől a szabadság és távollét paramétereire

Ez a kiadás elkezdi kombinálni a Humán erőforrások paramétereit a szabadság és a távollét paramétereivel.

## <a name="carry-forward-rules"></a>Átvitel szabályai

Megadhatja, hogy az átviteli szabadságtípust az átviteli egyenlegekhez, ahová az átviteli korrekciók ár lesznek helyezve. Ha például egy alkalmazott 10 napot visz át, akkor a 10 napnál más szabadság-típust is kiválaszthat. További tájékoztatás: [Szabadság és távolléti típusok konfigurálása](hr-leave-and-absence-types.md).

## <a name="see-also"></a>Lásd még

[Új vagy módosult elemek a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]