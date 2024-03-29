---
title: Számsorozatok beállítása egyedi alapon
description: Ez a témakör bemutatja a számsorozatok egyéni beállítását.
author: SunilGarg
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceDetails
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7be72d348957c5c6494958276b2baa9c67d63c58
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904988"
---
# <a name="set-up-number-sequences-on-an-individual-basis"></a>Számsorozatok beállítása egyedi alapon

[!include [banner](../../includes/banner.md)]

Ez a témakör bemutatja a számsorozatok egyéni beállítását. A számsorozatokat az alapadatok és az azokat igénylő tranzakciós bejegyzések olvasható, egyedi azonosítóinak létrehozására használja a rendszer. Az azonosítókat igénylő alapadatokat és tranzakciós bejegyzéseket hivatkozásnak nevezik. Egy hivatkozáshoz tartozó új rekordok létrehozása előtt be kell állítania egy számsorozatot, és a hivatkozáshoz társítani. Beállíthatja egyszerre az összes igényelt számsorozatot a **Számsorozatok beállítása** varázsló használatával, vagy a **Számsorozat** lap használatával létrehozhatja, illetve módosíthatja az egyes számsorozatokat.

1. Ugorjon a **Navigációs ablaktábla > Modulok > Szervezeti adminisztráció > Számsorozatok > Számsorozatok** elemre.
2. Válassza ki a **Számsorozat** elemet.
3. Adjon meg egy értéket a **Számsorozat kódja** mezőben.
4. Írjon be egy értéket a **Név** mezőbe.
5. A **Hatókör paraméterei** gyorslapon válassza ki a számsorozathoz tartozó hatókört és a hatókör értékét a legördülő listából. A hatókör határozza meg, mely szervezetek használják a számsorozatot. Ezenkívül azok a számsorozatok, amelyek nem **Megosztott** állapotú hatókörrel rendelkeznek olyan szegmensekkel rendelkezhetnek, amelyek megfelelnek a hatókörüknek. Például egy **Jogi személy** hatókörrel ellátott számsorozat rendelkezhet jogi személy hatókörrel. A hatókörökkel kapcsolatos további információkat lásd: [Számsorozatok áttekintése](../number-sequence-overview.md). 
6. Bontsa ki a **Szegmensek** szakaszt.
    - A szegmensek hozzáadásával, eltávolításával és átrendezésével adja meg a számsorozat formátumát.  
    - Az összes hatókör számsorozata tartalmazhatja az *Állandó szegmenseket* és az *Alfanumerikus szegmenseket*. Az állandó szegmensek tartalmazzák azoknak az alfanumerikus karakterek a készletét, amelyek nem módosulnak. Ezen szegmenstípus használatával írjon be egy kötőjelet vagy más elválasztót a Számsorozat szegmensei közé. Az Alfanumerikus szegmensek a kettős kereszt (#) és az és-jel (&) kombinációját tartalmazzák. Ezek a karakterek betűk és számok, melyek a sorozat számainak minden használatánál növekednek. A kettős kereszt (#) használatával jelezheti a növekvő számokat, az (&) jel pedig a növekvő betűket. Például a `#####_2014` formátum az `00001_2014`, `00002_2014` és így tovább sorozatot hozza létre. Legalább egy alfanumerikus szegmensnek lennie kell. A hatókörszegmensek, mint például a társaság vagy a jogi személy, nem kötelező jellegűek. Azonban, ha a formátumban nem helyezi el a hatókörszegmenseket, a rendszer a kijelölt hivatkozáshoz tartozó számokat továbbra is hatókörönként fogja létrehozni.  
7. Bontsa ki a **Referenciák** szakaszt. Válassza ki azt a dokumentumtípust vagy rekordot, amelyhez hozzá kell rendelni ezt a számsorozatot. Ez a lépés nem kötelező a speciális alkalmazási szokásokhoz definiált sorozatok esetében. Ezen esetekben hivatkozás használata nélkül egy új szám jön létre a számsorozat kódja vagy azonosítója értékének használatával. A különleges alkalmazási mód egyik példája egy bizonylatsorozat használata különleges naplónevek létrehozására. Ilyen minták használata azonban nem ajánlott.  
8. Bontsa ki az **Általános** szakaszt. Az Átalános Gyorslapon adja meg, hogy a számsorozat manuális, illetve folytonos vagy nem folytonos legyen. Ezen túlmenően adja meg a számsorozatban használható legkisebb és legnagyobb számot. Nem folytonos számsorozat folytonos számsorozatra cserélése nem ajánlott. A számsorozat nem lesz valóban folyamatos. Ez a változtatás ismétlődő kulcsok miatti hibát is okozhat az adatbázisban. Ezenkívül a folyamatos számsorozatok nagyobb hatással vannak a teljesítményre.   
9. Kattintson a **Mentés** gombra.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
