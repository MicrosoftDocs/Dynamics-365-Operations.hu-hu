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
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: abe9212372fb7429d68c1fb6b32ec1d15c20a6d7
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="electronic-reporting-overview"></a>Elektronikus jelentések áttekintése

[!include[banner](../includes/banner.md)]


Ez a cikk az Elektronikus jelentéskészítés eszközről nyújt áttekintést. Tájékoztatást nyújt az alapfogalmakról, az Elektronikus jelentéskészítés által támogatott esetekről, valamint az Elektronikus jelentéskészítés megoldás részeként megtervezett és kibocsátott formátumok listájáról.

Az elektronikus jelentés (ER) egy olyan eszköz, amelyet elektronikus dokumentumok formázására használhat, a különböző országok/régiók jogi követelményeinek megfelelően. Az ER lehetővé teszi, hogy ezeket a formátumokat a teljes életciklusuk során kezelje. Például alkalmazhat új jogszabályi követelményeket, és létrehozhat üzleti dokumentumokat a kívánt formátumban, annak érdekében, hogy elektronikusan információt cseréljen kormányzati testületekkel, bankokkal és egyéb felekkel. Az ER-motor a fejlesztők helyett az üzleti felhasználóknak készült. Mivel nem kódokat, hanem formátumokat konfigurál, az elektronikus dokumentumok formátumának létrehozása és beállítása gyorsabb és könnyebb. Az ER jelenleg a TEXT, XML és OPENXML munkalap-formátumokat támogatja. Azonban egy kiterjesztési felület több formátum támogatását biztosítja.

## <a name="capabilities"></a>Képességek
Az ER motor a következő képességekkel rendelkezik:

-   Egységes, közös eszközt képvisel a különböző tartományokban történő elektronikus jelentésekhez, és több mint 20 különböző motort helyettesít, amelyek az elektronikus jelentés valamely típusára képesek a Microsoft Dynamics 365 for Operations rendszerben.
-   A jelentés formátumát elkülöníti jelenlegi Dynamics 365 for Operations rendszertől. (Más szóval a formátum a Dynamics 365 for Operations különböző verzióiban is használható.)
-   Támogatja egy egyéni formátum létrehozását, ami az eredeti formátumon alapul. Képes automatikusan frissíteni az egyéni formátumot, ha változás történik az eredeti formátumban új honosítási/személyre szabási követelmények bevezetése miatt.
-   Ez válik az elsődleges, szabványos eszközzé a honosítási követelmények támogatására az elektronikus jelentésekben, mind a Microsoft-nál, mind a Microsoft partnereinél.
-   Támogatja a formátumok elosztását a partnerek és a vevők részére, a Microsoft Dynamics Lifecycle Services (LCS) rendszeren keresztül.

## <a name="concepts"></a>Koncepció
### <a name="components"></a>Összetevők

Az ER két összetevő-típust támogat: **Adatmodell**és **Formátum**.

#### <a name="data-model-components"></a>Adatmodell összetevők

Egy adatmodell-összetevő egy adatstruktúra absztrakt ábrázolása, és arra használatos, hogy egy adott üzleti szakterület jelentési követelményinek megfelelő részletességgel leírja a területet. Egy adatmodell-összetevő a következő részekből áll:

-   Egy adatmodell, ami a területspecifikus üzleti entitások egy csoportja, és egy hierarchikusan felépített kapcsolatrendszer ezen entitások között
-   Egy modell-leképezés, amely összekapcsolja a Dynamics 365 for Operations adatforrásokat az adatmodell adott, egyes elemeivel a futási időben, valamint az adatfolyam, és az üzleti adatok feltöltésének szabályai az adatmodell-összetevőbe.

Egy adatmodell üzleti entitását egy tároló (rekord) képviseli. Az üzleti entitások tulajdonságai adatelemként (mezőként) jelennek meg. Minden adatelem egyedi névvel, címkével, leírással és értékkel rendelkezik. Az egyes adatelemek értékeit megszerkesztheti, hogy karakterláncként, egész számként, valós számként, dátumként, enumerációs típusként, logikai értékként vagy egyéb változóként legyenek kiolvasva. Továbbá lehet másik rekord vagy rekordlista is. Egy adatmodell-összetevő tartalmazhat több tartományspecifikus üzleti entitás-hierarchiát, és olyan modell-hozzárendeléseket, amelyek a futási idő alatt bizonyos jelentés-specifikus adatfolyamokat támogatnak. A hierarchiákat egyetlen rekord különbözteti meg, amit a modell-hozzárendelés gyökerének választott ki. Például, a fizetési tartomány adatmodellje támogathatja a következő leképezéseket:

-   Vállalat -&gt; Szállító -&gt; Az AP tartomány kifizetési tranzakciói
-   Vevő -&gt; Vállalat -&gt; Az AR tartomány kifizetési tranzakciói

Vegyük figyelembe, hogy az üzleti entitásokat (úgy mint a Vállalat és a Fizetési tranzakciók) egyszer hozza létre. Ezután különböző hozzárendelések újrahasználják őket. Egy modell-hozzárendelés a következő képességekkel rendelkezik:

-   Használhat különböző Dynamics 365 for Operations-adattípusokat az adatmodell adatforrásaként. Használhat például táblázatokat, adatentitásokat, módszereket vagy felsorolásokat.
-   Olyan felhasználói bemeneti paramétereket támogat, amelyeket meghatározhat az adatmodell adatforrásaiként, amikor bizonyos adatokat a futási időben kell megadni.
-   Támogatja a Dynamics 365 for Operations-adatok kívánt csoportokká való átalakítását, az adatok szűrését, rendezését és összegzését, valamint a Microsoft Excel-ben használtakhoz hasonló képletekkel létrehozott, logikai számított mezőkhöz való hozzáfűzésüket (további információért lásd: [Képletszerkesztő elektronikus jelentésekhez](general-electronic-reporting-formula-designer.md)).

[![Excel-szerű képletszerkesztő](./media/pic-formula-1024x615.png)](./media/pic-formula.png) Egy adatmodell-összetevő készült minden olyan üzleti területhez, amit egyesített adatforrásként fognak használni az olyan jelentéskészítésben, amely elválasztja a jelentést a Dynamics 365 for Operations adatforrások fizikai implementációjától, és területspecifikus üzleti koncepciókat és funkciókat reprezentál egy olyan formában, amely a jelentés formátumának kezdeti megjelenését és a további karbantartását hatékonyabbá teszi.

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
-   A**TERVEZETT** verzió átkonvertálható egy **BEFEJEZŐDÖTT** verzióvá. Ez a verzió használható a helyi jelentési folyamatokban.
-   A **KÉSZ** verzió átkonvertálható egy **MEGOSZTOTT** verzióvá. Ezen verzió közzétételre kerül az LCS-n, és a globális jelentési folyamatokban is használható.
-   A **MEGOSZTOTT**verzió átkonvertálható egy **NEM FOLYTATOTT** verzióvá. Ez a verzió törölhető.

A **KÉSZ** vagy **MEGOSZTOTT** állapotú verziók elérhetőek további adatcsere céljából. Egy ezekkel az állapotokkal rendelkező összetevőn a következő műveletek végezhetőek el:

-   Szerializálhatóak XML-formátumba és a Dynamics 365 for Operations rendszerből exportálhatóak XML formátumú fájlba.
-   Újraszerializálhatóak XML fájlból és importálhatóak a Dynamics 365 for Operationsbe egy ER összetevő új verziójaként.

#### <a name="component-date-effectivity"></a>Összetevő érvényességi dátuma

Az ER-összetevő verziói érvényességi dátumhoz kötöttek. Az ER-összetevőhöz megadható az**Érvényesség kezdete**dátum, hogy meghatározzuk, mikortól lesz érvényes az összetevő a jelentési folyamatban. A Dynamics 365 for Operations munkamenet dátuma arra használható, hogy meghatározzuk, érvényes-e az összetevő a végrehajtásra. Amennyiben egy bizonyos dátumhoz egynél több verzió is érvényes, a jelentési folyamathoz a legutóbbi verzió kerül felhasználásra.

#### <a name="component-access"></a>Összetevő hozzáférése

Az ER formátum összetevőinek hozzáférése függ az ország/terület ISO kódjának beállításától. Ha ez a beállítás nincs bejelölve a formátum beállítások kiválasztott verziójánál, akkor a formátum összetevők elérhetőek bármely Dynamics 365 for Operations-vállalatnál a futási idő során. Ha ez a beállítás tartalmazza az ország/régió ISO kódját, akkor a formátum összetevője csak abból a Dynamics 365 for Operations-vállalatból érhető el, amely elsődleges címének egy formátum-összetevő ország/terület ISO kódja van megadva. Előfordulhat, hogy az adatformátum-összetevők különböző verziói más ország/terület ISO kód beállításaival rendelkeznek.

#### <a name="configuration"></a>Konfiguráció

Az ER beállítás egy adott ER-összetevő csomagolója vagy **Adatmodell**, vagy **Formátum**. A konfiguráció tartalmazhatja egy bizonyos ER összetevő különböző verzióit. Az egyes konfigurációk tulajdonosa egy bizonyos konfigurációs szolgáltatóként van megjelölve. Egy konfiguráció összetevőjének **VÁZLAT** verziója akkor szerkeszthető, amikor a konfiguráció tulajdonosa aktív szolgáltatóként van beállítva a Dynamics 365 for Operations ER-beállításokban. Minden modell beállítás tartalmaz egy **Adatmodell** összetevőt. Új konfiguráció származtatható egy bizonyos adatmodell konfigurációból. A létrehozott formátum konfiguráció a konfiguráció fában lesz jelen az eredeti adatmodell konfiguráció leszármazottjaként. A létrehozott formátum beállítás tartalmaz egy **Formátum**összetevőt. Ez eredeti modell konfiguráció **Adatmodell** komponense automatikusan beillesztésre kerül a leszármazott formátumkonfiguráció **Formátum**komponensébe alapértelmezett adatforrásként. Az ER-konfiguráció megosztásra kerül a Dynamics 365 for Operations-vállalatok számára.

#### <a name="provider"></a>Szolgáltató

Az ER-szolgáltató az a félazonosító, amely az egyes ER-konfigurációk szerzőjét (tulajdonosát) meghatározza. ER segítségével kezelheti a konfigurációs szolgáltatók listáját. A Dynamics 365 for Operations megoldás részeként kiadott elektromos dokumentumokra érvényes formátumkonfigurációk tulajdonosa a **Microsoft** konfigurációs szolgáltató.

#### <a name="repository"></a>Tárház

Egy ER tárház ER konfigurációkat tárol. A következő típusú ER tárházak támogatottak jelenleg: **Operations-erőforrások** és **LCS-projekt**. Az **Operations-erőforrások** tárház hozzáférést biztosít azon konfigurációk listájához, melyeket a Dynamics 365 for Operations megoldás részeként a Microsoft szállít mint GER konfigurációszolgáltató,. Ezek a konfigurációk importálhatóak a jelenlegi Dynamics 365 for Operations munkamenetbe és felhasználhatóak elektronikus jelentés céljából. Használhatóak ezen kívül további lokalizációkhoz és testreszabásokhoz. Az **LCS projekt**tárház hozzáférést biztosít egy bizonyos, a tárház regisztrációs szakaszában kiválasztott LCS projekt konfigurációinak listájához (LCS projekt eszköztár). Az ER lehetőséget biztosít a megosztott konfigurációk feltöltésére a jelenlegi Dynamics 365 for Operations példányból egy adott **LCS-projekt** tárházba. Importálhat továbbá konfigurációkat egy bizonyos **LCS-projekt** tárházából a Dynamics 365 for Operations jelenlegi példányába. A szükséges **LCS-projekt** tárházak egyesével regisztrálhatók a jelenlegi Dynamics 365 for Operations példány különböző konfigurációs szolgáltatóihoz. Minden tárház hozzárendelhető egy bizonyos konfigurációs szolgáltatóhoz.

## <a name="supported-scenarios"></a>Támogatott esetek
### <a name="building-a-data-model"></a>Adatmodell létrehozása

Az ER modelltervezőt biztosít egy bizonyos üzleti tartomány adatmodelljeinek építésére. Minden tartományspecifikus üzleti entitás és a köztük lévő kapcsolat beállítható adatmodellként egy hierarchikus struktúrában. A következő ábrán egy példa látható az ilyen típusú adatmodellekre (a fizetési tartomány adatmodell). [![Egy adatmodell példája](./media/pic-data-model-1024x550.png)](./media/pic-data-model.png) Ahhoz, hogy megismerje ennek a folyamatnak a részleteit, játssza le az **ER tartományspecifikus adatmodell kialakítása** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része), hogy megismerkedjen a folyamat részleteivel.

### <a name="translating-data-model-content"></a>Az adatok modell tartalmának fordítása

Az adatok modell tartalma (címke és leírás) lefordítható más, a Dynamics 365 for Operations által támogatott nyelvre Érdemes lehet az adatok modell tartalmának fordítása a következő okok miatt:

-   Hogy tervezés közben érthetőbb legyen az idegen nyelvű formátumtervezők számára, akik adatmodellt fognak használni a formátum-összetevők adatleképezéséhez
-   Hogy a felület felhasználóbarátabb legyen futtatás közben a rákérdezések és a futtatási paraméterek súgójának megjelenítésekor, valamint a konfigurált ellenőrzési üzenetek (hibák, figyelmeztetések) megjelenítésekor a preferált Dynamics 365 for Operations felhasználói nyelven.

A következő illusztráció bemutat egy példát arra az esetre, hogy hogyan lehet lefordítani az adatmodell tartalmát angolról japánra. [![Adatmodell tartalma angolul](./media/pic-translate-en-1024x495.png)](./media/pic-translate-en.png) [![Adatmodell tartalma japán nyelvre lefordítva](./media/pic-translate-ja-1024x495.png)](./media/pic-translate-ja.png)

### <a name="configuring-data-model-mappings"></a>Adatmodell hozzárendeléseinek beállítása

Az ER biztosít egy modell-leképezés tervezőt, amely lehetővé teszi a felhasználó számára az általuk specifikus Dynamics 365 for Operations adatforrásokhoz tervezett adatmodellek leképezését. A következő ábra az ilyen adatmodell-leképezést szemlélteti (A Fizetési tartomány adatmodell **SEPA Kredit átutalás** modell-leképezése). [![Egy adatmodell-leképezés példája ](./media/pic-model-mapping-1024x551.png)](./media/pic-model-mapping.png) Az ezen forgatókönyv részleteinek megismeréséhez hajtsa végre az **ER modellfeltérképezés definiálása és adatforrások kiválasztása** feladatot, majd az **ER adatmodellezés térkép a kiválasztott adatforrásokhoz** feladatútmutatókat (a **7.5.4.3 IT szolgáltatás/megoldás megszerzése/kifejlesztése elemek (10677))** üzleti folyamat része)

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>A létrehozott modell-összetevő tárolása modell-konfigurációként

Az ER képes a megtervezett adatmodellt a hozzárendelt adatfeltérképezésekkel modellkonfigurációként tárolni az aktuális Dynamics 365 for Operations példányban. A következő ábrán egy példa látható az ilyen típusú adatmodell-konfigurációkra (a fizetési modellkonfigurációra). [![Egy adatmodell-konfiguráció példája ](./media/pic-model-configuration-1024x585.png)](./media/pic-model-configuration.png) Ahhoz, hogy megismerje ennek a folyamatnak a részleteit, játssza le az **ER Adatmodell leképezése a kiválasztott adatforrásokra** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része), hogy megismerkedjen a folyamat részleteivel.

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Formátum létrehozása adatmodell alapként való kijelölésével

Az ER támogatja azt a formátumtervezőt, amely az adott elektromos dokumentum formátumának tervezésére szolgál a kiválasztott üzleti tartomány számára, úgy, hogy a modell-összetevőt alapként választja ki. Ugyanaz az ER formátumtervező képes arra, hogy feltérképezzen egy Ön által létrehozott, egy adott tartomány adatmodell-feltérképezését adatforrásként használó formátumot. A következő ábrán egy példát láthat erre a típusú formátumra (olyan formátumkonfiguráció, ami támogatja a **BACS** fizetési formátumot az Egyesült Királyságban). [![Példa egy adatmodell-alapú formátumra](./media/pic-format-1024x690.png)](./media/pic-format.png) Ahhoz, hogy megismerje ennek a folyamatnak a részleteit, játssza le az **ER - tartományspecifikus formátum kialakítása** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része), hogy megismerkedjen a folyamat részleteivel.

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Az OPENXML munkafüzet formátumban elektronikus dokumentumok létrehozásához egy konfigurációkészlet létrehozása

Az ER formátumtervezővel bizonyos elektronikus dokumentumok hozhatók létre OPENXML munkalap-formátumban. Az alábbi ábra egy ilyen típusú formátum példája (olyan formátumkonfiguráció, mellyel OPENXML munkalap hozható létre, a kiválasztott fizetési napló részleteivel):[![Pic-ER-format-Excel](./media/pic-er-format-excel.jpg)](./media/pic-er-format-excel.jpg) Ahhoz, hogy megismerje ennek a folyamatnak a részleteit, játssza le az **ER-konfiguráció létrehozása OPENXML formátumú jelentésekhez** feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része). A lent említett Excel fájlt használja az ER-formátum mintájaként, így hajtsa végre az ezen feladatútmutató formátummintájának importálását: [Kifizetési jelentés mintája (SampleVendPaymWsReport.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Egy megtervezett formátumösszetevő tárolása a formátumkonfigurációban

Az ER képes a megtervezett formátumnak a konfigurált adatfeltérképezésekkel történő együttes tárolására formátumkonfigurációként az aktuális Dynamics 365 for Operations példányban. Az előző illusztrációban egy példa szerepel erre a típusú formátumkonfigurációra (**BACS (UK)**, ami a **Kifizetési modell**konfigurációból van származtatva). Ahhoz, hogy megismerje ennek a folyamatnak a részleteit hajtsa végre az **ER tartományspecifikus adatmodell kialakítása** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

### <a name="configuring-dynamics-365-for-operations-to-start-to-use-a-created-format-internally"></a>A Dynamics 365 for Operations konfigurálása a létrehozott formátum belső használatához

A Dynamics 365 for Operations beállítható úgy, hogy az elektronikus jelentések generálásához egy már létrehozott formátumot használjon. A létrehozott formátum konfigurációjának hivatkozásához bizonyos tartományspecifikus beállításokat kell meghatározni. Például, egy ER formátumkonfiguráció használható az elektronikus szállítói kifizetésekhez BACS formátumban, ha a formátumkonfiguráció a kifizetések módjánál külön le van hivatkozva, ahogyan a következő illusztrációkon is látható: 

[![BACS (UK) formátumkonfiguráció](media/ger-bacs-uk-format-configuration.png) 

[![Hivatkozás a BACS (UK) formátumra a kifizetés módjánál](media/ger-bacs-uk-format-method.png) 

Játssza le az **ER formátum használata elektronikus dokumentumok létrehozására a fizetésekhez** című feladatútmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része), hogy megismerje ennek az esetnek a részleteit.

## <a name="handling-er-components"></a>ER-összetevők kezelése
### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>ER-összetevő közzététele az LCS-ben külső használatra (lokalizáció)

A létrehozott összetevő (modell vagy formátum) tulajdonosa az ER segítségével közzé tudja tenni az összetevő kész verzióját az LCS-ben. Ehhez a folyamathoz az **LCS projekt**típus tárháza szükséges az aktuális ER konfigurációs szolgáltatónál. Ha az összetevő kész verziója **KÉSZ** státuszról **MEGOSZTOTT** státuszra módosul, a verziót közzéteszi a rendszer az LCS-ben. Ha egy összetevőt közzétettünk az LCS-ben, az összetevő tulajdonosa szolgáltatóvá válik az összetevő támogatása céljából. Például ha ezt a formátum-összetevőt egy jogilag kötelező elektromos dokumentum létrehozására tervezték (például a lokalizációs esettel összhangban), ez a szolgáltatás feltételezi azt, hogy ez a formátum megfelel a jogszabályi változtatásoknak és új verziókat tesz közzé, amikor az új jogszabályi követelményeket kell támogatni. Ahhoz, hogy megismerje ennek a folyamatnak a részleteit hajtsa végre az **ER konfiguráció feltöltése a Lifecycle Services-be**című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>ER-összetevő importálása az LCS-ből belső használatra

Az EZ lehetővé teszi az ER komponensek importálását az LCS-ből az aktuális Dynamics 365 for Operations példányba. Az **LCS projekt**típus tárháza szükséges ehhez a folyamathoz. Amikor egy ER-összetevőt importáltak az LCS-ből az aktuális Dynamics 365 for Operations példányba, akkor ennek a példánynak a tulajdonosa lesz annak a szolgáltatásnak a fogyasztója, amelyet az importált összetevő tulajdonosa (szerzője) kínál. Például, ha ez a formátum-összetevő arra szolgál, hogy a Dynamics 365 for Operations szoftverből egy bizonyos elektronikus dokumentumot generáljon egy adott ország-/régióspecifikus formátumban (lokalizációs eset), akkor feltételezzük, hogy a felhasználó minden frissítést meg tud szerezni a jogi szabványoknak megfelelően. Ahhoz, hogy megismerje ennek a folyamatnak a részleteit hajtsa végre az **ER konfiguráció importálása a Lifecycle Services-ből** című feladat-útmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Formátum létrehozása más formátum alapként való kijelölésével (testreszabás)

Az ER segítségével létrehozhat (származtathat) egy új komponenst az LCS-ből importált komponens (alap) jelenlegi verziójából. Például egy felhasználó új formátumot szeretne származtatni testreszabás támogatása érdekében az elektronikus dokumentum (például egy további mező vagy egy részletes leírást) néhány különleges követelményének végrehajtásához. Hajtsa végre az **ER formátum frissítése új alapverzió használatával** című feladatútmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része), hogy megismerje ennek az esetnek a részleteit.

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Formátum frissítése az alapformátum új verziójának kiválasztásával (új alap megadása)

Az ER automatikusan igazodik az alapösszetevő legújabb verziójához a származtatott összetevő jelenlegi vázlat-verziójában. Ennek a folyamatnak a neve *új alap* megadása. Például az LCS-ből importált formátum-összetevő legújabb verziójában megjelent új szabályozási módosítások automatikusan összevonhatók az elektronikus dokumentum a saját testreszabott verziójával. Az automatikusan nem egyesíthető módosítások ütközésnek minősülnek. Ezek az ütközések a megfelelő összetevőhöz tartozó tervezőeszközben manuális megoldásra megjelennek. Hajtsa végre az **ER formátum frissítése új alapverzió használatával** című feladatútmutatót (a **7.5.4.3 Informatikai szolgáltatások/megoldások összetevőinek beszerzése/kifejlesztése (10677)** üzleti folyamat része), hogy megismerje ennek az esetnek a részleteit.

## <a name="list-of-er-configurations-that-are-delivered-in-the-dynamics-365-for-operations-solution"></a>A Dynamics 365 for Operations megoldásra küldött ER-konfigurációk listája
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




