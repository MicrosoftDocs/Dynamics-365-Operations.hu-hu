---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. május 28.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. május 28-i kiadásban.
author: Darinkramer
manager: AnnBe
ms.date: 05/28/2020
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
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 00a5881ea88749c8553e4c810fb57070f217b01c
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712012"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-28-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. május 28.)

Ez a témakör a Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le. A változtatások a 8.1.3287-es buildszámra vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.

## <a name="leaverequest-entity-doesnt-work-when-you-enable-multiple-types-per-leave-plan-447498"></a>A LeaveRequest entitás nem működik, ha szabadságtervenként több típust engedélyez (447498)

Ezzel a módosítással a **LeaveEnrollmentV2Entity** elérhetővé válik, hogy kijavítsa a különböző típusú szabadságok engedélyezésekor jelentkező hibát.

## <a name="batch-contention-reduction-feature-preview-446619"></a>Kötegtartalom-csökkentési funkció (előzetes verzió) (446619)

Ha engedélyezi ezt a funkciót, akkor a feladatok és a befejező feladatok kiválasztásakor várhatóan csökkenhet a kötegkeretrendszer tábláinak zárolása.

## <a name="updateconflict-while-saving-worker-prevents-editing-a-record-in-people-427915"></a>Az UpdateConflict a dolgozó mentésekor megakadályozza egy rekord szerkesztését a személyeknél (427915)

A módosítás kijavítja a hibát, ami egy új dolgozó hozzáadásakor, a címadatok frissítésekor és a nyelvi beállítások módosításakor jelentkezik. Ebben az egyedi esetben egy hibaüzenet jelenik meg, amely jelzi, hogy a rekord nem frissíthető. 

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-to-resubmit-425407"></a>Nem adható hozzá melléklet egy jóváhagyott szabadságkérelemhez az újraküldéshez (425407)

Ez a változtatás most már lehetővé teszi mellékletek csatolását a jóváhagyott szabadságkérelmekhez.

## <a name="user-can-enter-compensation-for-an-employee-in-a-different-legal-entity-form-409529"></a>A felhasználó megadhatja az alkalmazott kompenzációját másik jogi személy űrlapján (409529).

A módosítás letiltja a kompenzációs beállításokat a nem megfelelő jogi személyre vonatkozó kompenzációs rekordok véletlen bevitelének megakadályozására.

## <a name="error-when-you-transfer-an-employee-and-the-worker-position-assignment-date-is-before-the-position-duration-429402"></a>Hiba történik, amikor egy alkalmazottat visz át, és a dolgozó beosztásának hozzárendelési dátuma a beosztás időtartama előtt van (429402)

Az ebben a helyzetben az alkalmazott átvitelekor adott hibaüzenetek frissítve lettek, hogy jobban leírják a probléma javításához szükséges módosításokat.

## <a name="attachments-capabilities-in-employee-self-service-benefits-enrollment"></a>Az alkalmazotti önkiszolgálói juttatások jelentkezésének mellékletcsatolási lehetőségei
 
Most már hozzáadhat mellékleteket a juttatások jelentkezési folyamata során minden olyan csomaghoz, amelyre az alkalmazott jelentkezik. Ezt követően megtekintheti a **dolgozó regisztrált juttatásai** űrlap mellékleteit.

## <a name="in-preview"></a>Előnézetben

## <a name="human-resources-application-in-teams"></a>Human Resources alkalmazás a Teamsben

Az alkalmazottak megtekinthetik és kérhetik a munkából való távollétet a Microsoft Teams alkalmazásban. Ezek egy robottal lépnek interakcióba a szabadságkérelmek létrehozásához. További tájékoztatás: [Human Resources alkalmazás a Teamsben](https://go.microsoft.com/fwlink/?linkid=2127841). 

## <a name="leave-suspension"></a>Szabadság felfüggesztése

Egy alkalmazottra vonatkozóan felfüggesztheti a szabadságokat és a távollétet. A szabadság felfüggesztése kiválasztott távolléti típusoknál leállítja az elhatárolást. Ha a felfüggesztés a könyvelés feldolgozását követően következik be, akkor a szabadság felfüggesztése az alkalmazott szabadságának egyenlegéhez egy arányosan korrigált kiigazítást hoz létre. További információ: [Szabadság felfüggesztése](hr-leave-and-absence-suspend-leave.md).

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>Felhasználói élmény frissítése annak jelzésére, hogy az elhatárolás fel van függesztve (429550)

A felhasználói élmény immár jelzi, hogy az elhatárolás fel van függesztve egy tervhez.

## <a name="coming-soon"></a>Hamarosan

## <a name="database-logging-in-preview-in-june"></a>Adatbázis naplózása (júniusban előzetes verzióban)

Az adatbázis-naplózási funkció segítségével meghatározhatja, hogy mely táblákat és mezőket kell figyelni. Azt is lehetővé teszi, hogy meghatározza a változáskövetést igénylő eseményeket. A lekérdezési lehetőségekkel ezek a változások az idő függvényében megtekinthetők.

## <a name="buy-and-sell-leave-in-preview-june-1"></a>Szabadság eladása és vásárlása (a június 1-jei előzetes verzióban)

Néhány szervezet olyan juttatást biztosít, amely lehetővé teszi az alkalmazottak számára, hogy megvásárolják vagy eladják a szabadságukat. Ezt a folyamatot gyakran manuálisan kell kezelni. Ez a funkció automatizálja a HR részleg házirendjeinek és kéréseinek kezelését, valamint segít kiküszöbölni a hibákat a szabadságkezelési folyamat racionalizálása során. További tájékoztatás:

- [Szabadság vásárlásával és eladásával kapcsolatos irányelv kezelése](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Szabadság vásárlása és eladása](hr-employee-self-service-buy-sell-leave.md)

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Az adatkezelési keretrendszer (DMF) entitásai a juttatások kezeléséhez
 
A juttatások kezelése entitások kiadnak. A DMF entitások lehetővé teszik az adatok importálását és exportálását a juttatáskezelés egyszerű konfigurálásához. A juttatáskezelési sablon az adatok áthelyezésére is elérhető lesz. A sablon egymást követő módon exportálja és importálja az adatokat az adatfüggőségek tiszteletben tartásához.

## <a name="add-reason-code-to-accrual-suspensions-june-1"></a>Okkód hozzáadása az elhatárolás-felfüggesztésekhez (június 1.)

Okkódok kerültek hozzáadásra az elhatárolás-felfüggesztéshez.

## <a name="carry-forward-rules-june-1"></a>Átvitel/áthozat szabályai (június 1.)

Megadhatja, hogy az átviteli szabadságtípust az átviteli egyenlegekhez, ahová az átviteli korrekciók ár lesznek helyezve. Ha például egy alkalmazott 10 napot visz át, akkor a 10 napnál más szabadság-típust is kiválaszthat. További tájékoztatás: [Szabadság és távolléti típusok konfigurálása](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types-june-1"></a>Felfüggeszti a távollét elhatárolását a megadott szabadságtípusokhoz (június 1.)

Ebben a kiadásban a HR olyan szabályt hozhat létre, amely felfüggeszti a távolléti elhatárolásokat a fizetés nélküli szabadságokhoz megadott szabadságkérelmekhez. A fizetetlen szabadság lehet egy típus, de ez nem kötelező. Bármilyen szabadságot egy másik szabadság típus alapján fel lehet függeszteni.

## <a name="dmf-entity-available-for-accrual-suspensions-june-1"></a>A DMF entitás elérhető az elhatárolásfelfüggesztésekhez (június 1.)

A DMF entitás immár elérhető az elhatárolás-felfüggesztésekhez.

## <a name="see-also"></a>Lásd még

[Új vagy módosult elemek a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)