---
title: ER Vízszintesen bővíthető tartományok használata oszlopok Excel-kimutatásokba történő dinamikus hozzáadásához (1. rész – Formátum kialakítása)
description: Ez a témakör azt mutatja be, hogyan kell konfigurálni egy Elektronikus jelentéskészítési (ER) formátumot jelentések OPENXML-munkalap (Excel) fájlként történő generálásához. (1. rész)
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ab360c259af37ce3995d3cd2560bc2e765e0bceb
ms.sourcegitcommit: e3290eb58ae569a59d6ae2e6922e7d8be8f1980f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2021
ms.locfileid: "7551776"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-1---design-format"></a>ER Vízszintesen bővíthető tartományok használata oszlopok Excel-kimutatásokba történő dinamikus hozzáadásához (1. rész – Formátum kialakítása)

[!include [banner](../../includes/banner.md)]

Az alábbi útmutató azt ismerteti, hogy a rendszergazda vagy elektronikus jelentésfejlesztői szerepkörhöz hozzárendelt felhasználó hogyan konfigurálhat elektronikus jelentési (ER) formátumot jelentések létrehozásához OPENXML munkalap (Excel) fájlok formájában, amelyekben a szükséges oszlopok vízszintesen bővíthető tartományokként, dinamikusan hozhatók létre. Ezeket a lépéseket bármely vállalatban végrehajthatja.

A lépések végrehajtásához először hajtsa végre ezt a három feladat-útmutatót:

„ER Konfigurációszolgáltató létrehozása és megjelölése aktívként”

„ER Pénzügyi dimenziók használata adatforrásként (1. rész – Adatmodell kialakítása)”

„ER Pénzügyi dimenziók használata adatforrásként (2. rész – Modell hozzárendelése)”

Ki kell töltenie és mentenie kell a sablon helyi másolatát az itt található mintajelentéssel [Pénzügyi dimenziók webszolgáltatásának mintajelentése](https://download.microsoft.com/download/3/1/3/313e2090-bc0a-421f-bf96-c58da9bc0dea/SampleFinDimWsReport.xlsx).

Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.

## <a name="create-a-new-report-configuration"></a>Új jelentéskonfiguráció létrehozása

1. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
2. A fastruktúrában válassza ki a `Financial dimensions sample model` csomópontot.
3. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
4. Az Új mezőben adja meg a `Format based on data model Financial dimensions sample model` értéket.
    * Használja az előzetesen létrehozott modellt az új jelentés adatforrásaként.  
5. A Név mezőbe írja be a „`Sample report with horizontally expandable ranges`” szöveget.
    * Mintajelentés vízszintesen bővíthető tartományokkal  
6. A Leírás mezőbe írja be a `To make Excel output with dynamically adding columns` értéket.
    * Excel kimenet készítése oszlopok dinamikus hozzáadásával  
7. Az Adatmodell definíciója mezőben válassza a Bejegyzés lehetőséget.
8. Kattintson a Konfiguráció létrehozása lehetőségre.

## <a name="design-the-report-format"></a>A jelentésformátum megtervezése

1. Kattintson a Tervező pontra.
2. Kapcsolja be a `Show details` váltógombot.
3. A Művelet panelen kattintson az Importálás gombra.
4. Kattintson az Importálás a Microsoft Excel programból lehetőségre.
5. Kattintson a Mellékletek lehetőségre.
    * Importálja a jelentés sablonját. Használja az ehhez letöltött Excel-fájlt.  
6. Kattintson az Új elemre.
7. Kattintson a Fájlra.
8. Zárja be a lapot.
9. A Sablon mezőben adjon meg vagy válasszon ki egy értéket.
    * Letöltött sablon kijelölése  
10. Kattintson az OK gombra.
    * Adjon hozzá egy új tartományt az Excel-kimenet dinamikus létrehozásához a (felhasználói párbeszédpanelen) kiválasztott számú oszloppal a pénzügyi dimenziókhoz. Az egyes oszlopok minden egyes cellája egy adott pénzügyi dimenzió nevét jelöli.  
11. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
12. A fastruktúrában válassza ki a `Excel\Range` csomópontot.
13. Az Excel tartomány mezőbe írja be a következőt: `DimNames`.
    * DimNames  
14. A Replikálás iránya mezőben válassza a `Horizontal` lehetőséget.
15. Kattintson az OK gombra.
16. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal` csomópontot.
17. Kattintson a Felfelé gombra.
18. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Cell<DimNames>` csomópontot.
19. Válassza a Kivágás parancsot.
20. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal` csomópontot.
21. Kattintson a Beillesztés parancsra.
22. A fastruktúrában bontsa ki a `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal` csomópontot.
23. A fastruktúrában bontsa ki a `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical` csomópontot.
24. A fastruktúrában bontsa ki a `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical` csomópontot.
25. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical` csomópontot.
    * Adjon hozzá egy új tartományt az Excel-kimenet dinamikus létrehozásához a (felhasználói párbeszédpanelen) kiválasztott számú oszloppal a pénzügyi dimenziókhoz. Az egyes oszlopok minden egyes cellája egy adott pénzügyi dimenzió értékét jelöli mindegyik jelentési tranzakcióra.  
26. Kattintson a Tartomány hozzáadása lehetőségre.
27. Az Excel tartomány mezőbe írja be a következőt: `DimValues`.
    * DimValues  
28. A Replikálás iránya mezőben válassza a `Horizontal` lehetőséget.
29. Kattintson az OK gombra.
30. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<DimValues>` csomópontot.
31. Válassza a Kivágás parancsot.
32. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal` csomópontot.
33. Kattintson a Beillesztés parancsra.
34. A fastruktúrában bontsa ki a `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal` csomópontot.

## <a name="map-format-elements-to-data-sources"></a>Formátum-összetevők leképezése az adatforrásokhoz

1. Kattintson a Hozzárendelés fülre.
2. A fastruktúrában bontsa ki a `model: Data model Financial dimensions sample model` csomópontot.
3. A fastruktúrában bontsa ki a `model: Data model Financial dimensions sample model\Journal: Record list` csomópontot.
4. A fastruktúrában bontsa ki a `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list` csomópontot.
5. A fastruktúrában bontsa ki a `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list` csomópontot.
6. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal\Cell<DimValues>` csomópontot.
7. A fastruktúrában válassza ki a `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String` csomópontot.
8. Kattintson a Kötés gombra.
9. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Range<DimValues>: Horizontal` csomópontot.
10. A fastruktúrában válassza ki a `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list` csomópontot.
11. Kattintson a Kötés gombra.
12. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Credit>` csomópontot.
13. A fastruktúrában válassza ki a `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real` csomópontot.
14. Kattintson a Kötés gombra.
15. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Debit>` csomópontot.
16. A fastruktúrában válassza ki a `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real` csomópontot.
17. Kattintson a Kötés gombra.
18. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<Currency>` csomópontot.
19. A fastruktúrában válassza ki a `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String` csomópontot.
20. Kattintson a Kötés gombra.
21. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransDate>` csomópontot.
22. A fastruktúrában válassza ki a `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date` csomópontot.
23. Kattintson a Kötés gombra.
24. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransVoucher>` csomópontot.
25. A fastruktúrában válassza ki a `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String` csomópontot.
26. Kattintson a Kötés gombra.
27. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical\Cell<TransBatch>` csomópontot.
28. A fastruktúrában válassza ki a `model: Data model Financial dimensions sample model\Journal: Record list\Batch: String` csomópontot.
29. Kattintson a Kötés gombra.
30. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Range<TransactionLine>: Vertical` csomópontot.
31. A fastruktúrában válassza ki a `model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list` csomópontot.
32. Kattintson a Kötés gombra.
33. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical\Cell<Batch>` csomópontot.
34. A fastruktúrában válassza ki a `model: Data model Financial dimensions sample model\Journal: Record list\Batch: String` csomópontot.
35. Kattintson a Kötés gombra.
36. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Range<JournalLine>: Vertical` csomópontot.
37. A fastruktúrában válassza ki a `model: Data model Financial dimensions sample model\Journal: Record list` csomópontot.
38. Kattintson a Kötés gombra.
39. A fastruktúrában bontsa ki a `model: Data model Financial dimensions sample model\Dimensions setting: Record list` csomópontot.
40. A fastruktúrában válassza ki a `model: Data model Financial dimensions sample model\Dimensions setting: Record list\Code: String` csomópontot.
41. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal\Cell<DimNames>` csomópontot.
42. Kattintson a Kötés gombra.
43. A fastruktúrában válassza ki a `model: Data model Financial dimensions sample model\Dimensions setting: Record list` csomópontot.
44. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Range<DimNames>: Horizontal` csomópontot.
45. Kattintson a Kötés gombra.
46. A fastruktúrában válassza ki a `Excel = "SampleFinDimWsReport"\Cell<CompanyName>` csomópontot.
47. A fastruktúrában válassza ki a `model: Data model Financial dimensions sample model\Company: String` csomópontot.
48. Kattintson a Kötés gombra.
49. Kattintson a Mentés gombra.
50. Zárja be a lapot.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
