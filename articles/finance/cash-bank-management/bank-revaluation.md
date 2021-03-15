---
title: Bank – devizaátértékelés
description: Ez a témakör a banki devizaátértékelés folyamatával kapcsolatban nyújt áttekintést. A telepítéssel, a folyamat futtatásával, a folyamathoz tartozó számításokkal és az újraértékelési tranzakciók sztornírozásával kapcsolatban tartalmaz információkat.
author: mikefalkner
manager: AnnBe
ms.date: 05/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankCurrencyRevalHistory
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-03-08
ms.dyn365.ops.version: 10
ms.openlocfilehash: 5b7d2e33c1edb36227a76453d1981aec5babbf75
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985362"
---
# <a name="bank-foreign-currency-revaluation"></a>Bank – devizaátértékelés

[!include [banner](../includes/banner.md)]


Ez a témakör a banki devizaátértékelés folyamatával kapcsolatban nyújt áttekintést. Bemutatja, hogyan lehet a folyamatot beállítani és futtatni, valamint tájékoztatást nyújt a folyamathoz tartozó számításokról. Azt is bemutatja, hogy hogyan lehet az újraértékelési tranzakciókat sztornírozni, ha sztornírozásra lenne szükség.

Az időszak végén a könyvelési szabályok előírják a külföldi pénznemben levő bankszámlaegyenlegek a különböző árfolyamtípusok használatával történő átértékelését (aktuális, múltbeli, átlag stb.). A banki devizaátértékelés funkció segítségével egy vagy több bankszámla átértékelésére van lehetőség. A funkció globális funkció is. Ezért egyetlen oldalról az Ön által hozzáférhető összes jogi személyhez tartozó bankot átértékelheti.

> [!NOTE]
> Az átértékelési folyamat futtatásakor az egyes bankszámlákon levő, külföldi pénznemben közzétett egyenleget átértékeli a rendszer. Az átértékelési folyamat során létrehozott nem realizált nyereség vagy veszteség tranzakciókat a rendszer generálja. Két tranzakció hozható létre: egy a könyvelési pénznem és egy a jelentési pénznem számára, ha a jelentési pénznemre is szükség van. Minden egyes könyvelési tételt a rendszer a nem realizált nyereségbe vagy veszteségbe adja fel, a fő számlát átértékeli.

## <a name="prepare-to-run-foreign-currency-revaluation"></a>Devizaátértékelés futtatásának előkészítése

Az átértékelési folyamat futtatása előtt a következő beállítás szükséges.

- A **Főkönyv** lapon határozza meg az árfolyamtípust. Ha az árfolyamtípus nincs megadva a fő számlán, a devizaátértékelés során a rendszer ezt az árfolyamtípust fogja használni.
- A **Főkönyv** lapon határozza meg a realizált nyereség, a realizált veszteség, a nem realizált nyereség és nem realizált veszteség számlákat az átértékeléshez. A realizált nyereség és a realizált veszteség számlákat a Kinnlevőségek és Kötelezettségek modul tranzakciói kiegyenlítésre kerülnek. A nem realizált nyereség és a nem realizált veszteség számláival a nyitott tranzakciókat és a főkönyv fő számláit lehet átértékelni.
- A **Devizaátértékelési számlák** lapon különböző devizaátértékelési számlákat állíthat be az egyes pénznemekhez és vállalatokhoz. Ha nem határoz meg számlát, a rendszer a **Főkönyv** lapon található számlákat használja.

## <a name="enable-foreign-currency-revaluation"></a>Devizaátértékelés engedélyezése

A devizaáértékelések feldolgozása csak azután lehetséges, hogy bekapcsolta a banki devizaátértékelés funkciót.

1. Lépjen a **Készpénz- és bankkezelés \> Beállítás \> Készpénz- és bankkezelési paraméterek** elemre.
2. Az **Általános** lap **Devizaátértékelés** részében állítsa a **Banki átértékelés engedélyezése** lehetőséget **Igen** értékre, amellyel bekapcsolja a funkciót az aktuális jogi személyhez. 
3. A **Számsorozatok** lapon adjon meg egy számsorozatot a devizaátértékeléshez.
4. Frissítse a böngészőt, hogy megjelenjen a **Devizaátértékelés** a területlap **Időszakos feladatok** szakaszában.

Minden olyan jogi személyhez be kell kapcsolnia a funkciót, amely használ majd devizaátértékelést. Ha Önhöz a rendszergazda szerepkör vagy a funkciókezelő szerepkör van társítva, akkor ez a lépés kiküszöbölhető a **Paraméter nélküli banki átértékelés engedélyezése** elnevezésű funkció engedélyezésével a **Funkciókezelés** munkaterületen.

> [!NOTE]
> Ha a jogi személy orosz, lengyel vagy magyar ország/régiókódot használ, akkor már végezhet banki devizaátértékelést. A más országok és régiók által használt devizaátértékelést nem használhatja.

## <a name="process-foreign-currency-revaluation"></a>Devizaátértékelés feldolgozása

A telepítés befejezése után használja a Készpénz- és bankkezelés **Devizaátértékelés** oldalát ahhoz, hogy az összes jogi személyre vonatkozóan átértékelje egy vagy több bankszámla egyenlegét. A folyamatot futtathatja valós időben, vagy köteg segítségével is ütemezheti.

A **Devizaátértékelés** oldalon megtekinthetők az egyes átértékelési folyamatok előzményei. Megmutatja, hogy mikor futtatták a folyamatot, milyen feltételt határoztak meg, és szerepel itt egy hivatkozás az átértékeléshez létrehozott bizonylathoz. Azt is megmutatja, hogy egy korábbi átértékelés sztornírozása történt-e. Az átértékelési folyamat futtatásához válassza a **Devizaátértékelés** lehetőséget a Műveleti ablaktáblán, amellyel megnyílik a **Bank - devizaátértékelés** párbeszédablak.

Az **Átértékelési dátum** mező megadja a fordulónapot, amelyre az átértékelendő devizaegyenleg kiszámításához van szükség. Az eddig a dátumig történt összes banki tranzakció összegét átértékeli a rendszer.

Az **Árfolyam dátuma** mező meghatározza a pénznemegyenlegek átértékeléséhez használt árfolyam dátumát. Például lehetséges a január 31-ei egyenlegek átértékelése a február 1-jére meghatározott árfolyammal is.

Az átértékelési folyamat egy vagy több jogi személy számára futtatható. A keresés csak az ön számára hozzáférhető jogi személyeket jeleníti meg. Válassza ki a jogi személyeket, amelyekhez ki szeretné választani a devizaátértékelésre jogosult bankszámlákat. Az adott jogi személyekhez tartozó összes bankszámla megjelenik a rácsban.

Állítsa az **Előnézet feladás előtt** beállítást **Igen** értékre, ha szeretné feladás előtt áttekinteni az átértékelés eredményeit. A devizaátértékelés rendelkezik feladható előnézettel. Nincs szükség az átértékelési folyamat újbóli futtatására. Az előnézet eredményeit exportálhatja a Microsoft Excel programba, hogy megőrizze az összegek kiszámítási módjának előzményeit. Nem használhat kötegelt feldolgozást, ha meg akarja tekinteni az átértékelés eredményének előnézetét.

A devizaátértékelés feldolgozásához válassza az **OK** lehetőséget. Ekkor létrejön egy rekord, amely minden egyes futtatás előzményeit nyomon követi. Minden jogi személy és a feladási réteg számára külön rekord jön létre.

## <a name="calculate-unrealized-gainloss"></a>Nem realizált nyereség/veszteség kiszámítása

A Készpénz- és bankkezelés modulban a banki pénznemet a rendszer az alappénznemként kezeli, és nem értékeli át. A könyvelési pénznemben levő bankszámlaegyenleget átértékeli a banki pénznem és a könyvelési pénznem közti, **Árfolyam dátuma** napján érvényes árfolyammal. A jelentési pénznemben levő bankszámlaegyenleget átértékeli a banki pénznem és a jelentési pénznem közti, **Árfolyam dátuma** napján érvényes árfolyammal.

Létrejön egy tranzakció a bankszámlaegyenleg és a könyvelési pénznemre átszámított új egyenleg közötti különbséghez. Létrejön egy másik tranzakció a bankszámlaegyenleg és a jelentési pénznemre átszámított új egyenleg közötti különbséghez. A tranzakciók bejegyzéseit a rendszer egyeztetettként jelöli meg. 

Nem készül bejegyzés a könyvelési pénznemhez, ha a banki pénznem és a könyvelési pénznem megegyezik. Hasonlóképpen nem készül bejegyzés a jelentési pénznemhez, ha a banki pénznem és a jelentési pénznem megegyezik.

A devizaátértékelési tranzakció ugyanazon dimenziók szerint kerül felosztásra, amelyek a banki tranzakciókban találhatók. A felosztás alapja az egyes dimenziók egyenlege. Például a banki egyenleg összege 10 000, de a 001 számú üzleti egység egyenlege 4000, a 002 számú üzleti egység egyenlege pedig 6000. Ebben az esetben az átértékelés összegének 40%-a a 001 számú üzleti egység átértékelési számlájára kerül feladásra, 60%-a pedig a 002 számú üzleti egység átértékelési számlájára. Ha a számlastruktúrában nem szerepel az egyik üzleti egység, akkor a teljes összeget az átértékelési számlára adják fel.

## <a name="reverse-foreign-currency-revaluation"></a>Devizaátértékelés sztornírozása

Ha az átértékelési tranzakciót sztorníroznia kell, válassza ki a **Sztornírozási tranzakció** gombot a **Devizaátértékelés** lap Műveleti ablaktábláján. Új devizaátértékelési előzményrekord jön létre az átértékelés megtörténte vagy sztornírozási időpontja könyvvizsgálati ellenőrzési előzményeinek megőrzése érdekében.

Több átértékelés sztornírozásához a legutoljára létrehozott átértékelést kell először sztornírozni. Ezután dátum szerint folytassa a korábbi átértékelések sztornírozását. Ezután a sztornírozott időszakokra feldolgozhat új átértékeléseket.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]