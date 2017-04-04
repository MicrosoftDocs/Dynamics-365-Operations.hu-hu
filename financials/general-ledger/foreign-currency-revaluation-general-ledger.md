---
title: "Főkönyvi devizaátértékelés"
description: "Ez a témakör a főkönyvi árfolyam átértékelési folyamat - a folyamat, a folyamat és újraértékelési tranzakciók sztornírozása számítási fut, szükség esetén a telepítő a következő áttekintése."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CurrencyLedgerGainLossAccount
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62153
ms.assetid: 842e8561-560f-4cc6-8668-70cca60b1ba3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 5d6d13fe44eef7766b4dcaf274c3522bce3da816
ms.lasthandoff: 03/31/2017


---

# <a name="foreign-currency-revaluation-for-general-ledger"></a>Főkönyvi devizaátértékelés

Ez a témakör a főkönyvi árfolyam átértékelési folyamat - a folyamat, a folyamat és újraértékelési tranzakciók sztornírozása számítási fut, szükség esetén a telepítő a következő áttekintése. 

Az időszak végén a könyvelési szabályok előírják a külföldi pénznemben levő főkönyvi számlaegyenlegek a különböző árfolyamtípusok használatával történő átértékelését (aktuális, múltbeli, átlag stb.). Például az egyik könyvelési megállapodás előírja az eszközök és források aktuális átváltási árfolyamon, a tárgyi eszközök múltbeli árfolyamon, illetve az eredményszámlák havi átlagon történő átértékelését. A Főkönyvi devizaátértékelés segítségével átértékelheti a mérleg- és az eredményszámlákat. 

> [!NOTE]
> Árfolyam-korrekció érhető el (AR) követelések és kötelezettségek (AP). E modulokat használ, ha a nyitott tranzakciók át kell értékelni az árfolyam-korrekció e modulok használatával. Az AR és az AP devizaátértékelése számlabejegyzést hoz létre a főkönyvben a nem realizált nyereség vagy veszteség megjelenítése érdekében, biztosítva a részkönyvek és a főkönyv egyeztethetőségét. Mivel az AR és az AP devizaátértékelése könyvelési tételeket hoz létre a Főkönyvben, a kinnlevőségek és kötelezettségek főszámlákat ki kell zárni a Főkönyv devizaátértékeléséből. 

Az átértékelési folyamat futtatásakor az egyes fő számlákon levő, külföldi pénznemben közzétett egyenleget átértékeli a rendszer. Az átértékelési folyamat során létrehozott nem realizált nyereség vagy veszteség tranzakciókat a rendszer generálja. Két tranzakció feltétlenül hozhatók létre, az egyik az alapértelmezett pénznemben, a kimutatási pénznemhez egy második Ha szükséges. Az egyes könyvelési tételt könyvel a nem realizált nyereség vagy veszteség, és a fő számla átértékelendő.

## <a name="prepare-to-run-foreign-currency-revaluation"></a>Devizaátértékelés futtatásának előkészítése
Az átértékelési folyamat futtatása előtt a következő beállítás szükséges.

-   A **Fő számla** lapon:
-   Ha a fő számlát a Főkönyvben akarja átértékelni, válassza ki a **Devizaátértékelés** lehetőséget. Ha a fő számlát nem szabad átértékelni (például AR és AP esetén, ha a részkönyvekben történik meg az átértékelés), törölje a jelölést.
-   Ha a fő számla be van jelölve átértékelésre, adja meg az **Árfolyamtípust**. A fő számla átértékelése során ezt a rögzített árfolyamtípust használja a rendszer. A pénzügyi beszámolók készítésére külön mező – **Pénzügyi jelentéskészítés árfolyamtípusa** – érhető el. A két mező nincs szinkronizálva, amely különböző árfolyamtípusok használatát teszi lehetővé az átértékeléshez és a pénzügyi jelentésekhez.

-   A **Főkönyv** lapon:
-   Adja meg az **Árfolyamtípust**. Ha az árfolyamtípus nincs megadva a fő számlán, a devizaátértékelés során a rendszer ezt az árfolyamtípust fogja használni.
-   Határozza meg a realizált nyereség, a realizált veszteség, a nem realizált nyereség és nem realizált veszteség számlákat a devizaátértékeléshez. A realizált nyereség és a realizált veszteség számlákat az AR és AP tranzakciók kiegyenlítéséhez használják, míg a nem realizált nyereség és nem realizált veszteség számlákat a nyitott tranzakciók átértékeléséhez és a főkönyvi fő számlákhoz.

-   A **Devizaátértékelési számlák** lapon:
-   Válassza ki a különböző devizaátértékelési számlákat az egyes pénznemek és vállalatok esetében. Ha nem határoz meg számlát, a rendszer a **Főkönyv** lapon található számlákat használja.

## <a name="process-foreign-currency-revaluation"></a>Devizaátértékelés feldolgozása
A beállítás befejezése után a **Devizaátértékelés** lap segítségével átértékelheti a fő számlák egyenlegeit. A folyamatot futtathatja valós időben, vagy köteg segítségével ütemezheti is. 

A **Devizaátértékelés** lap megjeleníti az egyes átértékelési folyamatok előzményeit, többek között a folyamat futtatásának időpontját, a megadott kritériumokat, az átértékeléshez létrehozott bizonylatot, valamint az esetleges korábbi átértékelés sztornírozási rekordját. Az átértékelési folyamat futtatásához kattintson a **Devizaátértékelés** gombra. 

A **Kezdő dátum** és a **Záró dátum** értékek meghatározzák az átértékelni kívánt devizaegyenleg számítási dátumtartományát. Eredményszámlák átértékelésekor minden, az adott dátumtartományban előforduló tranzakció összegének átértékelése megtörténik. Mérlegszámlák átértékelésekor a rendszer figyelmen kívül hagyja a Kezdő dátumot. Ehelyett az átértékelendő egyenleg meghatározása a pénzügyi év kezdetétől számítva a Záró dátumig történik. 

A **árfolyam dátuma** segítségével határozza meg a dátumot, amelyre az átváltási árfolyamot kell alapértelmezett. Például a dátum tartomány a január 1-január 31 között az egyenlegek átértékeléséhez, de február 1 meghatározott átváltási árfolyamát. 

Válassza ki az átértékelni kívánt fő számlákat: Mind, Mérleg vagy Nyereség és veszteség. Csak a kijelölt átértékelési (a fő számla lapon) fő számlák értékeli. Fő számlák köre tovább korlátozhatja, használja a rekordok **is** fülre, és a fő partnerek vagy egyes fő számlák határozza meg. 

Az átértékelés folyamat futtatható egy vagy több jogi személy számára. A keresés csak a jogi személyek rendelkezünk hozzáféréssel jelenik meg. Válassza ki a jogalanyok, legyen az átértékelési folyamat futtatásához. 

Az átértékelés egy vagy több deviza számára futtatható. A keresés minden olyan pénznem feladott a dátumtartományba fő számla (mérleg vagy eredmény), a kijelölt átértékelni jogalanyok típusának megfelelő fogja tartalmazni. Az alapértelmezett pénznemben szerepelnek a listán, de semmi sem fog átértékelt, ha az alapértelmezett pénznemben van megadva. 

Set **megtekintése könyvelés előtt** a **Igen** Ha szeretne, tekintse át a főkönyvi átértékelés eredménye. A kép általános főkönyvi eltér a szimuláció a P.A. és AP árfolyam-korrekció. A szimuláció P.A. és a hozzáférési pont a jelentést, de főkönyvbe könyvelhető, anélkül, hogy futtassa újra az átértékelési folyamat, amely előzetes van. Az előnézet eredményeit exportálhatja a Microsoft Excel programba, hogy megőrizze az összegek kiszámítási módjának előzményeit. Nem használhat kötegelt feldolgozást, ha meg akarja tekinteni az átértékelés eredményének előnézetét. Az előnézetben a felhasználónak lehetősége van a **Feladás** gombot használó valamennyi jogi személy eredményének feladására. Ha hiba merül fel valamelyik jogi személy eredményeivel kapcsolatban, a felhasználó feladhatja a jogi személyek alkészletét a **Jogi személyek kijelölése feladáshoz** gomb segítségével. 

A külföldi pénznemben átértékelési folyamat befejezése után rekord jön létre minden egyes előzményeinek nyomon követéséhez.  Külön nyilvántartást minden jogi személy és a feladási réteg létrejön.

## <a name="calculate-unrealized-gainloss"></a>Nem realizált nyereség/veszteség kiszámítása
A nem realizált nyereség/veszteség tranzakcióit másképpen hozza létre a rendszer a Főkönyvi devizaátértékelésben, illetve az AR és AP átértékelési folyamat során. Az AR és AP esetén a rendszer teljes mértékben sztornózza az előző átértékelést (feltéve, hogy a tranzakció még nincs kiegyenlítve), és új átértékelési tranzakció jön létre a nem realizált nyereség/veszteség számára az új árfolyam alapján. Ez azért van, mivel a rendszer minden egyes tranzakciót átértékel az AR és az AP lehetőségben. Főkönyvi könyvelés nem vissza az előző átértékelés. Ehelyett között, beleértve a korábbi átértékelési összegek és az új érték az árfolyam dátuma az átváltási árfolyam alapján, a fő számla egyenlegét a különbözeti tranzakció jön létre. 

**Példa** a következő egyenlegek fő számla 110110 létezik.

|            |                    |                        |                       |
|------------|--------------------|------------------------|-----------------------|
| **Dátum**   | **Főkönyvi számla** | **Tranzakció összege** | **Könyvelési összeg** |
| Január 20. | 110110 (készpénz)      | 500 EUR (tartozik)        | 1000 USD (tartozik)      |

A fő számla átértékelésekor január 31.  A nem realizált nyereség/veszteség az alábbiak szerint kell kiszámítani.

|                                             |                                            |                                  |                                    |                             |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| **Aktuális egyenleg a tranzakció pénznemében** | **Aktuális egyenleg a könyvelési pénznemben** | **Átértékelési árfolyam** | **Új könyvelési pénznem összege** | **Nem realizált nyereség/veszteség**    |
| 500 EUR                                     | 1000 USD                                   | 166.6667                         | 833,33 EUR (500 x 1,666667)        | 166,67 veszteség (833,33 – 1000) |

A következő könyvelési bejegyzés jön létre.

|            |                          |           |            |
|------------|--------------------------|-----------|------------|
| **Dátum**   | **Főkönyvi számla**       | **Tartozik** | **Követel** |
| Január 31. | 110110 (készpénz)            |           | 166.67     |
| Január 31. | 801400 (Nem realizált veszteség) | 166.67    |            |

Új tranzakciófeladás sem történik a hónap február.  A fő számla február 28 van átértékelni.

|                                             |                                            |                                  |                                    |                             |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| **Aktuális egyenleg a tranzakció pénznemében** | **Aktuális egyenleg a könyvelési pénznemben** | **Átértékelési árfolyam** | **Új könyvelési pénznem összege** | **Nem realizált nyereség/veszteség**    |
| 500 EUR                                     | 833,33 USD (1000 - 166,67)                 | 250.0000                         | 1250 USD (500 x 2,5)               | 416,67 nyereség (1250 – 833,33) |

A következő könyvelési bejegyzés jön létre.

|             |                          |           |            |
|-------------|--------------------------|-----------|------------|
| **Dátum**    | **Főkönyvi számla**       | **Tartozik** | **Követel** |
| február 28. | 110110 (készpénz)            | 416.67    |            |
| február 28. | 801600 (Nem realizált nyereség) |           | 416.67     |

## <a name="reverse-foreign-currency-revaluation"></a>Devizaátértékelés sztornózása
Ha az átértékelési tranzakciót sztorníroznia kell, válassza ki a **Sztornírozási tranzakció** gombot a **Devizaátértékelés** lapon. Új devizaátértékelési előzményrekord jön létre az átértékelés megtörténte vagy sztornírozási időpontja könyvvizsgálati ellenőrzési előzményeinek megőrzése érdekében. 

Dátumsorrend ki az átértékelés eredményének sztornírozhatók, de szükség lehet annak biztosítása érdekében, minden egyes átértékelt fő számla egyenlege megfelelően több aktuális átértékelés is fordított. A sztornírozási elavult rendelés fordulhat elő, mert semmilyen módon szabályozhatja, mely fő számlák újraértékelik és gyakorisága, amikor újra. Egy szervezet például válassza ki a fő készpénzszámlák negyedéves alapon, de a fő számlák havi átértékelni.


