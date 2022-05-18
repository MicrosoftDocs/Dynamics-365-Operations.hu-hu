---
title: A levelek kezelése
description: Ez a témakör a levelek kezelését ismerteti. A levél általában egy szállító szállításonként egy entitásnak vagy vállalatnak szánt termékeiből áll. A levélben található áruk lehetnek egy konténerben vagy több konténer között elosztva is.
author: Weijiesa
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMFolioTable, ITMFolioTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: f908ae3c150a09af61bb0ee97469619744cd1079
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695302"
---
# <a name="manage-folios"></a>A levelek kezelése

[!include [banner](../../includes/banner.md)]

A leveleket gyakran vámszabályok határozzák meg. Egy szállító szállításonként egy entitásnak vagy vállalatnak szánt termékeiből állhat. A fóliában található áruk kezelése egy tárolóban van.

Az **Összes levél** oldal megnyitásához nyissa meg a **Partraszállítási költség \> Levelek \> Összes levél** menüpontot. Ez az oldal az összes aktuális levél listáját jeleníti meg. A Művelet panel gombjaival leveleket hozhat létre, törölhet és kezelhet. A lista bármely levelét kiválasztva megtekintheti a részleteit **Levelek** oldalon.

## <a name="action-pane"></a>Műveleti panel

Az **Összes levél** és a **Levelek** oldal Művelet paneljén olyan gombok vannak, amelyek segítségével a kiválasztott levélen dolgozhat. Minden gomb egyetlen műveletet hajt végre. A Művelet panel lapokat is tartalmaz, amelyek viszont kapcsolódó gombokat biztosítanak. A jelezett kivételtől függően az alábbi alszakaszok alatt leírt gombok és lapok mind a listanézetben (azaz az **Összes levél** oldalon), mind a részletes nézetben (azaz a **Levelek** oldalon) elérhetők.

### <a name="buttons-that-appear-directly-on-the-action-pane"></a>A Művelet panelen közvetlenül megjelenő gombok

A következő táblázat a közvetlenül a Művelet panelen elérhető gombok leírását tartalmazza.

| Gomb | Leírás |
|---|---|
| Új | Levél létrehozása. |
| Eltávolítás | A nyitott vagy kiválasztott levél törlése. |
| Út költségei | A **Hajóút költségei** oldal megnyitása, ahol a hajóút minden áruja számára megtekinthetők és hozzáadhatók a levélszintű költségek. Ha a levél költségeit kézzel adják hozzá az hajóúthoz, akkor automatikusan hozzáadódnak a költségek lekérdezése oldalhoz, és a **Hajóút költségei** oldalon megadott módszernek megfelelően arábnyosítva lesznek minden árura. |

### <a name="buttons-on-the-manage-tab"></a>Gombok a Kezelés lapon

A következő táblázat a Művelet panel **Kezelés** lapján elérhető gombok leírását tartalmazza.

| Gomb | Leírás |
|---|---|
| Bevételezési lista feladása | Bevételezési lista feladása a levélen található összes beszerzésirendelés-sorhoz. Többvállalatos szállítmányok használata esetén minden vállalat számára új bevételezésilista-feladási párbeszédpanel nyílik meg. |
| Termékbevételezés feladása | Termékbevételezés feladása a levélben található összes beszerzésirendelés-sorhoz. Többvállalatos hajóút használata esetén minden vállalat számára új termékbevételezés-feladási párbeszédpanel nyílik meg. |
| Számlafeladás | Számla feladása a levélben található összes beszerzésirendelés-sorhoz. Többvállalatos hajóutak használata esetén minden vállalat számára új számlafeladási párbeszédpanel nyílik meg. |
| Átmozgatási rendelések szállítása | Átmozgatási rendelés feladása a kapcsolódó szállítmány aktuális leveléhez tartozó összes átmozgatásirendelés-sorhoz. |
| Átmozgatási rendelés bevételezése | Átmozgatási rendelés bevételezése a kapcsolódó szállítmány aktuális leveléhez tartozó összes átmozgatásirendelés-sorhoz. |
| Úton lévő áruk bevételezése | Minden olyan rendelési sor bevételezése, amely úton van a levélben. |
| Dokumentumok bevételezve | A **Kapott dokumentumok** beállításának frissítése *Igen* értékre. Ezzel a gombbal zárolhatja a cikket és/vagy a beszerzési sort, így azt nem lehet tovább frissíteni. |
| Automatikus költségek keresése | Keresse meg a vonatkozó hajóútköltségeket. Ha ezek a költségek már megtalálhatóak vagy frissítve vannak, a következő üzenet jelenik meg: „Nem számlázott költségsorok léteznek. Felül kívánja írni őket?” Ne feledje, hogy a levélhez kapcsolódó és számlázott hajóútköltségek nem írhatók felül. |
| Érkezési napló létrehozása | Szervezetek érkeztetési naplójának speciális raktári funkciók használatával történő létrehozása. Kiválaszthatja a **Mennyiség inicializálása** (ajánlott), illetve a **Létrehozás úton lévő árukból** és/vagy a **Létrehozás beszerzési rendelésekből** lehetőséget. Az utolsó lehetőség attól függ, hogy használatban van-e az úton lévő áruk feldolgozása. |
| Elhatárolt költségek | Olyan költségek elhatárolása, amelyekben a költségtípushoz meg van adva főkönyvi számla a tartozik tételhez. Ez a gomb általában akkor használatos, amikor a készlet szállítás közben van, vagy amikor az árukat bevételezték és számlázták. |

### <a name="buttons-on-the-general-tab"></a>Gombok az Általános lapon

A következő táblázat a Művelet panel **Általános** lapján elérhető gombok leírását tartalmazza.

| Gomb | Leírás |
|---|---|
| Bevételezések listája | Bevételezési lista feladása a levélen található összes beszerzésirendelés-sorhoz. Többvállalatos hajóút használata esetén minden vállalat számára új bevételezésilista-feladási párbeszédpanel nyílik meg. |
| Termékbevételezés | A termékbevételezési rekord megtekintése, ha használatban van. |
| Cikk érkezése | A cikkérkeztetési napló megtekintése, ha használatban van. |
| Költségek lekérdezése | A költséglekérdezési oldal megnyitása egy hajóút összes költségének megtekintéséhez, beleértve a szállítókonténert, a levelet és a beszerzési rendelést. Az oldal pontos nézetét a Megtekintés művelet segítségével lehet módosítani. A költséglekérdezési lapon megtekintheti bármelyik területet, valamint a cikk- és költségtípuskódot. Ezeknek a cikkeknek a törlésével a költségeket csoportosítva módosíthatja az oldalt. Ez a képesség akkor lehet hasznos, ha méreteket és színeket használ. A lapon megjelenő dimenziók megváltoztathatók. A **Költségek** oldal csak azokat a költségtípuskódokat jeleníti meg, amelyekben a **Feladás** lap **Dr** bejegyzése *Cikk* értékre van állítva. |

## <a name="header-view"></a>Fejlécnézet

A **Fejléc** nézet megnyitásához nyisson meg egy levelet, majd válassza a levél fejlécének jobb felső részén található **Fejléc** lapot.

### <a name="settings-on-the-general-fasttab"></a>Az Általános gyorslap beállításai

Az alábbi táblázat leírja azokat a mezőket, amelyek a levél **Fejléc** nézetében, az **Általános** gyorlapon érhetők el.

| Mező | Leírás |
|---|---|
| Ívlap | A levél neve. Ezt a nevet a rendszer automatikusan generálja a levél létrehozásakor.|
| Út | A levélhez kapcsolódó hajóút. |
| Vámügynök | A levél vámügynökének kiválasztása. A vámügynökök definiálva vannak a szállítóhoz. Lehetővé teszik a létrehozott költségek automatikus meghatározását. |
| Házi légi fuvarlevél/fuvarlevél | A házon belüli légi fuvarlevél vagy fuvarlevél megadása, amely a levélre vonatkozik. |
| Cég | A levélhez társított jogi személy (vállalat). |
| Rakomány-ellenőrzési szám | Ezt a mezőt egyes országokban vagy régiókban a vámügyi részlegek használják. |
| Mértékegység | Ez a mező teszi lehetővé a **Partraszállítási költség** modulban megadott mérték beállítását. A mértékeket gyakran használják azok a szervezetek, amelyek nem ismerik az áruk egyedi mennyiségét vagy súlyát, de pontosabb arányosítást igényelnek, mint amit az összeg vagy mennyiség biztosít. A fuvarozó megadja a súlyt vagy a köbméteres mértéket, és azt elhelyezheti egy cikk vagy a beszerzési rendelés szintjén. A paraméter kiválasztása esetén automatikusan frissíthető, illetve manuálisan is meg lehet adni. |
| Mértékegység | A megadott mértékre vonatkozó egység. |
| Kartondobozok száma | A levélben található kartonok száma. A mező automatikusan frissíthető a kiválasztott paramétertől függően. |
| Szállítói számla | A levélhet társított szállító kiválasztása. Ez a mező csak tájékoztatásra szolgál. Semmilyen funkciót nem befolyásol. |
| Név | A kiválasztott szállítói fiók neve. |
| Megjegyzések | A levélre vonatkozó kiegészítő információk megadása. |
| Áruk leírása | A levél azonosításához válasszon egy áruleírást. További információért tekintse meg az [Áruk leírása](shipping-information-setup.md#description-of-goods) részt. |
| Értékelés dátuma | Ez a mező a vámbeviteli oldalhoz kapcsolódik. A **Partraszállítási költség** modul az itt beállított dátumra érvényes vámárfolyamot használja. Az alapértelmezett érték a vámbeviteli oldalon található dátum. |
| Vám azonosítója | Adja meg a vámazonosítót. Az egyes országokban vagy régiókban található vámügyi részlegek biztosítják ezt az azonosítót. |
| Vámtarifakód | A levélhez társítandó tarifakód megadása. Ezt a kódot jellemzően az az ország vagy régió követeli (és határozza) meg, amelybe a szállítást végzi. |

### <a name="settings-on-the-delivery-fasttab"></a>A Szállítás gyorslap beállításai

Az alábbi táblázat leírja azokat a beállításokat, amelyek a levél **Fejléc** nézetében, a **Szállítás** gyorlapon érhetők el.

| Mező | Leírás |
|---|---|
| Ívlap dátuma | Jelöljön ki egy dátumot, amelyet a levélhez kíván társítani. Az alapértelmezett érték a hajóút létrehozásának dátuma. |
| A becsült érkezési időpont a szállítási kikötőnél | A becsült érkezési idő (ETA) a célkikötőnél („cél” kikötő). |
| Becsült szállítási dátum | Általában az a dátum, amikorra az áru megérkezik a raktárba. Ez a mező nincs használatban a becsült szállítási dátum számítása során. (A rendszer a követési vezérlő becsült szállítási dátumát használja helyette.) Ha a mezőt úgy kell beállítani, hogy az érték megegyezzen a követési vezérlő becsült szállítási dátumával, használja a [Követési vezérlőközpontot](delivery-information-setup.md#tracking-control-center). |
| Az eredeti dokumentumok beérkeztek | Az eredeti dokumentumok beérkezési dátuma. |
| Ügynök tanácsa szerint | A közvetítő értesítési dátuma. |
| Eredeti fuvarlevél elküldve | Az eredeti fuvarlevél elküldésének dátuma. |
| Kiadott áruk | Az áruk kiadásának dátuma. |
| Vevői találkozó | A vevői találkozó dátuma. |
| Kiszállítva a raktárba | A dátum, amikor az árut a raktárba szállították. |
| Ellenőrzési dátum | Az ellenőrzési dátum. |
| Szállítási utasítások | A szállítási utasítások beérkezési dátuma. |
| Kiindulási kikötő | Az a kikötő, amelyből a hajóút indul. |
| Célkikötő | Az a kikötő, ahvá a hajóút megérkezik. A szállítókonténernek különböző kikötője lehet, mivel a hajó több kikötőnél is megállhat. |

### <a name="settings-on-the-export-fasttab"></a>Az Exportálás gyorslap beállításai

Az alábbi táblázat leírja azokat a beállításokat, amelyek a levél **Exportálás** nézetében, a **Szállítás** gyorlapon érhetők el.

| Mező | Leírás |
|---|---|
| Exportőr | Az exportőr a levélen tárolható. A nemzetközi kereskedelemben előfordulhat, hogy egy beszerzési rendelést az egyik vállalatnak küld el, de az árut egy másik vállalattól vételezi be. A vámkezeléshez szükséges követés és dokumentáció. Az exportőr neve és címe itt tárolható. |
| Név | A kiválasztott exportőr neve. |

## <a name="lines-view"></a>Sorok nézet

A **Sorok** nézet megnyitásához nyisson meg egy levelet, majd válassza a levél fejlécének jobb felső részén található **Sorok** lapot.

### <a name="information-on-the-folio-fasttab"></a>Információk a Levél gyorslapon

A **Sorok** nézet **Levél** gyorslapja a levéla datait jeleníti meg. A legtöbb ilyen információ a **Fejléc** nézetben is megjelenik a témakörben korábban ismertetett módon.

### <a name="information-and-buttons-on-the-lines-fasttab"></a>A Sorok gyorslap információi és gombjai

A **Sorok** nézet **Sorok** gyorslapja az aktuális levélbe foglalt teljes vagy részleges beszerzésirendelés-sorok részletes adatait jeleníti meg.

A következő táblázat a **Sorok** nézet **Sorok** gyorslapján elérhető gombok leírását tartalmazza.

| Gomb | Leírás |
|---|---|
| Eltávolítás | A kiválasztott beszerzésirendelés-sor eltávolítása az hajóútról. |
| Készlet \> Tranzakciók | A kiválasztott beszerzésirendelés-sor készlettranzakcióinak megtekintése. Ne feledje, hogy ha úton lévő árukat használ, akkor az eredeti rendelés és az úton lévő áruk rendelései is megjelennek. |
| Készlet \> Dimenziók megjelenítése | Egy párbeszédpanel megnyitása, ahol kiválaszthatja a megtekintett tranzakciókhoz megjelenő készletdimenziókat. |
| Frissítés | A kiválasztott beszerzésirendelés-sor sormennyiségével, súlyával vagy térfogatával kapcsolatos adatok frissítése. |

### <a name="information-on-the-lines-details-fasttab"></a>Információk a Sorok részletei gyorslapon

A **Sorok** nézetében található **Sorok részletei** gyorslap további részleteket jelenít meg a **Sorok** gyorslapon jelenleg kiválasztott beszerzésirendelés-sorról.
