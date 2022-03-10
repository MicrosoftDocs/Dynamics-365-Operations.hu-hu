---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. szeptember 16.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. szeptember 16-i kiadásban.
author: jcart1106
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-09-16
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cd3424db6bf918b4041f6d12e5d840bc3a8dfef7
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8061573"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-16-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. szeptember 16.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Ez a témakör a Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le. A változtatások a 8.1.3557-es buildszámra vonatkoznak. A néhány funkció mellett látható, zárójelben lévő számok tájékoztatásként a Lifecycle Services (LCS) támogatási számaira vonatkoznak.

## <a name="included-in-this-release"></a>A verzióban megtalálható

-  [Mentett nézetek – általános elérhetőség](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability)<br>- További információ: [Mentett nézetek](../fin-ops-core/fin-ops/get-started/saved-views.md). 

- A **Pozícióműveletek** képernyő frissített dimenziókat és egy új párbeszédet tartalmaz (469495).

- Ha a **Dolgozói adatok elérésének korlátozása** elemet igen értékre állítja **Speciális hozzáférés** elemnél a **Human Resources megosztott paraméterei** juttatások képernyői most csak a megfelelő dolgozókat mutatják (393384).

- Új naptár-generálási beállítások a **WorkCalendar** entitásban (477055):<br>- Alapértelmezett befejezési idő<br>-    Alapértelmezett kezdési idő<br>- Péntek munkanap<br>- Hétfő munkanap<br>- Szombat munkanap<br>- Vasárnap munkanap<br>- Csütörtök munkanap<br>- Kedd munkanap<br>- Szerda munkanap<br>- Munkanaptár ünnepnap-azonosító

- A **LeaveBankTransactionV1** entitás most az okkódot (477823) tartalmazza.

- Most mentheti a feladatrögzítéseket (492923).

- Az adatok mostantól sikeresen közzétéve a **HCMWorkerContactEntity** (427620) entitásból.

- A **Kompenzáció** gyorslap immár megjelenik a **dolgozói műveletek** képernyőjén az alvállalkozó dolgozótípushoz(482494).

- A **Fix kompenzáció** beállítása esetén kötelező megadni a **Szint** és a **Csomag** mezőt. Ha üresen hagyja ezeket a mezőket, egy hibaüzenet jelenik meg (482497).

- A **Konstrukció típusa** mező a **Juttatások** alatt immár egy legördülő lista (488768).

- A rendszergazdák most értesítést kapnak, ha egy egyéni mezőt törölnek az emberi Human Resources alkalmazásból (481408).

- Az alkalmazotti munkaviszonyának megszüntetése folyamat során a Human Resources a várakozásnak megfelelően működik, és nem változtatja meg a kiválasztott vállalatot a zárolást követően (479877). 

- A vezetők már nem adhatnak hozzá szám oszlopot a személyre szabás segítségével (485317).

- A vezetők már nem tudják eltávolítani az adattartomány-szűrőt a lejáró azonosítószámokból (485321).

- Ha a **Felettes** mező üres, akkor a beosztás részletei továbbra is megjelennek, ha az egérmutatót a beosztásra helyezi (433328).

- Az alkalmazottak most már megtekinthetik a juttatási konstrukció adatait az Alkalmazotti önkiszolgáló szolgáltatásban (481676).

- Az alkalmazottak most már megtekinthetik az összes regisztrált tanfolyamot (429048).

- Most korlátozhatja a **Szakmai tanúsítványok** lap megjelenítési beállításait. Az aktuális jogi személyre, a dolgozói állapotra és a dolgozó típusára (451501) korlátozhatja megjelenítési beállításokat. 


## <a name="in-preview"></a>Előnézetben

### <a name="human-resources-app-in-teams"></a>Human Resources alkalmazás a Teamsben

Az alkalmazottak megtekinthetik és kérhetik a munkából való távollétet a Microsoft Teams alkalmazásban. Ezek egy robottal lépnek interakcióba a szabadságkérelmek létrehozásához. További tájékoztatás:

- [Alkalmazott szabadsága és távolléte a Microsoft Teams rendszerben](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) a Dynamics 365 2020-as kiadási hullámának 1. csomagjában
- [Human Resources alkalmazás a Teamsben](./hr-admin-teams-leave-app.md) a Human Resources dokumentációjában

### <a name="human-resources-app-in-teams-preview-features"></a>Human Resources alkalmazás a Teamsben előzetes funkciók
 
-  **Értesítések**: A szabadságkérelmek beküldői és jóváhagyói értesítést kapnak az Emberi erőforrások alkalmazásban a Teamsben. A jóváhagyók jóvá tudják hagyni vagy el tudják utasítani a távolléti kérelmeket. A kérelem jóváhagyása vagy elutasítása esetén a beküldő értesítést kap. További tájékoztatás:
   - [Alkalmazott szabadsága és távolléte a Microsoft Teams rendszerben](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) a Dynamics 365 2020-as kiadási hullámának 2. csomagjában
   - [Human Resources alkalmazás értesítéseinek engedélyezése a Teamsben](./hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) a Human Resources dokumentációjában
   - [A Teams értesítéseinek be-és kikapcsolása az egyes felhasználók számára](./hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users) a Human Resources dokumentációjában
   - [Teams értesítések](./hr-teams-leave-app.md#respond-to-teams-notifications) a Human Resources dokumentációjában
   - [A csapat távolléti naptárának megtekintése a](./hr-teams-leave-app.md#view-your-teams-leave-calendar) a Human Resources dokumentációjában
 
- **Vezetői szabadságnaptár**: A felettesek a naptár nézetben megtekinthetik a beosztottjaik jóváhagyott és függőben lévő távolléteit. Ez a nézet annak áttekintését teszi lehetővé, hogy a csapattagok mikor nem dolgoznak. További tájékoztatás:
   - [Alkalmazott szabadsága és távolléte a Microsoft Teams rendszerben](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) a Dynamics 365 2020-as kiadási hullámának 2. csomagjában
   - [A csapat távolléti naptárának megtekintése a](./hr-teams-leave-app.md#view-your-teams-leave-calendar) a Human Resources dokumentációjában

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a>Konfigurációs beállítás a hozzám rendelt munkaelemek lista pozicionálásához (477004)

Most egy új beállítás érhető el, amivel a **Hozzám rendelt munkaelemek** lista az irányítópult jobb oldali oszlopába helyezhető. Ezzel a módosítással az összes munkaelem és a teendőlista ugyanazon a területen jelenik meg. A funkció engedélyezéséhez kapcsolja be az **Előzetes verzió – Munkafolyamat-élmények továbbfejlesztései** lehetőséget a Funkciókezelés modulban. Az előzetes funkciók bekapcsolásával kapcsolatos további információt lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakörben.

Ez a funkció segíti a személyzeti műveletek képernyőjén megjelenő munkafolyamat-beállításokat is. A munkafolyamat-beállítások a gyors hozzáféréshez a művelet gyors lapja fölött is megjelenhetnek. További tájékoztatás: 

- [A szervezeti és személyzetkezelési munkafolyamatok fejlesztései](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) a Dynamics 365 2020-as 2. kiadási hullám csomagjában

![Hozzám rendelt munkatételek.](./media/hr-workflow-work-items-assigned-to-me.png)

![Munkafolyamat-elemek gyors elérése.](./media/hr-workflow-quick-access.png)

### <a name="leave-and-absence-calendar"></a>A szabadságok és távollétek naptára

Ez a kiadás további naptár-beállításokat tartalmaz a szabadság- és a távolléti naptárakhoz. További tájékoztatás: [Csoportos és vállalati naptárak megtekintése](./hr-employee-self-service-calendar.md).

## <a name="coming-soon"></a>Hamarosan

### <a name="checklist-entities-included-in-dataverse"></a>Ellenőrzőlista-entitások szerepelnek a következőben: Dataverse

Az Előkészítés, Felszámolás, Áthelyezések és Üzleti folyamatok hamarosan elérhetők lesznek a Dataverse alkalmazásban.

### <a name="benefits-management-reason-codes"></a>Juttatások kezelése okkódok

A juttatáskezelés okkódjai hamarosan kombinálva lesznek a Human Resources meglévő okkódjaival. Ha a Juttatások kezelése modulban több, mint 15 karakterből álló okkódok szerepelnek, akkor az Juttatások kezelése **Okkódok** űrlapján az okkódot maximum 15 karakter hosszúra kell módosítania. Miután frissítette a nevet, az okkód a Személyzetkezelés modul meglévő okkódok képernyőjén fog megjelenni. Ez a változtatás a jövőben elérhető lesz, és nem fogja befolyásolni a meglévő funkciókat.

## <a name="see-also"></a>Lásd még

[Újdonságok vagy változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2019 második kiadási hullámának áttekintése](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
