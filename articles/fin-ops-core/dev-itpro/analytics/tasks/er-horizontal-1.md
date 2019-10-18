---
title: ER Vízszintesen bővíthető tartományok használata oszlopok Excel-kimutatásokba történő dinamikus hozzáadásához (1. rész – Formátum kialakítása)
description: Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat elektronikus jelentési (ER) formátumot jelentések létrehozásához OPENXML munkalap (Excel) fájlok formájában, amelyekben a szükséges oszlopok vízszintesen bővíthető tartományokként, dinamikusan hozhatók létre.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e9fb7f108367aee348aa343b4011fb809caac577
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184853"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-1-design-format"></a>ER Vízszintesen bővíthető tartományok használata oszlopok Excel-kimutatásokba történő dinamikus hozzáadásához (1. rész: Formátum kialakítása)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat elektronikus jelentési (ER) formátumot jelentések létrehozásához OPENXML munkalap (Excel) fájlok formájában, amelyekben a szükséges oszlopok vízszintesen bővíthető tartományokként, dinamikusan hozhatók létre. Ezeket a lépéseket bármely vállalatban végrehajthatja.

A lépések végrehajtásához először hajtsa végre ezt a három feladat-útmutatót: 

„ER Konfigurációszolgáltató létrehozása és megjelölése aktívként”

„ER Pénzügyi dimenziók használata adatforrásként (1. rész: Adatmodell kialakítása)”

„ER Pénzügyi dimenziók használata adatforrásként (2. rész: Modell hozzárendelése)”

Ki kell töltenie és mentenie kell a sablon helyi másolatát az itt található mintajelentéssel [Pénzügyi dimenziók webszolgáltatásának mintajelentése](https://go.microsoft.com/fwlink/?linkid=862266).

Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.


## <a name="create-a-new-report-configuration"></a>Új jelentéskonfiguráció létrehozása
1. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
2. A fastruktúrában válassza a „Pénzügyi dimenziók mintamodell” szöveget.
3. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
4. Az Új mezőbe írja be a „ Pénzügyi dimenziók mintamodell adatmodellen alapuló formátum” kifejezést.
    * Használja az előzetesen létrehozott modellt az új jelentés adatforrásaként.  
5. A Név mezőbe írja be a következőt: „Mintajelentés vízszintesen bővíthető tartományokkal”.
    * Mintajelentés vízszintesen bővíthető tartományokkal  
6. A Leírás mezőbe írja be a következőt: „Excel kimenet készítése oszlopok dinamikus hozzáadásával”.
    * Excel kimenet készítése oszlopok dinamikus hozzáadásával  
7. Az Adatmodell definíciója mezőben válassza a Bejegyzés lehetőséget.
8. Kattintson a Konfiguráció létrehozása lehetőségre.

## <a name="design-the-report-format"></a>A jelentésformátum megtervezése
1. Kattintson a Tervező pontra.
2. Kapcsolja be állapotban a „Részletek megjelenítése” váltógombot.
3. A Művelet panelen kattintson az Importálás gombra.
4. Kattintson az Importálás a Microsoft Excel programból lehetőségre.
5. Kattintson a Mellékletek lehetőségre.
    * Importálja a jelentés sablonját. Használja az ehhez letöltött Excel-fájlt.  
6. Kattintson az Új lehetőségre.
7. Kattintson a Fájlra.
8. Zárja be a lapot.
9. A Sablon mezőben adjon meg vagy válasszon ki egy értéket.
    * Letöltött sablon kijelölése  
10. Kattintson az OK gombra.
    * Adjon hozzá egy új tartományt az Excel-kimenet dinamikus létrehozásához a (felhasználói párbeszédpanelen) kiválasztott számú oszloppal a pénzügyi dimenziókhoz. Az egyes oszlopok minden egyes cellája egy adott pénzügyi dimenzió nevét jelöli.  
11. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
12. A fastruktúrában válassza ki a következőt: „Excel\Tartomány”.
13. Az Excel tartomány mezőbe írja be a következőt: „DimNames”.
    * DimNames  
14. A Replikálás iránya mezőben válassza a „Vízszintes” lehetőséget.
15. Kattintson az OK gombra.
16. A fastruktúrában válassza ki a következőt: „Excel = "SampleFinDimWsReport"\Range<DimNames>: Vízszintes”.
17. Kattintson a Felfelé gombra.
18. A fastruktúrában válassza ki a következőt: „Excel = "SampleFinDimWsReport"\Cell<DimNames>”.
19. Válassza a Kivágás parancsot.
20. A fastruktúrában válassza ki a következőt: „Excel = "SampleFinDimWsReport"\Range<DimNames>: Vízszintes”.
21. Kattintson a Beillesztés parancsra.
22. A fastruktúrában bontsa ki a következőt: „Excel = "SampleFinDimWsReport"\Range<DimNames>: Vízszintes”.
23. A fastruktúrában bontsa ki a következőt: „Excel = "SampleFinDimWsReport"\Range<JournalLine>: Függőleges”.
24. A fastruktúrában bontsa ki a következőt: „Excel = "SampleFinDimWsReport"\Függőleges\Tartomány<JournalLine>JournalLine<TransactionLine>: Függőleges".
25. A fastruktúrában válassza ki a következőt: „Excel = "SampleFinDimWsReport"\Függőleges\Tartomány<JournalLine>JournalLine<TransactionLine>: Függőleges".
    * Adjon hozzá egy új tartományt az Excel-kimenet dinamikus létrehozásához a (felhasználói párbeszédpanelen) kiválasztott számú oszloppal a pénzügyi dimenziókhoz. Az egyes oszlopok minden egyes cellája egy adott pénzügyi dimenzió értékét jelöli mindegyik jelentési tranzakcióra.  
26. Kattintson a Tartomány hozzáadása lehetőségre.
27. Az Excel tartomány mezőbe írja be a következőt: „DimValues”.
    * DimValues  
28. A Replikálás iránya mezőben válassza a „Vízszintes” lehetőséget.
29. Kattintson az OK gombra.
30. A fastruktúrában válassza ki a következőt: Excel = "SampleFinDimWsReport"\Range<JournalLine>: Függőleges\Range<TransactionLine>: Vertical\Cell<DimValues>".
31. Válassza a Kivágás parancsot.
32. A fastruktúrában válassza ki a következőt: Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Vízszintes'.
33. Kattintson a Beillesztés parancsra.
34. A fastruktúrában bontsa ki a következőt: Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Vízszintes'.

## <a name="map-format-elements-to-data-sources"></a>Formátum-összetevők leképezése az adatforrásokhoz
1. Kattintson a Hozzárendelés fülre.
2. A fastruktúrában bontsa ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell”.
3. A fastruktúrában bontsa ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista”.
4. A fastruktúrában bontsa ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista”.
5. A fastruktúrában bontsa ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dimenzióadatok: Rekordlista”.
6. A fastruktúrában válassza ki a következőt: Excel = SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal\Cell<DimValues>'.
7. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dimenzióadatok: Rekordlista\Kód: Karakterlánc”.
8. Kattintson a Kötés gombra.
9. A fastruktúrában válassza ki a következőt: Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Vízszintes'.
10. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dimenzióadatok: Rekordlista”.
11. Kattintson a Kötés gombra.
12. A fastruktúrában válassza ki a következőt: Excel = "SampleFinDimWsReport"\Range<JournalLine>: Függőleges\Range<TransactionLine>: Vertical\Cell<Credit>".
13. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Követel: Valós”.
14. Kattintson a Kötés gombra.
15. A fastruktúrában válassza ki a következőt: Excel = "SampleFinDimWsReport"\Range<JournalLine>: Függőleges\Range<TransactionLine>: Vertical\Cell<Debit>".
16. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Tartozik: Valós”.
17. Kattintson a Kötés gombra.
18. A fastruktúrában válassza ki a következőt: Excel = "SampleFinDimWsReport"\Range<JournalLine>: Függőleges\Range<TransactionLine>: Vertical\Cell<Currency>".
19. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Pénznem: Karakterlánc”.
20. Kattintson a Kötés gombra.
21. A fastruktúrában válassza ki a következőt: Excel = "SampleFinDimWsReport"\Range<JournalLine>: Függőleges\Range<TransactionLine>: Vertical\Cell<TransDate>".
22. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Dátum: Dátum”.
23. Kattintson a Kötés gombra.
24. A fastruktúrában válassza ki a következőt: Excel = "SampleFinDimWsReport"\Range<JournalLine>: Függőleges\Range<TransactionLine>: Vertical\Cell<TransVoucher>".
25. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista\Bizonylat: Karakterlánc”.
26. Kattintson a Kötés gombra.
27. A fastruktúrában válassza ki a következőt: Excel = "SampleFinDimWsReport"\Range<JournalLine>: Függőleges\Range<TransactionLine>: Vertical\Cell<TransBatch>".
28. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Köteg: Karakterlánc”.
29. Kattintson a Kötés gombra.
30. A fastruktúrában válassza ki a következőt: „Excel = "SampleFinDimWsReport"\Függőleges\Tartomány<JournalLine>JournalLine<TransactionLine>: Függőleges".
31. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Tranzakció: Rekordlista”.
32. Kattintson a Kötés gombra.
33. A fastruktúrában válassza ki a következőt: Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Cell<Batch>.
34. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista\Köteg: Karakterlánc”.
35. Kattintson a Kötés gombra.
36. A fastruktúrában válassza ki a következőt: Excel = "SampleFinDimWsReport"\Range<JournalLine>: Függőleges.
37. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Napló: Rekordlista”.
38. Kattintson a Kötés gombra.
39. A fastruktúrában bontsa ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Dimenzióbeállítások: Rekordlista”.
40. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Dimenzióbeállítások: Rekordlista\Kód: Karakterlánc”.
41. A fastruktúrában válassza ki a következőt: „Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal\Cell<DimNames>'.
42. Kattintson a Kötés gombra.
43. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Dimenzióbeállítások: Rekordlista”.
44. A fastruktúrában válassza ki a következőt: „Excel = "SampleFinDimWsReport"\Range<DimNames>: Vízszintes”.
45. Kattintson a Kötés gombra.
46. A fastruktúrában válassza ki a következőt: „Excel = "SampleFinDimWsReport"\Cell<CompanyName>”.
47. A fastruktúrában válassza ki a következőt: „modell: Adatmodell Pénzügyi dimenziók mintamodell\Vállalat: Karakterlánc”.
48. Kattintson a Kötés gombra.
49. Kattintson a Mentés gombra.
50. Zárja be a lapot.

