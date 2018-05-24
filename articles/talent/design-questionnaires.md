---
title: "Kérdőívek tervezése"
description: "Ez a témakor a kérdőívkészítés folyamatát írja le. Az első lépés a kérdőív megtervezése. Egy kérdőív megtervezésekor, nem csupán a kérdéseket és a válaszokat kell összeállítani, hanem olyan szerkezetet kell felállítani, amely lehetővé teszi, hogy a válaszok rögzíthetőek és rendezhetőek legyenek."
author: kherr75
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KCMCollectionType, KMAnswerCollection, KMCollection
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 17341
ms.assetid: b27e2f12-c7a0-4a54-b8d8-17819f8a1c72
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: cc25f4fde93df03145baedafb9c6b093659594d0
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="design-a-questionnaire"></a>Kérdőívek tervezése

[!include [banner](includes/banner.md)]

Ez a témakor a kérdőívkészítés folyamatát írja le. Az első lépés a kérdőív megtervezése. Egy kérdőív megtervezésekor, nem csupán a kérdéseket és a válaszokat kell összeállítani, hanem olyan szerkezetet kell felállítani, amely lehetővé teszi, hogy a válaszok rögzíthetőek és rendezhetőek legyenek. 

Egy alaposan megtervezett kérdőív segítségével javítható a begyűjtött adatok minősége. Alapos tervezéssel könnyebben kiválaszthatja a megfelelő beállításokat a megfelelő időben kérdőívhez. A következő szempontok segíthetnek hatékony kérdőívet tervezni:

-   Egyértelműen határozza meg a kérdőív célját, hogy a kérdések biztosan a célnak megfelelőek legyenek.
-   Határozza meg azt a személyt vagy csoportot, amellyel ki szeretné töltetni a kérdőívet.
-   Írjon kérdéseket a kérdőívhez, melyek amennyiben szükséges, tartalmazzanak válaszlehetőségeket is.
-   Győződjön meg arról, hogy a kérdőív logikailag jól felépített, hogy a válaszadókat lefoglalja az.
-   Állítsa sorba a kérdéseket és a válaszokat annak megfelelően, ahogy a válaszadóknak szeretné megjeleníteni azokat.
-   Amennyiben szükséges, döntse el, hogyan kell az eredményeket kiértékelni.
-   Döntse el, hogy lesz-e szüksége további jellemzőkre. Például meghatározhatja, hogyan legyenek kategorizálva az eredmények, szükséges-e idő keretet szabni illetve, hogy minden kérdés kötelezően megválaszolandó-e.

A tervezési fázis négy feladat kategóriát tartalmaz, melyeket ebben a sorrendben kell teljesíteni:

1.  Szükség szerint állítsa be az előfeltételeket.
2.  Határozzon meg válaszcsoportokat és válaszokat, amennyiben vannak ilyenek.
3.  Határozza meg a kérdéseket és a válaszcsoportokhoz való társításukat.
4.  Határozza meg magát a kérdőívet, és társítson hozzá kérdéseket.

## <a name="prerequisites"></a>Előfeltételek
Bizonyos előfeltételeket meg kell határoznia mielőtt kérdőíveket, kérdéseket vagy válaszokat készít. Azonban nincs szükség minden előfeltételre a teljes működéshez.

### <a name="required"></a>Szükséges

| Előfeltételek        | Leírás                |
|---------------------|----------------------------|
| Kérdőívtípusok | Kérdőívek kategorizálása. |
| Kérdéstípusok      | Kérdések kategorizálása.      |

### <a name="optional"></a>Választható

| Előfeltételek             | Leírás                                                    |
|--------------------------|----------------------------------------------------------------|
| Kérdőív paraméterei | Szabjon meg alapvető szabályokat és beállításokat a kérdőívekhez. |

### <a name="questionnaire-types"></a>Kérdőívtípusok

A kérdőívtípusok kötelezőek, és kötelező társítani őket egy kérdőív létrehozásakor. A kérdőív típusok segítenek, a kérdőívek könnyebb kezelésében és rendezésében. A kérdőívek rendezése és megkülönböztetése érdekében, használja a kérdőív típusokat. Például, amennyiben több kérdőív közül is választhat, kiszűrheti őket típusok alapján, hogy megkönnyítse a megfelelő kérdőív megtalálását. Az alábbiakban néhány példa látható a különböző kérdőív típusokra:

-   Emberi erőforrások fejlesztése
-   Vevői felmérések
-   Értékelési folyamat

### <a name="question-types"></a>Kérdéstípusok

A kérdéstípusok kötelezőek, és kötelező kijelölni őket egy kérdőív létrehozásakor. 

Használja a kérdés típusokat, hogy kategorizálja a kérdéseket a jelentéshez. A kérdéstípusok megkönnyítik továbbá a kérdések megtalálását, mivel szűrőként is használhatja a típusokat a **kérdések** oldalon. Az alábbiakban néhány példa látható a különböző kérdés típusokra:

-   Emberi erőforrások
-   Üzletkezelés
-   Tanfolyam-értékelés

### <a name="questionnaire-parameters"></a>Kérdőív paraméterei

A kérdőív-paraméterek opcionálisak. A vállalata igényeinek megfelelően használhatóak. 

A kérdőív paraméterek meghatározzák az anonimitást, a sorozatszám kódokat és a kérdőív referencia típusait. Amikor egy szervezet szétosztja a kérdőíveket, a válaszadók anonimitásának megőrzése problémát jelenthet. 

A számsorozat-kódok a kérdések és a válaszok rendszerezésére szolgálnak. E számsorozat-kódok alapján az értékeket a rendszer automatikusan hozzárendeli a cikkekhez. 

Az adatok elkészítése előtt ajánlott minden paramétert meghatározni. A kérdőív beállítások később bármikor módosíthatóak.

## <a name="questionnaire-components"></a>A kérdőív részei
A kérdőívek három fő elemből állnak: válaszcsoportok, melyek a feleletválasztós kérdések válaszait tartalmazzák, kérdések és a kérdőív maga. A kérdéseket a kérdőíven válaszcsoportokba csoportosíthatja. A válaszcsoportok segítségével kérdéseket kategorizálhat és további elemzést végezhet a kérdőíven. 

[![QuestionnaireComponents](./media/questionnairecomponents-1024x615.png)](./media/questionnairecomponents.png)

### <a name="answer-groups-and-answers"></a>Válaszcsoportok és válaszok

A válaszadók a kérdés tárgyától függően kétféleképpen adhatnak választ a kérdésekre.

-   A nyitott kérdések nem igényelnek meghatározott formátumú válaszokat. A válaszadók válaszolhatnak szöveg, idő vagy dátum esetén, szám formájában. Ezeknél a kérdéseknél a válaszadónak általában szubjektív információkat, például véleményt, értékelést vagy becslést kell közölnie.
-   Eldöntendő kérdések esetén a válaszadónak a megadott válaszok listájából kell kiválasztania a megfelelő válaszokat.

Ahhoz, hogy eldöntendő kérdésekhez hozzon létre lehetséges válaszokat, használja a **válaszcsoportok** oldalt. 

A válaszcsoportok és a válaszok adják meg a fő információkat, melyekből a kérdések készülnek. Válaszcsoport létrehozása után, a válaszcsoportokat és a kérdéseket a **Válaszcsoport** mezőn, a **Kérdések** oldalon társíthatja. 

Ugyanaz a válaszcsoport ugyanannak a kérdőívnek több kérdésére, illetve egynél több kérdőívre is alkalmazható. 

**Megjegyzés:** Amennyiben olyan válasz szövegét módosítja, amely már használatban van kitöltött kérdőíveken, az adatok nehezen kiértékelhetővé válhatnak és a kérdőív eredményei már nem biztos, hogy érvényesek lesznek. Amennyiben módosítani kell egy válaszcsoportot, fontolja meg az új válaszcsoport létrehozását, a meglévő megváltoztatása helyett. A kérdésekhez vagy válaszokhoz csatolt, illetve a már megválaszolt válaszcsoportok nem törölhetőek.

### <a name="questions"></a>Kérdések

A kérdőíveknek kötelezően tartalmaznia kell kérdéseket. A kérdések nyílt vagy zárt kérdések lehetnek.

-   A nyitott kérdésekre adott válaszok nem szabályázottak, a válaszadók beírhatják a saját válaszaikat.
-   Eldöntendő kérdések esetén előre felállított válaszlista szükséges és a kérdések úgy is meglehetnek alkotva, hogy a válaszadónak lehetősége legyen több választ is adni. A kérdéseket úgy kell megtervezni, hogy a kívánt információt kapjuk meg a válaszadótól. Emellett a kapott válasz köthető kell, hogy legyen egy zárt kérdéses válaszcsoporthoz is. 
     -  **Megjegyzés:** Eldöntendő kérdések létrehozása előtt, készítenie kell válaszcsoportokat és válaszokat is.

A kérdések szervezhetőek feltételesen egymásra épülve, így a másodlagos kérdések az előző kérdésre adott választól függenek majd. A kérdéseket megírhatja előre is, hogy aztán később rendezze őket sorrendbe.

## <a name="setting-up-questionnaires"></a>Kérdőívtípusok beállítása
**Megjegyzés:** Mielőtt felállítana egy kérdőívet, be kell állítania kérdéseket, válaszokat és előfeltételeket. 

Minden kérdőívnél, a következő információkat adhatja meg:

-   A teljes idő vagy az időkorlát a kötelező kérdések megválaszolására.
-   Kötelező-e az összes kérdés?
-   Kérdőíven elérhető maximális pontszám kiszámítása.
-   Hogyan kategorizálja az eredményeket?
-   Korlátozott számú válaszadónak lesz-e elérhető a kérdőív?
-   Jelenjen-e meg háttérként képernyősablon a kérdőív oldalain?
-   Szükségesek-e további megjegyzések, annak érdekében, hogy a válaszadók számára tiszta legyen kérdőív célja?
-   A kérdéseket megadott sorrendben vagy a halmazból véletlenszerűen kívánja-e megjeleníteni?
-   Lesznek-e olyan kérdések, melyek csak az előzőleg adott válaszok alapján jelennek meg?

### <a name="set-up-a-questionnaire"></a>Kérdőív összeállítása

Az elsődleges oldal, amely a kérdőív beállítását szolgálja, a **Kérdőívek** oldal. Kérdőív összeállításához kövesse sorrendben a következő feladatokat:

1.  Hozzon létre egy kérdőívet.
2.  Hajtsa végre az alábbi lépések egyikét, hogy kérdéseket hozhasson létre a kérdőívhez:
    -   Amennyiben eredménycsoportokat alkalmaz, használhatja azokat a kérdések és a kérdőív összekapcsolására. Először állítson fel eredménycsoportokat a kérdőívhez, majd adjon hozzá kérdéseket az eredménycsoportokhoz.
    -   Amennyiben nem alkalmaz eredménycsoportokat, csatolhatja a kérdéseket közvetlenül a kérdőívhez is.

3.  Amennyiben szükséges, állítson fel egy feltételes kérdés hierarchiát.
4.  Tesztelje le a kérdőívet.

Kattintson a **Kérdőívek** oldalon, az **Ellenőrzés** lehetőségre, hogy letesztelje megfelelően van-e összeállítva a kérdőíve. Jó módszer a kérdőív terjesztés előtti tesztelésére azonban az is, ha a készítő maga tölti ki a kérdőívet.

### <a name="modify-a-questionnaire"></a>Kérdőív módosítása

A következő feladatokat a **Kérdőívek** oldalon végezheti el:

-   A kérdőívben szereplő adatok – többek között az eredménycsoportok és a kérdések – szerkesztése.
-   Kérdések törlése és hozzáadása.
-   Az eredménycsoportok és a sorszám módosítása 

**Figyelem:** Legyen óvatos a már megválaszolt kérdőívek megváltoztatásával. A változtatások csökkenthetik a statisztikák pontosságát, így nem megfelelő alapot nyújtva a kiértékeléshez. Fontolja meg az új kérdés létrehozását, már megválaszolt kérdés módosítása helyett.

A következő típusú kérdések nem törölhetőek a kérdőívből:

-   Kérdőívhez rendelt kérdések
-   Kérdések, amelyeket már megválaszoltak, és ezért megjelennek **Válaszok** párbeszédpanelen.

### <a name="result-groups"></a>Eredménycsoportok

Az eredménycsoportok használata nem kötelező, amennyiben a kérdéseket csatolja a kérdőívhez. 

Az eredménycsoport célja a kérdőív pontjainak a kiszámítása és az eredmények kategorizálása. Amennyiben eredménycsoportokat használ, a következő feladatokat hajthatja végre:

-   Kérdőív eredményeinek kiértékelése a pontstatisztikák alapján.
-   A válaszadó pontjainak kiértékelése, minden megadott eredménycsoport alapján.
-   Statisztikát generálhat minden egyes eredménycsoportról, az eredmények elemzése céljából.
-   Nyomtathat jelentést, amely megmutatja minden válaszcsoport eredményét, valamint opcionális pontokat/szövegeket, amelyek az egyes válaszcsoportokban elért pontokon alapszanak.

**Megjegyzés:** Eredménycsoportok beállítása előtt a következő feladatokat kell elvégeznie:

-   Állítson be eldöntendő kérdéseket. Eldöntendő kérdések esetén a **Kérdések** oldalon a **Jelölőnégyzet**, **Választógomb** vagy a **Kombinált lista** opciót kell kiválasztani.
-   Határozza meg az egyes válaszok pontjait a kérdésekhez rendelt válaszcsoportokban.
-   Állítson össze egy kérdőívet.

Ahhoz, hogy eredménycsoportokat használva kérdéseket csatoljon a kérdőívhez, először állítson be eredménycsoportokat a kérdőívhez, majd adjon kérdéseket az eredménycsoporthoz. Amennyiben nem alkalmaz eredménycsoportokat, csatolhatja a kérdéseket közvetlenül a kérdőívhez is. 

Amennyiben kategóriánként szeretné kiértékelni a válaszadó pontjait, felállíthat több eredménycsoportot is. Kérdőív befejezése után, megtekintheti az egyes eredménycsoportokban elért pontszámokat. 

**Tipp:** Amennyiben a kérdőívet pontok használatával kívánja kiértékelni, azonban nem akar különböző kategóriákat alkalmazni, az összes kérdést hozzá tudja adni egyetlen eredménycsoporthoz is. 

Az eredménycsoportokhoz csatolhat továbbá egy vagy több pontalapú üzenetet, melyeket a válaszadók a kérdőív kitöltése után kapnak meg. A megjelenített szöveg a válaszadó által elért pontszám függvényében változhat. A pontszám alapú üzenetek használatakor, ki kell jelölnie pontszám-tartományokat, valamint egy leírást minden egyes tartományhoz. Mikor a válaszadó elér egy bizonyos pontszámot, az ahhoz a pontszám-tartományhoz tartozó szöveg megjelenik az eredményjelentésben. 

Mivel az eredménycsoportok kapcsolódnak a kérdőív bizonyos kérdéseinél elért pontokhoz, ezért csak specifikus eredménycsoportok alkalmazhatóak egy kérdőívnél.

#### <a name="example-pointstexts-for-result-group-3"></a>Például: Pontok/szövegek a 3-as számú eredménycsoporthoz.

Ön egy olyan vezetőségi tesztet alkalmaz éppen, melynek 15 kérdése van, 3 kategóriában. Három eredménycsoportot készít és öt kérdést ad mindegyikhez. A pontok a három csoportban lesznek összesítve. A három eredménycsoport a következő:

-   Kreatív képességek
-   Vezetői képességek
-   Technikai képességek

A pont alapú üzenetek használatához, minden eredménycsoporthoz felállít egy szövegintervallumot. Minden kérdéshez két pont van társítva. Így a maximum pont minden eredménycsoportban 10. 

Az alábbi táblázatban azok a pontalapú üzenetek láthatóak, melyek a „vezetői képességek” eredménycsoporthoz tartoznak.

| Ponthatárok | Szöveg                                       |
|----------------|--------------------------------------------|
| 1–3         | Átlagos vezetői képességekkel rendelkezik.     |
| 4–7         | Jó vezetői képességekkel rendelkezik.        |
| 8–10        | Kiemelkedő vezetői képességekkel rendelkezik. |

A kérdőív minden eredménycsoportjához állíthat be ponthatárokat és szövegeket. A válaszadók pontjaira reflektáló szövegek minden eredménycsoportnál megjelennek. 

**Megjegyzés**: A ponthatárok és a szövegek változtathatóak. Amennyiben egy kérdőív már ki van töltve, a változtatások eltéréseket okozhatnak a régi és az új eredmény kimutatások között.

### <a name="conditional-question-hierarchies"></a>Feltételes kérdés hierarchiák

A feltételes egymáson alapuló kérdések használata opcionális kérdőív készítésekor. 

**Megjegyzés**: Feltételes egymáson alapuló kérdések beállítása előtt, válaszcsoportokhoz rendelt kérdéseket kell adni a kérdőívhez. 

Amennyiben a kérdőívben egymásra alapuló kérdéseket szeretne létrehozni, a feltételes kérdések használatakor beállíthatja, hogy a sorozatban szereplő kérdések a válaszadó által adott válaszok alapján alakuljanak. Azáltal, hogy a kérdéssorozatot a kitöltő személy válaszaira alapozza, személyre szabott kérdőíveket hozhat létre.

#### <a name="examples"></a>Példák

A jogi személy mind eszközöket, mind pedig szolgáltatásokat kínál vásárlóinak. Ahogy az gyakran előfordul, egyes vásárlók csak eszközöket, míg mások csak szolgáltatásokat vesznek igénybe, megint csak mások pedig eszközöket és szolgáltatásokat is igénybe vesznek. Ebből adódóan tehát, mikor egy jogi személy kioszt egy vásárló-elégedettségi felmérést, feltételes szerkezetet alkalmaz a kérdőívben, így azok a vásárlók akik csak a szolgáltatásokat vásárolják meg, nem kell, hogy válaszoljanak a termékekkel kapcsolatos kérdésekre. 

Másik lehetőségként egy kérdőív összeállítható úgy is, hogy ha a válaszadó az 1-es kérdésre az A választ adja, akkor a sorozat következő kérdése a 2-es kérdés lesz. Ha azonban a válaszadó az 1. kérdésre a B választ adja, az 5. kérdés következik.

<a name="additional-resources"></a>További erőforrások
--------

[Kérdőívek használata](questionnaires.md)

[Kérdőívek kiosztása és kitöltése](distribute-questionnaires.md)

[Kérdőívek megtekintése, az eredmények kiértékelése](evaluate-questionnaire-results.md)


