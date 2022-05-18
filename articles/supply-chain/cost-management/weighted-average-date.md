---
title: Dátummal súlyozott átlag a tényleges értékkel és a jelöléssel együtt
description: A dátum szerinti súlyozott átlag elvű készletmodell a súlyozott átlag elven alapul, amelyben a készletből történő kiadásokat a készletzárási időszak egyes napjain a készletbe bevételezett cikkek átlagos értékével súlyozzák.
author: JennySong-SH
ms.date: 03/04/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28991
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1497cb08f4cc5a455c832b9bf125c309cd90aa3d
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672122"
---
# <a name="weighted-average-date-with-include-physical-value-and-marking"></a>Dátummal súlyozott átlag a tényleges értékkel és a jelöléssel együtt

[!include [banner](../includes/banner.md)]

*A dátummal* súlyozott átlag olyan készletmodell, amely az egyes összetevők (cikktranzakciók) és az időszak egyes napjaiban fontosságának (mennyiségének) megfelelő tényezővel (önköltségi ár) megszorzódik. Más szóval ez a készletmodell a kiadási tranzakciók költségét a minden napon beérkezett készlet átlagos értéke, valamint az előző napi aktuális készlet alapján rendeli hozzá.

Ha a dátummal súlyozott átlagon és dátumon súlyozott átlag készletmodellen futtat egy készletzárást, akkor két módszer használható a kiegyenlítés létrehozására. Általában minden bevételezés egy virtuális kiadásval van kiegyenlítve, amely a teljes bevételezési mennyiséget és értéket tartalmazza. Ehhez a virtuális kiadáshoz egy virtuális bevételezés is van, amelyből a kiadást kiegyenlítik. Ily módon minden egyes nap ugyanaz lesz az átlagköltség. A virtuális kiadás és a virtuális bevételezés virtuális transzfernek tekinthető. Ezt a virtuális transzfert *súlyozott átlagú készletzárási transzfernek is nevezik*. Ennek megfelelően ezt a kiegyenlítési módszert *súlyozott átlagú összesített kiegyenlítésnek is nevezik*. Ha csak egy bevételezés van, akkor minden bevételezést ebből egyenlíthet ki, és nem jön létre virtuális transzfer. Ezt a kiegyenlítési módszert nevezik közvetlen *elszámolásnak*. A készletzárás után aktuális készleteket az előző időszak utolsó napja sorának súlyozott átlaga alapján számítja ki a program, és a következő időszak dátummal súlyozott átlaga alapján számítja ki a készletet.

A dátummal súlyozott átlag elv felülbírálható a készlettranzakciók megjelölésével, így egy adott cikkbevételezést egy adott kiadással szemben lehet kiegyenlíteni. Időszaki készletzárásra van szükség, ha a dátummal súlyozott átlag elvű készletmodellel kiegyenlítéseket lehet létrehozni, és a dátum szerinti súlyozott átlag elv szerint módosítani lehet a problémák értékét. Amíg nem futtatja a készletzárást, a kiadási tranzakciókat a tényleges és pénzügyi frissítések mozgóátlagon értékelik. Ha nem használ jelölést, akkor a rendszer a fizikai vagy pénzügyi frissítéskor kiszámítja a mozgóátlagot.

A dátummal súlyozott átlagon és a készlet költségszámítási módszerének számítása az alábbi napi képlet alkalmazásával történik:

*Költség* = \[ (*Qb*<sub>*·*</sub> × *Pb*<sub>*·*</sub>) + &#x2211;<sub>*n*</sub>(*Qn*<sub>*·*</sub> × *Pn*<sub>*·*</sub>)\] ÷ (*Qb*<sub>*·*</sub> + &#x2211;<sub>*nQn)*</sub>*·*<sub>*·*</sub>

- *Q* = A tranzakció mennyisége
- *P* = A tranzakció ára

Más szóval a súlyozott átlagköltség egyenlő a kezdő mennyiség és a kezdő ár szorzóval, valamint az egyes bevételezési mennyiségek összegével és a bevételezési árral, elosztva a kezdő mennyiséggel és a bevételezési mennyiségek összegével.

A készletzárás során a program a záró időszak minden napját kiszámítja.

> [!NOTE]
> További tájékoztatás a kiegyenlítésről: Készletzárás [...](inventory-close.md).

A következő példák azt mutatják be, hogy milyen hatással van a dátummal súlyozott átlag öt konfigurációra:

- Dátummal súlyozott átlagot alkalmazó közvetlen elszámolás a **Tényleges értékkel együtt** beállítás nincs aktiválva
- Dátummal súlyozott átlagot alkalmazó összesített elszámolás a **Tényleges értékkel együtt** beállítás aktiválása nélkül
- Dátummal súlyozott átlagot alkalmazó közvetlen elszámolás a **Tényleges értékkel együtt** beállítással
- Dátummal súlyozott átlagot alkalmazó összesített elszámolás a **Tényleges értékkel együtt** beállítással
- Dátummal súlyozott átlag jelölés használatával

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-isnt-used"></a>Dátummal súlyozott átlagot alkalmazó közvetlen elszámolás a Tényleges értékkel együtt beállítás nincs aktiválva

A közvetlen kiegyenlítési elv a további készlettranzakciók létrehozása nélkül közvetlenül hozza létre a kiegyenlítéseket a bevételezések és a problémák között. A rendszer a következő helyzetekben használja ezt a közvetlen kiegyenlítési elvet:

- Az időszak során egy bevételezést és egy vagy több problémát feladtak.
- Az időszak folyamán csak kiadásokat adtak fel, és a tényleges készletben csak egy előző zárásból származó cikkek találhatók.

Ebben a példában a tényleges értékkel **kapcsolatos** **jelölőnégyzetből törölve van a jelölés a kiadott termék cikkmodellcsoport-lapján**. A következő diagram a következő tranzakciókat mutatja be:

**1. nap:**

- 1a. Fizikai bevételezés készletre, 10 mennyiséggel, 10,00 USD áron.
- 1b. Pénzügyi bevételezés készletre, 10 mennyiséggel, 10,00 USD áron.
- 2a. Fizikai bevételezés készletre, 10 mennyiséggel, 20,00 USD áron.
- 3a. Fizikai kiadás készletről, 1 mennyiséggel, USD 10.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).
- 3b. Pénzügyi kiadás készletről, 1 mennyiséggel, USD 10.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).

**2. nap:**

- 4a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
- 5a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 5b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 6a. Pénzügyi kiadás készletről, 1 mennyiséggel, USD 20.00 egységenként (a pénzügyileg feladott tranzakciók mozgóátlaga).

**3. nap:**

- 7\. Készletzárást hajtanak végre. A dátummal súlyozott átlagon alapuló rendszer a december 30-ai (12/30) közvetlen kiegyenlítési módszert használja, mivel pénzügyileg csak egy bevételezés frissül december 12-30-án. Ebben a példában egy kiegyenlítés jön létre az 1b és 3b tranzakciók között. A program USD 10.00, hogy a 3b tranzakció értékét 20,00-ra vigye. December 31-én (12/31) nem kerül sor helyesbítésre vagy kiegyenlítésre, mert nincs pénzügyileg frissített probléma 12/31-én.

A következő ábra ezt a tranzakciósorozatot mutatja **be**, és a súlyozott átlag készletmodell, valamint a tényleges értékkel való be nem foglalva beállítás nélkül a közvetlen kiegyenlítési elv hatását a folyamatra.

![Dátummal súlyozott átlagot alkalmazó közvetlen elszámolás a Tényleges értékkel együtt beállítás nélkül.](media/weighted-average-date-direct-settlement-without-include-physical-value.png)

**A diagram kulcsa:**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak ábrázolják.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelzik.
- A készletre való bevételezéseket a tengely fölötti függőleges nyilak jelzik.
- A készletről való problémákat a tengely alatti függőleges nyilak jelzik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A dátumokat vékony fekete függőleges sorok választják el egymástól. A dátumok a diagram alján jelölve vannak.
- A készletzárásokat piros színű, szaggatott függőleges sorok ábrázolják.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-isnt-used"></a>Dátummal súlyozott átlagot alkalmazó összesített elszámolás a Tényleges értékkel együtt beállítás aktiválása nélkül

Ha egy időszakban több bevételezés van, akkor a *dátummal súlyozott átlag az összesített kiegyenlítési elvet használja, és egy nap minden bevételezését egy olyan tranzakcióba összegzi, amely súlyozott átlagú készletzárásnak van nevezve*. A nap bevételezései az újonnan létrehozott készlettranzakció kiadásának ellenében lesznek kiegyenlítve. A nap minden bevételezését az új készlettranzakció bevételezésével szemben egyenlíti ki a rendszer. Ha a készletzárás után is marad aktuális készletérték, a súlyozott átlagú készletzárási tranzakciók bevételezési tranzakciója az aktuális készletértéket is tartalmazza.

A következő diagram a következő tranzakciókat mutatja be:

**1. nap:**

- 1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
- 2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 22,00 USD áron.
- 3a. Fizikai kiadás készletről, 1 mennyiséggel, USD 16.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).
- 3b. Pénzügyi kiadás készletről, 1 mennyiséggel, USD 16.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).

**2. nap:**

- 4a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
- 5a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 5b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 6a. Fizikai kiadás készletről, 1 mennyiséggel, USD 23.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).

**3. nap:**

- 7\. Készletzárást hajtanak végre.
- 7a. Súlyozott átlagú készletzárási tranzakció pénzügyi kiadás jön létre az összes pénzügyi készletbevételezés kiegyenlítésének összegzése érdekében.

    - Az 1b. tranzakciót 1 mennyiséggel egyenlítik ki, kiegyenlített összeggel, USD 10.00.
    - A 2b. tranzakciót 1 mennyiséggel egyenlítik ki, kiegyenlített összeggel, USD 22.00.
    - A 7a. tranzakció 2 mennyiségre jön létre, kiegyenlített összeggel, USD 32.00. Ez a tranzakció kiegyenlíti az időszakban pénzügyileg frissített két bevételezési tranzakció összegét.

- 7b. Súlyozott átlagú készletzárási tranzakció pénzügyi bevételezése jön létre a pénzügyileg feladott problémák ellentételeként.

    - A 3b. tranzakciót 1 mennyiséggel egyenlítik ki, kiegyenlített összeggel, USD 16.00. Ez a tranzakció nem helyesbül, mert a pénzügyileg feladott tranzakciók súlyozott átlaga, december 1-ján (12/1).
    - A 7b. tranzakció 2 mennyiséggel jön létre, pénzügyi összeggel és USD 32.00 a 3b. ellentranzakcióhoz USD 16.00 kiegyenlített összeggel. Ez a tranzakció kiegyenlíti az időszakban pénzügyileg frissített egyetlen kiadási tranzakció összegét. A tranzakció nyitott marad, mert még mindig van egy.

A következő ábra ezt a tranzakciósorozatot mutatja be, és a súlyozott átlag készletmodell és az összesített kiegyenlítési elv hatását, **de a Tényleges értékkel való értékkel kapcsolatos beállítás használata** nélkül.

![Dátummal súlyozott átlagot alkalmazó összesített elszámolás a Tényleges értékkel együtt beállítás nélkül.](media/weighted-average-date-summarized-settlement-without-include-physical-value.png)

**A diagram kulcsa:**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak ábrázolják.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelzik.
- A készletre való bevételezéseket a tengely fölötti függőleges nyilak jelzik.
- A készletről való problémákat a tengely alatti függőleges nyilak jelzik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A dátumokat vékony fekete függőleges sorok választják el egymástól. A dátumok a diagram alján jelölve vannak.
- A készletzárásokat piros színű, szaggatott függőleges sorok ábrázolják.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-is-used"></a>Dátummal súlyozott átlagot alkalmazó közvetlen elszámolás a Tényleges értékkel együtt beállítással

A termék jelenlegi verziójában **a** Tényleges értékkel együtt beállítás másképp működik a dátummal súlyozott átlagon és készletmodellen, mint a korábbi verziókban. Ha **a** **Cikkmodellcsoport** lapon egy cikk tényleges értékkel való beszámítása jelölőnégyzetet választja, a rendszer a ténylegesen frissített bevételezéseket fogja használni a becsült kiadási önköltségi ár vagy a mozgóátlag kiszámításakor. A kiadások feladása az időszaknak ezen a becsült önköltségi árán alapul. A készletzárás során a súlyozott átlag számításában csak a pénzügyi bevételezések számítanak.

A következő diagram a következő tranzakciókat mutatja be:

**1. nap:**

- 1a. Fizikai bevételezés készletre, 10 mennyiséggel, 10,00 USD áron.
- 1b. Pénzügyi bevételezés készletre, 10 mennyiséggel, 10,00 USD áron.
- 2a. Fizikai bevételezés készletre, 10 mennyiséggel, 20,00 USD áron.
- 3a. Fizikai kiadás készletről, 1 mennyiséggel, USD 15.00 önköltségi áron (a ténylegesen és pénzügyileg feladott tranzakciók mozgóátlaga).
- 3b. Pénzügyi kiadás készletről, 1 mennyiséggel, USD 15.00 önköltségi áron (a ténylegesen és pénzügyileg feladott tranzakciók mozgóátlaga).

**2. nap:**

- 4a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
- 5a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 5b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 6a. Fizikai kiadás készletről, 1 mennyiséggel, USD 21.25 egység költségeként (a ténylegesen és pénzügyileg feladott tranzakciók mozgóátlaga).

**3. nap:**

- 7\. Készletzárást hajtanak végre. A dátummal súlyozott átlagon alapuló rendszer a december 30-ai (12/30) közvetlen kiegyenlítési módszert használja, mivel pénzügyileg csak egy bevételezés frissül december 12-30-án. Ebben a példában egy kiegyenlítés jön létre az 1b és 3b tranzakciók között. Nem történt módosítás a kiadáson 12/30-án. Emellett december 31-én (12/31) nem kerül sor helyesbítésre vagy kiegyenlítésre, mivel nincs pénzügyileg frissített probléma december 31-én.

A következő ábra ezt a tranzakciósorozatot mutatja **be, és a súlyozott átlag készletmodell, valamint a közvetlen kiegyenlítési elv hatását a Tényleges értékkel együtt beállításra**.

![Súlyozott átlagú közvetlen kiegyenlítés a tényleges értékkel együtt.](media/weighted-average-date-direct-settlement-with-include-physical-value.png)

**A diagram kulcsa:**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak ábrázolják.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelzik.
- A készletre való bevételezéseket a tengely fölötti függőleges nyilak jelzik.
- A készletről való problémákat a tengely alatti függőleges nyilak jelzik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A dátumokat vékony fekete függőleges sorok választják el egymástól. A dátumok a diagram alján jelölve vannak.
- A készletzárásokat piros színű, szaggatott függőleges sorok ábrázolják.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-is-used"></a>Dátummal súlyozott átlagot alkalmazó összesített elszámolás a Tényleges értékkel együtt beállítással

A termék jelenlegi verziójában **a** Tényleges értékkel együtt beállítás másképp működik a súlyozott átlaggal, mint a korábbi verziókban. Ha **a** **Cikkmodellcsoport** lapon egy cikk tényleges értékkel való beszámítása jelölőnégyzetet választja, a rendszer a ténylegesen frissített bevételezéseket fogja használni a becsült önköltségi ár számítása vagy a mozgóátlag kiszámításakor. A kiadások feladása az időszaknak ezen a becsült önköltségi árán alapul. A készletzárás során a súlyozott átlag számításában csak a pénzügyi bevételezések számítanak. A súlyozott átlagon áteső készletmodell használata esetében javasoljuk, hogy havonta zárjon készletzárást. Ebben a példában a dátummal súlyozott átlagon és összesített kiegyenlítésen a készletmodell magában foglalja a tényleges értéket.

A következő diagram a következő tranzakciókat mutatja be:

**1. nap:**

- 1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
- 2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 22,00 USD áron.
- 3a. Fizikai kiadás készletről, 1 mennyiséggel, USD 16.00 önköltségi áron (a ténylegesen és pénzügyileg feladott tranzakciók mozgóátlaga).
- 3b. Pénzügyi kiadás készletről, 1 mennyiséggel, USD 16.00 önköltségi áron (a ténylegesen és pénzügyileg feladott tranzakciók mozgóátlaga).

**2. nap:**

- 4a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
- 5a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 5b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 6a. Fizikai kiadás készletről, 1 mennyiséggel, USD 23.67 önköltségi áron (a ténylegesen és pénzügyileg feladott tranzakciók mozgóátlaga).

**3. nap:**

- 7\. Készletzárást hajtanak végre.
- 7a. Súlyozott átlagú készletzárási tranzakció pénzügyi kiadás jön létre az összes pénzügyi készletbevételezés kiegyenlítésének összegzése érdekében.

    - Az 1b. tranzakciót 1 mennyiséggel egyenlítik ki, kiegyenlített összeggel, USD 10.00.
    - A 2b. tranzakciót 1 mennyiséggel egyenlítik ki, kiegyenlített összeggel, USD 22.00.
    - A 7a. tranzakció 2 mennyiségre jön létre, kiegyenlített összeggel, USD 32.00. Ez a tranzakció kiegyenlíti az időszakban pénzügyileg frissített két bevételezési tranzakció összegét.

- 7b. Súlyozott átlagú készletzárási tranzakció pénzügyi bevételezése jön létre a pénzügyileg feladott problémák ellentételeként.

    - A 3b. tranzakciót 1 mennyiséggel egyenlítik ki, kiegyenlített összeggel, USD 16.00. Ez a tranzakció nem helyesbül, mert a pénzügyileg feladott tranzakciók súlyozott átlaga, december 1-ján (12/1).
    - A 7b. tranzakció 2 mennyiséggel jön létre, pénzügyi összeggel és USD 32.00 a 3b. ellentranzakcióhoz USD 16.00 kiegyenlített összeggel. Ez a tranzakció kiegyenlíti az időszakban pénzügyileg frissített egyetlen kiadási tranzakció összegét. A tranzakció nyitott marad, mert még mindig van egy.

A következő ábra ezt a tranzakciósorozatot mutatja **be**, és a súlyozott átlag készletmodell, valamint a Tényleges értékkel való be nem foglalva beállítás nélküli összesített kiegyenlítési elv hatását a folyamatra.

![Súlyozott átlagú összesített kiegyenlítés a tényleges értékkel együtt.](media/weighted-average-date-summarized-settlement-with-include-physical-value.png)

**A diagram kulcsa:**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak ábrázolják.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelzik.
- A készletre való bevételezéseket a tengely fölötti függőleges nyilak jelzik.
- A készletről való problémákat a tengely alatti függőleges nyilak jelzik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A dátumokat vékony fekete függőleges sorok választják el egymástól. A dátumok a diagram alján jelölve vannak.
- A készletzárásokat piros színű, szaggatott függőleges sorok ábrázolják.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

## <a name="weighted-average-date-when-marking-is-used"></a>Dátummal súlyozott átlag jelölés használatával

A jelölés egy olyan folyamat, amellyel összekapcsolható egy kiadási tranzakció egy bevételezési tranzakcióval. A jelölés történhet a tranzakciók feladása előtt és után is. A jelölés használható a készlet pontos költségének kiértékelésére a tranzakció feladott vagy a készletzárás során.

Tegyük fel például, hogy az ügyfélszolgálati osztály elfogadott egy sürgős megrendelést egy fontos vevőtől. A rendelés sürgős, ezért a vevő kérésének kiszolgálása érdekében többet kell fizetni. Meg kell bizonyosodni arról, hogy ennek a készletcikknek a költsége megjelenik az árrésben vagy az eladott áruk költségében (ELÁBÉ) az adott értékesítési számla esetében.

A beszerzési rendelés feladásakor a készlet bevételezése 120,00 USD értéken történik. Ha még a csomagjegyzék vagy a számla feladása előtt meg van jelölve az értékesítési rendelési dokumentum a beszerzési rendelésen, akkor a program elábéként USD 120.00 elábé költséget, nem pedig a cikk aktuális mozgóátlagát. Ha a jelölés az értékesítési rendelés csomagjegyzékének vagy számlájának feladása után történik, az ELÁBÉ feladása a mozgóátlagon áteső önköltségi áron történik.

A két tranzakció még a készletzárás végrehajtása előtt is összekapcsolható egymással.

Ha egy bevételezési tranzakció egy kiadási tranzakcióhoz van megjelölve, a program figyelmen kívül hagyja a cikk cikkmodellcsoportjaként kiválasztott értékelési módot, és egymással egyenlíti ki ezeket a tranzakciókat.

Kiadási tranzakciót a tranzakció feladása előtt jelölhet hozzá egy nyugtához. Ezt a jelölést az **Értékesítési rendelés részletei lapon található értékesítésirendelés-sorból lehet** megtenni. A nyitott bevételezési tranzakciók a Jelölés lapon **jelennek** meg.

Kiadási tranzakciót a tranzakció feladása után jelölhet hozzá egy nyugtához. Egyeztethet vagy megjelölhet egy kiadási tranzakciót egy nyílt nyugtájú tranzakcióhoz egy leltárazott cikk esetén, feladott készlethelyesbítési naplósorból.

A következő diagram a következő tranzakciókat mutatja be:

**1. nap:**

- 1a. Fizikai bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 1b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 10,00 USD áron.
- 2a. Fizikai bevételezés készletre, 1 mennyiséggel, 20,00 USD áron.
- 2b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 22,00 USD áron.
- 3a. Fizikai kiadás készletről, 1 mennyiséggel, USD 16.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).
- 3b. Pénzügyi kiadás készletről, 1 mennyiséggel, USD 16.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).
- 3c. A 3b. tranzakcióhoz kapcsolódó pénzügyi készlet-kiadás a 2b. tranzakció pénzügyi készlet kiadására van bejelölve.

**2. nap:**

- 4a. Fizikai bevételezés készletre, 1 mennyiséggel, 25,00 USD áron.
- 5a. Fizikai bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 5b. Pénzügyi bevételezés készletre, 1 mennyiséggel, 30,00 USD áron.
- 6a. Fizikai kiadás készletről, 1 mennyiséggel, USD 23.00 önköltségi áron (a pénzügyileg feladott tranzakciók mozgóátlaga).

**3. nap:**

- 7\. Készletzárást hajtanak végre. A súlyozott átlag módszert használó jelölési elv alapján a megjelölt tranzakciókat egymással szemben egyenlítik ki. Ebben a példában a 3b. tranzakciót a 2b. tranzakcióval szemben egyenlítik ki, és USD 6.00 a 3b tranzakcióba feladnak egy korrekciót, hogy az értéket USD 22.00. Ebben a példában nem kerül sor további kiegyenlítésre, mert a lezárás csak a pénzügyileg frissített tranzakciókhoz hoz létre kiegyenlítéseket.

A következő diagram bemutatja a tranzakciósorozatot, valamint a súlyozott átlagon és jelölésen áteső készletmodell hatását.

![Súlyozott átlag jelöléssel.](media/weighted-average-date-with-marking.png)

**A diagram kulcsa:**

- A készlettranzakciókat függőleges nyilak jelölik.
- A fizikai tranzakciókat rövidebb világosszürke nyilak ábrázolják.
- A pénzügyi tranzakciókat hosszabb fekete nyilak jelzik.
- A készletre való bevételezéseket a tengely fölötti függőleges nyilak jelzik.
- A készletről való problémákat a tengely alatti függőleges nyilak jelzik.
- Minden új bevételezési és kiadási tranzakciót egy új címke jelöl.
- Mindegyik függőleges nyíl egy sorszámozott azonosítóval van ellátva, például *1a*. Az azonosítók a készlettranzakciók feladásának időbeli sorrendjét jelölik.
- A dátumokat vékony fekete függőleges sorok választják el egymástól. A dátumok a diagram alján jelölve vannak.
- A készletzárásokat piros színű, szaggatott függőleges sorok ábrázolják.
- A készletzárás által végrehajtott elszámolásokat szaggatott piros nyilak jelölik, amelyek átlósan haladnak egy bevételezéstől egy kiadás felé.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
