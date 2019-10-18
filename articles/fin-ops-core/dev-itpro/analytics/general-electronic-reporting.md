---
title: Elektronikus jelentéskészítés (ER) áttekintése
description: Ez a témakör az Elektronikus jelentéskészítés eszközről nyújt áttekintést. Tájékoztatást nyújt az alapfogalmakról, az Elektronikus jelentéskészítés által támogatott esetekről, valamint az Elektronikus jelentéskészítés megoldás részeként megtervezett és kibocsátott formátumok listájáról.
author: NickSelin
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33ce7b5418ab9e1a9abd6c3206c74c5a1cf739a3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181887"
---
# <a name="electronic-reporting-er-overview"></a>Elektronikus jelentéskészítés (ER) áttekintése

[!include [banner](../includes/banner.md)]

Ez a témakör az Elektronikus jelentéskészítés eszközről nyújt áttekintést. Tájékoztatást nyújt az alapfogalmakról, az Elektronikus jelentéskészítés által támogatott esetekről, valamint az Elektronikus jelentéskészítés megoldás részeként megtervezett és kibocsátott formátumok listájáról.

Az elektronikus jelentés (ER) olyan eszköz, amelyet bejövő és kimenő elektronikus dokumentumok formázására egyaránt használhat, a különböző országok/régiók jogi követelményeinek megfelelően. Az ER lehetővé teszi, hogy ezeket a formátumokat a teljes életciklusuk során kezelje. Például alkalmazhat új jogszabályi követelményeket, és létrehozhat üzleti dokumentumokat a kívánt formátumban, annak érdekében, hogy elektronikusan információt cseréljen kormányzati testületekkel, bankokkal és egyéb felekkel.

Az ER-motor a fejlesztők helyett az üzleti felhasználóknak készült. Mivel nem kódokat, hanem formátumokat konfigurál, az elektronikus dokumentumok formátumának létrehozása és beállítása gyorsabb és könnyebb.

Az ER jelenleg a TEXT, XML, Microsoft Word dokumentumokat és OPENXML munkalap-formátumokat támogatja. Azonban egy kiterjesztési felület további formátumok támogatását biztosítja.

## <a name="capabilities"></a>Képességek
Az ER motor a következő képességekkel rendelkezik:

- Egyetlen megosztott eszközt képvisel a különböző tartományokban történő elektronikus jelentésekhez, és több mint 20 különböző motort helyettesít, amelyek az elektronikus jelentés valamely típusára képesek a Finance and Operations alkalmazásokban.
- A jelentés formátumát elkülöníti jelenlegi megvalósítástól. Más szóval a formátum különböző verziókban is használható.
- Támogatja egy egyéni formátum létrehozását, ami az eredeti formátumon alapul. Emellett képes automatikusan frissíteni az egyéni formátumot, ha változás történik az eredeti formátumban új honosítási/személyre szabási követelmények miatt.
- Ez válik az elsődleges, szabványos eszközzé a honosítási követelmények támogatására az elektronikus jelentésekben, mind a Microsoft-nál, mind a Microsoft partnereinél.
- Támogatja a formátumok elosztását a partnerek és a vevők részére, a Microsoft Dynamics Lifecycle Services (LCS) rendszeren keresztül.

## <a name="key-concepts"></a>Alapfogalmak
### <a name="components"></a>Összetevők

Az ER két összetevő-típust támogat: **Adatmodell** és **Formátum**.

#### <a name="data-model-components"></a>Adatmodell összetevők

Az adatmodell-összetevő az adatszerkezet absztrakt ábrázolása. Egy adott üzleti területet leírására szolgál elegendő részletességgel ahhoz, hogy megfeleljen a terület jelentési követelményeinek. Egy adatmodell-összetevő a következő részekből áll:

- Egy adatmodell, ami a területspecifikus üzleti entitások egy csoportja, és egy hierarchikusan felépített kapcsolatrendszer ezen entitások között.
- Egy modell-leképezés, amely összekapcsolja az alkalmazás-adatforrásokat az adatmodell adott, egyes elemeivel a futási időben, valamint az adatfolyam, és az üzleti adatok feltöltésének szabályai az adatmodell-összetevőbe.

Egy adatmodell üzleti entitását egy tároló (rekord) képviseli. Az üzleti entitások tulajdonságai adatelemként (mezőként) jelennek meg. Minden adatelem egyedi névvel, címkével, leírással és értékkel rendelkezik. Az egyes adatelemek értékeit megszerkesztheti, hogy karakterláncként, egész számként, valós számként, dátumként, enumerációként, logikai értékként vagy egyéb változóként legyenek kiolvasva. Továbbá lehet másik rekord vagy rekordlista is.

Egyetlen adatmodell-összetevő több tartományspecifikus üzletientitás-hierarchiát tartalmazhat. Modell-hozzárendeléseket is tartalmazhat, amelyek támogatják a jelentésspecifikus adatáramlást futásidőben. A hierarchiákat egyetlen rekord különbözteti meg, amit a modell-hozzárendelés gyökerének választott ki. Például, a fizetési tartomány adatmodellje támogathatja a következő leképezéseket:

- Vállalat \> Szállító \> Az AP tartomány kifizetési tranzakciói
- Vevő \> Vállalat \> Az AR tartomány kifizetési tranzakciói

Vegyük figyelembe, hogy az üzleti entitásokat (úgy mint a vállalat és a fizetési tranzakciók) egyszer hozza létre. Ezután különböző hozzárendelések újrahasználják őket.

A modell-hozzárendelés, amely támogatja a kimenő elektronikus dokumentumokat, a következő lehetőségeket kínálja:

- Használhat különböző adattípusokat az adatmodell adatforrásaként. Használhat például táblázatokat, adatentitásokat, módszereket vagy felsorolásokat.
- Olyan felhasználói bemeneti paramétereket támogat, amelyeket meghatározhat az adatmodell adatforrásaiként, amikor bizonyos adatokat a futási időben kell megadni.
- Támogatja az adatok átalakítását a szükséges csoportokba. Az adatok szűrését, rendezését és összegzését is lehetővé teszi, továbbá logikai számított mezők hozzáfűzését a Microsoft Excel képleteihez hasonló képletekkel, a következő ábrán látható módon. További tudnivalókért lásd: [Képletszerkesztő elektronikus jelentésekhez](general-electronic-reporting-formula-designer.md)).

[![Képletszerkesztő](./media/ER-overview-01.png)](./media/ER-overview-01.png)

A modell-hozzárendelés, amely támogatja a bejövő elektronikus dokumentumokat, a következő lehetőségeket kínálja:

- Különböző frissíthető adatelemeket használhat célként. Ezek az adatelemek lefedik a táblákat, az entitásokat és a nézeteket is. A bejövő elektronikus dokumentumok adatai alapján lehet frissíteni az adatokat. Egy modell hozzárendelésben több cél is használható.
- Olyan felhasználói bemeneti paramétereket támogat, amelyeket meghatározhat az adatmodell adatforrásaiként, amikor bizonyos adatokat a futási időben kell megadni.

Minden üzleti tartományhoz készül egy adatmodell-összetevő, amelyet egységes adatforrásként kell használni a jelentésekhez, és amely elkülöníti a jelentéskészítést az adatforrások fizikai megvalósításától. Olyan módon képezi le a tartományspecifikus üzleti fogalmakat és funkciókat, amely hatékonyabbá teszi a jelentésformátum kezdeti tervét és további karbantartását.

#### <a name="format-components-for-outgoing-electronic-documents"></a>Kimenő elektronikus dokumentumok komponensformázása

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

#### <a name="format-components-for-incoming-electronic-documents"></a>Bejövő elektronikus dokumentumok komponensformázása
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

Az ER formátum összetevőinek hozzáférése függ az ország/terület ISO kódjának beállításától. Ha ez a beállítás nincs bejelölve a formátum beállítások kiválasztott verziójánál, akkor a formátum összetevők elérhetőek bármely vállalatnál a futási idő során. Ha ez a beállítás tartalmazza az ország/régió ISO kódját, akkor a formátum összetevője csak abból a vállalatból érhető el, amely elsődleges címének egy formátum-összetevő ország/terület ISO kódja van megadva.

Előfordulhat, hogy az adatformátum-összetevők különböző verziói más ország/terület ISO kód beállításaival rendelkeznek.

#### <a name="configuration"></a>Konfiguráció

Az ER-konfiguráció egy adott ER-összetevő csomagolója. Az összetevő lehet adatmodell-összetevő vagy formátum-összetevő. A konfiguráció tartalmazhatja egy ER-összetevő különböző verzióit. Az egyes konfigurációk tulajdonosa egy konkrét konfigurációs szolgáltatóként van megjelölve. Egy konfiguráció összetevőjének **Vázlat** verziója akkor szerkeszthető, amikor a konfiguráció tulajdonosa aktív szolgáltatóként van beállítva az alkalmazás ER-beállításokban.

Minden modellkonfiguráció tartalmaz egy adatmodell összetevőt. Új formátumkonfiguráció származtatható egy bizonyos adatmodell konfigurációból. A létrehozott formátumkonfiguráció a konfigurációfában az eredeti adatmodell-konfiguráció leszármazottjaként jelenik meg.

A létrehozott formátumbeállítás tartalmaz egy formátum-összetevőt. Ez eredeti modell konfiguráció adatmodell komponense automatikusan beillesztésre kerül a leszármazott formátumkonfiguráció formátum komponensébe alapértelmezett adatforrásként.

Az ER-konfiguráció megosztásra kerül az alkalmazás vállalatok számára.

#### <a name="provider"></a>Szolgáltató

Az ER-szolgáltató az a félazonosító, amely az egyes ER-konfigurációk szerzőjét (tulajdonosát) meghatározza. ER segítségével kezelheti a konfigurációs szolgáltatók listáját. A Finance and Operations megoldás részeként kiadott elektromos dokumentumokra érvényes formátumkonfigurációk tulajdonosa a **Microsoft** konfigurációs szolgáltató.

Új ER-szolgáltató regisztrálási módjának megismeréséhez játssza le a feladat-útmutatót: **ER Konfigurációszolgáltató létrehozása és megjelölése aktívként** (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

#### <a name="repository"></a>Tárház

Egy ER tárház ER konfigurációkat tárol. A következő típusú ER tárházak támogatottak jelenleg: 

- LCS megosztott tár
- LCS-projekt
- Fájlrendszer
- Jogszabályban előírt konfigurációs szolgáltatások (RCS)
- Üzemi erőforrások


Egy **LCS megosztott könyvtár** tár a megosztott eszköztárbó elérést biztosít a konfigurációk listájához a közös eszköz könyvtárban a Lifecycle Services (LCS) szolgáltatásban. Az ilyen típusú ER tárházat csak a Microsoft-szolgáltatóhoz lehet regisztrálni. Az LCS közös eszköz tárból importálhatja a legújabb verzióit az ER konfigurációknak az aktuális példányba.

Az **LCS projekt** tárház hozzáférést biztosít egy bizonyos, a tárház regisztrációs szakaszában kiválasztott LCS projekt konfigurációinak listájához (LCS projekt eszköztár). Az ER lehetőséget biztosít a megosztott konfigurációk feltöltésére a jelenlegi példányból egy adott **LCS-projekt** tárházba. Importálhat továbbá konfigurációkat egy **LCS-projekt** tárházából a Finance and Operations jelenlegi példányába.

A **Fájlrendszer** adattár hozzáférést nyújt azokhoz a konfigurációk listájához, amelyek XML-fájlként a berendezés helyi fájlrendszerének meghatározott mappájában vannak, ahol az AOS szolgáltatást tárolják. A szükséges mappát az adattár regisztrációs fázisában választják ki. Importálhat továbbá konfigurációkat egy **Fájlrendszer** adattárból a jelenlegi példányba. 

Vegye figyelembe, hogy ez a tárhelytípus elérhető a következő környezetekben:

- Fejlesztés céljából telepített felhőbeli környezetek (amelyek a csatolt csomagok tesztmodelljeit tartalmazzák)
- Helyben telepített környezetek (helyszíni)

További információ: [Elektronikus jelentéskészítési (ER) konfigurációk importálása](./electronic-reporting-import-ger-configurations.md).

Az **RCS példány** adattár hozzáférést biztosít a meghatározott RCS-példány konfigurációs listájához, amelyet az adattár regisztrációs fázisában választottak ki. Az ER segítségével befejezett vagy megosztott konfigurációkat importálhat a kiválasztott RCS-példányból a jelenlegi példányba, amelyet aztán elektronikus jelentéskészítésre használhatnak fel.

További információért lásd: [Elektronikus jelentéskészítési (ER) konfigurációk importálása a jogszabályban előírt konfigurációs szolgáltatásból (RCS)](./rcs-download-configurations.md)

Az **Operations-erőforrások** tárház hozzáférést biztosít azon konfigurációk listájához, melyeket kezdetben a a alkalmazásmegoldás részeként a Microsoft szállít mint ER-konfigurációszolgáltató. Ezek a konfigurációk importálhatóak a jelenlegi munkamenetbe és felhasználhatóak elektronikus jelentés céljából vagy egyszerű feladatútmutatók lejátszásához. Használhatóak ezen kívül további lokalizációkhoz és testreszabásokhoz. Vegye figyelembe, hogy a Microsoft által bizosított legfrissebb ER konfigurációkat az LCS megosztott eszköztárból kell importálni a megfelelő ER tárház használatával.

A szükséges **LCS-projekt**, **Fájlrendszer**, és **Jogszabályban előírt konfigurációs szolgáltatás** adattárakat külön-külön is lehet regisztrálni az aktuális példány minden egyes konfigurációs szolgáltatójára. Minden tárház hozzárendelhető egy bizonyos konfigurációs szolgáltatóhoz.

## <a name="supported-scenarios"></a>Támogatott esetek
### <a name="building-a-data-model"></a>Adatmodell létrehozása

Az ER modelltervezőt biztosít egy bizonyos üzleti tartomány adatmodelljeinek építésére. Minden tartományspecifikus üzleti entitás és a köztük lévő kapcsolat beállítható adatmodellként egy hierarchikus struktúrában. A következő ábrán egy példa látható az ilyen típusú adatmodellekre (a fizetési tartomány adatmodell).

[![Fizetési tartomány adatmodell](./media/ER-overview-04.png)](./media/ER-overview-04.png)

Ahhoz, hogy megismerje ennek a folyamatnak a részleteit játssza le az **ER tartományspecifikus adatmodell kialakítása** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része), hogy megismerkedjen a folyamat részleteivel.

### <a name="translating-data-model-content"></a>Az adatok modell tartalmának fordítása

Az adatok modell tartalma (címke és leírás) lefordítható más, az alkalmazás által támogatott nyelvre. Érdemes lehet az adatok modell tartalmának fordítása a következő okok miatt:

- Hogy tervezés közben érthetőbb legyen az idegen nyelvű formátumtervezők számára, akik adatmodellt fognak használni a formátum-összetevők adatleképezéséhez
- Hogy a felület felhasználóbarátabb legyen futtatás közben a rákérdezések és a futtatási paraméterek súgójának megjelenítésekor, valamint a konfigurált ellenőrzési üzenetek (hibák, figyelmeztetések) megjelenítésekor a bejelentkezett felhasználó preferált nyelven.

A következő illusztráció bemutat egy példát arra az esetre, amikor az adatmodell tartalmát angolról japánra fordítjuk le.

[![Adatmodell tartalma angolul](./media/ER-overview-05.png)](./media/ER-overview-05.png)

[![Adatmodell tartalma japán nyelvre lefordítva](./media/ER-overview-06.png)](./media/ER-overview-06.png)

### <a name="configuring-data-model-mappings-for-outgoing-documents"></a>A kimenő dokumentumok adatmodell hozzárendeléseinek beállítása

Az ER biztosít egy modell-leképezés tervezőt, amely lehetővé teszi a felhasználó számára az általuk specifikus alkalmazás adatforrásokhoz tervezett adatmodellek leképezését. A leképezés alapján a rendszer az adatokat importálja futásidőben a kijelölt adatforrásokból az adatmodellbe. Az adatmodellt a rendszer ezután absztrakt adatforrásként használja a kimenő elektronikus dokumentumokat létrehozó ER-formátumokhoz. A következő ábra az ilyen adatmodell-leképezést szemlélteti (A Fizetési tartomány adatmodell **SEPA Kredit átutalás** modell-leképezése).

[![Egy adatmodell-leképezés példája](./media/ER-overview-07.png)](./media/ER-overview-07.png)

Az ezen forgatókönyv részleteinek megismeréséhez hajtsa végre az **ER modellfeltérképezés definiálása és adatforrások kiválasztása** feladatot, majd az **ER adatmodellezés térkép a kiválasztott adatforrásokhoz** feladatútmutatókat (a **7.5.4.3 IT szolgáltatás/megoldás megszerzése/kifejlesztése elemek (10677))** üzleti folyamat része)

### <a name="configuring-data-model-mappings-for-incoming-documents"></a>A bejövő dokumentumok adatmodell hozzárendeléseinek beállítása
Az ER biztosít egy modell-leképezés tervezőt, amely lehetővé teszi a felhasználó számára az általuk specifikus célokhoz tervezett adatmodellek leképezését. Az adatmodellek például frissíthető adatösszetevőkhöz (táblák, adatentitások és nézetek) rendelhetők. A leképezés alapján a rendszer futásidőben frissíti az adatokat, az adatmodellből származó adatok felhasználásával. Az ER-formátum absztrakt tárolásaként az adatmodell ki van töltve a bejövő elektronikus dokumentumból importált adatokkal. A következő ábrán egy példa látható az ilyen típusú adatmodell-leképezésre. Ebben a példában a fizetési tartomány adatmodelljének **Megfeleltetés importálása NETS-hez** modell-hozzárendelését használjuk a banki kivonatok importálásának támogatására NETS banki formátumban Norvégia esetében.

[![Importálási leképezés NETS-adatmodellhez, példa](./media/ER-overview-08.png)](./media/ER-overview-08.png)

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>A létrehozott modell-összetevő tárolása modell-konfigurációként

Az ER képes a megtervezett adatmodellt a hozzárendelt adatfeltérképezésekkel modellkonfigurációként tárolni az aktuális példányban. A következő ábrán egy példa látható az ilyen típusú adatmodell-konfigurációkra (a fizetési modellkonfigurációra).

Ahhoz, hogy megismerje ennek a folyamatnak a részleteit, játssza le az **ER adatmodell-feltérképezés a kiválasztott adatforrásokhoz** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Formátum létrehozása adatmodell alapként való kijelölésével

Az ER támogatja azt a formátumtervezőt, amely az elektromos dokumentum formátumának tervezésére szolgál a kiválasztott üzleti tartomány számára, úgy, hogy a modell-összetevőt alapként választja ki. Ugyanaz az ER formátumtervező képes arra, hogy feltérképezzen egy Ön által létrehozott, egy adott tartomány adatmodell-feltérképezését adatforrásként használó formátumot. A következő ábrán egy példát láthat erre a típusú formátumra (olyan formátumkonfiguráció, ami támogatja a **BACS** fizetési formátumot az Egyesült Királyságban).

[![Példa egy adatmodell-alapú formátumra](./media/ER-overview-09.png)](./media/ER-overview-09.png)

Ahhoz, hogy megismerje ennek a folyamatnak a részleteit hajtsa végre az **ER tartományspecifikus adatmodell kialakítása** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Az OPENXML munkafüzet formátumban elektronikus dokumentumok létrehozásához egy konfigurációkészlet létrehozása

Az ER formátumtervezővel elektronikus dokumentumok hozhatók létre OPENXML munkalap-formátumban. Az alábbi ábra egy ilyen típusú formátum példája (olyan formátumkonfiguráció, mellyel OPENXML munkalap hozható létre, a kiválasztott fizetési napló részleteivel).

[![Pic-ER-format-Excel](./media/ER-overview-10.png)](./media/ER-overview-10.png)

Ahhoz, hogy megismerje ennek a folyamatnak a részleteit hajtsa végre az **ER jelentés konfigurálása OPENXML formátumban** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része). A sablon importálása feladatútmutató lépésének részeként használja a következőt: [Kifizetési jelentés mintája (SampleVendPaymWsReport.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202) Excel-fájl sablonként.

### <a name="building-a-configuration-to-generate-electronic-documents-in-a-word-document-format"></a>A Word-dokumentum formátumban elektronikus dokumentumok létrehozásához egy konfigurációkészlet létrehozása
Az ER formátumtervezővel elektronikus dokumentumok hozhatók létre Word-dokumentum formátumban. A következő ábrán egy példa látható az ilyen típusú formátumra. Fontos, hogy ez a formátum újrahasznosítja a meglévő ER-konfigurációt, amelyet eredetileg a jelentés OPENXML-formátumban történő előállítására terveztek.

[![Pic-ER-format-Word](./media/ER-overview-11.png)](./media/ER-overview-11.png)

Ahhoz, hogy megismerje ennek a folyamatnak a részleteit, hajtsa végre A Microsoft WORD formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése című feladat-útmutatót (a 7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677) üzleti folyamat része). A sablon importálása feladatútmutató lépésének részeként használja a következő Word-fájlokat sablonként az ER-formátumhoz:

- [Kifizetési jelentés mintája (SampleVendPaymDocReport.docx)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Kifizetési jelentés bekötött sablonja (SampleVendPaymDocReportBounded.docx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="building-a-configuration-to-import-data-from-incoming-electronic-documents"></a>Konfigurációs létrehozása az adatok importálásához a bejövő elektronikus dokumentumokból
Az ER-formátumtervezővel XML vagy szöveg formátumban írhatók le az adatimportáláshoz használni kívánt elektronikus dokumentumok. A tervezett formátumot használjuk a bejövő dokumentum elemzéséhez. Az ER formátumleképezés-tervező használható a tervezett formátum elemeinek a kötéséhez az adatmodellhez. A következő ábra egy példát mutat be a formátumnak és a formátumleképezésnek erre a típusára. Ebben a példában olyan NETS banki kivonatokat importálunk, amelyek szöveges formátumban tartalmazzák a szállító fizetési adatait.

[![ER-format-designer](./media/ER-overview-12.png)](./media/ER-overview-12.png)

[![ER-model-mapping-designer](./media/ER-overview-13.png)](./media/ER-overview-13.png)

Ahhoz, hogy megismerje ennek a folyamatnak a részleteit, hajtsa végre a Szükséges ER-konfigurációk létrehozása adatok importálásához egy külső fájlból című feladat-útmutatót (a 7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677) üzleti folyamat része). Az útmutató végrehajtásához használja a következő fájlokat:

- [ER-adatmodellkonfiguráció (1099model.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [ER-formátumkonfiguráció (1099format.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Minta a beérkező dokumentumra XML-formátumban (1099entries.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Minta a beérkező dokumentum adatinak kezelésére szolgáló munkafüzetre (1099entries.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Egy megtervezett formátumösszetevő tárolása a formátumkonfigurációban

Az ER képes a megtervezett formátumnak a konfigurált adatfeltérképezésekkel történő együttes tárolására formátumkonfigurációként az aktuális példányban. Az előző illusztrációban egy példa szerepel erre a típusú formátumkonfigurációra (**BACS (UK)**, ami a **Kifizetési modell** konfigurációból van származtatva). Ahhoz, hogy megismerje ennek a folyamatnak a részleteit hajtsa végre az **ER tartományspecifikus adatmodell kialakítása** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

### <a name="configuring-finance-to-start-to-use-a-created-format-internally"></a>A Finance konfigurálása a létrehozott formátum belső használatához

Az alkalmazás beállítható úgy, hogy az elektronikus jelentések generálásához egy már létrehozott formátumot használjon. A létrehozott formátum konfigurációjának hivatkozásához bizonyos tartományspecifikus beállításokat kell meghatározni. Például, egy ER formátumkonfiguráció használható az elektronikus szállítói kifizetésekhez BACS formátumban, ha a formátumkonfiguráció a kifizetések módjánál külön le van hivatkozva, ahogyan a következő illusztrációkon is látható:

[![BACS (UK) formátumkonfiguráció](./media/ER-overview-14.png)](./media/ER-overview-14.png)

[![Hivatkozás a BACS (UK) formátumra a kifizetés módjánál](./media/ER-overview-15.png)](./media/ER-overview-15.png)

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

## <a name="list-of-er-configurations-that-are-delivered-in-the-finance-application"></a>A Finance alkalmazás megoldásra küldött ER-konfigurációk listája

| Tartományspecifikus adatmodell-konfigurációk: Cím | Tartomány                | Adatmodell-függő formátumkonfigurációk: Cím | Leírás                                                        |
|--------------------------------------------------|-----------------------|---------------------------------------------------|--------------------------------------------------------------------|
| Könyvvizsgálati fájlmodell                                 | Pénzügyi ellenőrzés       |                                                   |                                                                    |
|                                                  |                       | Könyvvizsgálati fájl (NL)                                   | Holland könyvvizsgálati fájlformátum                                  |
| BAS modell                                        | Adójelentés         |                                                   |                                                                    |
|                                                  |                       | BAS (AU)                                          | Ausztrál BAS formátum                                           |
| Építőipari sémamodell               | Adójelentés         |                                                   |                                                                    |
|                                                  |                       | CIS havi visszáru (UK)                           | Egyesült Királyság-beli havi CIS visszatérítése formátum                   |
| Fizetési felszólítás modell                          | Elektronikus számlázás  |                                                   |                                                                    |
|                                                  |                       | OIOUBL Fizetési felszólítás (DK)                     | Dán OIOUBL fizetési felszólítás formátum                        |
| Elektronikus főkönyvi számlamodell (MX)          | Adójelentés         |                                                   |                                                                    |
|                                                  |                       | Kiegészítő főkönyv XML (MX)                         | Mexikói számlajelentésekhez tartozó kiegészítő főkönyvi tranzakcióformátum |
|                                                  |                       | Számlatükör XML (MX)                         | Mexikói számlatükör-jelentés formátum                          |
|                                                  |                       | Naplók XML (MX)                                 | Mexikói naplótranzakciók jelentésformátuma                      |
|                                                  |                       | Főkönyvi kivonat XML (MX)                            | Mexikói főkönyvi kivonat jelentésformátuma                             |
| Elster-modell                                     | Adójelentés         |                                                   |                                                                    |
|                                                  |                       | Elster (DE)                                       | Német Elster formátum                                          |
| EU értékesítési lista modell                              | Kereskedelmi jelentés       |                                                   |                                                                    |
|                                                  |                       | EU értékesítési lista (DE)                                | Német EU-s értékesítési lista TXT-formátumban                               |
|                                                  |                       | EU értékesítési lista (DK)                                | Dán EU-s értékesítési lista TXT-formátumban                               |
|                                                  |                       | EU értékesítési lista (FR)                                | Francia EU-s értékesítési lista XML-formátumban                                |
|                                                  |                       | EU értékesítési lista (NL)                                | Holland EU-s értékesítési lista XML-formátumban                           |
|                                                  |                       | EU értékesítési lista TXT-formátumban (UK)                            | Egyesült Királyság-beli EU-s értékesítési lista TXT-formátumban                    |
|                                                  |                       | EU értékesítési lista XML-formátumban (UK)                            | Egyesült Királyság-beli EU-s értékesítési lista XML-formátumban                    |
|                                                  |                       | EU értékesítési lista oszlopok szerinti jelentés                   | EU értékesítési lista oszlopok szerinti jelentés                                    |
|                                                  |                       | EU értékesítési lista sorok szerinti jelentés                      | EU értékesítési lista sorok szerinti jelentés                                       |
| FEC Könyvelési modell (FR)                        | Adójelentés         |                                                   |                                                                    |
|                                                  |                       | FEC könyvelési adat XML-formátumban (FR)                      | FEC könyvelési adatok exportálása XML-formátumban, Franciaország                   |
| Német könyvvizsgálati fájl                                | Pénzügyi ellenőrzés       |                                                   |                                                                    |
|                                                  |                       | Német könyvvizsgálati kimeneti fájl                          | Németország és Ausztria kimeneti fájl                          |
| Intrastat modell                                  | Kereskedelmi jelentés       |                                                   |                                                                    |
|                                                  |                       | Intrastat (DE)                                    | Német Intrastat formátum                                       |
|                                                  |                       | Intrastat (DK)                                    | Dán Intrastat formátum                                       |
|                                                  |                       | Intrastat INTRACOM (FR)                           | Francia INTRACOM formátum                               |
|                                                  |                       | Intrastat SAISUNIC (FR)                           | Francia SAISUNIC formátum                               |
|                                                  |                       | Intrastat (NL)                                    | Holland Intrastat formátum                               |
|                                                  |                       | Intrastat (UK)                                    | Egyesült Királyság-beli Intrastat formátum                            |
|                                                  |                       | Intrastat jelentés                                  | Intrastat Excel kontrolljelentés                                     |
| Vevői számlamodell                           | Elektronikus számlázás  |                                                   |                                                                    |
|                                                  |                       | OIOUBL Projektjóváírás (DK)                   | Dán OIOUBL projektjóváírási formátum                      |
|                                                  |                       | OIOUBL Projektszámla (DK)                       | Dán OIOUBL projektszámla formátum                          |
|                                                  |                       | OIOUBL Értékesítési jóváírás (DK)                     | Dán OIOUBL értékesítési jóváírás formátuma                        |
|                                                  |                       | OIOUBL Eladási számla (DK)                         | Dán OIOUBL eladási számlaformátum                            |
| OB nyilatkozatmodell                             | Adójelentés         |                                                   |                                                                    |
|                                                  |                       | OB nyilatkozat (NL)                               | Holland OB nyilatkozat formátum                          |
| Fizetési modell                                    | Fizetések              |                                                   |                                                                    |
|                                                  |                       | Betalingsservice (DK)                             | Dán Betalingsservice fizetési formátum                        |
|                                                  |                       | Váltó átutalása (FR)                  | Váltó átutalása formátum, Franciaország                      |
|                                                  |                       | BTL91 (NL)                                        | Holland BTL91 szállítói kifizetés formátum                    |
|                                                  |                       | CFONB Prelevements (FR)                           | CFONB beszedési megbízás formátum, Franciaország                       |
|                                                  |                       | CFONB Virements (FR)                              | CFONB hazai szállítói kifizetés, Franciaország                    |
|                                                  |                       | Nordea-szállító (DK)                                | Dán Nordea vállalati netbankos szállítói kifizetési formátum         |
|                                                  |                       | ANZ közvetlen jóváírási szolgáltatás (AU)                    | Ausztrál ANZ közvetlen kifizetési szolgáltatás formátum                 |
|                                                  |                       | CBA közvetlen jóváírási szolgáltatás (AU)                    | Ausztrál CBA közvetlen kifizetési szolgáltatás formátum                 |
|                                                  |                       | NAB közvetlen jóváírási szolgáltatás (AU)                    | Ausztrál NAB közvetlen kifizetési szolgáltatás formátum                 |
|                                                  |                       | STG közvetlen jóváírási szolgáltatás (AU)                    | Ausztrál STG közvetlen kifizetési szolgáltatás formátum                 |
|                                                  |                       | WBC közvetlen bejegyzési rendszer (AU)                      | Ausztrál WBC közvetlen bejegyzési rendszer formátum                   |
|                                                  |                       | DirectLink (NZ)                                   | Új-zélandi DirectLink formátum                              |
|                                                  |                       | JBA Fizetési fájl (JP)                             | Japán JBA fizetési formátum                                       |
|                                                  |                       | ISO20022 Jóváírás átutalása                          | Európai SEPA jóváírásátviteli formátum                             |
|                                                  |                       | ISO20022 Jóváírásátutalás (FR)                     | Francia SEPA jóváírásátviteli formátum                             |
|                                                  |                       | ISO20022 Jóváírásátutalás (DE)                     | Német SEPA jóváírásátviteli formátum                            |
|                                                  |                       | ISO20022 Jóváírásátutalás (NL)                     | Holland SEPA jóváírásátviteli formátum                    |
|                                                  |                       | ISO20022 Beszedési megbízás                             | Európai SEPA beszedési formátum                                |
|                                                  |                       | ISO20022 Beszedési megbízás (FR)                        | Francia SEPA beszedési megbízás formátum                                |
|                                                  |                       | ISO20022 Beszedési megbízás (DE)                        | Német SEPA beszedési megbízás formátum                               |
|                                                  |                       | ISO20022 Beszedési megbízás (NL)                        | Holland SEPA beszedési megbízás formátum                       |
|                                                  |                       | BACS (UK)                                         | Egyesült Királyság-beli BACS szállítói visszatérítés formátum                  |
| Fordított fizetés                                   | Adójelentés         |                                                   |                                                                    |
|                                                  |                       | Fordított fizetési értékesítési lista                         | Fordított fizetési értékesítési lista formátum                                   |
| Holland XBRL integrációs modell                     | XBRL-jelentéskészítés        |                                                   |                                                                    |
|                                                  |                       | Semansys XBRL (NL)                                | Holland Semansys XBRL exportálási formátum                    |
| GAF modell (MY)                                   | Pénzügyi ellenőrzés       |                                                   |                                                                    |
|                                                  |                       | GAF fájl (MY)                                     | Maláj GAF formátum                                         |
| Szállítói korosítási jelentés (CN)                         | Szállítói adatok elemzése |                                                   |                                                                    |
|                                                  |                       | Szállítói korosítási jelentés formátum (CN)                   | Kínai szállítói korosítási jelentés formátum                               |
| Szállítói számla bevallása modell                 | Szállítói adatok elemzése |                                                   |                                                                    |
|                                                  |                       | Szállítói számla bevallása (IS)                   | Izlandi szállítói számla nyilatkozat formátum                      |
|                                                  |                       | Szállítói számla bevallásjelentés (IS)            | Izlandi szállítói számla nyilatkozatjelentés                      |

## <a name="additional-resources"></a>További erőforrások

- [H honosítási követelményeknek – Elektronikus jelentési konfiguráció létrehozása](electronic-reporting-configuration.md)
- [Elektronikus jelentéskészítési konfigurációk életciklusainak kezelése](general-electronic-reporting-manage-configuration-lifecycle.md)
