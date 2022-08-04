---
title: Mobileszközök beállítása raktári munkához
description: Ez a cikk bemutatja, hogyan kell konfigurálni a raktári munkások által munkára használt menüpontokat egy mobileszközön.
author: Mirzaab
ms.date: 03/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFSysDirSort, WHSWorkUserDisplaySettings
audience: Application User
ms.reviewer: kamaybac
ms.custom: 29941
ms.assetid: 6dff6313-dc6e-4f06-9c0c-dab24eefe4da
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ef392fd744a68c54bc0438152b3487233ac5c7f3
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9070349"
---
# <a name="set-up-mobile-devices-for-warehouse-work"></a>Mobileszközök beállítása raktári munkához

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja, hogyan kell konfigurálni a raktári munkások által munkára használt menüpontokat egy mobileszközön.

> [!NOTE]
> Ez a cikk a Raktárkezelés funkcióira vonatkozik. A Készletkezelés funkciókra nem vonatkozik. A menüpontok, amelyek a raktári mobileszközön jelennek meg, a **Mobileszköz menüpontok** oldalon vannak konfigurálva. Mivel a menüelemek különféle menükbe sorolhatók, könnyen lehet úgy konfigurálni a menü szerkezetét, hogy bizonyos típusú munkák csak bizonyos felhasználók számára legyenek elérhetők. Beállíthatja, hogy a menüelemekkel a következő feladatok legyenek elvégezhetők:

- Kérelem feldolgozása vagy tevékenység elvégzése, például címke nyomtatása, rendszámtáblák létrehozása, termelési rendelés indítása vagy cikkekre vonatkozó információk gyors megkeresése egy helyen.
- Hozzon létre egy másik folyamaton keresztül elvégzendő munkát. Például egy beszerzési rendelés elemének fogadása betárolási munkát hozhat létre egy másik dolgozó számára.
- Munka elvégzése, amelyet egy másik folyamatban hoztak létre (meglévő munka), például betárolási munkáé, amely beszerzési rendeléshez tartozó elem fogadásakor jött létre.

Menüelem létrehozásához tevékenységhez vagy lekérdezéshez állítsa a **Mód** mezőt **Közvetett** értékre. Ekkor elérhetővé válik a **Tevékenységkód**-lehetőségek listája, és kiválaszthatja a lekérdezés vagy tevékenység típusát, amelyre a menüelem vonatkozni fog. Raktári munka létrehozására szolgáló menüelem készítéséhez állítsa a **Mód** mezőt **Munka** értékre. Ekkor elérhetővé válik a **Munkalétrehozási folyamat** lehetőségeinek listája. Ha szeretne létrehozni egy meglévő raktári munka feldolgozására való menüelemet, állítsa a **Mód** mezőt **Munka** állásba, majd állítsa a **Meglévő munka használata** opciót az **Igen** lehetőségre. 

> [!NOTE]
> A menüelemhez kiválasztott módtól, és attól függően, hogy a menüelem használatos-e meglévő munkához, további mezők lehetnek elérhetők a menüelemhez. A további mezőválasztékkal kapcsolatos tudnivalókat lásd a jelen cikk „További menüelem-beállítások” című, későbbi szakaszában.

## <a name="configure-menu-items-for-activities-and-inquiries"></a>Menüelemek konfigurációja tevékenységekhez és lekérdezésekhez

Ha a **Mód** mezőjének értéke egy menüelemnél **Közvetett** opcióra van állítva, létrehozhat egy általános tevékenység vagy lekérdezés elvégzéséhez való menüelemet, amely nem hoz létre a munkát. Például ezek közé tartozik az azonosító táblák címkéinek újranyomtatása és az egy helyen található cikkekre vonatkozó lekérdezések. A következő táblázat az elérhető lehetőségeket sorolja fel:

| Lehetőség | Leírás |
|---|---|
| Egyik sem | Ez az alapértelmezett érték nem engedélyez tevékenységet vagy lekérdezést. |
| Névjegy | A rendszerrel kapcsolatos információk megtekintése, például a verziószám, a raktárazonosító és a dolgozó, aki jelenleg be van jelentkezve. |
| Raktár módosítása | Módosítsa a raktárat, ahol a munkavállaló be van jelentkezve. |
| Hely lekérdezése | Minden cikkel és mennyiséggel kapcsolatos információk megtekintése. |
| Azonosítótábla lekérdezése | Azonosító tábla elemei mennyiségének és az azonosító tábla helyének megjelenítése. |
| Termelési rendelés indítása | Termelési rendelés indítása. |
| Termelési selejt | Adja meg az egyes anyagjegyzék-sorokhoz (BOM) létrehozott selejtmennyiséget. |
| Termelés – utolsó raklap | Jelezze, hogy a cikkek utolsó raklapja termelési rendelésre készült, és hogy a termelési rendelés állapotát a **Bejelentés készként** lehetőségre kell frissíteni. A termelés során nem felhasznált nyersanyagok állapota visszaáll **Kitárolva** értékről **Megrendelt** értékre, és a cikkek visszaküldhetők a készletbe. |
| Cikklekérdezés | Olvasson be egy cikket, hogy meghatározza, hol helyezkedik el a raktárban. A lekérdezés megadja a leolvasott cikkek helyét és mennyiségét. |
| Címke újranyomtatása | Azonosítótábla címkéjének újranyomtatása. |
| Azonosítótábla felépítése | Szülő azonosítótábla létrehozása több azonosítótáblák kombinációjával azonos helyen. Ez a lehetőség akkor hasznos, ha egyszerre több azonosító táblát helyez át. A szülő azonosítótábla áthelyezése után egyy azonosítótábla-felbontást kell végeznie, mielőtt kiválaszthatja az egyes azonosítótáblákból származó cikkeket. <p></p>**Tipp:** Szülő azonosító tábla áthelyezéséhez olyan mobileszközt kell használnia, amely munka létrehozására van beállítva. |
| Azonosítótábla felbontása | Bontson fel egy azonosítótábla-felépítést, hogy kiválaszthasson cikkeket a buildben szereplő azonosítótáblákból. |
| Járművezető bejelentkezése | Ha Szállításkezelést használ, regisztrálja a vezető megérkezését a kimenő rakodási azonosító, találkozóazonosító vagy szállítmányazonosító beolvasásával. Ehhez az opcióhoz az szükséges, hogy a rakomány hozzá legyen rendelve a találkozóhoz, és hogy a rakomány állapota **Berakodva** legyen. |
| Járművezető kijelentkezése | Regisztrálja, hogy a vezető befejezte a találkozóját. |
| Készpénz-számsorozat gyorsítótárának kiürítése | Törölje a sorozatszámokat a gyorsítótárból. Ezt a tevékenységet általában rendszergazda végzi gyorsítótárazási problémák megoldásához, mobileszközök használata esetén. |
| Köteg intézkedésének módosítása | Engedélyezze, hogy a dolgozó megadhassa a köteg intézkedéskódját egy cikkhez és köteghez. Ez a választás frissíti az intézkedési kódot, amely a köteghez meg van adva. |
| Nyitott munkalista megjelenítése | Egy adott felhasználó számára elérhető munka listájának megjelenítése. A felhasználó kiválaszthatja az elvégzendő munkát, és a rendszer átirányítja a munkához. Ennek a listának a megtekintése táblagép eszközön ajánlott, 7 hüvelyk vagy annál nagyobb méretű kijelzőn. Ha bejelöli ezt a lehetőséget, a **Lekérdezés szerkesztése** és a **Mezőlista** menüelemek elérhetővé válnak. A **Lekérdezés szerkesztése** oldalon feltételeket állíthat be a listában megjelenő munkához.. A **Mezőlista** lapon megadhatja, hogy milyen mezők jelenjenek meg a munkalistán. Például csökkentheti a látható mezők számát, hogy a felhasználó számára gyorsabbá tegye a legmegfelelőbb munkatétel kiválasztását. Az **Általános** gyorslapon, a **Rekord oldalanként** mezőben bejelölheti, hogy oldalanként hány munka rekordot szeretne megjeleníteni. Ha a **Felhasználók engedélyezése a munka tranzakciótípusonkénti szűrésére** opció ki van választva, a felhasználó látni fog egy **Munka szűrése** vezérlőelemet a munkalistában, amely lehetővé teszi a tranzakciótípus szerinti szűrést. A felhasználók csak azokat a munkákat fogják látni a munkalistában, amelyekhez rendelkeznek hozzáféréssel. Ellenőrizze, hogy a felhasználóknak van-e engedélyük egy vagy több felhasználó által irányított menüelemekhez, amelyek támogatják a meghatározott munkaosztály-típusokat, amelyekhez hozzá kell, hogy férjenek. Az engedélyek akkor kerülnek ellenőrzésre, amikor egy felhasználó megkísérli a munka végrehajtását a listából.|
| Átmozgatási rendelés létrehozása azonosítótáblákból | Lehetővé teszi a raktári dolgozók számára, hogy közvetlenül a Raktárkezelés mobilalkalmazásból hozzanak létre és dolgozzanak fel átmozgatási rendeléseket. A raktári dolgozók azzal kezdik, hogy kiválasztják a célraktárat, majd az alkalmazás segítségével egy vagy több azonosítótáblát beolvasnak. Ha a raktári dolgozó kiválasztja a **Rendelés teljesítése** elemet, akkor egy kötegelt feladat létrehozza a szükséges átmozgatási rendelést és a rendelési sorokat az adott azonosítótáblákhoz regisztrált aktuális készlet alapján. További információért lásd: [Átmozgatási rendelések létrehozása raktári alkalmazásból](create-transfer-order-from-warehouse-app.md).

## <a name="configure-menu-items-to-create-work-for-another-worker-or-process"></a>Menüelemek konfigurációja munka létrehozásához egy másik dolgozónak vagy folyamatnak

Létrehozhat egy menüelemet, amely egy másik dolgozónak hoz létre munkát egy kezdeti művelet végrehajtása után a mobileszközön. Például amikor egy dolgozó mobileszközzel bevételez egy cikket, betárolási munka jön létre egy további dolgozó számára. Munkát létrehozó menüelem beállításához a **Mobileszköz menü elemei** oldalon, a **Mód** mezőben válassza ki **Munka** lehetőséget. A következő táblázatban a **Munka-létrehozási folyamat** mező opciói munkarendelés-típus szerint vannak rendezve.

<table>
<tbody>
<tr>
<th>Munkarendelés típusa</th>
<th>Lehetőség</th>
<th>Leírás</th>
</tr>
<tr>
<td rowspan="8">Beszerzési rendelés</td>
<td>Beszerzésirendelés-sor bevételezése</td>
<td>Regisztrálja a cikkmennyiség bevételezését a beszerzési rendelés számával és a beszerzési rendelés sorának számával, és hozzon létre betárolási munkát egy másik dolgozó számára.</td>
</tr>
<tr>
<td>Beszerzésirendelés-sor bevételezése és betárolása</td>
<td>Regisztrálható a cikkmennyiség bevételezése a beszerzési rendelés számával és a beszerzési rendelés sorának számával, majd tárolja be a cikkeket. Ugyanaz a dolgozó hajtja végre mindkét műveletet.</td>
</tr>
<tr>
<td>Beszerzési rendelési cikk bevételezése</td>
<td>Regisztrálja a cikkmennyiség bevételezését egy beszerzési rendelésnél úgy, hogy regisztrálja a beszerzési rendelés számát és a cikkszámot, és hozzon létre betárolási munkát egy másik dolgozó számára.</td>
</tr>
<tr>
<td>Beszerzési rendelés – cikk bevételezése és eltárolása</td>
<td>Regisztrálható a cikkmennyiség bevételezése a beszerzési rendeléshez a számának és a cikkszámnak a regisztrálásával, majd tárolja be a cikket. Ugyanaz a dolgozó hajtja végre mindkét műveletet.</td>
</tr>
<tr>
<td>Azonosítótábla bevételezése</td>
<td>Fogadja a bejövő előzetes kiszállítási értesítést (ASN) az azonosító tábla azonosítója segítségével.</td>
</tr>
<tr>
<td>Azonosítótábla bevételezése és eltárolása</td>
<td>Fogadja és a betárolja a bejövő előzetes kiszállítási értesítést (ASN) az azonosító tábla azonosítója segítségével.</td>
</tr>
<tr>
<td>Rakomány – cikk bevételezése</td>
<td>Regisztrálja a cikk mennyiségének bevételezését egy rakományhoz a rakományazonosító segítségével, és hozzon létre egy betárolási munkát egy másik dolgozónak. A cikkszám és a termékdimenziók hozzárendelik a nyugtát a beszerzésirendelés-sorokhoz.</td>
</tr>
<tr>
<td>Rakomány – cikk bevételezése és eltárolása</td>
<td>A rakományazonosító használatával rögzítse a rakomány fogadását, és tárolja be a cikkeket. A cikkszám és a termékdimenziók hozzárendelik a nyugtát a beszerzésirendelés-sorokhoz. Ugyanaz a dolgozó hajtja végre mindkét műveletet.</td>
</tr>
<tr>
<td rowspan="2">Visszárurendelés</td>
<td>Visszárurendelés bevételezése</td>
<td>Regisztrálja a cikk mennyiségének bevételezését az RMA szám rögzítésével, és hozzon létre egy betárolási munkát egy másik dolgozónak.</td>
</tr>
<tr>
<td>Visszárurendelés bevételezése és eltárolása</td>
<td>Regisztrálja a cikk mennyiségének bevételezését az RMA szám rögzítésével, és tárolja be a cikkeket. Ugyanaz a dolgozó hajtja végre mindkét műveletet.</td>
</tr>
<tr>
<td rowspan="6">Átmozgatási rendelés</td>
<td>Átmozgatási rendelés – cikk bevételezése</td>
<td>Regisztrálja a cikk mennyiségének bevételezését, és hozzon létre egy betárolási munkát egy másik dolgozónak.

<strong>Megjegyzés:</strong> Ezt a lehetőséget csak akkor használja, ha a cikkeket olyan raktárból szállították, amely nincs engedélyezve a raktárkezelési folyamatokhoz (WMS).</td>
</tr>
<tr>
<td>Átmozgatási rendelés – cikk bevételezése és eltárolása</td>
<td>Regisztrálja a cikkmennyiség bevételezését, és tárolja el a cikkeket. Ugyanaz a dolgozó hajtja végre mindkét műveletet.

<strong>Megjegyzés:</strong> Ezt a lehetőséget csak akkor használja, ha a cikkeket olyan raktárból szállították, amely nincs engedélyezve a raktárkezelési folyamatokhoz (WMS).</td>
</tr>
<tr>
<td>Átmozgatási rendelés – sor bevételezése</td>
<td>Regisztrálja a cikk mennyiségének bevételezését, és hozzon létre egy betárolási munkát egy másik dolgozónak.</td>
</tr>
<tr>
<td>Átmozgatásirendelés-sor bevételezése és betárolása</td>
<td>Regisztrálja a cikkmennyiség bevételezését, és tárolja el a cikkeket. Ugyanaz a dolgozó hajtja végre mindkét műveletet.</td>
</tr>
<tr>
<td>Azonosítótábla bevételezése</td>
<td>Fogadja a bejövő előzetes kiszállítási értesítést (ASN) az azonosító tábla azonosítója segítségével.</td>
</tr>
<tr>
<td>Azonosítótábla bevételezése és eltárolása</td>
<td>Fogadja és a betárolja a bejövő előzetes kiszállítási értesítést (ASN) az azonosító tábla azonosítója segítségével.</td>
</tr>
<tr>
<td rowspan="4">Termelés</td>
<td>Készként jelentés</td>
<td>Regisztrálja egy befejezett cikk mennyiségét, amely befejeződött a termeléshez, és hozzon létre betárolási munkát egy másik dolgozónak. A mennyiség lehet a termelésre tervezett mennyiség része vagy egésze.</td>
</tr>
<tr>
<td>Készként jelentés és betárolás</td>
<td>Regisztrálja egy befejezett cikk mennyiségét, amely befejeződött a termeléshez, és tárolja el a cikkeket. A mennyiség lehet a termelésre tervezett mennyiség része vagy egésze. Ugyanaz a dolgozó hajtja végre mindkét műveletet.</td>
</tr>
<tr>
<td>Kanban</td>
<td>Adja meg, hogy a Kanban befejeződött, és hozzon létre betárolási munkát egy másik dolgozó számára.</td>
</tr>
<tr>
<td>Kanban betárolás</td>
<td>Jelezze, hogy a Kanban befejeződött, és tárolja be a cikkeket. Ugyanaz a dolgozó hajtja végre mindkét műveletet.</td>
</tr>
<tr>
<td rowspan="5">Készlet</td>
<td>Áthelyezés</td>
<td>Rögzítse, hogy cikkek kerültek egyik helyről a másikra. A dolgozó megadja a cikkek forráshelyét és célhelyét.</td>
</tr>
<tr>
<td>Karantén</td>
<td>Aktuális készlet állapotának módosítása azonosítótáblához vagy helyhez sérült vagy hiányzó készletcikkek nem érhetőként feltüntetéséhez.</td>
</tr>
<tr>
<td>Mozgás sablon szerint</td>
<td>Cikkek áthelyezése egyik helyről egy másikra félig automatikus módon. A dolgozó kiválasztja a forráshelyet, és a rendszer a helyutasítás segítségével meghatározza a cikkek célhelyét.</td>
</tr>
<tr>
<td>Raktári átmozgatás</td>
<td>Rögzítse, hogy cikkek kerültek egyik raktárból a másikba. Ehhez az opcióhoz az szükséges, hogy a dolgozó mindkét raktárban végezhessen munkát.

<strong>Megjegyzés:</strong> Ez a menüpont egy olyan alapértelmezett készletmozgatási naplót követel meg, amelynek a <strong>Bizonylatkiállítás</strong> mezője a <strong>Feladás</strong> opcióra van állítva.</td>
</tr>
<tr>
<td>Azonosítótábla rakodása</td>
<td>Ezt a lehetőséget akkor használja, amikor először állítja be a raktárat. Olvassa be az összes azonosító táblát minden helyen a raktárban. A helyeknek azonosítótáblás szabályozásúaknak kell lenniük. Nem használhatja ezt az opciót, ha a <strong>Sorozatszám</strong> vagy a <strong>Kötegszám</strong> a készletfoglalási hierarchiában a <strong>Hely</strong> felett szerepel.</td>
</tr>
<tr>
<td rowspan="3">Ciklikus leltározás</td>
<td>Igazítás be</td>
<td>A készletcikkek mennyiségének növelése. Adja meg a helyet, az azonosítótáblát, a cikket, a mennyiséget, a mértékegységet és az állapotot.</td>
</tr>
<tr>
<td>Igazítás ki</td>
<td>A készletcikkek mennyiségének csökkentése. Adja meg a készlet helyét, azonosítótábláját, cikkét, mennyiségét, mértékegységét és állapotát.</td>
</tr>
<tr>
<td>Eseti ciklikus leltár</td>
<td>Kezdje el a hely számlálását. A dolgozónak meg kell számolnia a hely minden cikkét. Ha a leltározás eredménye kisebb, mint a várható mennyiség, a hiányzó mennyiség veszteségnek minősül.</td>
</tr>
</tbody>
</table>

## <a name="configure-menu-items-to-process-existing-work"></a>Menüelemek konfigurálása a meglévő munka feldolgozásához
A menüelemek raktári munka létrehozására történő beállításán kívül a már létrehozott munkák feldolgozására is állíthat be menüelemeket. Állítsa a **Mód** mezőt a **Munka** lehetőségre, és válassza ki a **Meglévő munka használata** lehetőséget. Ezután néhány további lehetőség lesz elérhető az **Általános** lapon. A menüelemhez való hozzáférést úgy szabályozhatja, hogy egy vagy több munkaosztályt rendel hozzá a **Munkaosztály** gyorslapon. A munkaosztályok határozzák meg a munkát, amelyet a menüelem fel tud dolgozni. A munkaosztály arra is használható, hogy hozzáférést biztosítson adott felhasználói szerepkörök számára, illetve elválaszthatók vele a különböző műveletek feldolgozása. A következő táblázat az elérhető lehetőségeket írja le: A beállítás az **Irányítja** mezőben választható ki a **Mobileszköz menüpontjai** oldalon. 

<table>




<thead>
<tr class="header">
<th>Lehetőség</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Egyik sem</td>
<td>Ez az alapértelmezett érték nem dolgozza fel a munkát.</td>
</tr>
<tr class="even">
<td>Rendszer által irányított</td>
<td>A Supply Chain Management szabályozza a munka típusát a dolgozóhoz társítva, és a megrendelést, amelyen a dolgozó munkát végez. Amikor ezt a beállítást választja, kattintson <strong>Rendszer által irányított munka</strong> elemre a műveletpanelen a <strong>Rendszer által meghatározott rendezési sorrend</strong> oldal megnyitásához, amelyen beállíthatja rendezési feltételeket a munkához. A rendezési feltételek azt szabályozzák, hogy a dolgozó milyen sorrendben hajtja végre a munkát. Annyi feltételt adhat hozzá, amennyire szüksége van.</td>
</tr>
<tr class="odd">
<td>Felhasználó által irányított</td>
<td>A dolgozó kiválasztja az elvégzendő munkát és az elvégzés sorrendjét.</td>
</tr>
<tr class="even">
<td>Felhasználócsoportosítás</td>
<td>A dolgozó manuálisan csoportosítja a munkát. Ez az opció például akkor hasznos, ha egy dolgozó egyszerre több cikket tárol ki egy helyen. Miután a dolgozó végzett az összes szükséges cikk kiválasztásával, tárolhatja a cikkeket.</td>
</tr>
<tr class="odd">
<td>Rendszercsoportosítás</td>
<td>A Supply Chain Management csoportok egy megadott mező dolgozójának munkája alapján működnek. Például a kitárolási munka csoportosított, ha egy dolgozó beolvas egy szállítmányazonosítót, terhelésazonosítót vagy bármely értéket, amely minden munkaegységhez csatolható. Ha ezt a lehetőséget választja, akkor a következő mezőket kell kitöltenie:
<ul>
<li><strong>Rendszercsoportosítás mezője</strong> – Válassza ki azt a mezőt, amelyet a dolgozó beolvas a munka csoportosításához.</li>
<li><strong>Csoportosító rendszercímke</strong> – Adja meg a szöveget, amely tájékoztatja a dolgozót, hogy mit olvasson be a munka csoportosításához.</li>
</ul></td>
</tr>
<tr class="even">
<td>Ellenőrizve, felhasználó által irányítva</td>
<td>A dolgozó kiválasztja a végrehajtandó munkát, ha a munka egy nagyobb entitással, például terheléshez vagy szállítmányhoz van társítva. A dolgozó a cikkek kitárolásának sorrendjét határozza meg. Ha ezt a lehetőséget választja, akkor a következő mezőket kell kitöltenie:
<ul>
<li><strong>Ellenőrizve, felhasználó által irányítva mező</strong> – Válassza ki azt a mezőt, amelyet a dolgozó beolvas a munka csoportosításához.</li>
<li><strong>Ellenőrizve, felhasználó által irányítva</strong> – Adja meg a szöveget, amely tájékoztatja a dolgozót, hogy mit olvasson be, amikor a rendszer csoportosítja kitárolási munkát.</li>
</ul>
Ez például akkor hasznos, ha például több raklap van előkészítve egy rakodáshoz. Ha bejelöli a <strong>LoadId</strong> lehetőséget az <strong>Ellenőrizve, felhasználó által irányítva</strong> mezőben, a dolgozó tárolhatja a rakományhoz társított bármelyik raklapot. Ha a dolgozó olyan cikket vizsgál meg, amely nincs társítva a rakományhoz, hibaüzenet jelenik meg.</td>
</tr>
<tr class="odd">
<td>Fürt kitárolása</td>
<td>A dolgozói csoportok fürtökben dolgoznak. A fürtök lehetővé teszik, hogy a dolgozók egy helyről egyszerre több munkarendelés cikkeit is tárolják.</td>
</tr>
<tr class="even">
<td>Ciklikus leltározás csoportosítása</td>
<td>A dolgozó kiválaszt egy zónát, munkagyűjtőt vagy helyet, és a Supply Chain Management hozzárendeli a munkát a kiválasztás alapján. Ha ezt a lehetőséget választja, akkor kattinthat a <strong>Ciklikus leltározás</strong> elemre a Műveleti ablakban további adatok megjelenítésének beállításához, és megadhatja, hogy a dolgozónak hányszor kell megismételnie a leltárt, ha eltérés van.</td>
</tr>
 <tr class="odd">
<td>Szállítási berakodás</td>
<td>Ez a funkció lehetővé teszi, hogy több raktári dolgozó ugyanabból vagy különböző rakományokból rakodhasson készletet ugyanarra a targoncára, teljesen vagy részlegesen kiszállított rakományokkal.</td>
</tr>
</tbody>
</table>

## <a name="additional-menu-item-options"></a>Kiegészítő menüpont-lehetőségek
További menüpont-opciók érhetők el a **Mobileszköz menü elemei** oldalon. A lehetőségek eltérőek lehetnek a folyamattól függően, amelyhez a menüelemet konfigurálja. 

Az alábbi táblázatban található ezeknek a beállításoknak az ismertetése.

<table>




<thead>
<tr class="header">
<th>Mező</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Munka felosztásának engedélyezése</td>
<td>Jelölje be ezt az opciót, bejelölésével engedélyezheti a felhasználóknak a munka rendelés cikkeinek üzembe egynél több cél azonosítótáblát. Ez az opció akkor hasznos, ha például a cél azonosító tábla megtelt, és a dolgozónak a fennmaradó cikkeket egy másik azonosító táblához kell hozzáadnia. A dolgozó a <strong>Megtelt</strong> lehetőség kiválasztásával jelezheti, hogy az azonosítótábla megtelt, és leállíthatja az erre vonatkozó összeszedési folyamatot. Ekkor megjelenik a kitárolt cikkek a betárolási hely, és egy új Munkarendelés kerül a kitárolási munka, amely már befejeződött. A fennmaradó munka a cél azonosítótáblát a kitárolási munka az eredeti rendelésen marad.</td>
</tr>
<tr class="even">
<td>Horgonyzás</td>
<td>Az opció kiválasztásával engedélyezi a dolgozók számára, hogy megadjanak egy helyet, amely felülbírálja a javasolt előkészítési vagy berakodási helyet. A fennmaradó összes betárolási munka az új helyre irányul. Ez az opció akkor hasznos például, ha egy dolgozónak az 1. megrendelés cikkeit az 1. tároló előkészítő helyére kell tennie, de ez nem lehetséges, mert egy előző rakományt a rendszer még nem törölt az adott helyről. Ahelyett, hogy arra várna, hogy az 1. tároló előkészítési helye felszabaduljon, a dolgozó dönthet úgy, hogy inkább a 2. tároló előkészítési helyét használja. Ebben az esetben a dolgozó felülírja a javasolt előkészítési helyet. Ekkor a megrendelés fennmaradó cikkeinek betárolási helyét a rendszer a 2. tároló előkészítési helyére frissíti. Ha ezt a lehetőséget választja, meg kell adni a <strong>Horgonyzó</strong> mezőt.</td>
</tr>
<tr class="odd">
<td>Horgonyzó</td>
<td>Ha a horgonyzást használja, meg kell adnia, hogy a szállítmány vagy a rakomány alapján szeretne horgonyozni.</td>
</tr>
<tr class="even">
<td>Vizsgálati sablon azonosítója</td>
<td>Válassza ki azt a munkaellenőrzési sablont, amely megállítja ennek a menücikknek a munkafolyamatát, hogy egy másik folyamatot kezdhessen el. Például ha ez a menüpont a bejövő munkához áll rendelkezésre, a vizsgálati sablon megkövetelheti, hogy a dolgozó ellenőrizze a szállítási tároló hőmérsékletét. A vizsgálati sablon adja meg a pontot, ahol a folyamat megszakad. Ez a pont lehet például munka kezdése vagy befejezése, vagy amikor megváltozik az állapota.</td>
</tr>
<tr class="odd">
<td>Fürtprofil azonosítója</td>
<td>A fürtkitároláshoz használandó fürtprofil kiválasztása. A fürtprofil olyan beállításokat tartalmaz, mint például a fürtök automatikus létrehozása, a hozzárendelhető munkaegységek száma és a beosztások neve, hogy mikor bontsa fel az egyedi egységekké a fürtöket és hogy szükséges-e ellenőrzés. Ez a mező csak akkor érhető el, ha a <strong>Fürt kitárolása</strong> beállítás van kiválasztva az <strong>Irányítja</strong> mezőben.</td>
</tr>
<tr class="even">
<td>Először a teljes cikkmennyiség számlálása</td>
<td>Az opció kiválasztásával kötelezővé teheti a dolgozó számára, hogy a leltározás során először számlálja meg a teljes mennyiséget. Amennyiben eltérést talál, a dolgozónak további információkat kell adnia, például az azonosító tábla számát, a kötegszámot és sorozatszámokat.</td>
</tr>
<tr class="odd">
<td>Mozgás létrehozása</td>
<td>Jelölje be ezt a lehetőséget ahhoz, hogy dolgozó anélkül hozhasson létre egy átmozgatási munkát, hogy azt azonnal végre kéne hajtania. Ez a lehetőség például akkor hasznos, ha a minőségellenőrzés befejeződött, és az ellenőr szeretné áthelyezni a cikket a minőségi vizsgálati területről.</td>
</tr>
<tr class="even">
<td>Utasításkód</td>
<td>Egy adott helyszín-irányelv használatához jelölje be azt az utasításkódot, amely ahhoz kapcsolódik. Ez a mező akkor érhető el, amikor munkát hoz létre, és a munka létrehozásának folyamata <strong>Mozgás sablon szerint</strong>.</td>
</tr>
<tr class="odd">
<td>Ciklikus leltározási küszöbértékek letiltása</td>
<td>Jelölje be ezt a lehetőséget a ciklikus leltározási küszöbértékek figyelmen kívül hagyásához. Ha bejelöli ezt a lehetőséget, a ciklikus leltározási munka nem jön létre a küszöbértékek túllépése esetén.</td>
</tr>
<tr class="even">
<td>Köteg intézkedési kódjának megjelenítése</td>
<td>Ha meg szeretné jeleníteni a köteg intézkedési kódjait, jelölje be ezt a lehetőséget. A kötegrendelkezési kódokat például megjelenítheti egy visszaadott köteget érkezésekor. Ez lehetővé teszi a dolgozók számára egy köteg állapotának vagy minőségének a kiértékelését, valamint a megfelelő kód kiválasztását. A köteg intézkedéskódjainak szabályai határozzák meg, hogy a köteg más raktárkezelési folyamatok számára is elérhető lesz-e. Ha nem választja ezt a beállítást, a következő kötegrendelkezési kódok közül kell egyet használni:
<ul>
<li>Ha új kötegszám jelenik meg, a cikkmodellcsoportban megadott alapértelmezett kötegrendelkezési kódot fogja a rendszer használni.</li>
<li>A köteghez már hozzárendelt kötegrendelkezési kód</li>
</ul></td>
</tr>
<tr class="odd">
<td>Intézkedési kód megjelenítése</td>
<td>Ha meg szeretné jeleníteni az intézkedési kódokat, jelölje be ezt a lehetőséget. Az intézkedési kódokat például megjelenítheti, ha visszárut kap. Ez lehetővé teszi a dolgozók számára a cikkek állapotának vagy minőségének a kiértékelését, valamint a megfelelő kód kiválasztását. Az intézkedéskódok szabályai határozzák meg, hogy a cikkek más raktárkezelési folyamatok számára is elérhetők lesznek-e.</td>
</tr>
<tr class="even">
<td>Készletállapot megjelenítése</td>
<td>Jelölje be ezt a lehetőséget, ha a készletben található cikkek állapotát meg szeretné jeleníteni. Ez az opció rendelkezésre áll minden olyan menüelemhez ami a már meglévő munkát használja, kivéve a ciklikus leltározást.</td>
</tr>
<tr class="odd">
<td>Kitárolást összefoglaló képernyő megjelenítése</td>
<td>Jelölje be ezt a lehetőséget, ha szeretné megjeleníteni a kiválasztott munkarendeléssel kapcsolatos kiválasztási munka összegzését. Az összegző mindaddig megjelenik, amíg az első munkasort fel nem dolgozza a munkarendeléshez.</td>
</tr>
<tr class="even">
<td>Azonosítótábla előállítása</td>
<td>Jelölje be ezt a lehetőséget, ha a számsorozat kiválasztásával egyedi azonosító táblát szeretne generálni. Például létrehozhat azonosító táblát a beszerzési rendelésekhez bevételezett cikkekhez.</td>
</tr>
<tr class="odd">
<td>Csoportos betárolás</td>
<td>Jelölje be ezt a lehetőséget, ha csoportosítani szeretné a betárolási munkát. Ez a lehetőség akkor érhető el, ha a munka vagy a dolgozó, vagy a Supply Chain Management szerint volt csoportosítva. Ha a dolgozó befejezett minden kitárolási munkát a csoportban, létre lesz hozva egy betárolási munka ugyanahhoz a csoporthoz.</td>
</tr>
<tr class="even">
<td>Készlet-kiigazítás típusai </td>
<td>Válassza ki a készlethelyesbítés típusát, ami meghatározza azt a leltárnaplót, amellyel a korrekciót közzétette, valamint a foglalások eltávolítását. Ez a mező csak az <strong>Igazítás be</strong> vagy <strong>Igazítás ki</strong> munkalétrehozási folyamathoz érhető el.</td>
</tr>
<tr class="odd">
<td>Kötegszám felülbírálata</td>
<td>Ennek a lehetőségnek a bejelölésével lehetővé teszi a termelési rendeléshez egy mennyiséget befejezettként megjelölő dolgozók számára hogy a termelési rendeléshez rendelt kötegszámtól eltérő kötegszámot adjanak meg.</td>
</tr>
<tr class="even">
<td>Cél azonosítótábla felülbírálata</td>
<td>Az opció kiválasztásával lehetővé teszi a dolgozók számára, hogy cél azonosítótábla-számként olyan számot adjanak meg, amely eltér a javasolt cél azonosító táblától. Ezt a lehetőséget akkor használja, ha a munkarendelés első kitárolása az azonosítótábla cikkeinek teljes mennyiségére vonatkozik. Ez a lehetőség jól használható például egy raklap újbóli használatánál.</td>
</tr>
<tr class="odd">
<td>Kitárolás és csomagolás</td>
<td>Jelölje be ezt az opciót ahhoz, hogy a dolgozók számára engedélyezze egy értékesítési rendelés vagy egy terhelés munkájának egyesítését egyetlen munkaegységgé. Egy dolgozó csak az értékesítési rendeléshez vagy a terheléshez végezhet munkát. Ez a lehetőség például akkor hasznos, ha mindenképpen növelnie kell egy értékesítési rendelés mennyiségét a terhelés, a szállítmány és munka létrehozása után az értékesítési rendeléshez. Ez a lehetőséget akkor érhető el, ha a menüelem folyamatban lévő munkát használ és a munkát a felhasználó vagy a rendszer irányítja.</td>
</tr>
<tr class="even">
<td>Legrégebbi köteg kitárolása</td>
<td>Adja meg, hogy a dolgozó egy helyen a legrégebbi köteget válassza-e ki először. Az alábbi lehetőségek közül választhat:
<ul>
<li><strong>Nincs</strong> – A dolgozó bármilyen köteget kiválaszthat a helyen. A dolgozó nem kap üzenetet.</li>
<li><strong>Figyelmeztetés</strong> – A dolgozó bármilyen köteget kiválaszthat a helyen, de figyelmeztető üzenetet kap, ha nem a legrégebbi köteget választja ki.</li>
<li><strong>Kötelező</strong> – A dolgozó a legrégebbi köteget kell, hogy kiválassza a helyen. A dolgozó hibaüzenetet kap, ha a köteg nem legrégebbi köteg. <strong>Megjegyzés:</strong> Ez az opció csak akkor fontos, ha a <strong>Kötegszám</strong> alacsonyabb mint a <strong>Hely</strong> abban a foglalási hierarchiában, amelyhez a cikk tartozik.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Címkenyomtatás</td>
<td>Jelölje be ezt a lehetőséget az azonosító táblák címkéinek nyomtatása engedélyezéséhez a dolgozók számára.</td>
</tr>
<tr class="even">
<td>Csoportosító rendszermező</td>
<td>Válassza ki azt a mezőt, amely meghatározza, hogyan fogja a Supply Chain Management a dolgozók számára a kitárolási munkát csoportosítani. Ha például bejelöli a <strong>ShipmentId</strong> mezőt, a dolgozó ellenőrzi a szállítmányazonosítót a kitárolási munka csoportosításához. A rendszer hozzárendeli a dolgozóhoz a szállítmány minden munkáját. Ez a mező azt igényli, hogy hozzon létre egy menüelemet a rendszer által csoportosított meglévő munka használatához. A <strong>Csoportosító rendszercímke</strong> mezőben is meg kell adnia egy szöveget, amely tájékoztatja a dolgozót, hogy mit olvasson be.</td>
</tr>
<tr class="odd">
<td>Csoportosító rendszercímke</td>
<td>Adja meg a szöveget, amely tájékoztatja a dolgozót, hogy mit olvasson be, ha a kitárolási munkát a Supply Chain Management csoportosítja. Például ha a <strong>Szállítmányazonosító</strong> mezőt használja egy szállítmány kitárolási munkájának csoportosítására, megadhatja a <strong>Szállítási azonosító</strong> értékét a mezőben. Ez a mező azt igényli, hogy hozzon létre egy menüelemet a rendszer által csoportosított meglévő munka használatához. A <strong>Rendszercsoportosítás</strong> mezőben ki kell választania a mezőt is, amely szerint a csoportosítás történik.</td>
</tr>
<tr class="even">
<td>Alapértelmezett adatok használata</td>
<td>Ezzel a lehetőséggel engedélyezheti az <strong>Alapadatok</strong> gombot a Művelet ablakban, ahol kiválaszthatja a dolgozó napi munkájához szükséges adatokat megjelenítő mezőket. Ez a lehetőség például akkor hasznos, ha egy dolgozó a kitárolási cikkeket gyakran ugyanarról a helyről veszi fel. Kiválaszthatja a <strong>Forráshely</strong> mezőt a hely alapértelmezés szerinti megjelenítéséhez.</td>
</tr>
<tr class="odd">
<td>Ellenőrizve, felhasználó által irányítva mező</td>
<td>Válassza ki azt a mezőt, amelyet a dolgozó ellenőrizni fog a munka csoportosításához. Ha például a <strong>LoadId</strong> elemet jelöli be, a dolgozó tárolhat minden, a kiválasztott terheléshez társított munkát. A <strong>Ellenőrizve, felhasználó által irányítva címke</strong> mezőben is meg kell adnia egy szöveget, amely tájékoztatja a dolgozót, hogy mit olvasson be.</td>
</tr>
<tr class="even">
<td>Ellenőrizve, felhasználó által irányítva címke</td>
<td>Adja meg a szöveget, amely tájékoztatja a dolgozót, hogy mit olvasson be, ha a kitárolási munka egy felhasználó által irányított érvényesített mező szerint van csoportosítva. Például ha a <strong>LoadID</strong> mezőt használja egy terhelés kitárolási munkájának csoportosítására, megadhatja a <strong>Terhelésazonosító</strong> értékét a mezőben.</td>
</tr>
<tr class="odd">
<td>Munkasablonkód</td>
<td>Válassza ki azt a munkasablont, amely létrehozza a folyamathoz a munkát. Például ha cikket kap a beszerzési rendeléshez, a betárolási munka a munkasablon alapján jön létre. Ha nem jelöl be munkasablont, a Supply Chain Management hozzárendel egy sablont a lekérdezési feltételek alapján. A Munkasablonokkal kapcsolatos további információkat lásd: <a href="control-warehouse-location-directives.md">A raktári munka ellenőrzése munkasablonok és helyutasítások használatával</a>.</td>
<tr class="even">
<td>Munkasorlista megjelenítése</td>
<td>Válasszon ki egy beállítást, hogy a dolgozók hogyan fogják tudni megtekinteni és megérinteni a kiválasztott kitárolási munka sorait. Ezzel a beállítással kapcsolatos további információkat lásd: <a href="pick-line-overview.md">Mobileszköz menüelemének beállítása a kitárolási sor áttekintésének biztosításához</a>.</td>
</tr>
</tbody>
</table>

## <a name="require-workers-to-confirm-the-product-location-or-quantity-when-they-pick-items"></a>A termék, a hely vagy a mennyiség megerősítésének megkövetelése a dolgozóktól a cikkek kitárolásakor

Beállíthatja a munkák visszaigazolását úgy, hogy azok megköveteljék a dolgozóktól egy mobileszköz használatát a hely vagy a mennyiség regisztrációjához a raktárban való munkavégzés közben. A Munkamegerősítés segíti annak biztosítását, hogy a dolgozó a megfelelő helyen legyen, és a megfelelő cikkmennyiséget kezelje. Engedélyezheti a Supply Chain Management számára dolgozó regisztrációjának automatikus megerősítését is. Ha engedélyezi az automatikus megerősítést, nem tudja a hely vagy a mennyiség visszaigazolását is igényelni. A Munkamegerősítések a termékekre és a termékváltozatokra is vonatkoznak. Valamint lehetősége van a visszaigazolások regisztrálására vonalkód beolvasásával is. Termékek és a termékváltozatok megerősítéséhez meg kell adnia egy azonosítót a termékhez vagy a termékváltozathoz. Ez az azonosító lehet a termék azonosítója, a keresési termékazonosító, a külső azonosító, a GTIN vagy a vonalkód. Miután megadta az azonosítót vagy beolvasta a vonalkódot, a mobileszközön a termékváltozat dimenziói megjelennek. 

A következő táblázat leírja a különféle munkatípusokat, amelyekkel használhatja a munka-visszaigazolásokat.

| Lehetőség | Leírás |
|------------------------|----------------------------------------------------------------------------|
| Választás | Kötelező visszaigazolás a cikkek kitárolásakor. |
| Eltárolás | Kötelező visszaigazolás a cikkek elhelyezésekor a helyen. |
| Számlálás | Kötelező visszaigazolás ciklikus leltározáskor. |
| Kiigazítások | Kötelező visszaigazolás a készletmennyiségek kiigazításakor. |
| Egyéni | Kötelező visszaigazolás egyéni munka esetén. |
| Karantén | Kötelező visszaigazolás a cikkek karanténba való mozgatásakor. |
| Azonosítótábla felépítése | Kötelező visszaigazolás a cikkek azonosító tábla létrehozásához való konszolidálásánál. |
| Nyomtatás | Kötelező visszaigazolás az azonosító táblák címkéinek nyomtatásakor. |
| Állapotváltozás | Kötelező visszaigazolás a készlet állapotának módosításakor. |

> [!NOTE]
> A termék visszaigazolása csak kitárolási és betárolási típusú munkáknál követelhető meg.

## <a name="additional-resources"></a>További erőforrások

- [Mobileszköz menüelemének beállítása beszerzési rendelés típusú munka befejezéséhez](tasks/set-up-mobile-device-menu.md)
- [Mobileszköz-menüelem beállítása a bevételezett elemek regisztrálásához](tasks/set-up-mobile-device-menu-item-register-received-items.md)
- [Készletállapotok](../inventory/inventory-statuses.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
