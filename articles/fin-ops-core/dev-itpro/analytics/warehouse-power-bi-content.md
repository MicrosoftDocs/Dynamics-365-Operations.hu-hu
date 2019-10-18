---
title: Raktári teljesítmény Power BI tartalom
description: Ez a témakör azt ismerteti, mit tartalmaz a Raktári teljesítmény Power BI tartalom modul. Leírja, hogy hogyan kell hozzáférni a Power BI-jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához korábban használt entitásokkal és adatmodellekkel kapcsolatban.
author: Mirzaab
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: WHSWarehousePerformancePowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 272953
ms.assetid: 4e4d4323-78cf-4ffa-8d5a-05e856c33db6
ms.search.region: Global
ms.author: mirzaab
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: c5d07cb9fbb32a2d9b8be11179dbba00ee73d28b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184577"
---
# <a name="warehouse-performance-power-bi-content"></a>Raktári teljesítmény Power BI tartalom

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, mit tartalmaz a **Raktári teljesítmény** Microsoft Power BI tartalom modul. Leírja, hogy hogyan kell hozzáférni a Power BI-jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához korábban használt entitásokkal és adatmodellekkel kapcsolatban.

## <a name="overview"></a>Áttekintés

A **Raktári teljesítmény** Power BI tartalmat úgy hozták létre, hogy a raktár és a műveletek vezetői képesek figyelemmel kísérni a fontos bejövő, kimenő és készletmutatókat. A program a Raktárkezelésre, termékekre vonatkozó és más tranzakciós adatokat használja, és egyaránt megjeleníti a raktárteljesítményt, illetve szállítókra, termékcsoportokra, termékekre, helyszínekre és raktárakra lebontva is bemutatja azt.

A raktárkezelők a **Raktárteljesítmény** Power BI tartalom segítségével a következő három területet mérhetik:

- **Beérkező teljesítmény** – Mérje meg, mennyire jól teljesít egy szállító egy ügyfél igényeihez képest (más szóval, mérje a szállítási teljesítményt), és mérje fel az elhúzódó teljesítményt, hogy azonosítsa azokat a problémákat, amelyek a munkavállalókat vagy a cikkeket egy adott időszakban érintik. Fontos tudni, hogy a szállítók időben, korán vagy későn szállítanak-e, így meghatározhatja, hogy a szállító teljesítménye milyen hatást gyakorol az átfogó teljesítményre. Egy olyan szállító, aki a megadott időpontokon kívül szállít, különös terhelést gyakorolhat a raktárra a váratlan munka miatt, és növelheti az átlagos betárolási időt.
- **Szállítási teljesítmény** – Megmérheti, hogy a raktár teljes mértékben és időben szállít-e az ügyfeleknek (más szavakkal lemérheti a kimenő szállítási és kézbesítési teljesítményeket), hogy azonosítsa azokat a problémákat, amelyek termékekkel, helyekkel vagy raktárakkal, illetve adott ügyfelekkel kapcsolatosak. Ha úgy találja, hogy késedelmesen szállít adott területekre vagy városokba, akkor lehet, hogy több figyelmet kell fordítania a szállításra vagy az ügyfél kezelésére.
- **Hely készletének pontossága** – A készlet pontossága fontos a belső raktár-üzletiintelligencia (BI) szempontjából. Nagyon fontos, hogy meghatározza, hogy általában mennyire pontosan számol. Azonban fontos, hogy meghatározza, mennyire pontos a cikkek megfelelő helyeken való tárolására, és hogy kiemelje az eltérési adatokat annak érdekében, hogy jobb pozíciókat találjon a cikkek számára, vagy megkezdhesse az adott cikk számlálását. (Jelenleg az új cikkalapú számlálási funkció gyorsjavításként jelenik meg.) Ha ezt a Power BI tartalmat használja a helyszínen megtalálható készletadatok helyességének megállapításához, a lopás is azonosítható a boltokban. Azt is meghatározhatja, hogy van-e olyan hely, ahol a kéznél lévő mennyiségek eltérnek a vállalati erőforrás-tervezési rendszer (ERP) adataitól. Lehet, hogy ezek a helyek túl nagyok, vagy nem lehet megszámolni őket. Emellett a fizikai helymeghatározás esetenként téves lehet, ezért nehéz egyetlen típusú cikket szinkronban tartani a kéznél lévő adatokkal.

## <a name="accessing-the-power-bi-content-pack"></a>A Power BI tartalmi csomag elérése
A **Raktári teljesítmény** Power BI tartalom a **Raktári teljesítmény** oldalon látható (**Raktárkezelés** \> **Lekérdezések és jelentések** \> **Raktári teljesítményelemzés** \> **Raktári teljesítmény**).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Mérőszámok, amelyek a Power BI tartalomban szerepelnek
A **Raktárteljesítmény** Power BI tartalom jelentést tartalmaz. Ez a jelentés több olyan metrikát tartalmaz, amelyek diagramok, mozaikok, táblázatok formájában jeleníthetők meg. Az alábbi táblázatban a **Raktári teljesítmény** Power BI-tartalom megjelenítési formáinak áttekintése található.

| Jelentéslap                 | Diagramok                                   | Leírás |
|-----------------------------|------------------------------------------|-------------|
| Beérkező teljesítmény         | Összes betárolás                          | Az adott időszakra vonatkozó feldolgozott betárolási munkasorok száma. |
| Beérkező teljesítmény         | Betárolás átlagos időtartama                    | Az az átlagos idő órában, amely alatt a beszerzési rendelés összes betárolási sora feldolgozásra kerül, az utolsóként betárolt cikk regisztrálásáig. |
| Beérkező teljesítmény         | Korai bevételezés                           | A beszerzésirendelés-sorok korai bevételezéseinek száma. |
| Beérkező teljesítmény         | Időben történt bevételezés                         | Azon beszerzésirendelés-sorok száma, amelyek bevételezése időben történt. |
| Beérkező teljesítmény         | Késedelmes bevételezés                            | A beszerzésirendelés-sorok kései bevételezéseinek száma. |
| Beérkező teljesítmény         | Szállító által időben                        | Azon beszerzésirendelés-sorok százalékos aránya, amelyet a szállító vagy a szállítócsoport korán, időben és későn küld. |
| Beérkező teljesítmény         | Átlagos betárolási idő (órákban) | Az átlagos betárolás idő órákban kifejezve az idők során. |
| Beérkező teljesítmény         | Dolgozó betárolási átlaga               | Az az átlagos idő órákban, ameddig egy dolgozónak eltart a beszerzésirendelés-sorok betárolása. |
| Beérkező teljesítmény         | Átlagos betárolási idő szállító szerint          | Az átlagos betárolási idő órákban szállítónként vagy szállítócsoportonként. |
| Beérkező teljesítmény         | Átlagos betárolási idő termék szerint         | Az átlagos betárolási idő órákban cikkenként vagy cikkcsoportonként. |
| Hely készletének pontossága | Teljes szám                              | Az adott időszakra vonatkozó feldolgozott számlálási munkasorok száma. |
| Hely készletének pontossága | Eltérési arány                         | A teljes eltérési arány az adott időszakban összesen megszámolt sorok százalékában. |
| Hely készletének pontossága | Szám eltérés nélkül                | Az összes feldolgozott számlálási sor közül azoknak a soroknak a száma, amelyeknek feldolgozása eltérés nélkül történt. |
| Hely készletének pontossága | Az idők során megszámolt cikkek                  | Azoknak a cikkeknek a százaléka, amelyeknek számlálása eltéréssel vagy eltérés nélkül történt az idők során. |
| Hely készletének pontossága | Cikk mennyiségi eltérés nagyobb mint % | Táblázatos nézet azokról a számlálási sorokról, amelyeknél az eltérések meghaladnak egy meghatározott százalékos értéket. A táblázat információkat tartalmaz a helyekről, cikkekről, átlagos eltérésekről, összesen számlált munkasorokról, a hely eltéréssel rendelkező sorairól, a számlált átlagos mennyiségről, a várhatóan számlált összesített mennyiségről, valamint a ténylegesen számlált cikkmennyiségről. |
| Hely készletének pontossága | Cikkek száma dolgozónként                     | A dolgozók számlálási teljesítménye. A teljesítmény kifejezése azon számlálási sorok százalékos arányában történik, amelyeknél nincsenek eltérések. |
| Hely készletének pontossága | Cikkek száma hely/raktár szerint           | Számbeli teljesítmény a feldolgozott számlálási munkasorok szerint olyan helyenként vagy raktáranként, amelyek tartalmaznak vagy nem tartalmaznak eltéréseket. |
| Hely készletének pontossága | Eltérési arány termék szerint              | A számlálási teljesítmény eltérési aránya. Az arány a feldolgozott számlálási munkasorok százalékában fejeződik ki cikkenként vagy cikkcsoportonként. |
| Szállítási teljesítmény        | Szállított sorok                            | Azoknak a szállítmánysoroknak az összesített száma, amelyeket az adott időszakban szállítottak. |
| Szállítási teljesítmény        | Korán                                    | A korán leszállított szállítmánysorok százaléka. |
| Szállítási teljesítmény        | Időben                                  | Az időben leszállított szállítmánysorok százaléka. |
| Szállítási teljesítmény        | Késve                                     | A későn leszállított szállítmánysorok százaléka. |
| Szállítási teljesítmény        | Szállítmányok az idők során                      | Azoknak a szállítmánysoroknak a százalékos aránya, amelyeket az adott időszakban időben, korán vagy későn szállítottak. Trendvonal mutatja az időben szállított sorok arányát. |
| Szállítási teljesítmény        | Város szerint késve szállítva                     | A kései szállítások által érintett városok és területek megjelenítése térképen. |
| Szállítási teljesítmény        | Szállítva termék szerint                       | Korai, időbeni vagy késedelmes cikk vagy cikkcsoport raktár szerint szállított százalékos értéke. |
| Szállítási teljesítmény        | Vevő által szállítva                      | Korai, időbeni vagy késedelmes vevő vagy vevőcsoport raktár szerint szállított százalékos értéke. |
| Szállítási teljesítmény        | Szállító hely / raktár              | Korai, időbeni vagy késedelmes hely vagy raktár szerint szállított százalékos értéke. |

## <a name="understanding-the-data-model-and-calculations"></a>Adatmodell, illetve számítások ismertetése
A **Raktári teljesítmény** Power BI tartalom jelentési oldalainak feltöltésére a következő adatok szolgálnak. Ezeket az adatokat az Entitástárban lebonyolított összesített mérések jelenítik meg. Az entitástár az analitikai célokra optimalizált Microsoft SQL Server adatbázisa. További tudnivalókért lásd: [Az entitástár és a Power BI integrációjának áttekintése](power-bi-integration-entity-store.md).

A következő fő összesítő mértékek szolgálnak a tartalom alapjaként.

| Jelentéslap                 | Diagramok                                   | Táblák                                | Számítások leírásai |
|-----------------------------|------------------------------------------|---------------------------------------|--------------------------|
| Beérkező teljesítmény         | Összes betárolás                          | WHSWorkLine                           | Olyan munkasorok száma, ahol a munkatípus **betárolás**. |
| Beérkező teljesítmény         | Betárolás átlagos időtartama                    | WHSWorkLine                           | A munkasorok max. idejének összege osztva a munkasorok max. idejének számával, ahol a munkasorok max. ideje a maximális eltérés a munka létrehozásának és lezárásának dátuma között. |
| Beérkező teljesítmény         | Korai bevételezés                           | WHSWorkLine                           | Azoknak a munkasoroknak a száma, ahol a munka létrehozási dátuma korábbi, mint a használt kézbesítési dátum. Ha a visszaigazolt kézbesítési dátum nincs beállítva, használja az alapértelmezett kézbesítési dátumot. |
| Beérkező teljesítmény         | Időben történt bevételezés                         | WHSWorkLine                           | Azoknak a munkasoroknak a száma, ahol a munka létrehozási dátuma azonos a használt kézbesítési dátummal. Ha a visszaigazolt kézbesítési dátum nincs beállítva, használja az alapértelmezett kézbesítési dátumot. |
| Beérkező teljesítmény         | Késedelmes bevételezés                            | WHSWorkLine                           | Azoknak a munkasoroknak a száma, ahol a munka létrehozási dátuma későbbi, mint a használt kézbesítési dátum. Ha a visszaigazolt kézbesítési dátum nincs beállítva, használja az alapértelmezett kézbesítési dátumot. |
| Beérkező teljesítmény         | Szállító által időben                        | WHSWorkLine                           | Korán érkezett, időben érkezett és késedelmesen érkezett (lásd a táblázat korábbi részében található leírást). |
| Beérkező teljesítmény         | Átlagos betárolási idő (órákban)   | WHSWorkLine                           | Átlagos betárolási idő (lásd a táblázat korábbi részében található leírást). |
| Beérkező teljesítmény         | Dolgozó betárolási átlaga               | WHSWorkLine                           | Átlagos betárolási idő (lásd a táblázat korábbi részében található leírást). |
| Beérkező teljesítmény         | Átlagos betárolási idő szállító szerint          | WHSWorkLine                           | Átlagos betárolási idő (lásd a táblázat korábbi részében található leírást). |
| Beérkező teljesítmény         | Átlagos betárolási idő termék szerint         | WHSWorkLine                           | Átlagos betárolási idő (lásd a táblázat korábbi részében található leírást). |
| Hely készletének pontossága | Teljes szám                              | WHSWorkLineCycleCount                 | Azon ciklusok száma, ahol az abszolút eltérés mértéke egyenlő vagy nagyobb, mint 0 (nulla). |
| Hely készletének pontossága | Eltérési arány                         | WHSWorkLineCycleCount                 | Olyan ciklusok száma, amelyeknél eltérések tapasztalhatók, elosztva a teljes számmal. A ciklusszámban akkor van eltérés, ha az abszolút eltérésmennyiség több mint 0 (nulla). |
| Hely készletének pontossága | Szám eltérés nélkül                | WHSWorkLineCycleCount                 | Azon ciklusok száma, ahol az abszolút eltérés mértéke nagyobb, mint 0 (nulla). |
| Hely készletének pontossága | Szám eltéréssel                   | WHSWorkLineCycleCount                 | Azon ciklusok száma, ahol az abszolút eltérés mértéke egyenlő a 0 (nulla) értékkel. |
| Hely készletének pontossága | Az idők során megszámolt cikkek                  | WHSWorkLineCycleCount                 | Szám eltérés nélkül és Szám eltéréssel (A táblázat korábbi részében található leírás.) |
| Hely készletének pontossága | Cikk mennyiségi eltérés nagyobb mint % | WHSWorkLineCycleCount                 | Az átlagos eltérés az abszolút eltérésmennyiség elosztva a várt mennyiséggel, ahol az abszolút eltérési mennyiség több mint 0 (nulla). Az átlagos eltérés mennyisége az abszolút eltérésmennyiség átlaga, ahol az abszolút eltérési mennyiség több mint 0 (nulla). Számlálás eltérésssel, teljes számmal, várt mennyiséggel, valamint számolt mennyiségek, ahol a teljes mennyiség csoportosítás cikkek és helyek szerint történik (lásd a táblázat korábbi részének leírásait). |
| Hely készletének pontossága | Cikkek száma dolgozónként                     | WHSWorkLineCycleCount                 | Szám eltérés nélkül és Szám eltéréssel (lásd a táblázat korábbi részében található leírást). |
| Hely készletének pontossága | Cikkek száma hely/raktár szerint           | WHSWorkLineCycleCount                 | Szám eltérés nélkül és Szám eltéréssel (lásd a táblázat korábbi részében található leírást). |
| Hely készletének pontossága | Eltérési arány termék szerint              | WHSWorkLineCycleCount                 | Eltérési arány (lásd a táblázat korábbi leírását). |
| Szállítási teljesítmény        | Szállított sorok                            | SalesLine               | Az értékesítési sorok száma, ahová megtörténik az értékesítési sorok szállítása. |
| Szállítási teljesítmény        | Korán                                    | CustPackingSlipOnTimeStatus           | Értékesítési sorok, ahol a szállítási dátum állapota **1 (korai)**. A korai azt jelenti, hogy a csomagoláson szereplő szállítási dátum korábbi, mint az értékesítési sor megerősített szállítási dátuma. Ha a visszaigazolt szállítási dátum nincs beállítva, használja az igényelt szállítási dátumot. |
| Szállítási teljesítmény        | Időben                                  | CustPackingSlipOnTimeStatus           | Értékesítési sorok, ahol a szállítási dátum állapota **2 (időben)**. Az időben azt jelenti, hogy a csomagoláson szereplő szállítási dátum azonos, mint az értékesítési sor megerősített szállítási dátuma. Ha a visszaigazolt szállítási dátum nincs beállítva, használja az igényelt szállítási dátumot. |
| Szállítási teljesítmény        | Késve                                     | CustPackingSlipOnTimeStatus           | Értékesítési sorok, ahol a szállítási dátum állapota **3 (késés)**. A késés azt jelenti, hogy a csomagoláson szereplő szállítási dátum későbbi, mint az értékesítési sor megerősített szállítási dátuma. Ha a visszaigazolt szállítási dátum nincs beállítva, használja az igényelt szállítási dátumot. |
| Szállítási teljesítmény        | Szállítmányok az idők során                      | SalesLine CustPackingSlipOnTimeStatus | Teljes mértékben leszállított megrendelések, ahol az értékesítési sor teljes mennyisége leszállított, plusz korán, időben és későn (lásd a táblázatban korábban leírtakat). |
| Szállítási teljesítmény        | Város szerint késve szállítva                     | CustPackingSlipOnTimeStatus           | Késés (lásd a táblázat korábbi leírását). |
| Szállítási teljesítmény        | Szállítva termék szerint                       | CustPackingSlipOnTimeStatus           | Korai, időbeni és késedelmes (lásd a táblázat korábbi részében található leírást). |
| Szállítási teljesítmény        | Vevő által szállítva                      | CustPackingSlipOnTimeStatus           | Korai, időbeni és késedelmes (lásd a táblázat korábbi részében található leírást). |
| Szállítási teljesítmény        | Szállító hely / raktár              | CustPackingSlipOnTimeStatus           | Korai, időbeni és késedelmes (lásd a táblázat korábbi részében található leírást). |
