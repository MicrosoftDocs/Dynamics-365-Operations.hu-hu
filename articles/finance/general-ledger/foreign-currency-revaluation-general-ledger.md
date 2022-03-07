---
title: Főkönyvi devizaátértékelés
description: 'Ez a témakör áttekintést nyújt a főkönyvi devizaátértékelési folyamat következő pontjairól: telepítés, a folyamat futtatása, a folyamat számításai, valamint szükség esetén az átértékelési tranzakciók sztornírozása.'
author: kweekley
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CurrencyLedgerGainLossAccount
audience: Application User
ms.reviewer: roschlom
ms.custom: 62153
ms.assetid: 842e8561-560f-4cc6-8668-70cca60b1ba3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 49f724eb31904c7fd745864c9d71f401a4d539e29b5ff01814334adf6f0ebc37
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6771656"
---
# <a name="foreign-currency-revaluation-for-general-ledger"></a>Főkönyvi devizaátértékelés

[!include [banner](../includes/banner.md)]

Ez a témakör áttekintést nyújt a főkönyvi devizaátértékelési folyamat következő pontjairól: telepítés, a folyamat futtatása, a folyamat számításai, valamint szükség esetén az átértékelési tranzakciók sztornírozása. 

Az időszak végén a könyvelési szabályok előírják a külföldi pénznemben levő főkönyvi számlaegyenlegek a különböző árfolyamtípusok használatával történő átértékelését (aktuális, múltbeli, átlag stb.). Például az egyik könyvelési megállapodás előírja az eszközök és források aktuális átváltási árfolyamon, a tárgyi eszközök múltbeli árfolyamon, illetve az eredményszámlák havi átlagon történő átértékelését. A Főkönyvi devizaátértékelés segítségével átértékelheti a mérleg- és az eredményszámlákat. 

> [!NOTE]
> A devizaátértékelés a Kinnlevőségek (AR) és a Kötelezettségek (AP) pontban is elérhető. Ha ezeket a modulokat használja, a nyitott tranzakciókat át kell értékelni az adott modulok devizaátértékelésének használatával. Az AR és az AP devizaátértékelése számlabejegyzést hoz létre a főkönyvben a nem realizált nyereség vagy veszteség megjelenítése érdekében, biztosítva a részkönyvek és a főkönyv egyeztethetőségét. Mivel az AR és az AP devizaátértékelése könyvelési tételeket hoz létre a Főkönyvben, a kinnlevőségek és kötelezettségek főszámlákat ki kell zárni a Főkönyv devizaátértékeléséből. 

Az átértékelési folyamat futtatásakor az egyes fő számlákon levő, külföldi pénznemben közzétett egyenleget átértékeli a rendszer. Az átértékelési folyamat során létrehozott nem realizált nyereség vagy veszteség tranzakciókat a rendszer generálja. Két tranzakció hozható létre: egy a könyvelési pénznem és egy a jelentési pénznem számára, ha szükséges. Minden egyes könyvelési tétel a nem realizált nyereségbe vagy veszteségbe adódik fel, a fő számlát pedig átértékeli a rendszer.

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

Az **Árfolyam dátuma** segítségével határozza meg a dátumot, amelyre az árfolyam alapértelmezett. Például átértékelheti a január 1-je és a január 31-e dátumtartományban levő egyenlegeket a február 1-jén érvényes árfolyamot használva. 

Válassza ki az átértékelni kívánt fő számlákat: Mind, Mérleg vagy Nyereség és veszteség. A rendszer csak az átértékelésre (a Fő számla lapon) megjelölt fő számlákat értékeli át. Ha tovább szeretné korlátozni a fő számlák tartományát, használja a **Belefoglalandó** rekordok lapot a fő számlák tartományának vagy egyes fő számlák meghatározásához. 

Az átértékelési folyamat egy vagy több jogi személy számára futtatható. A keresés csak az ön számára hozzáférhető jogi személyeket jeleníti meg. Válassza ki azokat a jogi személyeket, amelyek számára futtatni akarja az átértékelési folyamatot. 

Az átértékelés egy vagy több deviza számára futtatható. A keresés minden olyan pénznemet tartalmaz, amelyet a fő számlatípus (Mérleg vagy Nyereség és veszteség) dátumtartományán belül adtak fel az átértékelésre kijelölt jogi személyek számára. A könyvelési pénznem szerepel a listában, de a rendszer nem végzi el az átértékelése, ha a könyvelési pénznem van kiválasztva. 

Állítsa az **Előnézet feladás előtt** pontot **Igen** lehetőségre, ha szeretné megtekinteni a Főkönyvi átértékelési eredményét. A Főkönyv előnézete eltér a Kinnlevőségek és a Kötelezettségek devizaátértékelési szimulációjától. Az AR és AP szimulációja egy jelentés, de Főkönyvnek van előnézete, amelyet fel lehet adni az átértékelési folyamat újbóli futtatása nélkül. Az előnézet eredményeit exportálhatja a Microsoft Excel programba, hogy megőrizze az összegek kiszámítási módjának előzményeit. Nem használhat kötegelt feldolgozást, ha meg akarja tekinteni az átértékelés eredményének előnézetét. Az előnézetben a felhasználónak lehetősége van a **Feladás** gombot használó valamennyi jogi személy eredményének feladására. Ha hiba merül fel valamelyik jogi személy eredményeivel kapcsolatban, a felhasználó feladhatja a jogi személyek alkészletét a **Jogi személyek kijelölése feladáshoz** gomb segítségével. 

A devizaátértékelési folyamat befejezése után az egyes futtatások előzményeinek nyomon követésére létrejön egy rekord.  Minden jogi személy és a feladási réteg számára külön rekord jön létre.

## <a name="calculate-unrealized-gainloss"></a>Nem realizált nyereség/veszteség kiszámítása
A nem realizált nyereség/veszteség tranzakcióit másképpen hozza létre a rendszer a Főkönyvi devizaátértékelésben, illetve az AR és AP átértékelési folyamat során. Az AR és AP esetén a rendszer teljes mértékben sztornózza az előző átértékelést (feltéve, hogy a tranzakció még nincs kiegyenlítve), és új átértékelési tranzakció jön létre a nem realizált nyereség/veszteség számára az új árfolyam alapján. Ez azért van, mivel a rendszer minden egyes tranzakciót átértékel az AR és az AP lehetőségben. A Főkönyvben a korábbi átértékelés nem kerül sztornírozásra. Ehelyett különbözeti tranzakció jön létre a fő számla egyenlege tekintetében, ideértve az előző átértékelési összegeket, valamint az Árfolyam dátuma árfolyamán alapuló új összeget. 

**Példa** A 110110 fő számlához a következő egyenlegek léteznek.

| Dátum   | Főkönyvi számla| Tranzakció összege | Könyvelési összeg |
|------------|--------------------|------------------------|-----------------------|
| Január 20. | 110110 (készpénz)      | 500 EUR (tartozik)        | 1000 USD (tartozik)      |

A fő számla január 31-én kerül átértékelésre.  A nem realizált nyereség/veszteség kiszámítása a következőképpen történik.

| Aktuális egyenleg a tranzakció pénznemében | Aktuális egyenleg a könyvelési pénznemben | Átértékelési árfolyam | Új könyvelési pénznem összege | Nem realizált nyereség/veszteség    |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| 500 EUR                                     | 1000 USD                                   | 166.6667                         | 833,33 USD (500 x 1,666667)        | 166,67 veszteség (833,33 – 1000) |

A következő könyvelési bejegyzés jön létre.

| Dátum   | Főkönyvi számla       | Tartozik | Követel |
|------------|--------------------------|-----------|------------|
| Január 31. | 110110 (készpénz)            |           | 166.67     |
| Január 31. | 801400 (Nem realizált veszteség) | 166.67    |            |

Február hónapra nem történik új tranzakciófeladás.  A fő számla átértékelése február 28-án történik.

| Aktuális egyenleg a tranzakció pénznemében | Aktuális egyenleg a könyvelési pénznemben | Átértékelési árfolyam | Új könyvelési pénznem összege | Nem realizált nyereség/veszteség    |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| 500 EUR                                     | 833,33 USD (1000 - 166,67)                 | 250.0000                         | 1250 USD (500 x 2,5)               | 416,67 nyereség (1250 – 833,33) |

A következő könyvelési bejegyzés jön létre.

| Dátum    | Főkönyvi számla       | Tartozik | Követel |
|-------------|--------------------------|-----------|------------|
| február 28. | 110110 (készpénz)            | 416.67    |            |
| február 28. | 801600 (Nem realizált nyereség) |           | 416.67     |

## <a name="reverse-foreign-currency-revaluation"></a>Devizaátértékelés sztornózása
Ha az átértékelési tranzakciót sztorníroznia kell, válassza ki a **Sztornírozási tranzakció** gombot a **Devizaátértékelés** lapon. Új devizaátértékelési előzményrekord jön létre az átértékelés megtörténte vagy sztornírozási időpontja könyvvizsgálati ellenőrzési előzményeinek megőrzése érdekében. 

Sztornózhatja az elavult rendelés átértékelési eredményeit, de szükség lehet egy frissebb átértékelés sztornírozására is az egyes átértékelt fő számlák helyes egyenlegeinek biztosításához. Az elavult rendelés sztornírozása azért fordulhat elő, mert nem lehet meghatározni, hogy mely fő számlákat és milyen gyakorisággal értékeljen át a rendszer. Egy szervezet például kiválaszthatja a fő készpénzszámlák negyedéves átértékelését, de a többi fő számla átértékelése havonta történik.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
