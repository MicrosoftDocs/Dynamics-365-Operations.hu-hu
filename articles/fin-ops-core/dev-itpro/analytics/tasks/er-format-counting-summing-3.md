---
title: ER Számláláshoz és összegzéshez használt formátum konfigurálása (3. rész – Számlálások használata a kimenet elkészítéséhez)
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni az elektronikus jelentési formátumokat a már létrehozott szövegkimenet adatai alapján történő leltározáshoz és összegzéshez. (3. rész)
author: kfend
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
ms.openlocfilehash: 818c48f8c9ac874a36c741e59061d79fb34995ce
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290634"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a>ER Számláláshoz és összegzéshez használt formátum konfigurálása (3. rész – Számlálások használata a kimenet elkészítéséhez)

[!include [banner](../../includes/banner.md)]

Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján. Ezeket a lépéseket bármely vállalatban végrehajthatja.

A lépések végrehajtásához először végre kell hajtania az „ER Számláláshoz és összegzéshez használt formátum konfigurálása (2. rész: Számlálások konfigurálása)” eljárás lépéseit.

Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.


## <a name="configure-this-report-to-use-counting-and-summing-info"></a>A jelentéssel konfigurálása a számlálási és összegzési információk konfigurálásához
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
2. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
3. A fastruktúrában bontsa ki az „Instrastat modell” elemet.
4. A fastruktúrában bontsa ki a következőt: „Intrastat modell\Intrastat (DE)”.
5. A fastruktúrában válassza ki a következőt: „Intrastat modell\Intrastat (DE) \Intrastat (DE) számolással és összegzéssel”.
6. Kattintson a Tervező pontra.
7. Kattintson a Hozzárendelés fülre.
8. Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.
    * Adjon hozzá újra adatforrást a memorizált blokkok listájának lekéréséhez.  
9. A fán válassza ki a „Functions\Calculated mező” lehetőséget.
10. A Név mezőbe írja be a következőt: „$BlocksList”.
    * $BlocksList  
11. Kattintson a Receptúra szerkesztése lehetőségre.
12. A fastruktúrában válassza ki a következőt: „Adatgyűjtési függvények\COLLECTEDLIST”.
13. Kattintson a Függvény hozzáadása gombra.
14. Kattintson az Adatforrás hozzáadása pontra.
15. A Képlet mezőbe írja be a következőt: „COLLECTEDLIST('$BlockName', ”.
    * COLLECTEDLIST('$BlockName',  
16. A Képlet mezőbe írja be a következőt: „COLLECTEDLIST('$BlockName', "*")”.
    * COLLECTEDLIST('$BlockName', "*")  
17. Kattintson a Mentés gombra.
    * A „*” minta azt jelenti, hogy minden blokk szerepelni fog a rekord listáján.  
18. Zárja be a lapot.
19. Kattintson az OK gombra.
20. Kattintson a Formátum fülre.
21. Válassza ki az „Intrastat\Adat” lehetőséget a fastruktúrában.
22. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
23. A fastruktúrában válassza ki ezt: „Szöveg\Sorozat”.
24. A Név mezőbe írja be a „Összegek blokkok szerint” szöveget.
    * Összegek blokkok szerint  
25. A Különleges karakterek mezőben válassza ki az „Új sor – Windows (CR LF)” lehetőséget.
26. Kattintson az OK gombra.
27. A fastruktúrában bontsa ki az „Instrastat\Adat\Összegek blokkok szerint” elemet.
28. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
29. A fában válassza ki ezt: „Text\String”.
30. A Név mezőbe írja be a „Blokk kód” szöveget.
    * Blokk kód  
31. Kattintson az OK gombra.
32. Kattintson a Karakterlánc hozzáadás lehetőségre.
33. A Név mezőbe írja be a „Sorszámlálás” szöveget.
    * Sorszámlálás  
34. Kattintson az OK gombra.
35. Kattintson a Karakterlánc hozzáadás lehetőségre.
36. A Név mezőbe írja be a „Teljes összeg” szöveget.
    * Teljes összeg  
37. Kattintson az OK gombra.
38. Kattintson a Hozzárendelés fülre.
39. A fastruktúrában válassza ki ezt: „$BlocksList”.
40. Kattintson a Kötés gombra.
    * Hozzon létre összegző sort minden memorizált blokkhoz.  
41. Kattintson a Formátum fülre.
42. A fastruktúrában válassza ki az „Instrastat\Adat\Összegek blokkok szerint\Blokk kód” elemet.
43. Kattintson a Hozzárendelés fülre.
44. Kattintson a Receptúra szerkesztése lehetőségre.
45. A Képlet mezőbe írja be a következőt: „„Blokkazonosító:” és ”.
    * „Blokk azonosítója:” és  
46. A fastruktúrában bontsa ki ezt: „$BlocksList”.
47. A fastruktúrában válassza ki a következőt: „$BlocksList\Érték”.
48. Kattintson az Adatforrás hozzáadása pontra.
49. Kattintson a Mentés gombra.
50. Zárja be a lapot.
51. Kattintson a Formátum fülre.
52. A fastruktúrában válassza ki a következőt: „Instrastat\Adat\Összegek blokkok szerint\Sorszámlálás”.
53. Kattintson a Hozzárendelés fülre.
54. Kattintson a Receptúra szerkesztése lehetőségre.
    * Hozzon létre kimenetet a jelentésben szereplő minden egyes blokk sorainak számához.  
55. A Képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és ”.
    * „Sorok száma ebben a blokkban:” és  
56. A Képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és TEXT ”.
    * „Sorok száma ebben a blokkban:” és TEXT(  
57. A fastruktúrában válassza ki a következőt: „Adatgyűjtési függvények\COUNTIFS”.
58. Kattintson a Függvény hozzáadása gombra.
59. Kattintson az Adatforrás hozzáadása pontra.
60. A képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', ".
    * „Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName',  
61. A fastruktúrában bontsa ki ezt: „$BlocksList”.
62. A fastruktúrában válassza ki a következőt: „$BlocksList\Érték”.
63. Kattintson az Adatforrás hozzáadása pontra.
64. A képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, ".
    * „Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,  
65. A fastruktúrában válassza ki a következőt: „$RecName”.
66. Kattintson az Adatforrás hozzáadása pontra.
67. A Képlet mezőben adja meg a következőt: „„Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))”.
    * „Sorok száma ebben a blokkban:” és TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))  
68. Kattintson a Mentés gombra.
69. Zárja be a lapot.
70. Kattintson a Formátum fülre.
71. A fastruktúrában válassza ki a következőt: „Instrastat\Adat\Összegek blokkok szerint\Teljes összeg”.
72. Kattintson a Hozzárendelés fülre.
73. Kattintson a Receptúra szerkesztése lehetőségre.
    * Hozzon létre kimenetet, amely a számlázott összegek összegzése lesz a jelentésben szereplő összes blokk esetében.  
74. A Képlet mezőben adja meg a következőt: „Számlázott összeg összegzése:” és TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))”.
    * „Számlázott összeg összegzése:” és TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))  
75. Kattintson a Mentés gombra.
76. Zárja be a lapot.
77. Kattintson a Mentés gombra.
78. Zárja be a lapot.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
