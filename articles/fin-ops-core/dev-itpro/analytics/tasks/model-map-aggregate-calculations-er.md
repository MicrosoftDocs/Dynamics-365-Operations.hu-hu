---
title: Modell-leképezési konfigurációk használata összesítő számítások létrehozásához az adatbázis szintjén
description: A folyamat révén új, elektronikus jelentésen (ER) alapuló modell-leképezési konfigurációt tervezhet meg, és a beépített ER-funkciók segítségével hatékony összesített számításokat végezhet.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f1c4ddf0fac5ba962c3dab545bfa7e0df4afa948
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684115"
---
# <a name="use-model-mapping-configurations-for-aggregate-calculations-at-the-database-level"></a>Modell-leképezési konfigurációk használata összesítő számítások létrehozásához az adatbázis szintjén

[!include [banner](../../includes/banner.md)]

A folyamat révén új, elektronikus jelentésen (ER) alapuló modell-leképezési konfigurációt tervezhet meg, és a beépített ER-funkciók segítségével hatékony összesített számításokat végezhet. Ebben a folyamatban egy konfigurációt hoz létre a Litware, Inc. példavállalatra vonatkozóan. 

Ez az eljárás a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkör rendelkező felhasználók számára készült. Ezek a lépések bármely adathalmazzal végrehajthatók.

 A jelenlegi lépések végrehajtásához előbb „Az ER javítja az aggregált számítások hatékonyságát ezek adatbázis szintjén történő végrehajtásával (1. rész: Konfigurációk előkészítése)” folyamat lépéseit kell végrehajtania.

1. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
2. A fastruktúrában bontsa ki az „Instrastat modell” elemet.
3. A fastruktúrában jelölje ki a következőt: „Intrastat (model)\Intrastat sample mapping”.
4. Kattintson a Tervező pontra.
5. Kattintson a Tervező pontra.
6. A fastruktúrában válassza ki a következőt: „Dynamics 365 for Operations\Tábla rekordjai” csomópont.
7. Kattintson a Gyökér hozzáadása gombra.
    * Adja hozzá a csoportosítani kívánt rekordokat jelző új adatforrást.  
8. A Név mezőbe írja be a „Transactions” szöveget.
    * Tranzakciók  
9. Írja be a Tábla mezőbe az „Intrastat” szöveget.
    * Intrastat  
10. Kattintson az OK gombra.
11. A fastruktúrában válassza ki a „Funkciók\Csoportosítás alapja ” lehetőséget.
    * Ezen adatforrástípussal futásidőben vezethet be új adatforrásokat a rekordok csoportosításához és szükséges aggregációk kiszámításához.  
12. Kattintson a Gyökér hozzáadása gombra.
13. A Név mezőbe írja be „TransactionsGroups” szöveget.
    * TranzakcióCsoportok  
14. Kattintson a Csoport szerkesztési szempontja lehetőségre.
15. A fastruktúrában válassza ki a Tranzakciók pontot.
    * Válassza ki azt a hozzáadott adatforrást a „Rekordlista” típusban, amely a csoportosításához használni kívánt rekordjait képviseli.  
16. Kattintson a Mező hozzáadása a következőhöz lehetőségre.
17. Kattintson a Csoportosítandó lehetőségre.
18. A fában bontsa ki a Tranzakciók csomópontot.
19. A fastruktúrában válassza ki a „Transactions\Direction” lehetőséget.
20. Kattintson a Mező hozzáadása a következőhöz lehetőségre.
21. Kattintson a Csoportosított mezők lehetőségre.
    * Jelölje ki a mezőt a csoportosítási szint megadásához. A kiválasztás alapján az adatforrás futásidejében annyi tranzakciócsoport jelenik meg, ahány iránykód érvényesül az Intrastat-táblában.  
22. A fán jelölje be a „Tranzakciók\Számla összege(AmountMST)” lehetőséget.
    * Válassza ki a mezőt az aggregációs számítás forrásának megadásához.  
23. Kattintson a Mező hozzáadása a következőhöz lehetőségre.
24. Kattintson az Aggregációs mezők lehetőségre.
25. A listában jelölje meg a kiválasztott sort.
26. A Módszer mezőben válassza az „Összeg” lehetőséget.
    * Itt adhatja meg az aggregáció típusát.  
27. A Név mezőbe írja be a SumOfAmountMSTn szöveget.
    * Adja meg az aggregáció nevét a konfigurált adatforrásban.  
28. Kattintson a Mentés gombra.
    * Vegye figyelembe, hogy a Végrehajtás helye mező mutatja, hogy a csoportosítás futásidőben történik az SQL-adatbázisban.  
29. Zárja be a lapot.
30. Kattintson az OK gombra.
31. A fastruktúrában bontsa ki az Összegek pontot.
32. A fában bontsa ki a TransactionsGroups elemet.
33. A fában bontsa ki a „TransactionsGroups\aggregated” elemet.
34. A fán jelölje be a „TransactionsGroups\aggregated\SumOfAmountMST” lehetőséget.
35. A fán jelölje be az „Összegek\Teljes számlaérték(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')” lehetőséget.
36. Kattintson a Kötés gombra.
    * Ezen beállítás alapján ez az adatforrás kiszámítja az „AmountMST” mező minden egyes tranzakciócsoportjának összértékét. Ez az aggregált számítás a TransactionsGroups.aggregated.TotalAmount cikként érhető el.  
37. A fában bontsa ki a TransactionsGroups elemet.
38. A fastruktúrában válassza ki a TransactionsGroups lehetőséget.
39. Kattintson a Szerkesztés lehetőségre.
40. Kattintson a Csoport szerkesztési szempontja lehetőségre.
41. A fában bontsa ki a Tranzakciók csomópontot.
42. A fán jelölje be a „Tranzakciók\Számla összege(AmountMST)” lehetőséget.
43. Kattintson a Mező hozzáadása a következőhöz lehetőségre.
44. Kattintson az Aggregációs mezők lehetőségre.
45. A listában jelölje meg a kiválasztott sort.
46. A Módszer mezőben válassza a „Max” lehetőséget.
47. A Név mezőbe írja be a MaxOfAmountMST szöveget.
48. Kattintson a Mentés gombra.
    * Jelenleg a GROUPBY adatforrások végrehajtását bizonyos korlátozásokkal át lehet számítani az SQL-adatbázis szintjére. Az átszámítást a „Rekordlista” típus adatforrásai számára kifejezésként megjelenő adatforrásokra végezheti a SZŰRŐ funkció használatával. Ez akkor is megtehető, ha az egyetlen aggregáció a csoportosítási rekordok egyetlen mezőjére van konfigurálva.  
    * Vegye figyelembe, hogy annak ellenére, hogy az AmountMST mezőben egynél több aggregáció lett beállítva, a Végrehajtás helye mező továbbra is jelzi, hogy a csoportosítást futásidőben történik az SQL-adatbázisban. Ennek oka, hogy csak egy aggregáció kötődik az adatmodellcikkhez, és futásidőben használják az adatforrás adatainak lekérésére.  
49. Zárja be a lapot.
50. Kattintson az OK gombra.
51. A fában bontsa ki a TransactionsGroups elemet.
52. A fában bontsa ki a „TransactionsGroups\aggregated” elemet.
53. A fán jelölje be a „TransactionsGroups\aggregated\MaxOfAmountMST” lehetőséget.
54. A fán jelölje be az „Összegek\Teljes statisztikai érték(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')” lehetőséget.
55. Kattintson a Kötés gombra.
56. A fában bontsa ki a TransactionsGroups elemet.
57. A fastruktúrában válassza ki a TransactionsGroups lehetőséget.
58. Kattintson a Szerkesztés lehetőségre.
59. Kattintson a Csoport szerkesztési szempontja lehetőségre.
    * Vegye figyelembe, hogy a Végrehajtás helye mező azt jelzi, hogy a csoportosításra a memória futásidőben kerül sor, mivel ugyanazon mező mindkét aggregációja az adatmodellcikkekhez kötődik.   
60. A listában jelölje meg az összes sort, vagy törölje a jelölésüket.
61. Kattintson a Törlés gombra.
62. Kattintson az Igen gombra.
63. Kattintson a Törlés gombra.
64. Kattintson az Igen gombra.
65. Kattintson a Mező hozzáadása a következőhöz lehetőségre.
66. Kattintson a Csoportosítandó lehetőségre.
67. A fastruktúrában bontsa ki az Árucikkrekord(Instrastat) elemet.
68. Kattintson a Mentés gombra.
    * Vegye figyelembe, hogy a Végrehajtás helye mező azt mutatja, hogy a csoportosításra a memória futásidőben kerül sor annak ellenére, hogy nincsenek definiálva aggregációk, és a Tábla rekordjai típus az Intrastat tábla megfelelő értékeire vonatkozik. Ennek oka az, hogy az adatforrás tartalmaz néhány olyan számított mezőt, amelyeket még nem lehet átszámítani az SQL-adatbázis szintjére.  

