--- 
title: "Jelentés tervezése pénzügyi dimenziók adatforrásként történő használatára elektronikus jelentéskészítéshez (ER)"
description: "A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője szerepkörhöz hozzárendelt felhasználó miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként."
author: NickSelin
manager: AnnBe
ms.date: 10/18/2016
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
ms.openlocfilehash: 6b9b6a59d5e350502c618e11924c46e4ad8229ca
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="design-a-report-to-use-financial-dimensions-as-a-data-source-for-electronic-reporting-er"></a>Jelentés tervezése pénzügyi dimenziók adatforrásként történő használatára elektronikus jelentéskészítéshez (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője szerepkörhöz hozzárendelt felhasználó miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként. Ezeket a lépéseket bármely vállalatban végrehajthatja.

A lépések végrehajtásához először hajtsa végre az „ER Pénzügyi dimenziók használata adatforrásként (2. rész: Modell leképezése)” eljárás lépéseit.


## <a name="design-a-report-to-present-financial-dimensions"></a>Tervezzen jelentést a pénzügyi dimenziók megjelenítésére
1. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
2. A fastruktúrában válassza a „Pénzügyi dimenziók mintamodell” szöveget.
3. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
4. Az Új mezőbe írja be a „ Pénzügyi dimenziók mintamodell adatmodellen alapuló formátum” kifejezést.
    * Annak a modellnek a használata, amelyet már előre létrehoztak az új jelentés adatforrásaként.  
5. A Név mezőbe írja be a „Főkönyvi naplójelentés” szöveget.
6. Az Adatmodell definíciója mezőben válassza a Bejegyzés lehetőséget.
7. Kattintson a Konfiguráció létrehozása lehetőségre.
8. Kattintson a Tervező pontra.
9. Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.
10. A fában válassza ki az XML\Element csomópontot.
11. A Név mezőbe írja be a következőt: „Gyökér”.
12. Kattintson az OK gombra.
13. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
14. A fastruktúrában válassza ki az XML\Attribute elemet.
15. A Név mezőbe írja be a Vállalat szót.
16. Kattintson az OK gombra.
17. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
18. A fában válassza ki az XML\Element csomópontot.
19. A Név mezőbe írja be a következőt: „Napló”.
20. Kattintson az OK gombra.
21. A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem”.
22. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
23. A fastruktúrában válassza ki az XML\Attribute elemet.
24. A Név mezőbe írja be a következőt: „Köteg”.
25. Kattintson az OK gombra.
26. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
27. A fában válassza ki az XML\Element csomópontot.
28. A Név mezőbe írja be a „Tranzakció” szöveget.
29. Kattintson az OK gombra.
30. A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem”.
31. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
32. A fastruktúrában válassza ki az XML\Attribute elemet.
33. A Név mezőbe írja be a következőt: „Bizonylat”.
34. Kattintson az OK gombra.
35. Kattintson az Attribútum hozzáadása lehetőségre.
36. A Név mezőbe írja be a következőt: „Dátum”.
37. Kattintson az OK gombra.
38. Kattintson az Attribútum hozzáadása lehetőségre.
39. A név mezőbe írja be a „Pénznem” szöveget.
40. Kattintson az OK gombra.
41. Kattintson az Attribútum hozzáadása lehetőségre.
42. A Név mezőbe írja be a következőt: „Dt”.
43. Kattintson az OK gombra.
44. Kattintson az Attribútum hozzáadása lehetőségre.
45. A Név mezőbe írja be a következőt: „Ct”.
46. Kattintson az OK gombra.
47. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
48. A fában válassza ki az XML\Element csomópontot.
49. A Név mezőbe írja be a következőt: „Dimenziók”.
50. Kattintson az OK gombra.
51. A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dimenziók: XML-elem”.
52. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
53. A fastruktúrában válassza ki az XML\Attribute elemet.
54. A Név mezőbe írja be a következőt: „Kód”.
55. Kattintson az OK gombra.
56. Kattintson az Attribútum hozzáadása lehetőségre.
57. A Név mezőbe írja be a következőt: „Érték”.
58. Kattintson az OK gombra.
59. Kattintson az Attribútum hozzáadása lehetőségre.
60. A Név mezőbe írja be a következőt: „Leír.”.
61. Kattintson az OK gombra.

## <a name="map-report-elements-to-data-sources"></a>Rendelje hozzá a jelentés elemeit az adatforrásokhoz
1. Kattintson a Hozzárendelés fülre.
2. A fastruktúrában bontsa ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell”.
3. A fastruktúrában bontsa ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista”.
4. A fastruktúrában bontsa ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista”.
5. A fastruktúrában bontsa ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dimenzióadatok: Rekordlista”.
6. A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dimenziók: XML-elem\Leír.: XML-attribútum”.
7. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dimenzióadatok: Rekordlista\Leírás: Karakterlánc”.
8. Kattintson a Kötés gombra.
9. A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dimenziók: XML-elem\Érték: XML-attribútum”.
10. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dimenzióadatok: Rekordlista\Kód: Karakterlánc”.
11. Kattintson a Kötés gombra.
12. A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dimenziók: XML-elem\Kód: XML-attribútum”.
13. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dimenzióadatok: Rekordlista\Név: Karakterlánc”.
14. Kattintson a Kötés gombra.
15. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dimenzióadatok: Rekordlista”.
16. A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dimenziók: XML-elem”.
17. Kattintson a Kötés gombra.
18. A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Ct: XML-attribútum”.
19. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Követel: Valós”.
20. Kattintson a Kötés gombra.
21. A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dt: XML-attribútum”.
22. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Tartozik: Valós”.
23. Kattintson a Kötés gombra.
24. A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Pénznem: XML-attribútum”.
25. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Pénznem: Karakterlánc”.
26. Kattintson a Kötés gombra.
27. A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Dátum: XML-attribútum”.
28. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dátum: Dátum”.
29. Kattintson a Kötés gombra.
30. A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem\Bizonylat: XML-attribútum”.
31. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Bizonylat: Karakterlánc”.
32. Kattintson a Kötés gombra.
33. A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Tranzakció: XML-elem”.
34. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista”.
35. Kattintson a Kötés gombra.
36. A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem\Köteg: XML-attribútum”.
37. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Köteg: Karakterlánc”.
38. Kattintson a Kötés gombra.
39. A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Napló: XML-elem”.
40. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista”.
41. Kattintson a Kötés gombra.
42. A fastruktúrában válassza ki a következőt: „Gyökér: XML-elem\Vállalat: XML-attribútum”.
43. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Vállalat: Karakterlánc”.
44. Kattintson a Kötés gombra.
45. Kattintson a Mentés gombra.
46. Zárja be a lapot.


