---
title: ER Számláláshoz és összegzéshez használt formátum konfigurálása (2. rész – Számlálások konfigurálása)
description: Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2d785b321037645837dbcbaf28c8ede9b8e97b79
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550602"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-2---configure-computations"></a>ER Számláláshoz és összegzéshez használt formátum konfigurálása (2. rész – Számlálások konfigurálása)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat egy elektronikus jelentési (ER) formátumot számlálás és összegzés céljára a már létrehozott szöveges kimeneti adatok alapján. Ezeket a lépéseket bármely vállalatban végrehajthatja.

A lépések végrehajtásához először végre kell hajtania az „ER Számláláshoz és összegzéshez használt formátum konfigurálása (1. rész: Formátum létrehozása)” eljárás lépéseit.

Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.


## <a name="create-a-format-configuration-to-add-counting-and-summing-details"></a>Hozzon létre egy formátumkonfigurációt a számlálási és összegzési részletek hozzáadásához
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
2. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
3. A fastruktúrában bontsa ki az „Instrastat modell” elemet.
4. A fastruktúrában jelölje ki a következőt: „Intrastat modell\Intrastat (DE)”.
    * Tegyük fel, hogy testre kell szabnia a Microsoft által biztosított formátumot összefoglaló adatokat tartalmazó sorok hozzáadásával az Intrastat jelentés végéhez. Ehhez saját példányt kell származtatni az Intrastat konfigurációból a Microsoft példányt alapul véve, hogy módosításokat lehessen végezni.  
5. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
6. Az Új mezőbe írja be a következőt: „Származtatás innen: Név: Intrastat (DE), Microsoft”.
7. A Név mezőben írja be a „Intrastat (DE) számolással és összegzéssel”.
8. Kattintson a Konfiguráció létrehozása lehetőségre.

## <a name="configure-this-report-to-do-counting-and-summation-based-on-output-details"></a>A jelentés konfigurálása számlálás és összegzés végzésére a kimeneti adatok alapján
1. Kattintson a Tervező pontra.
2. Válassza az Igen lehetőséget a Kimeneti részletek gyűjtése mezőben.
    * Ez a jelző futásidőben aktiválja kimeneti adatokat az Intrastat-fájl létrehozásához összegyűjtő folyamatot.  
    * Számlálást kell végezni a különböző Intrastat irányokra, így hozzá kell adnia egy dedikált modellfelsorolást a formátumkonfiguráció adatforráslistájához.  
3. Kattintson a Hozzárendelés fülre.
4. Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.
5. A fastruktúrában válassza ki az „Adagmodell\Felsorolás” lehetőséget.
6. A Név mezőbe írja be a következőt: „Irány”.
7. A Modellfelsorolás mezőben adjon meg, vagy válasszon ki egy értéket.
    * Válassza ki az Irány lehetőséget.  
8. Kattintson az OK gombra.
9. Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.
10. A fán válassza ki a „Functions\Calculated mező” lehetőséget.
11. A Név mezőbe írja be a következőt: „$BlockName”.
12. Kattintson a Receptúra szerkesztése lehetőségre.
13. A Képlet mezőbe írja be a következőt: „blokk”.
14. Kattintson a Mentés gombra.
15. Zárja be a lapot.
16. Kattintson az OK gombra.
17. Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.
18. A fán válassza ki a „Functions\Calculated mező” lehetőséget.
19. A Név mezőbe írja be a következőt: „$RecName”.
20. Kattintson a Receptúra szerkesztése lehetőségre.
21. A Képlet mezőbe írja be a következőt: „rekord”.
22. Kattintson a Mentés gombra.
23. Zárja be a lapot.
24. Kattintson az OK gombra.
25. Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.
26. A fán válassza ki a „Functions\Calculated mező” lehetőséget.
27. A Név mezőbe írja be a következőt: „$InvName”.
28. Kattintson a Receptúra szerkesztése lehetőségre.
29. A Képlet mezőbe írja be a következőt: „InvoicedAmountEUR”.
30. Kattintson a Mentés gombra.
31. Zárja be a lapot.
32. Kattintson az OK gombra.
33. Válassza ki az „Intrastat\Adat” lehetőséget a fastruktúrában.
34. Kattintson a Szerkesztés gombra a „Gyűjtött adatkulcs neve” mező esetében
35. Kattintson az Adatforrás hozzáadása pontra.
    * $BlockName  
36. Kattintson a Mentés gombra.
37. Zárja be a lapot.
38. Kattintson a „Gyűjtött adatkulcs neve” mező Szerkesztés gombjára.
39. A Képlet mezőbe írja be a következőt: IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export").
    * IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")  
40. Kattintson a Mentés gombra.
41. Zárja be a lapot.
    * A sorok megszámlálása a sorozatban. Az eredmények használata a „blokk” névvel, a különböző irányokra különállóan fog történni. Az „Import” értéket az összes érkező Intrastat-tranzakcióhoz fogjuk használni. Az „Export” értéket az összes elküldési Intrastat-tranzakcióhoz fogjuk használni. Érdemes úgy elképzelni a dolgot, mint egy virtuális Excel-számolótáblát. Minden tranzakció egy sor, ahol az első oszlop („blokk”) az „Import” vagy az „Export” értéket veszi fel.  
42. A fastruktúrában bontsa ki az „Instrastat\Adat: Sorozat” elemet.
43. A fastruktúrában bontsa ki az „Instrastat\Adat: Sorozat\Érkezések?” elemet.
44. Kattintson a Szerkesztés gombra a „Gyűjtött adatkulcs neve” mező esetében.
    * A sorok megszámlálása a sorozatban. Az eredmények rögzítése a „rekord” név használatával történik.  
45. A fastruktúrában válassza ki a következőt: „$RecName”.
46. Kattintson az Adatforrás hozzáadása pontra.
47. Kattintson a Mentés gombra.
48. Zárja be a lapot.
49. Kattintson a „Gyűjtött adatkulcs értéke” mező Szerkesztés gombjára.
50. A Képlet mezőben adja meg a következőt: "Intrastat.CommodityRecord.CommodityCode".
51. Kattintson a Mentés gombra.
52. Zárja be a lapot.
    * A sorok megszámlálása a sorozatban. Az eredmények használata a „rekord” névvel, a különböző árucikkódokra különállóan fog történni. Érdemes úgy elképzelni a dolgot, mint egy virtuális Excel-számolótáblát. Minden tranzakció egy sor, ahol az első oszlop („blokk”) az „Import” vagy az „Export” értéket veszi fel, a második oszlopot pedig („rekord”) az árucikkód-értékkel tölti fel a rendszer.  
53. A fastruktúrában válassza ki az „Instrastat\Adat: Sorozat\Elküldések?” elemet.
54. Kattintson a Szerkesztés gombra a „Gyűjtött adatkulcs neve” mező esetében
55. A fastruktúrában válassza ki a következőt: „$RecName”.
56. Kattintson az Adatforrás hozzáadása pontra.
57. Kattintson a Mentés gombra.
58. Zárja be a lapot.
59. Kattintson a „Gyűjtött adatkulcs értéke” mező Szerkesztés gombjára.
60. A Képlet mezőben adja meg a következőt: "Intrastat.CommodityRecord.CommodityCode".
61. Kattintson a Mentés gombra.
62. Zárja be a lapot.
63. A fastruktúrában bontsa ki az „Instrastat\Adat: Sorozat\Elküldések: Sorozat?” elemet.
64. A fastruktúrában bontsa ki az „Instrastat\Adat: Sorozat\Elküldések: Sorozat?\Rekord = Intrastat.CommodityRecord” elemet.
65. Kattintson a Formátum fülre.
66. A fastruktúrában válassza ki a következőt: „Intrastat\Adat\Elküldések\Rekord\Számlaösszeg EUR”.
67. Kattintson a Hozzárendelés fülre.
68. Kattintson a Szerkesztés gombra a „Gyűjtött adatkulcs neve” mező esetében.
69. A fastruktúrában válassza ki ezt: „$InvName”.
70. Kattintson az Adatforrás hozzáadása pontra.
71. Kattintson a Mentés gombra.
72. Zárja be a lapot.
    * Összegezze a számlázott összegértékeket a sorozat soraira. Az eredmények használata az „InvoicedAmountEUR” névvel, a különböző Intrastat irányokra és árucikkódokra különállóan fog történni. Érdemes úgy elképzelni a dolgot, mint egy virtuális Excel-számolótábla feltöltését. Minden tranzakció egy sor, ahol az első oszlop („blokk”) az „Import” vagy az „Export” értéket veszi fel. A második oszlopot („rekord”) az árucikkód-értékkel tölti fel a rendszer, a harmadik oszlopot („InvoicedAmountEUR”) pedig a számla összege értékkel.  
73. A fastruktúrában bontsa ki az „Instrastat\Adat: Érkezések?” elemet.
74. A fastruktúrában bontsa ki az „Instrastat\Adat\Érkezések?\Rekord = Intrastat.CommodityRecord” elemet.
75. Kattintson a Formátum fülre.
76. A fastruktúrában válassza ki a következőt: „Intrastat\Adat\Érkezések\Rekord\Számlaösszeg EUR”.
77. Kattintson a Hozzárendelés fülre.
78. Kattintson a Szerkesztés gombra a „Gyűjtött adatkulcs neve” mező esetében.
79. A fastruktúrában válassza ki ezt: „$InvName”.
80. Kattintson az Adatforrás hozzáadása pontra.
81. Kattintson a Mentés gombra.
82. Zárja be a lapot.
83. Kattintson a Mentés gombra.
84. Zárja be a lapot.

