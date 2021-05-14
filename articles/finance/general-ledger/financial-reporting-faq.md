---
title: Pénzügyi jelentéskészítés – GYIK
description: Ebben a témakörben más felhasználóknál a pénzügyi jelentéskészítéssel kapcsolatban felmerült kérdésekre adunk választ.
author: jiwo
ms.date: 01/13/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 023354b0e2973f63411bf81cbeb0344333c49112
ms.sourcegitcommit: d63e7e0593084a61362a6cad3937b1fd956c384f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2021
ms.locfileid: "5923025"
---
# <a name="financial-reporting-faq"></a>Pénzügyi jelentéskészítés – GYIK 

Ez a témakör a pénzügyi jelentéskészítéssel kapcsolatos gyakran ismételt kérdésekre ad választ. 

## <a name="how-do-i-restrict-access-to-a-report-using-tree-security"></a>Hogyan lehet korlátozni a jelentésekhez való hozzáférést a fa biztonsági beállítással?

A következő példák bemutatják, hogyan lehet korlátozni a jelentésekhez való hozzáférést a fa biztonsági beállítással.

Az USMF bemutatóvállalat mérlegkimutatás készít, amelyhez a pénzügyi jelentéskészítési funkció nem minden felhasználójának kellene hozzáférnie. A hozzáférés korlátozása érdekében a fa biztonsági beállítással korlátozhatja az adott jelentéshez való hozzáférést, amelyet így csak bizonyos felhasználók érhetnek el. A hozzáférés korlátozásához kövesse az alábbi lépéseket: 

1. Jelentkezzen be a Pénzügyi jelentés – Jelentéstervező alkalmazásba.
2. Hozzon létre új fadefiníciót. Lépjen a **Fájl > Új > Fadefiníció** lehetőségre.
3. Kattintson duplán az **Összegzés** sorra az **Egység biztonsága** oszlopban.
4. Válassza ki a **Felhasználók és csoportok** lehetőséget.  
5. Válassza ki azokat a felhasználókat vagy csoportokat, amelyeknek hozzá kell férnie ehhez a jelentéshez. 
6. Válassza a **Mentés** lehetőséget.
7. A jelentésdefinícióban adja meg az új fadefiníciót.
8. A fadefinícióban válassza ki a **Beállítások** lehetőséget. A **Jelentési egység kiválasztása** pont alatt válassza az **Összes egységgel együtt** lehetőséget.

## <a name="how-do-i-identify-which-accounts-do-not-match-my-balances"></a>Hogyan tudom meghatározni, hogy mely számlák nem egyeznek meg az egyenlegeimmel?

Ha a jelentés egyenlegei nem egyeznek meg, az alábbi lépésekkel azonosíthatja a számlákat és az eltéréseket. 

**A Pénzügyi jelentés – Jelentéstervező alkalmazás**
1. A Pénzügyi jelentés – Jelentéstervező alkalmazásban hozzon létre egy új sordefiníciót. 
2. Válassza ki a **Szerkesztés > Sorok beszúrása dimenziókból** lehetőséget.
3. Válassza ki a **Főszámla** lehetőséget.  
4. Válassza ki az **OK** lehetőséget.
5. Mentse a sordefiníciót.
6. Hozzon létre egy új oszlopdefiníciót
7. Hozzon létre új jelentésdefiníciót.
8. Válassza ki a **Beállítások** lehetőséget és törölje az opció kijelölését.  
9. Hozza létre a jelentést. 
10. Exportálja a jelentést a Microsoft Excel szoftverbe.

**Dynamics 365 Finance** 
1. A Dynamics 365 Finance szolgáltatásban lépjen a **Főkönyv > Lekérdezések és jelentések > Főkönyvi kivonat** lehetőségre.
2. A következő paraméterek beállítása:
   - **Kezdő dátum** – Adja meg a pénzügyi év kezdetét.
   - **Záró dátum** – Adja meg a dátumot, amelyhez létrehozza a jelentést.
   - **Pénzügyi dimenzió** – Állítsa ezt a mezőt a **Fő számlakészet** lehetőségre.
 3. Válassza ki a **Számítás** lehetőséget.
 4. Exportálja a jelentést a Microsoft Excel szoftverbe.

Most már a főkönyvi kivonati jelentésbe másolhatja az Excelben létrehozott pénzügyi jelentést, hogy összehasonlítsa a **Záró egyenleg** oszlopokat.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]