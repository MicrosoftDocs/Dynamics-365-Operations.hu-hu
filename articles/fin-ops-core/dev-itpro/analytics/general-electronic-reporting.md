---
title: Elektronikus jelentéskészítés (ER) áttekintése
description: Ez a témakör az Elektronikus jelentéskészítési eszközről nyújt áttekintést. Alapvető fogalmakat, támogatott eseteket és a megoldás részét képező formátumokat ír le.
author: NickSelin
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d22a6fc336708028ce4953df50360c233398303d
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893177"
---
# <a name="electronic-reporting-er-overview"></a>Elektronikus jelentéskészítés (ER) áttekintése

[!include [banner](../includes/banner.md)]

Ez a témakör az Elektronikus jelentéskészítés eszközről nyújt áttekintést. Tájékoztatást nyújt az alapfogalmakról, az Elektronikus jelentéskészítés által támogatott esetekről, valamint az Elektronikus jelentéskészítés megoldás részeként megtervezett és kibocsátott formátumok listájáról.

Az elektronikus jelentés (ER) olyan eszköz, amelyet bejövő és kimenő elektronikus dokumentumok formázására egyaránt használhat, a különböző országok/régiók jogi követelményeinek megfelelően. Az ER lehetővé teszi, hogy ezeket a formátumokat a teljes életciklusuk során kezelje. Például alkalmazhat új jogszabályi követelményeket, és létrehozhat üzleti dokumentumokat a kívánt formátumban, annak érdekében, hogy elektronikusan információt cseréljen kormányzati testületekkel, bankokkal és egyéb felekkel.

Az ER-motor a fejlesztők helyett az üzleti felhasználóknak készült. Mivel nem kódokat, hanem formátumokat konfigurál, az elektronikus dokumentumok formátumának létrehozása és beállítása gyorsabb és könnyebb.

Az ER jelenleg a TEXT, XML, Microsoft Word dokumentumokat és OPENXML munkalap-formátumokat támogatja. Azonban egy kiterjesztési felület további formátumok támogatását biztosítja.

## <a name="capabilities"></a>Képességek

Az ER motor a következő képességekkel rendelkezik:

- Egyetlen megosztott eszközt képvisel a különböző tartományokban történő elektronikus jelentésekhez, és több mint 20 különböző motort helyettesít, amelyek az elektronikus jelentés valamely típusára képesek a Finance and Operations-ben.
- A jelentés formátumát elkülöníti jelenlegi megvalósítástól. Más szóval a formátum különböző verziókban is használható.
- Támogatja egy egyéni formátum létrehozását, ami az eredeti formátumon alapul. Emellett képes automatikusan frissíteni az egyéni formátumot, ha változás történik az eredeti formátumban új honosítási/személyre szabási követelmények miatt.
- Ez válik az elsődleges, szabványos eszközzé a honosítási követelmények támogatására az elektronikus jelentésekben, mind a Microsoft-nál, mind a Microsoft partnereinél.
- Támogatja a formátumok elosztását a partnerek és a vevők részére, a Microsoft Dynamics Lifecycle Services (LCS) rendszeren keresztül.

## <a name="key-concepts"></a>Alapfogalmak

### <a name="components"></a>Összetevők

Az ER két összetevő-típust támogat: **Adatmodell** és **Formátum**.

#### <a name="data-model-and-model-mapping-components"></a>Adatmodell és modell-hozzárendelési összetevők

Az adatmodell-összetevő az adatszerkezet absztrakt ábrázolása. Egy adott üzleti területet leírására szolgál elegendő részletességgel ahhoz, hogy megfeleljen a terület jelentési követelményeinek. Egy adatmodell-összetevő a következő részekből áll:

- <a name="DataModelComponent"></a>Egy adatmodell, ami a területspecifikus üzleti entitások egy csoportja, és egy hierarchikusan felépített kapcsolatrendszer ezen entitások között.
- <a name="ModelMappingComponent"></a>Egy modell-leképezés, amely összekapcsolja az alkalmazás-adatforrásokat az adatmodell adott, egyes elemeivel a futási időben, valamint az adatfolyam, és az üzleti adatok feltöltésének szabályai az adatmodell-összetevőbe.

Egy adatmodell üzleti entitását egy tároló (rekord) képviseli. Az üzleti entitások tulajdonságai adatelemként (mezőként) jelennek meg. Minden adatelem egyedi névvel, címkével, leírással és értékkel rendelkezik. Az egyes adatelemek értékeit megszerkesztheti, hogy karakterláncként, egész számként, valós számként, dátumként, enumerációként, logikai értékként vagy egyéb változóként legyenek kiolvasva. Továbbá lehet másik rekord vagy rekordlista is.

Egyetlen adatmodell-összetevő több tartományspecifikus üzletientitás-hierarchiát tartalmazhat. Modell-hozzárendeléseket is tartalmazhat, amelyek támogatják a jelentésspecifikus adatáramlást futásidőben. A hierarchiákat egyetlen rekord különbözteti meg, amit a modell-hozzárendelés gyökerének választott ki. Például, a fizetési tartomány adatmodellje támogathatja a következő leképezéseket:

- Vállalat \> Szállító \> Az AP tartomány kifizetési tranzakciói
- Vevő \> Vállalat \> Az AR tartomány kifizetési tranzakciói

Vegyük figyelembe, hogy az üzleti entitásokat (úgy mint a vállalat és a fizetési tranzakciók) egyszer hozza létre. Ezután különböző hozzárendelések újrahasználják őket.

A modell-hozzárendelés, amely támogatja a kimenő elektronikus dokumentumokat, a következő lehetőségeket kínálja:

- Használhat különböző adattípusokat az adatmodell adatforrásaként. Használhat például táblázatokat, adatentitásokat, módszereket vagy felsorolásokat.
- Olyan felhasználói bemeneti paramétereket támogat, amelyeket meghatározhat az adatmodell adatforrásaiként, amikor bizonyos adatokat a futási időben kell megadni.
- Támogatja az adatok átalakítását a szükséges csoportokba. Az adatok szűrését, rendezését és összegzését is lehetővé teszi, továbbá logikai számított mezők hozzáfűzését a Microsoft Excel képleteihez hasonló képletekkel. További tudnivalókért lásd: [Képletszerkesztő elektronikus jelentéskészítésben (ER)](general-electronic-reporting-formula-designer.md).

A modell-hozzárendelés, amely támogatja a bejövő elektronikus dokumentumokat, a következő lehetőségeket kínálja:

- Különböző frissíthető adatelemeket használhat célként. Ezek az adatelemek lefedik a táblákat, az entitásokat és a nézeteket is. A bejövő elektronikus dokumentumok adatai alapján lehet frissíteni az adatokat. Egy modell hozzárendelésben több cél is használható.
- Olyan felhasználói bemeneti paramétereket támogat, amelyeket meghatározhat az adatmodell adatforrásaiként, amikor bizonyos adatokat a futási időben kell megadni.

Minden üzleti tartományhoz készül egy adatmodell-összetevő, amelyet egységes adatforrásként kell használni a jelentésekhez, és amely elkülöníti a jelentéskészítést az adatforrások fizikai megvalósításától. Olyan módon képezi le a tartományspecifikus üzleti fogalmakat és funkciókat, amely hatékonyabbá teszi a jelentésformátum kezdeti tervét és további karbantartását.

#### <a name="format-components-for-outgoing-electronic-documents"></a><a name="FormatComponentOutbound"></a>Kimenő elektronikus dokumentumok komponensformázása

A formátum összetevője a futásidőben létrejövő jelentési kimenet sémája. A rendszer az alábbi elemekből áll:

- Egy formátum, amely a kimenő elektronikus dokumentum futásidőben generált struktúráját és tartalmát határozza meg.
- Adatforrásokból, amelyek felhasználói bemeneti paraméterek és tartományspecifikus adatmodellek formájában jelennek meg kiválasztott modell-hozzárendeléssel.
- Egy formátum hozzárendelésből, amely formátum-adatforrások formájában jelenik meg olyan egyedi formátumelemekkel, amelyek megadják a futásidőben az adatfolyamot és a formátumkimenet generálásának szabályait.
- Formátumérvényesítésből, amely olyan konfigurálható szabályok formájában jelenik meg, melyek a jelentéslétrehozást kontrollálják a futásidőben a futó környezetben. Létezhet például egy olyan szabály, amely leállítja a szállítói kifizetések kimenetének létrehozását, és kivételt okoz, ha a kiválasztott szállító meghatározott attribútumai hiányoznak, például a bankszámlaszám.

Egy formátum összetevő, amely támogatja az alábbi funkciókat:

- Különálló fájlokként különböző formátumú kimenet jelentés létrehozása, például szöveg, XML, Microsoft Word-dokumentum vagy munkalap.
- Több külön fájl létrehozása, és ezen fájlok zip fájlba történő tömörítése.

A formátum-összetevő lehetővé teszi bizonyos fájlok csatolását, amelyek a jelentési kimenetben a következőképpen használhatók:

- Excel-munkafüzetek, melyek olyan munkalapot tartalmaznak amik sablonként használhatóak a kimenethez az OPENXML munkalap formátumban
- Word-fájlok, melyek olyan dokumentumot tartalmaznak, amely sablonként használható a kimenethez a Microsoft Word-dokumentum formátumban
- Más fájlok, amelyeket előre definiált fájlként konvertálni lehet a formátum kimenetébe.

A következő ábra azt mutatja, hogy hogyan áramlanak az adatok ezeknek a formátumoknak az esetében.

[![Kimenő formátum-összetevők adatáramlása](./media/ER-overview-02.png)](./media/ER-overview-02.png)

Egyetlen ER-formátumkonfiguráció futtatásához és egy kimenő elektronikus dokumentum létrehozásához meg kell adni a formátumkonfiguráció hozzárendelését.

#### <a name="format-components-for-incoming-electronic-documents"></a><a name="FormatComponentInbound"></a>Bejövő elektronikus dokumentumok komponensformázása

A formátum-összetevő a futásidőben importált bejövő dokumentum sémája. A rendszer az alábbi elemekből áll:

- Egy formátumból, amely a bejövő, adatokat tartalmazó elektronikus dokumentum futásidőben importált struktúráját és tartalmát határozza meg Egy formátum-összetevőből, amely különböző formátumú bejövő dokumentumok elemzésére szolgál: ilyen például a szöveg és az XML.
- Egy formátum-hozzárendelésből, amely összekapcsolja az egyes formátumelemeket egy tartományspecifikus adatmodell elemeivel. Futási időben az adatmodell elemei megadják az adatfolyamot és az adatok importálásának szabályait a bejövő dokumentumokból, majd ezt követően tárolják az adatokat egy adatmodellben.
- Formátumérvényesítésből, amely olyan konfigurálható szabályok formájában jelenik meg, melyek az adatimportálást kontrollálják a futásidőben a futó környezetben. Létezhet például egy olyan szabály, amely leállítja egy szállító kifizetéseivel rendelkező banki kivonat importálását, és kivételt okoz, ha a kiválasztott szállító attribútumai hiányoznak, például a szállító azonosító kódja.

A következő ábra azt mutatja, hogy hogyan áramlanak az adatok ezeknek a formátumoknak az esetében.

[![Bejövő formátum-összetevők adatáramlása](./media/ER-overview-03.png)](./media/ER-overview-03.png)

Egyetlen ER-formátumkonfiguráció futtatásához, adatok importálásához egy bejövő elektronikus dokumentumból, meg kell adni egy formátumkonfiguráció kívánt hozzárendelését, valamint a modell-hozzárendelés integrációs pontját. A különböző típusú bejövő dokumentumokhoz ugyanaz a modell-leképezés és célok használhatók különböző formátumokkal.

#### <a name="component-versioning"></a>Összetevő verziókövetése

Az ER-összetevő esetében támogatott a verziókövetés. A következő munkafolyamat az ER-összetevők változásainak kezelésére szolgál:

1. Az eredetileg létrehozott verzió **Tervezet** verzióként van megjelölve. Ez a verzió szerkeszthető és elérhető próbakísérletekhez.
2. A **Tervezet** verzió átkonvertálható egy **Befejeződött** verzióvá. Ez a verzió használható a helyi jelentési folyamatokban.
3. A **Befejeződött** verzió átkonvertálható egy **Megosztott** verzióvá. Ezen verzió közzétételre kerül az LCS-n, és a globális jelentési folyamatokban is használható.
4. A **Megosztott** verzió átkonvertálható **Nem folytatott** verzióvá. Ez a verzió törölhető.

A **Befejeződött** vagy **Megosztott** állapotú verziók elérhetőek más adatcsere céljából. Egy ezekkel az állapotokkal rendelkező összetevőn a következő műveletek végezhetőek el:

- Az összetevő szerializálható XML-formátumba és a rendszerből exportálható XML formátumú fájlba.
- Az összetevők újraszerializálhatóak XML fájlból, és importálhatóak az alkalmazásba egy ER-összetevő új verziójaként.

#### <a name="component-date-effectivity"></a>Összetevő érvényességi dátuma

Az ER-összetevő verziói érvényességi dátumhoz kötöttek. Az ER-összetevőhöz beállítható az **Érvényesség kezdete** dátum, hogy meghatározzuk, mikortól lesz érvényes az összetevő a jelentési folyamatban. Az alkalmazás munkamenetdátuma arra használható, hogy meghatározzuk, érvényes-e az összetevő a végrehajtásra. Amennyiben egy bizonyos dátumhoz egynél több verzió is érvényes, a jelentési folyamathoz a legutóbbi verzió kerül felhasználásra.

#### <a name="component-access"></a>Összetevő hozzáférése

Az ER formátum összetevőinek hozzáférése függ az ország/régió ISO kódjának beállításától. Ha ez a beállítás nincs bejelölve a formátum beállítások kiválasztott verziójánál, akkor a formátum összetevők elérhetőek bármely vállalatnál a futási idő során. Ha ez a beállítás tartalmazza az ország/régió ISO kódját, akkor a formátum összetevője csak abból a vállalatból érhető el, amely elsődleges címének egy formátum-összetevő ország/terület ISO kódja van megadva.

Előfordulhat, hogy az adatformátum-összetevők különböző verziói más ország/régió ISO kód beállításaival rendelkeznek.

#### <a name="configuration"></a><a name="Configuration"></a>Konfiguráció

Az ER-konfiguráció egy adott ER-összetevő csomagolója. Az összetevő lehet adatmodell-összetevő vagy formátum-összetevő. A konfiguráció tartalmazhatja egy ER-összetevő különböző verzióit. Az egyes konfigurációk tulajdonosa egy konkrét konfigurációs szolgáltatóként van megjelölve. Egy konfiguráció összetevőjének **Vázlat** verziója akkor szerkeszthető, amikor a konfiguráció tulajdonosa aktív szolgáltatóként van beállítva az alkalmazás ER-beállításokban.

Minden modellkonfiguráció tartalmaz egy adatmodell összetevőt. Új formátumkonfiguráció származtatható egy bizonyos adatmodell konfigurációból. A létrehozott formátumkonfiguráció a konfigurációfában az eredeti adatmodell-konfiguráció leszármazottjaként jelenik meg.

A létrehozott formátumbeállítás tartalmaz egy formátum-összetevőt. Ez eredeti modell konfiguráció adatmodell komponense automatikusan beillesztésre kerül a leszármazott formátumkonfiguráció formátum komponensébe alapértelmezett adatforrásként.

Az ER-konfiguráció megosztásra kerül az alkalmazás vállalatok számára.

#### <a name="provider"></a><a name="Provider"></a>Szolgáltató

Az ER-szolgáltató az a félazonosító, amely az egyes ER-konfigurációk szerzőjét (tulajdonosát) meghatározza. ER segítségével kezelheti a konfigurációs szolgáltatók listáját. A Finance and Operations megoldás részeként kiadott elektromos dokumentumokra érvényes formátumkonfigurációk tulajdonosa a **Microsoft** konfigurációs szolgáltató.

Új ER-szolgáltató regisztrálási módjának megismeréséhez játssza le a feladat-útmutatót: **ER Konfigurációszolgáltató létrehozása és megjelölése aktívként** (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

#### <a name="repository"></a><a name="Repository"></a>Tárház

Egy ER tárház ER konfigurációkat tárol. A következő típusú ER tárházak támogatottak jelenleg: 

- LCS megosztott tár
- LCS-projekt
- Fájlrendszer
- RCS
- Operations-erőforrások
- Globális tárház

Egy **LCS megosztott könyvtár** tár a megosztott eszköztárbó elérést biztosít a konfigurációk listájához a közös eszköz könyvtárban a Lifecycle Services (LCS) szolgáltatásban. Az ilyen típusú ER tárházat csak a Microsoft-szolgáltatóhoz lehet regisztrálni. Az LCS közös eszköz tárból importálhatja a legújabb verzióit az ER konfigurációknak az aktuális példányba.

Az **LCS projekt** tárház hozzáférést biztosít egy bizonyos, a tárház regisztrációs szakaszában kiválasztott LCS projekt konfigurációinak listájához (LCS projekt eszköztár). Az ER lehetőséget biztosít a megosztott konfigurációk feltöltésére a jelenlegi példányból egy adott **LCS-projekt** tárházba. Importálhat továbbá konfigurációkat egy **LCS-projekt** tárból a Finance and Operations jelenlegi példányába.

A **Fájlrendszer** adattár hozzáférést nyújt azokhoz a konfigurációk listájához, amelyek XML-fájlként a berendezés helyi fájlrendszerének meghatározott mappájában vannak, ahol az AOS szolgáltatást tárolják. A szükséges mappát az adattár regisztrációs fázisában választják ki. Importálhat továbbá konfigurációkat egy **Fájlrendszer** adattárból a jelenlegi példányba. 

Vegye figyelembe, hogy ez a tárhelytípus elérhető a következő környezetekben:

- Fejlesztés céljából telepített felhőbeli környezetek (amelyek a csatolt csomagok tesztmodelljeit tartalmazzák)
- Helyben telepített környezetek (helyszíni)

További információ: [Elektronikus jelentéskészítési (ER) konfigurációk importálása](./electronic-reporting-import-ger-configurations.md).

Az **RCS** adattár hozzáférést biztosít a [Konfigurációs szolgáltatás (RCS)](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration) adott példányának konfigurációs listájához, amelyet az adattár regisztrációs fázisában választottak ki. Az ER segítségével befejezett vagy megosztott konfigurációkat importálhat a kiválasztott RCS-példányból a jelenlegi példányba, amelyet aztán elektronikus jelentéskészítésre használhatnak fel.

További információ: [Elektronikus jelentéskészítési (ER) konfigurációk importálása RCS-ből](./rcs-download-configurations.md).

A **Globális tár** adattár hozzáférést biztosít a [Konfigurációs szolgáltatás](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration) globális tárához tartozó konfigurációk listájához. Az ilyen típusú ER tárházat csak a Microsoft-szolgáltatóhoz lehet regisztrálni. Az globális tárból importálhatja a legújabb verzióit az ER konfigurációknak az aktuális példányba.

További információért lásd: [Elektronikus jelentéskészítési (ER) konfigurációk importálása a konfigurációs szolgáltatás Globális tárából](./er-download-configurations-global-repo.md)

Az **Operations-erőforrások** tárház hozzáférést biztosít azon konfigurációk listájához, melyeket kezdetben a a alkalmazásmegoldás részeként a Microsoft szállít mint ER-konfigurációszolgáltató. Ezek a konfigurációk importálhatóak a jelenlegi munkamenetbe és felhasználhatóak elektronikus jelentés céljából vagy egyszerű feladatútmutatók lejátszásához. Használhatóak ezen kívül további lokalizációkhoz és testreszabásokhoz. Vegye figyelembe, hogy a Microsoft által bizosított legfrissebb ER konfigurációkat az LCS megosztott eszköztárból kell importálni a megfelelő ER tárház használatával.

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

Ahhoz, hogy megismerje ennek a folyamatnak a részleteit hajtsa végre az **ER jelentés konfigurálása OPENXML formátumban** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része). A sablon importálása feladatútmutató lépésének részeként használja a következőt: [Kifizetési jelentés mintája (SampleVendPaymWsReport.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202) Excel-fájl sablonként.

### <a name="building-a-configuration-to-generate-electronic-documents-in-a-word-document-format"></a>A Word-dokumentum formátumban elektronikus dokumentumok létrehozásához egy konfigurációkészlet létrehozása

Az ER formátumtervezővel elektronikus dokumentumok hozhatók létre Word-dokumentum formátumban. A következő ábrán egy példa látható az ilyen típusú formátumra. Fontos, hogy ez a formátum újrahasznosítja a meglévő ER-konfigurációt, amelyet eredetileg a jelentés OPENXML-formátumban történő előállítására terveztek.

Ahhoz, hogy megismerje ennek a folyamatnak a részleteit, hajtsa végre A Microsoft WORD formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése című feladat-útmutatót (a 7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677) üzleti folyamat része). A sablon importálása feladatútmutató lépésének részeként használja a következő Word-fájlokat sablonként az ER-formátumhoz:

- [Kifizetési jelentés mintája (SampleVendPaymDocReport.docx)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Kifizetési jelentés bekötött sablonja (SampleVendPaymDocReportBounded.docx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="building-a-configuration-to-import-data-from-incoming-electronic-documents"></a>Konfigurációs létrehozása az adatok importálásához a bejövő elektronikus dokumentumokból

Az ER-formátumtervezővel XML vagy szöveg formátumban írhatók le az adatimportáláshoz használni kívánt elektronikus dokumentumok. A tervezett formátumot használjuk a bejövő dokumentum elemzéséhez. Az ER formátumleképezés-tervező használható a tervezett formátum elemeinek a kötéséhez az adatmodellhez. 

Ahhoz, hogy megismerje ennek a folyamatnak a részleteit, hajtsa végre a Szükséges ER-konfigurációk létrehozása adatok importálásához egy külső fájlból című feladat-útmutatót (a 7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677) üzleti folyamat része). Az útmutató végrehajtásához használja a következő fájlokat:

- [ER-adatmodellkonfiguráció (1099model.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [ER-formátumkonfiguráció (1099format.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Minta a beérkező dokumentumra XML-formátumban (1099entries.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Minta a beérkező dokumentum adatinak kezelésére szolgáló munkafüzetre (1099entries.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202)

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

![A Globális adattár tartalma a Konfigurációs adattár oldalon](./media/er-overview-03.gif)

## <a name="additional-resources"></a>További erőforrások

- [Elektronikus jelentéskészítési (ER) konfigurációk létrehozása](electronic-reporting-configuration.md)
- [Elektronikus jelentéskészítési (ER) konfigurációk életciklusainak kezelése](general-electronic-reporting-manage-configuration-lifecycle.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]