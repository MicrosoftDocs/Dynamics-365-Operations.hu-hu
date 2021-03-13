---
title: ER-modelleképezések meghatározása és adatforrások kiválasztása hozzájuk
description: Ez a témakör bemutatja, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörű felhasználó miként választhat ki adatforrásokat az Elektronikus jelentéskészítés adatmodellhez.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7fccdda3ac441630836a0d33f78eb04e9cd26d4a
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092110"
---
# <a name="define-er-model-mappings-and-select-data-sources-for-them"></a>ER-modelleképezések meghatározása és adatforrások kiválasztása hozzájuk

[!include [banner](../../includes/banner.md)]

A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörű felhasználó miként választhat ki adatforrásokat az Elektronikus jelentés (ER) adatmodellhez. Az adatforrások a kijelölt adatmodell egyes komponenseihez lesznek kötve a tervezéskor, és futásidőben feltöltik az adatmodellt üzleti adatokkal. Ebben a példában ki fogja választani a meglévő adatok termékmodellt a minta vállalatra vonatkozóan, amelyet az vállalat, a Litware, Inc. mintájára hoztak létre. Hajtsa végre az alábbi lépéseket, először végezze el a „Hozzon létre egy új adatmodell” műveletsorban ismertetett lépéseket.


## <a name="open-the-electronic-reporting-configurations-tree"></a>Az elektronikus jelentéskészítés konfigurációs fa megnyitása
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
2. Kattintson a Jelentéskészítés konfigurációi lehetőségre.

## <a name="insert-a-new-model-mapping"></a>Új modell leképezés beszúrása
1. A fán válassza ki a következőt: „Payments (simplified model)”.
2. Kattintson a Tervező pontra.
3. Kattintson a Modell hozzárendelése adatforráshoz gombra.
4. Kattintson az Új lehetőségre.
    * Ez létrehoz egy új rekordot, amely az adatmodellt leképezi az adatforrásokra. Ebben a példában az adatmodellt a kívánt fizetéstípus adatforrásaira képezi le: a jóváírás-átvitelre.     Lehetséges egynél több hozzárendelés egy adott adatmodellhez. Például létrehozhat leképezést a különböző típusú kifizetésekre, például beszedési megbízások vagy átutalások. Ebben a példában létrehoz egy leképezést jóváírás-átvitelekhez.  
5. A Név mezőbe írja be a „CT mapping” szöveget.
    * CT-leképezés  
6. A Leírás mezőbe írja be a „Payment model mapping CT” szöveget.
    * Fizetési modell leképezési CT  
7. A Definíció mezőbe írja be a „CustomerCreditTransferInitiation” szöveget.
    * CustomerCreditTransferInitiation  
8. ResolveChanges meghatározása.
9. Kattintson a Mentés gombra.

## <a name="define-required-data-sources-for-the-current-model-mapping"></a>Adja meg a szükséges adatforrásokat az aktuális modell-leképezéshez
1. Kattintson a Tervező pontra.
2. A fastruktúrában válassza ki a következőt: „Dynamics 365 for Operations\Tábla rekordjai” csomópont.
3. Kattintson a Gyökér hozzáadása gombra.
    * Adja meg az adatforrást a fizetési tranzakció eléréséhez.  
4. A Név mezőbe írja be a „Transactions” szöveget.
    * Tranzakciók  
5. Írja be a Címke mezőbe, hogy „Tranzakciók”.
    * Tranzakciók  
6. A Súgó mezőbe írja be a "Főkönyvi naplósorok" szöveget.
    * Főkönyvi naplósorok  
7. Válassza az Igen lehetőséget a Lekérdezés kérése mezőben.
    * Válassza az Igen lehetőséget.  
8. Írja be a Tábla mezőbe a „LedgerJournalTrans” szöveget.
    * LedgerJournalTrans  
9. Kattintson az OK gombra.
    * Az aktuális adatmodellhez adatforrásként válassza a LedgerJournalTrans táblát.  
10. A fán válassza ki a „Functions\Calculated mező” lehetőséget.
11. Kattintson a Hozzáadás gombra.
    * Kattintson a Hozzáadás gombra egy új számított mező hozzáadásához.  
12. A Név mezőbe írja be a '$EndToEndID' szöveget.
    * $EndToEndID  
13. Kattintson a Receptúra szerkesztése lehetőségre.
14. A fában válassza ki a 'String\CONCATENATE' lehetőséget.
15. Kattintson a Függvény hozzáadása gombra.
16. A fában bontsa ki a Tranzakciók csomópontot.
17. A fastruktúrában válassza ki a „Transactions\Voucher” lehetőséget.
18. Kattintson az Adatforrás hozzáadása pontra.
19. Adja meg a Képlet mezőben a „CONCATENATE(Transactions.Voucher, "-", ” szöveget.
    * Írja be a [, "-",] kifejezést a képlet végére.  
20. A fában válassza ki a 'String\TEXT' csomópontot.
21. Kattintson a Függvény hozzáadása gombra.
22. A fán válassza ki a „Transactions\Record-ID(RecId)” lehetőséget.
23. Kattintson az Adatforrás hozzáadása pontra.
24. Adja meg a Képlet mezőben a „CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))” szöveget.
    * Írja be a [))] kifejezést a képlet végére.  
25. Kattintson a Mentés gombra.
    * Győződjön meg arról, hogy nincsenek hibák a létrehozott képletben. Lásd a receptúra-szerkesztő vezérlőelem alatti HIBÁK fület.  
26. Zárja be a lapot.
27. Kattintson az OK gombra.
    * A számított mező hozzáadása az adatforráshoz.  
28. Kattintson a Hozzáadás gombra.
    * Kattintson a Hozzáadás gombra egy új számított mező hozzáadásához.  
29. A Név mezőbe írja be a '$Amount' szöveget.
    * $Összeg  
30. Kattintson a Receptúra szerkesztése lehetőségre.
31. A fában bontsa ki a Tranzakciók csomópontot.
32. A fán válassza ki a „Transactions\Debit(AmountCurDebit)” lehetőséget.
33. Kattintson az Adatforrás hozzáadása pontra.
34. Adja meg a Képlet mezőben a „Transactions.AmountCurDebit - ” szöveget.
    * Írja be a [ - ] kifejezést a képlet végére.  
35. A fán válassza ki a „Transactions\Credit(AmountCurCredit)” lehetőséget.
36. Kattintson az Adatforrás hozzáadása pontra.
37. Kattintson a Mentés gombra.
38. Zárja be a lapot.
39. Kattintson az OK gombra.
    * Ez a $Amount számított mezőt hozzáadja a kijelölt adatforráshoz az aktuális adatmodell számára.  
40. A fastruktúrában válassza ki a „Transactions\$Amount” lehetőséget.
41. A fában bontsa ki a Tranzakciók csomópontot.
42. A fában bontsa ki a „Tranzakciók\$Összeg” elemet.
43. A fában bontsa ki vagy csukja össze a „Tranzakciók” elemet.
44. A fastruktúrában válassza ki a következőt: „Dynamics 365 for Operations\Tábla rekordjai” csomópont.
45. Kattintson a Gyökér hozzáadása gombra.
    * Adja meg az adatforrást a vállalati bankszámla részleteihez való hozzáféréshez.  
46. A Név mezőbe írja be a BankAccount szöveget.
    * Bankszámla  
47. Írja be a Címke mezőbe, hogy „Bank Account”.
    * Bankszámla  
48. Írja be a Súgó mezőbe, hogy „Bank Account”.
    * Bankszámla  
49. Válassza az Igen lehetőséget a Lekérdezés kérése mezőben.
    * Válassza az Igen lehetőséget.  
50. Írja be a Tábla mezőbe a „BankAccountTable” szöveget.
    * BankAccountTable  
51. Kattintson az OK gombra.
    * Az aktuális adatmodellhez adatforrásként válassza a BankAccountTable táblát.  
52. Kattintson a Gyökér hozzáadása gombra.
    * Adja meg az adatforrást a vállalati követelményekhez való hozzáféréshez.  
53. A Név mezőbe írja be a Vállalat szót.
    * Cég  
54. A Címke mezőbe írjon be egy értéket.
    * Cégadatok  
55. A Súgó mezőbe írja be a Vállalati információk szöveget.
    * Cégadatok  
56. Válassza az Igen lehetőséget a Lekérdezés kérése mezőben.
    * Válassza az Igen lehetőséget.  
57. Írja be a Tábla mezőbe a „CompanyInfo” szöveget.
    * CompanyInfo  
58. Kattintson az OK gombra.
    * Az aktuális adatmodellhez adatforrásként válassza a CompanyInfo táblát.  
59. A fán válassza ki a „Functions\Calculated mező” lehetőséget.
60. Kattintson a Gyökér hozzáadása gombra.
    * Számított mező beszúrása új adatforrásként.  
61. A Név mezőbe írja be az „ProcessingDateTime” szöveget.
    * ProcessingDateTime  
62. A Címke mezőbe írja be a 'Feldolgozás dátuma és időpontja' szöveget.
    * Feldolgozás dátuma és időpontja  
63. Kattintson a Receptúra szerkesztése lehetőségre.
64. A fastruktúrán jelölje be a „Dátum/idő\SESSIONNOW” elemet.
65. Kattintson a Függvény hozzáadása gombra.
66. Kattintson a Mentés gombra.
67. Zárja be a lapot.
68. Kattintson az OK gombra.
    * Adja hozzá a ProcessingDateTime számított mezőt az aktuális adatmodellhez adatforrásként.  
69. Kattintson a Mentés gombra.
70. Zárja be a lapot.
71. Zárja be a lapot.
72. Zárja be a lapot.

