---
title: ER Pénzügyi dimenziók használata adatforrásként (1. rész – Adatmodell kialakítása)
description: A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b02496ebb06e0c2eb644fc7ef3280ca4eca05923
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142024"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1---design-data-model"></a>ER Pénzügyi dimenziók használata adatforrásként (1. rész – Adatmodell kialakítása)

[!include [banner](../../includes/banner.md)]

A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként. Ezeket a lépéseket bármely vállalatban végrehajthatja.

Hajtsa végre az alábbi lépéseket: először hajtsa végre a „Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit.


## <a name="create-a-new-data-model"></a>Új adatmodell létrehozása
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
    * Győződjön meg róla, hogy a „Litware, Inc.” szolgáltató elérhető és aktívként megjelölt legyen.  
2. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
3. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
4. A Név mezőben írja be a „Pénzügyi dimenziók mintamodell” szöveget.
5. Kattintson a Konfiguráció létrehozása lehetőségre.
6. Kattintson a Tervező pontra.
7. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
8. A Név mezőbe írja be a következőt: „Bejegyzés”.
9. Kattintson a Hozzáadás gombra.
10. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
11. A Név mezőbe írja be a Vállalat szót.
12. Kattintson a Hozzáadás gombra.
    * A modellhez hozzáadunk egy új rekordlistát. Ez a lista (a modellt adatforrásként használó összes ER-jelentés esetében) megmutatja kijelölt pénzügyi dimenziók beállításait. Minden egyes pénzügyi dimenzió rekordként jelenik meg a listában, és a megfelelő mezők képezik le a dimenzió beállításait.  
13. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
14. A Név mezőbe írja be a következőt: „Dimenziók beállítása”.
15. A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.
16. Kattintson a Hozzáadás gombra.
17. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
18. A Név mezőbe írja be a következőt: „Kód”.
19. A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.
20. Kattintson a Hozzáadás gombra.
21. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
22. A Név mezőbe írja be a „Név” szöveget.
23. Kattintson a Hozzáadás gombra.
24. A fastruktúrában válassza ki ezt: „Bejegyzés”.
25. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
26. A Név mezőbe írja be a következőt: „Napló”.
27. A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.
28. Kattintson a Hozzáadás gombra.
29. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
30. A Név mezőbe írja be a következőt: „Köteg”.
31. A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.
32. Kattintson a Hozzáadás gombra.
33. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
34. A Név mezőbe írja be a „Tranzakció” szöveget.
35. A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.
36. Kattintson a Hozzáadás gombra.
37. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
38. A Név mezőbe írja be a következőt: „Dátum”.
39. A Cikktípus mezőben válassza ki a „Dátum” lehetőséget.
40. Kattintson a Hozzáadás gombra.
41. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
42. A Név mezőbe írja be a következőt: „Tartozik”.
43. A Cikktípus mezőben válassza ki a „Valós” lehetőséget.
44. Kattintson a Hozzáadás gombra.
45. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
46. A Név mezőbe írja be a „Követel” szöveget.
47. Kattintson a Hozzáadás gombra.
48. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
49. A név mezőbe írja be a „Pénznem” szöveget.
50. A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.
51. Kattintson a Hozzáadás gombra.
52. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
53. A Név mezőbe írja be a következőt: „Bizonylat”.
54. Kattintson a Hozzáadás gombra.
55. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
56. A Név mezőbe írja be a következőt: „Dimenzióadatok”.
57. A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.
58. Kattintson a Hozzáadás gombra.
    * A modellhez hozzáadtunk egy új rekordlistát. Ez a lista (a modellt adatforrásként használó összes ER-jelentés esetében) megmutatja kijelölt pénzügyi dimenziók értékeit. Minden egyes pénzügyi dimenzió rekordként jelenik meg a listában, és a megfelelő mezők képezik le a dimenzió értékeit. A dimenzió neve is megjelenik a rekordban mezőként, amely szükség esetén kiválasztási célból használható.  
59. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
60. A Név mezőbe írja be a következőt: „Kód”.
61. A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.
62. Kattintson a Hozzáadás gombra.
63. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
64. A Név mezőbe írja be a „Leírás” szöveget.
65. Kattintson a Hozzáadás gombra.
66. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
67. A Név mezőbe írja be a „Név” szöveget.
68. Kattintson a Hozzáadás gombra.
69. Kattintson a Mentés gombra.
70. Zárja be a lapot.

