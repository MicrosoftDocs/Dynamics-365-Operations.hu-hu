---
title: Tárgyieszköz-feladási profilok beállítása
description: Ez a feladat-útmutató beállítja a Tárgyieszköz-feladási profilokat.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 286c8732c1f2c92d0f16582b0b9de41990280e5a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "351102"
---
# <a name="set-up-fixed-asset-posting-profiles"></a>Tárgyieszköz-feladási profilok beállítása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a feladat-útmutató beállítja a Tárgyieszköz-feladási profilokat.  Ez a Könyvelői szerepkört és a bemutató adatokat használja a USMF jogi személyhez.  A feladat-útmutatóban megadott példák egy alap feladási profilra vonatkoznak, a feladási profilokat azonban az Ön konkrét számlatükrének és pénzügyi-jelentéskészítési elvárásainak megfelelően kell létrehoznia.

1. Ugrojon a Tárgyi eszközök > Beállítás > Tárgyieszköz-feladási profilok pontra.
2. Kattintson az Új lehetőségre.
3. Írjon egy értéket a Feladási profil mezőbe.
4. A Leírás mezőben adjon meg egy értéket.
    * Amikor tárgyi eszközökkel dolgozik, minden egyes tárgyieszköz-tranzakció típushoz létre kell hoznia feladási profilt.  Ez a feladat-útmutató a Beszerzési tranzakciótípussal indul.  
5. Kattintson a Hozzáadás gombra.
6. A Könyv mezőben adjon meg vagy válasszon ki egy értéket.
    * A Csoportosítások mező lehetővé teszi, hogy meghatározza a feladási profilt a Táblázat (külön számla beállítása minden egyes tárgyi eszközhöz) vagy a Csoport (külön számla beállítása minden egyes tárgyieszköz-csoporthoz) kapcsán.  Ennél a feladat-útmutatónál az értéket a „Mind” beállításon hagyom, hogy a megadott könyvhöz tartozó összes tárgyi eszközre vonatkozzon.  
7. A Fő számla mezőben adja meg a kívánt értékeket.
    * A Beszerzésekhez megadhat ellenszámlát, vagy hagyja a mezőt üresen, ha azt az adott tranzakció kapcsán szeretné kitölteni.    
8. A Tranzakció típusa mezőben válassza a „Beszerzés-kiigazítás” lehetőséget.
    * Beszerzés-kiigazítási tranzakciók esetén ugyanazokat a számlákat használjuk, mint amelyeket a Beszerzési tranzakciók esetén.  
9. Kattintson a Hozzáadás gombra.
10. A Könyv mezőben adjon meg vagy válasszon ki egy értéket.
11. A Fő számla mezőben adja meg a kívánt értékeket.
    * A Beszerzés-kiigazításokhoz megadhat ellenszámlát, vagy hagyja a mezőt üresen, ha azt az adott tranzakció kapcsán szeretné kitölteni.    
12. A Tranzakció típusa mezőben válassza az „Értékcsökkenés” lehetőséget.
13. Kattintson a Hozzáadás gombra.
14. A Könyv mezőben adjon meg vagy válasszon ki egy értéket.
15. A Fő számla mezőben adja meg a kívánt értékeket.
16. Az Ellenszámla mezőben adja meg a kívánt értékeket.
17. A Tranzakció típusa mezőben válassza az „Értékcsökkenés-kiigazítás” lehetőséget.
    * Értékcsökkenés-kiigazítási tranzakciók esetén ugyanazokat a számlákat használjuk, mint amelyeket az Értékcsökkenés tranzakciók esetén.  
18. Kattintson a Hozzáadás gombra.
19. A Könyv mezőben adjon meg vagy válasszon ki egy értéket.
20. A Fő számla mezőben adja meg a kívánt értékeket.
21. Az Ellenszámla mezőben adja meg a kívánt értékeket.
22. A Tranzakció típusa mezőben válassza a „Kivezetés - eladás” lehetőséget.
23. Kattintson a Hozzáadás gombra.
24. A Könyv mezőben adjon meg vagy válasszon ki egy értéket.
25. A Fő számla mezőben adja meg a kívánt értékeket.
    * A Kivezetésekhez megadhat ellenszámlát, vagy hagyja a mezőt üresen, ha azt az adott tranzakció kapcsán szeretné kitölteni.  
26. A Tranzakció típusa mezőben válassza a „Kivezetés - selejtezés” lehetőséget.
    * Kivezetés - eladás esetén ugyanazokat a számlákat használjuk, mint Kivezetés - selejtezés esetén.  
27. Kattintson a Hozzáadás gombra.
28. A Könyv mezőben adjon meg vagy válasszon ki egy értéket.
29. A Fő számla mezőben adja meg a kívánt értékeket.
    * A Kivezetésekhez megadhat ellenszámlát, vagy hagyja a mezőt üresen, ha azt az adott tranzakció kapcsán szeretné kitölteni.  
30. Bontsa ki a Kivezetés szakaszt.
    * Mind az eladás, mind a selejtezés kapcsán kell beállítania kivezetés feladást.  A folyamatot az értékesítéses kivezetés tranzakciókkal indítjuk.  
31. Kattintson a Hozzáadás gombra.
32. A Könyv mezőben adjon meg vagy válasszon ki egy értéket.
33. A Feladási érték mezőben válassza a „Beszerzési érték" lehetőséget.
    * A beszerzési érték minden évre vonatkozóan figyelembe veszi a Beszerzési és Beszerzés-kiigazítási értékeket.  Ön is megadhat számlákat az ilyen tranzakciótípusok kapcsán.  
    * A kivezetési folyamatot be lehet úgy állítani, hogy az - a kivezetés eredményének előjele függvényében - más-más számlát használjon.  Az Eladás értéktípusát „Mind” értékre állítom, hogy ugyanazokat a számlákat használjam az összes selejtezés-típusra.  
34. A Fő számla mezőben adja meg a kívánt értékeket.
35. Az Ellenszámla mezőben adja meg a kívánt értékeket.
36. Kattintson a Hozzáadás gombra.
37. A Könyv mezőben adjon meg vagy válasszon ki egy értéket.
    * A Feladási érték mezőben válassza az „Értékcsökkenés (előző évek)” elemet.  
38. A Fő számla mezőben adja meg a kívánt értékeket.
39. Az Ellenszámla mezőben adja meg a kívánt értékeket.
40. Kattintson a Hozzáadás gombra.
41. A Könyv mezőben adjon meg vagy válasszon ki egy értéket.
42. A Feladási érték mezőben válassza az „Értékcsökkenés (tárgyév)” elemet.
43. A Fő számla mezőben adja meg a kívánt értékeket.
44. Az Ellenszámla mezőben adja meg a kívánt értékeket.
45. Kattintson a Hozzáadás gombra.
46. A Könyv mezőben adjon meg vagy válasszon ki egy értéket.
47. A Feladási érték mezőben válassza az „Értékcsökkenés-kiigazítások (előző évek)” elemet.
48. A Fő számla mezőben adja meg a kívánt értékeket.
49. Az Ellenszámla mezőben adja meg a kívánt értékeket.
50. Kattintson a Hozzáadás gombra.
51. A Könyv mezőben adjon meg vagy válasszon ki egy értéket.
52. A Feladási érték mezőben válassza az „Értékcsökkenés-kiigazítások (tárgyév)” elemet.
53. A Fő számla mezőben adja meg a kívánt értékeket.
54. Az Ellenszámla mezőben adja meg a kívánt értékeket.
55. Kattintson a Hozzáadás gombra.
56. A Könyv mezőben adjon meg vagy válasszon ki egy értéket.
57. A Feladási érték mezőben válassza a „Nettó könyv szerinti érték" lehetőséget.
58. A Fő számla mezőben adja meg a kívánt értékeket.
59. Az Ellenszámla mezőben adja meg a kívánt értékeket.
60. Az értékesítés vagy selejtezés mezőben válassza a „Selejtezés” elemet.
61. Kattintson a Hozzáadás gombra.
62. A Könyv mezőben adjon meg vagy válasszon ki egy értéket.
63. A Feladási érték mezőben válassza a „Beszerzési érték" lehetőséget.
64. A Fő számla mezőben adja meg a kívánt értékeket.
65. Az Ellenszámla mezőben adja meg a kívánt értékeket.
66. Kattintson a Hozzáadás gombra.
67. A Könyv mezőben adjon meg vagy válasszon ki egy értéket.
    * A Feladási érték mezőben válassza az „Értékcsökkenés (előző évek)” elemet.  
68. A Fő számla mezőben adja meg a kívánt értékeket.
69. Az Ellenszámla mezőben adja meg a kívánt értékeket.
70. Kattintson a Hozzáadás gombra.
71. A Könyv mezőben adjon meg vagy válasszon ki egy értéket.
72. A Feladási érték mezőben válassza az „Értékcsökkenés (tárgyév)” elemet.
73. A Fő számla mezőben adja meg a kívánt értékeket.
74. Az Ellenszámla mezőben adja meg a kívánt értékeket.
75. Kattintson a Hozzáadás gombra.
76. A Könyv mezőben adjon meg vagy válasszon ki egy értéket.
77. A Feladási érték mezőben válassza az „Értékcsökkenés-kiigazítások (előző évek)” elemet.
78. A Fő számla mezőben adja meg a kívánt értékeket.
79. Az Ellenszámla mezőben adja meg a kívánt értékeket.
80. Kattintson a Hozzáadás gombra.
81. A Könyv mezőben adjon meg vagy válasszon ki egy értéket.
82. A Feladási érték mezőben válassza az „Értékcsökkenés-kiigazítások (tárgyév)” elemet.
83. A Fő számla mezőben adja meg a kívánt értékeket.
84. Az Ellenszámla mezőben adja meg a kívánt értékeket.
85. Kattintson a Hozzáadás gombra.
86. A Könyv mezőben adjon meg vagy válasszon ki egy értéket.
87. A Feladási érték mezőben válassza a „Nettó könyv szerinti érték" lehetőséget.
88. A Fő számla mezőben adja meg a kívánt értékeket.
89. Az Ellenszámla mezőben adja meg a kívánt értékeket.

