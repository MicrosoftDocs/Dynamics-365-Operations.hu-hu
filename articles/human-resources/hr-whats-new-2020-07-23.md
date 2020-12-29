---
title: A Dynamics 365 Human Resources új vagy módosult elemei (2020. július 23.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. július 23-i kiadásban.
author: Darinkramer
manager: AnnBe
ms.date: 07/23/2020
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
ms.search.validFrom: 2020-07-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d0672e3039f54a4591db49eee00d69bf5e4278fd
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528449"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-23-2020"></a>A Dynamics 365 Human Resources új vagy módosult elemei (2020. július 23.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a témakör a Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le. A változtatások a 8.1.3416-es buildszámra vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.

## <a name="deleting-financial-dimensions-on-a-position-doesnt-work-as-expected-445476"></a>A beosztáshoz tartozó pénzügyi dimenziók törlése nem az elvártaknak megfelelően működik (445476)

A dimenziók beosztásból való eltávolítása ezennel eltávolítja ezeket a beosztásokat a Common Data Service-ből.

## <a name="positions-not-in-hierarchy-show-inactive-positions-397257"></a>A hierarchiában nem szereplő pozíciók inaktív pozíciókat mutatnak (397257)

Az inaktív beosztások (lejárt időtartamú) a pozícióhierarchiában már nem **Hierarchiában nem szereplő beosztások** lehetőségként jelennek meg. 

## <a name="validation-occurring-between-leaveenrollmententity-and-hcmworkerentity-on-data-management-framework-dmf-import-causes-slow-data-loads-442324"></a>Az Adatkezelési keretrendszer (DMF) importálásának LeaveEnrollmentEntity és HcmWorkerEntity közti érvényesítése lassú adatterhelést okoz (442324)

A kiadás módosításai növelik a **LeaveEnrollmentEntity** teljesítményét.

## <a name="unable-to-personalize-in-organization-administration-447490"></a>Nem lehet személyre szabni a Szervezeti adminisztrációban (447490)

Ezzel a módosítással testreszabhatja a **Szervezeti adminisztráció** hivatkozásait.

## <a name="in-preview"></a>Előnézetben

## <a name="mandatory-fields"></a>Kötelező mezők 

Most már kötelezővé teheti a mezőket a Human Resources személyre szabási funkcióival. Ehhez a funkcióhoz **Mentett nézetek** szükségesek.

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

## <a name="checklist-entities-included-in-common-data-service"></a>Ellenőrzőlista-entitások szerepelnek a következőben: Common Data Service

Az Előkészítés, Felszámolás, Áthelyezések és Üzleti folyamatok hamarosan elérhetők lesznek a Common Data Service alkalmazásban.

## <a name="platform-changes"></a>Platformok módosításai

Platform frissítése erre: 10.0.12 (36)

## <a name="see-also"></a>Lásd még

[Új vagy módosult elemek a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)
