---
title: A Dynamics 365 Human Resources új és módosult elemei (2020. június 11.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. június 11-i kiadásban.
author: Darinkramer
manager: AnnBe
ms.date: 06/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-06-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0720b2024a865fcd42cd80fd905586d626388f8f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4418894"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-11-2020"></a>A Dynamics 365 Human Resources új és módosult elemei (2020. június 11.)

Ez a cikk a Dynamics 365 Human Resources szolgáltatásban található új vagy módosított funkciókat írja le. A változtatások a 8.1.3316-es buildszámra vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.

## <a name="streamlined-employee-form-sometimes-causes-child-form-close-x-buttons-to-stop-working-442369"></a>Az egyszerűsített alkalmazotti képernyő néha a gyermek képernyő bezárás (X) gombjainak működésképtelenségét okozza (442369)

Amikor az új **Dolgozó** képernyő engedélyezve van, a bezárás (**X**) gomb esetenként nem működött a gyermek képernyőkön. Ez a probléma szakaszosan jelentkezett. Ha elnavigált onnan, majd visszalépett oda be lehetett zárni a képernyőt. Kiválaszthatta például egy menüparancsot a bal oldalon, majd visszatérhetett a **Dolgozó** képernyőre, majd bezárhatta azt. Az eheti kiadás kijavítja ezt a problémát. 

## <a name="the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-a-parent-relationship-type"></a>A Dolgozó személyes kapcsolattartó entitása nem exportálja a személyes kapcsolattartókat szülő kapcsolattípussal

Ebben a kiadásban a **Dolgozó személyes kapcsolattartó** entitás exportálja az összes kapcsolattípust.

## <a name="the-hcmpositionworkerassignmentv2entity-should-be-part-of-the-ceridian-payroll-integration-package-by-default-448506"></a>A HcmPositionWorkerAssignmentV2Entity alapértelmezésben rész kell legyen a Ceridian bérlistaintegrációs csomagjának (448506)

Ezzel a módosítással a **HcmPositionWorkerAssignmentV2Entity** a Ceridian bérlistaintegrációs csomagjának része.

## <a name="in-preview"></a>Előnézetben

## <a name="database-logging"></a>Adatbázis naplózása

Az adatbázis-naplózási funkció segítségével meghatározhatja, hogy mely táblát és mezőket kell figyelni. Azt is lehetővé teszi, hogy meghatározza a változáskövetést igénylő eseményeket. Az adatbázis-naplózási funkciók segítségével ezeknek a változásoknak a történetét megjelenítheti. További tájékoztatás: [Adatbázis-naplózás konfigurálása és kezelése](hr-admin-database-logging.md).

## <a name="human-resources-application-in-teams"></a>Human Resources alkalmazás a Teamsben

Az alkalmazottak megtekinthetik és kérhetik a munkából való távollétet a Microsoft Teams alkalmazásban. Ezek egy robottal lépnek interakcióba a szabadságkérelmek létrehozásához. További tájékoztatás: [Human Resources alkalmazás a Teamsben](https://go.microsoft.com/fwlink/?linkid=2127841). 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Az adatkezelési keretrendszer (DMF) entitásai a juttatások kezeléséhez
 
A juttatások kezelése entitások kiadnak. A DMF entitások lehetővé teszik az adatok importálását és exportálását a juttatáskezelés egyszerű konfigurálásához. A juttatáskezelési sablon az adatok áthelyezésére elérhető lesz. A sablon egymást követően exportálja és importálja az adatokat az adatfüggőségek tiszteletben tartásához.

## <a name="buy-and-sell-leave"></a>Szabadság vásárlása és eladása 

Néhány szervezet olyan juttatást biztosít, amely lehetővé teszi az alkalmazottak számára, hogy megvásárolják vagy eladják a szabadságukat. Ezt a folyamatot gyakran manuálisan kell kezelni. Ez a funkció automatizálja a HR osztályhoz tartozó kezelési házirendek és kérelmek kezelését. Racionalizálja a szabadság-kezelési folyamatot, és segít kiküszöbölni a hibákat. További tájékoztatás:

- [Szabadság vásárlásával és eladásával kapcsolatos irányelv kezelése](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Szabadság vásárlása és eladása](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Szabadság elhatárolása egyetlen vállalat vagy egy terv esetében

A vevők az elhatárolást egyetlen vállalatra vagy egyetlen szabadságtervhez is feldolgozhatják. Ez a képesség tisztává teszi az elhatárolási folyamatot a különböző szabadságévekkel rendelkező vagy elhatárolási házirendekkel rendelkező vevők esetében. A további tudnivalókat lásd: [Szabadság elhatárolása vállalatonként vagy szabadság tervenként](hr-leave-and-absence-accrue.md).

## <a name="add-attachments-to-time-off-requests"></a>Mellékletek hozzáadása szabadságkérelmekhez

A jóváhagyott szabadságkérelmekhez tartozó mellékletek hozzáadásának lehetősége kritikus az aktuális COVID-19-környezetben. Az alkalmazottak ezután hozzáadhatják ezeket a mellékleteket. Ők is nagyobb betekintést kapnak a szabadságkérelmek frissítései tekintetében. A további tudnivalókat lásd: [Melléklet hozzáadása meglévő kérelemhez](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).

## <a name="add-reason-code-to-accrual-suspensions"></a>Okkódhozzáadása az elhatárolás-felfüggesztésekhez 

Okkódok kerültek hozzáadásra az elhatárolás-felfüggesztéshez.

## <a name="carry-forward-rules"></a>Átvitel szabályai 

Megadhatja, hogy az átviteli szabadságtípust az átviteli egyenlegekhez, ahová az átviteli korrekciók ár lesznek helyezve. Ha például egy alkalmazott 10 napot visz át, akkor a 10 napnál más szabadság-típust is kiválaszthat. További tájékoztatás: [Szabadság és távolléti típusok konfigurálása](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>Felfüggeszti a távollét elhatárolását a megadott szabadság-típusokhoz

Olyan szabályt hozhat létre, amely felfüggeszti a távolléti elhatárolásokat a fizetés nélküli szabadságokhoz megadott szabadságkérelmekhez. A fizetetlen szabadság lehet egy típus, de ez nem kötelező. Bármilyen szabadságot egy másik szabadság típus alapján fel lehet függeszteni.

## <a name="dmf-entity-available-for-accrual-suspensions"></a>A DMF entitás elérhető az elhatárolás-felfüggesztésekhez 

A DMF entitás immár elérhető az elhatárolás-felfüggesztésekhez.

## <a name="coming-soon"></a>Hamarosan

## <a name="new-platform-capabilities"></a>Új platformképességek 

A mezőket a személyre szabás segítségével kötelezővé tehet mezőket. Ez a funkció csak akkor szükséges, ha engedélyezni szeretné a **Mentett nézeteket**.

## <a name="configure-the-name-of-employee-self-service"></a>Alkalmazotti önkiszolgáló rendszer nevének konfigurálása

A Humánerőforrás-paraméterek között egy új beállítás érhető el, ahol az Alkalmazotti önkiszolgáló rendszer munkaterület neve Önkiszolgáló rendszerre frissíthető. 

## <a name="see-also"></a>Lásd még

[Új vagy módosult elemek a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]