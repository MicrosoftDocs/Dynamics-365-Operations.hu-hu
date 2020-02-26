---
title: Adatintegrációs technológia választása
description: Ez a cikk útmutatást nyújt a Human Resources által kezelt adatokkal való integráció különféle lehetőségeiről, és leírja a különböző integrációs technológiák jellemzőit, hogy az integrátorok megalapozott döntéseket hozhassanak az igényeiknek legjobban megfelelő technológiákkal kapcsolatban.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f2de5dd41c00e6546b4a4feadaf5774430d572bb
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029888"
---
# <a name="choose-a-data-integration-technology"></a>Adatintegrációs technológia választása

A Dynamics 365 Human Resources olyan üzleti adatokat kezel, amelyek számos üzleti folyamat során hasznosak. Ez a cikk útmutatást nyújt a Human Resources által kezelt adatokkal való integráció különféle lehetőségeiről, és leírja a különböző integrációs technológiák jellemzőit, hogy az integrátorok megalapozott döntéseket hozhassanak az igényeiknek legjobban megfelelő technológiákkal kapcsolatban.

## <a name="data-integration-vision"></a>Az adatintegráció áttekintése

A Microsoft az üzleti adatokat olyan kulcsfontosságú eszköznek tekinti, amely egyedivé teszi a vállalatát. Vállalatának adatai rendkívül értékesek. A vállalat egyik része által összegyűjtött és kezelt adatok a vállalat egy másik része által összegyűjtött adatokhoz kapcsolódnak, és ezek a kapcsolatok felhasználhatók az üzleti folyamatok és az üzleti intelligencia szervezeten belüli tökéletesítésére. Egyszerű, biztonságos és stabil hozzáférés biztosítása az üzleti adatokhoz, függetlenül attól, hogy melyik rendszer az adatok „tulajdonosa” – ez a kulcsfontosságú elv abban a szemléletben, amelyet a Human Resources rendszerben megvalósított adatintegrációhoz alkalmazunk.

Korábban nehézkes volt az adatok integrálása több rendszer között.
A Microsoft lépéseket tesz annak érdekében, hogy könnyebb legyen az adatok integrálása, és komoly haladást ért el a [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro) segítségével.

Még tovább lépve a Human Resources segítségével a Common Data Service válik a Human Resources szolgáltatás preferált nyilvános felületévé. Arra számítunk, hogy idővel a Human Resources által kezelt összes fontos adat megjelenik a Common Data Service szolgáltatásban. A Common Data Service szolgáltatást olyan technológiaként tudjuk ajánlani, amely megfelelő választás a legtöbb integrációs alkalmazáshoz. Tisztában vagyunk azzal, hogy a Common Data Service szolgáltatásban nincs még jelen az alkalmazása számára szükséges összes adat, és hogy a projektjeinek időbeosztásai más technológiákat is igényelhetnek, ezért azt kérjük, hogy tudassa velünk, ha a Common Data Service nem felel meg az integrációs igényeinek.

## <a name="integration-technologies"></a>Integrációs technológiák

A következő szakaszok leírják a Human Resources szolgáltatással használható különböző adatintegrációs technológiákat.

### <a name="common-data-service-entities"></a>Common Data Service-entitások

A Common Data Service a Human Resources elsődleges nyilvános adatillesztő-felülete. A Common Data Service egy kiérlelt platformra épül, amely a Dynamics 365 „XRM” platformból jött létre, amelyre a [Dynamics 365 Customer Engagement](https://docs.microsoft.com/dynamics365/#pivot=business-apps&panel=customer-engagement) megoldásai épülnek.

A Common Data Service platformot biztosít az adatentitások, valamint az ezekhez az entitásokhoz hozzáférő API számára. A szervezetében telepített Human Resources szolgáltatás egy Common Data Service-példányhoz csatlakozik, és a Human Resources adatait kezelő entitások telepítve lesznek az adott Common Data Service-példányban, így az entitások és az adatok elérhetővé válnak minden olyan alkalmazás számára, amely csatlakozik a Common Data Service-példányhoz. Attól függően, hogy a Human Resources melyik alkalmazásait használja, a Human Resources közvetlenül hajtja végre az adatműveleteket a Common Data Service-entitásokon (például az Attract és az Onboard esetében), vagy szinkronizálja az adatok a Common Data Service-entitásokkal a megfelelő irányban.

Miután a Common Data Service már tartalmazza azokat az adatentitásokat, amelyek az adatokat szolgáltatják az integrációs alkalmazásai számára, teljes mértékben kihasználhatja a [Common Data Service és a támogatott API-k ](https://docs.microsoft.com/powerapps/#pivot=home&panel=developer) által nyújtott lehetőségeket. A támogatott API-k között szerepel a [Dynamics 365 webes API-ja](https://docs.microsoft.com/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api), amely egy OData-megvalósítást biztosít a Common Data Service-adatok eléréséhez.

A Common Data Service-entitások és a társított API-k jelentik a legjobb megoldást a Human Resources-adatok eléréséhez a webalkalmazásokból, a webszolgáltatásokból és API-kból, valamint az OData-adatfolyamokhoz csatlakozó egyéb alkalmazásokból.

> [!NOTE]
> Ha úgy dönt, hogy a Common Data Service szolgáltatást választja a viszonylag újnak számító Human Resources adatillesztó-felületének, előfordulhat, hogy az integrációhoz szükséges Human Resources-adatentitások még nem érhetők el a Common Data Service<sup>1</sup> szolgáltatásban. Ha az integrációhoz szükséges Human Resources-entitások még nem állnak rendelkezésre, akkor várnia kell, amíg az adatentitások elérhetővé válnak, vagy az alábbiakban ismertetett egyéb integrációs technológiák valamelyikét kell használnia.
> 
> Alapértelmezés szerint a Common Data Service-integráció ki van kapcsolva az olyan új környezetekben, amelyekben nem szerepelnek a bemutató adatok. Az integráció be van kapcsolva a bemutató adatokat tartalmazó új környezetekben, és az adatok szinkronizálása a környezet létesítése alkalmával kezdődik. Miután a környezet készen áll az adatok szinkronizálására, bekapcsolhatja az integrációt.

<sup>1</sup>A Common Data Service szolgáltatásban elérhető Human Resource-entitások listáját lásd: [A Human Resources és a Common Data Service](https://docs.microsoft.com/dynamics365/unified-operations/talent/corehrentities) Az Attract és az Onboard esetében az összes entitás elérhető a Common Data Service szolgáltatásban.

### <a name="dmfdixf-entities"></a>DMF-/DIXF-entitások

A Human Resources elsődlegesen a Finance and Operations alkalmazásai által is használt platformra épül, és [adatkezelési keretrendszert (DMF)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json), más néven adatimportálási keretrendszert (DIXF) biztosít, valamint adatentitás-készleteket, amelyek az adatoknak a Human Resources szolgáltatásba történő importálásához és exportálásához használhatók. Noha a Common Data Service-entitások alkotják a Human Resources elsődleges adatintegrációs felületét, a DMF-entitások továbbra is hasznosak lehetnek bizonyos körülmények között, például a következő helyzetekben:

- A Common Data Service-entitások még nem érhetők el.

- Az integrációhoz nagy teljesítményű tömegesadat-importálási és-exportálási lehetőségek szükségesek.

A DMF-entitások nyújtják jelenleg a legteljesebb adatlefedettséget a Human Resources adatai számára.

A DMF nem megfelelő a valós idejű integrációk számára (például amikor azonnali felhasználói visszajelzés szükséges a felhasználói felületen), mivel a csomagműveletek ütemezett kötegelt feladatok, és a kötegelt szolgáltatás gyakran minimum 1–2 perces késéssel tudja elkezdeni a feladat végrehajtását, és ehhez adódik még az importálási vagy exportálási művelet végrehajtásához szükséges idő is.

A DMF akkor lehet a legjobb megoldás, ha nagy áteresztőképességre van szükség (például rekordok ezreinek éjszakára ütemezett importálása vagy exportálása esetén).

> [!NOTE]
> A DMF nem érhető el az Attract és az Onboard alkalmazáshoz.

### <a name="dmf-package-rest-api"></a>DMF-csomag REST API-ja

A DMF a [REST API-t](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-api) biztosítja az adatcsomagok kezeléséhez. Ez az API használható a DMF-fel folytatott programozott kommunikációhoz, például a következő műveletek esetében:

- Adatcsomag importálása.

- Adatcsomag exportálása.

- Importálási/exportálási művelet állapotának ellenőrzése.

A DMF csomag REST API-ja teljes mértékben támogatott a Human Resources szolgáltatásban: Core HR.

### <a name="azure-sql-db-byod"></a>Azure SQL DB (BYOD)

A DMF emellett egy hatékony funkciót is biztosít (a [saját adatbázis használatát](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/export-entities-to-your-own-database) – BYOD), amely lehetővé teszi, hogy a Human Resources szolgáltatás az Ön Microsoft Azure SQL-adatbázisába exportálja az adatait. Ez rendkívüli rugalmasságot biztosít, mivel amikor az adatok jelen vannak a saját SQL-adatbázisában, igénybe vehet olyan alkalmazásokat vagy középrétegű megoldásokat, amelyek csatlakozni tudnak az SQL-adattárakhoz.

A BYOD általában csak olvasást végző megoldásnak tekintendő. Az Azure SQL-adatbázisban tárolt minden adatot kezelhet és tárolhat (például az adategyesítésekhez), azonban az Azure SQL-adatbázisban tárolt adatok nem lesznek visszaszinkronizálva a Human Resources adataival.

A BYOD a jelentésekhez, az adatintegrációkhoz, az adategyesítésekhez, valamint az [Azure Data Factory](https://docs.microsoft.com/azure/data-factory/) folyamatainak adatforrásaihoz alkalmas.

> [!NOTE]
> A BYOD nem érhető el az Attract és az Onboard alkalmazáshoz.

### <a name="odata-enabled-entities"></a>OData-kompatibilis entitások

A DMF-entitások többsége a Human Resources adatszolgáltatásán (OData) keresztül is elérhető. A [Finance and Operations OData szolgáltatásához](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/odata) biztosított dokumentáció általánosságban a Human Resources szolgáltatásra is érvényes, de az OData által is használt saját entitások létrehozásával kapcsolatos dokumentáció nem érhető el.

Bár a Common Data Service és a Common Data Service által (a [Dynamics 365 Web API](https://docs.microsoft.com/previous-versions/dynamicscrm-2016/developers-guide/mt593051(v=crm.8)) használatával) biztosított OData-megvalósítás a preferált a Human Resources adatszolgáltatással szemben, a Human Resources adatszolgáltatás jelenleg teljesebb entitáslefedettséget kínál a Human Resources-adatok számára.

### <a name="excel-add-in"></a>Excel-bővítmény

Az [Excel-bővítmény](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in?toc=/dynamics365/unified-operations/talent/toc.json) lehetővé teszi az OData-kompatibilis entitások felszín alatti használatát. Kényelmes módszert biztosít a végfelhasználók számára a Human Resources-adatok beolvasására és módosítására az Excel megszokott felületén.

Az Excel-bővítmény megfelelő az üzleti tartomány szakértői számára is az eseti adatimportáláshoz és -exportáláshoz. A programozott automatizálást igénylő ismétlődő adatintegráció esetében alkalmasabb lehet egy másik integrációs technológia.

### <a name="data-integrator"></a>Data Integrator

A Common Data Service rendszergazdai felülete tartalmaz egy [adatintegrátor szolgáltatást](https://docs.microsoft.com/powerapps/administrator/data-integrator), amely a Common Data Service adatintegrációihoz használható. A Data Integrator használatával integrációs projektek definiálhatók (ez gyakran olyan előre definiált sablonok alapján történik, amelyeket az alkalmazás fejlesztői alakítottak ki a különböző integrációknak megfelelőn). Az integrációs projektek ütemezhetők ismétlődő automatikus futtatásra, vagy manuálisan is futtathatók.

A Data Integrator projektjei megfelelőek a Common Data Service kötegelt integrációi számára, és jó választást jelentenek a Dynamics 365 termékcsaládba tartozó alkalmazások közötti integrációhoz. A Microsoft például biztosít egy használatra kész Data Integrator-sablont, amelynek segítségével a Human Resources-adatok integrálhatók a Dynamics 365 Finance szolgáltatásba. További tudnivalók: [Integráció a Dynamics 365 Human Resources és a Dynamics 365 Finance között](hr-admin-integration-finance.md).

### <a name="power-query"></a>Power Query

A Data Integrator támogatást biztosít a [Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query) számára is (a [speciális lekérdezési funkcióján](https://docs.microsoft.com/powerapps/administrator/data-integrator#advanced-data-transformation-and-filtering) keresztül).
A Power Query hatékony, rugalmas adatszűrést és-átalakítást tesz lehetővé, beleértve az M képletnyelvet, és nem lesz szokatlan azok számára, akik már szereztek tapasztalatokat a Power BI-jelentések fejlesztésében.

## <a name="deciding-on-an-integration-technology"></a>Az integrációs technológiára vonatkozó döntés

Mivel számos különböző integrációs technológia érhető el, a használandó integrációs megközelítés kiválasztására vonatkozó döntés sokszor komoly gondolkodásra adhat okot. Az idő haladtával, és különösen a Common Data Service adatlefedettségének kiérlelődésével a döntés is könnyebb lesz, mivel a Common Data Service lesz a legtöbb esetben az elsődleges adatfelület. Amíg ez meg nem valósul, vélekedhet úgy, hogy a Common Data Service még nem felel meg az igényeinek. A következő táblázat összefoglalja a különböző integrációs technológiai lehetőségek néhány kulcsfontosságú jellemzőjét.

| Technológia/eszköz/API    | Ismétlődő integrációk                   | Szinkron/aszinkron                    | Programozott hozzáférés API-val        | Megfelelő adatkötetek                                   | Adatlefedettség                       |
|------------------------|------------------------------------------|---------------------------------------------|-------------------------------------------|------------------------------------------------------------|-------------------------------------|
| Common Data Service-entitások           | Igen, a Data Integrator vagy középrétegű megoldás használatával | Szinkron, aszinkron, kötegelt (a Data Integratorral) | Igen, a Dynamics 365 Web API-val (OData) | A használati esettől függően változik (támogatja a lapozást az interaktív használathoz) | Javítás<sup>2</sup>                       |
| DMF-entitások           | Igen, középrétegű megoldásokkal ütemezve        | Aszinkron, kötegelt                                | Igen, a DMF csomagok REST API-jával         | Magas (rekordok százezrei)                    | Magas                                |
| DMF-csomagok REST API-ja   | Igen, középrétegű megoldásokkal ütemezve        | Aszinkron, kötegelt                                | Igen                                       | Magas (rekordok százezrei)                    | Az API az összes DMF-entitást támogatja       |
| BYOD                   | Igen, a Human Resources rendszergazdája által ütemezve        | Aszinkron, kötegelt                                | Nem<sup>3</sup>                                    | Magas (rekordok százezrei)                    | Az összes DMF-entitást támogatja           |
| OData-kompatibilis entitások | Igen, középrétegű megoldás használatával                    | Szinkronizálás                                        | Igen, a Human Resources adatszolgáltatásával (OData)  | A használati esettől függően változik (támogatja a lapozást az interaktív használathoz) | Magas                                |
| Excel-bővítmény           | Nem                                       | Szinkronizálás                                        | Nem                                        | Közepes (rekordok tízezrei)                      | Támogatja az összes OData-kompatibilis entitást |
| Data Integrator        | Igen, a Data Integratorban ütemezve        | Aszinkron, kötegelt                                | Nem                                        | A használati esettől függően változik                                       | Az összes Common Data Service-entitást támogatja           |

<sup>2</sup>A Microsoft nagymértékben növeli az adatlefedettséget a Common Data Service-entitások számára, és azt javasolja, hogy a lefedettség kiépítése után a Common Data Service legyen az elsődleges adatfelület. A Common Data Service adatlefedettsége jelenleg alacsony a DMF- és az OData-kompatibilis entitásokéhoz képest.

<sup>3</sup>Az SQL-adatbázis programkóddal érhető el.

## <a name="summary"></a>Összegzés

Az üzleti adatok értékes eszköznek számítanak, de az értékük számottevően csökkenhet, ha nehézséget jelent az adatok felhasználása a meghatározott célokra (például jelentéskészítéshez, adategyesítésekhez vagy egyéni alkalmazásokhoz). A Dynamics 365 Human Resources számos technológiát kínál, amelyek lehetővé teszik az adatokkal való munkát a Human Resources alkalmazás felhasználói felületén (UI) kívül is az adatokhoz való hozzáférés integrációjának biztosításával. Ez a témakör ismertette az elérhető integrációs technológiákat és azok néhány kulcsfontosságú jellemzőjét. Ez a tájékoztatás segítséget nyújt az integrációs projektekhez használandó megoldások kiválasztásával kapcsolatos döntések meghozásához.

