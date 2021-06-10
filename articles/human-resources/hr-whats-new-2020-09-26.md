---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. szeptember 26.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. szeptember 26-i kiadásban.
author: jcart1106
ms.date: 09/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: aa0a26144cec387d35c2549c82b6179f2940c0cf
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051689"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-26-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. szeptember 26.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a témakör a Dynamics 365 Human Resources új, módosított vagy nemsokára várható szolgáltatásait írja le. A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

További tájékoztatás az új szolgáltatásokról és a nyilvános megjelenési dátumokról: [A Dynamics 365 Human Resources 2020. második kiadási hullámának áttekintése](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.3589-hf.3 buildszámra vonatkoznak.

### <a name="new-features"></a>Új funkciók

Az alábbi funkció általában a következő verzióval lesz elérhető:

- **A 10.0.13 platformfrissítés már elérhető**: a frissítéssel kapcsolatos további tudnivalókért lásd: [Platformfrissítések a Finance and Operations alkalmazások 10.0.13 verziójához (2020. október)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-13.md).

### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. Előfordulhat, hogy a jelen témakör frissítései olyan hibajavításokat is tartalmazhatnak, amelyek annak első közzététele után léptek életbe.

| Kiadás száma | Kiadás | Leírás |
| --- | --- | --- |
| 469495 | A pénzügyi dimenziók alapértelmezett rácsának és párbeszédpanelének frissítése | A pénzügyi dimenziók rácsa és párbeszédpanel frissült a Human Resources alkalmazás minden részében. |
| 474887 | A szabadságkérelem munkaelem rossz hivatkozást nyit meg kézi döntés esetén | Amikor egy munkafolyamat-konfiguráció manuális döntést tartalmaz, a **Hozzám rendelt munkatételek** elemről a szabadságkérelemre lépve nem a megfelelő hivatkozás jelenik meg, és vagy egy üres képernyő, vagy az aktuális felhasználó által a kézi döntés céljára hozzárendelt, nem pedig az aktuális felhasználó által létrehozott szabadságkérelem jelenik meg. |
| 474962 | A szabadság és a távollét paraméterek entitása félreérthető feliratú mezőket tartalmaz | A szabadság és a távollét paraméterei entitások címkéi a frissítésben egyértelműbbek lettek. |
| 481401 | Az eredményszemléletű feldolgozás lefagy, ha a könyvelési dátum alapja a könyvelési kezdési dátum után és a hónap végén van | Az eredményszemléletű feldolgozást frissítettük, hogy ne legyen késés, ha a könyvelési dátum alapja a könyvelés kezdő dátuma után és a hónap végén van. |
| 447167 | A lejáró rekordok listája inaktív dolgozókat tartalmaz | A **Személyzet kezelése** rész **Lejáró rekordok** lapja inaktív dolgozókat tartalmaz. Most már csak az aktív dolgozók szerepelnek benne. |
| 486840 | Hibás szabadságkérelem nyílik meg a **Hozzám rendelt munkatételek** elemből | A **Hozzám rendelt munkatételek** elemből szabadságkérelem megnyitása az aktuális felhasználóhoz rendelt legutóbbi szabadságkérelmet. |
| 506868 | A Dataverse **Cím** mezeje nicns beállítva a **Feladat beosztása** entitás esetén | A **Cím** mező a **Beosztás** és a **Feladat beosztása** entitásokban nem meghatározottként jelenik meg. A **Cím** mező most már megjelenik. |
| 430359 | Nem érhetők el a felszámolási ellenőrzőlista-feladatok, ha a vezető és alkalmazotti szerepköröket hozzárendelték | A jövőbeli megszűnési dátumú dolgozók csak akkor férhetnek hozzá a ellenőrzőlista feladataihoz, ha kizárólag alkalmazotti vagy vezetői szerepkörrel rendelkeztek. Most már csak az alkalmazotti vagy vezetői szerepkörrel rendelkező felhasználók férhetnek hozzá a jövőbeli megszűnési dátummal rendelkező felszámolási feladatokhoz. |
| 458102 | Az új alkalmazott nem jelenik meg a **Dolgozó bérszámfejtési információi** entitásban a létrehozásakor | Az új alkalmazottak bekerültek a dolgozói bérszámfejtési entitásba anélkül, hogy az entitás exportálása előtt meg kellene nyitni az alkalmazott bérszámfejtési adatait. |

## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- vagy kikapcsolásával kapcsolatos további információkért lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakört.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Human Resources alkalmazás a Microsoft Teams alkalmazásban | [Alkalmazott szabadsági és távolléti élménye a Microsoft Teams rendszerben](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Human Resources alkalmazás a Teamsben](./hr-admin-teams-leave-app.md)<br>[Szabadságkérelmek kezelése a Teamsben](hr-teams-leave-app.md) |
| Továbbfejlesztett munkafolyamat-kérelmek és -jóváhagyások | [Szervezeti és személyzeti felügyeleti munkafolyamat-tapasztalatok továbbfejlesztései](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Konfigurációs beállítás a hozzám rendelt munkaelemek lista pozicionálásához](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |

## <a name="coming-soon"></a>Hamarosan

A következő új funkciót egy jövőbeli kiadásra ütemeztük:

- [Egyéni hivatkozások a vezetői önkiszolgáló rendszerben](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service)

A tervezett szolgáltatások és az ütemezett kiadások teljes listája az alábbi témakörben olvasható: [A Dynamics 365 Human Resources 2019. második kiadási hullámának áttekintése](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/).

## <a name="additional-resources"></a>További erőforrások

[Mik az újdonságok vagy változások a Human Resources rendszerben](hr-admin-whats-new.md)
[A Dynamics 365 Human Resources 2020 második kiadási hullámának terveti](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)
[Frissítési folyamat](hr-admin-setup-update-process.md)
[Funkciók kezelése](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]