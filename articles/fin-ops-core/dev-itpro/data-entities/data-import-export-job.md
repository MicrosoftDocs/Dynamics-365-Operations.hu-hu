---
title: Adatimportálási és -exportálási feladatok áttekintése
description: Az Adatezelése munkaterület segítségével hozhatja létre és kezelheti az adatimportálási és -exportálási feladatokat.
author: peakerbl
ms.date: 08/26/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a03f8fd0fa05a1400c69a2da8867dee135ad06a1
ms.sourcegitcommit: 7bcaf00a3ae7e7794d55356085e46f65a6109176
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/26/2022
ms.locfileid: "9357591"
---
# <a name="data-import-and-export-jobs-overview"></a>Adatimportálási és -exportálási feladatok áttekintése

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Az **Adatkezelés** munkaterület segítségével hozhatja létre és kezelheti az adatimportálási és -exportálási feladatokat. Alapértelmezés szerint az adatimportálási és -exportálási folyamat létrehoz egy előkészítési táblát az egyes entitásokhoz a céladatbázisban. Az előkészítési táblák segítségével ellenőrizhetők, megtisztíthatók és konvertálhatók az adatok a mozgatás előtt.

> [!NOTE]
> Ez a cikk abból indul ki, hogy jól ismeri az [adatentitásokat](data-entities.md).

## <a name="data-importexport-process"></a>Adatimportálási és -exportálási folyamat
Az alábbiakban a lépéseket kövesse az adatok exportálásához vagy importálásához.

1. Hozzon létre egy importálási vagy exportálási feladatot, ahol hajtsa végre a következőket:

    - Adja meg a projektkategóriát.
    - Azonosítsa az importálni vagy exportálni kívánt entitásokat.
    - Végezze el a feladat adatformátumának beállítását.
    - Rendezze sorba az entitásokat úgy, hogy logikai csoportokban és értelmes sorrendben történjen meg a feldolgozásuk.
    - Határozza meg, hogy használ-e előkészítési táblákat.

2. Annak az ellenőrzése, hogy a forrásadatok és a céladatok megfelelően vannak leképezve.
3. Az importálási vagy az exportálási feladat biztonságának ellenőrzése.
4. Az importálási vagy az exportálási feladat futtatása.
5. Annak az ellenőrzése, hogy a feladat megfelelően futott-e le, a feladat előzményeinek megtekintésével.
6. Az előkészítési táblák megtisztítása.

A cikk további részei a folyamat mindegyik lépését részletesen ismertetik.

> [!NOTE]
> Használja a képernyő frissítése ikont az adatimportálási/-exportálási képernyő frissítéséhez a legújabb állapot megjelenítése érdekében. A böngészőszintű frissítés nem ajánlott, mert az megszakít minden olyan importálási/exportálási feladatot, amelyet nem kötegben futtattak.

## <a name="create-an-import-or-export-job"></a>Egy importálási vagy exportálási feladat létrehozása
Az adatimportálási vagy -exportálási feladatok egyszer vagy többször is futtathatók.

### <a name="define-the-project-category"></a>Projektkategória megadása
Azt ajánljuk, hogy szánjon időt a megfelelő projektkategória kiválasztására az importálási vagy exportálási feladathoz. A projektkategóriák segítséget nyújtanak a kapcsolódó feladatok kezeléséhez.

### <a name="identify-the-entities-to-import-or-export"></a>Azonosítsa az importálni vagy exportálni kívánt entitásokat
Adott entitásokat adhat hozzá az importálási vagy exportálási feladatokhoz, vagy kiválaszthat egy alkalmazni kívánt sablont is. A sablonok enitások listájával töltenek fel egy feladatot. A **Sablon alkalmazása** beállítás azután érhető el, hogy elnevezte és mentette a feladatot.

### <a name="set-the-data-format-for-the-job"></a>Végezze el a feladat adatformátumának beállítását
Ha kiválaszt egy entitást, ki kell választania az exportálandó vagy importálandó adatok formátumát. A formátumokat az **Adatforrások beállítása** csempe segítségével határozhatja meg. A forrásoldali adatformátum a **Típus**, a **Fájlformátum**, a **Sorelválasztó** és az **Oszlopelválasztó** kombinációja. Vannak egyéb attribútumok is, de ezek a legfontosabbak, amelyeket érteni kell. Az alábbi táblázat felsorolja az érvényes kombinációkat.

| Fájlformátum            | Sor-/oszlopelválasztó                       | XML-stílus                 |
|------------------------|--------------------------------------------|---------------------------|
| Excel                  | Excel                                      | \-–                     |
| XML                    | \-–                                      | XML-elem XML-attribútum |
| Elválasztott, rögzített szélesség | Vessző, pontosvessző, tabulátor, függőleges sáv, kettőspont | \-–                     |

> [!NOTE]
> Fontos kiválasztani a helyes értéket a **Sorelválasztó**, az **Oszlopelválasztó** és a **Szövegminősítő** számára, ha a **Fájlformátum** beállítása **Tagolt**. Győződjön meg róla, hogy az adatok nem tartalmazzák elválasztóként vagy minősítőként használt karaktert, mivel ez hibákat okozhat az importálás és exportálás során.

> [!NOTE]
> XML-alapú fájlformátumok esetén ügyeljen arra, hogy csak jogi karaktereket használjon. Az érvényes karakterekről [az 1.0 XML-kódban szereplő érvényes karaktereknél olvashat bővebben](https://www.w3.org/TR/2006/REC-xml-20060816/Overview.html#charsets/). Az XML 1.0 nem enged meg vezérlő karaktereket, kivéve lapok, visszkocsik és sorbeadagolások esetén. A szabálytalan karakterekre példák a szögletes zárójelek, a szögletes zárójelek és a törtpillák. 

Az adatok importálására és exportálására nem csak a Unicode kódlap használható. Ezzel a leg konzisztensebb eredményeket lehet elérni, és az adatkezelési feladatok sikertelenek lesznek, mivel Unicode karaktereket tartalmaznak. A Unicode-t használó, rendszer által definiált forrásadatformátumok **forrásneve Unicode**. A Unicode-formátum a Unicode kódolású ANSI-kódlapot **·** **a** Területi beállítások lapon kódlapként beválasztó Unicode-kódlap kiválasztásával alkalmazható. Válassza a Unicode következő kódoldalai közül:

| Kódlap | Megjelenítendő név                |
|-----------|-----------------------------|
| 1200      | Unicode                     |
| 12000     | Unicode (UTF-32)            |
| 12001     | Unicode (UTF-32 Nagy végi) |
| 1201      | Unicode (nagy végű)        |
| 65000     | Unicode (UTF-7)             |
| 65001     | Unicode (UTF-8)             |

A kódlapokkal kapcsolatos további tudnivalókat lásd [a kódlap-azonosítóknál](/windows/win32/intl/code-page-identifiers/).

### <a name="sequence-the-entities"></a>Az entitások sorozetba állítása
Az entitások sorrendbe állíthatók egy adatsablonban, valamint az importálási és exportálási feladatokban. Ha egy több adatentitást tartalmazó feladatot futtat, meg kell győződnie arról, hogy az adatentitások megfelelően vannak sorrendbe állítva. Az entitásokat alapvetően úgy kell sorozatba állítani, hogy meg lehessen címezni a funkcionális függőségeket az entitások között. Ha az entitások között nincsenek funkcionális függőségek, párhuzamos importálásra vagy exportálásra lehet ütemezni őket. 

#### <a name="execution-units-levels-and-sequences"></a>Végrehajtási egységek, szintek és sorozatok
A végrehajtási egység, a végrehajtási egységbeli szint és az entitás sorrendje határozza meg az adatok exportálási vagy importálási sorrendjét.

- A különböző végrehajtási egységekben levő entitások feldolgozása párhuzamosan fut.
- A végrehajtási egységekben az entitások feldolgozása párhuzamosan fut, ha ugyanazon a szinten vannak.
- Az egyes szinteken az entitások feldolgozása az adott szinthez tartozó sorozatszámuk alapján történik.
- Egy szint feldolgozása után a következő szint feldolgozása következik.

#### <a name="resequencing"></a>Újraszekventálás
Érdemes lehet ismételten sorrendbe állítani az entitásokat a következő esetekben:

- Ha csak egy adatfeladat van használatban az összes változtatásához, az újraszekventálási beállítások segítségével optimalizálhatja a teljes feladat végrehajtási idejét. Ebben az esetben a végrehajtási egységet a modul megadására használhatja, a szintet a modulon belüli szolgáltatás megadására, a sorozatot pedig az entitás megadására. Ennek a megközelítésnek az alkalmazásával több modulban párhuzamosan dolgozhat, de továbbra is dolgozhat sorrendben a modulon belül. A párhuzamos műveletek sikeres végrehajtását elősegítendő minden függőséget figyelembe kell venni.
- Több adatfeladat használata esetén (például egy feladat minden egyes modulhoz) a sorrendbe állítás használatával befolyásolható az entitások szintje és sorrendje az optimális végrehajtás érdekében.
- Ha egyáltalán nincsenek függőségek, a maximális optimalizálás érdekében az entitások sorrendbe állítása különböző végrehajtási egységeknél történhet.

Az **Újraszekventálás** menü akkor érhető el, amikor több entitás van kijelölve. Az ismételt sorrendbe állítást végrehajtási egység, szint vagy a sorozatbeállítások alapján lehet végrehajtani. Be lehet állítani egy növekményt a kijelölt entitások ismételt sorrendbe állításához. Az egyes entitásokhoz kiválasztott egység, szint és/vagy sorozatszám frissítése a megadott növekmény szerint történik.

#### <a name="sorting"></a>Rendezés
Használhatja a **Rendezés** beállítást az entitások listájának sorrendben való megtekintéséhez.

### <a name="truncating"></a>Csonkolás
A projektek importálásakor az importálás előtt csonkolhatja a rekordokat az entitásokban. Ez akkor hasznos, ha a rekordokat tiszta táblázatokba kell importálnia. Alapesetben ez a beállítás ki van kapcsolva.

## <a name="validate-that-the-source-data-and-target-data-are-mapped-correctly"></a>Annak az ellenőrzése, hogy a forrásadatok és a céladatok megfelelően vannak leképezve
A leképezés funkció az importálási és exportálási feladatokra egyaránt vonatkozik.

- Az importálási feladatok összefüggésében a leképezés azt mutatja be, hogy a forrásfájl mely oszlopai válnak az előkészítő tábla oszlopaivá. Ezért a rendszer meghatározhatja, hogy a forrásfájl mely oszlopadatait kell átmásolni az előkészítési tábla melyik oszlopaiba.
- Az exportálási feladatok összefüggésében a leképezés azt mutatja be, hogy az előkészítési tábla (vagyis a forrás) mely oszlopai válnak a célfájl oszlopaivá.

Ha az oszlopnevek megegyeznek az előkészítési táblában és a fájlban, a rendszer automatikusan létrehozza a leképezést a nevek alapján. Azonban, ha különböznek a nevek, az oszlopok leképezése nem automatikus. Ezekben az esetekben a leképezés lezárásához ki kell választani a **Leképezés megtekintése** beállítást az entitás esetében az adatfeladatban.

Két leképezési nézet van: **Megfeleltetés megjelenítése**, amely az alapértelmezett nézet, és a **Hozzárendelés adatai**. Piros csillag (\*) azonosítja az entitás minden szükséges mezőjét. Ezeket a mezőket az entitással végzett munka előtt le kell képezni. Az egyéb mezők leképezése tetszés szerint törölhető az entitással végzett munka során. Mezőleképezés törléséhez jelölje ki a mezőt vagy az **Entitás** vagy a **Forrás** oszlopban, és válassza ki **Kiválasztás törlése** lehetőséget. Válassza a **Mentés** lehetőséget a módosítások mentéséhez, és zárja be a lapot a projekthez való visszatéréshez. Ugyanezen eljárás segítségével végezheti el a mezőleképezés szerkesztését a forrásből az előkészítésbe az importálás után.

A **Forrásmegfeleltetések előállítása** kiválasztásával lehet létrehozni az oldalon egy leképezést. A létrehozott leképezés ugyanúgy viselkedik, mint az automatikus leképezése. Ezért manuálisan kell leképezni az esetleges le nem képezett mezőket.

![Adatleképezés.](./media/dixf-map.png)

## <a name="verify-the-security-for-your-import-or-export-job"></a>Az importálási vagy az exportálási feladat biztonságának ellenőrzése
A hozzáférés az **Adatkezelés** munkaterülethez korlátozható, hogy a rendszergazdai jogokkal nem rendelkező felhasználók csak meghatározott adatfeladatokhoz férhessenek hozzá. Az adatfeladathoz való hozzáférés azt jelenti, hogy teljes a hozzáférés az adott feladat végrehajtási előzményeihez, és az előkészítési táblákhoz is van hozzáférés. Ezért az adatfeladatok létrehozásakor gondoskodnia kell a megfelelő hozzáférés-szabályozás meglétéről.

### <a name="secure-a-job-by-roles-and-users"></a>Feladatok szerepkörök és felhasználók általi biztonságossá tétele
Használja az **Alkalmazható szerepkörök** menüt a feladat korlátozásához egy vagy több biztonsági szerepkörre. Így csak az érintett szerepkörök tagjai férhetnek hozzá a feladathoz.

A feladat korlátozható meghatározott felhasználókra is. Ha biztonság szerepkör helyett a felhasználókra korlátoz egy feladatot, erősebb a szabályozás lehetősége, ha több felhasználó van hozzárendelve egy szerepkörhöz.

### <a name="secure-a-job-by-legal-entity"></a>Feladat jogi személy szerinti biztosítása
Az adatfeladatok globális jellegűek. Ezért ha egy adatfeladatot hoznak létre és használnak egy jogi személy esetében, a feladat látható lesz más jogi személyeknél is a rendszerben. Bizonyos alkalmazási esetekben előfordulhat, hogy ez az alapértelmezett viselkedés az előnyben részesített. Például egy szervezet, amelyik adatentitások segítségével importálja a számlákat, olyan központi számlafeldolgozási csoporttal rendelkezhet, amely a számlázási hibák kezeléséért felelős a szervezet összes részlegére nézve. Ebben az esetben hasznos a központi számlafeldolgozási csoport számára, ha hozzáfér az összes jogi személy számlaimportálási feladataihoz. Ezért alapértelmezés szerinti viselkedés megfelel a követelménynek a jogi személyek szempontjából.

Azonban előfordulhat az is, hogy egy szervezet jogi személyenként állít fel számlafeldolgozási csapatokat. Ebben az esetben egy adott jogi személy csoportjának csak a saját jogi személye számlaimportálási feladaihoz szabad hozzáféréssel rendelkeznie. Ennek a követelménynek a teljesítéséhez az adatfeladatok jogiszemély-alapú hozzáférés-vezérlése állítható be az adatfeladat **Alkalmazható jogi személyek** menüjének használatával. Miután megtörtént a konfiguráció, a felhasználók csak azokat a feladatokat tekinthetik meg, amelyek abban a jogi személyben állnak rendelkezésre, amelybe be vannak jelentkezve. Egy másik jogi személy feladatainak megtekintéséhez a felhasználóknak át kell váltaniuk arra a jogi személyre.

A feladatok egy időben biztosíthatók szerepkörök, felhasználók és jogi személy szerint.

## <a name="run-the-import-or-export-job"></a>Az importálási vagy az exportálási feladat futtatása
A feladat meghatározása után a feladat futtatható egyszer az **Importálás** vagy az **Exportálás** gomb megnyomásával. Ismétlődő feladat beállításához jelölje be az **Ismétlődő adatkezelési feladat létrehozása** lehetőséget.

> [!NOTE]
> Egy importálási vagy az exportálási feladat futtatható az **Importálás** vagy **Exportálás** gomb kiválasztásával. Ennek hatására a kötegelt feladat csak egyszeri futásra lesz ütemezve. A feladat lehet, hogy nem lesz azonnal végrehajtva,, ha a kötegelt szolgáltatás a kötegelt szolgáltatásban a terhelés miatt korlátozva van. A feladatok futtatható szinkronban is az **Importálás most** vagy az **Exportálás most** kiválasztásával. Ez a azonnal elindítja a feladatot, és akkor hasznos, ha a a kötegelt feladatként nem indul el lekorlátozás miatt. A feladatok egy későbbi időpontra is ütemezhetők. Ezt úgy teheti meg, hogy kiválasztja a **Futtatás kötegben** lehetőséget. A Kötegerőforrások leszabályozásnak lehetnek kitéve, így a kötegelt feladat nem feltétlenül indul el azonnal. A köteg használata az ajánlott beállítás, mivel ez segít nagy mennyiségű adat esetében, amelyeket importálni vagy exportálni kell. Kötegelt feladatok ütemezhetők futtatásához egy adott kötegcsoportban, amelynek több szabályozást tesz lehetővé a terhelés elosztása szempontjából.

## <a name="validate-that-the-job-ran-as-expected"></a>Ellenőrizze, hogy a feladat megfelelően futott le
A feladatelőzmények hibaelhárítási és vizsgálati célra rendelkezésre állnak mind az importálási, mint az exportálási feladatoknál. Az előzményfeladat-futtatások időtartományok szerint vannak rendezve.

![Feladat előzménytartományai.](./media/dixf-job-history.md.png)

Minden lefuttatott feladat megadja a következő adatokat:

- Végrehajtás részletei
- Végrehajtási napló

A végrehajtás részletei megmutatják a feladat által feldolgozott minden egyes adatentitás állapotát. Ezért gyorsan megtalálhatja a következő adatokat:

- Melyek a feldolgozott entitások.
- Egy entitás esetében hány rekord feldolgozása történt meg sikeresen, és hány volt sikertelen.
- Az előkészítési rekordok az egyes entitásokhoz.

Letöltheti az előkészítési adatokat fájlban az exportálási feladatokhoz, vagy letöltheti csomagként az importálási és exportálási feladatokhoz.

A végrehajtás részleteknél a végrehajtási napló is megnyitható.

## <a name="parallel-imports"></a>Párhuzamos importálások
Az adatok importálásának gyorsítása érdekében engedélyezheti egy fájl importálásának párhuzamos feldolgozását, ha az entitás támogatja a párhuzamos importálást. Egy entitás párhuzamos importálásának konfigurálásához a következő lépéseket kell követnie.

1. Ugrás a **Rendszerfelügyelet \> Munkaterületek \> Adatkezelés** elemre.
2. Az **Importálás és exportálás** szakaszban válassza ki a **keretrendszer paraméterei** lapot az **Adatimportálási és-exportálási keretrendszer paraméterei** oldal megnyitásához.
3. Az **entitás beállításai** lap **entitás-végrehajtási paraméterek konfigurálása** elemét választva nyissa meg az **entitásimportálás végrehajtási paraméterei** oldalt.
4. A következő mezők beállításával konfigurálhatja az entitások párhuzamos importálását:

    - Az **Entitás** mezőben válassza ki az entitást.
    - Az **Importálási küszöbérték rekordszáma** mezőben adja meg az importálás rekordjainak küszöbszámát. Ez határozza meg a szál által feldolgozandó rekordok számát. Ha egy fájl 10 000 rekorddal rendelkezik, akkor ha a rekordok száma 2500 és a feladat száma 4, akkor minden szál 2500 rekordot dolgoz fel.
    - Az **importálási feladat száma** mezőbe írja be az importálási feladatok darabszámát. Ez nem haladhatja meg a kötegelt feldolgozásra engedélyezett maximális kötegszálak számát a **Rendszerfelügyelet \> Kiszolgáló konfigurációja** pontban.

## <a name="job-history-clean-up"></a>Feladatelőzmények tisztítása 
Az adatkezelés során a feladatelőzmények törlési funkcióit kell használni a végrehajtási előzmények periodikus törlésének ütemezéséhez. Ez a funkció felváltja a korábbi előkészítési tábla törlése funkciót, amely most már elavult. A következő táblák lesznek törölve a törlési folyamat során.

-   Minden előkészítési tábla

-   DMFSTAGINGVALIDATIONLOG

-   DMFSTAGINGEXECUTIONERRORS

-   DMFSTAGINGLOGDETAIL

-   DMFSTAGINGLOG

-   DMFDEFINITIONGROUPEXECUTIONHISTORY

-   DMFEXECUTION

-   DMFDEFINITIONGROUPEXECUTION

A funkciókezelés modulban engedélyezni kell a **Végrehajtási előzmények törlése** funkciót , ekkor elérhető lesz az **Adatkezelés \> Feladatelőzményeinek kiürítése** helyen.

### <a name="scheduling-parameters"></a>Ütemezési paraméterek

A tisztítási folyamat ütemezésekor a következő paramétereket kell megadni a tisztítási feltételek definiálásához.

-   **Az előzményekben megtartandó napok száma** – ez a beállítás a megőrzendő végrehajtási előzmények mennyiségének megadására szolgál Ez napok számában van megadva. Ha a tisztítási feladat ismétlődő kötegelt feladatként van ütemezve, ez a beállítás egy folyamatosan mozgó ablakhoz hasonlóan működik, mindig megtartja a megadott szám nap eredményeit, míg a többi törli. Az alapértelmezett érték 7 nap.

-   A feladat **végrehajtásához tartozó óraszám** – A törlendő előzmények számától függően a törlési feladat teljes végrehajtási ideje néhány perctől néhány óráig tarthat. Ezt a paramétert a feladat által végrehajtandó órák számával kell megadni. Miután a tisztítási feladat végrehajtása megtörtént a megadott számú órán belül, a feladat kilép, és a következő futtatásakor folytatja a karbantartást.

    A maximális végrehajtási idő a feladat futási idejének felső határértékével adható meg. A tisztítási logika egyszerre egy feladat-végrehajtási azonosítót végez el, időrendi sorrendben, az előzmények törlését a legrégebbivel kezdi. Nem vesz át további végrehajtási azonosítókat törésre, amikor a fennmaradó végrehajtási időtartam a megadott időtartan utolsó 10%-án belül van. Egyes esetekben várható, hogy a törlési feladat a megadott maximális idő után is folytatódni fog. Ez nagyban függ attól, hogy hány rekordot kell törölni az aktuális végrehajtási azonosító alapján amely még a 10%-os küszöb elérése előtt indult el. Az adatok sértetlenségének biztosításához az elindított törlési feladatot is el kell végezni, ami azt jelenti, hogy a törlése a megadott korlát túllépése ellenére is folytatódni fog. Ha ez befejeződött, új végrehajtási azonosító már nem lesz felvéve és a törlési feladat befejeződik. A hátralévő végrehajtási előzmények, amelyek a megfelelő végrehajtási idő hiányában nem lettek törölve, a következő alkalommal kerülnek felvételre, amikorra a törlési feladat ütemezve van. A beállítás alapértelmezett és minimális értéke 2 óra.

-   **Ismétlődő köteg** – A törlési feladat futtatható egyszeri, manuális végrehajtással, vagy ismétlődő kötegelt végrehajtás is ütemezhető. A köteget be a **Futtatás a háttérben** beállítások segítségével beállításokkal lehet ütemezni, ez a standard kötegelési beállítás.

> [!NOTE]
> Ha az előkészítési táblák rekordjait nem teljes mértékben tisztították meg, győződjön meg arról, hogy az tisztítási feladat futtatása ismétlődő ütemezésű. A fentieknek megfelelően a tisztítási művelet során a feladat csak annyi végrehajtási azonosítót tisztít meg, amennyi a megadott maximum órán belül lehetséges. Ha folytatni szeretné a fennmaradó előkészítési rekordok tisztítását, akkor a feladatnak rendszeresen futnia kell.

## <a name="job-history-clean-up-and-archival"></a>Feladatelőzmények tisztítása és archiválása 
A feladat előzmények törlése és archiválása funkció felülírja a karbantartás funkció korábbi verzióit. Ez a szakasz ezeket az új képességeket fogja elmagyarázni.

A karbantartás funkció egyik fő változtatása a rendszer kötegelt munkájának használata a előzmények törlésére. A rendszer kötegelt feladatának használata lehetővé teszi, hogy a pénzügyi és a műveletalkalmazások a tisztítási kötegelt feladatot automatikusan ütemezni és futtatják, amint a rendszer készen áll. A kötegelt feladat manuális ütemezésére már nincs szükség. Ebben az alapértelmezett végrehajtási módban a kötegelt feladat éjféltől óránként indul, és a legutóbbi 7 nap végrehajtási előzményeit fogja megtartani. A program archiválja a kiürített előzményeket a jövőbeli visszakeresés céljából. A 10.0.20-as verziótól kezdve ez a funkció mindig be van kapcsolva.

A karbantartási folyamat második változása a törölt végrehajtási előzmények archiválása. A karbantartási feladat archiválja a törölt rekordokat a blob-tárolóba amelyet a DIXF használ a rendszeres integrációhoz. Az archivált fájl DIXF-csomagformátumú lesz, és 7 napig elérhető lesz a blobban, és ekkor azt le lehet tölteni. Az archivált fájl alapértelmezett megtartási időtartama 7 nap, ami legfeljebb 90 napra módosítható a paraméterekben.

### <a name="changing-the-default-settings"></a>Az alapértelmezett beállítások módosítása
Ez a funkció jelenleg a előzetes verziójú, és DMFEnableExecutionHistoryCleanupSystemJob tesztfeladat engedélyezésével explicit módon be kell kapcsolni. Az előkészítés-karbantartás funkciónak is be kell lennie kapcsolva a funkciókezelés modulban.

Ha módosítani szeretné az archivált fájl megtartásának alapértelmezett beállítását, nyissa meg az adatkezelési munkaterületet, és válassza a **Feladatelőzmények törlése** elemet. A **Megtartása a blobban** elemet 7és 90 közötti értékre állíthatja be. Ez a módosítás után létrejövő archívumokra lesz érvényes.

### <a name="downloading-the-archived-package"></a>Az archivált csomag letöltése
Ez a funkció jelenleg a előzetes verziójú, és DMFEnableExecutionHistoryCleanupSystemJob tesztfeladat engedélyezésével explicit módon be kell kapcsolni. Az előkészítés-karbantartás funkciónak is be kell lennie kapcsolva a funkciókezelés modulban.

Az archivált végrehajtási előzmények letöltéséhez nyissa meg az adatkezelési munkaterületet, és válassza ki a **Feladatelőzmények törlése** elemet. Válassza ki a **Csomag mentési előzményeit** az előzmények képernyő megnyitásához. Ez az űrlap az archivált csomagok listáját tartalmazza. Az Archívum kiválasztható és letölthetõ a **Csomag letöltése** lehetőség kiválasztásával. A letöltött csomag a DIXF csomagformátumban lesz, és a következő fájlokat tartalmazza:

-   Az entitás előkészítési táblájának fájlneve
-   DMFDEFINITIONGROUPEXECUTION
-   DMFDEFINITIONGROUPEXECUTIONHISTORY
-   DMFEXECUTION
-   DMFSTAGINGEXECUTIONERRORS
-   DMFSTAGINGLOG
-   DMFSTAGINGLOGDETAILS
-   DMFSTAGINGVALIDATIONLOG



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

