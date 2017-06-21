---
title: "Anyagjegyzékek és receptúrák"
description: "Ez a cikk a termékek és termékváltozatok meghatározásának alapvető részét képező anyagjegyzékekkel (AJ) és receptúrákkal kapcsolatban tartalmaz tájékoztatást. Az anyagjegyzékek és receptúrák határozzák meg az adott termékre vonatkozóan a szükséges anyagokat vagy összetevőket. A receptúrák emellett egy adott termelési környezetben kapott társ- és melléktermékeket is meghatároznak."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConsistOf, BOMDesigner, BOMTable, EcoResProductProcessManufacturingWorkspace
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19331
ms.assetid: c19b437a-2de2-4728-9477-2bcb0c2b1f5e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 5a23acfa95bb93dbc5990bf3839bbc629f15cc2f
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="bills-of-materials-and-formulas"></a>Anyagjegyzékek és receptúrák

[!include[banner](../includes/banner.md)]


Ez a cikk a termékek és termékváltozatok meghatározásának alapvető részét képező anyagjegyzékekkel (AJ) és receptúrákkal kapcsolatban tartalmaz tájékoztatást. Az anyagjegyzékek és receptúrák határozzák meg az adott termékre vonatkozóan a szükséges anyagokat vagy összetevőket. A receptúrák emellett egy adott termelési környezetben kapott társ- és melléktermékeket is meghatároznak. 

<a name="bills-of-materials"></a>Anyagjegyzékek
------------------

Az anyagjegyzék (AJ) határozza meg azokat az összetevőket, amelyek szükségesek egy termék előállításához. Az összetevők lehetnek nyersanyagok, félkész termékek vagy alapanyagok. Bizonyos esetekben a szolgáltatások hivatkozhatók az anyagjegyzékben. Azonban az anyagjegyzékek általában a szükséges *anyagi erőforrások* leírását tartalmazzák.  

Ha egy útvonallal vagy olyan termelési folyamattal van összevonva, amely leírja a termék előállításához szükséges műveleteket és erőforrásokat akkor az anyagjegyzék adja a termék becsült költség számításának alapját.  

Az anyagjegyzék egy egyedi entitás, amit a következő információk írnak le:

-   Anyagjegyzék-azonosító
-   Anyagjegyzék neve
-   Az anyagjegyzék sorok, amelyek leírják az összetevőket és alapanyagokat.
-   Az anyagjegyzék-verziók, amelyek meghatározzák a terméket és a periódust, amihez az anyagjegyzék használható.

Egy anyagjegyzék egy szintet ír le, amit egy egyedi azonosító azonosít. Előfordulhat, hogy az alkatrészeknek saját anyagjegyzékeik vannak, amikre az anyagjegyzék-verziók hivatkoznak. Megjelenítheti és szerkesztheti az anyagjegyzékek teljes hierarchiáját egy konkrét termékhez az anyagjegyzék tervezőben.

### <a name="formulas-co-products-and-by-products"></a>Receptúrák, társtermékek és melléktermékek

A receptúra az anyagverziók egy altípusa, amit jellemzően a gyártásfolyamat során használnak. Az alkatrészeken és alapanyagokon túl egy receptúra leírja a társtermékeket és melléktermékeket. A tényleges verzióban a társtermékek és melléktermékek a receptúrához történő meghatározása megköveteli a receptúraverziót. A receptúra jellemzően egy a receptúraverzióban meghatározott konkrét végtermékhez van megadva (receptúra vagy tervezési cikk).

### <a name="boms-in-the-product-lifecycle"></a>Anyagjegyzékek a termék életciklusában.

A termék életciklusában sok anyagjegyzék típus készülhet, különböző okokból:

-   **Anyagjegyzék vázlat** – Ez az anyagjegyzék egy vázlatos becslést biztosít a szükséges anyagokról egy korai tervezési szakaszban és segít egy durva becslés készítésében a költséghez és a terméktulajdonságokhoz. Ez az anyagjegyzék általában nem használatos a vállalati erőforrás-tervezésben (ERP).
-   **Műszaki anyagjegyzék** – Ez az anyagjegyzék jellemzően olyan termékek tervezése esetén kerül használatra, amelyek létező termékportfóliókon alapulnak. A műszaki anyagjegyzékek úgy vannak felépítve, hogy leegyszerűsítsék a tervezési folyamatot és hogy összetett termékeket tervezési modulokhoz csoportosítsanak. Egyszerű termékek esetén lehetséges, hogy a műszaki anyagjegyzékek a tényleges termelési folyamatot írják le. Azonban más termékek esetében a műszaki anyagjegyzékek tényleges tervezési anyagjegyzékekké konvertálandók. A műszaki anyagjegyzékek jellemzően látszólagos anyagjegyzékként szerepelnek az anyagjegyzék hierarchiában. Habár a műszaki anyagjegyzékek használhatóak a termelési műveletek tervezéséhez és végrehajtásához ez a hozzáállás hatástalanságokhoz vezethet, különösen az ismétlődő műveletek esetén, ahol sok rendelés készül.
-   **Tervezési Anyagjegyzék** – Ez az anyagjegyzék anyagigény-tervezés kialakítására szolgál. Az alapanyag–és összetevő igény a késztermékigény alapján számolandó. A költségszámítási anyagjegyzékekhez hasonlatosan a tervezési anyagjegyzékek képviselhetnek egy konkrét anyagösszetételt, ami egy időszakban felhasználásra kerül.
-   **Termelési anyagjegyzék** – Ez a konkrét termelés során használt tényleges anyagjegyzék. A termelési anyagjegyzéknek figyelembe kell vennie a tényleges erőforrásokat, amik a termék előállítása során felhasználásra kerülnek. Egy termelési rendelést, kötegrendelés vagy kanban létrehozásakor anyagjegyzékeit megjelenítő kitárolási jelölik a többszintű egyszintű gyűjti össze, és a műveletek sorrendjének elosztva.
-   **Költségszámítási anyagjegyzék** – Ez az anyagjegyzék használatos egy termék becsült költségének számításához. Használhatja például költségszámítási anyagjegyzéket amikor elszámoló árat használ vagy amikor egy adott termék becsült, tervezett ára kerül számításra. A költségszámítási anyagjegyzékek hivatkozhatnak egy adott anyag– és erőforrás összetételre, amelynek felhasználása várható. Ezért a költségszámítási anyagjegyzék felhasználható egy jellegzetes költségbecslés elkészítéséhez egy időszakra és segít az időben való eltérések elkerülésében.

Az anyagjegyzék-típusok, amelyek ténylegesen felhasználásra kerülnek megvalósításánál, függenek a megvalósítástól és az üzleti esetektől- és elvárásoktól. Egyszerű megvalósítások esetén egy tervezési anyagjegyzék, egy termelési anyagjegyzék és egy költségszámítási anyagjegyzék modellezhető egy anyagjegyzékként. Olyan környezetekben, ahol gyakoriak a műszaki változások és több alternatív útvonal létezik valószínűleg egy több anyagjegyzéket magában foglaló készletre lesz szükség.

### <a name="approval-of-boms-and-formulas"></a>Anyagjegyzékek és receptúrák jóváhagyása

Minden anyagjegyzék és receptúra külön jóváhagyott vagy jóvá nem hagyott lehet. Jellemzően az anyagjegyzék vagy receptúra jóváhagyása akkor történik, amikor az első a tárgyhoz tartozó anyagjegyzék verzió jóváhagyásra kerül. Azonban bizonyos üzleti esetekben ezek a jóváhagyások eltérő lépések lehetnek a folyamatban és a folyamatoknak eltérő tulajdonosai lehetnek.  

Vegye figyelembe, hogy jóvá nem hagyott anyagjegyzékek esetén az összes kapcsolódó anyagjegyzék-verzió szintén jóvá nem hagyott.

## <a name="bom-and-formula-versions"></a>Anyagjegyzék–és receptúraverziók
Hogy egy adott anyagjegyzéket vagy receptúrát egy előállítható termékváltozathoz rendeljen létre kell hoznia egy anyagjegyzék verziót vagy receptúraverziót. Az anyagjegyzék–és receptúraverziókat korlátozhatja az időszak, mennyiség, telephely, adott termékdimenziók és egyéb követelmények. A receptúraverziók egyéb fontos tulajdonságokkal rendelkeznek, úgy mind hozam, társ–és melléktermék meghatározások és a költségeloszlás utasítások a receptúrához.

### <a name="approval-of-bom-and-formula-versions"></a>Anyagjegyzék–és receptúraverziók jóváhagyása

Mielőtt egy anyagjegyzék verzió használható a tervezési és termelési folyamatban azt jóvá kell hagyni. Amikor egy anyagjegyzék verziót jóváhagynak a kapcsolódó anyagjegyzék szintén jóváhagyható, a felhasználó kiválasztási–és hitelesítési jogaitól függően. Vegye figyelembe, hogy az anyagjegyzék verziót csak akkor lehet jóvá hagyni, ha a vonatkozó anyagjegyzék is jóvá van hagyva.

### <a name="activation-of-the-default-bom-or-formula-version"></a>Az alapértelmezett anyagjegyzék verzió vagy receptúraverzió aktiválása.

Ahhoz, hogy egy adott anyagjegyzéket vagy receptúrát alapértelmezett anyagjegyzék verziónak vagy receptúraverziónak állítson be, amely az alaptervezésben és a termelési utasítások készítésében lesz használatos aktiválnia kell a verziót. Egy verzió aktiválásakor a verzió egyedisége az adott megszorítások alapján (például: időszak, telephely vagy mennyiség) ellenőrzésre kerül. Hibaüzenetet kap, ha a verzió, amit aktiválni próbál, ütközik egy verzióval, ami már aktív. Ezután vagy hatástalanítania kell az ütköző verziót vagy módosítania kell a verzió megszorításait (jellemzően az időszakot) hogy megakadályozza a kétértelmű aktivációt.

### <a name="product-change-with-case-management"></a>Termékmódosítás esetkezeléssel.

A termékmódosítási eset új vagy módosított anyagjegyzékek vagy anyagjegyzék verziók jóváhagyása és aktiválása esetén egyszerű módot biztosít, hogy áttekintsük az anyagjegyzék verziók megszorításait. Továbbá minden anyagjegyzék és receptúra amely egy aktivációs dátumhoz kötött adott módosításhoz tartozik jóváhagyható és aktiválható.

### <a name="alternative-bom-versions"></a>Alternatív anyagjegyzék verziók

Bizonyos esetekben az aktív anyagjegyzék verziót vagy receptúraverziót nem tanácsos előrejelzésekben, értékesítésekben vagy egy szülőtermék esetén használni. Ebben az esetben kiválaszthat egy adott jóváhagyott anyagjegyzéket a követelmény (előrejelzési sor, értékesítési sor vagy anyagjegyzék sor) részeként, ha létezik egy jóváhagyott anyagjegyzék verzió vagy receptúraverzió az alternatív anyagjegyzékhez vagy receptúrához.  

Amikor tervezett rendelések, termelési rendelések vagy kanban-ok készülnek a tervező vagy üzemirányítási felügyelő bármely jóváhagyott anyagjegyzék verziót használhat, amely érvényes a kért tervezett termelési dátumon, hogy megtervezzen vagy előállítson egy adott terméket. A használt anyagjegyzék verziónak nem szükséges alapértelmezett anyagjegyzék verzióként beállítva lennie.

## <a name="bom-and-formula-lines"></a>Anyagjegyzék–és receptúrasorok
Minden anyaghoz, szolgáltatáshoz vagy alapanyaghoz anyagjegyzék sor készül. A sor meghatározza egy adott termékváltozat tervezett fogyasztását, továbbá a tervezett fogyasztáshoz tarozó különféle tulajdonságokat.  

Az anyagjegyzék sorok a következő sortípusokkal rendelkezhetnek: **Cikk**, **Látszólagos**, **Rögzített készletek**, **Szállítói**.

### <a name="item"></a>Cikk

Válassza ki a **Cikk** sortípust az anyagokhoz vagy szolgáltatásokhoz, amelyek közvetlenül elfogyasztásra kerülnek és nem igényelnek további alábontást vagy rögzített készleteket.

### <a name="phantom"></a>Látszólagos

Válassza ki a **Látszólagos** sortípust, amikor az anyagjegyzék sorban szereplő alacsonyabb szintű anyagjegyzék cikkeket alá akarja bontani. Alapütemezés, tervezett költség számítása vagy egy olyan termelési rendelés becslése esetén, amely **Látszólagos** anyagjegyzék sorokat használ, a szülő anyagjegyzék sor ami egy olyan termékváltozatra hivatkozik amelynek látszólagos anyagjegyzéke van kicserélésre kerül olyan összetevő cikkek által, amik anyagjegyzék sorként vannak listázva abban az anyagjegyzékben úgy, ahogy a termékváltozat alkalmazható aktív anyagjegyzék verziója meghatározza. Ha a termékváltozat rendelkezik alkalmazható aktív útvonallal, akkor annak az útvonalnak a műveletei egyesülnek a szülő útvonallal.  

Vegye figyelembe, hogy a látszólagos típusok jellemzően azért kerülnek használatra, hogy leegyszerűsödjön a műszaki folyamat. A látszólagos anyagjegyzékek kiterjedt használata számos szinten hatással van a teljesítményre, különösen a sokszor ismétlődő gyártási esetekben. A teljesítmény javítása érdekében tanácsos elkerülni a látszólagos típusok mély hierarchiáit. Helyette használjon előre alábontott termelési anyagjegyzékeket és útvonalakat.

### <a name="pegged-supply"></a>Rögzített készletek

Válassza ki a**Rögzített készletek** sortípust amikor résztermelést, ami egy anyagjegyzék sor esemény kanban, vagy közvetlen beszerzési rendelést kíván létrehozni bármely olyan termékváltozathoz, amire az anyagjegyzék sor hivatkozik. A résztermelés, az esemény kanban vagy a beszerzési rendelés akkor készül el, amikor Ön elvégzi a termelési megrendelés becslését. A szükséges cikkmennyiségeket a program automatikusan lefoglalja a fogyasztó termelési rendeléshez.

### <a name="vendor"></a>Szállító

Válassz ki a **Szállító** típust, ha a termelési folyamat alvállalkozót használ, és az alvállalkozóhoz automatikusan résztermelést vagy beszerzési rendelést szeretne létrehozni.  

**Az anyagjegyzékben szereplő alvállalkozói műveletekkel kapcsolatos megjegyzés:** a szolgáltatást vagy az alvállalkozó által végzett munkát a készletben nyomon követett szolgáltatási cikként kell létrehozni. A szolgáltatási cikket hozzá kell rendelni a szülő cikkhez az anyagjegyzék sorban. Az útvonalnak tartalmaznia kell egy az alvállalkozó műveleti erőforrásához hozzárendelt műveletet.




