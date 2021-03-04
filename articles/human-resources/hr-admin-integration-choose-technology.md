---
title: Válasszon ki egy adatintegrációs technológiát
description: Ez a cikk a Human Resources által kezelt adatokkal való integrációval kapcsolatban tartalmaz tájékoztatást. Leírja a különböző integrációs technológiákat, amelyek segítségével eldöntheti, hogy mely technológiáknak legmegfelelőbbek a szükségleteinek.
author: andreabichsel
manager: AnnBe
ms.date: 02/28/2020
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
ms.openlocfilehash: 9e6eeac66cff24d193e30aa942039707fc0aed52
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528341"
---
# <a name="choose-a-data-integration-technology"></a>Válasszon ki egy adatintegrációs technológiát

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a cikk a Dynamics 365 Human Resources által kezelt adatokkal való integrációval kapcsolatban tartalmaz tájékoztatást. Leírja a különböző integrációs technológiákat, amelyek segítségével eldöntheti, hogy mely technológiáknak legmegfelelőbbek a szükségleteinek.

## <a name="data-integration-background"></a>Az adatintegráció háttere

Az üzleti adatok olyan kulcsfontosságú eszközök, amely egyedivé teszik a vállalatát. Vállalatának adatai rendkívül értékesek. Az üzleti folyamatok és az üzleti intelligencia szervezeten belüli fejlesztése érdekében a vállalaton belül összegyűjtött adatok közötti kapcsolatokat is használhatja. Igyekszünk egyszerű, biztonságos és stabil hozzáférést biztosítani üzleti adataihoz, függetlenül attól, hogy melyik rendszerből származnak.

Korábban nehézkes volt az adatok integrálása több rendszer között.
A Microsoft lépéseket tesz annak érdekében, hogy könnyebb legyen az adatok integrálása, és komoly haladást ért el a [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro) segítségével.

A Human Resources segítségével a Common Data Service válik a Human Resources szolgáltatás preferált nyilvános felületévé. Arra számítunk, hogy idővel a Human Resources által kezelt összes fontos adat megjelenik a Common Data Service szolgáltatásban. A Common Data Service szolgáltatást olyan technológiaként tudjuk ajánlani, amely megfelelő választás a legtöbb integrációs alkalmazáshoz.

Előfordulhat, hogy a Common Data Service még nem tartalmazza az alkalmazás által igényelt összes adatot. Azzal is tisztában vagyunk, hogy a projekt időbeosztása alternatív technológiát igényelhet. Mindenképpen tudassa velünk , ha a Common Data Service nem felel meg az integrációs szükségleteknek.

## <a name="integration-technologies"></a>Integrációs technológiák

A következő szakaszok leírják a Human Resources szolgáltatással használható különböző adatintegrációs technológiákat.

### <a name="common-data-service-entities"></a>Common Data Service-entitások

A Common Data Service a Human Resources elsődleges nyilvános adatillesztő-felülete. A program a Dynamics 365 XRM-platformból nőtt ki, amelyet a [Dynamics 365 Customer Engagement](https://docs.microsoft.com/dynamics365/#pivot=business-apps&panel=customer-engagement) megoldások használnak.

Common Data Service egy platformot és API-t biztosít az adatentitásokhoz. A Human Resources telepítésekor az egy Common Data Service példányhoz kapcsolódik. A Human Resources entitásai abba a Common Data Service példányba települnek. Az entitások és adataik minden olyan alkalmazás számára elérhetők, amely csatlakozni képes a Common Data Service példányhoz. A Human Resources szinkronizálja az adatokat a Common Data Service entitások között.

Amikor az integrációs alkalmazások által igényelt adatentitások a Common Data Service szolgáltatásban vannak, teljes mértékben használhatja [Common Data Service szolgáltatást és a támogatott API-kat](https://docs.microsoft.com/powerapps/#pivot=home&panel=developer). A támogatott API-k között szerepel a [Dynamics 365 webes API-ja](https://docs.microsoft.com/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api), amely egy OData-megvalósítást biztosít a Common Data Service-adatok eléréséhez.

A Common Data Service-entitások és a társított API-jaik jelentik a legjobb megoldást a Human Resources-adatok eléréséhez a webalkalmazásokból, a webszolgáltatásokból és API-kból, valamint az OData-adatfolyamokhoz csatlakozó egyéb alkalmazásokból.

> [!NOTE]
> Ha úgy dönt, hogy a Common Data Service szolgáltatást választja a viszonylag újnak számító Human Resources adatillesztó-felületének, előfordulhat, hogy az integrációhoz szükséges Human Resources-adatentitások még nem érhetők el a Common Data Service szolgáltatásban.
</br>
> A Common Data Service szolgáltatásban elérhető Human Resource-entitások listáját lásd: [A Human Resources és a Common Data Service](https://docs.microsoft.com/dynamics365/unified-operations/talent/corehrentities).
> </br>
> Ha az integrációhoz szükséges Human Resources-entitások még nem állnak rendelkezésre, akkor várnia kell, amíg az adatentitások elérhetővé válnak, vagy az alábbiakban ismertetett egyéb integrációs technológiák valamelyikét kell használnia.
> </br>
> Alapértelmezés szerint a Common Data Service-integráció ki van kapcsolva az olyan új környezetekben, amelyekben nem szerepelnek a bemutató adatok. Az integráció be van kapcsolva a bemutató adatokat tartalmazó új környezetekben, és az adatok szinkronizálása a környezet létesítése alkalmával kezdődik. Miután a környezet készen áll az adatok szinkronizálására, bekapcsolhatja az integrációt.

### <a name="dmfdixf-entities"></a>DMF-/DIXF-entitások

A Human Resources nagyrészt a Finance and Operations alkalmazásokkal azonos platformra épül, és egy [Adatkezelési keretrendszert (DMF)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-entities-data-packages?toc=/fin-and-ops/toc.json) biztosít. A DMF Adatimportálási és-exportálási keretrendszerként (DIXF) is ismert. A Human Resources a humánerőforrás-adatok importálására és exportálására használható adatentitások készletét biztosítja. Noha a Common Data Service-entitások alkotják a Human Resources elsődleges adatintegrációs felületét, a DMF-entitások továbbra is hasznosak lehetnek bizonyos körülmények között, például a következő helyzetekben:

- A Common Data Service-entitások még nem érhetők el.

- Az integrációhoz nagy teljesítményű tömegesadat-importálási és-exportálási lehetőségek szükségesek.

A DMF-entitások nyújtják jelenleg a legteljesebb adatlefedettséget a Human Resources adatai számára.

A DMF nem megfelelő a valós idejű integrációhoz, például ha azonnali felhasználói visszajelzésre van szükség egy felhasználói felületen. A csomagműveletek az ütemezett kötegelt feladatok, és gyakran minimum 1-2 perc késéssel is jár, mielőtt a kötegelt szolgáltatás felveszi a feladatot a végrehajtáshoz, valamint az importálási és exportálási művelet befejezéséhez szükséges idő is ott van.

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

A DMF emellett egy hatékony funkciót is biztosít (a [saját adatbázis használatát](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/export-entities-to-your-own-database) – BYOD), amely lehetővé teszi, hogy a Human Resources szolgáltatás az Ön Microsoft Azure SQL-adatbázisába exportálja az adatait. Ez a funkció óriási rugalmasságot biztosít. Amikor az adatok jelen vannak a saját SQL-adatbázisában, igénybe vehet olyan alkalmazásokat vagy középrétegű megoldásokat, amelyek csatlakozni tudnak az SQL-adattárakhoz.

A BYOD elsősorban csak olvasható megoldás. Az Azure SQL-adatbázisban tárolt minden adatot kezelhet és tárolhat (például az adategyesítésekhez), azonban az Azure SQL-adatbázisban tárolt adatok nem lesznek visszaszinkronizálva a Human Resources adataival.

A BYOD a jelentésekhez, az adatintegrációkhoz, az adategyesítésekhez, valamint az [Azure Data Factory](https://docs.microsoft.com/azure/data-factory/) folyamatainak adatforrásaihoz alkalmas.

> [!NOTE]
> A BYOD nem érhető el az Attract és az Onboard alkalmazáshoz.

### <a name="odata-enabled-entities"></a>OData-kompatibilis entitások

A DMF-entitások többsége a Human Resources adatszolgáltatásán (OData) keresztül is elérhető. A [Finance and Operations OData szolgáltatáshoz](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/odata) biztosított dokumentáció érvényes a Human Resources alkalmazásra, kivéve a saját OData által használt entitások létrehozásához.

Bár a Common Data Service és a Common Data Service által (a [Dynamics 365 Web API](https://docs.microsoft.com/previous-versions/dynamicscrm-2016/developers-guide/mt593051(v=crm.8)) használatával) biztosított OData-megvalósítás a preferált a Human Resources adatszolgáltatással szemben, a Human Resources adatszolgáltatás jelenleg teljesebb entitáslefedettséget kínál a Human Resources-adatok számára.

### <a name="excel-add-in"></a>Excel-bővítmény

Az [Excel-bővítmény](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in?toc=/dynamics365/unified-operations/talent/toc.json) lehetővé teszi az OData-kompatibilis entitások felszín alatti használatát. Kényelmes módszert biztosít a végfelhasználók számára a Human Resources-adatok beolvasására és módosítására az Excel megszokott felületén.

Az Excel-bővítmény megfelelő az üzleti tartomány szakértői számára is az eseti adatimportáláshoz és -exportáláshoz. A programozott automatizálást igénylő ismétlődő adatintegráció esetében alkalmasabb lehet egy másik integrációs technológia.

### <a name="data-integrator"></a>Data Integrator

Az [Adatintegrátor szolgáltatás](https://docs.microsoft.com/powerapps/administrator/data-integrator) segítségével integrálhatja az adatokat a Common Data Service szolgáltatásba. A Data Integrator használatával integrációs projektek definiálhatók (ez gyakran olyan előre definiált sablonok alapján történik, amelyeket az alkalmazás fejlesztői alakítottak ki a különböző integrációknak megfelelőn). Integrációs projekteket ütemezhet ismétlődő automatikus futtatásra, vagy manuálisan is futtathatók.

A Data Integrator projektek megfelelőek a Common Data Service kötegelt integrációkhoz. Remek választást jelentenek a Dynamics 365 termékcsaládba tartozó alkalmazások közötti integrációhoz. A Microsoft például biztosít egy használatra kész Data Integrator-sablont, amelynek segítségével a Human Resources-adatok integrálhatók a Dynamics 365 Finance szolgáltatásba. További tájékoztatás az integrációs sablonról: [Integráció a Dynamics 365 Human Resources és a Dynamics 365 Finance között](hr-admin-integration-finance.md).

### <a name="power-query"></a>Power Query

A Data Integrator támogatást biztosít a [Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query) számára is (a [speciális lekérdezési funkcióján](https://docs.microsoft.com/powerapps/administrator/data-integrator#advanced-data-transformation-and-filtering) keresztül). A Power Query erőteljes, rugalmas adatszűrést és-átalakítást tesz lehetővé, többek között a kibővített M Formula nyelvet. A Power Query valószínűleg ismerős, ha már fejlesztett Power BI-jelentéseket.

## <a name="deciding-on-an-integration-technology"></a>Az integrációs technológiára vonatkozó döntés

Mivel számos különböző integrációs technológia érhető el, a használandó integrációs megközelítés kiválasztására vonatkozó döntés sokszor komoly gondolkodásra adhat okot. A Common Data Service adatlefedettségének kiérlelődésével a döntés is könnyebb lesz, mivel a Common Data Service lesz a legtöbb esetben az elsődleges adatfelület. Amíg ez meg nem valósul, vélekedhet úgy, hogy a Common Data Service még nem felel meg az igényeinek. A következő táblázat összefoglalja az integrációs technológiai lehetőségek néhány kulcsfontosságú jellemzőjét.

| Technológia/eszköz/API    | Ismétlődő integrációk                   | Szinkron/aszinkron                    | Programozott hozzáférés API-val        | Megfelelő adatkötetek                                   | Adatlefedettség                       |
|------------------------|------------------------------------------|---------------------------------------------|-------------------------------------------|------------------------------------------------------------|-------------------------------------|
| Common Data Service-entitások           | Igen, a Data Integrator vagy középrétegű megoldás használatával | Szinkron, aszinkron, kötegelt (a Data Integratorral) | Igen, a Dynamics 365 Web API-val (OData) | A használati esettől függően változik (támogatja a lapozást az interaktív használathoz) | Javítás<sup>2</sup>                       |
| DMF-entitások           | Igen, középrétegű megoldásokkal ütemezve        | Aszinkron, kötegelt                                | Igen, a DMF csomagok REST API-jával         | Magas (rekordok százezrei)                    | Magas                                |
| DMF-csomagok REST API-ja   | Igen, középrétegű megoldásokkal ütemezve        | Aszinkron, kötegelt                                | Igen                                       | Magas (rekordok százezrei)                    | Az API az összes DMF-entitást támogatja       |
| BYOD                   | Igen, a Human Resources rendszergazdája által ütemezve        | Aszinkron, kötegelt                                | Nem<sup>3</sup>                                    | Magas (rekordok százezrei)                    | Az összes DMF-entitást támogatja           |
| OData-kompatibilis entitások | Igen, középrétegű megoldás használatával                    | Szinkronizálás                                        | Igen, a Human Resources adatszolgáltatásával (OData)  | A használati esettől függően változik (támogatja a lapozást az interaktív használathoz) | Magas                                |
| Excel-bővítmény           | Nem                                       | Szinkronizálás                                        | Nem                                        | Közepes (rekordok tízezrei)                      | Támogatja az összes OData-kompatibilis entitást |
| Data Integrator        | Igen, a Data Integratorban ütemezve        | Aszinkron, kötegelt                                | Nem                                        | A használati esettől függően változik                                       | Az összes Common Data Service-entitást támogatja           |

<sup>2</sup>A Microsoft nagymértékben növeli a növekvő adatlefedettséget a Common Data Service entitások számára. A Common Data Service használatát ajánljuk, amikor a lefedettség elérhető. A Common Data Service adatlefedettsége jelenleg alacsony a DMF- és az OData-kompatibilis entitásokéhoz képest.

<sup>3</sup>Az SQL-adatbázis programkóddal érhető el.


[!INCLUDE[footer-include](../includes/footer-banner.md)]