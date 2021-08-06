---
title: Dynamics 365 Human Resources infrastruktúraegyesítés – GYIK
description: Ez a témakör a Microsoft Dynamics 365 Human Resources és Finance and Operations alkalmazások infrastruktúra-egyesítésével kapcsolatos gyakori kérdéseket válaszolja meg.
author: rachel-profitt
ms.date: 07/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fee4fea9b67ff8a0c8d813940a65cf882bd13abe
ms.sourcegitcommit: bf2daeccbe3f2826e734f409bfc823820144aa23
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/15/2021
ms.locfileid: "6617991"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-faq"></a>Dynamics 365 Human Resources infrastruktúraegyesítés – GYIK

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a témakör a Microsoft Dynamics 365 Human Resources és Finance and Operations alkalmazások infrastruktúra-egyesítésével kapcsolatos gyakori kérdéseket válaszolja meg.

## <a name="what-is-the-dynamics-365-human-resources-infrastructure-merge"></a>Mit jelent a Dynamics 365 Human Resources egyesítés?

A Dynamics 365 Human Resources olyan önálló alkalmazás, amely más infrastruktúrát használ, mint a többi Finance and Operations alkalmazás, például a Dynamics 365 Finance, a Dynamics 365 Supply Chain Management, Dynamics 365 Commerce és a Dynamics 365 Project Operations. Az infrastruktúra-egyesítés ugyanabba az infrastruktúrába helyezi a Dynamics 365 Human Resources alkalmazást, mint többi Finance and Operations alkalmazás.

## <a name="value-and-benefits-of-the-infrastructure-merge"></a>Az infrastruktúra-egyesítés értékei és előnyei

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-what-benefits-will-we-see-from-these-changes"></a>A szervezetem a Dynamics 365 Human Resources alkalmazást használja a HR műveleteinek kezelésére. Milyen előnyöket kaphatunk a változtatásokból?

- Ezek a változtatások eltávolítanak több emberi erőforrás (HR) többféle képességet a Dynamics 365-ből.
- Ezek nyújtják a Microsoft Power Platform bővíthetőségét és lehetőséget nyújtanak az üzleti logika és a funkciók kiterjesztésére.
- Konzisztenciát biztosítanak a Dynamics 365 Human Resources és más Finance and Operations alkalmazások között az Alkalmazások életciklus-kezelése (ALM), Microsoft Dynamics. Lifecycle Services (LCS), földrajzi elérhetőség, bővíthetőség stb. terén.
- lehetővé teszik megosztott szolgáltatások és eszközkészletek használatát és hozzájárulnak a költségek csökkentéséhez.

### <a name="my-organization-uses-dynamics-365-human-resources-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-benefits-will-we-see-from-these-changes"></a>A szervezetem a Dynamics 365 Human Resources alkalmazást a Dynamics 365 Finance, Supply Chain Management, Commerce vagy Project Operations alkalmazásban használja. Milyen előnyöket kaphatunk a változtatásokból?

A Dynamics 365 Human Resources alkalmazásban már megtalálható képességek és beruházások elérhetővé válnak azok a vevők számára, akik a HR modult használják a Dynamics 365 Finance alkalmazásban. Ilyen képeségek többek között a szabadság- és távollétkezelés, a juttatások kezelése és a feladatkezelés.

### <a name="will-i-lose-any-features-or-capabilities-that-i-currently-use"></a>Elvesznek általam jelenleg használt funkciók és funkciók?

Az Dynamics 365 Human Resources és a Finance and Operations HR modulja között funkcionális paritás lesz. Dynamics 365 Human Resources élvez előnyt a funkciók terén. További tájékoztatás: [Funkciókezelés – áttekintés](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="will-the-experience-change-for-my-users"></a>Megváltozik az élmény a felhasználóim számára?

Az új HR-funkciók a Funkciókezelés segítségével lesznek kezelhetők. Az ügyfelek dönthetik el, hogy szeretnék-e használni ezeket. Bizonyos esetekben a képességek módosulhatnak. Ilyen esetben a dokumentáció is rendelkezésre áll majd.

### <a name="how-does-this-change-affect-me-if-i-am-an-existing-customer-and-i-use-both-the-hr-module-on-the-finance-and-operations-infrastructure-and-dynamics-365-human-resources-through-custom-integrations"></a>Hogyan érint engem az a változás, ha már felhasználó vagyok, és használom a HR-modult a Finance and Operations infrastruktúrában és a Dynamics 365 Human Resources alkalmazást integrációkon keresztül?

A továbbiakban nem szükséges egyéni integráció a Dynamics 365 Human Resources és a Dynamics 365 Finance HR-modulja között. Minden HR-adat ugyanabban az adatbázisban lesz, mint a többi Finance and Operations alkalmazás adatai.

## <a name="migration-from-dynamics-365-human-resources-to-finance-and-operations-apps"></a>Áttelepítés a Dynamics 365 Human Resources alkalmazásból a Finance and Operations alkalmazásokba

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-hr-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>A szervezetem a Dynamics 365 Human Resources alkalmazást használja a HR műveleteinek kezelésére. Mit kell megterveznünk az új élményre való áttelepítéshez?

Ha a szervezet más Dynamics 365 Human Resources alkalmazásokat használ, de nem használ semmilyen más Finance and Operations alkalmazásokat, a Human Resources környezet áttelepítve lesz az új infrastruktúrába. Az áttelepítési folyamat nagy része automatizálva lesz. Az adatbázis áttelepítéséhez és az új infrastruktúrával való szinkronizálásához folyamatok lesznek bevetve.

Ezenkívül a termelési környezet áttelepítése előtt rendelkezésre állnak majd eszközök eszközöknek, hogy tesztelni és ellenőrizni tudja az adatokat és az elményt mielőtt áttelepíteni a termelési környezetét.

Ha a szervezet egyszerre Dynamics 365 Human Resources alkalmazást és más Finance and Operations alkalmazásokat is használ, akkor több időt kell tervezni az ellenőrzésre, hogy az adatok megfelelően át legyenek telepítve az új környezetbe. Az új infrastruktúrára való áttelepítés során a rendszer a Human Resources környezetben lévő adatokat egyesíteni foguk a Finance and Operations környezettel. Az eszköz a lehető legnagyobb mértékben automatizálja az adategyesítési folyamatot. Az ütköző adatok esetében azonban felhasználói adatbevitel szükséges az ütközés megoldási módjának meghatározásához. A felhasználóknak és a rendszergazdáknak kezelniük kell az adatleképezéseket, ahol ütközések vannak, és tesztelni kell az áttelepítést tesztkörnyezetben a termelési környezet áttelepítése előtt.

### <a name="my-organization-uses-dynamics-365-human-resources-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>A szervezetem a Dynamics 365 Human Resources alkalmazást a Dynamics 365 Finance, Supply Chain Management, Commerce vagy Project Operations alkalmazásban használja. Mit kell megterveznünk az új élményre való áttelepítéshez?

A Finance and Operations alkalmazásokban a HR modult használó szervezeteknél az új funkció a Dynamics 365 Human Resources alkalmazásból a szokásos "Egyverziós" frissítési folyamaton keresztül lesznek alkalmazva a környezetére. Látni fogja majd az új funkciókat a környezetében, ahogy elérhetővé válnak az egyes frissítések során. A Szolgáltatáskezelés használatával kapcsolhatja be az új funkciókat. Azonban a funkciók érvényességét ellenőrizni kell. Kövesse azokat a folyamatokat, amelyel már rendelkezésre állnak környezetében a más frissítések ellenőrzésére. A frissítések a Finance and Operations alkalmazásokra való alkalmazásának kapcsolatosan lásd: [Egyverziós frissítés áttekintése](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="when-will-my-organization-be-migrated"></a>Mikor történik meg a saját szervezetem áttelepítése?

Az egyes szervezetek áttelepítése a konfigurációtól és az új infrastruktúrára való áttelepítésre való alkalmasságtól függ. Ezek a dátumok változhatnak.

- Azok a szervezetek, amelyek jelenleg a Finance and Operations alkalmazásokban használják az HR modult, a szokásos Egyverziós frissítési folyamat részeként megkapják a HR-funkciókat a Dynamics 365 Human Resources alkalmazáshoz. Az új funkciók a tervek szerint 2021 októberében válnak általánosan elérhetővé.
- Azok a szervezetek, amelyek jelenleg csak a Dynamics 365 Human Resources alkalmazást használják hozzáférnek az áttelepítési eszközhöz, hogy megkezdjék a tesztelést és elindíthassák az áttelepítést 2022 elején-közepén. Még nem határoztuk meg azt a dátumot, amikorra az új infrastruktúrára való átállást végre kell hajtani. Az áttelepítési eszköz elérhetővé válását követően legalább egy évet biztosítunk erre.
- Azok a szervezetek, amelyek jelenleg a Dynamics 365 Human Resources alkalmazást és más Finance and Operations alkalmazásokat is használnak hozzáférnek az áttelepítési eszközhöz, hogy megkezdjék a tesztelést és elindíthassák az áttelepítést 2022 végén. Még nem határoztuk meg azt a dátumot, amikorra az új infrastruktúrára való átállást végre kell hajtani. Az áttelepítési eszköz elérhetővé válását követően legalább egy évet biztosítunk erre.

A Dynamics 365 Human Resources új funkcióival kapcsolatos további tudnivalókat lásd a [Human Resources újdonságai és módosításai](./hr-admin-whats-new.md) részben.

### <a name="i-am-using-new-capabilities-that-are-available-only-in-dynamics-365-human-resources-such-as-leave-and-absence-and-benefits-management-will-these-capabilities-now-be-available-in-the-human-resources-module-on-the-finance-and-operations-infrastructure-too"></a>Olyan új funkciókat használok, amelyek csak a Dynamics 365 Human Resources alkalmazásban érhetők el (például **Szabadság és távolét** és **Juttatások kezelése**). Ezek a képességek elérhetők lesznek a Human Resources modulban a Finance and Operations infrastruktúrában is?

Igen, a Dynamics 365 Human Resources minden modulja ugyanúgy működik majd a Finance and Operations alkalmazásokban, és 100 százalékos funkcióparitás lesz. Az ezeket a HR képességeket használó ügyfelek számára az áttelepítési stratégia részeként az ügyféladatok át lesznek telepítve, hogy továbbra is biztosítva legyen a működés a Finance and Operations infrastruktúrájában is.

### <a name="i-use-the-new-dynamics-365-human-resources-benefits-management-capabilities-ive-built-custom-integrations-with-the-hr-module-on-the-finance-and-operations-infrastructure-so-that-i-can-take-advantage-of-the-payroll-capabilities-by-using-benefits-data-will-these-custom-integrations-be-required-going-forward"></a>A Dynamics 365 Human Resources új juttatáskezelési képességeit használom. Egyéni integrációkat építtem fel a HR modullal a Finance and Operations infrastruktúrában, így a juttatásadatok segítségével kihasználhatom a bérszámfejtési lehetőségeket. Ezt követően szüksége lesz ezekre az egyéni integrációkra?

Az infrastruktúra-egyesítés részeként a HR-adatok ugyanannak az adatbázisnak a részei lesznek, mint a többi Finance and Operations alkalmazás adatai. A Finance and Operations alkalmazások moduljai közötti integrációra már nem lesz szükség.

### <a name="my-organization-uses-one-or-more-isv-solutions-with-dynamics-365-human-resources-will-our-isv-solutions-be-migrated-automatically"></a>A szervezetem egy vagy több ISV-megoldást használ a Dynamics 365 Human Resources alkalmazással. A saját ISV-megoldásaink automatikusan át lesznek telepítve?

A független szoftverszállítói (ISV) megoldásoknál az áttelepítési élmény a megoldás integrációs módszerétől függően eltérő lehet. A Microsoft szorosan együttműködik az ISV-kkel, így biztosítja az új infrastruktúrára való zökkenőmentes átállást.

### <a name="my-organization-uses-linkedin-talent-hub-integration-with-dynamics-365-human-resources-will-this-integration-continue-to-work-after-the-infrastructure-change-is-completed"></a>A szervezem a LinkedIn Talent Hub integrációját használja a Dynamics 365 Human Resources alkalmazással. Továbbra is működik majd ez az integráció az infrastruktúra-módosítás befejezése után?

Igen, a LinkedIn Talent Hub integráció az új infrastruktúrára való áttelepítés után is működni fog.

### <a name="my-organization-uses-the-human-resources-app-for-teams-will-the-app-continue-to-work-after-the-infrastructure-change-is-completed"></a>Saját szervezetem a Human Resources alkalmazást használja a Teamshez. Továbbra is működik majd ez az alkalmazás az infrastruktúra-módosítás befejezése után?

Igen a Teamshez készült Human Resources alkalmazás az új infrastruktúrára való áttelepítés után is működni fog.

### <a name="my-organization-has-configured-custom-security-in-dynamics-365-human-resources-will-our-custom-security-still-be-applied-after-the-infrastructure-change-is-completed"></a>Szervezetem egyéni biztonsági beállításokat konfigurált a Dynamics 365 Human Resources alkalmazásban: Az infrastruktúra-változás befejezése után is alkalmazva lesznek az egyéni biztonsági megoldásaink?

Igen, az új infrastruktúrába való adatáttelepítésben is szerepelni fognak az egyéni biztonsági konfigurációk.

### <a name="we-are-using-data-integrator-to-move-data-between-dynamics-365-human-resources-and-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected"></a>Adatintegrátort használunk az adatok mozgatására a Dynamics 365 Human Resources és a Finance and Operations alkalmazások között. Hogyan lesz ez hatással éppen integrált adatokra?

A Dynamics 365 Human Resources alkalmazásban mesteradatként kezelt HR-adatok a Dataverse-rendszerrel vannak szinkronizálva. Ezután az adatintegrátor egyirányú szinkronizálásra használható a Finance and Operations alkalmazásokkal. Az új infrastruktúrába való áttelepítés után a HR-adatok natívak lesznek a Finance and Operations alkalmazásokban. Az adatintegrátorra már nem lesz szükség a Finance and Operations alkalmazások és a Human Resources közötti adatszinkronizáláshoz.

A Human Resources aktuális Dataverse natív adattáblái továbbra is szinkronizálni fogják az új infrastruktúra alatt a környezet adatait. Az entitások kétírásos formátum támogatásához lesznek konvertálva. A többi Dynamics 365 alkalmazások az Adatintegrátor segítségével konfigurált egyéb adatintegrációi a jelenleg konfigurált módon folytatódnak.

### <a name="we-are-using-dual-write-to-move-hr-data-between-dataverse-and-other-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected-by-the-migration-to-the-new-infrastructure"></a>A HR-adatok mozgatásár a Dataverse és más Finance and Operations alkalmazások között kettős írással végezzük majd. Hogyan lesz hatással az jelenleg integrált adatokra az új infrastruktúrára való áttelepítés?

Az új infrastruktúra környezetében a HR-adatok natívak lesznek a Finance and Operations alkalmazásokhoz. Ezt követően a kettős írás segítségével lehet mozgatni a HR-adatokat az új környezet és a Dataverse-környezet között.

### <a name="we-have-built-custom-integrations-from-dynamics-365-human-resources-to-one-or-more-external-systems-will-we-have-to-develop-new-integrations-after-the-infrastructure-change-is-completed"></a>Egyéni integrációt építünk fel egy Dynamics 365 Human Resources felől egy vagy több külső rendszerbe. Új integrációkat kell majd fejlesztenünk infrastruktúra-módosítás befejezése után?

Ez az integrációs végponttól függ. A Finance and Operations alkalmazásokban elérhető integrációs technológiákkal és a legjobb integrációs technológia választásával kapcsolatos további tudnivalókat lásd az [Integrációk áttekintése](../fin-ops-core/dev-itpro/data-entities/integration-overview.md) című témakörben.

### <a name="we-have-extended-dataverse-for-dynamics-365-human-resources-will-these-extensions-be-migrated-automatically"></a>Bővítettük a Dataverse-t a Dynamics 365 Human Resources alkalmazáshoz. Ezek a bővítések automatikusan át lesznek telepítve?

Ha a Dynamics 365 Human Resources és a Finance and Operations környezetek, amelyek össze lesznek kapcsolva az új környezetben az új infrastruktúrában ugyanahhoz a Dataverse-környezethez kapcsolódnak, a két alkalmazás továbbra is ugyanabban a Dataverse-környezetben lesz az áttelepítés után. A Dataverse-bővítmények áttelepítése ennek megfelelően nem szükséges.

Ugyanakkor, ha a Dynamics 365 Human Resources és a Finance and Operations környezetek jelenleg külön Dataverse-környezetekhez vannak kapcsolva, a két Dataverse-környezet egyesítése lesz szükséges, hogy egy környezethez kapcsolódjanak az új infrastruktúrában. A Dataverse áttelepítés során a Human Resources estében szabványos Dataverse táblákat lehet csatlakoztatni és újraszinkronizálni az új Dataverse környezethez. A Dataverse környezet bővítései azonban nem lesznek automatikusan áttelepítve, hanem újra kell azokat telepíteni az új környezetben. Javasoljuk, hogy a felügyelt megoldások segítségével kezelje a Dataverse-bővítményeket. A további tudnivalókat lásd: [Bevezetés a megoldásokba](https://docs.microsoft.com/powerapps/developer/data-platform/introduction-solutions).

### <a name="we-have-configured-microsoft-power-automate-flows-andor-microsoft-power-apps-to-work-with-dynamics-365-human-resources-will-these-microsoft-power-platform-components-be-migrated-and-work-automatically-after-the-infrastructure-change-is-completed"></a>Úgy konfiguráltuk a Microsoft Power Automate folyamatokra és/vagy Microsoft Power Apps alkalmazásokat, hogy működjenek Dynamics 365 Human Resources alkalmazással. Ezeket a Microsoft Power Platform összetevőket áttelepíti a program, és automatikusan működnek az infrastruktúra-módosítás befejezése után?

A Power Apps és Power Automate folyamatok és egyéb Microsoft Power Platform testreszabások hasonlóak a Dataverse bővítményekhez. Az, hogy automatikusan működnek-e az új infrastruktúrára való áttelepítés után, attól függ, hogy a Human Resources alkalmazás és a Finance and Operations alkalmazások az áttelepítés előtt ugyanahhoz a Power Apps környezethez kapcsolódnak-e.

Ha az alkalmazások jelenleg ugyanahhoz a Power Apps környezethez vannak csatlakoztatva, akkor az új infrastruktúrára való áttelepítés után is csatlakoznak ugyanahhoz a Power Apps-környezethez. Ebben az esetben a Power Apps és Power Automate folyamatok és egyéb Microsoft Power Platform testreszabások további konfiguráció nélkül is működnek. Javasoljuk, hogy a felügyelt megoldások segítségével kezelje az alkalmazásbővítményeket a Dataverse alatt. A további tudnivalókat lásd: [Bevezetés a megoldásokba](https://docs.microsoft.com/powerapps/developer/data-platform/introduction-solutions).

Ha azonban a Human Resources alkalmazás és a Finance and Operations alkalmazások külön Power Apps környezetekhez vannak kapcsolva, akkor az áttelepítés részeként kombinálni kell ezeket. Ehhez a feladathoz az szükséges, hogy az új környezetben újra legyen telepítve az összes Power Apps és más testreszabások.

### <a name="we-have-enabled-dataverse-virtual-tables-for-dynamics-365-human-resources-what-will-happen-to-these-tables-during-the-migration"></a>Engedélyeztük a Dataverse virtuális táblákat a Dynamics 365 Human Resources alkalmazáshoz. Mi történjen ezekkel a táblákkal az áttelepítés során?

Az áttelepítés után, ha az új infrastruktúra környezete továbbra is csatlakozik a jelenleg csatlakoztatott Dataverse-környezethez, amely kapcsolódik a Dynamics 365 Human Resources alkalmazáshoz, az ebben a környezetben létrehozott Dataverse virtuális táblák további konfiguráció nélkül is működni fognak.

Ha azonban az új infrastruktúra környezete az áttelepítés után másik Dataverse környezethez csatlakozik, akkor az új Dataverse-környezetben újra létre kell hozni a virtuális táblákat.

### <a name="we-have-developed-an-integration-by-using-the-applicant-tracking-system-ats-api-payroll-api-dataverse-virtual-tables-for-dynamics-365-human-resources-or-other-entities-in-the-dataverse-web-api-will-these-integrations-continue-to-work-after-the-infrastructure-change-is-completed"></a>Létrehoztunk egy integrációt az Applicant Tracking System (ATS) API, Payroll API, Dataverse virtuális táblák használatával a Dynamics 365 Human Resources alkalmazáshoz, vagy más entitásokhoz a Dataverse Web API-ban. Továbbra is működnek majd ezek az integrációk az infrastruktúra-módosítás befejezése után?

Az áttelepítés után, ha az új infrastruktúra környezete továbbra is csatlakozik a jelenleg csatlakoztatott Dataverse-környezethez, amely kapcsolódik a Dynamics 365 Human Resources alkalmazáshoz, minden a Dataverse webes API-hoz létrehozott integráció továbbra is működik az áttelepítés befejezés után is.

Ugyanakkor, ha a környezet egy az új infrastruktúrán egy másik Dataverse-környezethez kapcsolódik az áttelepítés után, a Dataverse webes API-hoz kifejlesztett integrációkat újra kell majd konfigurálni, hogy az új Dataverse-környezethez kapcsolódjanak.

### <a name="is-there-an-impact-on-the-azure-region-when-my-environment-is-migrated"></a>Befolyásolja az Azure-régiót, amikor a környezetem át lesz telepítve?

A Human Resources környezete jellemzően ugyanabban az Azure-régióban marad az áttelepítés során. Az egyetlen kivétel akkor fordul elő, ha a Human Resources egyesíte lesz egy Finance and Operations környezettel, amely másik régióban található. Ebben az esetben a Human Resources környezet át lesz telepítve a Finance and Operations környezet Azure-régiójába.

### <a name="my-organization-depends-on-workflows-in-dynamics-365-human-resources-for-one-or-more-business-processes-will-the-workflows-be-migrated-automatically"></a>A saját szervezet egy vagy több üzleti folyamata Dynamics 365 Human Resources munkafolyamataitól függ. Ezek a munkafolyamatok automatikusan át lesznek telepítve?

Igen, a munkafolyamat-konfigurációk, a munkafolyamat-előzmények és az aktuális folyamatban lévő munkafolyamatok áttelepítésre kerülnek.

### <a name="what-training-and-resources-will-be-available-to-help-with-the-migration-process"></a>Milyen képzések és erőforrások lesznek elérhetők az áttelepítési folyamathoz?

Teljes dokumentációt biztosítunk, hogy részletesen leírjuk az áttelepítési folyamat mindegyik lépését. Szükség esetén további képzési erőforrások, például videók és workshopok is rendelkezésre állnak.

### <a name="my-organization-has-created-saved-views-in-dynamics-365-human-resources-to-improve-the-usability-of-the-interface-will-the-saved-views-be-migrated-automatically"></a>A szervezetem létrehozott mentett nézeteket Dynamics 365 Human Resources alkalmazásban a felület használhatóságának javítása érdekében. A mentett nézetek automatikusan át lesznek telepítve?

Igen, a mentett nézetek át lesznek telepítve az új infrastruktúrába.

### <a name="we-are-using-ceridian-with-dynamics-365-human-resources-will-the-ceridian-integration-be-available-after-the-infrastructure-change-is-completed"></a>A Ceridiant használjuk a Dynamics 365 Human Resources alkalmazással. A Ceridian integráció infrastruktúra-módosítás befejezése után is elérhető lesz? 

A Ceridian rendszer integrációja át lesz telepítve a Bérlista API-on alapuló integrációba. A fájl alapú integrációt, amely jelenleg létezik a Dynamics 365 Human Resources alkalmazásba, nem lesz áttelepítve a Finance and Operations infrastruktúrába. A további tudnivalókat lásd: [Bérszámfejtés API bevezetés](./hr-admin-integration-payroll-api-introduction.md).

### <a name="how-will-the-migration-affect-the-service-update-process"></a>Hogyan fogja befolyásolni az áttelepítés a szolgáltatásfrissítés folyamatát?

Az áttelepítés után a vevők nagyobb rugalmasságot fognak kapni az ALM és a szolgáltatásfrissítések szempontjából. A szolgáltatásfrissítések már nem lesznek automatikusan alkalmazva a Human Resources környezetekre. Ehelyett a szolgáltatás az Egyverziós szolgáltatásfrissítések folyamatait és funkcionalitását követi. Ennek megfelelően a frissítések konfigurációs beállításai az LCS-n keresztül lesznek elérhetők. További információ: [Egyetlen verzió áttekintése](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="how-will-the-migration-affect-my-lcs-project-for-dynamics-365-human-resources"></a>Hogyan lesz hatással az áttelepítés a saját Dynamics 365 Human Resources LCS-projektjeimre?

Az új infrastruktúra áttelepítése a Dynamics 365 Human Resources környezetek kezelését egy LCS-megvalósítási projektbe fogja áthelyezni. Ha az áttelepítéssel a Dynamics 365 Human Resources környezetet egy meglévő Finance and Operations környezettel egyesíti, a Human Resources LCS-projekt egyesítve lesz egy LCS implementációs projektbe a Finance and Operations alkalmazáshoz. Ha jelenleg csak a Dynamics 365 Human Resources alkalmazást használja, a rendszer létrehoz egy új LCS implementálási projektet, és a meglévő Human Resources LCS-projektet áttelepíti az új projektbe.

Az új projekt a Finance and Operations alkalmazások által használttal megegyező típusú lesz. A környezetkezelésben ugyanazok a funkciók és funkciók lesznek elérhetők. További tudnivalókért lásd: [Lifecycle Services-erőforrások](../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

### <a name="we-have-linked-our-task-recordings-to-the-business-process-modeler-in-human-resources-how-will-the-business-process-modeler-be-migrated-and-merged-into-lcs"></a>Feladatrögzítések kapcsolva vannak az Üzletifolyamat-modellezőhöz a Human Resources alkalmazásban. Hogyan történik az Üzletifolyamat-modellező áttelepítése és egyesítése az LCS-felületre?

Az LCS-projekt üzletifolyamat-könyvtárait áttelepíti a rendszer az új LCS-projektbe a Human Resources számára.

### <a name="my-organization-currently-uses-only-dynamics-365-human-resources-what-resources-are-available-so-that-we-can-learn-more-about-the-development-capabilities-after-the-infrastructure-change-is-completed"></a>A szervezetem jelenleg csak a Dynamics 365 Human Resources alkalmazást használja. Milyen erőforrások állnak rendelkezésre, hogy az infrastruktúra-változás befejezése után többet tudjunk meg a fejlesztési lehetőségekről?

Mind a Microsoft Power Platform bővítési lehetőségek, mind a Finance and Operations bővítési lehetőségek elérhetők, és fejlesztésre használhatók. A további tudnivalókat lásd a [Kezdőlap kialakítása és testreszabása](../fin-ops-core/dev-itpro/dev-tools/developer-home-page.md) részben.

### <a name="we-have-enabled-features-in-dynamics-365-human-resources-will-these-features-be-enabled-automatically-during-the-migration"></a>Engedélyeztünk funkciókat a Dynamics 365 Human Resources alkalmazásban. Automatikusan engedélyezve lesznek ezek a szolgáltatások az áttelepítés során?

Azt, hogy az új infrastruktúra szolgáltatását automatikusan engedélyezzük-e, minden egyes szolgáltatás esetében külön lesz meghatározva. Ez az információ szerepelni fog a funkció dokumentációjában.

### <a name="what-happens-to-my-byod-database-during-the-migration"></a>Mi történik a BYOD-adatbázisommal az áttelepítés során?

A saját adatbázis bevonása (BYOD) konfigurációjának importálása és exportálása az új infrastruktúrába lesz áttelepítve.

### <a name="what-happens-to-my-azure-data-lake-during-the-migration"></a>Mi történik az Azure Data Lake adattavammal az áttelepítés során?

Minden, az Azure Data Lake Storage és Finance and Operations alkalmazásokhoz konfigurált exportálás az áttelepítés után megtartja ugyanazt a konfigurációt.

### <a name="we-are-currently-using-dynamics-ax-2012-will-the-upgrade-tools-that-are-currently-available-be-used-to-upgrade-the-hr-module-in-ax-2012-to-dynamics-365-human-resources"></a>Jelenleg a Dynamics AX 2012-t használjuk. Az AX 2012 – Dynamics 365 Human Resources HR moduljának frissítéséhez aktuálisan elérhető frissítési eszközök elérhetők lesznek?

Igen. A Dynamics 365 Human Resources egyesített kódleíró és az infrastruktúra része lesz a Finance and Operations alkalmazások számára. A Dynamics AX 2012 verzióról a Dynamics 365 Human Resources alkalmazásra való frissítés ugyanazt a frissítési útvonalat és eszközt fogja használni, amely a Finance and Operations alkalmazások legújabb verziójára való frissítéshez használatos.

### <a name="we-use-document-handling-with-dynamics-365-human-resources-what-will-happen-to-the-documents-during-the-migration"></a>Dokumentumkezelést használunk a Dynamics 365 Human Resources alkalmazással. Mi történik ezekkel a dokumentumokkal az áttelepítés során?

A dokumentumok megmaradnak a meglévő dokumentumtárolóban. Újra hozzárendeli őket a rendszer az új infrastruktúra környezetéhez.

### <a name="what-happens-to-the-batch-jobs-that-we-have-configured-in-dynamics-365-human-resources-after-the-migration"></a>Mi történik a Dynamics 365 Human Resources alkalmazásban konfigurált kötegelt feladatokkal az áttelepítés után ?

Az érintett kötegelt feladatok automatikusan át lesznek telepítve az új infrastruktúrába.

## <a name="licensing-impact"></a>Licencelési hatás

Ez a dokumentáció nem helyettesíti és nem cseréli le a használatra vonatkozó jogokat tartalmazó jogi dokumentációkat.

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-does-our-licensing-or-cost-change"></a>A szervezetem a Dynamics 365 Human Resources alkalmazást használja a HR műveleteinek kezelésére. A licencelés vagy a költség változik?

Ez a változás nem érinti a vevőket, akik Dynamics 365 Human Resources licenceket vásároltak. Ezeknek a vevőknek nincs licencáttelepítés. A kiegészítő tesztverziós termékváltozat (SKU), amely kifejezetten a Human Resources alkalmazáshoz volt specifikus a továbbiakban nem lesz érvényes. Ehelyett az ügyfelek választhatják, hogy egy 2. szintű tesztkörnyezetet vásárolnak a Finance and Operations alkalmazásokhoz, némileg alacsonyabb költséggel. A meglévő ügyfelek, akik a Human Resources tesztkörnyezetet megvásárolták további költség nélkül át lesznek a telepítve a Finance and Operations alkalmazások 2. szintű tesztkörnyezetébe.

### <a name="my-organization-uses-dynamics-365-human-resources-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-does-my-licensing-or-cost-change"></a>A szervezetem a Dynamics 365 Human Resources alkalmazást a Dynamics 365 Finance, Supply Chain Management, Commerce vagy Project Operations alkalmazásban használja. A licencelés vagy a költség változik?

A Dynamics 365-alkalmazások meglévő felhasználói és az önálló Dynamics 365 Finance, Supply Chain Management, Commerce, és Project Operations felhasználók a licencek részeként 2025 februárig, illetve a jelenlegi licencszerződés lejártáig (amelyik előbb bekövetkezik) hozzáférhetnek a Human Resources alkalmazáshoz. Dönthet úgy, hogy korábban áttér a Human Resources licencekre, ha az segítséget jelent Önnek, vagy így költségeket takaríthat meg. 2025 februártól kezdve minden meglévő CSP- és EA-vevőnek ki kell vezetnie a HR-modult, és meg kell vásárolnia a Human Resources licenceket, hogy kihasználják a Finance and Operations alkalmazásokba kerülő új funkciókat.

### <a name="my-organization-is-live-with-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-will-we-be-required-to-purchase-an-additional-environment-to-support-the-infrastructure-merge"></a>A szervezetem a Dynamics 365 Finance, Supply Chain Management, Commerce vagy Project Operations alkalmazást használja. Meg kell majd vásárolni egy további környezetet az infrastruktúra-egyesítés támogatása érdekében?

Nincs szükség további környezetekre az infrastruktúra-változás támogatásához.

### <a name="where-should-i-go-if-i-have-additional-questions-about-product-licensing"></a>Hova fordulhatok, ha további kérdéseim vannak a terméklicenceléssel kapcsolatosan?

Ha licencelési kérdései vannak, további információkat talál a [Biz Apps Hub – D365 árképzés és licencelés](https://businessapplications.transform.microsoft.com/resources/pricing-and-licensing?tab=grandfathering) részben. Ha az ott talált információk nem segítenek a probléma megoldásában, nyisson meg egy kérést a LicenseQ segítségével.
