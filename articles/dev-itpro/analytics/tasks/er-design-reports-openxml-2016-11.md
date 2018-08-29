--- 
title: "ER konfigurációk tervezése jelentések OpenXML-formátumú előállításához"
description: "A következő lépések leírják, hogy a Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre egy új Elektronikus jelentés (ER) konfigurációt, amely tartalmazza az elektronikus dokumentumok létrehozására vonatkozó sablont az OPENXML formátumban."
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
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: b42cfe36c57a9526e585bbad0fcd31ff60b90397
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---
# <a name="design-er-configurations-to-generate-reports-in-openxml-format"></a>ER konfigurációk tervezése jelentések OpenXML-formátumú előállításához

[!include [task guide banner](../../includes/task-guide-banner.md)]

A következő lépések leírják, hogy a Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre egy új Elektronikus jelentés (ER) konfigurációt, amely tartalmazza az elektronikus dokumentumok létrehozására vonatkozó sablont az OPENXML formátumban. Ezt a konfigurációt a szállítói kifizetések feldolgozására használják.



Ebben a példában a mintavállalatra, Litware-ra, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót. Ezeket a lépéseket a GBSI vállalatban hajthatja végre.



Hajtsa végre az alábbi lépéseket: Először hajtsa végre a „Konfiguráció szolgáltatói létrehozása és aktívként történő megjelölése” eljárás lépéseit. Le kell töltenie és mentenie kell a következő Microsoft Excel-fájlt: [Kifizetési jelentés sablonja](https://go.microsoft.com/fwlink/?linkid=862266). 

## <a name="upload-the-payments-data-model-configuration"></a>A Fizetési adatmodell-konfiguráció feltöltése
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
2. A listában jelölje meg a kiválasztott sort.
    * Válassza ki a konfigurációs szolgáltatót a Litware, Inc. minta vállalatra vonatkozóan. Ha nem látja a konfigurációs szolgáltatót, először el kell végeznie a „Konfigurációszolgáltató létrehozása, és megjelölés aktívként” eljárásban szereplő lépéseket.  
3. Kattintson erre: Beállítás aktívként.
4. Kattintson a Tárházak gombra.
    * Ha rendelkezésre áll, válassza ki az üzemi erőforrások típusának tárolóját. Ha rendelkezésre áll, hagyja ki a következő, az új tárház létrehozására vonatkozó lépéseket.  
5. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
6. A Konfiguráció tárházának típusa mezőbe írja be az „Üzemi erőforrások” szöveget.
7. Kattintson a Tárház létrehozása lehetőségre.
8. Kattintson az OK gombra.
9. Kattintson a Megnyitás gombra.
10. A fastruktúrában válassza ki a „Fizetési modell” lehetőséget.
11. Kattintson az Importálás gombra.
    * Ezen adatmodell importálása. Ezt a rendszer az új konfigurációban szereplő adatforrásként használja. Hagyja ki ezt a lépést, ha ezt a konfigurációt már importálta.  
12. Kattintson az Igen gombra.
13. Zárja be a lapot.
14. Zárja be a lapot.

## <a name="create-a-new-format-configuration"></a>Új formátumkonfiguráció létrehozása
1. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
2. A fastruktúrában válassza ki a „Fizetési modell” lehetőséget.
3. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
4. Az Új mezőbe írja be a „PaymentModel modellen alapuló formátum” kifejezést.
    * Hozzon létre egy PaymentModel adatmodellen alapuló formátumot.  
5. A Név mezőbe írja be a „Minta munkalap jelentés” szöveget.
    * Minta munkalap jelentés  
6. A Leírás mezőben írja be a „Minta munkalap jelentés a szállítók kifizetéseihez” szöveget.
    * Minta munkalap jelentés a szállítók kifizetéseihez.  
7. Az Adatmodell mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a „CustomerCreditTransferInitiation” definíciót.  
8. Kattintson a Konfiguráció létrehozása lehetőségre.

## <a name="design-a-new-document-in-openxml-worksheet-format"></a>Új dokumentum tervezése az OPENXML munkalapformátumban
1. A fastruktúrában válassza ki a „Fizetési modell\Minta munkalap jelentés” lehetőséget.
2. Kattintson a Tervező pontra.
3. A Művelet panelen kattintson az Importálás gombra.
4. Kattintson az Importálás a Microsoft Excel programból lehetőségre.
5. Kattintson a Mellékletek lehetőségre.
    * A meglévő Excel dokumentum sablonként történő csatolása.  
6. Kattintson az Új lehetőségre.
7. Kattintson a Fájlra.
    * Mutasson a meglévő Excel-fájlra.  
8. Zárja be a lapot.
9. A Sablon mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a sablonként használandó csatolt Excel-fájlt.  
10. Kattintson az OK gombra.
    * Vegye figyelembe, hogy az ER-formátum összetevőit a rendszer a hivatkozó Microsoft Excel-dokumentum (más néven tartományok) struktúráján alapuló tervezési formátumban hozta létre.  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a>Egy új adatforrás létrehozása a pénznemkódok alapján történő összesítés kiszámításához
1. Kattintson a Hozzárendelés fülre.
2. Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.
3. A fastruktúrában válassza ki a „Funkciók\Csoportosítás alapja ” lehetőséget.
4. A Név mezőbe írja be a „Kifizetés pénzneme” szöveget.
    * Kifizetés pénzneme  
5. Kattintson a Csoport szerkesztési szempontja lehetőségre.
6. A fában bontsa ki a „model” elemet.
7. A fán válassza ki a következőt: „model\Payments”.
8. Kattintson a Mező hozzáadása a következőhöz lehetőségre.
9. Kattintson a Csoportosítandó lehetőségre.
10. A fában bontsa ki a „model\Payments” elemet.
11. A fastruktúrában válassza ki a „Modell\Kifizetések\Pénznem” lehetőséget.
12. Kattintson a Mező hozzáadása a következőhöz lehetőségre.
13. Kattintson a Csoportosított mezők lehetőségre.
14. A fastruktúrában válassza ki a „Modell\Kifizetések\Rendelkezésben megadott összeg (InstructedAmount)” lehetőséget.
15. Kattintson a Mező hozzáadása a következőhöz lehetőségre.
16. Kattintson az Aggregációs mezők lehetőségre.
17. Válassza ki valamelyik lehetőséget a Módszer mezőben.
    * Válassza az Összeg aggregáció funkciót.  
18. A Név mezőbe írja be a „TotalInstructuredAmount” szöveget.
    * TotalInstructuredAmount  
19. Kattintson a Mentés gombra.
20. Zárja be a lapot.
21. Kattintson az OK gombra.

## <a name="map-format-components-to-data-sources"></a>Formátum-összetevők leképezése az adatforrásokhoz
1. A fában bontsa ki a „model” elemet.
2. A fában bontsa ki a „model\Payments” elemet.
3. A fastruktúrában bontsa ki a „Modell\Kifizetések\Kezdeményező fél(InitiatingParty)” lehetőséget.
4. A fastruktúrában válassza ki a „Modell\Kifizetések\Kezdeményező fél(InitiatingParty)\Név” lehetőséget.
5. A fában bontsa ki az „Excel\Jelentésfejléc” elemet.
6. A fában bontsa ki az „Excel\ReportHeader\CompanyName” elemet.
7. Kattintson a Kötés gombra.
8. A fában bontsa ki a „model\Payments= Transactions\Creditor” elemet.
9. A fastruktúrában bontsa ki a „modell\Kifizetések\Hitelező\Azonosító” lehetőséget.
10. A fastruktúrában bontsa ki a „modell\Kifizetések\Hitelező\Azonosító\Forrásazonosító” lehetőséget.
11. A fában bontsa ki az „Excel\PaymLines” elemet.
12. A fában bontsa ki az „Excel\PaymLines\VendAccountName” elemet.
13. Kattintson a Kötés gombra.
14. A fán válassza ki „model\Kifizetések = Transactions\Creditor\Name” pontot.
15. A fában válassza ki az „Excel\PaymLines\VendName” elemet.
16. Kattintson a Kötés gombra.
17. A fastruktúrában bontsa ki a „modell\kifizetések\Hitelező ügynöke(CreditorAccount)” lehetőséget.
18. A fastruktúrában válassza ki a „modell\kifizetések\Hitelező ügynöke(CreditorAccount)\Név” lehetőséget.
19. A fában válassza ki az „Excel\PaymLines\Bank” elemet.
20. Kattintson a Kötés gombra.
21. A fastruktúrában válassza ki „modell\Kifizetések\Hitelező ügynöke(CreditorAgent)\Útvonalszám(RoutingNumber)” lehetőséget.
22. A fában válassza ki az „Excel\PaymLines\RoutingNumber” elemet.
23. Kattintson a Kötés gombra.
24. A fában bontsa ki a következőt: „model\Payments\Creditor Account(CreditorAccount)”.
25. A fában bontsa ki a következőt: „model\Payments\Creditor Account(CreditorAccount)”.
26. A fastruktúrában válassza ki a „modell\Kifizetések\Hitelező számlája(CreditorAccount)\Azonosító\Szám” lehetőséget.
27. A fában válassza ki az „Excel\PaymLines\AccountNumber” elemet.
28. Kattintson a Kötés gombra.
29. A fastruktúrában válassza ki a „Modell\Kifizetések\Rendelkezésben megadott összeg (InstructedAmount)” lehetőséget.
30. A fában válassza ki az „Excel\PaymLines\Tartozik” elemet.
31. Kattintson a Kötés gombra.
32. A fában bontsa ki a „model\Payments= Transactions\Creditor” elemet.
33. A fában bontsa ki a következőt: „model\Payments\Creditor Account(CreditorAccount)”.
34. A fastruktúrában bontsa ki a „modell\kifizetések\Hitelező ügynöke(CreditorAccount)” lehetőséget.
35. A fastruktúrában válassza ki a „Modell\Kifizetések\Pénznem” lehetőséget.
36. A fában válassza ki az „Excel\PaymLines\Pénznem” elemet.
37. Kattintson a Kötés gombra.
38. Bontsa ki a fastruktúrában a „Kifizetés pénzneme” lehetőséget.
39. Bontsa ki a fastruktúrában a „Kifizetés pénzneme\Csoportosítva” lehetőséget.
40. A fastruktúrában válassza ki a „Kifizetés pénzneme\Csoportosítva\Pénznem” lehetőséget.
41. A fában bontsa ki az „Excel\SummaryLines” elemet.
42. A fában válassza ki az „Excel\SummaryLines\SummaryCurrency” elemet.
43. Kattintson a Kötés gombra.
44. Bontsa ki a fastruktúrában a„Kifizetés pénzneme\Összesített” lehetőséget.
45. A fastruktúrában válassza ki a „Kifizetés pénzneme\Összesített\TotalInstructuredAmount” lehetőséget.
46. A fában válassza ki az „Excel\SummaryLines\SummaryAmount” elemet.
47. Kattintson a Kötés gombra.
48. A fastruktúrában válassza ki a „Kifizetés pénzneme” lehetőséget.
49. A fastruktúrában válassza ki a következőt: „Excel\SummaryLines”.
50. Kattintson a Kötés gombra.
51. A fán válassza ki a következőt: „model\Payments”.
52. A fában válassza ki az „Excel\PaymLines” elemet.
53. Kattintson a Kötés gombra.
54. Kattintson a Mentés gombra.
55. Zárja be a lapot.

## <a name="use-the-created-configuration-for-payments-processing"></a>A létrehozott konfiguráció használata a fizetések feldolgozásához
1. Kattintson az Állapot módosítása elemre.
2. Kattintson a Befejezés gombra.
3. Kattintson az OK gombra.
4. Zárja be a lapot.
5. Zárja be a lapot.
6. Ugorjon a Kötelezettségek > Kifizetés beállítása > Fizetési módok pontra.
7. A gyorsszűrő használatával keresse meg azokat a rekordokat, ahol a Fizetési mezőben az „Elektronikus” érték szerepel.
    * Elektronikus  
8. Kattintson a Szerkesztés lehetőségre.
9. Bontsa ki a Fájlformátumok szakaszt.
10. Válassza az Igen beállítást az Általános elektronikus jelentéskészítés mezőben.
11. Az Exportformátum konfigurációja mezőben adjon meg vagy válasszon ki egy értéket.
    * Válassza ki a "Minta munkalap jelentés" konfigurációt.  
12. Kattintson a Mentés gombra.
13. Zárja be a lapot.

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a>A létrehozott konfiguráció használata a Kifizetési naplók feldolgozásának vizsgálatához
1. Ugorjon a Kötelezettségek > Fizetési beállítás > Fizetési napló pontra.
2. Kattintson az Új lehetőségre.
    * Hozzon létre egy új kifizetési naplót.  
3. A Név mezőbe írja be: „VendPay”.
    * VendPay  
4. Kattintson a Sorok pontra.
5. A Számla mezőben adja meg a „GB_SI_000001” értékeket.
    * GB_SI_000001  
6. Állítsa a Terhelést „1000” értékre.
7. Kattintson az Új lehetőségre.
8. A Számla mezőben adja meg a „GB_SI_000005” értékeket.
    * GB_SI_000005  
9. Állítsa a Terhelést „2000” értékre.
10. A Pénznem mezőben írja be az „EUR” szöveget.
    * HUF  
11. Az Ellenszámla mezőben adja meg a „GBSI OPER” értékeket.
    * GBSI MŰV.  
12. A Fizetési mód mezőbe írja be az „Elektronikus” szöveget.
    * Elektronikus  
13. Kattintson a Mentés gombra.
14. Kattintson a Kifizetések létrehozása elemre.
15. A Fizetési mód mezőbe írja be az „Elektronikus” szöveget.
    * Elektronikus  
16. A Fájlnév mezőbe írja be a következőt: „Fizetések”.
    * Például írja be a Kifizetések szöveget.  
17. A Bankszámla mezőben írja be a „GBSI OPER” szöveget.
    * GBSI MŰV.  
18. Kattintson az OK gombra.
19. Kattintson az OK gombra.
    * Tekintse át a létrehozott munkalapot, többek között a kifizetési sorok részleteit, valamint az ebben a fizetési üzenetben használt pénznemkódra vonatkozó összegeket is.  


