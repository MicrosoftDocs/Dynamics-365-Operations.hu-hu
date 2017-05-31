---
title: "Elavult szolgáltatások"
description: "Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva a Dynamics 365 for Operations-ből, vagy eltávolításuk be van tervezve. Olyan funkciókat is tartalmaz, amelyek a Dynamics AX 7.0 kiadásaiban már nem szerepeltek."
author: sericks007
manager: AnnBe
ms.date: 04/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, Platform
ms.custom: 21821
ms.assetid: 31019808-4cbf-47d7-b1ba-d791db4281ae
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 6
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 46a6f054f1cc5162e19d962964eb6eeb780087a6
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="deprecated-features"></a>Elavult szolgáltatások

[!include[banner](../includes/banner.md)]


Ez a témakör azokat a funkciókat ismerteti, amelyek el lettek távolítva a Dynamics 365 for Operations-ből, vagy eltávolításuk be van tervezve. Olyan funkciókat is tartalmaz, amelyek a Dynamics AX 7.0 kiadásaiban már nem szerepeltek.

<a name="features-that-have-been-deprecated-in-dynamics-365-for-operations-1611-with-platform-update-3"></a>Olyan funkciók, amelyek elavulnak a Dynamics 365 for Operations 1611 3. platformfrissítése során
---------------------------------------------------------------------------------------------

### <a name="aeb-payment-formats-for-spain"></a>Spanyol AEB fizetési formátumok

A Consejo Superior Bancario fizetési formátumok átutalási fájlok bankhoz történő küldésére használatosak vevői és szállítói kifizetések esetén. Ezen formátumok tartalmát az Asociación Española de Banca határozza meg. A következőket fedi le: Cuaderno 19, 32, 58, 34.

|                              |                                                                          |
|------------------------------|--------------------------------------------------------------------------|
| Megszűnés oka       | A fizetési formátumok már nem használhatók.                                  |
| Felváltotta másik szolgáltatás? | Igen, az ISO20022 átutalási és beszedési formátumok Spanyolország esetében |
| Érintett modulok             | Kötelezettség és kinnlevőség                                    |

### <a name="bank-payments-transfer-for-lithuania"></a>Banki átutalásos kifizetések Litvánia esetében

A banki átutalásos kifizetések létrehozása és nyomtatása a fizetési átutalás (LT) exportformátumban történik Litvánia vonatkozásában. A litván piac 2005-ben kezdte el a LITAS egységesített elektronikus bankrendszert használni.

|                              |                                                            |
|------------------------------|------------------------------------------------------------|
| Megszűnés oka       | A fizetési formátumok már nem használhatók.                    |
| Felváltotta másik szolgáltatás? | Igen, ISO20022 átutalási fizetési formátum Litvánia esetében |
| Érintett modulok             | Kötelezettségek                                           |

### <a name="bbs-direkte-remittering-payment-formats-for-norway"></a>BBS Direkte Remittering fizetési formátumok Norvégia esetében

A BBS Direkte Remittering fizetési formátumok a következőket tartalmazzák: vevői fizetés beszedésének exportálása (beszedési megbízás) és a válaszüzenet importálása.

|                              |                                                                                                                                                                |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A fizetési formátumok már nem használhatók.                                                                                                                        |
| Felváltotta másik szolgáltatás? | A Norvégiában rendelkezésre álló, AvtaleGiro vevői fizetési formátum használható beszedési megbízási üzenetek létrehozására. A visszaigazoló üzenetek importálása a jövőbeli kiadásokban kerül bevezetésre. |
| Érintett modulok             | Kötelezettség és kinnlevőség                                                                                                                          |

### <a name="chart-of-accounts-tool-for-spain"></a>Számlatükör eszköz Spanyolország esetében

Ez az eszköz akkor használatos, ha a számlatükör esetében jelentős változtatásokra van szükség Spanyolországban. A felhasználók importálhatják az új számlatükröt Microsoft Excel vagy a szöveges formátumban, valamint importálhatják a pénzügyi kimutatásokat is.

|                              |                |
|------------------------------|----------------|
| Megszűnés oka       | Korlátozott felhasználás  |
| Felváltotta másik szolgáltatás? | Nincs             |
| Érintett modulok             | Főkönyv |

### <a name="dom80-payment-format-for-belgium"></a>Belga Dom80 fizetési formátum

Hagyományos fizetési formátum fizetés beszedéséhez (beszedési megbízási).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| Megszűnés oka       | A fizetési formátum már nem használható.                  |
| Felváltotta másik szolgáltatás? | Igen, ISO 20022 beszedési megbízási fizetési formátum Belgium esetében. |
| Érintett modulok             | Kinnlevőségek                                    |

### <a name="dtaezag-payment-formats-for-switzerland"></a>DTA/EZAG fizetési formátumok Svájc esetében

A DTA/EZAG formátumok az ESR rendszer integrált részét alkotják, mert rendelkezhetnek hivatkozási számmal. Mivel a hivatkozási számok nem kötelezők, ezért bármilyen szállítói fizetés feldolgozható ezen formátumok használatával. Ezeket a formátumokat olyan vállalatok használják, amelyeknek a „Postfinance”-től eltérő helyen van bankszámlája.

|                              |                                                              |
|------------------------------|--------------------------------------------------------------|
| Megszűnés oka       | A fizetési formátumok már nem használhatók.                      |
| Felváltotta másik szolgáltatás? | Igen, ISO20022 átutalási fizetési formátum Svájc esetében |
| Érintett modulok             | Kötelezettségek                                             |

### <a name="edifact-dirdeb-payment-format-for-austria"></a>EDIFACT-DIRDEB fizetési formátum Ausztria esetében.

EDIFACT-DIRDEB fizetési formátum fizetés beszedéséhez (beszedési megbízás).

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| Megszűnés oka       | A fizetési formátum már nem használható.                  |
| Felváltotta másik szolgáltatás? | Igen, ISO 20022 beszedési megbízási fizetési formátum Ausztria esetében |
| Érintett modulok             | Kinnlevőségek                                    |

### <a name="edivat-for-belgium"></a>EDIVAT Belgium esetében

EDIVAT a biztonságos levelezésen keresztüli elektronikus nyilatkozat elavult belga szabványa. A Microsoft Dynamics AX 2012 megtartja a "csak olvasásra" megoldást annak érdekében, hogy a régebbi adatokhoz hozzá lehessen férni.

|                              |                                      |
|------------------------------|--------------------------------------|
| Megszűnés oka       | Ez a funkció már nincs használatban. |
| Felváltotta másik szolgáltatás? | Nincs                                   |
| Érintett modulok             | Főkönyv                       |

### <a name="egiro-edifact-cremul-payment-import-format-for-norway"></a>eGiro EDIFACT CREMUL fizetési importformátum Norvégia esetében

Az eGiro az ENSZ EDIFACT CREMUL (Multiple Credit Advice Message) nemzetközi szabványon alapszik, amely a vevői kifizetések automatikus feladásához használatos. A Microsoft Dynamics AX rendszerben az eGiro egy vevői kifizetés importformátumaként van megvalósítva.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| Megszűnés oka       | A fizetési formátum már nem használható.                                                     |
| Felváltotta másik szolgáltatás? | Szám A formátum helyére ISO-20022 típusú kivonatok importformátumai kerülnek a jövőbeli kiadásokban. |
| Érintett modulok             | Kinnlevőségek                                                                       |

### <a name="external-inventory-for-poland"></a>Külső készlet Lengyelország esetében

Szállítótól beszerzés nélkül, értékesítésre átvett áruk bizonylata. A külső készleten kezelt áruk, amelyek a normál készletet nem érintik, és automatikusan eladhatóak, majd később megvásárolhatók. Ez a folyamat tényleges készletmozgást hoz létre.

|                              |                                                 |
|------------------------------|-------------------------------------------------|
| Megszűnés oka       | Másik szolgáltatás váltotta fel                     |
| Felváltotta másik szolgáltatás? | Igen, a bejövő szállítmány alapfunkciója |
| Érintett modulok             | Kötelezettségek, készletkezelés          |

### <a name="financial-reports-generator-for-eastern-europe"></a>Pénzügyi beszámolók létrehozása Kelet-Európa esetében

Egy eszköz szolgál a könyvelési és adójelentések adatgyűjtésének beállításához és az adatok XLS vagy DOC jelentéssablonba való exportálásához

|                              |                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------|
| Megszűnés oka       | Korlátozott felhasználás                                                                            |
| Felváltotta másik szolgáltatás? | Szám Az eszközt elektronikus jelentési konfigurációk fogják leváltani a jövőbeli kiadásokban. |
| Érintett modulok             | Főkönyv                                                                           |

### <a name="import-of-customer-payment-transactions-for-finland"></a>Vevői kifizetési tranzakciók importálása Finnország esetében

Kiválaszthat egy olyan importálási formátumot a finn fizetésekhez, amely a vevői kifizetési tranzakciókat importálja egy bank által biztosított külső fájlból.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| Megszűnés oka       | A fizetési formátum már nem használható.                                                     |
| Felváltotta másik szolgáltatás? | Szám A formátum helyére ISO-20022 típusú kivonatok importformátumai kerülnek a jövőbeli kiadásokban. |
| Érintett modulok             | Kinnlevőségek                                                                       |

### <a name="import-of-payment-transactions-into-a-general-ledger-journal-for-finland"></a>A Finnországra vonatkozó fizetési tranzakciók importálása a főkönyvi naplóba

Finnországra vonatkozó, specifikus formátum, amellyel könyvelési tranzakciók importálhatóak a főkönyvbe.

|                              |                                                                                           |
|------------------------------|-------------------------------------------------------------------------------------------|
| Megszűnés oka       | A fizetési formátum már nem használható.                                                     |
| Felváltotta másik szolgáltatás? | Szám A formátum helyére ISO-20022 típusú kivonatok importformátumai kerülnek a jövőbeli kiadásokban. |
| Érintett modulok             | Kinnlevőségek                                                                       |

### <a name="integration-with-isabel-synchronized-cis-for-belgium"></a>Integráció az Isabel-hez szinkronizált (CIS) rendszerekkel Belgium esetében

Az Isabel az elektronikus banki ügyintézés európai rendszere, Belgiumban de facto szabványnak minősül.

|                              |                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Az Isabel-klienssel való integráció már nincs forgalomban.                                                                |
| Felváltotta másik szolgáltatás? | Szám A már nem használt fizetési formátumok helyébe ISO20022 átutalási fizetési formátum lépett Belgium esetében. |
| Érintett modulok             | Kötelezettségek                                                                                                     |

### <a name="modifications-in-the-chart-of-accounts-and-accounting-rules-for-spain"></a>A számlatükör és a számviteli szabályok módosulása Spanyolország esetében

Ez a funkció a számlatükör és a számviteli szabályok változásaihoz használatos Spanyolországban esetében. Leképezi a számlákat, hogy segítsen a régi számlatükröt az új számlatükörré alakítani, és összehasonlítja az előző pénzügyi évet az új pénzügyi évvel még akkor is, ha azokhoz eltérő számlaszámokat rendeltek.

|                              |                |
|------------------------------|----------------|
| Megszűnés oka       | Korlátozott felhasználás  |
| Felváltotta másik szolgáltatás? | Nincs             |
| Érintett modulok             | Főkönyv |

### <a name="pagamento-fornittori-vendor-payment-format"></a>Pagamento Fornittori szállítói fizetési formátum

Hagyományos olasz fizetési formátum átutalásokhoz.

|                              |                                                        |
|------------------------------|--------------------------------------------------------|
| Megszűnés oka       | A fizetési formátum már nem használható.                  |
| Felváltotta másik szolgáltatás? | Igen, ISO20022 átutalási fizetési formátum Olaszország esetében |
| Érintett modulok             | Kötelezettségek                                       |

### <a name="payment-export-formats-for-estonia"></a>Kifizetésexportálás formátuma Észtország esetében

Banki fizetés exportálása a Telehansa és Teleservice formátumot használja.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| Megszűnés oka       | A fizetési formátumok már nem használhatók.                  |
| Felváltotta másik szolgáltatás? | Igen, ISO20022 átutalási fizetési formátum Észtország esetében |
| Érintett modulok             | Kötelezettségek                                         |

### <a name="payment-file-archive-for-norway"></a>Fizetési fájlarchívum Norvégia esetében

Amikor fizetési fájlok jönnek létre, a fájlarchívum automatikusan archivál minden létrehozott fájlt, még akkor is fájlokat korábban írták vagy olvasták.

|                              |                                                                    |
|------------------------------|--------------------------------------------------------------------|
| Megszűnés oka       | Másik szolgáltatás váltotta fel                                        |
| Felváltotta másik szolgáltatás? | Igen. Elektronikus jelentéskészítési archivált feladatok                            |
| Érintett modulok             | Kötelezettségek, kinnlevőségek, a szervezet felügyelete |

### <a name="payment-import-formats-for-estonia"></a>Kifizetésimportálás formátuma Észtország esetében

Banki fizetés importálása a TeleTeenus formátumot használja.

|                              |                                                                                            |
|------------------------------|--------------------------------------------------------------------------------------------|
| Megszűnés oka       | A fizetési formátumok már nem használhatók.                                                    |
| Felváltotta másik szolgáltatás? | Szám A formátumok helyére ISO-20022 típusú kivonatok importformátumai kerülnek a jövőbeli kiadásokban. |
| Érintett modulok             | Kinnlevőségek                                                                        |

### <a name="performance-management-goal-workflow"></a>Teljesítménymenedzsment, célok munkafolyamata

A teljesítménymenedzsment a célok kezelését tartalmazza, és integrálja a teljeseítményellenőrzést.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A teljesítménymenedzsment át lett tervezve, és a célok oldalainak száma csökkent a folyamat egyszerűsítése érdekében.                 |
| Felváltotta másik szolgáltatás? | Szám A célok láthatók a vezetők számára az Vezetők önkiszolgáló portálján; ezeket a vezető módosíthatja és megtekintheti. |
| Érintett modulok             | Emberierőforrás-menedzselés                                                                                                 |

### <a name="postgirot-and-postgirot-utland-payment-formats-for-sweden"></a>PostGirot és a Postgirot Utland fizetési formátumok Svédország esetében

PostGirot és a Postgirot Utland fizetési formátumok Svédország esetében.

|                              |                                                         |
|------------------------------|---------------------------------------------------------|
| Megszűnés oka       | A fizetési formátumok már nem használhatók.                 |
| Felváltotta másik szolgáltatás? | Igen, ISO20022 átutalási fizetési formátum Svédország esetében |
| Érintett modulok             | Kötelezettségek                                        |

### <a name="radio-frequency-identifier"></a>Rádiófrekvenciás azonosító

A rádiófrekvenciás azonosítás (Radio Frequency Identification – RFID) egy olyan adatgyűjtési technológia, amely az azonosítási adatok tárolásához elektronikus címkéket használ, az azonosítási adatok beolvasásához pedig nem közvetlen rálátású olvasót.

|                              |                                               |
|------------------------------|-----------------------------------------------|
| Megszűnés oka       | Alacsony vevői használat és korlátozott szolgáltatáskészlet. |
| Felváltotta másik szolgáltatás? | Nincs                                            |
| Érintett modulok             | Készletgazdálkodás                          |

### <a name="report-about-state-invoices-numbering-for-latvia"></a>Állami számlák számozására vonatkozó jelentés Lettország esetében

A lett jogszabályok szigorú szabályokat írnak elő az értékesítési számlák számozására vonatkozóan. A funkciók segítségével egyedi számokat lehet az értékesítési számlákhoz rendelni, a felhasználó vagy felhasználói csoport alapján. Ezután lehet létrehozni egy jelentést vagy egy XML-fájlt. A felhasznált számlaszámokról jelentést is lehet nyomtatni.

|                              |                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Az állami számlák számozását már nem kell fenntartani. A felhasznált számlaszámokra vonatkozó jelentésre már nincs szükség. |
| Felváltotta másik szolgáltatás? | Nincs                                                                                                                       |
| Érintett modulok             | Kinnlevőségek                                                                                                      |

### <a name="set-up-the-names-of-the-manager-and-general-accountant-of-a-company-for-lithuania"></a>Valamely vállalat vezetője és főkönyvelője nevének beállítása Litvánia esetében

A vállalat vezetőjének és főkönyvelőjének nevét a vállalati adatok között lehet megadni, és fel lehet használni különböző, helyi nyomtatott jelentésekben.

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| Megszűnés oka       | Másik szolgáltatás váltotta fel                                     |
| Felváltotta másik szolgáltatás? | Igen, a tisztviselők beállítása ugyanerre a célra használható.   |
| Érintett modulok             | Kötelezettségek, Kinnlevőségek, Készpénz- és bankkezelés |

### <a name="telepay-payment-formats-for-norway"></a>TelePay fizetési formátumok Norvégia esetében

TelePay fizetési formátumok közé tartozik a szállítói fizetés exportálása (átutalás) és a vevői kifizetési gyűjtemény (beszedési megbízás).

|                              |                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A fizetési formátumok már nem használhatók.                                                        |
| Felváltotta másik szolgáltatás? | Igen, ISO20022 átutalási fizetési formátum és AvtaleGiro vevői kifizetési formátum Norvégia esetében |
| Érintett modulok             | Kötelezettség és kinnlevőség                                                          |

### <a name="vendor-payment-export-formats-for-finland"></a>Szállítói fizetésexportálási formátumok Finnország esetében

Finnországban két formátum érhető el fizetések exportálásához. LM02 (FI) belföldi fizetésekhez használható, az LUM2 (FI) pedig külföldi fizetésekhez.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| Megszűnés oka       | A fizetési formátumok már nem használhatók.                  |
| Felváltotta másik szolgáltatás? | Igen, ISO20022 átutalási fizetési formátum Finnország esetében |
| Érintett modulok             | Kötelezettségek                                         |

### <a name="workflow-for-creating-goals"></a>Célok létrehozásának munkafolyamata

A munkavállalók céljai létrehozásának kezelésére vonatkozó munkafolyamat a számos olyan munkafolyamat egyike, amely rendelkezésre állt a teljesítménykezelési folyamat koordinálásának elősegítésére.

|                              |                                                                                                                                                                                                                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A teljesítménymenedzsment teljesen átalakult a Microsoft Dynamics 365 for Operations alatt.                                                                                                                                                                                                                                        |
| Felváltotta másik szolgáltatás? | Az átalakított teljesítménymendzsment funkciója segítségével jobban lehet felügyelni a célok tartalmát, az előrehaladás nyomon követéséhez használt méréseket és a kiegészítő dokumentumok csatolását. A célok sablonként tárolhatók, és ezután újra felhasználhatók. Ezen funkció segítségével gyorsabban beállíthatók további célok az alkalmazottak számára. |
| Érintett modulok             | Emberierőforrás-menedzselés                                                                                                                                                                                                                                                                                                               |

## <a name="features-deprecated-in-dynamics-ax-70-releases"></a>A Dynamics AX 7.0 kiadásokban elavult funkciók
### <a name="ability-to-cancel-changes-to-a-vendor-invoice"></a>Szállítói számla módosításainak érvénytelenítésére vonatkozó képesség

|                              |                         |
|------------------------------|-------------------------|
| Megszűnés oka       | Teljesítménynövekedés. |
| Felváltotta másik szolgáltatás? | Szám                      |
| Érintett modulok             | Kötelezettségek        |

### <a name="aif-axd-and-axbc-integrations"></a>AIF, AxD és AxBC integrációja

Az Alkalmazásintegrációs keretrendszerben (AIF-ben) adatok cserélhetőek ki külső rendszerekkel, szolgáltatásként kitett üzleti logikán keresztül. A Dynamics AX dokumentumokon és .NET Business Connector-on (AxBC) alapuló szolgáltatásokat tartalmaz. Dokumentumok XML használatával hozhatóak létre. Az XML által tartalmazott fejlécadatok hozzáadásával *üzenet* hozható létre, amely a Dynamics AX rendszerbe vagy rendszerből átvihető. Dokumentumok például az értékesítési rendelések és a beszerzési rendelések. Azonban szinte minden entitást (például vevőt) képviselhet dokumentum. A dokumentumokon alapuló szolgáltatások az **Axd &lt;*Dokumentum*&gt;** osztályokat használják.

|                              |                                                                                                                                                                                                          |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Az AIF és az AxD-k architektúráját nem sikerült felhőszolgáltatáshoz méretezni. A tömeges importálás során teljesítményproblémák léptek fel.                                                                               |
| Felváltotta másik szolgáltatás? | A Dynamics AX jelenlegi verziójában ezt a szolgáltatást felváltotta az Adatimportálási és -exportálási keretrendszer, amely támogatja az ismétlődő tömeges importálást/exportálást. AxBC esetén a tényleges táblák használatát javasoljuk. |
| Érintett modulok             | AxD-k, AxBC-k és AIF                                                                                                                                                                                     |

### <a name="boms-without-bom-versions"></a>Anyagjegyzékek Anyagjegyzék-verziók nélkül

Korábban az **Anyagjegyzék-verziók** konfigurációs kulcs letiltásakor, az anyagjegyzék-verziók (BOM) minden képernyőn rejtett állapotba kerültek, és a rendszer kötelezővé tette a kiadott termékek és anyagjegyzékek közti 1:1 arányú kapcsolatot. A Dynamics AX jelenlegi verziójában az **Anyagjegyzék-verziók** konfigurációs kulcsot nem lehet letiltani.

|                              |                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------|
| Megszűnés oka       | Anyagjegyzék-verziók konfigurációs kulcsokkal való vezérlése nem méretezhető felhő környezetre. |
| Felváltotta másik szolgáltatás? | Szám                                                                                      |
| Érintett modulok             | Termékinformációk kezelése, Készletkezelés                                    |

### <a name="brazilian-bordero"></a>Brazil borderó

Egyedi fizetési mód brazil vállalatok esetében

|                              |                                                                                                       |
|------------------------------|-------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A Brazil borderó fizetési mód támogatása már nem része a brazil honosításnak |
| Felváltotta másik szolgáltatás? | Nincs                                                                                                    |
| Érintett modulok             | Kötelezettségek                                                                                      |

### <a name="brazilian-sintegra-statement"></a>Brazil Sintegra kivonat

Szövetségi adókimutatás az ICMS adó esetében

|                              |                                                                                                                       |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Ez a kimutatás már nem alkalmazható néhány brazil államban.                                                     |
| Felváltotta másik szolgáltatás? | Szám A felhasználók általános elektronikus jelentési eszközt használhatnak a kimutatás beállításához, ha arra bizonyos helyzetekben szükség van. |
| Érintett modulok             | Pénzügyi könyvek                                                                                                          |

### <a name="brazilian-scan-contingency-mode-for-nf-e"></a>Brazil SCAN készenléti mód az NF-e esetében

A (SCAN) készenléti környezet a Nota Fiscal eletrônica (NF-e) állapotának előállítására, exportálására és importálására szolgál, amikor nem érhető el a Secretaria da Fazenda (SEFAZ) környezet.

|                              |                                                                             |
|------------------------------|-----------------------------------------------------------------------------|
| Megszűnés oka       | Ez a készenléti módszer már nem alkalmazható minden brazil államban |
| Felváltotta másik szolgáltatás? | Nincs                                                                          |
| Érintett modulok             | Kinnlevőségek                                                         |

### <a name="business-analyzer"></a>Business Analyzer

Ez a mobilalkalmazás lehetővé teszi a felhasználók számára a kulcsfontosságú üzleti mutatók áttekintését.

|                              |                                                                                                                                                               |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Ezt a szolgáltatást egy másik szolgáltatás váltotta fel.                                                                                                      |
| Felváltotta másik szolgáltatás? | A Microsoft Power BI Pénzügyi teljesítményfigyelő tartalmi csomagja magába foglalja a Business Analyzer alkalmazásban korábban elérhető kulcsfontosságú üzleti mutatókat. |
| Érintett modulok             | Főkönyv                                                                                                                                                |

### <a name="business-statistics"></a>Üzleti statisztikák

Üzleti statisztikai lekérdezések beállítása, amelyek segítségével elemezhető a szervezet teljesítménye.

|                              |                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------|
| Megszűnés oka       | Üzleti intelligencia (BI) elavult megközelítése, alacsony vevői használat és a korlátozott szolgáltatási kör. |
| Felváltotta másik szolgáltatás? | Új Üzleti Intelligencia megoldások a Dynamics AX jelenlegi verziójában.                                      |
| Érintett modulok             | Beszerzés és forrás, Kötelezettségek, Értékesítés és marketing, Kinnlevőségek         |

### <a name="change-document-date-function-in-invoice-approval-journal"></a>A Számla-jóváhagyási naplóban található Dokumentum dátumának módosítása funkció

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| Megszűnés oka       | Alacsony használat                                                               |
| Felváltotta másik szolgáltatás? | Igen. A feladott szállítói tranzakció dokumentumdátuma módosítható. |
| Érintett modulok             | Kötelezettségek                                                        |

### <a name="clieop03-payment-format-for-the-netherlands"></a>A holland ClieOp03 fizetési formátum

|                              |                                                                                                            |
|------------------------------|------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A formátum már nem alkalmazható Hollandiában, mivel azt felváltotta a SEPA funkció. |
| Felváltotta másik szolgáltatás? | SEPA exportkifizetések                                                                                       |
| Érintett modulok             | Mind                                                                                                        |

### <a name="compliance-center"></a>Megfelelési Központ

A Megfelelési Központ egy Enterprise Portal webhely volt, amely a Sarbanes-Oxley törvénnyel kapcsolatos megfelelési kezdeményezések dokumentációs követelményeinek kezelésére szolgált.

|                              |                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Vevői használat hiánya. A Microsoft SharePoint magában foglalja ugyanazt a képességet, ami korábban a Megfelelési Központban volt elérhető. |
| Felváltotta másik szolgáltatás? | Szám                                                                                                                     |
| Érintett modulok             | Megfelelés és belső ellenőrzés                                                                                       |

### <a name="connector-for-microsoft-dynamics"></a>Connector for Microsoft Dynamics

Ezzel az eszközzel integrálták a Microsoft Dynamics CRM rendszerből származó kulcsadatokat a Microsoft Dynamics ERP alkalmazásokba.

|                              |                                                          |
|------------------------------|----------------------------------------------------------|
| Megszűnés oka       | Ezt a szolgáltatást egy másik szolgáltatás váltotta fel. |
| Felváltotta másik szolgáltatás? | Dynamics Integrator                                      |
| Érintett modulok             | Connector for Microsoft Dynamics                         |

### <a name="container-unit-and-multi-dimension-on-hand"></a>Tárolóegység és a készleten lévő több dimenzió

|                              |                                                                                                                                                                 |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Máshol már meglévő funkció                                                                                                                                         |
| Felváltotta másik szolgáltatás? | Igen. Az AX 2012 óta, ezt a funkciót az összesített kötegrendelések szolgáltatáskészlet váltotta fel. Ez a szolgáltatáskészlet tartalmazza az egyesített készletnézetet. |
| Érintett modulok             | Termékinformációk kezelése, Gyártásvezérlés, Készletkezelés, Értékesítés és marketing                                                                   |

### <a name="cue-group-metadata"></a>Kötegcsoport-metaadatok

|                              |                                                                                                                                                                                                                               |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Kötegcsoportok használatával korábban egy vagy több Köteget lehetett megjeleníteni az Adatterületen. A feltöltés korlátozottsága mellett teljesítményproblémák is felléptek, mivel egy szülőűrlapon történő rekordváltoztatás a Kötegcsoport minden egyes Kötegéhez létrehozott egy lekérdezést. |
| Felváltotta másik szolgáltatás? | Szám                                                                                                                                                                                                                            |
| Érintett modulok             | Mind                                                                                                                                                                                                                           |

### <a name="cue-metadata"></a>Köteg-metaadatok

|                              |                                                                                                                                                                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A köteg-metaadatok információk számlálására vagy összesítésére korlátozódtak.                                                                                                                                                                                   |
| Felváltotta másik szolgáltatás? | Annak érdekében, hogy a modellezéshez nagyobb rugalmasságot biztosítsunk, bevezettük a csempe-metaadatokat. Modellezhet például aktuális számlálókat, navigációt, valamint fő teljesítménymutatókat (KPI-ket). A Köteg-metaadatokat közvetlenül helyettesítik a Csempeszámláló metaadatai. |
| Érintett modulok             | Mind                                                                                                                                                                                                                                     |

### <a name="danish-check-format"></a>Dán csekkformátum

|                              |                                                                                                                         |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A dán csekkformátum elrendezésének támogatása megszűnt, a jelentést eltávolítottuk a dán honosításból. |
| Felváltotta másik szolgáltatás? | Szám                                                                                                                      |
| Érintett modulok             | Mind                                                                                                                     |

### <a name="data-partitions"></a>Adatpartíciók

Az adatpartíciók az adatok logikus elkülönítését biztosítják a Microsoft Dynamics AX adatbázisában.

|                              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Az adatpartíciókat a Microsoft Dynamics AX 2012 R2 változatában vezették be adatok elkülönítéséhez. Általános esetben a vállalat leányvállalatokkal rendelkezik, és egy leányvállalat adatait nem láthatja egy másik leányvállalat, annak ellenére, hogy mindkét leányvállalatot azonos informatikai részleg kezeli. Azonban további parancsfájlok és kezelési többletköltség voltak szükségesek új partíciók létrehozására és azok adatokkal való feltöltésére, és a partíció adatainak biztonsági mentésére. A felhőben, ahol hozzáférésünk van platformhoz mint szolgáltatáshoz (PaaS), adatbázis-szolgáltatáshoz (Windows Azure a Microsoft SQL adatbázis), sokkal hatékonyabb az adatbázist elkülönítési tárolóként használni, mint a elkülönítést végezni a programon belül. Függetlenül attól, hogy adatpartíció szükségesek leányvállalatoknak, több bérlőnek vagy csak mérlegelésre, úgy véljük, hogy az esetek jobban kezelhetők több adatbázissal vagy több Dynamics AX példánnyal. |
| Felváltotta másik szolgáltatás? | Az adatpartíciókat több adatbázisra vagy Dynamics AX példányokra cserélik támogatással vagy egy jövőbeli programverzióban.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Érintett modulok             | Mind                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |

### <a name="delimitation"></a>Elválasztás

|                              |                                        |
|------------------------------|----------------------------------------|
| Megszűnés oka       | A funkció hasznossága nem mutatható ki. |
| Felváltotta másik szolgáltatás? | Szám                                     |
| Érintett modulok             | Munkaidő és jelenlét                    |

### <a name="desktop-client"></a>Asztali ügyfél

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A Dynamics AX ügyfél felhasználói felületét a több platformon és eszközön való jobb felhasználhatóság érdekében újraterveztük.                      |
| Felváltotta másik szolgáltatás? | Az új webes ügyfél az asztali képernyő metaadatain és programozási modelljén alapul, amelyeket egy multimédiás webes platform szolgáltatása érdekében módosítottunk. |
| Érintett modulok             | Mind                                                                                                                                    |

### <a name="direct-database-connection"></a>Közvetlen adatbázis-kapcsolat

A Dynamics AX 2012 R3 rendszerben a Retail Modern pénztár az Enterprise POS rendszerhez hasonló módon, közvetlenül tudott kapcsolódni a csatorna-adatbázishoz. Ez ráadás volt a Retail Modern pénztár Retail Server kiszolgálón keresztül kommunikáló szokásos kommunikációs módja mellett.  

|                              |                                                                                         |
|------------------------------|-----------------------------------------------------------------------------------------|
| Megszűnés oka       | A közvetlen adatbázis-kapcsolathoz alacsonyabb szintű biztonsági protokollok voltak szükségesek, és elsődleges használati célja a legmagasabb szintű teljesítmény elérése volt. A Dynamics 365 for Operations teljesítménybeli és biztonsági fejlesztései következtében ez a funkció több problémát okoz, mint amennyit megold. |
| Felváltotta másik szolgáltatás? | Szám Jelenleg csak a szabványos Retail Server által biztosított kommunikáció támogatott.    |
| Érintett modulok             | Csatorna-adatbázis/Retail Modern pénztár                                    |

### <a name="dutch-swift-mt940"></a>Holland SWIFT MT940

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A honosított funkció helyett már az általános funkció használatos.                                                                                                                                                                 |
| Felváltotta másik szolgáltatás? | Igen, ezt a funkciót a Továbbfejlesztett banki egyeztetés funkció váltotta fel. Továbbá, a camt.053 ISO20022 számlakivonat-import beépítése is tervbe van véve az Főkönyvi naplóra vonatkozóan a következő Dynamics AX frissítésben. |
| Érintett modulok             | Mind                                                                                                                                                                                                                                   |

### <a name="ebilanz-xbrl-for-germany"></a>eBilanz (XBRL, Németország)

Ez a funkció az eXtensible Business Reporting Language (XBRL) kimenetet biztosítja, amely kifejezetten a német eBilanz rendszertan részére lett szánva.

|                              |                                                                                                                                                                        |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Vevői használat hiánya.                                                                                                                                                 |
| Felváltotta másik szolgáltatás? | Ezt a szolgáltatást nem váltotta fel másik, azonban számos speciális, széles körű XBRL funkciókat magában foglaló XBRL csomag érthető el a német piac számára. |
| Érintett modulok             | Management Reporter                                                                                                                                                    |

### <a name="enterprise-portal-client"></a>Enterprise Portal-ügyfél

|                              |                                                                                                                                        |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Egy együgyfeles platform biztosított.                                                                                            |
| Felváltotta másik szolgáltatás? | Az új webes ügyfél az asztali képernyő metaadatain és programozási modelljén alapul, amelyeket egy multimédiás webes platform szolgáltatása érdekében módosítottunk. |
| Érintett modulok             | Mind                                                                                                                                    |

### <a name="environmental-sustainability"></a>Környezeti fenntarthatóság

|                              |                                                    |
|------------------------------|----------------------------------------------------|
| Megszűnés oka       | Alacsony vevői használat és korlátozott szolgáltatáskészlet.       |
| Felváltotta másik szolgáltatás? | Szám                                                 |
| Érintett modulok             | Megfelelés és belső ellenőrzés, Kötelezettségek |

### <a name="form-activex-and-managed-host-controls"></a>ActiveX és Felügyelt Állomás vezérlők

|                              |                                                                                                                                                                                               |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Az ActiveX és Felügyelt Állomás vezérlők a már megszűnt asztali ügyfélen alapulnak.                                                                                                             |
| Felváltotta másik szolgáltatás? | A bővíthető vezérlési keretrendszer támogatja új, HTML-, CSS- és JavaScript-alapú vezérlések kiépítését, továbbá Microsoft Visual Studio Tooling környezetben elsőrangú vezérlő. |
| Érintett modulok             | Mind                                                                                                                                                                                           |

### <a name="generate-prenotes-by-using-a-batch"></a>Ellenőrző tranzakciók létrehozása a köteg használatával

Előjegyzés létrehozás nem lehetséges köteg használatával, azonban a felhasználó által továbbra is végrehajtható.

|                              |                                                                                                        |
|------------------------------|--------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Nem létezik olyan képernyő, amely a köteg használatával létrehozott előjegyzési fájl tárolására és megjelenítésére alkalmas lenne. |
| Felváltotta másik szolgáltatás? | Előjegyzések továbbra is létrehozhatók, ekkor a fájl mentésének helyét a felhasználó állíthatja be.   |
| Érintett modulok             | Kötelezettségek, Kinnlevőségek, Készpénz- és bankkezelés                                        |

### <a name="german-dtaus-payment-export-and-account-statement-import-totals-and-transactions"></a>Német DTAUS kifizetési export és számlakivonat-import (összegek és tranzakciók)

|                              |                                                                                                                                                                                                                                                                                                |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A formátum már nem alkalmazható Németországban, mivel azt felváltotta a SEPA funkció.                                                                                                                                                                 |
| Felváltotta másik szolgáltatás? | Igen, ez a funkció le lett cserélve a SEPA kifizetési export és a továbbfejlesztett banki egyeztetés funkciókra a számlakivontok importálásához. Továbbá, a camt.053 ISO20022 számlakivonat-import beépítése is tervbe van véve az Főkönyvi naplóra vonatkozóan a következő Dynamics AX frissítésben. |
| Érintett modulok             | Mind                                                                                                                                                                                                                                                                                            |

### <a name="german-dtazv-payment-format"></a>Német DTAZV fizetési formátum

|                              |                                                                                                    |
|------------------------------|----------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A formátum már nem alkalmazható Németországban, mivel azt felváltotta a SEPA funkció. |
| Felváltotta másik szolgáltatás? | SEPA exportkifizetések                                                                               |
| Érintett modulok             | Mind                                                                                                |

### <a name="german-mt940-import"></a>Német MT940 importálása

|                              |                                                                                                                                                                                                                                       |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A honosított funkció helyett már az általános funkció használatos.                                                                                                                                                                 |
| Felváltotta másik szolgáltatás? | Igen, ezt a funkciót a Továbbfejlesztett banki egyeztetés funkció váltotta fel. Továbbá, a camt.053 ISO20022 számlakivonat-import beépítése is tervbe van véve az Főkönyvi naplóra vonatkozóan a következő Dynamics AX frissítésben. |
| Érintett modulok             | Mind                                                                                                                                                                                                                                   |

### <a name="german-xml-eu-sales-list"></a>Német XML-formátumú EU Értékesítési lista

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A Német EU Értékesítési Lista jelentés XML-formátuma, már nem támogatott. Csak az ELMA5 szövegfájl formátumban lehet a Német Adóhivatal számára jelenteni az EU értékesítési lista jelentést. |
| Felváltotta másik szolgáltatás? | Szám                                                                                                                                                                                 |
| Érintett modulok             | Adó                                                                                                                                                                                |

### <a name="gl-ssrs-reports"></a>GL SSRS-jelentések

A következő menüpontokat tartalmazó jelentések eltávolításra kerültek: **Összegző főkönyvi kivonat**, **Részletes főkönyvi kivonat**, **Számlatükör**, **Könyvvizsgálati ellenőrzés**, **Egyenlegek** és **Egyenleglista**.

|                              |                                                                                                                                              |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A Microsoft SQL Server Reporting Services (SSRS) pénzügyi jelentéseket felváltották a Felügyeleti jelentéskészítő funkciói és az alapértelmezett jelentések. |
| Felváltotta másik szolgáltatás? | Felügyeleti jelentéskészítő (a Dynamics AX jelenlegi verziójában **Pénzügyi jelentéskészítés** megjelöléssel)                                                  |
| Érintett modulok             | Főkönyv                                                                                                                               |

### <a name="infopart-and-formpart-metadata"></a>InfoPart és FormPart metaadatai

|                              |                                                                                                                                                                                                                                |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Az InfoPart és FormPart metaadatok két különböző ügyfél számára engedélyezték Adatterületek létrehozását.                                                                                                                                    |
| Felváltotta másik szolgáltatás? | Fejlesztés után az InfoPart metaadatokat, amelyek egy egyszerűsített képernyődefiníciót adtak meg, Képernyővé alakítottuk. Fejlesztés után a FormPart metaadatokat, amelyek egy Képernyőre hivatkoztak, közvetlenebb hivatkozással váltottuk fel. |
| Érintett modulok             | Mind                                                                                                                                                                                                                            |

### <a name="main-account-list-page"></a>Fő számla listaoldal

A jogi személy számláinak listája és kapcsolódó egyenleginformációk

|                              |                                                                                                                                                                                    |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Az egyenleginformációk elérhetőek a **Főkönyvi kivonat** listaoldalon, számla és dimenzió szerint.                                                                                      |
| Felváltotta másik szolgáltatás? | A **Fő számlák** ugyanazt a számlalistát tartalmazza, amit korábban a **Fő számla** listaoldal. A **Fő számlák** rácsnézetével egy még kisebb, rácsszerű megjelenítés is elérhető. |
| Érintett modulok             | Főkönyv                                                                                                                                                                     |

### <a name="malaysia-and-singapore-bank-cash-flow-report"></a>Malajziai és szingapúri banki pénzforgalmi jelentés

Ez a szolgáltatás olyan pénzforgalmi jelentés nyomtatását tette lehetővé a felhasználó számára, amelyen megjelentek a kiválasztott bankszámlák megadott dátumtartományához kapcsolódó tranzakciók, illetve a pénzbeáramlások és a pénzkiáramlások részletei.

|                              |                                                                         |
|------------------------------|-------------------------------------------------------------------------|
| Megszűnés oka       | Ugyanezek az adatok a Banki tranzakció lekérdezéséből is beszerezhetőek. |
| Felváltotta másik szolgáltatás? | A Banki tranzakció lekérdezése                                            |
| Érintett modulok             | Készpénz- és bankkezelés                                                |

### <a name="mexican-cfd-electronic-invoice"></a>Mexikói CFD elektronikus számla

Ez a funkció lehetővé tette a CFD módszerrel történő mexikói elektronikus számlák létrehozását, abban az esetben ha vállalat írja alá a számlát, valamint kérvényezi a kapcsolódó állami engedélyeket. Ez a szolgáltatás egy olyan havi jelentést is magában foglal, amely a periódusban kiadott összes elektronikus számlát tartalmazza.

|                              |                                                                                                                                                                                                                                                                                                                                                                                                           |
|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A módszer már nem alkalmazható. Az adóhatóságok beszüntettették az elektronikus számlák CFD módszerrel való létrehozását. Ennek helyét a CFDI (Comprobante Fiscal Digital a través de Internet) módszer vette át, amelynek megfelelően egy külső szolgáltató (PAC) ír alá. A havi jelentést eltávolítottuk, a felhasználók egy lekérdezési lehetőség segítségével kérhetnek le előzménytranzakciókat. |
| Felváltotta másik szolgáltatás? | Szám                                                                                                                                                                                                                                                                                                                                                                                                        |
| Érintett modulok             | Kinnlevőségek, Projekt                                                                                                                                                                                                                                                                                                                                                                              |

### <a name="mexico-realized-and-unrealized-vat"></a>Mexikói realizált és nem realizált áfa

A Microsoft Dynamics AX 2012 a nem realizált áfát a Mexikó-specifikus „nem realizált adó” funkció használatával kezelte.

|                              |                                                                                                                     |
|------------------------------|---------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Máshol már meglévő funkció                                                                                             |
| Felváltotta másik szolgáltatás? | Igen, ezt a funkciót felváltotta az alapból biztosított standard feltételes áfa funkció. |
| Érintett modulok             | Adó                                                                                                                 |

### <a name="microsoft-outlook-integration"></a>Microsoft Outlook-integráció

|                              |                                                                                |
|------------------------------|--------------------------------------------------------------------------------|
| Megszűnés oka       | Ezt a funkciót a Microsoft Exchange Server integrációja váltotta fel. |
| Felváltotta másik szolgáltatás? | Igen                                                                            |
| Érintett modulok             | Értékesítés és marketing                                                            |

### <a name="payroll-information-in-human-resources"></a>Bérlistaadatok az Emberi Erőforrásokban

Emberi Erőforrások Bérlistaadatai

|                              |                                                                                                                                                                                                                                                                                                                              |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Ezt a funkciót az alapvető Bérlista és az Emberi Erőforrások lapokok váltotta fel.                                                                                                                                                                                                                                              |
| Felváltotta másik szolgáltatás? | A **Juttatások** és a **Bevételek** oldalakon, valamint az egyéb kapcsolódó, korábban az amerikai Bérszámfejtésben levő oldalakon újrakonfigurálást végeztünk, így ezek most az Emberi erőforrások alapkonfiguráció részei, ezért a külső bérlisták feldolgozását segítik. Ez a funkció a **Humán Erőforrások 1** &gt; **Bérlista**-konfigurációs kulcs használatával érhető el. |
| Érintett modulok             | Emberi Erőforrások, Bérlista                                                                                                                                                                                                                                                                                                     |

### <a name="private-blocking-of-inventory-and-warehouse-management-journals"></a>Készlet- és raktárkezelési naplók személyes zárolása

A készlet- és raktárnaplók már nem támogatják naplók megjelölését egy kiválasztott felhasználó személyes tartalmaként. A naplók zárolásának folyamata csak felhasználócsoportok személyes tartalmaként, illetve szerkesztés alatt támogatott.

|                              |                                        |
|------------------------------|----------------------------------------|
| Megszűnés oka       | A funkció hasznossága nem mutatható ki. |
| Felváltotta másik szolgáltatás? | Szám                                     |
| Érintett modulok             | Készletgazdálkodás                   |

### <a name="product-builder"></a>Termékszerkesztő

A Termékszerkesztő használatával korábban értékesítési rendelésekből, beszerzési rendelésekből, termelési rendelésekből, értékesítési ajánlatokból projektajánlatokból vagy cikkszükségletekből származó cikkek dinamikus konfigurálására volt lehetőség. Egy modellezési változókkal rendelkező termékmodell alapján a felhasználó ki tudta választani a vevői követelményeknek megfelelő értékeket, valamint létre tudott hozni egy egyedi, anyagjegyzékkel és útvonallal rendelkező termékváltozatot.

|                              |                                                                                                                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A Termékszerkesztő a végfelhasználók számára X++ kódot jelenített meg, a Dynamics AX jelenlegi verziójában nem támogatott. Az átfedő, nagy terjedelmű kódbázisok ismétlődő karbantartásainak elkerülése érdekében eltávolításra került. |
| Felváltotta másik szolgáltatás? | Termékkonfiguráció                                                                                                                                                                                   |
| Érintett modulok             | Termékinformációk kezelése, Értékesítés és marketing                                                                                                                                                     |

### <a name="rename-product-dimension"></a>Termékdimenzió átnevezése

Ez a szolgáltatás lehetővé tette a három alap termékdimenzió egyikének (méret, szín vagy stílus) átnevezését egy olyan névre, amely jobban megfelel az üzleti követelményeknek. Az átnevezés kiterjedt minden olyan címkére, ahol megjelent a termékdimenzió neve.

|                              |                                                                               |
|------------------------------|-------------------------------------------------------------------------------|
| Megszűnés oka       | A Dynamics AX jelenlegi verziója nem támogatja címkék módosítását futtatás alatt. |
| Felváltotta másik szolgáltatás? | Nincs                                                                            |
| Érintett modulok             | Termékinformációk kezelése                                                |

### <a name="retail-server-connectivity-using-http"></a>Retail Server kapcsolat ellenőrzése HTTP segítségével

A Dynamics AX 2012 R3 rendszerben a Retail Server a HTTP-kommunikáció (nem védett) használatával működött. Ez a szabványos HTTPS-t használó szokásos kommunikáció mellett működött.

|                              |                                                                               |
|------------------------------|-------------------------------------------------------------------------------|
| Megszűnés oka       | Új biztonsági óvintézkedések következményeképpen kizárólag a TLS 1.2 (vagy az újabb, ha rendelkezésre áll) protokollt használó biztonságos kommunikáció támogatott. Az önkiszolgáló telepítő automatikusan konfigurálja a számítógépet ehhez a kommunikációs módhoz. |
| Felváltotta másik szolgáltatás? | Szám Jelenleg csak a szabványos HTTPS által biztosított kommunikáció támogatott.                                                                           |
| Érintett modulok             | Kiskereskedelmi kiszolgáló                                                |

### <a name="role-center-pages"></a>Szerepkör főoldalak lapjai

|                              |                                                                                                                                                                          |
|------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A Szerepkör főoldalak lapjai a már megszűnt Enterprise Portal platformra épültek, amelynek helyét a Dynamics AX jelenlegi verziójában az új webes ügyfélplatform vette át. |
| Felváltotta másik szolgáltatás? | Az új Munkaterület képernyőminta folyamatközpontú tervezése egyszerű hozzáférést biztosít az adott folyamaton belül gyakran használt feladatokhoz.                       |
| Érintett modulok             | Mind                                                                                                                                                                      |

### <a name="sales-tax-jurisdictions"></a>Áfailletékességek

|                              |                                              |
|------------------------------|----------------------------------------------|
| Megszűnés oka       | Alacsony vevői használat és korlátozott szolgáltatáskészlet. |
| Felváltotta másik szolgáltatás? | Szám                                           |
| Érintett modulok             | Amerikai áfa                                 |

### <a name="shipping-carrier-interface"></a>Szállítmányozói felületek

|                              |                                                                                                                                                 |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Máshol már meglévő funkció                                                                                                                         |
| Felváltotta másik szolgáltatás? | Igen, ezt a funkciót részben felváltotta a Szállításkezelés, de még nem váltotta fel az alap Raktárkezelés (WMS I). |
| Érintett modulok             | Értékesítés és marketing, Készletkezelés                                                                                                       |

### <a name="sites-services"></a>Sites Services

Az Oldal Szolgáltatások lehetővé teszik olyan weboldalak megalkotását, melyek kiterjesztik az üzleti folyamatokat az internetre informatikai segítség nélkül.

|                              |                                                                                                                                          |
|------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A Dynamics AX által használt Microsoft Azure infrastruktúra új helyettesítő lehetőségekkel rendelkezik (például Azure oldalakkal). |
| Felváltotta másik szolgáltatás? | Szám                                                                                                                                       |
| Érintett modulok             | HR felvétel, Esetkezelés, Kvóta kérelmek és Szállító regisztrálása                                                                  |

### <a name="ssas-demand-forecasting-strategy"></a>SSAS igény-előrejelzési szolgáltatások

|                              |                                                                              |
|------------------------------|------------------------------------------------------------------------------|
| Megszűnés oka       | A funkció kialakítása az új felhő architektúrában nem támogatható. |
| Felváltotta másik szolgáltatás? | Azure gépi tanulási kereslet-előrejelzési stratégia                           |
| Érintett modulok             | Tervezés                                                                     |

### <a name="travel-requisitions"></a>Utazási igénylések

|                              |                                                                 |
|------------------------------|-----------------------------------------------------------------|
| Megszűnés oka       | Alacsony használat, illetve a legtöbb funkció az Enterprise Portal-ban is létezett. |
| Felváltotta másik szolgáltatás? | Szám                                                              |
| Érintett modulok             | Költséggazdálkodás                                              |

### <a name="vendor-invoice-pool-excluding-posting-details"></a>Szállítói számlagyűjtő a feladási részletek nélkül

|                              |                                                                                                         |
|------------------------------|---------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Alacsony használat. Ezt a funkciót felváltotta a munkafolyamat funkcióval rendelkező Számlanapló. |
| Felváltotta másik szolgáltatás? | A Számlanapló munkafolyamat funkciói.                                                           |
| Érintett modulok             | Kötelezettségek                                                                                        |

### <a name="virtual-company-accounts"></a>Virtuális vállalati számlák

A virtuális vállalatok funkció már nem támogatott a Dynamics AX rendszerben. A virtuális vállalatok funkció lehetővé tette a felhasználók számára, hogy vállalatok egy csoportja által közösen használható táblákat állítsanak be. A szolgáltatás leírása itt található: [Vállalati számlák és Virtuális vállalati számlák](https://msdn.microsoft.com/en-us/library/aa834382(v=ax.10).aspx). A szolgáltatás úgy működik, hogy a táblákat gyűjteményekbe csoportosítja, ezeket pedig virtuális vállalatokhoz társítja. Utóbbiak létező, „valódi” vállalatok csoportjait jelentik. Lekérdezések jönnek létre, amelyek révén a virtuális vállalatban szereplő összes vállalat hozzáférhet a társított táblagyűjtemény tábláiban lévő adatokhoz.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td>Megszűnés oka</td>
<td><ul>
<li>A virtuális vállalatokat még az adatok táblákban való tárolása előtt be kell állítani. A virtuális vállalatok, már meglevő implementációra történő modernizálása nagyon nehézkes.</li>
<li>Mivel a Microsoft Dynamics AX jelenlegi verziójában rengeteg adatnormalizáció történt, igen nehézkessé vált átlátni azt, hogy a táblagyűjteményekhez mit szükséges hozzáadni. Például nehéz megállapítani, mely táblák kerüljenek megosztásra. A virtuális vállalatokban lévő táblákból hivatkozott összes egyéb táblát is hozzá kell adni. A táblanormalizáció miatt, még egy több táblában szétszóródó egyszerű alapadatot is a virtuális vállalat részévé kell tenni. Bármilyen itt történő hiba működési diszfunkciókat okozhat.</li>
<li>Egy virtuális vállalat részét képező táblában elvesznek az adatok eredetére vonatkozó információk , és csak a virtuális vállalat kerül rögzítésre.</li>
</ul></td>
</tr>
<tr class="even">
<td>Felváltotta másik szolgáltatás?</td>
<td>Globális táblák használatával a táblákat elérhetővé teheti az összes vállalatból. Jelenleg nincs helyettesítés.</td>
</tr>
<tr class="odd">
<td>Érintett modulok</td>
<td>Nem alkalmazható</td>
</tr>
</tbody>
</table>

### <a name="warehouse-management-ii"></a>Raktárkezelés II

|                              |                                                                                                                                                                                                                                                                                                             |
|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | A korábban a **Készletkezelés** modulban elérhető Raktárkezelés II megoldás (WMS II) ugyanazokkal a funkciókkal rendelkezik, mint a Microsoft Dynamics AX 2012 R3 verzióban kiadott **Raktárkezelés** modul.                                                                         |
| Felváltotta másik szolgáltatás? | A Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R3 CU8 és Microsoft Dynamics AX 2012 R3 CU9 verziókban kiadott **Raktárkezelés** modul váltja fel a Raktárkezelés II szolgáltatást. Az új modul több speciális funkcióval és rugalmasabb raktárkezelési folyamatokkal rendelkezik, mint a Raktárkezelés II funkció. |
| Érintett modulok             | Készletkezelés, értékesítés és marketing, beszerzés és forrás                                                                                                                                                                                                                                         |

### <a name="worker-reminders-in-human-resources"></a>Dolgozói emlékeztetők az Emberi Erőforrásokban

Emberi Erőforrások Bérlistaadatai

|                              |                 |
|------------------------------|-----------------|
| Megszűnés oka       | Alacsony használat       |
| Felváltotta másik szolgáltatás? | Szám              |
| Érintett modulok             | Emberi erőforrások |

### <a name="workplanner"></a>Munkatervező

|                              |                                                                                                                                                                      |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Megszűnés oka       | Alacsony használat                                                                                                                                                            |
| Felváltotta másik szolgáltatás? | Nem, de a **Profilkapcsolat** lap (amely a **Profilcsoportok** oldalon nyitható meg), ugyan azt az üzleti forgatókönyvet támogatja, mint az elavult **Munkatervező** oldal. |
| Érintett modulok             | Munkaidő és jelenlét                                                                                                                                                  |

### <a name="x-financial-statements"></a>X++ pénzügyi kimutatások

|                              |                                                                                             |
|------------------------------|---------------------------------------------------------------------------------------------|
| Megszűnés oka       | Ezt a szolgáltatást egy másik szolgáltatás váltotta fel.                                    |
| Felváltotta másik szolgáltatás? | Felügyeleti jelentéskészítő (a Dynamics AX jelenlegi verziójában **Pénzügyi jelentéskészítés** megjelöléssel) |
| Érintett modulok             | Főkönyv                                                                              |






