---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. szeptember 03.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. szeptember 3-i kiadásban.
author: Darinkramer
manager: tfehr
ms.date: 9/03/2020
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
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ddffff18e1d6d16bd5a5f7e7021f9a34651307fa
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527458"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-3-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. szeptember 3.)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a témakör a Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le. A változtatások a 8.1.3504-es buildszámra vonatkoznak. A néhány fejlécben látható, zárójelben lévő számok tájékoztatásként a Lifecycle Services (LCS) támogatási számaira vonatkoznak.

A Human Resources közelgő szolgáltatásaival kapcsolatos további tudnivalókat lásd: [Áttekintés: Dynamics 365 Human Resources 2019-es 2. kiadási hullám](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/). A Human Resources frissítési folyamatával kapcsolatos további tudnivalókat lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

## <a name="in-this-release"></a>Ebben a verzióban

### <a name="new-default-financial-dimensions-grid-and-dialog-pattern-throughout-human-resources-469495"></a>Új alapértelmezett pénzügyi dimenziók rácsa és párbeszédpanel-mintázata a Human Resources alkalmazás minden részében (469495)

A pénzügyi dimenziók új mintája jelenleg a következő területeken érhető el:

- Pozícióműveletek (Űrlap: **HcmPositionActionDetail**)
- Bérlista bevételkódjai (Űrlap: **PayrollEarningCode**)

### <a name="entries-dont-appear-in-company-leave-calendar-if-leave-and-absence-calendar-enhancements-arent-enabled-484406"></a>A bejegyzések nem jelennek meg a vállalat szabadságnaptárában, ha a szabadság és a távolléti naptár továbbfejlesztései nem engedélyezettek (484406)

Ez a kiadás javítja azt a hibát, amikor a szabadságbejegyzések nem jelennek meg a vállalat szabadságnaptárában. Ez a probléma csak akkor fordul elő, ha a **Szabadság és távolléti naptár fejlesztései** funkciókezelési beállítás nincs engedélyezve.

### <a name="benefitplanemployeeentity-issue-467597"></a>BenefitPlanEmployeeEntity problémája (467597)

Ez a kiadás kijavít egy hibát a **BenefitsPlanEmployee** entitással kapcsolatosan. A dolgozói regisztrációk importálásakor a **Fedezetkód** és a **Konstrukció típuskódja** immár helyesen vannak beállítva. Ez a hiba azt eredményezte, hogy az alkalmazotti juttatási konstrukciók helytelenül jelennek meg a **Dolgozói juttatáskonstrukció** űrlapjain és az Alkalmazotti önkiszolgáló rendszer **Nyitott belépés** képernyőjén.

### <a name="electronic-file-1094-c-output-missing-letter-in-xml-435190"></a>Elektronikus fájl 1094-C kimenet hiányzó betű az XML-ben (435190)

A módosítás javítja azt a hibát, amellyel a 1094-C kimeneti fájlból hiányzott eggy szükséges karakter az adóhatóságnak történő benyújtás során.

### <a name="employee-variable-compensation-table-mapped-to-fixed-compensation-form-476117"></a>Alkalmazott változó kompenzációs táblája a fix kompenzációs űrlapra leképezve (476117)

Ez a módosítás a fix kompenzációs mezőket a fix kompenzáció képernyőhöz igazítja. A változó kompenzációs mezők most már csak a változó kompenzáció képernyőjén érhetők el.

### <a name="leave-requests-allowed-before-enrollment-if-that-leave-type-has-a-negative-minimum-balance-469917"></a>A beléptetés előtt engedélyezve vannak a szabadságkérelmek, ha a szabadság típusának negatív minimális egyenlege van (469917)

Ez a módosítás tiltja a szabadság iránti kérelmek beírását a tervbe történő regisztráció előtt, még akkor is, ha a beiratkozás negatív minimális egyenleggel bír. Csak akkor adhat meg és küldhet be kérelmeket, ha a terv aktív.

### <a name="document-templates-dont-download-457279"></a>A dokumentumsablonok nem tölthetők le (457279)

Ezzel a módosítással most már letöltheti az összes dokumentumsablont. 

### <a name="data-displays-as-column-headers-instead-of-rows-for-the-pay-rate-field-in-the-compensation-plan-report-476077"></a>Az adatok oszlopfejlécként jelennek meg a kompenzációs terv jelentésben szereplő fizetési díjalap mező sorai helyett (476077)

Az elemzési jelentés most a **Fizetési díjalap** helyes adatait jeleníti meg.

## <a name="in-preview"></a>Előnézetben

### <a name="human-resources-application-in-teams"></a>Human Resources alkalmazás a Teamsben

Az alkalmazottak megtekinthetik és kérhetik a munkából való távollétet a Microsoft Teams alkalmazásban. Ezek egy robottal lépnek interakcióba a szabadságkérelmek létrehozásához. További tájékoztatás:

- [Alkalmazott szabadsága és távolléte a Microsoft Teams rendszerben](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) a Dynamics 365 2020-as kiadási hullámának 1. csomagjában
- [Human Resources alkalmazás a Teamsben](https://go.microsoft.com/fwlink/?linkid=2127841) a Human Resources dokumentációjában

### <a name="human-resources-app-in-teams-preview-features"></a>Human Resources alkalmazás a Teamsben előzetes funkciók
 
-  **Értesítések**: A szabadságkérelmek beküldői és jóváhagyói értesítést kapnak az Emberi erőforrások alkalmazásban a Teamsben. A jóváhagyók jóvá tudják hagyni vagy el tudják utasítani a távolléti kérelmeket. A kérelem jóváhagyása vagy elutasítása esetén a beküldő értesítést kap. További tájékoztatás:
   - [Alkalmazott szabadsága és távolléte a Microsoft Teams rendszerben](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) a Dynamics 365 2020-as kiadási hullámának 2. csomagjában
   - [Human Resources alkalmazás értesítéseinek engedélyezése a Teamsben](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-teams-leave-app#enable-notifications-for-the-human-resources-app-in-teams) a Human Resources dokumentációjában
   - [A Teams értesítéseinek be-és kikapcsolása az egyes felhasználók számára](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-teams-leave-app#turn-teams-notifications-on-or-off-for-individual-users) a Human Resources dokumentációjában
   - [Teams értesítések](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#teams-notifications) a Human Resources dokumentációjában
   - [A csapat távolléti naptárának megtekintése a](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#view-your-teams-leave-calendar) a Human Resources dokumentációjában
 
- **Vezetői szabadságnaptár**: A felettesek a naptár nézetben megtekinthetik a beosztottjaik jóváhagyott és függőben lévő távolléteit. Ez a nézet annak áttekintését teszi lehetővé, hogy a csapattagok mikor nem dolgoznak. További tájékoztatás:
   - [Alkalmazott szabadsága és távolléte a Microsoft Teams rendszerben](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) a Dynamics 365 2020-as kiadási hullámának 2. csomagjában
   - [A csapat távolléti naptárának megtekintése a](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#view-your-teams-leave-calendar) a Human Resources dokumentációjában

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a>Konfigurációs beállítás a hozzám rendelt munkaelemek lista pozicionálásához (477004)

Most egy új beállítás érhető el, amivel a **Hozzám rendelt munkaelemek** lista az irányítópult jobb oldali oszlopába helyezhető. Ezzel a módosítással az összes munkaelem és a teendőlista ugyanazon a területen jelenik meg. A funkció engedélyezéséhez kapcsolja be az **Előzetes verzió – Munkafolyamat-élmények továbbfejlesztései** lehetőséget a Funkciókezelés modulban. Az előzetes funkciók bekapcsolásával kapcsolatos további információt lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakörben.

Ez a funkció segíti a személyzeti műveletek képernyőjén megjelenő munkafolyamat-beállításokat is. A munkafolyamat-beállítások a gyors hozzáféréshez a művelet gyors lapja fölött is megjelenhetnek. További tájékoztatás: 

- [A szervezeti és személyzetkezelési munkafolyamatok fejlesztései](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) a Dynamics 365 2020-as 2. kiadási hullám csomagjában

![Hozzám rendelt munkatételek](./media/hr-workflow-work-items-assigned-to-me.png)

![Munkafolyamat-elemek gyors elérése](./media/hr-workflow-quick-access.png)

## <a name="coming-soon"></a>Hamarosan

### <a name="checklist-entities-included-in-common-data-service"></a>Ellenőrzőlista-entitások szerepelnek a következőben: Common Data Service

Az Előkészítés, Felszámolás, Áthelyezések és Üzleti folyamatok hamarosan elérhetők lesznek a Common Data Service alkalmazásban.

### <a name="benefits-management-reason-codes"></a>Juttatások kezelése okkódok

A juttatáskezelés okkódjai hamarosan kombinálva lesznek a Human Resources meglévő okkódjaival. Ha a Juttatások kezelése modulban több, mint 15 karakterből álló okkódok szerepelnek, akkor az Juttatások kezelése **Okkódok** űrlapján az okkódot maximum 15 karakter hosszúra kell módosítania. Miután frissítette a nevet, az okkód a Személyzetkezelés modul meglévő okkódok képernyőjén fog megjelenni. Ez a változtatás a jövőben elérhető lesz, és nem fogja befolyásolni a meglévő funkciókat.

## <a name="see-also"></a>Lásd még

[Új vagy módosult elemek a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]