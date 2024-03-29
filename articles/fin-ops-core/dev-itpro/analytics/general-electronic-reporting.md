---
title: Elektronikus jelentéskészítés (ER) áttekintése
description: Ez a cikk áttekintést nyújt az Elektronikus jelentéskészítő eszközről. Alapvető fogalmakat, támogatott eseteket és a megoldás részét képező formátumokat ír le.
author: kfend
ms.date: 11/02/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58941,  ""intro-internal
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.form: ERWorkspace
ms.openlocfilehash: e94846dd565abb6de2c1f07532d285e28307e9a2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269691"
---
# <a name="electronic-reporting-er-overview"></a>Elektronikus jelentéskészítés (ER) áttekintése

[!include [banner](../includes/banner.md)]

Ez a cikk az Elektronikus jelentéskészítő eszközről nyújt áttekintést. Tájékoztatást nyújt az alapfogalmakról, az Elektronikus jelentéskészítés által támogatott esetekről, valamint az Elektronikus jelentéskészítés megoldás részeként megtervezett és kibocsátott formátumok listájáról.

Az ER egy konfigurálható eszköz, amely a szabályozáson áteső elektronikus jelentések és kifizetések létrehozásában és karbantartásában segít. A következő három fogalomon alapul:

- Konfiguráció a kódolás helyett:

    - A konfigurálást egy üzleti felhasználó használhatja, de ehhez nincs szükség fejlesztőre.
    - Az adatmodell üzleti szempontból van meghatározva.
    - A vizuális szerkesztők segítségével lehet létrehozni az ER-konfiguráció összes összetevőjét.
    - Az adatátalakításhoz használt nyelv hasonlít a Microsoft Excel.

- Egy konfiguráció a Dynamics 365 Pénzügy több kiadásának:

    - Egy tartományspecifikus adatmodell kezelése, amely üzleti feltételekben van meghatározva.
    - Alkalmazás-kiadás részleteinek elengedése a kiadásfüggő adatmodell-leképezésekben.
    - Egy formátumkonfiguráció karbantartása az aktuális verzió többszöri kiadására az adatmodell alapján.

- Egyszerű vagy automatikus frissítés:

    - Az ER-konfigurációk verziószámozása támogatott.
    - A Microsoft Dynamics Lifecycle Services (LCS) assets tárház az ER-konfigurációk tárházaként használható verzióváltáshoz.
    - Az eredeti ER-konfigurációkon alapuló honosításokat gyermekverzióként is be lehet vezetni.
    - Az ER konfigurációs fa segítségével lehet szabályozni a verzióktól való függőségeket.
    - A honosítási vagy a különbözeti konfigurációk eltéréseit a rendszer rögzíti, hogy lehetővé tegye az eredeti ER-konfiguráció új verziójára való automatikus frissítést.
    - A honosítási verziók automatikus frissítése során talált ütközések manuális feloldása egyszerű.

Az ER segítségével elektronikus formátumszerkezeteket határozhat meg, majd megadhatja, hogyan kell kitölteni a szerkezeteket az adatok és algoritmusok segítségével. Az adatok átalakítása az Excel nyelvéhez hasonló képletnyelvet is használható. Az adatbázis-formátum leképezés kezelhetőbb, újrahasználható és a formátumváltozástól független beállítása érdekében egy köztes adatmodell-koncepciót is bevezet a rendszer. Ez a fogalom lehetővé teszi a megvalósítás részleteinek elrejtését a formátumleképezés elől, és lehetővé teszi egyetlen adatmodell újrahasználatát több formátumleképezéshez.

Az ER segítségével a különböző országok és régiók jogi követelményeinek megfelelően a bejövő és a kimenő elektronikus dokumentumok formátumait is beállíthatja. Az ER lehetővé teszi, hogy ezeket a formátumokat a teljes életciklusuk során kezelje. Például alkalmazhat új jogszabályi követelményeket, és létrehozhat üzleti dokumentumokat a kívánt formátumban, annak érdekében, hogy elektronikusan információt cseréljen kormányzati testületekkel, bankokkal és egyéb felekkel.

Az ER-motor a fejlesztők helyett az üzleti felhasználóknak készült. Mivel nem kódokat, hanem formátumokat konfigurál, az elektronikus dokumentumok formátumának létrehozása és beállítása gyorsabb és könnyebb.

Az ER jelenleg támogatja a TEXT, XML, JSON, PDF, Microsoft Word és Microsoft Excel OPENXML munkalapformátumokat.

## <a name="capabilities"></a>Képességek

Az ER motor a következő képességekkel rendelkezik:

- Közös eszközt jelent a különböző tartományokban történő elektronikus jelentéskészítéshez, és több mint 20 különböző motort cserél le, amelyek valamilyen típusú elektronikus jelentéseket és pénzügyi jelentéseket és műveleteket írnak le.
- A jelentés formátumát elkülöníti jelenlegi megvalósítástól. Más szóval a formátum különböző verziókban is használható.
- Támogatja egy egyéni formátum létrehozását, ami az eredeti formátumon alapul. Emellett képes automatikusan frissíteni az egyéni formátumot, ha változás történik az eredeti formátumban új honosítási/személyre szabási követelmények miatt.
- Ez válik az elsődleges, szabványos eszközzé a honosítási követelmények támogatására az elektronikus jelentésekben, mind a Microsoft-nál, mind a Microsoft partnereinél.
- Támogatja a formátumok elosztását a partnerek és a vevők részére, a Microsoft Dynamics Lifecycle Services (LCS) rendszeren keresztül.

## <a name="key-concepts"></a>Alapfogalmak

### <a name="main-data-flow"></a>Fő adatáramlás

[![ER fő adatáramlás.](./media/ger-main-data-flow.jpg)](./media/ger-main-data-flow.jpg)

### <a name="component"></a>Összetevő

Az ER a következő típusú összetevőket támogatja:

- Adatmodell
- Modell leképezése
- Formátum
- Metaadatok

További információ: [Elektronikus jelentéskészítés összetevői](er-overview-components.md).

### <a name="configuration"></a><a name="Configuration"></a>Konfiguráció

Az ER-konfiguráció egy adott ER-összetevő csomagolója. Az összetevő lehet adatmodell-összetevő vagy formátum-összetevő. A konfiguráció tartalmazhatja egy ER-összetevő különböző verzióit. Az egyes konfigurációk tulajdonosa egy konkrét konfigurációs szolgáltatóként van megjelölve. Egy konfiguráció összetevőjének **Vázlat** verziója akkor szerkeszthető, amikor a konfiguráció tulajdonosa aktív szolgáltatóként van beállítva az alkalmazás ER-beállításokban.

Minden modellkonfiguráció tartalmaz egy adatmodell összetevőt. Új formátumkonfiguráció származtatható egy bizonyos adatmodell konfigurációból. A létrehozott formátumkonfiguráció a konfigurációfában az eredeti adatmodell-konfiguráció leszármazottjaként jelenik meg.

A létrehozott formátumbeállítás tartalmaz egy formátum-összetevőt. Ez eredeti modell konfiguráció adatmodell komponense automatikusan beillesztésre kerül a leszármazott formátumkonfiguráció formátum komponensébe alapértelmezett adatforrásként.

Az ER-konfiguráció megosztásra kerül az alkalmazás vállalatok számára.

### <a name="provider"></a><a name="Provider"></a>Szolgáltató

Az ER-szolgáltató az a félazonosító, amely az egyes ER-konfigurációk szerzőjét (tulajdonosát) meghatározza. ER segítségével kezelheti a konfigurációs szolgáltatók listáját. Az elektronikus dokumentumokhoz **a pénzügyi és műveleti megoldás részeként kiadott formátumkonfigurációk a Microsoft konfigurációs szolgáltató tulajdonában vannak**.

Új ER-szolgáltató regisztrálási módjának megismeréséhez játssza le a feladat-útmutatót: **ER Konfigurációszolgáltató létrehozása és megjelölése aktívként** (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

### <a name="repository"></a><a name="Repository"></a>Tárház

Egy ER tárház ER konfigurációkat tárol. A következő típusú ER tárházak támogatottak jelenleg: 

- LCS megosztott tár
- LCS-projekt
- Fájlrendszer
- RCS
- Operations-erőforrások
- Globális tárház

Egy **LCS megosztott könyvtár** tár a megosztott eszköztárbó elérést biztosít a konfigurációk listájához a közös eszköz könyvtárban a Lifecycle Services (LCS) szolgáltatásban. Az ilyen típusú ER tárházat csak a Microsoft-szolgáltatóhoz lehet regisztrálni. Az LCS közös eszköz tárból importálhatja a legújabb verzióit az ER konfigurációknak az aktuális példányba.

Az **LCS projekt** tárház hozzáférést biztosít egy bizonyos, a tárház regisztrációs szakaszában kiválasztott LCS projekt konfigurációinak listájához (LCS projekt eszköztár). Az ER lehetőséget biztosít a megosztott konfigurációk feltöltésére a jelenlegi példányból egy adott **LCS-projekt** tárházba. Az LCS-projekttárház **konfigurációit** is importálhatja a pénzügyi és műveleti alkalmazások aktuális példányába.

A **fájlrendszertárház** hozzáférést biztosít az AOS szolgáltatást tartalmazó számítógép helyi fájlrendszerének meghatározott mappájában XML-fájlként található konfigurációk listájához. A szükséges mappát a tárház regisztrálásának fázisában kell kiválasztani. Importálhat továbbá konfigurációkat egy **Fájlrendszer** adattárból a jelenlegi példányba. 

Vegye figyelembe, hogy ez a tárhelytípus elérhető a következő környezetekben:

- Fejlesztés céljából telepített felhőbeli környezetek (amelyek a csatolt csomagok tesztmodelljeit tartalmazzák)
- Helyben telepített környezetek (helyszíni)

További információ: [Elektronikus jelentéskészítési (ER) konfigurációk importálása](./electronic-reporting-import-ger-configurations.md).

Az **RCS** adattár hozzáférést biztosít a [Konfigurációs szolgáltatás (RCS)](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration) adott példányának konfigurációs listájához, amelyet az adattár regisztrációs fázisában választottak ki. Az ER segítségével befejezett vagy megosztott konfigurációkat importálhat a kiválasztott RCS-példányból a jelenlegi példányba, amelyet aztán elektronikus jelentéskészítésre használhatnak fel.

További információ: [Elektronikus jelentéskészítési (ER) konfigurációk importálása RCS-ből](./rcs-download-configurations.md).

A **Globális tár** adattár hozzáférést biztosít a [Konfigurációs szolgáltatás](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration) globális tárához tartozó konfigurációk listájához. Az ilyen típusú ER tárházat csak a Microsoft-szolgáltatóhoz lehet regisztrálni. Az globális tárból importálhatja a legújabb verzióit az ER konfigurációknak az aktuális példányba.

További információért lásd: [Elektronikus jelentéskészítési (ER) konfigurációk importálása a konfigurációs szolgáltatás Globális tárából](./er-download-configurations-global-repo.md)

Az **Operations-erőforrások** tárház hozzáférést biztosít azon konfigurációk listájához, melyeket kezdetben a a alkalmazásmegoldás részeként a Microsoft szállít mint ER-konfigurációszolgáltató. Ezek a konfigurációk importálhatóak a jelenlegi munkamenetbe és felhasználhatóak elektronikus jelentés céljából vagy egyszerű feladatútmutatók lejátszásához. Használhatóak ezen kívül további lokalizációkhoz és testreszabásokhoz. Ne feledje, hogy a Microsoft ER-konfigurációk által biztosított legújabb verziókat a megfelelő ER-tárház segítségével kell importálni az LCS megosztott eszköztárából.

A szükséges **LCS-projekt**, **Fájlrendszer**, és **Jogszabályban előírt konfigurációs szolgáltatás** adattárakat külön-külön is lehet regisztrálni az aktuális példány minden egyes konfigurációs szolgáltatójára. Minden tárház hozzárendelhető egy bizonyos konfigurációs szolgáltatóhoz.

## <a name="supported-scenarios"></a>Támogatott esetek

### <a name="building-a-data-model"></a>Adatmodell létrehozása

Az ER modelltervezőt biztosít egy bizonyos üzleti tartomány adatmodelljeinek építésére. Minden tartományspecifikus üzleti entitás és a köztük lévő kapcsolat beállítható adatmodellként egy hierarchikus struktúrában. 

Ahhoz, hogy megismerje ennek a folyamatnak a részleteit játssza le az **ER tartományspecifikus adatmodell kialakítása** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része), hogy megismerkedjen a folyamat részleteivel.

### <a name="translating-data-model-content"></a>Az adatok modell tartalmának fordítása

Az adatok modell tartalma (címke és leírás) lefordítható más, az alkalmazás által támogatott nyelvre. Érdemes lehet az adatok modell tartalmának fordítása a következő okok miatt:

- Hogy tervezés közben érthetőbb legyen az idegen nyelvű formátumtervezők számára, akik adatmodellt fognak használni a formátum-összetevők adatleképezéséhez
- Hogy a felület felhasználóbarátabb legyen futtatás közben a rákérdezések és a futtatási paraméterek súgójának megjelenítésekor, valamint a konfigurált ellenőrzési üzenetek (hibák, figyelmeztetések) megjelenítésekor a bejelentkezett felhasználó preferált nyelven.

### <a name="configuring-data-model-mappings-for-outgoing-documents"></a>A kimenő dokumentumok adatmodell hozzárendeléseinek beállítása

Az ER biztosít egy modell-leképezés tervezőt, amely lehetővé teszi a felhasználó számára az általuk specifikus alkalmazás adatforrásokhoz tervezett adatmodellek leképezését. A leképezés alapján a rendszer az adatokat importálja futásidőben a kijelölt adatforrásokból az adatmodellbe. Az adatmodellt a rendszer ezután absztrakt adatforrásként használja a kimenő elektronikus dokumentumokat létrehozó ER-formátumokhoz. 

Az ezen forgatókönyv részleteinek megismeréséhez hajtsa végre az **ER modellfeltérképezés definiálása és adatforrások kiválasztása** feladatot, majd az **ER adatmodellezés térkép a kiválasztott adatforrásokhoz** feladatútmutatókat (a **7.5.4.3 IT szolgáltatás/megoldás megszerzése/kifejlesztése elemek (10677)** üzleti folyamat része)

### <a name="configuring-data-model-mappings-for-incoming-documents"></a>A bejövő dokumentumok adatmodell hozzárendeléseinek beállítása

Az ER biztosít egy modell-leképezés tervezőt, amely lehetővé teszi a felhasználó számára az általuk specifikus célokhoz tervezett adatmodellek leképezését. Az adatmodellek például frissíthető adatösszetevőkhöz (táblák, adatentitások és nézetek) rendelhetők. A leképezés alapján a rendszer futásidőben frissíti az adatokat, az adatmodellből származó adatok felhasználásával. Az ER-formátum absztrakt tárolásaként az adatmodell ki van töltve a bejövő elektronikus dokumentumból importált adatokkal. 

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>A létrehozott modell-összetevő tárolása modell-konfigurációként

Az ER képes a megtervezett adatmodellt a hozzárendelt adatfeltérképezésekkel modellkonfigurációként tárolni az aktuális példányban. A következő ábrán egy példa látható az ilyen típusú adatmodell-konfigurációkra (a fizetési modellkonfigurációra).

Ahhoz, hogy megismerje ennek a folyamatnak a részleteit, játssza le az **ER adatmodell-feltérképezés a kiválasztott adatforrásokhoz** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Formátum létrehozása adatmodell alapként való kijelölésével

Az ER támogatja azt a formátumtervezőt, amely az elektromos dokumentum formátumának tervezésére szolgál a kiválasztott üzleti tartomány számára, úgy, hogy a modell-összetevőt alapként választja ki. Ugyanaz az ER formátumtervező képes arra, hogy feltérképezzen egy Ön által létrehozott, egy adott tartomány adatmodell-feltérképezését adatforrásként használó formátumot. 

Ahhoz, hogy megismerje ennek a folyamatnak a részleteit hajtsa végre az **ER tartományspecifikus adatmodell kialakítása** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Az OPENXML munkafüzet formátumban elektronikus dokumentumok létrehozásához egy konfigurációkészlet létrehozása

Az ER formátumtervezővel elektronikus dokumentumok hozhatók létre OPENXML munkalap-formátumban. 

Ahhoz, hogy megismerje ennek a folyamatnak a részleteit hajtsa végre az **ER jelentés konfigurálása OPENXML formátumban** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része). A sablon importálása feladatútmutató lépésének részeként használja a következőt: [Kifizetési jelentés mintája (SampleVendPaymWsReport.xlsx)](https://download.microsoft.com/download/3/f/0/3f0658b2-042c-43cf-a776-0f4c7f7cfe4e/SampleVendPaymWsReport.xlsx) Excel-fájl sablonként.

### <a name="building-a-configuration-to-generate-electronic-documents-in-a-word-document-format"></a>A Word-dokumentum formátumban elektronikus dokumentumok létrehozásához egy konfigurációkészlet létrehozása

Az ER formátumtervezővel elektronikus dokumentumok hozhatók létre Word-dokumentum formátumban. A következő ábrán egy példa látható az ilyen típusú formátumra. Fontos, hogy ez a formátum újrahasznosítja a meglévő ER-konfigurációt, amelyet eredetileg a jelentés OPENXML-formátumban történő előállítására terveztek.

Ahhoz, hogy megismerje ennek a folyamatnak a részleteit, hajtsa végre A Microsoft WORD formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése című feladat-útmutatót (a 7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677) üzleti folyamat része). A sablon importálása feladatútmutató lépésének részeként használja a következő Word-fájlokat sablonként az ER-formátumhoz:

- [Kifizetési jelentés mintája (SampleVendPaymDocReport.docx)](https://download.microsoft.com/download/0/d/e/0de5a87c-95fc-4dfa-958f-285cb28b5b2b/SampleVendPaymDocReport.docx)
- [Kifizetési jelentés bekötött sablonja (SampleVendPaymDocReportBounded.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded.docx)

### <a name="building-a-configuration-to-import-data-from-incoming-electronic-documents"></a>Konfigurációs létrehozása az adatok importálásához a bejövő elektronikus dokumentumokból

Az ER-formátumtervezővel XML vagy szöveg formátumban írhatók le az adatimportáláshoz használni kívánt elektronikus dokumentumok. A tervezett formátumot használjuk a bejövő dokumentum elemzéséhez. Az ER formátumleképezés-tervező használható a tervezett formátum elemeinek a kötéséhez az adatmodellhez. 

Ahhoz, hogy megismerje ennek a folyamatnak a részleteit, hajtsa végre a Szükséges ER-konfigurációk létrehozása adatok importálásához egy külső fájlból című feladat-útmutatót (a 7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677) üzleti folyamat része). Az útmutató végrehajtásához használja a következő fájlokat:

- [ER-adatmodellkonfiguráció (1099model.xml)](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml)
- [ER-formátumkonfiguráció (1099format.xml)](https://download.microsoft.com/download/e/8/7/e87154b0-b53f-431f-8e1e-0b7f7c9805a9/1099format.xml)
- [Minta a beérkező dokumentumra XML-formátumban (1099entries.xml)](https://download.microsoft.com/download/4/0/3/403a4958-df24-476a-b8b0-6843a9fa7f89/1099entries.xml)
- [Minta a beérkező dokumentum adatinak kezelésére szolgáló munkafüzetre (1099entries.xlsx)](https://download.microsoft.com/download/6/0/0/6001abab-a331-48db-a939-41851fb0f5d0/1099entries.xlsx)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Egy megtervezett formátumösszetevő tárolása a formátumkonfigurációban

Az ER képes a megtervezett formátumnak a konfigurált adatfeltérképezésekkel történő együttes tárolására formátumkonfigurációként az aktuális példányban. Az előző illusztrációban egy példa szerepel erre a típusú formátumkonfigurációra (**BACS (UK)**, ami a **Kifizetési modell** konfigurációból van származtatva). Ahhoz, hogy megismerje ennek a folyamatnak a részleteit hajtsa végre az **ER tartományspecifikus adatmodell kialakítása** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

### <a name="configuring-finance-to-start-to-use-a-created-format-internally"></a>A Finance konfigurálása a létrehozott formátum belső használatához

Az alkalmazás beállítható úgy, hogy az elektronikus jelentések generálásához egy már létrehozott formátumot használjon. A létrehozott formátum konfigurációjának hivatkozásához bizonyos tartományspecifikus beállításokat kell meghatározni. Például, egy ER formátumkonfiguráció használható az elektronikus szállítói kifizetésekhez BACS formátumban, ha a formátumkonfiguráció a kifizetések módjánál külön le van hivatkozva.

Játssza le az **ER formátum használata elektronikus dokumentumok létrehozására a fizetésekhez** című feladatútmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része), hogy megismerje ennek az esetnek a részleteit.

## <a name="handling-er-components"></a>ER-összetevők kezelése

### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>ER-összetevő közzététele az LCS-ben külső használatra (lokalizáció)

A létrehozott összetevő (modell vagy formátum) tulajdonosa az ER segítségével közzé tudja tenni az összetevő kész verzióját az LCS-ben. Ehhez a folyamathoz az **LCS projekt** típus tárháza szükséges az aktuális ER konfigurációs szolgáltatónál. Ha az összetevő kész verziója **KÉSZ** státuszról **MEGOSZTOTT** státuszra módosul, a verziót közzéteszi a rendszer az LCS-ben. Ha egy összetevőt közzétettünk az LCS-ben, az összetevő tulajdonosa szolgáltatóvá válik az összetevő támogatása céljából. Például ha ezt a formátum-összetevőt egy jogilag kötelező elektromos dokumentum létrehozására tervezték (például a lokalizációs esettel összhangban), ez a szolgáltatás feltételezi azt, hogy ez a formátum megfelel a jogszabályi változtatásoknak és új verziókat tesz közzé, amikor az új jogszabályi követelményeket kell támogatni. Ahhoz, hogy megismerje ennek a folyamatnak a részleteit hajtsa végre az **ER konfiguráció feltöltése a Lifecycle Services-be** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>ER-összetevő importálása az LCS-ből belső használatra

Az EZ lehetővé teszi az ER komponensek importálását az LCS-ből az aktuális példányba. Az **LCS projekt** típus tárháza szükséges ehhez a folyamathoz. Amikor egy ER-összetevőt importáltak az LCS-ből az aktuális példányba, akkor ennek a példánynak a tulajdonosa lesz annak a szolgáltatásnak a fogyasztója, amelyet az importált összetevő tulajdonosa (szerzője) kínál. Például, ha ez a formátum-összetevő arra szolgál, hogy az alkalmazásból egy bizonyos elektronikus dokumentumot generáljon egy adott ország-/régióspecifikus formátumban (lokalizációs eset), akkor feltételezzük, hogy a felhasználó minden frissítést meg tud szerezni a jogi szabványoknak megfelelően. Ahhoz, hogy megismerje ennek a folyamatnak a részleteit hajtsa végre az **ER konfiguráció importálása a Lifecycle Services-ből** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Formátum létrehozása más formátum alapként való kijelölésével (testreszabás)

Az ER segítségével létrehozhat (származtathat) egy új komponenst az LCS-ből importált komponens (alap) jelenlegi verziójából. Például egy felhasználó új formátumot szeretne származtatni testreszabás támogatása érdekében az elektronikus dokumentum (például egy további mező vagy egy részletes leírást) néhány különleges követelményének végrehajtásához. Hajtsa végre az **ER formátum frissítése új alapverzió használatával** című feladatútmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része), hogy megismerje ennek az esetnek a részleteit.

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Formátum frissítése az alapformátum új verziójának kiválasztásával (új alap megadása)

Az ER automatikusan igazodik az alapösszetevő legújabb verziójához a származtatott összetevő jelenlegi vázlat-verziójában. Ennek a folyamatnak a neve *új alap* megadása. Például az LCS-ből importált formátum-összetevő legújabb verziójában megjelent új szabályozási módosítások automatikusan összevonhatók az elektronikus dokumentum a saját testreszabott verziójával. Az automatikusan nem egyesíthető módosítások ütközésnek minősülnek. Ezek az ütközések a megfelelő összetevőhöz tartozó tervezőeszközben manuális megoldásra megjelennek. Hajtsa végre az **ER formátum frissítése új alapverzió használatával** című feladatútmutatót (a **7.5.5.3 Módosított informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10683)** üzleti folyamat része), hogy megismerje ennek az esetnek a részleteit.

## <a name="list-of-er-configurations-that-have-been-released-in-finance"></a><a name="list-of-configurations"></a>A Finance alkalmazásban kiadott ER-konfigurációk listája

A Finance megoldásban az ER-konfigurációk listája folyamatosan frissül. Nyissa meg a [globális tárházat](er-download-configurations-global-repo.md) a jelenleg támogatott ER-konfigurációk listájának ellenőrzéshez. A **Megszűnés részletei** gyorslapon áttekintheti a már megszüntetett vagy már nem karbantartott konfigurációk adatait. 

![A Globális adattár tartalma a Konfigurációs adattár oldalon.](./media/er-overview-03.gif)

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentéskészítés összetevői](er-overview-components.md)
- [Elektronikus jelentéskészítési (ER) konfigurációk létrehozása](electronic-reporting-configuration.md)
- [Elektronikus jelentéskészítési (ER) konfigurációk életciklusainak kezelése](general-electronic-reporting-manage-configuration-lifecycle.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

