---
title: Termelési folyamat verziójának létrehozása
description: Ez az eljárás a termelési folyamat új verziójának létrehozását foglalja össze.
author: cvocph
manager: tfehr
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da3b77ed459f42ef91d64066b18b07fece9efc8f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212135"
---
# <a name="create-a-production-flow-version"></a>Termelési folyamat verziójának létrehozása

[!include [banner](../../includes/banner.md)]

Ez az eljárás a termelési folyamat új verziójának létrehozását foglalja össze. Ehhez az eljáráshoz meg kell adni a lean manufacturingre vonatkozó termelési paramétereket és a mértékegységeket. Meg kell adnia egy érték-előállítási folyamatot és egy termelési csoportot is. További információt a termelési folyamatokról és a lean manufacturing tevékenységeiről a Lean manufacturing a Microsoft Dynamics AX szolgáltatáshoz c. tanulmányokban talál. Ez az eljárás az USMF bemutatócéget használja.


## <a name="create-a-production-flow"></a>Termelési folyamat létrehozása
1. Ugrás a Gyártásvezérléshez > Beállítás > Lean típusú termelési folyamat > Termelési folyamatok lehetőségre.
2. Kattintson az Új lehetőségre.
3. Írjon be egy értéket a Név mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
5. A Név mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
6. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Válasszon ki egy érték-előállítási folyamat típusú üzemi egységet. Az érték-előállítási folyamat egy olyan üzemi egység, amely az érték-előállítási folyamat minden tevékenységére és folyamatára kiterjed. Ebben a szakaszban az üzemi egységeknek csak egy jogi személye lehet, és nincs további funkciójuk.  
7. A Gyártási csoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
8. A listában kattintson a kijelölt sorban lévő hivatkozásra.
    * Válassza ki a termelési folyamat termelési csoportját. A termelési csoportokkal meghatározhatja a termelési folyamat anyagát, munkáját és a befejezetlen termelés fiókjait. A termelési folyamat könyvelési környezethez való társításához ki kell választani egy termelési csoportot.  
9. Kattintson a Mentés gombra.

## <a name="create-a-production-flow-version"></a>Termelési folyamat verziójának létrehozása
1. Kattintson a Hozzáadás gombra.
2. Az Lejárati dátum mezőben adjon meg egy dátumot és időpontot.
    * Szükség esetén adja meg a verzió Lejárati dátumát. Ezt bármikor, akár az aktív verzióknál is frissítheti. Ezzel megtervezheti egy verzió kivezetését is.  
3. Kattintson az OK gombra.
4. A listában jelölje meg a kiválasztott sort.
5. Írjon be egy értéket a Mértékegység mezőbe.
6. ResolveChanges a Takt egység.
7. Az Átlagos taktidő mezőben adjon meg egy számot.
    * Adja meg a verzió Átlagos taktidejét. A termelésifolyamat-verzió taktellenőrzéshez adjon meg egy célzott átlagos taktidőt. A takt a mennyiség egy adott időszakra vonatkozóan. Ebben a példában a taktidő 0,2 óra/10 darab. 8 órás munkaidővel ez 400 darabos napi termelési kapacitásnak felel meg.  
8. Adjon meg egy számot a Mennyiség/ciklus mezőben.
    * Adja meg az átlagos taktidőhöz kapcsolódó ciklusonkénti mennyiséget.  
9. Bontsa ki a Verzió részletei c. részt.
10. A Minimum taktidő mezőben adjon meg egy számot.
    * Adja meg a minimális taktidőt. A minimális taktidő kisebb vagy egyenlő lehet az átlagos taktidővel.  
11. A Maximum taktidő mezőben adjon meg egy számot.
    * A maximális taktidő nagyobb vagy egyenlő lehet az átlagos taktidővel.  
12. Adja meg az Időszak a tényleges ciklusidőhöz (napok) mezőben adjon meg egy számot.
    * Adja meg az Időszak a tényleges ciklusidőhöz napjainak a számát. A tényleges ciklusidő időszaka a feladatok által összesített napok száma a tényleges perctől visszafelé, a tényleges ciklusidő kiszámításához. Az érték bármikor módosítható, és azt csak a tényleges ciklusidők kiszámításához használjuk.  
13. Kattintson a Mentés gombra.

