---
title: Az egyedi alap számsorozatainak beállítása
description: A számsorozatokat az alapadatok és az azokat igénylő tranzakciós bejegyzések olvasható, egyedi azonosítóinak létrehozására használja a rendszer.
author: sericks007
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceDetails
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6734d66a06f8a8dc90a48bd68b7b4e22177b4672
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "362211"
---
# <a name="set-up-number-sequences-on-an-individual-basis"></a>Az egyedi alap számsorozatainak beállítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

A számsorozatokat az alapadatok és az azokat igénylő tranzakciós bejegyzések olvasható, egyedi azonosítóinak létrehozására használja a rendszer. Az azonosítókat igénylő alapadatokat és tranzakciós bejegyzéseket hivatkozásnak nevezik. Egy hivatkozáshoz tartozó új rekordok létrehozása előtt be kell állítania egy számsorozatot, és a hivatkozáshoz társítani. Beállíthatja egyszerre az összes igényelt számsorozatot a Számsorozatok beállítása a varázsló használatával, vagy a Számsorozat lap használatával létrehozhatja illetve módosíthatja az egyes számsorozatokat.

1. Ugorjon a Szervezeti adminisztráció > Számsorozatok > Számsorozatokra pontra.
2. Kattintson a Számsorozat lehetőségre.
3. Adjon meg egy értéket a Számsorozat kódja mezőben.
4. Írjon be egy értéket a Név mezőbe.
5. Bontsa ki a Hatókör paraméterei szakaszt.
    * A Hatókör paraméterei Gyorslapon jelölje ki a számsorozathoz tartozó hatókört és a hatókör értékét.     A hatókör határozza meg, mely szervezetek használják a számsorozatot. Ezenkívül azok a számsorozatok, amelyek nem Megosztott állapotú hatókörrel rendelkeznek olyan szegmensekkel rendelkezhetnek, amelyek megfelelnek a hatókörüknek. Például egy Jogi személyhatókörrel ellátott számsorozat egy jogi személy hatókörrel rendelkezhet. A hatókörökkel kapcsolatos további információk a „Számsorozatok áttekintése” súgótémakörben olvashatók.  
6. Bontsa ki a Szegmensek szakaszt.
    * A Szegmensek gyorslapon határozza meg a számsorozat formátumát a szegmensek hozzáadásával, eltávolításával és átrendezésével.  
    * Az összes hatókör számsorozata tartalmazhatja az állandó szegmenseket és az alfanumerikus szegmenseket. Az állandó szegmensek tartalmazzák azoknak az alfanumerikus karakterek a készletét, amelyek nem módosulnak. Ezen szegmenstípus használatával írjon be egy kötőjelet vagy más elválasztót a Számsorozat szegmensei közé. Az Alfanumerikus szegmensek a kettős kereszt (#) és az és-jel (&) kombinációját tartalmazzák. Ezek a karakterek betűk és számok, melyek a sorozat számainak minden használatánál növekednek. A kettős kereszt (#) használatával jelezheti a növekvő számokat, az (&) jel pedig a növekvő betűket. Például a #####_2014 formátum a 00001_2014, 00002_2014 és így tovább sorozatot hozza létre.     Legalább egy alfanumerikus szegmensnek lennie kell. A hatókörszegmensek, mint például a társaság vagy a jogi személy, nem kötelező jellegűek. Azonban, ha a formátumban nem helyezi el a hatókörszegmenseket, a rendszer a kijelölt hivatkozáshoz tartozó számokat továbbra is hatókörönként fogja létrehozni.  
7. Bontsa ki a Feltöltés szakaszt.
    * A Hivatkozás gyorslapon válassza ki azt a dokumentumtípust vagy rekordot, amelyhez hozzá kell rendelni ezt a számsorozatot.     Ez a lépés nem kötelező a speciális alkalmazási szokásokhoz definiált sorozatok esetében. Ezen esetekben hivatkozás használata nélkül egy új szám jön létre a számsorozat kódja vagy azonosítója értékének használatával. A különleges alkalmazási mód egyik példája egy bizonylatsorozat használata különleges naplónevek létrehozására. Ilyen minták használata azonban nem ajánlott.  
8. Bontsa ki az Általános szakaszt.
    * Az Átalános Gyorslapon adja meg, hogy a számsorozat manuális, illetve folytonos vagy nem folytonos legyen. Ezen túlmenően adja meg a számsorozatban használható legkisebb és legnagyobb számot.     Nem folytonos számsorozat folytonos számsorozatra cserélése nem ajánlott. A számsorozat nem lesz valóban folyamatos. Ez a változtatás ismétlődő kulcsok miatti hibát is okozhat az adatbázisban. Ezenkívül a folyamatos számsorozatok nagyobb hatással vannak a teljesítményre.   
9. Kattintson a Mentés gombra.

