---
title: "Adatimportálási és -exportálási feladatok"
description: "Az Adatezelése munkaterület segítségével hozhatja létre és kezelheti az adatimportálási és -exportálási feladatokat."
author: Sunil-Garg
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application user
ms.reviewer: margoc
ms.search.scope: Operations
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cf531c3a8f3bdb17314d1de436b98249169f82a3
ms.openlocfilehash: d58bab48c65bb891155af95c79738b019e5760bf
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---

# <a name="data-import-and-export-jobs"></a>Adatimportálási és -exportálási feladatok

[!include [banner](../includes/banner.md)]

Adatimportálási és -exportálási feladatok létrehozásához és kezeléséhez a Microsoft Dynamics 365 for Finance and Operations alkalmazásban használja az **Adatkezelés** munkaterületet. Alapértelmezés szerint az adatimportálási és -exportálási folyamat létrehoz egy előkészítési táblát az egyes entitásokhoz a céladatbázisban. Az előkészítési táblák segítségével ellenőrizhetők, megtisztíthatók és konvertálhatók az adatok a mozgatás előtt.

> [!NOTE]
> Ez a témakör feltételezi, hogy már ismeri az [adatentitásokat](data-entities.md).

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

A témakör hátralévő részei további részleteket tartalmaznak az eljárás egyes lépéseiről.

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

| **Fájlformátum**        | **Sor-/oszlopelválasztó**                   | **XML-stílus**             |
|------------------------|--------------------------------------------|---------------------------|
| Excel                  | Excel                                      | \-–                     |
| XML                    | \-–                                      | XML-elem XML-attribútum |
| Elválasztott, rögzített szélesség | Vessző, pontosvessző, tabulátor, függőleges sáv, kettőspont | \-–                     |



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

![Adatleképezés](./media/dixf-map.png)

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

## <a name="validate-that-the-job-ran-as-expected"></a>Ellenőrizze, hogy a feladat megfelelően futott le
A feladatelőzmények hibaelhárítási és vizsgálati célra rendelkezésre állnak mind az importálási, mint az exportálási feladatoknál. Az előzményfeladat-futtatások időtartományok szerint vannak rendezve.

![Feladat előzménytartományok](./media/dixf-job-history.md.png)

Minden lefuttatott feladat megadja a következő adatokat:

- Végrehajtás részletei
- Végrehajtási napló

A végrehajtás részletei megmutatják a feladat által feldolgozott minden egyes adatentitás állapotát. Ezért gyorsan megtalálhatja a következő adatokat:

- Melyek a feldolgozott entitások
- Egy entitás esetében hány rekord feldolgozása történt meg sikeresen, és hány volt sikertelen
- Az előkészítési rekordok az egyes entitásokhoz

Letöltheti az előkészítési adatokat fájlban az exportálási feladatokhoz, vagy letöltheti csomagként az importálási és exportálási feladatokhoz.

A végrehajtás részleteknél a végrehajtási napló is megnyitható.

## <a name="clean-up-the-staging-tables"></a>Az előkészítési táblák megtisztítása
Az előkészítési táblák adattisztítását elvégezheti **Az előkészítési táblák megtisztítása** funkcióval az **Adatkezelés** munkaterületen. A következő beállítások segítségével választható ki, hogy mely rekordok törlődjenek melyik előkészítési táblából:

- **Entitás** – Ha csak egy entitás van megadva, az entitás előkészítési táblájának minden rekordja törlődik. Ezt a lehetőséget akkor használja, ha minden adatot törölni akar az entitásra nézve, az összes adatprojektben és az összes feladatban.
- **Feladatazonosító** – Ha csak a Feladatazonosító van megadva, a kiválasztott feladat összes entitásának összes rekordja törlődik a megfelelő előkészítési táblákból.
- **Adatprojektek** – Ha csak egy adatprojekt van kiválasztva, a rendszer az összes entitás összes rekordját törli az összes feladatra nézve a kiválasztott adatprojektben.

A lehetőségek kombinálásával tovább korlátozhatja a törölt rekordkészletet.

