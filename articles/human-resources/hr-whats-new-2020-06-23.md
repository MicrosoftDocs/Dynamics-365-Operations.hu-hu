---
title: A Dynamics 365 Human Resources új és módosult elemei (2020. június 25.)
description: Ez a témakör olyan funkciókat ismertet, amelyek vagy újak, vagy módosulnak a Microsoftban Dynamics 365 Human Resources 2020. június 23-án.
author: andreabichsel
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7fe8b685a2b492fe5ad23b410f6a99d81991e98a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904101"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-23-2020"></a>A Dynamics 365 Human Resources új és módosult elemei (2020. június 23.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Ez a cikk a Dynamics 365 Human Resources szolgáltatásban található új vagy módosított funkciókat írja le. A változtatások a 8.1.3347-es buildszámra vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok az LCS támogatási számaira vonatkoznak referenciaképpen.

## <a name="when-an-enrollment-is-expired-for-a-terminated-employee-the-leave-type-balance-and-amount-are-all-cleared-in-the-leave-enrollment-form-444867"></a>Ha egy kilépett alkalmazottnál lejár a beléptetés, akkor a szabadság típusa, egyenlege és összege törlődik a Szabadságregisztrációs űrlapról (444867).

A **Szabadság típusa**, **Egyenleg** és **Összeg** értékeit a program a kiválasztáskor nem törli, hanem megtartja.

## <a name="incorrect-forecasted-balance-when-new-feature-leave-accrual-for-a-single-company-or-a-single-plan-is-enabled-456553"></a>Hibás előre jelzett egyenleg, ha a z új funkció (Szabadság elhatárolása egyetlen vállalat vagy egy terv esetében) engedélyezve van (456553).

A hibás előrejelzett egyenleg most megjeleníti, ha a szabadság elhatárolása egyetlen vállalat vagy egy terv esetében engedélyezve van.

## <a name="entities-with-relations-that-result-in-duplicate-navigation-properties-456486"></a>Ismétlődő navigációs tulajdonságokat eredményező kapcsolatokat tartalmazó entitások (456486)

Ez a kiadás javítja több entitás navigációs tulajdonságával (objektumkapcsolat) kapcsolatos hibát. Ismétlődő objektumkapcsolatok észlelhetők. Ezek a helyzetek mind javítva lettek.
 
## <a name="cross-company-comments-on-performance-review-455536"></a>Több vállalatot érintő megjegyzések a Teljesítmény-ellenőrzéssel kapcsolatban (455536)

A több vállalatot érintő megjegyzések most már láthatók a javításnak köszönhetően a teljesítmény-ellenőrzésekben. Ez a módosítás korrigálja a különböző vállalatokban ugyanahhoz a teljesítmény-ellenőrzéshez megadott véleményezői megjegyzések nézetét.
 
## <a name="inconsistency-in-showing-compensation-management-data-432562"></a>Inkonzisztencia a kompenzációkezelési adatok megjelenítésében (432562)

A kompenzációs adatok konzisztens nézete a vezetői önkiszolgáló szolgáltatásban most már megmarad. Attól függően, hogy hogyan navigál a dolgozó **Kompenzáció részletei** lehetőséghez, a kompenzációs adatok konzisztensen jelennek meg a vezetőknek.
 
## <a name="fixed-compensation-plans-effective-date-defaults-to-todays-date-411994"></a>Javítva lett a probléma, amely miatt a kompenzációs csomag érvényességi dátuma az adott napi dátumra állt be alapértelmezettként (411994)

A kompenzáció kezdő dátuma most az alkalmazotthoz rendelt beosztás kezdő dátumán alapul.

## <a name="leave-and-absence-form-enable-half-day-definition-is-disabled-when-form-opens-452607"></a>Szabadság és távollét a Félnapos meghatározás engedélyezéséből le van tiltva az űrlap megnyitásakor (452607)

Ezzel a módosítással a **Félnapos meghatározás engedélyezése** engedélyezett addig, amíg nem léteznek új szabadságtranzakciók. 

## <a name="unable-to-publish-to-hcmdiscussionentity-via-excel-totalratingscore-field-error-453899"></a>Nem lehet közzétenni a HcmDiscussionEntity az elemhez az Excel programon keresztül; TotalRatingScore mező hibája (453899)

Most frissítheti a **TotalRatingScore** mezőt a **HCMDiscussionEntity** használatával az Excel-munkafüzet-tervezőben.

## <a name="in-preview"></a>Előnézetben

## <a name="database-logging"></a>Adatbázis naplózása

Az adatbázis-naplózás segítségével meghatározhatja, hogy mely táblát és mezőket kell figyelni. Azt is lehetővé teszi, hogy meghatározza a változáskövetést igénylő eseményeket. Az adatbázis-naplózási funkciók segítségével ezeknek a változásoknak a történetét megjelenítheti. További tájékoztatás: [Adatbázis-naplózás konfigurálása és kezelése](hr-admin-database-logging.md).

## <a name="mandatory-fields"></a>Kötelező mezők 

Most már kötelezővé teheti a mezőket a Human Resources személyre szabási funkcióival. Ehhez a funkcióhoz **Mentett nézetek** szükségesek.

## <a name="human-resources-application-in-teams"></a>Human Resources alkalmazás a Teamsben

Az alkalmazottak megtekinthetik és kérhetik a munkából való távollétet a Microsoft Teams alkalmazásban. Ezek egy robottal lépnek interakcióba a szabadságkérelmek létrehozásához. További tájékoztatás: [Human Resources alkalmazás a Teamsben](./hr-admin-teams-leave-app.md). 

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

## <a name="configure-the-name-of-employee-self-service"></a>Alkalmazotti önkiszolgáló rendszer nevének konfigurálása

Az **Emberi erőforrások paraméterei** között egy új beállítás érhető el, ahol az Alkalmazotti önkiszolgáló rendszer munkaterület neve Önkiszolgáló rendszerre frissíthető.

## <a name="checklist-entities-included-in-dataverse"></a>Ellenőrzőlista-entitások szerepelnek a következőben: Dataverse

Az Előkészítés, Felszámolás, Áthelyezések és Üzleti folyamatok hamarosan elérhetők lesznek a Dataverse alkalmazásban.

## <a name="see-also"></a>Lásd még

[Új vagy módosult elemek a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]