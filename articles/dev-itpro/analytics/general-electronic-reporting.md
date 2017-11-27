---
title: "Az Elektronikus jelentéskészítés áttekintése"
description: "Ez a témakör az Elektronikus jelentéskészítés eszközről nyújt áttekintést. Tájékoztatást nyújt az alapfogalmakról, az Elektronikus jelentéskészítés által támogatott esetekről, valamint az Elektronikus jelentéskészítés megoldás részeként megtervezett és kibocsátott formátumok listájáról."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ea9550b7209064a2842d7e5efe55e9e51c23b9f8
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="electronic-reporting-overview"></a>Elektronikus jelentések áttekintése

[!include[banner](../includes/banner.md)]


Ez a témakör az Elektronikus jelentéskészítés eszközről nyújt áttekintést. Tájékoztatást nyújt az alapfogalmakról, az Elektronikus jelentéskészítés által támogatott esetekről, valamint az Elektronikus jelentéskészítés megoldás részeként megtervezett és kibocsátott formátumok listájáról.

Az elektronikus jelentés (ER) olyan eszköz, amelyet bejövő és kimenő elektronikus dokumentumok formázására egyaránt használhat, a különböző országok/régiók jogi követelményeinek megfelelően. Az ER lehetővé teszi, hogy ezeket a formátumokat a teljes életciklusuk során kezelje. Például alkalmazhat új jogszabályi követelményeket, és létrehozhat üzleti dokumentumokat a kívánt formátumban, annak érdekében, hogy elektronikusan információt cseréljen kormányzati testületekkel, bankokkal és egyéb felekkel.

Az ER-motor a fejlesztők helyett az üzleti felhasználóknak készült. Mivel nem kódokat, hanem formátumokat konfigurál, az elektronikus dokumentumok formátumának létrehozása és beállítása gyorsabb és könnyebb.

Az ER jelenleg a TEXT, XML, Microsoft Word dokumentum és OPENXML munkalap-formátumokat támogatja. Azonban egy kiterjesztési felület további formátumok támogatását biztosítja.

## <a name="capabilities"></a>Képességek
Az ER motor a következő képességekkel rendelkezik:

- Egységes, megosztott eszközt képvisel a különböző tartományokban történő elektronikus jelentésekhez, és több mint 20 különböző motort helyettesít, amelyek az elektronikus jelentés valamely típusára képesek a Microsoft Dynamics 365 for Finance and Operations rendszerben.
- A jelentés formátumát elkülöníti jelenlegi Dynamics 365 for Finance and Operations rendszertől. Más szóval a formátum a Dynamics 365 for Finance and Operations különböző verzióiban is használható.
- Támogatja egy egyéni formátum létrehozását, ami az eredeti formátumon alapul. Emellett képes automatikusan frissíteni az egyéni formátumot, ha változás történik az eredeti formátumban új honosítási/személyre szabási követelmények miatt.
- Ez válik az elsődleges, szabványos eszközzé a honosítási követelmények támogatására az elektronikus jelentésekben, mind a Microsoft-nál, mind a Microsoft partnereinél.
- Támogatja a formátumok elosztását a partnerek és a vevők részére, a Microsoft Dynamics Lifecycle Services (LCS) rendszeren keresztül.

## <a name="key-concepts"></a>Alapfogalmak
### <a name="components"></a>Összetevők

Az ER két összetevő-típust támogat: **Adatmodell** és **Formátum**.

#### <a name="data-model-components"></a>Adatmodell összetevők

Az adatmodell-összetevő az adatszerkezet absztrakt ábrázolása. Egy adott üzleti területet leírására szolgál elegendő részletességgel ahhoz, hogy megfeleljen a terület jelentési követelményeinek. Egy adatmodell-összetevő a következő részekből áll:

- Egy adatmodell, ami a területspecifikus üzleti entitások egy csoportja, és egy hierarchikusan felépített kapcsolatrendszer ezen entitások között.
- Egy modell-leképezés, amely összekapcsolja a Finance and Operations adatforrásokat az adatmodell adott, egyes elemeivel a futási időben, valamint az adatfolyam, és az üzleti adatok feltöltésének szabályai az adatmodell-összetevőbe.

Egy adatmodell üzleti entitását egy tároló (rekord) képviseli. Az üzleti entitások tulajdonságai adatelemként (mezőként) jelennek meg. Minden adatelem egyedi névvel, címkével, leírással és értékkel rendelkezik. Az egyes adatelemek értékeit megszerkesztheti, hogy karakterláncként, egész számként, valós számként, dátumként, enumerációként, logikai értékként vagy egyéb változóként legyenek kiolvasva. Továbbá lehet másik rekord vagy rekordlista is.

Egyetlen adatmodell-összetevő több tartományspecifikus üzletientitás-hierarchiát tartalmazhat. Modell-hozzárendeléseket is tartalmazhat, amelyek támogatják a jelentésspecifikus adatáramlást futásidőben. A hierarchiákat egyetlen rekord különbözteti meg, amit a modell-hozzárendelés gyökerének választott ki. Például, a fizetési tartomány adatmodellje támogathatja a következő leképezéseket:

- Vállalat > Szállító > Az AP tartomány kifizetési tranzakciói
- Vevő > Vállalat > Az AR tartomány kifizetési tranzakciói

Vegyük figyelembe, hogy az üzleti entitásokat (úgy mint a vállalat és a fizetési tranzakciók) egyszer hozza létre. Ezután különböző hozzárendelések újrahasználják őket.

A modell-hozzárendelés, amely támogatja a kimenő elektronikus dokumentumokat, a következő lehetőségeket kínálja:

- Használhat különböző Finance and Operations-adattípusokat az adatmodell adatforrásaként. Használhat például táblázatokat, adatentitásokat, módszereket vagy felsorolásokat.
- Olyan felhasználói bemeneti paramétereket támogat, amelyeket meghatározhat az adatmodell adatforrásaiként, amikor bizonyos adatokat a futási időben kell megadni.
- Támogatja a Finance and Operations adatok átalakítását a szükséges csoportokba. Az adatok szűrését, rendezését és összegzését is lehetővé teszi, továbbá logikai számított mezők hozzáfűzését a Microsoft Excel képleteihez hasonló képletekkel, a következő ábrán látható módon. További tudnivalókért lásd: [Képletszerkesztő elektronikus jelentésekhez](general-electronic-reporting-formula-designer.md)).

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
- Az összetevők újraszerializálhatóak XML fájlból, és importálhatóak a Finance and Operationsbe egy ER-összetevő új verziójaként.

#### <a name="component-date-effectivity"></a>Összetevő érvényességi dátuma

Az ER-összetevő verziói érvényességi dátumhoz kötöttek. Az ER-összetevőhöz beállítható az **Érvényesség kezdete** dátum, hogy meghatározzuk, mikortól lesz érvényes az összetevő a jelentési folyamatban. A Finance and Operations munkamenet dátuma arra használható, hogy meghatározzuk, érvényes-e az összetevő a végrehajtásra. Amennyiben egy bizonyos dátumhoz egynél több verzió is érvényes, a jelentési folyamathoz a legutóbbi verzió kerül felhasználásra.

#### <a name="component-access"></a>Összetevő hozzáférése

Az ER formátum összetevőinek hozzáférése függ az ország/terület ISO kódjának beállításától. Ha ez a beállítás nincs bejelölve a formátum beállítások kiválasztott verziójánál, akkor a formátum összetevők elérhetőek bármely vállalatnál a futási idő során. Ha ez a beállítás tartalmazza az ország/régió ISO kódját, akkor a formátum összetevője csak abból a vállalatból érhető el, amely elsődleges címének egy formátum-összetevő ország/terület ISO kódja van megadva.

Előfordulhat, hogy az adatformátum-összetevők különböző verziói más ország/terület ISO kód beállításaival rendelkeznek.

#### <a name="configuration"></a>Konfiguráció

Az ER-konfiguráció egy adott ER-összetevő csomagolója. Az összetevő lehet adatmodell-összetevő vagy formátum-összetevő. A konfiguráció tartalmazhatja egy ER-összetevő különböző verzióit. Az egyes konfigurációk tulajdonosa egy konkrét konfigurációs szolgáltatóként van megjelölve. Egy konfiguráció összetevőjének **Tervezet** verziója akkor szerkeszthető, amikor a konfiguráció tulajdonosa aktív szolgáltatóként van beállítva a Finance and Operations ER-beállításokban.

Minden modellkonfiguráció tartalmaz egy adatmodell összetevőt. Új formátumkonfiguráció származtatható egy bizonyos adatmodell konfigurációból. A létrehozott formátumkonfiguráció a konfigurációfában az eredeti adatmodell-konfiguráció leszármazottjaként jelenik meg.

A létrehozott formátumbeállítás tartalmaz egy formátum-összetevőt. Ez eredeti modell konfiguráció adatmodell komponense automatikusan beillesztésre kerül a leszármazott formátumkonfiguráció formátum komponensébe alapértelmezett adatforrásként.

Az ER-konfiguráció megosztásra kerül a Finance and Operations-vállalatok számára.

#### <a name="provider"></a>Szolgáltató

Az ER-szolgáltató az a félazonosító, amely az egyes ER-konfigurációk szerzőjét (tulajdonosát) meghatározza. ER segítségével kezelheti a konfigurációs szolgáltatók listáját. A Finance and Operations megoldás részeként kiadott elektromos dokumentumokra érvényes formátumkonfigurációk tulajdonosa a **Microsoft** konfigurációs szolgáltató.

Új ER-szolgáltató regisztrálási módjának megismeréséhez játssza le a feladat-útmutatót: **ER Konfigurációszolgáltató létrehozása és megjelölése aktívként** (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

#### <a name="repository"></a>Tárház

Egy ER tárház ER konfigurációkat tárol. Két típusú ER-tárház támogatott jelenleg: **Operations-erőforrások** és **LCS-projekt**.

Az **Operations-erőforrások** tárház hozzáférést biztosít azon konfigurációk listájához, melyeket a Finance and Operations megoldás részeként a Microsoft szállít mint ER-konfigurációszolgáltató,. Ezek a konfigurációk importálhatóak a jelenlegi Finance and Operations munkamenetbe és felhasználhatóak elektronikus jelentés céljából. Használhatóak ezen kívül további lokalizációkhoz és testreszabásokhoz.

Az **LCS projekt** tárház hozzáférést biztosít egy bizonyos, a tárház regisztrációs szakaszában kiválasztott LCS projekt konfigurációinak listájához (LCS projekt eszköztár). Az ER lehetőséget biztosít a megosztott konfigurációk feltöltésére a jelenlegi Finance and Operations példányból egy adott **LCS-projekt** tárházba. Importálhat továbbá konfigurációkat egy **LCS-projekt** tárházából a Finance and Operations jelenlegi példányába.

A szükséges **LCS-projekt** tárházak egyesével regisztrálhatók a jelenlegi Finance and Operations példány különböző konfigurációs szolgáltatóihoz. Minden tárház hozzárendelhető egy bizonyos konfigurációs szolgáltatóhoz.

## <a name="supported-scenarios"></a>Támogatott esetek
### <a name="building-a-data-model"></a>Adatmodell létrehozása

Az ER modelltervezőt biztosít egy bizonyos üzleti tartomány adatmodelljeinek építésére. Minden tartományspecifikus üzleti entitás és a köztük lévő kapcsolat beállítható adatmodellként egy hierarchikus struktúrában. A következő ábrán egy példa látható az ilyen típusú adatmodellekre (a fizetési tartomány adatmodell). 

[![Fizetési tartomány adatmodell](./media/ER-overview-04.png)](./media/ER-overview-04.png)

Ahhoz, hogy megismerje ennek a folyamatnak a részleteit játssza le az **ER tartományspecifikus adatmodell kialakítása** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része), hogy megismerkedjen a folyamat részleteivel.

### <a name="translating-data-model-content"></a>Az adatok modell tartalmának fordítása

Az adatok modell tartalma (címke és leírás) lefordítható más, a Finance and Operations által támogatott nyelvre. Érdemes lehet az adatok modell tartalmának fordítása a következő okok miatt:

-   Hogy tervezés közben érthetőbb legyen az idegen nyelvű formátumtervezők számára, akik adatmodellt fognak használni a formátum-összetevők adatleképezéséhez
-   Hogy a felület felhasználóbarátabb legyen futtatás közben a rákérdezések és a futtatási paraméterek súgójának megjelenítésekor, valamint a konfigurált ellenőrzési üzenetek (hibák, figyelmeztetések) megjelenítésekor a bejelentkezett felhasználó preferált nyelven.

A következő illusztráció bemutat egy példát arra az esetre, amikor az adatmodell tartalmát angolról japánra fordítjuk le. 

[![Adatmodell tartalma angolul](./media/ER-overview-05.png)](./media/ER-overview-05.png)

[![Adatmodell tartalma japán nyelvre lefordítva](./media/ER-overview-06.png)](./media/ER-overview-06.png)


### <a name="configuring-data-model-mappings-for-outgoing-documents"></a>A kimenő dokumentumok adatmodell hozzárendeléseinek beállítása

Az ER biztosít egy modell-leképezés tervezőt, amely lehetővé teszi a felhasználó számára az általuk specifikus Finance and Operations adatforrásokhoz tervezett adatmodellek leképezését. A leképezés alapján a rendszer az adatokat importálja futásidőben a kijelölt adatforrásokból az adatmodellbe. Az adatmodellt a rendszer ezután absztrakt adatforrásként használja a kimenő elektronikus dokumentumokat létrehozó ER-formátumokhoz. A következő ábra az ilyen adatmodell-leképezést szemlélteti (A Fizetési tartomány adatmodell **SEPA Kredit átutalás** modell-leképezése). 

[![Egy adatmodell-leképezés példája](./media/ER-overview-07.png)](./media/ER-overview-07.png)

Az ezen forgatókönyv részleteinek megismeréséhez hajtsa végre az **ER modellfeltérképezés definiálása és adatforrások kiválasztása** feladatot, majd az **ER adatmodellezés térkép a kiválasztott adatforrásokhoz** feladatútmutatókat (a **7.5.4.3 IT szolgáltatás/megoldás megszerzése/kifejlesztése elemek (10677))** üzleti folyamat része)

### <a name="configuring-data-model-mappings-for-incoming-documents"></a>A bejövő dokumentumok adatmodell hozzárendeléseinek beállítása
Az ER biztosít egy modell-leképezés tervezőt, amely lehetővé teszi a felhasználó számára az általuk specifikus célokhoz tervezett adatmodellek leképezését. Az adatmodellek például Finance and Operations frissíthető adatösszetevőkhöz (táblák, adatentitások és nézetek) rendelhetők. A leképezés alapján a rendszer futásidőben frissíti a Finance and Operations adatokat, az adatmodellből származó adatok felhasználásával. Az ER-formátum absztrakt tárolásaként az adatmodell ki van töltve a bejövő elektronikus dokumentumból importált adatokkal. A következő ábrán egy példa látható az ilyen típusú adatmodell-leképezésre. Ebben a példában a fizetési tartomány adatmodelljének **Megfeleltetés importálása NETS-hez** modell-hozzárendelését használjuk a banki kivonatok importálásának támogatására NETS banki formátumban Norvégia esetében.

[![Importálási leképezés NETS-adatmodellhez, példa](./media/ER-overview-08.png)](./media/ER-overview-08.png)

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>A létrehozott modell-összetevő tárolása modell-konfigurációként

Az ER képes a megtervezett adatmodellt a hozzárendelt adatfeltérképezésekkel modellkonfigurációként tárolni az aktuális Finance and Operations példányban. A következő ábrán egy példa látható az ilyen típusú adatmodell-konfigurációkra (a fizetési modellkonfigurációra). 

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

Az ER képes a megtervezett formátumnak a konfigurált adatfeltérképezésekkel történő együttes tárolására formátumkonfigurációként az aktuális Finance and Operations példányban. Az előző illusztrációban egy példa szerepel erre a típusú formátumkonfigurációra (**BACS (UK)**, ami a **Kifizetési modell** konfigurációból van származtatva). Ahhoz, hogy megismerje ennek a folyamatnak a részleteit hajtsa végre az **ER tartományspecifikus adatmodell kialakítása** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

### <a name="configuring-finance-and-operations-to-start-to-use-a-created-format-internally"></a>A Finance and Operations konfigurálása a létrehozott formátum belső használatához

A Finance and Operations beállítható úgy, hogy az elektronikus jelentések generálásához egy már létrehozott formátumot használjon. A létrehozott formátum konfigurációjának hivatkozásához bizonyos tartományspecifikus beállításokat kell meghatározni. Például, egy ER formátumkonfiguráció használható az elektronikus szállítói kifizetésekhez BACS formátumban, ha a formátumkonfiguráció a kifizetések módjánál külön le van hivatkozva, ahogyan a következő illusztrációkon is látható: 

[![BACS (UK) formátumkonfiguráció](./media/ER-overview-14.png)](./media/ER-overview-14.png)

[![Hivatkozás a BACS (UK) formátumra a kifizetés módjánál](./media/ER-overview-15.png)](./media/ER-overview-15.png)

Játssza le az **ER formátum használata elektronikus dokumentumok létrehozására a fizetésekhez** című feladatútmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része), hogy megismerje ennek az esetnek a részleteit.

## <a name="handling-er-components"></a>ER-összetevők kezelése
### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>ER-összetevő közzététele az LCS-ben külső használatra (lokalizáció)

A létrehozott összetevő (modell vagy formátum) tulajdonosa az ER segítségével közzé tudja tenni az összetevő kész verzióját az LCS-ben. Ehhez a folyamathoz az **LCS projekt** típus tárháza szükséges az aktuális ER konfigurációs szolgáltatónál. Ha az összetevő kész verziója **KÉSZ** státuszról **MEGOSZTOTT** státuszra módosul, a verziót közzéteszi a rendszer az LCS-ben. Ha egy összetevőt közzétettünk az LCS-ben, az összetevő tulajdonosa szolgáltatóvá válik az összetevő támogatása céljából. Például ha ezt a formátum-összetevőt egy jogilag kötelező elektromos dokumentum létrehozására tervezték (például a lokalizációs esettel összhangban), ez a szolgáltatás feltételezi azt, hogy ez a formátum megfelel a jogszabályi változtatásoknak és új verziókat tesz közzé, amikor az új jogszabályi követelményeket kell támogatni. Ahhoz, hogy megismerje ennek a folyamatnak a részleteit hajtsa végre az **ER konfiguráció feltöltése a Lifecycle Services-be** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>ER-összetevő importálása az LCS-ből belső használatra

Az ER lehetővé teszi az ER komponensek importálását az LCS-ből az aktuális Finance and Operations példányba. Az **LCS projekt** típus tárháza szükséges ehhez a folyamathoz. Amikor egy ER-összetevőt importáltak az LCS-ből az aktuális Finance and Operations példányba, akkor ennek a példánynak a tulajdonosa lesz annak a szolgáltatásnak a fogyasztója, amelyet az importált összetevő tulajdonosa (szerzője) kínál. Például, ha ez a formátum-összetevő arra szolgál, hogy a Finance and Operations szoftverből egy bizonyos elektronikus dokumentumot generáljon egy adott ország-/régióspecifikus formátumban (lokalizációs eset), akkor feltételezzük, hogy a felhasználó minden frissítést meg tud szerezni a jogi szabványoknak megfelelően. Ahhoz, hogy megismerje ennek a folyamatnak a részleteit hajtsa végre az **ER konfiguráció importálása a Lifecycle Services-ből** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Formátum létrehozása más formátum alapként való kijelölésével (testreszabás)

Az ER segítségével létrehozhat (származtathat) egy új komponenst az LCS-ből importált komponens (alap) jelenlegi verziójából. Például egy felhasználó új formátumot szeretne származtatni testreszabás támogatása érdekében az elektronikus dokumentum (például egy további mező vagy egy részletes leírást) néhány különleges követelményének végrehajtásához. Hajtsa végre az **ER formátum frissítése új alapverzió használatával** című feladatútmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része), hogy megismerje ennek az esetnek a részleteit.

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Formátum frissítése az alapformátum új verziójának kiválasztásával (új alap megadása)

Az ER automatikusan igazodik az alapösszetevő legújabb verziójához a származtatott összetevő jelenlegi vázlat-verziójában. Ennek a folyamatnak a neve *új alap* megadása. Például az LCS-ből importált formátum-összetevő legújabb verziójában megjelent új szabályozási módosítások automatikusan összevonhatók az elektronikus dokumentum a saját testreszabott verziójával. Az automatikusan nem egyesíthető módosítások ütközésnek minősülnek. Ezek az ütközések a megfelelő összetevőhöz tartozó tervezőeszközben manuális megoldásra megjelennek. Hajtsa végre az **ER formátum frissítése új alapverzió használatával** című feladatútmutatót (a **7.5.5.3 Módosított informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10683)** üzleti folyamat része), hogy megismerje ennek az esetnek a részleteit.

## <a name="list-of-er-configurations-that-are-delivered-in-the-finance-and-operations-solution"></a>A Finance and Operations megoldásra küldött ER-konfigurációk listája
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



<a name="see-also"></a>Lásd még
--------

[H honosítási követelményeknek – Elektronikus jelentési konfiguráció létrehozása](electronic-reporting-configuration.md)

[Elektronikus jelentéskészítési konfigurációk életciklusainak kezelése](general-electronic-reporting-manage-configuration-lifecycle.md)




