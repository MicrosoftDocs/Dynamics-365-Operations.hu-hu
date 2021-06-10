---
title: Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. december 2.)
description: Ez a témakör a Microsoft Dynamics 365 Human Resources új vagy módosított szolgáltatásait írja le a 2020. december 2-i kiadásban.
author: marcelbf
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fa772691eebd177cae8cb8e470a48d27d1f33822
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054861"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-december-2-2020"></a>Új vagy módosult elemek a Dynamics 365 Human Resources szolgáltatásban (2020. december 2.)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör a Dynamics 365 Human Resources új, módosított vagy nemsokára várható szolgáltatásait írja le.

A frissítési folyamattal és ütemezéssel kapcsolatos további tudnivalókért lásd: [Frissítési folyamat](hr-admin-setup-update-process.md).

További tájékoztatás az új szolgáltatásokról és a nyilvános megjelenési dátumokról: [A Dynamics 365 Human Resources 2020. második kiadási hullámának áttekintése](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Ebben a verzióban

Ez a kiadás az alábbi új funkciókat és hibajavításokat tartalmazza. A változtatások a 8.1.3788-es buildszámra vonatkoznak.

### <a name="new-features"></a>Új funkciók

Az alábbi funkciók általában a következő verzióval lesznek elérhetők.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| A vezetők benyújthatnak toborzási kérelmeket pozíciókra | [A vezetők benyújthatnak toborzási kérelmeket a nyitott pozíciókra](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Toborzási kérelem hozzáadása](./hr-personnel-recruit.md#add-a-recruiting-request) |
| Továbbfejlesztett jelöltprofil a Személyzetkezelésben | [Továbbfejlesztett jelöltprofil a személyzetkezelésben](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Jelöltprofil hozzáadása vagy szerkesztése](./hr-personnel-recruit.md#add-or-edit-a-candidate-profile) |
| Egyszerűsített integráció engedélyezése a toborzási szolgáltatókkal | [Egyszerűsített integráció engedélyezése a toborzási szolgáltatókkal](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Jelöltek toborzása](./hr-personnel-recruit.md) |
| Egyéni hivatkozások a vezetői önkiszolgáló rendszerben | [Egyéni hivatkozások a vezetői önkiszolgáló rendszerben](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service) | [Egyéni hivatkozások a vezetői önkiszolgáló rendszerben](./hr-employee-manager-self-service-custom-links.md) |


### <a name="bug-fixes"></a>Hibajavítások

Ez a kiadás az alábbi hibajavításokat tartalmazza.

> [!NOTE]
> Célunk, hogy a lehető leghamarabb eljuttassuk Önhöz ezeket az információkat. Előfordulhat, hogy a jelen témakört frissítjök olyan hibajavításokkal, amelyek annak első közzététele után léptek életbe.

| Kiadás száma | Kiadás | Leírás |
| --- | --- | --- |
| 514087 | A BenefitEligibilityProcessResult eredménynek tartalmaznia kell a feldolgozáshoz használt datetime értéket. | A BenefitEligibity feldolgozási eredménye mostmár tartalmazza az utolsó feldolgozás datetime pecsétjét, amely korábban hiányzott. |
| 526903 | A juttatási regisztráció sikertelen a függő feleket tartalmazó csomagok esetében ha a **Kijelölt személyek automatikus kiválasztása** be van kapcsolva az **Human Resource megosztott paramétereiben**. | Kijavítottuk azt a problémát, amely miatt a juttatási regisztráció sikertelen volt az függő felek esetében, amikor a **Kijelölt személyek automatikus kiválasztása** beállítás be volt kapcsolva az alapértelmezett kijelölt személyek számára. |
| 521922 | **Távollét megjelenítése részletek nélkül** paraméter megjeleníti a szabadságkérelmeket a csapat távolléti naptárában. | A szabadság típusa, a szabadság típusának színe és a nap részletei a csapat távolléti naptárában megjelentek, amikor a **Tavollét megjelenítése részletek nélkül** értéke **Igen** volt a **Szabadság és távollét paramétereiben**. Ez ki lett javítva, és nincs megjelenítve a távollét típusa és az alapértelmezett típusszín (sötétkék) van használva minden szabadságtípushoz a csapat távolléti naptárában. |
| 527316 | A beosztás, a beosztás és a dolgozói értesítések címmódosításai nem szinkronizálódnak. | Korábban egy Cím kapcsolat lett hozzáadva a Feladat, a Beosztás és a Dolgozó entitásokhoz. A kapcsolat szinkronizálása a Human Resources és a Dataverseközött működött, de nem működött a Dataverse-szolgáltatásból származó értesítéseknél. Ez ki lett javítva. |
| 512275 | Távolítsa el a színbeállításokat a **Szabadság és távollét paramétereiből**. | Most, hogy a színek a szabadság típusokhoz definiálva vannak, a színbeállításokra már nincs szükség a **Szabadság és távollét paramétereiben**, így ezek el lettek távolítva.. |
| 437112 | Félrevezető hibaüzenet-szöveg az alkalmazotti beosztás-hozzárendelések során. | Frissített a hibaüzenetet, amikor megpróbálnak egy dolgozót felvenni, és azt hozzárendelni egy olyan beosztáshoz, ami nem aktív. Frissített üzenet: **A megadott beosztás nem aktív a foglalkoztatás kezdő dátumakor. Kérjük, ellenőrizze a beosztás időtartamát.** |
| 527816 | Teljesítményproblémák a **Szabadságolás** oldalon. | A teljesítmény javult a **Szabadidő** oldalon. |
| 523158 | A BenefitPeriodMigrationUpgrade és a BenefitPlanMigrationUpgrade nem hajtható végre. | Javítottuk az **Időszak** és a **Terv** juttatás-áttelepítés hibás végrehajtásával kapcsolatos problémákat. |

## <a name="in-preview"></a>Előnézetben

Az alábbi új funkciók előzetes verzióban érhetők el. A funkciók be- vagy kikapcsolásával kapcsolatos további információkért lásd a [Szolgáltatások kezelése](hr-admin-manage-features.md) című témakört.

| Funkció | Kiadási terv | Dokumentáció |
| --- | --- | --- |
| Human Resources alkalmazás a Microsoft Teams alkalmazásban | [Alkalmazott szabadsági és távolléti élménye a Microsoft Teams rendszerben](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Human Resources alkalmazás a Teamsben](./hr-admin-teams-leave-app.md)<br>[Szabadságkérelmek kezelése a Teamsben](hr-teams-leave-app.md) |
| Továbbfejlesztett munkafolyamat-kérelmek és -jóváhagyások | [Szervezeti és személyzeti felügyeleti munkafolyamat-tapasztalatok továbbfejlesztései](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Konfigurációs beállítás a hozzám rendelt munkaelemek lista pozicionálásához](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Integráció a LinkedIn Talent Hub szolgáltatással | [Integráció a LinkedIn Talent Hub szolgáltatással](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Integráció a LinkedIn Talent Hub szolgáltatással](./hr-admin-integration-linkedin.md) |
|Szabadságok vállalatközi nézete vezetőknek | [Munkavállalói szabadságok vállalatközi nézete vezetőknek](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Szabadság és távollét paramétereinek konfigurálása](./hr-leave-and-absence-parameters.md) |
|További betekintés biztosítása a szabadságegyenlegekbe| [További betekintés biztosítása a szabadságegyenlegekbe](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-into-leave-balances) | [Alkalmazotti szabadság kezelése](./hr-leave-and-absence-manage-employee-leave.md) |
| A vezetők benyújthatnak toborzási kérelmeket pozíciókra | [A vezetők benyújthatnak toborzási kérelmeket a nyitott pozíciókra](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Toborzási kérelem hozzáadása](./hr-personnel-recruit.md#add-a-recruiting-request) |
| Továbbfejlesztett jelöltprofil a Személyzetkezelésben | [Továbbfejlesztett jelöltprofil a személyzetkezelésben](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Jelöltprofil hozzáadása vagy szerkesztése](./hr-personnel-recruit.md#add-or-edit-a-candidate-profile) |
| Egyszerűsített integráció engedélyezése a toborzási szolgáltatókkal | [Egyszerűsített integráció engedélyezése a toborzási szolgáltatókkal](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Jelöltek toborzása](./hr-personnel-recruit.md) |

## <a name="coming-soon"></a>Hamarosan

A tervezett szolgáltatások és az ütemezett kiadások teljes listája az alábbi témakörben olvasható: [A Dynamics 365 Human Resources 2020. második kiadási hullámának áttekintése](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Lásd még

[Újdonságok vagy változások a Human Resources szolgáltatásban](hr-admin-whats-new.md)</br>
[A Dynamics 365 Human Resources 2020. második kiadási hullámának áttekintése](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Rendelés frissítése](hr-admin-setup-update-process.md)</br>
[Szolgáltatások kezelése](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]