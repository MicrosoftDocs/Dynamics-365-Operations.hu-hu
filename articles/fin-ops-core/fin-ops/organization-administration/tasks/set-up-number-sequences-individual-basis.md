---
title: Egyedi számsorozatok beállítása
description: Ez a témakör az egyedi számsorozatok beállítását ismerteti.
author: sericks007
manager: AnnBe
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceDetails
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6ae2fb85bfca6c6a30ec5bd7a13838628a6376f9
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560507"
---
# <a name="set-up-number-sequences-on-an-individual-basis"></a>Egyedi számsorozatok beállítása

[!include [banner](../../includes/banner.md)]

Ez a témakör az egyedi számsorozatok beállítását ismerteti. A számsorozatokat az alapadatok és az azokat igénylő tranzakciós bejegyzések olvasható, egyedi azonosítóinak létrehozására használja a rendszer. Az azonosítókat igénylő alapadatokat és tranzakciós bejegyzéseket hivatkozásnak nevezik. Egy hivatkozáshoz tartozó új rekordok létrehozása előtt be kell állítania egy számsorozatot, és a hivatkozáshoz társítani. Beállíthatja egyszerre az összes igényelt számsorozatot a **Számsorozatok beállítása** varázsló használatával, vagy a **Számsorozat** lap használatával létrehozhatja, illetve módosíthatja az egyes számsorozatokat.

1. Ugorjon a **Navigációs ablaktábla > Modulok > Szervezeti adminisztráció > Számsorozatok > Számsorozatok** elemre.
2. Válassza ki a **Számsorozat** elemet.
3. Adjon meg egy értéket a **Számsorozat kódja** mezőben.
4. Írjon be egy értéket a **Név** mezőbe.
5. A **Hatókör paraméterei** gyorslapon válassza ki a számsorozathoz tartozó hatókört és a hatókör értékét a legördülő listából. A hatókör határozza meg, mely szervezetek használják a számsorozatot. Ezenkívül azok a számsorozatok, amelyek nem **Megosztott** állapotú hatókörrel rendelkeznek olyan szegmensekkel rendelkezhetnek, amelyek megfelelnek a hatókörüknek. Például egy **Jogi személy** hatókörrel ellátott számsorozat rendelkezhet jogi személy hatókörrel. A hatókörökkel kapcsolatos további információkat lásd: [Számsorozatok áttekintése](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/number-sequence-overview). 
6. Bontsa ki a **Szegmensek** szakaszt.
    - A szegmensek hozzáadásával, eltávolításával és átrendezésével adja meg a számsorozat formátumát.  
    - Az összes hatókör számsorozata tartalmazhatja az *Állandó szegmenseket* és az *Alfanumerikus szegmenseket*. Az állandó szegmensek tartalmazzák azoknak az alfanumerikus karakterek a készletét, amelyek nem módosulnak. Ezen szegmenstípus használatával írjon be egy kötőjelet vagy más elválasztót a Számsorozat szegmensei közé. Az Alfanumerikus szegmensek a kettős kereszt (#) és az és-jel (&) kombinációját tartalmazzák. Ezek a karakterek betűk és számok, melyek a sorozat számainak minden használatánál növekednek. A kettős kereszt (#) használatával jelezheti a növekvő számokat, az (&) jel pedig a növekvő betűket. Például a `#####_2014` formátum az `00001_2014`, `00002_2014` és így tovább sorozatot hozza létre. Legalább egy alfanumerikus szegmensnek lennie kell. A hatókörszegmensek, mint például a társaság vagy a jogi személy, nem kötelező jellegűek. Azonban, ha a formátumban nem helyezi el a hatókörszegmenseket, a rendszer a kijelölt hivatkozáshoz tartozó számokat továbbra is hatókörönként fogja létrehozni.  
7. Bontsa ki a **Referenciák** szakaszt. Válassza ki azt a dokumentumtípust vagy rekordot, amelyhez hozzá kell rendelni ezt a számsorozatot. Ez a lépés nem kötelező a speciális alkalmazási szokásokhoz definiált sorozatok esetében. Ezen esetekben hivatkozás használata nélkül egy új szám jön létre a számsorozat kódja vagy azonosítója értékének használatával. A különleges alkalmazási mód egyik példája egy bizonylatsorozat használata különleges naplónevek létrehozására. Ilyen minták használata azonban nem ajánlott.  
8. Bontsa ki az **Általános** szakaszt. Az Átalános Gyorslapon adja meg, hogy a számsorozat manuális, illetve folytonos vagy nem folytonos legyen. Ezen túlmenően adja meg a számsorozatban használható legkisebb és legnagyobb számot. Nem folytonos számsorozat folytonos számsorozatra cserélése nem ajánlott. A számsorozat nem lesz valóban folyamatos. Ez a változtatás ismétlődő kulcsok miatti hibát is okozhat az adatbázisban. Ezenkívül a folyamatos számsorozatok nagyobb hatással vannak a teljesítményre.   
9. Kattintson a **Mentés** gombra.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]