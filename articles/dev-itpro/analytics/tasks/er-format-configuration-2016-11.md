--- 
title: "Elektronikus jelentéskészítés (ER) formátumkonfigurációjának létrehozása"
description: "A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre formátum konfigurációt az Elektronikus jelentéshez (ER)."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: c46b222cb12d0432609c47f89afc522e02c41ab6
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-format-configuration-for-electronic-reporting-er"></a>Elektronikus jelentéskészítés (ER) formátumkonfigurációjának létrehozása

[!include[task guide banner](../../includes/task-guide-banner.md)]

A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre formátum konfigurációt az Elektronikus jelentéshez (ER). Ez a formátum konfiguráció határozza meg a kifizetések feldolgozására használt elektronikus dokumentumok formátumát. Ebben a példában létrehoz egy formátum konfigurációt a mintavállalatra, a Litware, Inc.-re vonatkozóan. Hajtsa végre az alábbi lépéseket: Először végezze el a „Modell leképezése a kiválasztott adatforrásokhoz” műveletsorban ismertetett lépéseket.


## <a name="create-a-new-format-configuration"></a>Új formátumkonfiguráció létrehozása
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
2. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
3. A fán válassza ki a következőt: „Payments (simplified model)”.
4. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
5. Az Új mezőbe írja be a „PaymentModel modellen alapuló formátum” kifejezést.
6. A Név mezőbe írja be a „BACS (UK fictitious)” szöveget.
    * BACS (UK fiktív)  
7. A Leírás mezőbe írja be a „BACS vendor payment format (UK fictitious)” szöveget.
    * BACS szállítói kifizetés formátum (UK fiktív)  
    * Az aktív konfigurációs szolgáltató automatikusan megjelenik itt. Ez a szolgáltató tartja majd karban ezt a konfigurációt. Más szolgáltatók is használhatják ezt a konfigurációt, de nem tudják majd karbantartani.  
    * Elektronikusdokumentum-formátum definiálható. Ezt a mezőt hagyja üresen, ha azt szeretné, hogy futásidőben választhassa ki a formátumot.  
8. Az Adatmodell mezőben adjon meg vagy válasszon ki egy értéket.
9. Kattintson a Konfiguráció létrehozása lehetőségre.
    * Új konfiguráció létrehozása megtörtént. Egy vázlat verzió használható a tervezési formátum tárolására az elektronikus dokumentumok kezeléséhez.  

## <a name="design-format-of-electronic-document"></a>Elektronikus dokumentumok tervezési formátuma
1. Kattintson a Tervező pontra.
2. Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.
3. A fában válassza ki a Common\File csomópontot.
4. A Név mezőbe írja be az Xml szót.
    * Xml  
5. A Kódolás mezőbe írja be az UTF-8 szót.
    * UTF-8  
6. Kattintson az OK gombra.
7. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
8. A fában válassza ki az XML\Element csomópontot.
9. A Név mezőbe írja be a Message szöveget.
    * Üzenet  
10. Kattintson az OK gombra.
11. A fastruktúrában válassza ki ezt: „Xml\Üzenet”.
12. Kattintson az Elem hozzáadása lehetőségre.
13. A Név mezőbe írja be a ProcessingDate szót.
    * Feldolgozás dátuma  
14. Kattintson az OK gombra.
15. Kattintson az Elem hozzáadása lehetőségre.
16. A Név mezőbe írja be a MessageId szöveget.
    * Üzenetazonosító  
17. Kattintson az OK gombra.
18. Kattintson az Elem hozzáadása lehetőségre.
19. A Név mezőbe írja be a „Fizetések” szöveget.
    * Kifizetések  
20. Kattintson az OK gombra.
21. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések”.
22. Kattintson az Elem hozzáadása lehetőségre.
23. A Név mezőbe írja be az Item szót.
    * Tétel  
24. Kattintson az OK gombra.
25. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk”.
26. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
27. A fastruktúrában válassza ki az XML\Attribute elemet.
28. A Név mezőbe írja be az Id szöveget.
    * Azonosító  
29. Kattintson az OK gombra.
30. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
31. A fában válassza ki az XML\Element csomópontot.
32. A Név mezőbe írja be a Vendor szöveget.
    * Szállító  
33. Kattintson az OK gombra.
34. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító”.
35. Kattintson az Elem hozzáadása lehetőségre.
36. A Név mezőbe írja be a „Név” szöveget.
    * Név  
37. Kattintson az OK gombra.
38. Kattintson az Elem hozzáadása lehetőségre.
39. A Név mezőbe írja be a Bank szöveget.
    * Bank  
40. Kattintson az OK gombra.
41. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Bank”.
42. Kattintson az Elem hozzáadása lehetőségre.
43. A Név mezőbe írja be a „RoutingNumber” szöveget.
    * Útvonalszám  
44. Kattintson az OK gombra.
45. Kattintson az Elem hozzáadása lehetőségre.
46. A Név mezőbe írja be az „AccountNumber” szöveget.
    * Számlaszám  
47. Kattintson az OK gombra.
48. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító”.
49. Kattintson a Másolás lehetőségre.
50. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk”.
51. Kattintson a Beillesztés parancsra.
52. A Név mezőbe írja be a Payer szöveget.
    * Fizető  
53. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk”.
54. Kattintson az Elem hozzáadása lehetőségre.
55. A név mezőbe írja be a „Pénznem” szöveget.
    * Pénznem  
56. Kattintson az OK gombra.
57. Kattintson az Elem hozzáadása lehetőségre.
58. A Név mezőbe írja be a „Leírás” szöveget.
    * Leírás  
59. Kattintson az OK gombra.
60. Kattintson az Elem hozzáadása lehetőségre.
61. A Név mezőbe írja be a 'TransDate' szöveget.
    * Tranzakció dátuma  
62. Kattintson az OK gombra.
63. Kattintson az Elem hozzáadása lehetőségre.
64. A Név mezőbe írja be az 'Amount' szöveget.
    * Összeg  
65. Kattintson az OK gombra.

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a>Formátum-összetevők előkészítése adatmodell-elemek leképezéséhez
1. A fastruktúrában válassza ki ezt: „Xml\Üzenet\ProcessingDate”.
2. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
3. A fastruktúrában válassza ki ezt: „Szöveg\Dátum idő”.
4. A Formátum mezőbe írja be az yyyy-MM-dd szöveget.
    * éééé-HH-nn  
5. Kattintson az OK gombra.
6. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\TransDate”.
7. Kattintson a Dátum/idő hozzáadása lehetőségre.
8. A Formátum mezőbe írja be az yyyy-MM-dd szöveget.
    * éééé-HH-nn  
9. A DateTime típus mezőben válassza ki a „Dátum” lehetőséget.
10. Kattintson az OK gombra.
11. A fastruktúrában válassza ki ezt: „Xml\Üzenet\MessageId”.
12. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
13. A fában válassza ki ezt: „Text\String”.
14. Kattintson az OK gombra.
15. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Név”.
16. Kattintson a Karakterlánc hozzáadás lehetőségre.
17. Kattintson az OK gombra.
18. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Bank\RoutingNumber”.
19. Kattintson a Karakterlánc hozzáadás lehetőségre.
20. Kattintson az OK gombra.
21. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Szállító\Bank\Számlaszám”.
22. Kattintson a Karakterlánc hozzáadás lehetőségre.
23. Kattintson az OK gombra.
24. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Fizető\Név”.
25. Kattintson a Karakterlánc hozzáadás lehetőségre.
26. Kattintson az OK gombra.
27. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Fizető\Bank\RoutingNumber”.
28. Kattintson a Karakterlánc hozzáadás lehetőségre.
29. Kattintson az OK gombra.
30. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Fizető\Bank\Számlaszám”.
31. Kattintson a Karakterlánc hozzáadás lehetőségre.
32. Kattintson az OK gombra.
33. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Pénznem”.
34. Kattintson a Karakterlánc hozzáadás lehetőségre.
35. Kattintson az OK gombra.
36. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Leírás”.
37. Kattintson a Karakterlánc hozzáadás lehetőségre.
38. Kattintson az OK gombra.
39. A fastruktúrában válassza ki ezt: „Xml\Üzenet\Fizetések\Cikk\Összeg”.
40. Kattintson a Karakterlánc hozzáadás lehetőségre.
41. Kattintson az OK gombra.
42. Kattintson a Mentés gombra.
43. Zárja be a lapot.


