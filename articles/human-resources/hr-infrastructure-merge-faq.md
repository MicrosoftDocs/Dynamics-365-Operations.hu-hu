---
title: Dynamics 365 Human Resources infrastruktúraegyesítés – GYIK
description: Ez a témakör megválaszolja a Microsoft, a Pénzügy Dynamics 365 Human Resources és a Műveletalkalmazások infrastruktúra-egyesítésével kapcsolatos gyakori kérdéseket.
author: twheeloc
ms.date: 08/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a905d752af2cf8397acb4927aa99edb4c23bfa6a
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688120"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-faq"></a>Dynamics 365 Human Resources infrastruktúraegyesítés – GYIK

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Ez a témakör megválaszolja a Microsoft, a Pénzügy Dynamics 365 Human Resources és a Műveletalkalmazások infrastruktúra-egyesítésével kapcsolatos gyakori kérdéseket.

## <a name="what-is-the-dynamics-365-human-resources-infrastructure-merge"></a>Mit jelent a Dynamics 365 Human Resources egyesítés?

Dynamics 365 Human Resources A <a0/<a2/<a2/5><a2/5><a2/<a2/<a2/<a3/<a3/–<a3/<a3/ olyan alkalmazás, Dynamics 365 Supply Chain Management Dynamics 365 Commerce amely nem ugyanazt az infrastruktúrát használja,Dynamics 365 Project Operations Az infrastruktúra-egyesítés ugyanazon Dynamics 365 Human Resources infrastruktúra-egyesítést fogja lehetővé venni, mint a többi Pénzügyi és Üzemeltetési alkalmazás.

## <a name="value-and-benefits-of-the-infrastructure-merge"></a>Az infrastruktúra-egyesítés értékei és előnyei

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-what-benefits-will-we-see-from-these-changes"></a>A szervezetem a Dynamics 365 Human Resources alkalmazást használja a HR műveleteinek kezelésére. Milyen előnyöket kaphatunk a változtatásokból?

- Ezek a változások megszüntetik a Dynamics 365-ben a humánerőforrás (HR) képességek többféle készlete okozta zavart.
- Ezek nyújtják a Microsoft Power Platform bővíthetőségét és lehetőséget nyújtanak az üzleti logika és a funkciók kiterjesztésére.
- Az alkalmazás életciklusának Dynamics 365 Human Resources kezelése, a Lifecycle Services (LCS), Microsoft Dynamics a földrajzi elérhetőség, a kiterjeszthetőség stb. szempontjából egységességet hoznak a pénzügyek és a műveletek alkalmazásai között.
- lehetővé teszik megosztott szolgáltatások és eszközkészletek használatát és hozzájárulnak a költségek csökkentéséhez.

### <a name="my-organization-uses-the-human-resources-module-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-benefits-will-we-see-from-these-changes"></a>Egy szervezet a Dynamics 365 Pénzügy, Az Ellátásilánc-kezelés, a Commerce és a Projektművelet modul emberi erőforrások modulját használja. Milyen előnyöket kaphatunk a változtatásokból?

A benne található Dynamics 365 Human Resources képességek és beruházások elérhetővé lesznek azok a vevők számára, akik a Dynamics 365 Pénzügy modult használják a HR modulban. Ilyen képeségek többek között a szabadság- és távollétkezelés, a juttatások kezelése és a feladatkezelés.

### <a name="will-i-lose-any-features-or-capabilities-that-i-currently-use"></a>Elvesznek általam jelenleg használt funkciók és funkciók?

A Pénzügy és műveletek alkalmazásokban funkcionális paritás lesz a Dynamics 365 Human Resources HR-modul és a között. Dynamics 365 Human Resources élvez előnyt a funkciók terén. További tájékoztatás: [Funkciókezelés – áttekintés](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="will-the-experience-change-for-my-users"></a>Megváltozik az élmény a felhasználóim számára?

Az új HR-funkciók a Funkciókezelés segítségével lesznek kezelhetők. Az ügyfelek dönthetik el, hogy szeretnék-e használni ezeket. Bizonyos esetekben a képességek módosulhatnak. Ilyen esetben a dokumentáció is rendelkezésre áll majd.

### <a name="how-does-this-change-affect-me-if-i-am-an-existing-customer-and-i-use-both-the-hr-module-on-the-finance-and-operations-infrastructure-and-dynamics-365-human-resources-through-custom-integrations"></a>Hogyan befolyásolja ez a módosítás a meglévő vevőt, és mind a pénzügyi, mind a műveleti infrastruktúra HR Dynamics 365 Human Resources modulját, mind az egyéni integráción keresztül használom?

A Dynamics Dynamics 365 Human Resources 365 Pénzügy modulban már nem szükséges egyéni integráció a HR-modul és az között. Minden HR-adat ugyanabban az adatbázisban fog találhatók, mint a többi Pénzügy és Művelet alkalmazás.

## <a name="migration-from-dynamics-365-human-resources-to-finance-and-operations-apps"></a>Áttelepítés a Pénzügy Dynamics 365 Human Resources és a Műveletek alkalmazásba

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-hr-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>A szervezetem a Dynamics 365 Human Resources alkalmazást használja a HR műveleteinek kezelésére. Mit kell megterveznünk az új élményre való áttelepítéshez?

Ha a szervezet más Dynamics 365 Human Resources Pénzügyi és Üzemeltetési alkalmazásokat használ, de nem használ, az emberi erőforrások környezete áttelepíti az új infrastruktúrába. Az áttelepítési folyamat nagy része automatizálva lesz. Az adatbázis áttelepítéséhez és az új infrastruktúrával való szinkronizálásához folyamatok lesznek bevetve.

Ezenkívül a termelési környezet áttelepítése előtt rendelkezésre állnak majd eszközök eszközöknek, hogy tesztelni és ellenőrizni tudja az adatokat és az elményt mielőtt áttelepíteni a termelési környezetét.

Ha a szervezet mind Dynamics 365 Human Resources a Pénzügy, mind a Műveletek alkalmazást használja, az ellenőrzéshez több időt kell tervezni, hogy az adatok megfelelően áttelepítve legyen az új környezetbe. Az új infrastruktúrára való áttelepítés során a rendszer egyesíteni fogja az Emberi erőforrások környezetben lévő adatokat a pénzügyi és műveleti környezettel. Az ellentmondó adatokhoz a felhasználónak kell megadnia, hogyan kell feloldani az ellentmondást. A felhasználóknak és a rendszergazdáknak kell kezelniük az adatleképezéseket, ahol konfliktusok vannak, és tesztelniük kell a migrációt a tesztkörnyezetekben a termelési környezetek migrációja előtt.

### <a name="my-organization-uses-the-human-resources-module-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>Egy szervezet a Dynamics 365 Pénzügy, Az Ellátásilánc-kezelés, a Commerce és a Projektművelet modul emberi erőforrások modulját használja. Mit kell megterveznünk az új élményre való áttelepítéshez?

A Pénzügy és műveletek alkalmazások HR modulját használó szervezetek számára az új funkciófunkciókat a normál Egyverziós Dynamics 365 Human Resources frissítési folyamat fogja alkalmazni a környezetére. Látni fogja majd az új funkciókat a környezetében, ahogy elérhetővé válnak az egyes frissítések során. Az új funkciók bekapcsolásához használhatja a funkciókezelést, azonban terveznie kell, hogy ezeket a funkciókat érvényesíti. Kövesse azokat a folyamatokat, amelyel már rendelkezésre állnak környezetében a más frissítések ellenőrzésére. A Frissítések Pénzügyi és Üzemeltetési alkalmazásokban való alkalmazásának a műveletekkel kapcsolatos további tudnivalókat lásd az [Egy verzió áttekintése témakörben](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="when-will-my-organization-be-migrated"></a>Mikor történik meg a saját szervezetem áttelepítése?

Az egyes szervezetek áttelepítése a konfigurációtól és az új infrastruktúrára való áttelepítésre való alkalmasságtól függ. Ezek a dátumok változhatnak.

- Azok a szervezetek, amelyek a Pénzügy és Művelet modult használják a HR-modulban, a rendszeres "Egyverziós" frissítési folyamat részeként megkapják az HR-funkciókat Dynamics 365 Human Resources. Az új funkciók a tervek szerint 2022 januárjától válnak általánosan elérhetővé.
- A kizárólag a Dynamics 365 Human Resources rendszert használó szervezetek hozzáférhetnek az átállási eszközökhöz, így 2022 közepétől megkezdhetik a tesztelést és az átállást. Még nem határoztuk meg azt a dátumot, amikorra az új infrastruktúrára való átállást végre kell hajtani. Az áttelepítési eszköz elérhetővé válását követően legalább egy évet biztosítunk erre.
- Azok a szervezetek Dynamics 365 Human Resources, amelyek mind pénzügyi, mind műveleti alkalmazásokat is használni fognak, hozzáférhetnek az áttelepítési eszközökhöz, így megkezdheti a tesztelést és az áttelepítést 2022 végén kezdődően. Még nem határoztuk meg azt a dátumot, amikorra az új infrastruktúrára való átállást végre kell hajtani. Az áttelepítési eszköz elérhetővé válását követően legalább egy évet biztosítunk erre.

A Dynamics 365 Human Resources új funkcióival kapcsolatos további tudnivalókat lásd a [Human Resources újdonságai és módosításai](./hr-admin-whats-new.md) részben.

### <a name="my-organization-has-not-yet-gone-live-on-dynamics-365-human-resources-should-we-go-live-with-the-human-resources-module-in-the-finance-and-operations-apps-or-with-the-dynamics-365-human-resources-app-on-the-legacy-infrastructure"></a>Szervezetem még nem élő a Dynamics 365 Human Resources rendszerben. A Pénzügyi és üzemeltetési alkalmazásokban Dynamics 365 Human Resources vagy az örökölt infrastruktúra alkalmazásában az Emberi erőforrások modullal együtt kell együtt működikni?

Fontos figyelembe venni, hogy milyen HR-funkciókra van szükség, és hogy ezek a funkciók mikor lesznek elérhetők az új infrastruktúrán. Ha a szervezetnek szüksége van a személyzet kezeléséhez szükséges alapfunkciókra, amely jelenleg elérhető az új infrastruktúra Pénzügy és műveletek alkalmazás hr modulban. Dynamics 365 Human Resources A 10.0.25-ös verzióban várható a Pénzügy és műveletek alkalmazás HR-modulja és az alkalmazás közötti funkció paritás, amely az ütemezés szerint 2022 márciusában lesz általánosan elérhető. Az olyan integrációs funkciók, mint a Teams alkalmazás és a Dataverse entitás integrációk a későbbi kiadásokban lesznek elérhetők.

Ha a szervezet HR-funkcióira van szükség az új infrastruktúra számára a szervezet működésének időtartamán belül, akkor könnyebb lehet a Pénzügy és műveletek alkalmazások Emberi erőforrások moduljának használata. Ez könnyebb migrációt eredményez, mivel ez egy szabványos alkalmazásfrissítés lesz a Dynamics 365 Human Resources alkalmazáshoz, és az ügyfél már az új infrastruktúrán lesz. Ha a szervezet úgy dönt, hogy a Dynamics 365 Human Resources alkalmazást a régi infrastruktúrán vezeti be, akkor az új infrastruktúrára való áttéréshez környezeti migrációra lesz szükség. Ez elkerülhető az új infrastruktúra éles üzembe helyezésével.

### <a name="i-am-using-new-capabilities-that-are-available-only-in-dynamics-365-human-resources-such-as-leave-and-absence-and-benefits-management-will-these-capabilities-now-be-available-in-the-human-resources-module-on-the-finance-and-operations-infrastructure-too"></a>Olyan új funkciókat használok, amelyek csak a Dynamics 365 Human Resources alkalmazásban érhetők el (például **Szabadság és távolét** és **Juttatások kezelése**). Ezek a képességek elérhetők lesznek a Pénzügyi és üzemeltetési infrastruktúra modulban is?

Igen, minden Dynamics 365 Human Resources modul úgy működik, mint a Pénzügy és a Műveletek alkalmazásokban, és 100 százalékos funkció paritás lesz. Az ezeket a funkciókat jelenleg a HR-ben jelenleg felhasználó vevőkre vonatkozó átfogó áttelepítési stratégia részeként a rendszer áttelepíti a vevőadatokat, hogy továbbra is a pénzügyi és a műveleti infrastruktúra területén dolgozzon.

### <a name="i-use-the-new-dynamics-365-human-resources-benefits-management-capabilities-ive-built-custom-integrations-with-the-hr-module-on-the-finance-and-operations-infrastructure-so-that-i-can-take-advantage-of-the-payroll-capabilities-by-using-benefits-data-will-these-custom-integrations-be-required-going-forward"></a>A Dynamics 365 Human Resources új juttatáskezelési képességeit használom. Egyéni integrációt építtem fel a HR modullal a Pénzügyi és műveleti infrastruktúra modulban, hogy a juttatások segítségével ki tudjam használni a bérszámfejtési lehetőségeket. Ezt követően szüksége lesz ezekre az egyéni integrációkra?

Az infrastruktúra-egyesítés részeként a HR-adatok ugyanannak az adatbázisnak a részei, mint a többi Pénzügyi és Üzemeltetési alkalmazás. A Továbbiakban nem szükséges integrálni a modulokat a Pénzügy és az Üzemeltetés alkalmazásból.

### <a name="my-organization-uses-one-or-more-isv-solutions-with-dynamics-365-human-resources-will-our-isv-solutions-be-migrated-automatically"></a>A szervezetem egy vagy több ISV-megoldást használ a Dynamics 365 Human Resources alkalmazással. A saját ISV-megoldásaink automatikusan át lesznek telepítve?

A független szoftverszállítói (ISV) megoldásoknál az áttelepítési élmény a megoldás integrációs módszerétől függően eltérő lehet. A Microsoft szorosan együttműködik az ISV-kkel, így biztosítja az új infrastruktúrára való zökkenőmentes átállást.

### <a name="my-organization-uses-linkedin-talent-hub-integration-with-dynamics-365-human-resources-will-this-integration-continue-to-work-after-the-infrastructure-change-is-completed"></a>A szervezem a LinkedIn Talent Hub integrációját használja a Dynamics 365 Human Resources alkalmazással. Továbbra is működik majd ez az integráció az infrastruktúra-módosítás befejezése után?

Nem, a LinkedIn Talent Hub integráció nem fog működni az új infrastruktúrára való áttérés után. A LinkedIn Talent Hub integrációs szolgáltatása a régi Dynamics 365 Human Resources infrastruktúrával együtt nyugdíjba vonul.

### <a name="my-organization-uses-the-human-resources-app-for-teams-will-the-app-continue-to-work-after-the-infrastructure-change-is-completed"></a>Saját szervezetem a Human Resources alkalmazást használja a Teamshez. Továbbra is működik majd ez az alkalmazás az infrastruktúra-módosítás befejezése után?

Igen a Teamshez készült Human Resources alkalmazás az új infrastruktúrára való áttelepítés után is működni fog.

### <a name="my-organization-has-configured-custom-security-in-dynamics-365-human-resources-will-our-custom-security-still-be-applied-after-the-infrastructure-change-is-completed"></a>Szervezetem egyéni biztonsági beállításokat konfigurált a Dynamics 365 Human Resources alkalmazásban: Az infrastruktúra-változás befejezése után is alkalmazva lesznek az egyéni biztonsági megoldásaink?

Igen, az új infrastruktúrába való adatáttelepítésben is szerepelni fognak az egyéni biztonsági konfigurációk.

### <a name="we-are-using-data-integrator-to-move-data-between-dynamics-365-human-resources-and-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected"></a>Az Adat integrátort használjuk az adatoknak a Dynamics 365 Human Resources Pénzügy és a Művelet alkalmazás között való áthelyezéséhez. Hogyan lesz ez hatással éppen integrált adatokra?

A jelenleg a Dynamics 365 Human Resources rendszerben található HR-adatok szinkronizálódnak a Dataverse rendszerrel. Ezután az Adat integrátor egy megoldással egy megoldásként szinkronizálható a Pénzügy és a Műveletek alkalmazással. Az új infrastruktúrába való áttelepítés után a HR-adatok natívak lesznek a Pénzügy és műveletek alkalmazásokban. Az adat integrátorra a továbbiakban nem lesz szükség az adatoknak a Pénzügy és az Üzemeltetési alkalmazások, illetve az Emberi erőforrások közötti szinkronizálásához.

A Human Resources aktuális Dataverse natív adattáblái továbbra is szinkronizálni fogják az új infrastruktúra alatt a környezet adatait. Az entitások kétírásos formátum támogatásához lesznek konvertálva. A többi Dynamics 365 alkalmazások az Adatintegrátor segítségével konfigurált egyéb adatintegrációi a jelenleg konfigurált módon folytatódnak.

### <a name="we-are-using-dual-write-to-move-hr-data-between-dataverse-and-other-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected-by-the-migration-to-the-new-infrastructure"></a>A hr-adatokat két írással Dataverse mozgatjuk meg a pénzügy és a művelet más alkalmazásai között. Hogyan lesz hatással az jelenleg integrált adatokra az új infrastruktúrára való áttelepítés?

A HR-adatok natívak lesznek a környezetben, az új infrastruktúra pénzügyi és műveleti alkalmazásaiban. A kettős írást a HR-adatoknak az új környezet és a Dataverse környezet közötti mozgatására használják.

### <a name="we-have-built-custom-integrations-from-dynamics-365-human-resources-to-one-or-more-external-systems-will-we-have-to-develop-new-integrations-after-the-infrastructure-change-is-completed"></a>Egyéni integrációt építünk fel egy Dynamics 365 Human Resources felől egy vagy több külső rendszerbe. Új integrációkat kell majd fejlesztenünk infrastruktúra-módosítás befejezése után?

Ez az integrációs végponttól függ. A Pénzügy és műveletek alkalmazásokban elérhető integrációs technológiákkal és [a legjobb integrációs technológia választásával kapcsolatos további tudnivalókat lásd az Integráció áttekintése témakörben](../fin-ops-core/dev-itpro/data-entities/integration-overview.md).

### <a name="we-have-extended-dataverse-for-dynamics-365-human-resources-will-these-extensions-be-migrated-automatically"></a>Bővítettük a Dataverse-t a Dynamics 365 Human Resources alkalmazáshoz. Ezek a bővítések automatikusan át lesznek telepítve?

Ha az Dynamics 365 Human Resources Dataverse új infrastruktúra környezetben a környezethez kapcsolódó pénzügyi és műveleti környezetek ugyan ahhoz a környezethez csatlakoznak, Dataverse a két alkalmazás az áttelepítés után is ugyanannak a környezetnek a csatlakoztatva lesz. A Dataverse bővítmények esetében nem lesz szükség migrációra.

Ha azonban Dynamics 365 Human Resources Dataverse a pénzügy és a művelet környezete jelenleg külön környezetekhez kapcsolódik, Dataverse akkor a két környezetet össze kell kombinálni, hogy az új infrastruktúra egyetlen környezetéhez kapcsolódtak. A Dataverse áttelepítés során a Human Resources estében szabványos Dataverse táblákat lehet csatlakoztatni és újraszinkronizálni az új Dataverse környezethez. A Dataverse környezethez készült bővítmények nem kerülnek automatikusan áttelepítésre, hanem azokat újra kell telepíteni az új környezetbe. Javasoljuk, hogy a felügyelt megoldások segítségével kezelje a Dataverse-bővítményeket. A további tudnivalókat lásd: [Bevezetés a megoldásokba](/powerapps/developer/data-platform/introduction-solutions).

### <a name="we-have-configured-microsoft-power-automate-flows-andor-microsoft-power-apps-to-work-with-dynamics-365-human-resources-will-these-microsoft-power-platform-components-be-migrated-and-work-automatically-after-the-infrastructure-change-is-completed"></a>Úgy konfiguráltuk a Microsoft Power Automate folyamatokra és/vagy Microsoft Power Apps alkalmazásokat, hogy működjenek Dynamics 365 Human Resources alkalmazással. Ezeket a Microsoft Power Platform összetevőket áttelepíti a program, és automatikusan működnek az infrastruktúra-módosítás befejezése után?

A Power Apps és Power Automate folyamatok és egyéb Microsoft Power Platform testreszabások hasonlóak a Dataverse bővítményekhez. Az, hogy az új infrastruktúrára való áttelepítés után automatikusan működnek-e, függ attól, hogy az Emberi Power Apps erőforrások alkalmazás, valamint a Pénzügy és a Műveletek alkalmazások ugyan ahhoz a környezethez csatlakoznak-e az áttelepítés előtt.

Ha az alkalmazások jelenleg ugyanahhoz a Power Apps környezethez vannak csatlakoztatva, akkor az új infrastruktúrára való áttelepítés után is csatlakoznak ugyanahhoz a Power Apps-környezethez. Ebben az esetben a Power Apps és Power Automate folyamatok és egyéb Microsoft Power Platform testreszabások további konfiguráció nélkül is működnek. Javasoljuk, hogy a felügyelt megoldások segítségével kezelje az alkalmazásbővítményeket a Dataverse alatt. A további tudnivalókat lásd: [Bevezetés a megoldásokba](/powerapps/developer/data-platform/introduction-solutions).

Ha azonban az Emberi erőforrások alkalmazás és a Pénzügy Power Apps és a Művelet alkalmazás külön környezethez kapcsolódik, akkor az áttelepítés részeként együtt kell őket kombinálni. Ehhez a feladathoz az szükséges, hogy az új környezetben újra legyen telepítve az összes Power Apps és más testreszabások.

### <a name="we-have-enabled-dataverse-virtual-tables-for-dynamics-365-human-resources-what-will-happen-to-these-tables-during-the-migration"></a>Engedélyeztük a Dataverse virtuális táblákat a Dynamics 365 Human Resources alkalmazáshoz. Mi történjen ezekkel a táblákkal az áttelepítés során?

Az áttelepítés után, ha az új infrastruktúra környezete továbbra is csatlakozik a jelenleg csatlakoztatott Dataverse-környezethez, amely kapcsolódik a Dynamics 365 Human Resources alkalmazáshoz, az ebben a környezetben létrehozott Dataverse virtuális táblák további konfiguráció nélkül is működni fognak.

Ha azonban az új infrastruktúra környezete az áttelepítés után másik Dataverse környezethez csatlakozik, akkor az új Dataverse-környezetben újra létre kell hozni a virtuális táblákat.

### <a name="we-have-developed-an-integration-by-using-the-applicant-tracking-system-ats-api-payroll-api-dataverse-virtual-tables-for-dynamics-365-human-resources-or-other-entities-in-the-dataverse-web-api-will-these-integrations-continue-to-work-after-the-infrastructure-change-is-completed"></a>Létrehoztunk egy integrációt az Applicant Tracking System (ATS) API, Payroll API, Dataverse virtuális táblák használatával a Dynamics 365 Human Resources alkalmazáshoz, vagy más entitásokhoz a Dataverse Web API-ban. Továbbra is működnek majd ezek az integrációk az infrastruktúra-módosítás befejezése után?

Az áttelepítés után, ha az új infrastruktúra környezete továbbra is csatlakozik a jelenleg csatlakoztatott Dataverse-környezethez, amely kapcsolódik a Dynamics 365 Human Resources alkalmazáshoz, minden a Dataverse webes API-hoz létrehozott integráció továbbra is működik az áttelepítés befejezés után is.

Ugyanakkor, ha a környezet egy az új infrastruktúrán egy másik Dataverse-környezethez kapcsolódik az áttelepítés után, a Dataverse webes API-hoz kifejlesztett integrációkat újra kell majd konfigurálni, hogy az új Dataverse-környezethez kapcsolódjanak.

### <a name="is-there-an-impact-on-the-azure-region-when-my-environment-is-migrated"></a>Befolyásolja az Azure-régiót, amikor a környezetem át lesz telepítve?

A Human Resources környezete jellemzően ugyanabban az Azure-régióban marad az áttelepítés során. Az egyetlen kivétel az, ha az Emberi erőforrások környezetet egy másik régió pénzügyi és műveleti környezetével egyesíteni fogják. Ebben az esetben az Emberi erőforrások környezet áttelepítőd a Pénzügyi és műveleti környezet Azure-régiójába.

### <a name="my-organization-depends-on-workflows-in-dynamics-365-human-resources-for-one-or-more-business-processes-will-the-workflows-be-migrated-automatically"></a>A saját szervezet egy vagy több üzleti folyamata Dynamics 365 Human Resources munkafolyamataitól függ. Ezek a munkafolyamatok automatikusan át lesznek telepítve?

Igen, a munkafolyamat-konfigurációk, a munkafolyamat-előzmények és az aktuális folyamatban lévő munkafolyamatok áttelepítésre kerülnek.

### <a name="what-training-and-resources-will-be-available-to-help-with-the-migration-process"></a>Milyen képzések és erőforrások lesznek elérhetők az áttelepítési folyamathoz?

Teljes dokumentációt biztosítunk, hogy részletesen leírjuk az áttelepítési folyamat mindegyik lépését. Szükség esetén további képzési erőforrások, például videók és workshopok is rendelkezésre állnak.

### <a name="my-organization-has-created-saved-views-in-dynamics-365-human-resources-to-improve-the-usability-of-the-interface-will-the-saved-views-be-migrated-automatically"></a>A szervezetem létrehozott mentett nézeteket Dynamics 365 Human Resources alkalmazásban a felület használhatóságának javítása érdekében. A mentett nézetek automatikusan át lesznek telepítve?

Igen, a mentett nézetek át lesznek telepítve az új infrastruktúrába.

### <a name="we-are-using-ceridian-with-dynamics-365-human-resources-will-the-ceridian-integration-be-available-after-the-infrastructure-change-is-completed"></a>A Ceridiant használjuk a Dynamics 365 Human Resources alkalmazással. A Ceridian integráció infrastruktúra-módosítás befejezése után is elérhető lesz? 

A Ceridian rendszer integrációja át lesz telepítve a Bérlista API-on alapuló integrációba. A fájl alapú integrációt, Dynamics 365 Human Resources amely jelenleg létezik, nem lehet áttelepíteni a pénzügyi és műveleti infrastruktúrába. A további tudnivalókat lásd: [Bérszámfejtés API bevezetés](./hr-admin-integration-payroll-api-introduction.md).

### <a name="how-will-the-migration-affect-the-service-update-process"></a>Hogyan fogja befolyásolni az áttelepítés a szolgáltatásfrissítés folyamatát?

Az áttelepítés után a vevők nagyobb rugalmasságot fognak kapni az ALM és a szolgáltatásfrissítések szempontjából. A szolgáltatásfrissítések már nem lesznek automatikusan alkalmazva a Human Resources környezetekre. Ehelyett a szolgáltatás az Egyverziós szolgáltatásfrissítések folyamatait és funkcionalitását követi. Ennek megfelelően a frissítések konfigurációs beállításai az LCS-n keresztül lesznek elérhetők. További információ: [Egyetlen verzió áttekintése](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="how-will-the-migration-affect-my-lcs-project-for-dynamics-365-human-resources"></a>Hogyan lesz hatással az áttelepítés a saját Dynamics 365 Human Resources LCS-projektjeimre?

Az új infrastruktúra áttelepítése Dynamics 365 Human Resources a környezetek kezelését egy LCS-megvalósítási projektbe mozgatja át. Ha az áttelepítés egy Dynamics 365 Human Resources meglévő Pénzügyi és Műveleti környezettel egyesít, az Emberi erőforrások LCS-projekt egyesítése a Pénzügy és műveletek alkalmazás LCS-megvalósítási projektje között történik. Ha jelenleg csak a Dynamics 365 Human Resources alkalmazást használja, a rendszer létrehoz egy új LCS implementálási projektet, és a meglévő Human Resources LCS-projektet áttelepíti az új projektbe.

Az új projekt ugyanolyan típusú projekt lesz, mint amit a Pénzügy és üzemeltetési alkalmazások használnak. A környezetkezelésben ugyanazok a funkciók és funkciók lesznek elérhetők. További tudnivalókért lásd: [Lifecycle Services-erőforrások](../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

### <a name="we-have-linked-our-task-recordings-to-the-business-process-modeler-in-human-resources-how-will-the-business-process-modeler-be-migrated-and-merged-into-lcs"></a>Feladatrögzítések kapcsolva vannak az Üzletifolyamat-modellezőhöz a Human Resources alkalmazásban. Hogyan történik az Üzletifolyamat-modellező áttelepítése és egyesítése az LCS-felületre?

Az LCS-projekt üzletifolyamat-könyvtárait áttelepíti a rendszer az új LCS-projektbe a Human Resources számára.

### <a name="my-organization-currently-uses-only-dynamics-365-human-resources-what-resources-are-available-so-that-we-can-learn-more-about-the-development-capabilities-after-the-infrastructure-change-is-completed"></a>A szervezetem jelenleg csak a Dynamics 365 Human Resources alkalmazást használja. Milyen erőforrások állnak rendelkezésre, hogy az infrastruktúra-változás befejezése után többet tudjunk meg a fejlesztési lehetőségekről?

Mind Microsoft Power Platform a extensibility lehetőségek, mind a Pénzügy, mind a Műveletek extensibility lehetőség elérhetővé válik, és felhasználható fejlesztésre. A további tudnivalókat lásd a [Kezdőlap kialakítása és testreszabása](../fin-ops-core/dev-itpro/dev-tools/developer-home-page.md) részben.

### <a name="we-have-enabled-features-in-dynamics-365-human-resources-will-these-features-be-enabled-automatically-during-the-migration"></a>Engedélyeztünk funkciókat a Dynamics 365 Human Resources alkalmazásban. Automatikusan engedélyezve lesznek ezek a szolgáltatások az áttelepítés során?

Azt, hogy az új infrastruktúra szolgáltatását automatikusan engedélyezzük-e, minden egyes szolgáltatás esetében külön lesz meghatározva. Ez az információ szerepelni fog a funkció dokumentációjában.

### <a name="what-happens-to-my-byod-database-during-the-migration"></a>Mi történik a BYOD-adatbázisommal az áttelepítés során?

A saját adatbázis bevonása (BYOD) konfigurációjának importálása és exportálása az új infrastruktúrába lesz áttelepítve.

### <a name="what-happens-to-my-azure-data-lake-during-the-migration"></a>Mi történik az Azure Data Lake adattavammal az áttelepítés során?

A Pénzügy és műveletek Azure Data Lake Storage alkalmazásokban jelenleg konfigurált minden export az áttelepítés után is ugyanazt a konfigurációt fogja karbantartani.

### <a name="we-are-currently-using-dynamics-ax-2012-will-the-upgrade-tools-that-are-currently-available-be-used-to-upgrade-the-hr-module-in-ax-2012-to-dynamics-365-human-resources"></a>Jelenleg a Dynamics AX 2012-t használjuk. Az AX 2012 – Dynamics 365 Human Resources HR moduljának frissítéséhez aktuálisan elérhető frissítési eszközök elérhetők lesznek?

Igen. Dynamics 365 Human Resources A <a0/&;<a0/&a1><a2/&a4>része lesz az egyesített kódbázisnak és a Pénzügyi és Üzemeltetési alkalmazások infrastruktúrájának. A Dynamics AX 2012 Dynamics 365 Human Resources verzióról való frissítés ugyanazt a frissítési útvonalat és eszközt fogja használni, amely a Pénzügy és műveletek alkalmazás legújabb verziójára való frissítéshez szükséges.

### <a name="we-use-document-handling-with-dynamics-365-human-resources-what-will-happen-to-the-documents-during-the-migration"></a>Dokumentumkezelést használunk a Dynamics 365 Human Resources alkalmazással. Mi történik ezekkel a dokumentumokkal az áttelepítés során?

A dokumentumok megmaradnak a meglévő dokumentumtárolóban. Újra hozzárendeli őket a rendszer az új infrastruktúra környezetéhez.

### <a name="what-happens-to-the-batch-jobs-that-we-have-configured-in-dynamics-365-human-resources-after-the-migration"></a>Mi történik a Dynamics 365 Human Resources alkalmazásban konfigurált kötegelt feladatokkal az áttelepítés után ?

Az érintett kötegelt feladatok automatikusan át lesznek telepítve az új infrastruktúrába.

## <a name="licensing-impact"></a>Licencelési hatás

Ez a dokumentáció nem helyettesíti és nem cseréli le a használatra vonatkozó jogokat tartalmazó jogi dokumentációkat.

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-does-our-licensing-or-cost-change"></a>A szervezetem a Dynamics 365 Human Resources alkalmazást használja a HR műveleteinek kezelésére. A licencelés vagy a költség változik?

Ez a változás nem érinti a vevőket, akik Dynamics 365 Human Resources licenceket vásároltak. Ezeknek a vevőknek nincs licencáttelepítés. A kiegészítő tesztverziós termékváltozat (SKU), amely kifejezetten a Human Resources alkalmazáshoz volt specifikus a továbbiakban nem lesz érvényes. Ehelyett az ügyfelek választhatják, hogy a 2. szintű, pénzügyi és műveleti alkalmazásokat vásárolják egy kissé alacsonyabb költséggel. A meglévő ügyfelek, akik az Emberi erőforrások eszközét megvásárolták, áttelepítik a Pénzügyi és műveleti alkalmazások 2. szintű mappájába, további költség nélkül.

### <a name="my-organization-uses-the-human-resources-module-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-does-my-licensing-or-cost-change"></a>Egy szervezet a Dynamics 365 Pénzügy, Az Ellátásilánc-kezelés, a Commerce és a Projektművelet modul emberi erőforrások modulját használja. A licencelés vagy a költség változik?

A Dynamics 365-alkalmazások meglévő felhasználói és a különálló Dynamics 365 Pénzügy, Ellátásilánc-kezelés, Commerce és Projektműveletek felhasználói a licencek részeként 2025 februárig, illetve a jelenlegi licencszerződés lejártáig hozzáférhetnek az Emberi erőforrásokhoz, amelyik korábban van. Dönthet úgy, hogy korábban áttér a Human Resources licencekre, ha az segítséget jelent Önnek, vagy így költségeket takaríthat meg. 2025 februártól kezdve minden meglévő CSP- és EA-vevőnek le kell fordítania a HR modult, és meg kell vásárolnia az emberi erőforrás licenceket, hogy kihasználja a Pénzügy és műveletek alkalmazásokba telepített új funkciókat.

### <a name="my-organization-is-live-with-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-will-we-be-required-to-purchase-an-additional-environment-to-support-the-infrastructure-merge"></a>Saját szervezet működik együtt a Dynamics 365 Pénzügy, Az Ellátásilánc-kezelés, a Commerce és a Projektműveletekkel. Meg kell majd vásárolni egy további környezetet az infrastruktúra-egyesítés támogatása érdekében?

Nincs szükség további környezetekre az infrastruktúra-változás támogatásához.

