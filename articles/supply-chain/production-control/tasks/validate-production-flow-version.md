---
title: Termelési folyamat és verzió érvényesítése
description: Ez az eljárás bemutatja, hogyan hozhat létre új termelési folyamatot és első verziót lean manufacturing esetén.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6d87aa427c2bc3868e255c97ea11fd4e79456eef
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573585"
---
# <a name="validate-a-production-flow-and-version"></a>Termelési folyamat és verzió érvényesítése

[!include [banner](../../includes/banner.md)]

Ez az eljárás bemutatja, hogyan hozhat létre új termelési folyamatot és első verziót lean manufacturing esetén. Előfeltételek: Ehhez az eljáráshoz meg kell adni a Lean manufacturingre vonatkozó termelési paramétereket és a mértékegységeket. Meg kell adnia egy Érték-előállítási folyamatot és egy Termelési csoportot is. További információt a termelési folyamatokról és a lean manufacturing tevékenységeiről a Lean manufacturing témájáról szóló tanulmányokban talál. Ez az eljárás az USMF jogi személyre utal a bemutatóadatokban. Ugyanakkor, ha az adott jogi személy lean manufacturingre van konfigurálva, akkor más jogi személy is használható.


## <a name="create-a-production-flow"></a>Termelési folyamat létrehozása
1. Ugrás a Gyártásvezérléshez > Beállítás > Lean típusú termelési folyamat > Termelési folyamatok lehetőségre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Név mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Az érték-előállítási folyamat egy olyan üzemi egység, amely az érték-előállítási folyamat minden tevékenységére és folyamatára kiterjed.   Ebben a szakaszban az üzemi egységeknek csak egy jogi személye lehet, és nincs további funkciójuk.  
7. A Gyártási csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * A termelési csoportokkal meghatározhatja a termelési folyamat anyagát, munkáját és a befejezetlen termelés fiókjait. A termelési folyamat könyvelési környezethez való társításához ki kell választani egy termelési csoportot.  
9. Kattintson a Mentés gombra.

## <a name="create-a-production-flow-version"></a>Termelési folyamat verziójának létrehozása
1. Kattintson a Hozzáadás gombra.
2. Az Lejárati dátum mezőben adjon meg egy dátumot és időpontot.
    * A verzió lejárati dátumát bármikor frissítheti, akár aktív verziók esetén is. Egy verzió kivezetésének tervezéséhez használja a verzió lejáratát.  
3. Kattintson az OK gombra.
4. A listában jelölje meg a kiválasztott sort.
5. Írjon be egy értéket a Mértékegység mezőbe.
6. Válassza ki a taktegységet.
7. Az Átlagos taktidő mezőben adjon meg egy számot.
    * A termelésifolyamat-verzió taktellenőrzéshez adjon meg egy célzott átlagos taktidőt.   A takt a mennyiség egy adott időszakra vonatkozóan.  Ebben a példában a taktidő 0,2 óra/10 darab. 8 órás munkaidővel ez 400 darabos napi termelési kapacitásnak felel meg.  
8. Adjon meg egy számot a Mennyiség/ciklus mezőben.
9. Bontsa ki vagy csukja össze a Verzióadatok szakaszt.
10. A Minimum taktidő mezőben adjon meg egy számot.
    * A minimális taktidő kisebb vagy egyenlő lehet az átlagos taktidővel.  
11. A Maximum taktidő mezőben adjon meg egy számot.
    * A maximális taktidő nagyobb vagy egyenlő lehet az átlagos taktidővel.  
12. Adja meg az Időszak a tényleges ciklusidőhöz napjainak a számát
    * A tényleges ciklusidő időszaka a feladatok által összesített napok száma a tényleges perctől visszafelé, a tényleges ciklusidő kiszámításához. Az érték bármikor módosítható, és azt csak a tényleges ciklusidők kiszámításához használjuk.  
13. Kattintson a Mentés gombra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]