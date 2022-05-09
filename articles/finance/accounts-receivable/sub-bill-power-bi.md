---
title: Előfizetés számlázási Power BI tartalma
description: Ez a témakör azt írja le, mi szerepel az előfizetéses számlázási tartalomban Microsoft Power BI.
author: JodiChristiansen
ms.date: 04/13/2022
ms.topic: article
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-04-13
ms.openlocfilehash: fad96bdaf60e7772e9ea1ff937435b0274303505
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/27/2022
ms.locfileid: "8648147"
---
# <a name="subscription-billing-power-bi-content"></a>Előfizetés számlázási Power BI tartalma

[!include[banner](../includes/banner.md)]

Ez a témakör azt írja le, mi szerepel az előfizetéses számlázási tartalomban Microsoft Power BI. Leírja, hogy hogyan kell hozzáférni a Power BI-jelentésekhez, és információkat nyújt a tartalomcsomag összeállításához előzőleg használt entitásokkal és adatmodellekkel kapcsolatban. 

## <a name="overview"></a>Áttekintés

Az előfizetéses számlázási Power BI tartalom létre lett hozva az előfizetés számlázási adminisztrátorai és vezetői számára. Az előfizetés számlázási kulcsmmetrikus kulcsát, például a számlázási ütemezések havi ismétlődő bevételét (MRR) és a csökkenő egyenleget, valamint a halasztások ütemezésére vonatkozó információkat szolgáltat. Az ismétlődő bevételek és bevételek áttekintéséhez a számlázási és a halasztási ütemezések adatait használja fel.

A Power BI tartalomban a következő három lap található, amelyek összesen négy analitikus jelentést tartalmaznak: 

- **Analitika - MRR** – ez a lap biztosítja a Havi **ismétlődő** számlázási jelentést és a Számlázási **ütemezés részletei jelentést**.
- **Analitika – ez** a lap a Bevétel **jelentés jelentését** szolgáltatja.
- **Analitika - csökkenő egyenleg** – ezen a lapon található a **Csökkenő egyenleg jelentés**.

## <a name="view-data-on-the-analytical-reports"></a>Az elemzési jelentések adatainak megtekintése

Az elemzési jelentések adatainak megtekintése előtt le kell futtatnia egy időszakos folyamatot, amely az egyes jelentésekhez jelentési adatokat generál. A jelentéseket ehhez az adathoz létre kell hozatni, mert nem közvetlenül az adatbázisban van tárolva. 

1. Menjen az Előfizetéses **számlázás \> ismétlődő szerződés számlázása \> ismétlődő \> feladatok MRR analitikus** jelentés kötegelt feldolgozásához, és hajtsa végre a következő lépéseket:

    1. Adjon meg egy három évnél nem több dátumtartományt.
    2. Nem kötelező: Ismétlődő kötegelt feldolgozás beállítása az adatok rendszeres frissítéséhez.
    3. Válassza ki az **OK** lehetőséget.

2. Miután a kötegelt feladat futása befejeződött, menjen **\>\>** a Rendszerfelügyelet beállítása entitástárba, és frissítse **az MRR-jelentés** összesítő mértékegységét. 
3. Menjen az Előfizetéses **számlázás \> bevétel- és költség halasztások \>\> időszakos feladatai aNalitikus jelentés kötegelt** feldolgozásához, és hajtsa végre a következő lépéseket:

    1. Adjon meg egy olyan kezdő és egy záró dátumot, amely nem lehet hosszabb 26 időszaknál. 
    2. Ha az aktuális időszakban az elmúlt időszakok előre jelzett összegét szeretné megtekinteni, **állítsa** Az Aktuális időszak múltbeli összegének előrejelzése beállítást Igen **beállításra**.
    3. Nem kötelező: Ismétlődő kötegelt feldolgozás beállítása az adatok rendszeres frissítéséhez.
    4. Válassza ki az **OK** lehetőséget. 

4. A kötegelt feladat futásának befejezése után menjen **\>\>** a Rendszerfelügyelet beállítása entitástárba, és frissítse **a Jelentés összesítésének** mértékegységét.
5. Menjen az Előfizetéses **számlázás \> bevétel- és költség halasztások \>\> időszakos feladatai Csökkenő egyenleget elemző jelentés kötegelt feldolgozásához**, és hajtsa végre a következő lépéseket:

    1. Adjon meg egy olyan kezdő és egy záró dátumot, amely nem lehet hosszabb 26 időszaknál. 
    2. Ha az aktuális időszakban az elmúlt időszakok előre jelzett összegét szeretné megtekinteni, **állítsa** Az Aktuális időszak múltbeli összegének előrejelzése beállítást Igen **beállításra**.
    3. Nem kötelező: Ismétlődő kötegelt feldolgozás beállítása az adatok rendszeres frissítéséhez.
    4. Válassza ki az **OK** lehetőséget.

6. Miután a kötegelt feladat futása befejeződött, menjen **\>\>** a Rendszerfelügyelet beállítása entitástárba, és **frissítse a Csökkenő egyenleg jelentés összesítő** mértékét.

## <a name="accessing-the-power-bi-content"></a>A Power BI tartalom elérése

Az Előfizetés számlázási Power BI tartalma megjelenik az Előfizetés számlázási **munkaterületén**.
