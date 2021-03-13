---
title: ER Pénzügyi dimenziók használata adatforrásként (2. rész – Modell hozzárendelése)
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni egy Elektronikus jelentési (ER) modellt, amely a pénzügyi dimenziókat használja az ER-jelentések adatforrásaként. (2. rész)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 02c730d08c411e736a7f8b9e7bad3d6a18cb8e6a
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093237"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-2---model-mapping"></a>ER Pénzügyi dimenziók használata adatforrásként (2. rész – Modell hozzárendelése)

[!include [banner](../../includes/banner.md)]

A következő lépések leírják, hogy egy rendszergazda vagy az elektronikus jelentések fejlesztője szerepkörhöz hozzárendelt felhasználó miként konfigurálhat egy elektronikusjelentés-modellt (ER-modell) a pénzügyi dimenzió használatához az ER-jelentések adatforrásaként. Ezeket a lépéseket bármely vállalatban végrehajthatja.

A lépések végrehajtásához először hajtsa végre az „ER Pénzügyi dimenziók használata adatforrásként (1. rész: Adatmodell tervezése)” eljárás lépéseit.


## <a name="add-required-data-sources-to-model-mapping"></a>Kötelező adatfoforrások hozzáadása a modellek hozzárendeléseihez
1. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
2. A fastruktúrában válassza a „Pénzügyi dimenziók mintamodell” szöveget.
3. Kattintson a Tervező pontra.
4. Kattintson a Modell hozzárendelése adatforráshoz gombra.
5. Kattintson az Új lehetőségre.
6. A Definíció mezőben válassza a Bejegyzés lehetőséget.
7. A Név mezőbe írja be a következőt: „Dimenzióadatok leképezése”.
8. A Leírás mezőbe írja be a következőt: „Dimenzióadatok leképezése”.
9. Kattintson a Mentés gombra.
10. Kattintson a Tervező pontra.
11. A fastruktúrában válassza ki a következőt: „Dynamics 365 for Operations\Tábla” csomópont.
12. Kattintson a Gyökér hozzáadása gombra.
13. A Név mezőbe írja be a Vállalat szót.
14. Írja be a Tábla mezőbe a „CompanyInfo” szöveget.
15. Kattintson az OK gombra.
16. A fastruktúrában válassza a „Funkciók\Pénzügyi dimenziók részletei” elemet.
17. Kattintson a Gyökér hozzáadása gombra.
    * Az adatforrás meghatározza, hogy a rendszer hogy definiálja a pénzügyi dimenziók hatókörét az összes olyan jelentés esetében, amely ezt a modellt használja adatforrásként.  
18. Írjon be egy értéket a Név mezőbe.
19. Válassza az Igen lehetőséget a Dimenziók kérése mezőben.
    * Válassza az Igen lehetőséget, ha engedélyezni szeretné a felhasználó számára a dimenziók futásidejű kiválasztását a Felhasználó párbeszédpanelen. Ha a beállítása Nem, a rendszer alapértelmezetten az aktuális példány összes pénzügyi dimenzióját használja.  
20. A Pénzügyi dimenziók kiválasztása mezőben válassza ki a „Jogi személy” lehetőséget.
    * Válassza az Összes lehetőséget, ha lehetővé szeretné tenni a felhasználó számára a kívánt dimenziók kiválasztását az aktuális példányra a Keresés mezőben.  Válassza a Jogi személy lehetőséget, ha lehetővé szeretné tenni a felhasználó számára a dimenziók kiválasztását a vállalathoz a Keresés mezőben.  Válassza ki a Dimenzió lehetőséget annak az engedélyezéséhez a felhasználó számára, hogy dimenziókat válasszon ki egyetlen dimenziókészlet használatával.  
21. Válassza az Igen lehetőséget a Fő számla kérése mezőben.
    * A „Fő számla kérése” lehetőséget állítsa Igen értékre, ha engedélyezni szeretné a felhasználók számára a fő számla kiválasztását a dimenziók listájának részeként.   Ha a beállítása Nem, a fő számla nem lesz része a dimenziók listájának, és „A fő számla kötelező” beállítás engedélyezve van. Ha „A fő számla kötelező” beállítása Igen, a fő számla része lesz a dimenziók listájának, a felhasználói kiválasztástól függetlenül.  
22. Kattintson az OK gombra.
![Elektronikus jelentéskészítés – modell-leképezés tervező oldal](../media/er-financial-dimensions-guides-model-mapping1.png)
23. A fastruktúrában válassza ki a következőt: „Dynamics 365 for Operations\Tábla rekordjai” csomópont.
24. Kattintson a Gyökér hozzáadása gombra.
25. A Név mezőbe írja be a „LedgerJournal” szöveget.
26. Válassza az Igen lehetőséget a Lekérdezés kérése mezőben.
27. Írja be a Tábla mezőbe a „LedgerJournalTable” szöveget.
28. Kattintson az OK gombra.
![Elektronikus jelentéskészítés – modell-leképezés tervező oldal](../media/er-financial-dimensions-guides-model-mapping2.png)

## <a name="map-data-model-elements-to-added-data-sources"></a>Adatmodell-elemek leképezése a hozzáadott adatforrásokra
1. A fastruktúrában bontsa ki ezt: „Napló”.
2. A fastruktúrában bontsa ki ezt: „Napló\Tranzakció”.
3. A fastruktúrában bontsa ki ezt: „Napló\Tranzakció\Dimenzióadat”.
4. A fastruktúrában bontsa ki a következőt: „Dimenziók beállítása”.
5. A fastruktúrában bontsa ki a következőt: „LedgerJournal”.
6. A fastruktúrában bontsa ki a „LedgerJournal\<Kapcsolatok” elemet.
7. A fastruktúrában bontsa ki a „LedgerJournal\<Kapcsolatok\LedgerJournalTrans” elemet.
8. A fastruktúrában válassza ki a „LedgerJournal\<Kapcsolatok\LedgerJournalTrans\Bizonylat” elemet.
9. A fastruktúrában válassza ki a „Napló\Tranzakció\Bizonylat” elemet.
10. Kattintson a Kötés gombra.
11. A fastruktúrában válassza ki a „LedgerJournal\<Kapcsolatok\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)” elemet.
    * Ne feledje, hogy a pénzügyi dimenziókhoz tartozó minden egyes hivatkozáshoz, amely például a LedgerDimension elemhez van beállítva, tartozik egy adatforráscikk (LedgerDimension.Dimension). Ezt az adatforráselem a dimenziókészlet pénzügyi dimenzióit rekordlistakánt kínálja.  
12. A fastruktúrában bontsa ki a „LedgerJournal\<Kapcsolatok\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)” elemet.
13. A fastruktúrában bontsa ki a „LedgerJournal\<Kapcsolatok\LedgerJournalTrans\Account.Dimension (LedgerDimension.Dimension)\Fő számla és dimenziók” elemet.
14. A fastruktúrában bontsa ki a „LedgerJournal\<Kapcsolatok\LedgerJournalTrans\Account.Dimension (LedgerDimension.Dimension)\Fő számla és dimenziók\Érték” elemet.
15. A fastruktúrában bontsa ki a „LedgerJournal\<Kapcsolatok\LedgerJournalTrans\Account.Dimension (LedgerDimension.Dimension)\Fő számla és dimenziók\Definíció” elemet.
16. A fastruktúrában válassza ki a „LedgerJournal\<Kapcsolatok\LedgerJournalTrans\Account.Dimension (LedgerDimension.Dimension)\Fő számla és dimenziók\Név” elemet.
17. A fastruktúrában válassza ki ezt: „Napló\Tranzakció\Dimenzióadat\Név”.
18. Kattintson a Kötés gombra.
19. A fastruktúrában válassza ki a „LedgerJournal\<Kapcsolatok\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Fő számla és dimenziók\Érték\Leírás” elemet.
20. A fastruktúrában válassza ki ezt: „Napló\Tranzakció\Dimenzióadat\Leírás”.
21. Kattintson a Kötés gombra.
22. A fastruktúrában válassza ki a „LedgerJournal\<Kapcsolatok\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Fő számla és dimenziók\Érték\Kód” elemet.
23. A fastruktúrában válassza ki ezt: „Napló\Tranzakció\Dimenzióadat\Kód”.
24. Kattintson a Kötés gombra.
25. A fastruktúrában válassza ki a „LedgerJournal\<Kapcsolatok\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Fő számla és dimenziók” elemet.
26. A fastruktúrában válassza ki ezt: „Napló\Tranzakció\Dimenzióadat”.
27. Kattintson a Kötés gombra.
![Elektronikus jelentéskészítés – modell-leképezés tervező oldal](../media/er-financial-dimensions-guides-model-mapping3.png)
28. A fastruktúrában válassza ki a „LedgerJournal\<Kapcsolatok\LedgerJournalTrans\Debit(AmountCurDebit)” elemet.
29. A fastruktúrában válassza ki a „Napló\Tranzakció\Tartozik” elemet.
30. Kattintson a Kötés gombra.
31. A fastruktúrában válassza ki a „LedgerJournal\<Kapcsolatok\LedgerJournalTrans\Date(TransDate)” elemet.
32. A fastruktúrában válassza ki a „Napló\Tranzakció\Dátum” elemet.
33. Kattintson a Kötés gombra.
34. A fastruktúrában válassza ki a „LedgerJournal\<Kapcsolatok\LedgerJournalTrans\Currency(CurrencyCode)” elemet.
35. A fastruktúrában válassza ki a „Napló\Tranzakció\Pénznem” elemet.
36. Kattintson a Kötés gombra.
37. A fastruktúrában válassza ki a „LedgerJournal\<Kapcsolatok\LedgerJournalTrans\Credit(AmountCurCredit)” elemet.
38. A fastruktúrában válassza ki a „Napló\Tranzakció\Követel” elemet.
39. Kattintson a Kötés gombra.
40. A fastruktúrában válassza ki a „LedgerJournal\<Kapcsolatok\LedgerJournalTrans” elemet.
41. A fastruktúrában válassza ki a „Napló\Tranzakció” elemet.
42. Kattintson a Kötés gombra.
43. A fastruktúrában válassza ki a „LedgerJournal\Journal batch number(JournalNum)” elemet.
44. A fastruktúrában válassza ki a „Napló\Köteg” elemet.
45. Kattintson a Kötés gombra.
46. A fastruktúrában válassza ki ezt: „LedgerJournal”.
47. A fastruktúrában válassza ki ezt: „Napló”.
48. Kattintson a Kötés gombra.
49. A fastruktúrában bontsa ki ezt: „Dimenziók”.
50. A fastruktúrában bontsa ki ezt: „Dimenziók\Fő számla és dimenziók”.
51. A fastruktúrában bontsa ki ezt: „Dimenziók\Fő számla és dimenziók\Definíció”.
52. A fastruktúrában válassza ki ezt: „Dimenziók\Fő számla és dimenziók\Definíció\Név”.
53. A fastruktúrában válassza ki a következőt: „Dimenziók beállítása\Kód”.
54. Kattintson a Kötés gombra.
55. A fastruktúrában válassza ki ezt: „Dimenziók\Fő számla és dimenziók\Definíció\Jelentésoszlop neve”.
56. A fastruktúrában válassza ki a következőt: „Dimenziók beállítása\Név”.
57. Kattintson a Kötés gombra.
58. A fastruktúrában válassza ki ezt: „Dimenziók\Fő számla és dimenziók”.
59. A fastruktúrában válassza ki a következőt: „Dimenziók beállítása”.
60. Kattintson a Kötés gombra.
61. A fastruktúrában válassza ki ezt: „Vállalat”.
62. Kattintson a Szerkesztés lehetőségre.
63. Írja be a Company.'find()'.'name()' szöveget az expressionAsStringText mezőbe.
    * Company.'find()'.'name()'  
64. Kattintson a Mentés gombra.
![Elektronikus jelentéskészítés – modell-leképezés tervező oldal](../media/er-financial-dimensions-guides-model-mapping4.png)
65. Zárja be a lapot.
66. Kattintson a Mentés gombra.
67. Zárja be a lapot.

## <a name="complete-this-draft-models-version"></a>Töltse ki a tervezet termékmodell-verziót
1. Zárja be a lapot.
2. Zárja be a lapot.
3. Kattintson az Állapot módosítása elemre.
4. Kattintson a Befejezés gombra.
5. Kattintson az OK gombra.
![Elektronikus jelentéskészítés – modell-leképezés tervező oldal](../media/er-financial-dimensions-guides-model-mapping5.png)
