---
title: "Elektronikus jelentések áttekintése"
description: "Ez a cikk az Elektronikus jelentéskészítés eszközről nyújt áttekintést. Tájékoztatást nyújt az alapfogalmakról, az Elektronikus jelentéskészítés által támogatott esetekről, valamint az Elektronikus jelentéskészítés megoldás részeként megtervezett és kibocsátott formátumok listájáról."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: b3e8174d07c9b9fd4210486c369c640fe07c49eb
ms.lasthandoff: 03/31/2017


---

# <a name="electronic-reporting-overview"></a>Elektronikus jelentések áttekintése

Ez a cikk az Elektronikus jelentéskészítés eszközről nyújt áttekintést. Tájékoztatást nyújt az alapfogalmakról, az Elektronikus jelentéskészítés által támogatott esetekről, valamint az Elektronikus jelentéskészítés megoldás részeként megtervezett és kibocsátott formátumok listájáról.

Az elektronikus jelentés (ER) egy olyan eszköz, amelyet elektronikus dokumentumok formázására használhat, a különböző országok/régiók jogi követelményeinek megfelelően. Az ER lehetővé teszi, hogy ezeket a formátumokat a teljes életciklusuk során kezelje. Például alkalmazhat új jogszabályi követelményeket, és létrehozhat üzleti dokumentumokat a kívánt formátumban, annak érdekében, hogy elektronikusan információt cseréljen kormányzati testületekkel, bankokkal és egyéb felekkel. Az ER-motor a fejlesztők helyett az üzleti felhasználóknak készült. Mivel nem kódokat, hanem formátumokat konfigurál, az elektronikus dokumentumok formátumának létrehozása és beállítása gyorsabb és könnyebb. Az ER jelenleg a TEXT, XML és OPENXML munkalap-formátumokat támogatja. Azonban egy kiterjesztési felület több formátum támogatását biztosítja.

## <a name="capabilities"></a>Képességek
Az ER motor a következő képességekkel rendelkezik:

-   Egy egyetlen közös eszköz arra, hogy elektronikus jelentés különböző tartományokban, és több mint 20 különböző motorok, amelyek bizonyos típusú Microsoft Dynamics 365 műveletek elektronikus jelentés helyébe lép.
-   Így a jelentés formázása szigetelve a jelenlegi Dynamics 365 műveletek végrehajtásához. (Más szóval formátuma nem megfelelő Dynamics 365 műveletekhez különböző verzióinak.)
-   Támogatja egy egyéni formátum létrehozását, ami az eredeti formátumon alapul. Képes automatikusan frissíteni az egyéni formátumot, ha változás történik az eredeti formátumban új honosítási/személyre szabási követelmények bevezetése miatt.
-   Ez válik az elsődleges, szabványos eszközzé a honosítási követelmények támogatására az elektronikus jelentésekben, mind a Microsoft-nál, mind a Microsoft partnereinél.
-   Támogatja a formátumok elosztását a partnerek és a vevők részére, a Microsoft Dynamics Lifecycle Services (LCS) rendszeren keresztül.

## <a name="concepts"></a>Koncepció
### <a name="components"></a>Összetevők

Az ER két összetevő-típust támogat: **Adatmodell **és **Formátum**.

#### <a name="data-model-components"></a>Adatmodell összetevők

Egy adatmodell-összetevő egy adatstruktúra absztrakt ábrázolása, és arra használatos, hogy egy adott üzleti szakterület jelentési követelményinek megfelelő részletességgel leírja a területet. Egy adatmodell-összetevő a következő részekből áll:

-   Egy adatmodell, ami a területspecifikus üzleti entitások egy csoportja, és egy hierarchikusan felépített kapcsolatrendszer ezen entitások között
-   A modell, hogy hivatkozásokat Dynamics 365 kiválasztott műveletek adatforrások egy adatmodell a futási időben határozza meg egyes elemek megfeleltetése az adatfolyam- és üzleti adatok statisztikai adat szabályok minta összetevő.

Egy adatmodell üzleti entitását egy tároló (rekord) képviseli. Az üzleti entitások tulajdonságai adatelemként (mezőként) jelennek meg. Minden adatelem egyedi névvel, címkével, leírással és értékkel rendelkezik. Az egyes adatelemek értékeit megszerkesztheti, hogy karakterláncként, egész számként, valós számként, dátumként, enumerációs típusként, logikai értékként vagy egyéb változóként legyenek kiolvasva. Továbbá lehet másik rekord vagy rekordlista is. Egy adatmodell-összetevő tartalmazhat több tartományspecifikus üzleti entitás-hierarchiát, és olyan modell-hozzárendeléseket, amelyek a futási idő alatt bizonyos jelentés-specifikus adatfolyamokat támogatnak. A hierarchiákat egyetlen rekord különbözteti meg, amit a modell-hozzárendelés gyökerének választott ki. Például, a fizetési tartomány adatmodellje támogathatja a következő leképezéseket:

-   Vállalat -&gt; szállító -&gt; AP tartomány kifizetési tranzakciók
-   Vevő -&gt; vállalat -&gt; AR tartomány kifizetési tranzakciók

Vegyük figyelembe, hogy az üzleti entitásokat (úgy mint a Vállalat és a Fizetési tranzakciók) egyszer hozza létre. Ezután különböző hozzárendelések újrahasználják őket. Egy modell-hozzárendelés a következő képességekkel rendelkezik:

-   Különböző Dynamics 365 műveletek adattípus egy adatmodell adatforrásaként használhatja. Használhat például táblázatokat, adatentitásokat, módszereket vagy felsorolásokat.
-   Olyan felhasználói bemeneti paramétereket támogat, amelyeket meghatározhat az adatmodell adatforrásaiként, amikor bizonyos adatokat a futási időben kell megadni.
-   Az átalakítás 365 Dynamics támogatja a szükséges csoportokhoz, szűrés, rendezés és megengedő adatok műveleti adatok, és is Hozzáfűzés az logikai számított mezők, amelyek révén a Microsoft Excel-szerű képletek (További részletekért lásd: [az elektronikus jelentés Képletszerkesztő](general-electronic-reporting-formula-designer.md)).

[![Excel-szerű képletek szerkesztő](./media/pic-formula-1024x615.png)](./media/pic-formula.png) modell összetevőjeként tervezték minden üzleti tartomány az egységes adatforrásként használandó, amely elkülöníti a jelentés fizikai Dynamics 365 adatforrások műveletek végrehajtása, és a tartomány-specifikus üzleti fogalmak és oly módon, hogy a jelentés formátuma kezdeti tervezési és hatékonyabb további karbantartási funkciók jelenti.

#### <a name="format-components"></a>Formátum-összetevők

A formátum összetevője a futásidőben létrejövő jelentési kimenet sémája. A rendszer az alábbi elemekből áll:

-   Egy formátumból, amely az elektronikus dokumentum futásidőben generált struktúráját és tartalmát határozza meg
-   Adatforrásokból, amelyek felhasználói bemeneti paraméterek és tartományspecifikus adatmodellek formájában jelennek meg kiválasztott modell-hozzárendeléssel;
-   Egy formátum hozzárendelésből, amely formátum-adatforrások formájában jelenik meg olyan egyedi formátumelemekkel, amelyek megadják a futásidőben az adatfolyamot és a formátumkimenet generálásának szabályait
-   A formátum-ellenőrzést a jelentés létrehozásához a működési környezettől függően futásidőben szabályozó konfigurálható szabályok szerint (például olyan szabály, amely leállítja a szállítói kifizetések kimeneti keletkezését és kivételt okoz, ha a kiválasztott szállító meghatározott attribútumai hiányoznak, például a bank számlaszám).

Egy formátum összetevő, amely támogatja az alábbi funkciókat:

-   Különálló fájlokként különböző formátumú kimenet jelentés létrehozása: szöveg, XML vagy munkalap
-   Több külön fájl létrehozása, és ezen fájlok zip fájlba történő tömörítése

A formátum-összetevő lehetővé teszi bizonyos fájlok csatolását, amelyek a jelentési kimenetben a következőképpen használhatók:

-   Excel-munkafüzetek, melyek olyan munkalapot tartalmaznak amik sablonként használhatóak a kimenethez az OPENXML munkalap formátumban
-   Más fájlok, amelyeket előre definiált fájlként konvertálni lehet a formátum kimenetébe.

#### <a name="component-versioning"></a>Összetevő verziókövetése

Az ER-összetevő esetében támogatott a verziókövetés. A következő munkafolyamat az ER-összetevők kezelésére és megóvására szolgál:

-   Az eredetileg létrehozott verzió **TERVEZETT** verzióként van megjelölve. Ez a verzió szerkeszthető és elérhető próbakísérletekhez.
-   A** TERVEZETT** verzió átkonvertálható egy **BEFEJEZŐDÖTT** verzióvá. Ez a verzió használható a helyi jelentési folyamatokban.
-   A **kész** verzió átalakítható egy **megosztott** verzió. Ezen verziója LCS közzétételt, és a globális jelentési folyamatok is használható.
-   A **MEGOSZTOTT **verzió átkonvertálható egy **NEM FOLYTATOTT** verzióvá. Ez a verzió törölhető.

Vagy-verziók ** kész ** vagy **megosztott** állapot érhetők el más adatcsere. Egy ezekkel az állapotokkal rendelkező összetevőn a következő műveletek végezhetőek el:

-   Ezeket XML-formátumú szerializált és XML formátumú fájlként exportált Dynamics 365 műveletekhez.
-   Ezeket egy XML-fájlból reserialized és ER-összetevő új verzióként Dynamics 365 műveletek importálja.

#### <a name="component-date-effectivity"></a>Összetevő érvényességi dátuma

Az ER-összetevő verziói érvényességi dátumhoz kötöttek. Az ER-összetevőhöz megadható az** Érvényesség kezdete **dátum, hogy meghatározzuk, mikortól lesz érvényes az összetevő a jelentési folyamatban. A Dynamics 365 műveletek munkamenet dátuma határozza meg, hogy egy eleme végrehajtásra érvényes szolgál. Amennyiben egy bizonyos dátumhoz egynél több verzió is érvényes, a jelentési folyamathoz a legutóbbi verzió kerül felhasználásra.

#### <a name="component-access"></a>Összetevő hozzáférése

Az ER formátum összetevőinek hozzáférése függ az ország/terület ISO kódjának beállításától. Ha ez a beállítás nincs bejelölve, a kiválasztott verzió a formátum beállítások, format összetevő érhetők el a Dynamics 365 műveletek vállalat futási időben. Ha ez a beállítás tartalmaz ISO ország-/ régiókódokat, csak az egyik formátum összetevő ISO ország-/ régiókódokat definiált elsődleges címmel rendelkező vállalatok műveletek Dynamics 365 format összetevő érhető el. Előfordulhat, hogy az adatformátum-összetevők különböző verziói más ország/terület ISO kód beállításaival rendelkeznek.

#### <a name="configuration"></a>Konfiguráció

Az ER beállítás egy adott ER-összetevő csomagolója vagy **Adatmodell **, vagy **Formátum**. A konfiguráció tartalmazhatja egy bizonyos ER összetevő különböző verzióit. Az egyes konfigurációk tulajdonosa egy bizonyos konfigurációs szolgáltatóként van megjelölve. A **tervezett** egy összetevőt a konfigurációs szerkeszthető, ha a tulajdonos a konfiguráció egy aktív szolgáltató ER beállításai a Dynamics 365 műveletekhez van kiválasztva. Minden modell beállítás tartalmaz egy **Adatmodell** összetevőt. Új konfiguráció származtatható egy bizonyos adatmodell konfigurációból. A létrehozott formátum konfiguráció a konfiguráció fában lesz jelen az eredeti adatmodell konfiguráció leszármazottjaként. A létrehozott formátum beállítás tartalmaz egy **Formátum **összetevőt. Ez eredeti modell konfiguráció **Adatmodell** komponense automatikusan beillesztésre kerül a leszármazott formátumkonfiguráció **Formátum **komponensébe alapértelmezett adatforrásként. Az ER-konfigurációs műveletek vállalatok 365 Dynamics van osztva.

#### <a name="provider"></a>Szolgáltató

Az ER-szolgáltató az a félazonosító, amely az egyes ER-konfigurációk szerzőjét (tulajdonosát) meghatározza. ER segítségével kezelheti a konfigurációs szolgáltatók listáját. Konfigurációk, amelyek az elektronikus dokumentumok a Dynamics 365 műveletek megoldás részeként megjelölve tulajdonában formázni a **a Microsoft** konfigurációs szolgáltatója.

#### <a name="repository"></a>Tárház

Egy ER tárház ER konfigurációkat tárol. Jelenleg támogatott ER böngészhetnek a következő típusú: **műveletek erőforrások** és **LCS projekt**. Egy ** műveletek erőforrások ** tárház a Dynamics 365 műveletek megoldás részeként ER konfigurációs szolgáltatóként a Microsoft által kiadott konfigurációk listáját hozzáférést biztosít. A konfigurációk is importálja a jelenlegi Dynamics 365 műveletek példány és elektronikus jelentési. Használhatóak ezen kívül további lokalizációkhoz és testreszabásokhoz. Az **LCS projekt **tárház hozzáférést biztosít egy bizonyos, a tárház regisztrációs szakaszában kiválasztott LCS projekt konfigurációinak listájához (LCS projekt eszköztár). ER lehetővé teszi egy bizonyos műveletek példány a jelenlegi Dynamics 365 a megosztott konfigurációk feltöltése **LCS projekt** tárház. Konfigurációk is importálhatók egy adott a **LCS projekt** a jelenlegi Dynamics 365 műveletek példány a tárházat. Kötelező **LCS projekt** tárhelyek külön-külön az egyes műveletek példány a jelenlegi Dynamics 365 konfigurációs szolgáltatók regisztrálható. Minden tárház hozzárendelhető egy bizonyos konfigurációs szolgáltatóhoz.

## <a name="supported-scenarios"></a>Támogatott esetek
### <a name="building-a-data-model"></a>Adatmodell létrehozása

Az ER modelltervezőt biztosít egy bizonyos üzleti tartomány adatmodelljeinek építésére. Minden tartományspecifikus üzleti entitás és a köztük lévő kapcsolat beállítható adatmodellként egy hierarchikus struktúrában. A következő ábrán egy példa látható az ilyen típusú adatmodellekre (a fizetési tartomány adatmodell). [![Példa egy adatmodell](./media/pic-data-model-1024x550.png)](./media/pic-data-model.png) lejátszása megismerkedhet a részleteket a forgatókönyv, a **ER Tervező tartománymodell konkrét adatok** feladat útmutató (része a **7.5.4.3 megszerzése/fejlesztése IT service/megoldás-összetevők (10677)** üzleti folyamat).

### <a name="translating-data-model-content"></a>Az adatok modell tartalmának fordítása

Az adatok modell tartalmának (címke és leírás) lefordítható Dynamics 365 műveletek támogató más nyelvek. Érdemes lehet az adatok modell tartalmának fordítása a következő okok miatt:

-   Hogy tervezés közben érthetőbb legyen az idegen nyelvű formátumtervezők számára, akik adatmodellt fognak használni a formátum-összetevők adatleképezéséhez
-   A futási idő, a tartalom több felhasználó rövid utasításokat bemutatásával és futásidejű paramétereit, Súgó és is beállított a nyelvet, a jelenleg bejelentkezett Dynamics 365 felhasználói műveletek legszívesebben érvényesítési üzenetekben (hibák és figyelmeztetések),

A következő illusztráció bemutat egy példát arra az esetre, hogy hogyan lehet lefordítani az adatmodell tartalmát angolról japánra. [![Adatok minta tartalom angolul](./media/pic-translate-en-1024x495.png)](./media/pic-translate-en.png)[![adatok tartalmának lefordítását a japán modell](./media/pic-translate-ja-1024x495.png)](./media/pic-translate-ja.png)

### <a name="configuring-data-model-mappings"></a>Adatmodell hozzárendeléseinek beállítása

ER biztosít egy modell leképezési Tervező, amellyel a felhasználók az általuk létrehozott adatok modellek hozzárendelése adott Dynamics 365 műveletek adatforrásokhoz. A következő ábra az ilyen adatmodell-leképezést szemlélteti (A Fizetési tartomány adatmodell **SEPA Kredit átutalás** modell-leképezése). [![Modell megfeleltetése példa ](./media/pic-model-mapping-1024x551.png)](./media/pic-model-mapping.png)lejátszása megismerkedhet a részleteket a forgatókönyv, a **ER meg minta adatforrások hozzárendelését, és jelölje be** és **térkép ER adatmodell kijelölt adatforrásokhoz** tevékenység-segédvonalak (része a **7.5.4.3 megszerzése/fejlesztése IT service/megoldás-összetevők (10677)** üzleti folyamat).

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>A létrehozott modell-összetevő tárolása modell-konfigurációként

ER tárolhatja és kapcsolódó adatok hozzárendelések tervezett adatmodell műveleti példány a jelenlegi Dynamics 365 modell konfigurációként. A következő ábrán egy példa látható az ilyen típusú adatmodell-konfigurációkra (a fizetési modellkonfigurációra). [![Példa konfigurációs adatok modell ](./media/pic-model-configuration-1024x585.png)](./media/pic-model-configuration.png)lejátszása megismerkedhet a részleteket a forgatókönyv, a **ER térkép adatmodell kijelölt adatforrásokhoz** feladat útmutató (része a **7.5.4.3 megszerzése/fejlesztése IT service/megoldás-összetevők (10677)** üzleti folyamat).

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Formátum létrehozása adatmodell alapként való kijelölésével

Az ER támogatja azt a formátumtervezőt, amely az adott elektromos dokumentum formátumának tervezésére szolgál a kiválasztott üzleti tartomány számára, úgy, hogy a modell-összetevőt alapként választja ki. Ugyanaz az ER formátumtervező képes arra, hogy feltérképezzen egy Ön által létrehozott, egy adott tartomány adatmodell-feltérképezését adatforrásként használó formátumot. A következő ábrán egy példát láthat erre a típusú formátumra (olyan formátumkonfiguráció, ami támogatja a **BACS** fizetési formátumot az Egyesült Királyságban). [![Példa egy olyan formátumra, amelynek alapjául egy adatmodell](./media/pic-format-1024x690.png)](./media/pic-format.png) megismerkedhet a részleteket a forgatókönyv, lejátszása az **ER Tervező tartomány adott formátumú** feladat útmutató (része a **7.5.4.3 megszerzése/fejlesztése IT service/megoldás-összetevők (10677)** üzleti folyamat).

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Az OPENXML munkafüzet formátumban elektronikus dokumentumok létrehozásához egy konfigurációkészlet létrehozása

Az ER formátumtervezővel bizonyos elektronikus dokumentumok hozhatók létre OPENXML munkalap-formátumban. Az alábbi ábra szemlélteti, az ilyen típusú formátum (format konfiguráció kiválasztott kifizetési naplóban részleteivel együtt OPENXML munkalap létrehozásához):[![Pic-ER-formátum-Excel](./media/pic-er-format-excel.jpg)](./media/pic-er-format-excel.jpg) lejátszása megismerkedhet a részleteket a forgatókönyv, a **ER jelentések konfiguráció létrehozása a nyílt XML formátumú** feladat útmutató (része a **7.5.4.3 megszerzése/fejlesztése IT service/megoldás-összetevők (10677)** üzleti folyamat). Az említett alatti Excel fájlt sablonként használni tervezése ER formátum lépésre a feladat útmutató formátuma sablon importálása: [sablon, fizetési jelentés (SampleVendPaymWsReport.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Egy megtervezett formátumösszetevő tárolása a formátumkonfigurációban

ER és az előre beállított hozzárendelések tervezett formátumban tárolhatja a jelenlegi Dynamics 365 műveletek példány formátum konfigurációként. Az előző illusztrációban egy példa szerepel erre a típusú formátumkonfigurációra (**BACS (UK)**, ami a **Kifizetési modell **konfigurációból van származtatva). Ahhoz, hogy megismerje ennek a folyamatnak a részleteit hajtsa végre az **ER tartományspecifikus adatmodell kialakítása** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

### <a name="configuring-dynamics-365-for-operations-to-start-to-use-a-created-format-internally"></a>Dynamics 365 formátumot szeretnénk használni egy létrehozott belső indítása műveletek beállítása

365 Dynamics műveletek beállítható úgy, hogy a létrehozott formátumú elektronikus jelentések használatához. A létrehozott formátum konfigurációjának hivatkozásához bizonyos tartományspecifikus beállításokat kell meghatározni. Például egy ER formátumú konfigurációs használandó elektronikus fizetési BACS formátumban el a konfiguráció formázása kell lehet hivatkozni különleges módszerek fizetés, ahogy az alábbi ábrákon az: 

[![BACS (UK) konfiguráció formázása](media/ger-bacs-uk-format-configuration.png) 

[![A BACS (UK) formátum egy fizetési módot a hivatkozó](media/ger-bacs-uk-format-method.png) 

Játssza le az **ER formátum használata elektronikus dokumentumok létrehozására a fizetésekhez** című feladatútmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része), hogy megismerje ennek az esetnek a részleteit.

## <a name="handling-er-components"></a>ER-összetevők kezelése
### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>ER-összetevő közzététele az LCS-ben külső használatra (lokalizáció)

A létrehozott összetevő (modell vagy formátum) tulajdonosa az ER segítségével közzé tudja tenni az összetevő kész verzióját az LCS-ben. Ehhez a folyamathoz az **LCS projekt **típus tárháza szükséges az aktuális ER konfigurációs szolgáltatónál. Ha az összetevő kész verziója **KÉSZ** státuszról **MEGOSZTOTT** státuszra módosul, a verziót közzéteszi a rendszer az LCS-ben. Ha egy összetevőt közzétettünk az LCS-ben, az összetevő tulajdonosa szolgáltatóvá válik az összetevő támogatása céljából. Például ha ezt a formátum-összetevőt egy jogilag kötelező elektromos dokumentum létrehozására tervezték (például a lokalizációs esettel összhangban), ez a szolgáltatás feltételezi azt, hogy ez a formátum megfelel a jogszabályi változtatásoknak és új verziókat tesz közzé, amikor az új jogszabályi követelményeket kell támogatni. Ahhoz, hogy megismerje ennek a folyamatnak a részleteit hajtsa végre az **ER konfiguráció feltöltése a Lifecycle Services-be **című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>ER-összetevő importálása az LCS-ből belső használatra

ER ER összetevők importálása a jelenlegi Dynamics 365 műveletek példány LCS teszi lehetővé. Az **LCS projekt **típus tárháza szükséges ehhez a folyamathoz. A jelenlegi Dynamics 365 műveletek példány importálta a LCS ER összetevőként, a példány a tulajdonos a fogyasztó a szolgáltatás tulajdonosa (szerző) az importált összetevő által biztosított válik. Például ha a formátum célja, hogy egy adott elektronikus dokumentum létrehozása Dynamics 365 műveletek ország-/ területspecifikus formátumban (honosítás eset), feltételezhető, hogy a szolgáltatás fogyasztó lesz képes ezt a formátumot felel meg a jogszabályi követelményeknek folyamatosan végzett szerezheti. Ahhoz, hogy megismerje ennek a folyamatnak a részleteit hajtsa végre az **ER konfiguráció importálása a Lifecycle Services-ből** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Formátum létrehozása más formátum alapként való kijelölésével (testreszabás)

Az ER segítségével létrehozhat (származtathat) egy új komponenst az LCS-ből importált komponens (alap) jelenlegi verziójából. Például egy felhasználó új formátumot szeretne származtatni testreszabás támogatása érdekében az elektronikus dokumentum (például egy további mező vagy egy részletes leírást) néhány különleges követelményének végrehajtásához. Hajtsa végre az **ER formátum frissítése új alapverzió használatával** című feladatútmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része), hogy megismerje ennek az esetnek a részleteit.

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Formátum frissítése az alapformátum új verziójának kiválasztásával (új alap megadása)

Az ER automatikusan igazodik az alapösszetevő legújabb verziójához a származtatott összetevő jelenlegi vázlat-verziójában. Ennek a folyamatnak a neve *új alap* megadása. Például az LCS-ből importált formátum-összetevő legújabb verziójában megjelent új szabályozási módosítások automatikusan összevonhatók az elektronikus dokumentum a saját testreszabott verziójával. Az automatikusan nem egyesíthető módosítások ütközésnek minősülnek. Ezek az ütközések a megfelelő összetevőhöz tartozó tervezőeszközben manuális megoldásra megjelennek. Hajtsa végre az **ER formátum frissítése új alapverzió használatával** című feladatútmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része), hogy megismerje ennek az esetnek a részleteit.

## <a name="list-of-er-configurations-that-are-delivered-in-the-dynamics-365-for-operations-solution"></a>Listája érkeznek a Dynamics 365 műveletek megoldás ER-konfigurációk
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


