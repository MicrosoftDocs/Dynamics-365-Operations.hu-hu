---
title: A Finance and Operations-alkalmazások szolgáltatásleírása
description: Ez a témakör a Finance and Operations-alkalmazások szolgáltatásleírását tartalmazza.
author: tomhig
ms.date: 12/07/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: whigginb
ms.search.validFrom: 2021-09-03
ms.openlocfilehash: f7ce73018fda79156cc7ef3d4e1faa3fedf966f8
ms.sourcegitcommit: b101c21f972fdad2667431f712222e040cd69d43
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/07/2021
ms.locfileid: "7898389"
---
# <a name="service-description-for-finance-and-operations-apps"></a>A Finance and Operations-alkalmazások szolgáltatásleírása

[!include[banner](../includes/banner.md)]

A Finance and Operations-alkalmazások a vállalati erőforrás-tervezés (ERP) „szoftver szolgáltatásként” (SaaS) ajánlattételének részei, amelyeket a [Microsoft Azure](https://azure.microsoft.com/overview/what-is-azure/) rendszerre és rendszer számára hoztak létre. A Finance and Operations-szolgáltatás olyan ERP-funkciókat biztosít a szervezeteknek, amelyek egyedi követelményeiket támogatják, és segítik őket az üzleti környezetek folyamatos változásához való alkalmazkodásban anélkül, hogy kezelniük kellene az infrastruktúrát. A Finance and Operations-alkalmazások a következő megoldásterületeket tartalmazhatják:

- [Dynamics 365 Finance](/dynamics365/finance/)
- [Dynamics 365 Human Resources](/dynamics365/human-resources/)
- [Dynamics 365 Supply Chain Management](/dynamics365/supply-chain/)
- [Dynamics 365 Commerce](/dynamics365/commerce/)
- [Dynamics 365 Project Operations](/dynamics365/project-operations/)

Az [üzleti intelligenciával](/power-bi/fundamentals/power-bi-service-overview), az [infrastruktúrával](https://azure.microsoft.com/global-infrastructure/), a [számítási](/azure/service-fabric/service-fabric-overview) és [adatbázis-szolgáltatásokkal](https://devblogs.microsoft.com/azure-sql/running-1m-databases-on-azure-sql-for-a-large-saas-provider-microsoft-dynamics-365-and-power-platform/) együtt ezek az alkalmazások lehetővé teszik a szervezetek számára, hogy az iparágukra jellemző és üzemeltetési üzleti folyamatok futtatását. A megvalósítási partnerük által támogatva, az ügyfelek meghatározzák az üzleti alkalmazás logikájának konfigurációját, amely leginkább megfelel az egyedi üzleti folyamatoknak. A funkciók és üzleti folyamatok a következő megoldások egyikével vagy ezek egy kombinációjával bővíthetők és terjeszthetők ki:

- Beépített [személyre szabási felület](personalize-user-experience.md)
- A [Microsoft Power Platform](../../dev-itpro/power-platform/overview.md) eszközei
- [Visual Studio](https://visualstudio.microsoft.com)–alapú [Finance and Operations szoftverfejlesztő készlet (SDK)](../../dev-itpro/dev-tools/developer-home-page.md) és [Azure DevOps buildautomatizálás](../../dev-itpro/dev-tools/developer-home-page.md#build-automation-using-azure)
- Független szoftvergyártói (ISV) megoldások az [AppSource](https://appsource.microsoft.com/partners)-tól

A követelmények alapján a vevők saját megoldási módszerüket választják. A megvalósítási partnerükkel együttműködve meghatározzák, fejlesztik és tesztelik a megoldásukat a [Microsoft Dynamics Lifecycle Services (LCS)](../../dev-itpro/lifecycle-services/lcs.md) rendszerben biztosított eszközök és bevált gyakorlatok segítségével. Négy általános helyzet lehetséges:

- A standard szintű Finance and Operations-alkalmazások beépített konfigurációja (bővítmények nélkül)
- Egy vagy több ISV-megoldást tartalmazó Finance and Operations-alkalmazáskonfiguráció
- Egy vagy több vevőspecifikus bővítményt tartalmazó Finance and Operations-alkalmazáskonfiguráció
- Finance and Operations-alkalmazáskonfiguráció, amely vevőspecifikus bővítmények és egy vagy több ISV-megoldás kombinációját tartalmazza

A szervezetek követhetik az üzleti növekedésüket, hiszen egyszerűen adhatnak hozzá felhasználókat és üzleti folyamatokat egy egyszerű, transzparens előfizetési modellen keresztül. [A Dynamics 365 licencelési útmutató](https://www.microsoft.com/licensing/docs/view/Microsoft-Dynamics-365) című témakörben olvashat bővebben.

## <a name="operating-model"></a>Minősítési modell

A Finance and Operations-alkalmazások működési modellje a szolgáltatás teljes életciklusában meghatározza az ügyfél, a megvalósítási partner és a Microsoft számára meghatározott szerepköröket és felelősségeket. További tájékoztatás: [Felhőműveletek és szervizelés](../../dev-itpro/lifecycle-services/cloud-operations-servicing.md).

### <a name="customer-activities"></a>Ügyféltevékenységek

Az ügyfelek a [Dynamics 365 implementáció útmutatóját](https://community.dynamics.com/365/dynamics-365-fasttrack/p/dynamics365implementationguide), a keretrendszert, valamint [Success by Design](/dynamics365/fasttrack/success-by-design-overview), [Lifecycle Services](../../dev-itpro/lifecycle-services/lcs.md) rendszernek a megoldás megvalósításához rendelkezésre álló eszközöket és gyakorlati sablonokat követik, partnerüknek és [Microsoft FastTrackjüknek](/dynamics365/fasttrack/) megfelelően. Gyakori tevékenységek a következők:

- Felhasználói identitás és biztonságkezelés
- Üzleti folyamatok meghatározása, kialakítása és működtetása
- Bővítmények meghatározása, fejlesztése, tesztelése és működtetése
- Nem termelési telepítések figyelése és kezelése
- Alkalmazásfrissítések kezelése és bővítmények érvényesítése
- ISV-megoldások és külső gyártó integrációja

### <a name="microsoft-responsibilities"></a>Microsoft-felelősségi körök

A Microsoft kezeli a Finance and Operations szolgáltatást az ügyfelek teszt- és működési környezeteinek telepítése, aktív figyelése és szervizelése által a Microsoft SaaS előfizetésben. Ez a kezelés magában foglalja a rendszerinfrastruktúra felosztását, amely a szolgáltatás futtatásához és az ügyfelekkel a szolgáltatás állapotáról való proaktív kommunikálásához szükséges. A feladatkörök a következők:

**Infrastruktúra-kezelés**
- Biztonság és elkülönítés
- Operációs rendszerek és virtualizálás
- Kiszolgálók, tárolás és hálózat
- Adatközpont áramellátása, hálózatépítés, hűtés

**Alkalmazásplatform-kezelés**
- 24/7 alkalmazásfigyelés és értesítések
- Diagnosztika, platformfrissítések, javítások, szolgáltatásfrissítések
- Alkalmazásirányítás, terheléselosztás, hely replikálása
- Környezet létesítése és kezelése
- Adatbázis-kezelés, magas rendelkezésre állás (HA)/vészhelyreállítás (DR), skála, műveletek
- Telepítés kiszámítása, felskálázás és leskálázás

## <a name="system-configuration"></a>Rendszerkonfiguráció

A Finance and Operations alkalmazások a tranzakció volumenének és a felhasználói terhelésnek megfelelően skáláznak. Minden ügyfél-megvalósítás egyedi megoldást kínál, amely a következő elemekből áll:

- **Adatok összetétele** – a paraméterek egyedi halmaza, amely a működést, a szervezet elrendezését, az alapadatok szerkezetét (például pénzügyi és készletdimenziókat) és a tranzakciókövetés részletességét szabályozza.
- **Kiterjesztés és konfigurálás** – a kódkiterjesztéseket használó bővítményi megchanizmusokat, ISV-megoldásokat és egyedi konfigurációkat, amelyek munkafolyamatokat, integrációkat és jelentéskonfigurációkat magukban foglalnak.
- **Felhasználási mintázatok** – az online és kötegelt használat egyedi kombinációja, amely együttesen lehetővé teszi az egységes adatáramlás érdekében való fel- és lefelé irányuló rendszerekkel való integrációt, valamint az ügyfelek üzleti folyamataikban használt adatnézetek alapján történő megkülönböztetésére való képességet.

A Microsoft olyan működési környezeteket konfigurál, amelyek méretei a tranzakció volumenének és a felhasználói párhuzamosság kezeléséhez szükségesek. A Microsoft a következő feladatokért felelős:

- Az erőforrások megfelelő felosztása a működési környezetekben, a vevő profilkészítési adatai alapján a [LCS előfizetés-becslésében](../../dev-itpro/lifecycle-services/subscription-estimator.md)
- A működési környezetek szolgáltatás-elérhetőségének folyamatos figyelése és ellenőrzése
- A rendszer teljesítményével kapcsolatos problémák elemzése és hibaelhárítása a Finance and Operations-alkalmazásokkal

Annak biztosítására, hogy a megvalósítás nagy teljesítményre legyen konfigurálva, a vevőknek a következő feladatokat kell elvégezniük:

- Az [LCS előfizetési becslésben](../../dev-itpro/lifecycle-services/subscription-estimator.md) található Finance and Operations-implementációval kapcsolatos pontos használati információk szolgáltatása.
- Bővítmények létrehozása és tesztelése teljesítménnyel és skálázással kapcsolatban.
- Az adatkonfigurációk megfelelő tesztelése a teljesítményhez.
- A skálázhatóság biztosítása a [teljesítménytesztelés](https://community.dynamics.com/365/b/techtalks/posts/performance-testing-approach-april-30-2018) segítségével használat előtt.

## <a name="onboarding-and-implementation"></a>Előkészítés és megvalósítás

Az alábbi táblázat bemutatja a jellemző előkészítési és megvalósítási eseményeket.

| Kérelem | Várt Microsoft-művelet | Várt vevői/megvalósítási partnerművelet |
|---|---|---|
| Kezdeti ajánlat beszerzése | Az LCS-projekt az ajánlat beszerzése után jön létre, egy, a vevő által kiváltott esemény alapján. | Menjen végig a Nagyvállalati Szerződés (EA) vagy a Felhőmegoldás-szolgáltató (CSP) [kereskedelmi folyamaton](before-you-buy.md). A partner létrehoz egy bérlőt a vevő számára, ha van ilyen. |
| Bővítmény beszerzése | Hozzáférés megadása a vevőnek a megvalósítás során kiválasztott bővítményhez. | Nem alkalmazható |
| Megvalósítás tervezése és elemzése | Megfelelő eszközök biztosítása az LCS-ben, mint például az [Üzletifolyamat-modellező (BPM)](../../dev-itpro/lifecycle-services/bpm-overview.md), és [együttműködést az Azure DevOps](../../dev-itpro/lifecycle-services/synchronize-bpm-vsts.md) rendszerrel. | Tervezze meg a projektet, állítsa be az Azure DevOps rendszerben, végezze el a rendszer előkészítését és állítsa be a rendszergazdafiókot. |

A további tudnivalókat lásd: [Előkészítés egy megvalósítási projekttel kapcsolatban](../imp-lifecycle/onboard.md).

## <a name="globalization"></a>Globalizáció

A Finance and Operations-alkalmazásokat világszerte számos Azure-régió szolgáltatja. A Finance and Operations-alkalmazások olyan funkciókat biztosítanak, amelyek a különböző országokat/régiókat és anyanyelveket támogatják. További információ: [Honosítási és a szabályozási funkciók](../../dev-itpro/lcs-solutions/country-region.md#localization-and-regulatory-features).

### <a name="countryregion-specific-considerations"></a>Ország- vagy régióspecifikus szempontok

- A szabályozott iparágban vagy kereskedelmi szervezetben található olyan vevőknek, akik entitásokkal rendelkeznek Franciaországban, és helyi adattárolási helyre van szükségük, tekintsék át: [Finance and Operations Franciaországban](../../dev-itpro/deployment/france-local-deployment.md).
- Az ügyfelek, akik Kínában folytatnak üzletet, tekintsék át: [Finance and Operations amelyet a 21Vianet működtet Kínában](../../dev-itpro/deployment/china-local-deployment.md).
- Az Oroszországban üzletet folytató ügyfelek tekintsék át: [Oroszorszégi személyesadat-honosítással kapcsolatos törvény](/business-applications-release-notes/october18/dynamics365-finance-operations/russian-regulations-on-prem#when-will-the-cloud-deployment-option-of-dynamics-365-for-finance-and-operations-be-generally-available-for-russia).

### <a name="general-data-protection-regulation-gdpr"></a>Általános adatvédelmi rendelet (GDPR)

A Finance and Operations-alkalmazások esetében a Microsoft feldolgozóként viselkedik. Adatfeldolgozóként a Finance and Operations olyan folyamatokat és szolgáltatásokat biztosít, amelyek segítik a vevőket az adatkezelőként felmerülő GDPR-kötelezettségeknek való megfelelésben. További információ: [GDPR áttekintése](../../dev-itpro/gdpr/gdpr-guide.md).

## <a name="environment-and-data-management"></a>Környezet és adatkezelés

Ez a szakasz a szolgáltatásban előforduló jellemző környezeti és adatkezelési eseményeket írja le.

### <a name="environment-and-data-management-events-for-production-instances"></a>Működési példányok környezet- és adatkezelési eseményei

Az LCS [önkiszolgáló eszközöket](../../dev-itpro/deployment/infrastructure-stack.md) és [adatbázis-mozgási műveleteket](../../dev-itpro/database/dbmovement-operations.md) biztosít, amelyek a környezet- és adatkezelési feladatok elvégzésére használhatók. Íme néhány példa:

**Esemény:** [Működési példány kérése](../imp-lifecycle/prepare-go-live.md#requesting-the-production-environment)

- Töltse ki a [Közzétételi ellenőrzőlistát](../imp-lifecycle/prepare-go-live.md), és küldje el a [Microsoft FastTrack](/dynamics365/fasttrack/)-csapatnak.
- A termelési példány kérése előtt töltse ki az [LCS-előfizetés becslését](../../dev-itpro/lifecycle-services/subscription-estimator.md).
- Az [LCS-módszertanban](../../dev-itpro/lifecycle-services/create-methodology.md) meghatározott összes megvalósítási feladat végrehajtása.

**Esemény:** [Tesztkörnyezeti-adatbázis másolása termelési példányba](../../dev-itpro/database/dbmovement-scenario-goldenconfig.md)

- Próbaközzétételhez vagy tényleges közzétételi átálláshoz használják.

**Esemény:** [Karbantartási mód](../../dev-itpro/sysadmin/maintenance-mode.md)

1. Kapcsolja be a karbantartási módot az LCS-ben.
2. A szükséges karbantartást hajtsa végre.
3. Kapcsolja ki a karbantartási módot az LCS rendszerben.

### <a name="environment-and-data-management-events-for-non-production-instances"></a>Nem működési példányok környezet- és adatkezelési eseményei

Az LCS [önkiszolgáló üzembe helyezést](../../dev-itpro/deployment/infrastructure-stack.md) és [adatbázis-mozgási műveleteket](../../dev-itpro/database/dbmovement-operations.md) biztosít, amelyek a környezet- és adatkezelési feladatok elvégzésére használhatók. Íme néhány példa:

**Esemény:** [Új tesztkörnyezeti példány telepítése](../../dev-itpro/deployment/deployenvironment-newinfrastructure.md)

- Győződjön meg arról, hogy minden szükséges példány [meg van tervezve](../imp-lifecycle/environment-planning.md), és a megfelelő kiegészítő bővítményajánlatokat megvásárolták.
- Futtassa a telepítési folyamatot az LCS szolgáltatásban.
- Az LCS-ellenőrzőlistában meghatározott összes feladatot hajtsa végre.
    
>[!NOTE]
>A fejlesztői tesztkörnyezet egy virtuális gép (VM), amelyet az [ügyfél Azure-előfizetésére telepítettek](../../dev-itpro/dev-tools/access-instances.md) és az ügyfél kezeli.

**Esemény:** [Arany konfigurációs adatbázis másolása tesztkörnyezetből működési példányba](../../dev-itpro/database/dbmovement-scenario-goldenconfig.md)

- Próbaközzétételhez vagy tényleges közzétételi átálláshoz használják.

**Esemény:** [Működési példány időponthoz kötött biztonsági másolatának visszaállítása nem működési példányra](../../dev-itpro/database/database-pitr-prod-sandbox.md)

- Futtassa az [Adatbázis frissítése](../../dev-itpro/database/database-refresh.md) beállítást az LCS-ben.
- Utómásolás: Törölje vagy rejtse el az érzékeny adatokat parancsfájlokkal, módosítsa a környezetspecifikus alkalmazáskonfigurációkat (pl. integrációs végpontokat), és engedélyezzen vagy adjon hozzá felhasználókat. Ne feledje, hogy ezek a változtatások egy [adatcsomag](../../dev-itpro/data-entities/data-entities-data-packages.md#import-a-data-package) alkalmazásával végezhetők el.

**Esemény:** [Nem működési példány adatbázisának időponthoz kötött visszaállítása](../../dev-itpro/database/database-point-in-time-restore.md)

- Fogadja el, hogy a folyamat nem vonható vissza.
- Az időponthoz való visszaállítási műveletet futtassa az LCS-rendszeren.

**Esemény:** A 2. szintű tesztkörnyezeti adatbázs másolása fejlesztési tesztkörnyezetbe hibajavításhoz és [hibakereséshez](../../dev-itpro/database/dbmovement-scenario-debugdiag.md)

- Futtassa az adatbázis exportálási műveletét az LCS rendszerben, a 2. szintű tesztkörnyezetben.
- Adatbázis importálása és frissítése a fejlesztői környezetben.

## <a name="data-backup-and-retention"></a>Adatok biztonsági mentése és megőrzése

A Finance and Operations-környezetek adatbázisai a SaaS-előfizetésben automatikus biztonsági másolatokkal védettek. Éles környezetben az automatikus biztonsági másolatok 28 napig megmaradnak, hacsak a Microsoft nem végez visszaállítást. A teszt- (2. szintű) környezetek esetén 7 napig tárolják őket. A működési környezet visszaállítása akkor következhet be, ha a tervezett karbantartási frissítések során hiba történik.

Az automatikus biztonsági mentésekkel kapcsolatos további tudnivalókat lásd: [Automatikus biztonsági másolatok – Azure SQL-adatbázis & SQL-kezelt példány](/azure/azure-sql/database/automated-backups-overview?tabs=single-database).

## <a name="service-activity-responsibilities"></a>Szerviztevékenységgel kapcsolatos felelősségi körök

A következő táblázat a szolgáltatásra jellemző helyzeteket és tevékenységeket ír le. Azt is jelzi, hogy a Microsoft, az ügyfél, illetve mind a Microsoft, mind az ügyfél felelős-e a tevékenységekért.

| Tevékenység | Microsoft felelőssége | Ügyfél felelőssége |
|---|---|---|
| **Kezdeti bérlők kiépítése** | | |
| Az Előfizetés becslési eszközével méretezhető a várható terhelés az LCS-ben, és kérhető az egyes környezetek kiépítése. | | X |
| Építse ki az összes működési példányt és nem működési példányt. | X | |
| Ellenőrizze a telepített működési példányokat és nem működési példányokat. | | X |
| **Szolgáltatásfrissítések** | |
| Szolgáltatásfrissítéseket alkalmazása a kijelölt nem működési és működési példányokhoz. | X | |
| Szolgáltatásfrissítések manuális alkalmazása az LCS-ből tesztkörnyezeti példányokhoz. A frissítés definiálása, fejlesztése, és a kódfrissítés visszaküldése az LCS-be. | | X |
| Bővítményfrissítések működési példányra való alkalmazásának kérelmezése és ütemezése. | | X |
| A frissítések alkalmazása előtt hozzon létre biztonsági másolatot a kódról és az adatokról a működési példányban. | X | |
| Hiba esetén vissza kell állítani a termelési példányt a kód és az adatok biztonsági mentésére. | X | |
| **Adatkezelés (biztonsági másolat, visszaállítás és frissítés)** | | |
| Készítsen biztonsági mentést az adatbázisról. | X | |
| A magas rendelkezésre állás és a vészhelyreállítási terv meghatározása. | X | |
| A termelési példányok adatbázisának teljesítményének figyelése. | X | |
| A termelési példányok adatbázisának összehangolása a teljesítmény érdekében. | X | |
| A termelési példány adatbázisának egy időponthoz kötött frissítése nem termelési példányra. | | X |
| **Az infrastruktúra frissítése** | | |
| Rendszeres infrastruktúra-frissítések ütemezése. | X | |
| **Skálázás felfelé és lefelé (felhasználók, ttárterület és példányok)** | | |
| További felhasználókat és nem működési bővítményeket vásárolhat. | | X |
| Frissítse a használat változásait az LCS Előfizetés-becslési eszközében. | | X |
| Jelentse a szolgáltatás használatát befolyásoló lényeges teljesítménybeli problémákat. | | X |
| Az adott szolgáltatáshoz szükséges erőforrások proaktív kezelése. | X | |
| Az esetek kivizsgálása és hibaelhárítása. | X | |
| **Biztonság (felhasználói hozzáférés)** | | |
| Adjon felhasználói hozzáférést a szolgáltatáshoz. | | X |
| Adjon LCS-projekthozzáférést a példányok kezeléséhez és üzemeltetéséhez, amelyeket az LCS-en keresztül helyeztek üzembe. | | X |
| **Működési példányok figyelése** | | |
| A működési példányok figyelése 24/7 történjen. | X | |
| Proaktív módon értesítse az ügyfelet olyan esetekről, amelyek a működési példánnyal kapcsolatosak. | X | |
| **Nem működési példányok kezelése és figyelése** | | |
| Nem termelési példányok kezelése az LCS segítségével. | | X |
| Nem-működési példányok figyelése. | | X |

## <a name="service-update-strategy"></a>Szolgáltatásfrissítési stratégia

A [szoftver életciklusára vonatkozó irányelvnek](../../dev-itpro/migration-upgrade/versions-update-policy.md) megfelelően a Finance and Operations-alkalmazások a Microsoft [Modern életciklusra vonatkozó irányelvét](../../dev-itpro/migration-upgrade/versions-update-policy.md#modern-lifecycle-policy) követik, és olyan termékeket fednek le, amelyeket folyamatosan szervizelnek és támogatnak. 

A Microsoft a következő hónapokban nyolc szolgáltatásfrissítést ad ki az Finance and Operations-alkalmazásokhoz:

- Január
- Február
- Április
- máj.
- Július
- Augusztus
- Október
- November

>[!NOTE]
>Április és október a fő funkció-kiadási hullámok ideje. Az ügyfelek felfüggeszthetnek egy szolgáltatásfrissítést akár három egymást követő frissítési cikluson keresztül is.

További információért tekintse át az alábbi témaköröket:

- [Egyverziós szolgáltatásfrissítések áttekintése](../../dev-itpro/lifecycle-services/oneversion-overview.md)
- [Szolgáltatásfrissítések konfigurálása LCS-en keresztül](../../dev-itpro/lifecycle-services/configure-service-updates.md)
- [Szolgáltatásfrissítések szüneteltetése LCS-en keresztül](../../dev-itpro/lifecycle-services/pause-service-updates.md)
- [Értesítések kérése szolgáltatásfrissítésekkel kapcsolatban LCS-en keresztül](../../dev-itpro/lifecycle-services/notifications-service-updates.md)
- [Regresszív tesztelési eszközök a szolgáltatásfrissítések ellenőrzéséhez](../../dev-itpro/perf-test/rsat/rsat-overview.md)
- [Dynamics 365 ütemterv és kiadási hullámok](https://dynamics.microsoft.com/roadmap/overview/)

## <a name="security-and-administrative-access"></a>Biztonság és adminisztratív hozzáférés

A Finance and Operations működési környezet rendszergazdai hozzáférése szigorúan ellenőrzött és naplózott. Az ügyféladatok kezelése a [Microsoft Online szolgáltatásainak feltételeivel](https://www.microsoft.com/licensing/terms/productoffering) egyetértésben történik. 

### <a name="customer-administrative-access"></a>Ügyfél rendszergazdai hozzáférése

Az ügyfél bérlő-rendszergazdája hozzáférhet működési példányokhoz vagy nem működési példányokhoz a következő táblázatban leírtak szerint:

| Környezet típusa | Alkalmazás célja | A vevői hozzáférés szintje |
|---|---|---|
| **Nem működési**<br>1. szintű tesztkörnyezet | Nem működési környezet, amelyet a vevők helyeznek üzembe fejlesztési, bemutatási vagy képzési célból. | Az 1. szintű tesztkörnyezet (más néven felhőben tárolt környezet) egy ügyfél által kezelt VM, amely a vevő Azure-előfizetésére telepítve van az LCS-ről. Mivel ez egy virtuális gép az ügyfél Azure-előfizetésében, az ügyfél teljes rendszergazdai hozzáféréssel rendelkezik a környezethez a távoli asztalon keresztül. |
| **Nem működési**<br>2. (vagy magasabb) szintű tesztkörnyezet | Nem működési környezet, amelyet a vevők által a felhasználói elfogadás tesztelésére, integrációs tesztelésre, képzésre, előkészítésre vagy bármilyen más, éles üzem előtti helyzetre telepítik. | A 2. szintű és a magasabb szintű tesztkörnyezetek a Finance and Operations SaaS előfizetésbe vannak telepítve. A nem működési környezethez társított Azure SQL-adatbázisokhoz való hozzáférést az [igény szerinti hozzáféréssel](../../dev-itpro/database/database-just-in-time-jit-access.md) biztosítják. A távoli asztali hozzáférés nem érhető el. |
| **Termelés** | A működési környezet akkor telepíthető, ha a projekt [készen áll a kezdeti éles használatra](/imp-lifecycle/environment-planning.md#production-system-readiness). | A működési környezeteket a SaaS előfizetésre telepítik. Minden hozzáférés a böngészőn, a szolgáltatásvégpontokon vagy az LCS-n keresztüli elérést biztosít. |

### <a name="microsoft-administrative-access"></a>Microsoft adminisztratív hozzáférés

Az alábbi táblázat bemutatja a különböző Microsoft-rendszergazdák hozzáférési szintjét:

| Rendszergazda | Vevői adatok |
|---|---|
| Üzemi válaszok csapata<br>(Csak a központi személyzetére korlátozva) | A hozzáférés támogatási jegyen keresztül adható meg. A hozzáférést a rendszer naplózza, és csak a támogatási tevékenység időtartamára korlátozódik. |
| Microsoft ügyféltámogatási szolgáltatások (CSS) | Nincs közvetlen hozzáférés. Az ügyfél képernyőmegosztást is haználat a támogatási személyzettel való együttműködésre a hibák elhárítása érdekében. |
| Tervezés | Nincs közvetlen hozzáférés. Az Üzemeltetési válaszcsoport képernyőmegosztást használhat a mérnöki csapattal való együttműködéshez a hibák elhárítása érdekében. |
| Egyebek a Microsoftban | Nincs hozzáférés. |

## <a name="monitoring"></a>Figyelés

A Microsoft széles körű eszközkészletet biztosít a vevők működési példányainak figyelése és diagnosztizálása érdekében. A Microsoft napi 24 órában, heti 7 napon figyeli a vevők működési környezeteit. A további tudnivalókat lásd: [Termeléstámogatás és -figyelés](../imp-lifecycle/production-support-monitoring.md).

| Microsoft-felelősségi körök | Vevői felelősségi körök |
|---|---|
| <ul><li>A szolgáltatás elérhetőségének figyelése.</li><li>Folyamatos figyelés és riasztások az olyan kritikus összetevők állapotra vonatkozó mutatószámai és figyelői segítségével, mint például az Application Object Server (AOS), köteg, az adatok importálására/exportálására szolgáló keretrendszer (DIXF), Commerce és Management Reporter.</li><li>Kövesse nyomon az infrastruktúra-szolgáltatások (pl. Azure Active Directory \[Azure AD\] és Azure SQL) okozott teljesítménycsökkenést.</li><li>Ha a Microsoft úgy állapítja meg, hogy egyetlen folyamat vagy kötegelt feladat okozza a hibákat, akkor az adott feladatot vagy folyamatot leállítják az ügyféllel való kommunikációt követően.</li></ul> | <ul><li>Az alkalmazáskonfigurációk és -bővítmények módosításainak figyelése, amelyek működési és teljesítménybeli problémákat okozhatnak.</li><li>Az alkalmazáshibákat a figyelő eszközök segítségével kell diagnosztizálni. Ezekkel az eszközökkel diagnosztizálhatja a felhasználó által jelentett teljesítménybeli problémákat.</li><li>A Microsoft tájékoztatása, ha várható terhelés a rendszeren a becsült csúcsfelhasználáson túl.</li><li>Ha a megfelelő szolgáltatás nem érhető el a termelési példányon, akkor az ügyfél az LCS-en keresztül jelentést küldhet a [működés üzemkimaradásáról](../../dev-itpro/lifecycle-services/report-production-outage.md).</li></ul> |

Ha a támogatási kéréseket online, LCS-en keresztül küldik el, azzal az ügyfelek lehetővé teszik, hogy a Microsoft gyors és mélyreható technikai szakértelmet biztosítson hatékony módon. Annak ellenére, hogy a telefonos lehetőség elérhető, csak akkor használható, ha az online lehetőség nem érhető el. További információért lásd: [Telefonos támogatási lehetőségek](/power-platform/admin/support-overview.md?toc=/dynamics365/fin-ops-core/dev-itpro/toc.json&bc=/dynamics365/breadcrumb/toc.json#is-there-a-phone-number-i-can-call-to-contact-support).

## <a name="incident-management"></a>Esetkezelés

A Microsoft súlyossági szintek alapján válaszol az esetekre, és javítja őket. A Microsoft súlyossági szintjei az eset kezdeti értékelésekor módosíthatók, és amikor a hatásra és hatókörre vonatkozó további információ elérhetővé válik. Ha az esetet mérséklik, az esemény súlyossága változatlan marad.

A súlyossági szintekkel kapcsolatos további tudnivalókat lásd [ebben a súlyossági táblában](/power-platform/admin/support-overview#what-is-initial-response-time-and-how-quickly-can-i-expect-to-hear-back-from-someone-after-submitting-my-support-request).

## <a name="business-continuity-through-high-availability-and-disaster-recovery"></a>Üzletmenet-folytonosság a magas rendelkezésre állás és a vészhelyreállítás révén 

A Microsoft a Finance and Operations működési példányainak üzletmenet-folytonosságot és vészhelyreállítást biztosít az Azure-régió szintjén történt üzemszünet esetén. A további tudnivalókat lásd: [Üzletmenet-folytonosság és vészhelyreállítás](../../dev-itpro/sysadmin/business-continuity-disaster-recovery.md).

- **Magas rendelkezésre állás** – a HA-funkciók segítségével megakadályozhatja az üzemkimaradást, amelyet az Azure-adatközpont egyetlen csomópontjának hibája okozott. Minden egyes szolgáltatás felhőarchitektúrája az Azure rendelkezésre állási csoportját használja a szint kiszámításához, hogy megakadályozza az egy pontból fakadó hibák eseményeit. Az adatbázisok HA szolgáltatását az [Azure SQL HA szolgáltatásain](/azure/azure-sql/database/high-availability-sla) keresztül biztosítják.
- **Vészhelyreállítás** – [Azure vészhelyreállítási funkciói](/azure/best-practices-availability-paired-regions) védik az egyes szolgáltatásokat az olyan kimaradásokkal szemben, amelyek egy teljes Azure-adatközpontot érinthetnek. Az alábbiakban látható néhány ilyen funkció:

    - Az Azure SQL aktív geójának replikálása az elsődleges adatbázisra (üzleti adatbázis).
    - Az Azure Blob Storage geóban már létező példányai (amelyek dokumentummellékleteket tartalmaznak) más Azure-régiókba.
    - Az Azure SQL- és Azure Blob Storage-replikációk másodlagos régiója.

Az elsődleges adattárak támogatottak a replikációhoz. Emiatt az egyes szolgáltatások összetevői, például a Management Reporter és az entitástár átalakított adatokat használnak az elsődleges adatbázisból. Ezt az adatot azt követően kell generálni, hogy a visszaállítási webhelyet beállította, és elindította a szolgáltatást. Az ügyfélkód műtermékeit és a helyreállított adattárakat a webhely újbóli üzembe helyezésére használják. Az újratelepítés lehetővé teszi a számítási csomópontok állapotának replikálását a hálózattal és más összetevőkkel együtt, hogy a helyreállított adattárak segítségével állítsa be a másodlagos webhelyet. Ha az ügyfél működési példányát vészhelyreállítás segítségével állították helyre, a Microsoft és az ügyfél megfelelnek az [esetkezelési](service-description.md#incident-management) felelősségi körüknek.

A Microsoft vészhelyreállítási terveit és eljárásait rendszeresen ellenőrzik rendszer- és szervezetellenőrzések (SOC) vizsgálataival. Ezek a megfelelési ellenőrzések a bizonyítják a Microsoft DR-jének technikai és eljárási folyamatát, beleértve a Dynamics 365 Finance and Operations alkalmazásokat. Az [SOC-megfelelőségi](/compliance/regulatory/offering-soc-2) vizsgálat jelentései és az összes többi megfelelőségi jelentés megtalálható a [Microsoft megbízhatósági központ megfelelőségi szolgáltatáscsomagjában](/compliance/regulatory/offering-home).

| Microsoft-felelősségi körök | Vevői felelősségi körök |
|---|---|
| A Microsoft másodlagos környezetet biztosít az Azure párosított adatforrásában az elsődleges termelési példány telepítésekor. A további tudnivalókat lásd: [Üzletmenet-folytonosság és vészhelyreállítás (BCDR): Azure párosított régiók](/azure/best-practices-availability-paired-regions). | None |
| A Microsoft engedélyezi az Azure SQL- és Azure Blob Storage földrajzi redundanciáját az elsődleges termelési példány telepítésekor. | None |
| A Microsoft engedélyezi az automatikus biztonsági mentést az Azure SQL-adatbázisokon. | None |
| <p>Ha üzemkimaradás történik, a Microsoft meghatározza, hogy a vevő esetén el kell-e végezni a feladatátvételt, és hogy adatvesztés történik-e. A vevők a kiesés jellegétől és időzítésétől függően legfeljebb 15 percnyi adatvesztést tapasztalnak. | Adatvesztés esetén előfordulhat, hogy a vevőnek írásban alá kell írnia a feladatátvétel kiváltása érdekében. |
| A feladatátvételi folyamat esetén a megfelelő szolgáltatás korlátozott módban működik. A frissítés karbantartása nem indítható el feladatátvételi módban. | Az ügyfél nem kérhet csomagtelepítést vagy más rendszeres karbantartási kérést feladatátvételi módban. |
| Amikor az adatközpont működésbe lép, a Microsoft visszatér az elsődleges Azure-régió termelési példányához. A normál műveletek folytatódnak. | Előfordulhat, hogy az ügyfélnek vissza kell jelentkeznie a termelési példányra az elsődleges Azure-régióban. |

## <a name="finance-and-operations-support-offerings"></a>Finance and Operations támogatási ajánlattétel

A technikai támogatás olyan piacokon érhető el, ahol Finance and Operations-szolgáltatásokat kínálnak. [A támogatási felületet](../../dev-itpro/lifecycle-services/lcs-support.md) az LCS-ben és a Finance and Operations-alkalmazásokban biztosítanak. Íme néhány példa:

- [Megoldáskereső](../../dev-itpro/lifecycle-services/issue-search-lcs.md) az LCS-ben
- [Integrált technikai támogatás](../../dev-itpro/lifecycle-services/support-experience.md) a Finance and Operations-alkalmazásokban
- [Felhő alapú támogatás](../../dev-itpro/lifecycle-services/cloud-powered-support-lcs.md) az LCS-ben

A Microsoft három támogatási tervet kínál a Finance and Operations-vevőknek: Premier, Közvetlen professzionális támogatás, valamint az előfizetésben foglalt támogatást. A támogatás szintje tervenként eltérő. Az alábbi táblázat a három csomag összehasonlítását mutatja be.

| Támogatási funkció | Premier | Professzionális közvetlen | Előfizetés |
|---|---|---|---|
| Korlátlan szünet-/hibajavítási eset benyújtása | Igen | Igen | Igen |
| 24/7 hozzáférés LCS-en keresztül | Igen | Igen | Igen |
| Incidens válaszideje | Kevesebb, mint egy óra | Kevesebb, mint egy óra | Következő munkanap |
| Tanácsadási óra | A készletek szerződésenként lesznek beszerezve.. | Nem | Nem |
| Kijelölt támogatási ügyfélmenedzser | Igen | Nem | Nem |
| Kijelölt támogatási mérnök | Lépjen kapcsolatba küldő szerződés alapján | Nem | Nem |

A további tudnivalókat lásd: [Támogatás áttekintése](/power-platform/admin/support-overview).

### <a name="process-to-engage-support"></a>Támogatáshoz való tevékenység folyamata

A Finance and Operations-alkalmazásokkal kapcsolatos incidensek esetén az ügyfeleknek támogatási jegyeket kell küldeniük a Microsoftnak az LCS-en keresztül. A CSS kezeli az incidenst az ügyfél támogatási csomagja szerint, valamint az incidens súlyosságát, amit a CSS állapított meg.

### <a name="service-level-agreement"></a>Szolgáltatásiszint-szerződés

A Microsoft elkötelezett a szolgáltatás havonta 99,9 százalékos elérhetőségének biztosítása mellett. Ha a Microsoft nem éri el és nem tartja fenn a megfelelő szolgáltatási szintet a szolgáltatásiszint-szerződésnek (SLA) megfelelően, akkor a vevő jóváírásra jogosult a szolgáltatás havi szolgáltatási díjának egy részére. A szolgáltatási jóváírások kezdeményezéséről további információt az [SLA](https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services) „Követelések” részében találhat.

## <a name="important-resources"></a>Fontos erőforrások

- **[Megbízhatósági központ](https://www.microsoft.com/trust-center)** - Információkat találhat arról, hogy hol tárolják az Ön Finance and Operations-adatait, valamint további információkat az adatvédelmi, megfelelőségi és biztonsági eljárásokról.
- **[Licencelési feltételek és dokumentáció](https://www.microsoftvolumelicensing.com/)** – Gyorsan hozzáférhet a licencelési feltételekhez és kiegészítő információkhoz, amelyek a Microsoft mennyiségi licencelési programokon keresztül licencelt termékek és szolgáltatások használatával kapcsolatosak.
- **[Licencelési feltételek](https://www.microsoft.com/licensing/product-licensing/)** – Az ezen a lapon található erőforrások határozzák meg a Microsoft kereskedelmi licencprogramjaival vásárolt szoftveres és online szolgáltatási termékeire vonatkozó feltételeket.
- **[Microsoft-életciklus-irányelv](/lifecycle/)** – ez a lap egységes és kiszámítható útmutatást ad a támogatás elérhetőségére vonatkozóan a termék élettartama során.
- **[Licencelési útmutató](https://www.microsoft.com/licensing/docs/view/Microsoft-Dynamics-365)** – Ebben az útmutatóban további tudnivalókat olvashat a Dynamics 365 licencelésével kapcsolatban.
- **[Ügyféltámogatás](https://dynamics.microsoft.com/support/)** – Iparágvezető támogatást nyújt a Dynamics 365-alkalmazásokhoz.
- **[Dynamics Lifecycle Services](https://lcs.dynamics.com/)** – Itt kezelheti az alkalmazása életciklusát, és áttérhet tervezhető, megismételhető, jó minőségű megvalósításokra.

## <a name="definitions"></a>Definíciók

### <a name="azure-region"></a>[Azure-régió](/azure/availability-zones/az-overview#regions)

Olyan földrajzi terület, ahol egy vagy több Azure-adatközpont létezik. Ilyen például az Egyesült Államok és Európa.

### <a name="business-process-modeler-bpm"></a>[Üzletifolyamat-modellező (BPM)](../../dev-itpro/lifecycle-services/bpm-overview.md)

Egy LCS-ben található eszköz, amellyel egy adott megvalósításra végrehajtható egy hiányelemzés az American Productivity & Quality Centertől (APQC) származó üzletifolyamat-definíciók használatával, amelyek támogatottak a Finance and Operations-alkalmazásokban.

### <a name="cloud-solution-provider"></a>Felhőalapú megoldásszolgáltató

A Microsoft Felhőalapú megoldásszolgáltatói (CSP) program partneri tagja, amely az ügyfeleknek hozzáadott értékkel rendelkező felhőszolgáltatásokat, támogatást, egy számlát és skálázható ügyfélkezelést biztosít.

### <a name="customer"></a>Vevő

Az az üzleti entitás, amely felhasználja a Finance and Operations-alkalmazásokat, és egy bérlő képviseli az Office 365-ban.

### <a name="development-environment"></a>Fejlesztői környezet

Nem működési tesztkörnyezet, amely bővítmények fejlesztésére használható. Az ügyfelek ezt a környezetet saját Azure-előfizetésükre telepíthetik az LCS-ből. Ez a környezet bemutató-, képzési és egyéb tesztelési feladatok elvégzésére is használható. Ez [1. szintű tesztkörnyezetként](../imp-lifecycle/environment-planning.md#tier-1-vs-tier-2-and-higher) is ismert.

### <a name="downtime"></a>Leállás

Bármely időszak, amikor a felhasználók nem jelentkezhetnek be és nem férhetnek hozzá az aktív bérlőhöz a nem lejárt platform vagy a szolgáltatási infrastruktúra hibája miatt, ahogy azt a Microsoft az automatikus állapotfigyelés és a rendszernaplók alapján meghatározza. A leállási idő nem tartalmazza az ütemezett leállást, a szolgáltatás bővítményfunkcióinak elérhetetlenségét, a szolgáltatás elérésére irányuló képesség hiányát a szolgáltatáson végzett módosítások miatt, illetve a skálázási egységek kapacitását túllépő időszakokat.

### <a name="implementation-partner"></a>Megvalósítási partner

Az a partner, amelyet az ügyfél kiválaszt a Finance and Operations-megoldásainak testreszabásához, konfigurálásához, megvalósításához és kezeléséhez.

### <a name="incident"></a>Esemény

Olyan probléma, amelyet az ügyfél olyankor észlel, miközben a Finance and Operations szolgáltatást használja, és amelyre vonatkozóan beküld egy jegyet az LCS-en keresztül.

### <a name="microsoft-customer-support-services-css"></a>Microsoft ügyféltámogatási szolgáltatások (CSS)

A Microsoft globális támogatási csapata, amely a Finance and Operations alkalmazások minőségi szolgáltatásának nyújtására jött létre.

### <a name="microsoft-dynamics-lifecycle-services-lcs"></a>Microsoft Dynamics Lifecycle Services (LCS)

A Finance and Operations-alkalmazások életciklus-kezelésének rendszergazdai portálja a próbaverziótól a megvalósításon keresztül a működést követő kezelésig és támogatásig. További tudnivalókért lásd: [Lifecycle Services-erőforrások](../../dev-itpro/lifecycle-services/lcs.md).

### <a name="non-production-instance"></a>Nem-működési példány

A vevő által a bővítmények ellenőrzéséhez és más fejlesztési feladatok elvégzéséhez használt szolgáltatások bármely következő példánya:

- **1. szintű tesztkörnyezet** – Fejlesztői példány (ügyfél által tárolt)
- **2. szintű tesztkörnyezet** – Szabványos elfogadási tesztpéldány
- **3-5. szintű tesztkörnyezet** - Bővítmények tesztkörnyezetei

A 2–5. szintekkel kapcsolatos további tudnivalókat lásd: [A megfelelő 2. vagy magasabb szintű környezet kiválasztása](../imp-lifecycle/environment-planning.md#selecting-the-correct-tier-2-or-higher-environment).

### <a name="production-instance"></a>Működési példány

A Finance and Operations-környezet, amelyet az ügyfél az „élő” napi tranzakcióinak és üzleti folyamatainak kezelésére használ.

### <a name="sandbox-environment"></a>Tesztkörnyezet

Nem működési környezet, amelyet a vevő használ bemutatói, képzési, felhasználóelfogadás-tesztelési, bővítmény-ellenőrzési és más tesztelési feladatokra.

### <a name="service"></a>Szerviz

A Finance and Operations-alkalmazásokban foglalt alapvető szolgáltatások bármelyike.

### <a name="service-level-agreement-sla-for-microsoft-online-services"></a>Szolgáltatásiszint-szerződés (SLA) a Microsoft online szolgáltatásaihoz

A SLA a Microsoft online szolgáltatásaira vonatkozik. További információkért lásd: [Szolgáltatói szerződések](https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services).

### <a name="service-update"></a>Szolgáltatásfrissítés

A Microsoft a Finance and Operations-környezeteket a szolgáltatásfrissítések révén, rendszeres időközönként szervizeli. Az ügyfelek az üzleti igényeiknek megfelelően saját szolgáltatásfrissítési naptárat állíthatnak be. További információk: [Egyverziós szolgáltatásfrissítések](../../dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="user"></a>Felhasználó

Egy személy, aki Finance and Operations-környezeteket használ, és aki a vevő bérlőjéhez van társítva.
