---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. augusztus 20.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. augusztus 20-i kiadásban.
author: Darinkramer
manager: AnnBe
ms.date: 8/20/2020
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
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 46dadb8834195c5dd06cd1c56d79324def7d9f2d
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527481"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-20-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. augusztus 20.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a témakör a Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le. A változtatások a 8.1.3478-es buildszámra vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok tájékoztatásként a Lifecycle Services (LCS) támogatási számaira vonatkoznak.

## <a name="show-upcoming-and-pending-leave-of-absence-information-to-cards-in-people-workspace"></a>Az elkövetkező és függőben lévő távolléti információk megjelenítése a Személyek munkaterületén lévő kártyákhoz

A folyamatban lévő és a közelgő távozási kérelem beállításai a **Személyek** munkaterületének szabadság és távollét lapjain érhetők el.

## <a name="private-field-isnt-yes-by-default-for-employee-role-in-employee-self-service-477106"></a>A privát mező alapértelmezés szerinti értéke nem „Igen” Alkalmazotti önkiszolgáló Alkalmazott szerepkörében (477106)

A **Privát** mező alapértelmezésként az **Igen** értéket kapja, amikor az alkalmazottak új címrekordokat adnak hozzá az Alkalmazotti önkiszolgáló rendszer **Személyes adatok** lapján. 

## <a name="candidates-to-hire-fasttab-in-personnel-management-shows-an-incorrect-count-of-candidates-470110"></a>A Személyzetkezelés modulba felvenni kívánt jelöleknél helytelen számú jelentkezőt jelenik meg (470110)

A **Személyzetkezelés** lap most pontosan megjeleníti a felvenni kívánt jelöltek számát. 

## <a name="cant-enter-sickness-for-terminated-employee-when-accrual-is-set-to-zero-446195"></a>A kilépett alkalmazottnak nem lehet betegszabadságot adni, ha az elhatárolás nullára van állítva (446195)

A szabadságtranzakciók ezentúl engedélyezve vannak a jövőben kiléptetett alkalmazottaknál, az elhatárolás pedig nulla értékre van állítva. A szabadságtranzakciók az alkalmazott kiléptetési dátumáig megadhatók. 

## <a name="adding-custom-fields-to-the-new-worker-form-disables-the-fields-in-the-action-pane-for-manage-leave-473314"></a>Ha egyéni mezőket ad hozzá az új Dolgozó képernyőhöz, az letiltja a mezőket a Szabadság kezelése műveleti panelén (473314)

Ha az új **Dolgozó** képernyő műveleti panelének beállításai a **Szabadság kezelésénél** nem lesznek letiltva, ha egyéni mezők lettek hozzáadva a **Dolgozó** képernyőn.

## <a name="making-the-leave-comment-field-mandatory-allows-a-leave-request-to-be-submitted-when-no-comment-is-entered-473543"></a>Ha a Szabadság megjegyzése mezőt kötelezővé teszi, akkor megjegyzés megadása nélkül nem küldhető be szabadságkérelem (473543)

A megjegyzés mezők immár lehetnek kötelezőek, és a szabadságkérelmek ezt figyelembe veszik. A kötelező mezők egy előzetes funkció.

### <a name="dmf-entity-available-for-accrual-suspensions"></a>A DMF entitás elérhető az elhatárolás-felfüggesztésekhez

A DMF entitás immár elérhető az elhatárolás-felfüggesztésekhez.

## <a name="in-preview"></a>Előnézetben

### <a name="mandatory-fields"></a>Kötelező mezők

Kötelezővé teheti a mezőket a Human Resources személyre szabási funkcióival. Ehhez a funkcióhoz **Mentett nézetek** szükségesek. További információ a mentett nézetekről:

- [Mentett nézetek – nyilvános megjelenés](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) a Dynamics 365 2020-as kiadási hullámának 2. csomagjában
- [A mentett nézeteket teljes mértékben kihasználó képernyők létrehozása](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/user-interface/understanding-saved-views)

### <a name="human-resources-application-in-teams"></a>Human Resources alkalmazás a Teamsben

Az alkalmazottak megtekinthetik és kérhetik a munkából való távollétet a Microsoft Teams alkalmazásban. Ezek egy robottal lépnek interakcióba a szabadságkérelmek létrehozásához. További tájékoztatás:

- [Alkalmazott szabadsága és távolléte a Microsoft Teams rendszerben](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) a Dynamics 365 2020-as kiadási hullámának 1. csomagjában
- [Human Resources alkalmazás a Teamsben](https://go.microsoft.com/fwlink/?linkid=2127841)

## <a name="coming-soon"></a>Hamarosan

### <a name="human-resources-app-in-teams-preview-features"></a>Human Resources alkalmazás a Teamsben előzetes funkciók
 
-  **Értesítések**: A szabadságkérelmek beküldői és jóváhagyói értesítést kapnak az Emberi erőforrások alkalmazásban a Teamsben. A jóváhagyó jóváhagyhatja vagy elutasíthatja a szabadságkérelmeket, és értesítést kaphat, hogy a kérést jóváhagyták vagy elutasították.
 
- **Vezetői szabadságnaptár**: A felettesek a naptár nézetben megtekinthetik a beosztottjaik jóváhagyott és függőben lévő távolléteit. Ez a nézet annak áttekintését teszi lehetővé, hogy a csapattagok mikor nem dolgoznak.

### <a name="checklist-entities-included-in-common-data-service"></a>Ellenőrzőlista-entitások szerepelnek a következőben: Common Data Service

Az Előkészítés, Felszámolás, Áthelyezések és Üzleti folyamatok hamarosan elérhetők lesznek a Common Data Service alkalmazásban.

## <a name="known-issues"></a>Ismert problémák

Előfordulhat, hogy a **Funkciókezelés** munkaterületen olyan általánosan elérhető funkciók jelennek meg, amelyek előnézeti funkcióként le vannak tiltva. Az alábbiakban a helytelen állapottal megjelenő általánosan elérhető szolgáltatások listája látható. 

- Juttatáskezelés
- Esetkezelés
- Adatbázis-naplózás (auditálás)
- Szabadságelhatárolás egyetlen vállalatnál vagy egyetlen tervnél
- Szabadság- és távollét-elhatárolás felfüggesztése
- Egyenlegkorrekció okkódja és megjegyzése
- Szabadság vásárlása és eladása
- A szabadságok és távollétek naptára
- Szabadságáthozat szabályai
- Szabadságelhatárolás auditálása
- Szabadságelhatárolás törlése
- Szabadságelhatárolás kerekítése
- Több szabadságtípus konfigurálása egyetlen szabadságtervhez
- Szabadidő-fejlesztések frissítése
- Alkalmazott teljes munkaidejének megfelelő érték használata az elhatároláshoz
- Vállalatközi kompenzációs nézet
- Teljesítményértékelések nyomtatása
- Szabadságelhatárolás helyesbítése ünnepekkel

### <a name="benefit-plan-employee-entity"></a>Juttatási terv alkalmazotti entitás 

A közelmúltban két olyan problémát észleltünk, amely a **BenefitsPlanEmployee** entitásra vonatkozik. A dolgozói regisztrációk importálásakor a **Fedezetkód** és a **Konstrukció típuskódja** helytelenül vannak beállítva. Ez a hiba azt eredményezi, hogy az alkalmazotti juttatási konstrukciók helytelenül jelennek meg a **Dolgozói juttatáskonstrukció** képernyőjén és az Alkalmazotti önkiszolgáló rendszer **Nyitott belépés** képernyőjén. Ez a hiba hatással lehet arra is, ahogy az alkalmazottak konstrukciókat tudnak kiválasztani az Alkalmazotti önkiszolgáló rendszerben. Jelenleg nincs megkerülő megoldás. Ez egy magas prioritású javításként kezeljük, és a javítás a következő verzióval fog megjelenni.

## <a name="see-also"></a>Lásd még

[Új vagy módosult elemek a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]