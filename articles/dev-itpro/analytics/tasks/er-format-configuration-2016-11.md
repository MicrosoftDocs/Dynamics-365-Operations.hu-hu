---
title: ER – Formátumkonfiguráció létrehozása (2016. november)
description: A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre formátum konfigurációt az Elektronikus jelentéshez (ER).
author: NickSelin
manager: AnnBe
ms.date: 11/27/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 582e1a2baee805fe6770465edc7958954f638f1c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544771"
---
# <a name="er-create-a-format-configuration-november-2016"></a>ER – Formátumkonfiguráció létrehozása (2016. november)

[!include [task guide banner](../../includes/task-guide-banner.md)]

A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre formátum konfigurációt az Elektronikus jelentéshez (ER). Ez a formátum konfiguráció határozza meg a kifizetések feldolgozására használt elektronikus dokumentumok formátumát. Ebben a példában létrehoz egy formátum konfigurációt a mintavállalatra, a Litware, Inc.-re vonatkozóan. Hajtsa végre az alábbi lépéseket: Először végezze el a „Modell leképezése a kiválasztott adatforrásokhoz” műveletsorban ismertetett lépéseket.


## <a name="create-a-new-format-configuration"></a>Új formátumkonfiguráció létrehozása
1. Ugorjon a **Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés** pontra.
2. Kattintson a **Jelentéskészítés konfigurációi** lehetőségre.
3. A fán válassza ki a következőt: **Payments (simplified model)**.
4. A **Konfiguráció létrehozása** gombra kattintva megnyithatja a legördülő párbeszédablakot.

 > [!NOTE]
 > Ha nem látja a **Konfiguráció létrehozása** lehetőséget, a tervező módot engedélyeznie kell a **elektronikus bevallási paraméterek** lapon. 
 
5. Az **Új** mezőbe írja be a **PaymentModel modellen alapuló formátum** kifejezést.
6. A **Név** mezőbe írja be a **BACS (UK fictitious)** szöveget.
7. A **Leírás** mezőbe írja be a **BACS vendor payment format (UK fictitious)** szöveget.
    * Az aktív konfigurációs szolgáltató automatikusan megjelenik itt. Ez a szolgáltató tartja majd karban ezt a konfigurációt. Más szolgáltatók is használhatják ezt a konfigurációt, de nem tudják majd karbantartani.  
    * Elektronikusdokumentum-formátum definiálható. Ezt a mezőt hagyja üresen, ha azt szeretné, hogy futásidőben választhassa ki a formátumot.  
8. Az **Adatmodell mezőben** adjon meg vagy válasszon ki egy értéket.
9. Kattintson a **Konfiguráció létrehozása** lehetőségre. Új konfiguráció létrehozása megtörtént. Egy vázlat verzió használható a tervezési formátum tárolására az elektronikus dokumentumok kezeléséhez.  

## <a name="design-the-format-of-an-electronic-document"></a>Elektronikus dokumentumok formátumának tervezése
1. Kattintson a **Tervező** pontra.
2. Kattintson a **Gyökér hozzáadása** lehetőségre a legördülő párbeszédpanel megnyitásához.
3. A fában válassza ki a **Common\File** csomópontot.
4. A **Név** mezőbe írja be az **Xml** szót.
5. A **Kódolás** mezőbe írja be az **UTF-8** szót.
6. Kattintson az **OK** gombra.
7. Kattintson a **Hozzáadás** gombra.
8. A fában válassza ki az **XML\Element** csomópontot.
9. A **Név** mezőbe írja be a **Message** szöveget.
10. Kattintson az **OK** gombra.
11. A fastruktúrában válassza ki ezt: **Xml\Üzenet**.
12. Kattintson az **Elem hozzáadása** lehetőségre.
13. A **Név** mezőbe írja be a **ProcessingDate** szót.
14. Kattintson az **OK** gombra.
15. Kattintson az **Elem hozzáadása** lehetőségre.
16. A Név mezőbe írja be a **MessageId** szöveget.
17. Kattintson az **OK** gombra.
18. Kattintson az **Elem hozzáadása** lehetőségre.
19. A **Név** mezőbe írja be a **Fizetések** szöveget.
20. Kattintson az **OK** gombra.
21. A fastruktúrában válassza ki ezt: **Xml\Üzenet\Fizetések**.
22. Kattintson az **Elem hozzáadása** lehetőségre.
23. A **Név mezőbe** írja be az **Item** szót.
24. Kattintson az **OK** gombra.
25. A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item**.
26. Kattintson a **Hozzáadás** gombra.
27. A fastruktúrában válassza ki az **XML\Attribute** elemet.
28. A Név mezőbe írja be az **Id** szöveget.
29. Kattintson az **OK** gombra.
30. Kattintson a **Hozzáadás** gombra.
31. A fában válassza ki az **XML\Element** csomópontot.
32. A Név mezőbe írja be a **Vendor** szöveget.
33. Kattintson az **OK** gombra.
34. A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Vendor**.
35. Kattintson az **Elem hozzáadása** lehetőségre.
36. A Név mezőbe írja be a **Name** szöveget.
37. Kattintson az **OK** gombra.
38. Kattintson az **Elem hozzáadása** lehetőségre.
39. A **Név** mezőbe írja be a **Bank** szöveget.
40. Kattintson az **OK** gombra.
41. A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Vendor\Bank**.
42. Kattintson az **Elem hozzáadása** lehetőségre.
43. A **Név** mezőbe írja be a **RoutingNumber** szöveget.
44. Kattintson az **OK** gombra.
45. Kattintson az **Elem hozzáadása** lehetőségre.
46. A **Név** mezőbe írja be az **AccountNumber** szöveget.
47. Kattintson az **OK** gombra.
48. A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Vendor**.
49. Kattintson a **Másolás** lehetőségre.
50. A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item**.
51. Kattintson a **Beillesztés** parancsra.
52. A **Név** mezőbe írja be a **Payer** szöveget.
53. A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item**.
54. Kattintson az **Elem hozzáadása** lehetőségre.
55. A **Név** mezőbe írja be a **Pénznem** szöveget.
56. Kattintson az **OK** gombra.
57. Kattintson az **Elem hozzáadása** lehetőségre.
58. A **Név** mezőbe írja be a **Leírás** szöveget.
59. Kattintson az **OK** gombra.
60. Kattintson az **Elem hozzáadása** lehetőségre.
61. A Név mezőbe írja be a **TransDate** szöveget.
62. Kattintson az **OK** gombra.
63. Kattintson az **Elem hozzáadása** lehetőségre.
64. A Név mezőbe írja be az **Amount** szöveget.
65. Kattintson az **OK** gombra.

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a>Formátum-összetevők előkészítése adatmodell-elemek leképezéséhez
1. A fastruktúrában válassza ki ezt: **Xml\Message\ProcessingDate**.
2. A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.
3. A fastruktúrában válassza ki ezt: **Text\DateTime**.
4. A **Formátum** mezőbe írja be az **yyyy-MM-dd** szöveget.
5. Kattintson az **OK** gombra.
6. A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\TransDate**.
7. Kattintson a **Dátum/idő hozzáadása** lehetőségre.
8. A **Formátum** mezőbe írja be az **yyyy-MM-dd** szöveget.
9. A **DateTime** típus mezőben válassza ki a **Dátum** lehetőséget.
10. Kattintson az **OK** gombra.
11. A fastruktúrában válassza ki ezt: **Xml\Message\MessageId**.
12. A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.
13. A fában válassza ki ezt: **Text\String**.
14. Kattintson az **OK** gombra.
15. A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Vendor\Name**.
16. Kattintson a **Karakterlánc hozzáadása** lehetőségre.
17. Kattintson az **OK** gombra.
18. A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber**.
19. Kattintson a **Karakterlánc hozzáadása** lehetőségre.
20. Kattintson az **OK** gombra.
21. A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Vendor\Bank\AccountNumber**.
22. Kattintson a **Karakterlánc hozzáadása** lehetőségre.
23. Kattintson az **OK** gombra.
24. A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Payer\Name**.
25. Kattintson a **Karakterlánc hozzáadása** lehetőségre.
26. Kattintson az **OK** gombra.
27. A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Payer\Bank\RoutingNumber**.
28. Kattintson a **Karakterlánc hozzáadása** lehetőségre.
29. Kattintson az **OK** gombra.
30. A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Payer\Bank\AccountNumber**.
31. Kattintson a **Karakterlánc hozzáadása** lehetőségre.
32. Kattintson az **OK** gombra.
33. A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Currency**.
34. Kattintson a **Karakterlánc hozzáadása** lehetőségre.
35. Kattintson az **OK** gombra.
36. A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Description**.
37. Kattintson a **Karakterlánc hozzáadása** lehetőségre.
38. Kattintson az **OK** gombra.
39. A fastruktúrában válassza ki ezt: **Xml\Message\Payments\Item\Amount**.
40. Kattintson a **Karakterlánc hozzáadása** lehetőségre.
41. Kattintson az **OK** gombra.
42. Kattintson a **Mentés** gombra.
43. Zárja be a lapot.

