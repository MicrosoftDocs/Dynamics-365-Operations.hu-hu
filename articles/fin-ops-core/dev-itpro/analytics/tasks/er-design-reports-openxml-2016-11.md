---
title: ER – Az OPENXML formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése (2016. november)
description: Ez a témakör azt ismerteti, hogyan lehet létrehozni egy olyan új Elektronikus jelentéskészítési konfigurációt, amely egy sablont tartalmaz az elektronikus dokumentumok OPENXML-formátumú előállításához.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERModelGroupByFunctionEditor, VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0f23748f6f1d2c3045b1dc69d8e46821f67da593
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944268"
---
# <a name="er-design-a-configuration-for-generating-reports-in-openxml-format-november-2016"></a>ER – Az OPENXML formátumban létrejövő jelentésekre vonatkozó konfigurációk tervezése (2016. november)

[!include [banner](../../includes/banner.md)]

Ez a témakör leírja, hogy a Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként hozhat létre egy új Elektronikus jelentés (ER) konfigurációt, amely tartalmazza az elektronikus dokumentumok létrehozására vonatkozó sablont az OPENXML formátumban. Ezt a konfigurációt a szállítói kifizetések feldolgozására használják.

Ebben a példában a mintavállalatra, Litware-ra, Inc.-ra vonatkozóan létrehoz egy konfigurációs szolgáltatót. Ezeket a lépéseket a GBSI vállalatban hajthatja végre.

Hajtsa végre az alábbi lépéseket: először hajtsa végre a „Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit. Egy Excel-fájllal is rendelkeznie kell, amelyet importálni kell a sablon létrehozásakor. Ez a fájl a [Kifizetési jelentés sablonja](https://download.microsoft.com/download/3/f/0/3f0658b2-042c-43cf-a776-0f4c7f7cfe4e/SampleVendPaymWsReport.xlsx) dokumentumból érhető el.


## <a name="upload-the-payments-data-model-configuration"></a>A Fizetési adatmodell-konfiguráció feltöltése
1. A navigációs ablakban nyissa meg a **Modulok > Szervezeti felügyelet > Munkaterületek >elektronikus jelentéskészítés** lehetőséget.
2. A listában jelölje be a konfigurációs szolgáltatót a Litware, Inc. minta vállalatra vonatkozóan. Ha nem látja a konfigurációs szolgáltatót, először el kell végeznie a [Konfigurációszolgáltatók létrehozása, és megjelölésük aktívként](er-configuration-provider-mark-it-active-2016-11.md) eljárásban szereplő lépéseket.
3. Válassza ki az **Aktív beállítása** elemet.
4. Válassza ki a **Tárházak** lehetőséget. Ha rendelkezésre áll, válassza ki az üzemi erőforrások típusának tárolóját. Ha rendelkezésre áll, hagyja ki a következő, az új tárház létrehozására vonatkozó lépéseket.  
5. A **Hozzáadás** gombra kattintva nyissa meg a legördülő párbeszédpanelt.
6. A **Konfiguráció tárházának típusa** mezőbe írja be a `Operations resourcesdd` értéket.
7. Válassza a **Tárház létrehozása** lehetőséget.
8. Válassza ki az **OK** lehetőséget.
9. Válassza ki a **Megnyitás** lehetőséget.
10. A fastruktúrában válassza ki a **Fizetési modell** lehetőséget.
11. Válassza az **Importálás** lehetőséget. Ezen adatmodell importálása. Ezt a rendszer az új konfigurációban szereplő adatforrásként használja. Hagyja ki ezt a lépést, ha ezt a konfigurációt már importálta.  
12. Válassza ki az **Igen** lehetőséget.
13. Zárja be a lapokat, amíg vissza nem tér az elektronikus jelentés oldalára.

## <a name="create-a-new-format-configuration"></a>Új formátumkonfiguráció létrehozása
1. Válassza a **Jelentéskészítési konfigurációk** elemet.
2. A fastruktúrában válassza ki a **Fizetési modell** lehetőséget.
3. A **Konfiguráció létrehozása** kiválasztásával megnyithatja a legördülő párbeszédablakot.
4. Az **Új** mezőben adja meg a `Format based on data model PaymentModel` értéket. Hozzon létre egy PaymentModel adatmodellen alapuló formátumot.
5. A **Név** mezőbe írja be a `Sample worksheet report` kifejezést. Minta munkalap jelentés  
6. A **Leírás** mezőbe írja be a `Sample worksheet report for vendors' payments` értéket. Minta munkalap jelentés a szállítók kifizetéseihez.  
7. Az **Adatmodell mezőben** adjon meg vagy válasszon ki egy értéket. Válassza ki a **CustomerCreditTransferInitiation** definíciót.  
8. Válassza a **Konfiguráció létrehozása** lehetőséget.

## <a name="design-a-new-document-in-openxml-worksheet-format"></a>Új dokumentum tervezése az OPENXML munkalapformátumban
1. A fastruktúrában válassza ki a **Fizetési modell\Minta munkalap jelentés** lehetőséget.
2. Válassza a **Tervező** lehetőséget.
3. A műveleti ablaktáblán válassza az **Importálás** lehetőséget.
4. Válassza az **Importálás az Excel programból** lehetőséget.
5. **Mellékletek** kiválasztása. A meglévő Excel dokumentum sablonként történő csatolása.  
6. Válassza az **Új** lehetőséget.
7. Válassza a **Fájl** lehetőséget. Mutasson a meglévő Excel-fájlra.  
8. Zárja be a lapot.
9. A **Sablon** mezőben adjon meg vagy válasszon ki egy értéket. Válassza ki a sablonként használandó csatolt Excel-fájlt.  
10. Válassza ki az **OK** lehetőséget. Vegye figyelembe, hogy az ER-formátum összetevőit a rendszer a hivatkozó Microsoft Excel-dokumentum (más néven tartományok) struktúráján alapuló tervezési formátumban hozta létre.  

## <a name="create-a-new-data-source-to-calculate-totals-by-currency-codes"></a>Egy új adatforrás létrehozása a pénznemkódok alapján történő összesítés kiszámításához
1. Válassza a **Leképezések** lapot.
2. Válassza a **Gyökér hozzáadása** lehetőséget a legördülő párbeszédpanel megnyitásához.
3. A fastruktúrában válassza ki a **Funkciók\Csoportosítás alapja** lehetőséget.
4. A **Név** mezőbe írja be a `PaymentByCurrency` kifejezést.
5. Válassza a **Csoport szerkesztési szempontja** lehetőséget.
6. A fastruktúrában bontsa ki a **modell** lehetőséget, majd válassza a **model\Payments** lehetőséget.
7. Válassza a **Mező hozzáadása** lehetőséget.
8. Válassza a **Csoportosítandó** lehetőséget
9. A fastruktúrában bontsa ki a **model\Payments** lehetőséget, majd válassza a **model\Payments\Currency** lehetőséget.
10. Válassza a **Mező hozzáadása** lehetőséget.
11. Válassza a **Csoportosított mezők** lehetőséget.
12. A fastruktúrában válassza ki a **Modell\Kifizetések\Rendelkezésben megadott összeg (InstructedAmount)** lehetőséget.
13. Válassza a **Mező hozzádása** majd válassza **Összesítési mezők** lehetőséget.
14. Válassza ki valamelyik lehetőséget a **Módszer** mezőben. Válassza az **Összeg aggregáció** funkciót.  
15. A **Név** mezőbe írja be a `TotalInstructuredAmount` kifejezést.
16. Válassza a **Mentés** lehetőséget.
17. Zárja be a lapot.
18. Válassza ki az **OK** lehetőséget.

## <a name="map-format-components-to-data-sources"></a>Formátum-összetevők leképezése az adatforrásokhoz
1. A fastruktúrában válassza ki a **Modell\Kifizetések\Kezdeményező fél(InitiatingParty)\Név** és **Excel\ReportHeader\CompanyName** lehetőséget.
2. Válassza a **Bind** elemet.
3. A fastruktúrában bontsa ki a **modell\Kifizetések\Hitelező\Azonosító\Forrásazonosító** és **Excel\PaymLines\VendAccountName** lehetőséget.
4. Válassza a **Bind** elemet.
5. A fában válassza ki a **model\Payments\Creditor\Name** és az **Excel\PaymLines\VendName** lehetőséget.
6. Válassza a **Bind** elemet.
7. A fában válassza ki a **model\Payments\Creditor Agent(CreditorAgent)\Name** és az **Excel\PaymLines\VendName** lehetőséget.
8. Válassza a **Bind** elemet.
9. A fában válassza ki a **model\Payments\Creditor Agent(CreditorAgent)\Routing Number(RoutingNumber)** és az **Excel\PaymLines\RoutingNumber** lehetőséget.
10. Válassza a **Bind** elemet.
11. A fastruktúrában bontsa ki a **model\Payments\Creditor Account(CreditorAccount)\Identification\Number** és az **Excel\PaymLines\AccountNumber** lehetőséget.
12. Válassza a **Bind** elemet.
13. A fastruktúrában válassza ki a **Modell\Kifizetések\Rendelkezésben megadott összeg (InstructedAmount)** és az **Excel\PaymLines\Debit** lehetőséget.
14. Válassza a **Bind** elemet.
15. A fában válassza ki a **model\Payments\Currency** és az **Excel\PaymLines\Currency** lehetőséget.
16. Válassza a **Bind** elemet.
17. A fában válassza ki **a** PaymentByCurrency\grouped\Currency és az **Excel\SummaryLines\SummaryCurrency** lehetőséget.
18. Válassza a **Bind** elemet.
19. A fában válassza ki a **PaymentByCurrency\aggregated\TotalInstructuredAmount** és az **Excel\SummaryLines\SummaryAmount** lehetőséget.
20. Válassza a **Bind** elemet.
21. A fában válassza ki a **PaymentByCurrency** és az **Excel\SummaryLines** elemet.
22. Válassza a **Bind** elemet.
23. A fában válassza ki a **model\Payments** és az **Excel\PaymLines** lehetőséget.
24. Válassza a **Bind** elemet.
25. Kattintson a **Mentés** lehetőségre, majd zárja be az oldalt.

## <a name="use-the-created-configuration-for-payments-processing"></a>A létrehozott konfiguráció használata a fizetések feldolgozásához
1. Válassza az **Állapot módosítása** lehetőséget.
2. Válassza a **Kész** lehetőséget.
3. Válassza ki az **OK** lehetőséget.
4. A navigációs ablaktáblán ugorjon a **Modulok > Kötelezettségek > Fizetés beállítása > Fizetési módok** elemre.
5. A gyorsszűrő használatával keresse meg azokat a rekordokat, ahol a **Fizetési mód** mezőben az **Elektronikus** érték szerepel.
6. Válassza ki a **Szerkesztés** opciót.
7. Bontsa ki a **Fájlformátumok** szakaszt.
8. Válassza az **Igen** beállítást az **Általános elektronikus jelentéskészítés** mezőben.
9. Az **Exportformátum konfigurációja** mezőben adjon meg vagy válasszon ki egy értéket. Válassza ki a **Minta munkalap jelentés** konfigurációt.  
10. Válassza a **Mentés** lehetőséget.
11. Zárja be a lapot.

## <a name="use-the-created-configuration-for-testing-of-payment-journals-processing"></a>A létrehozott konfiguráció használata a Kifizetési naplók feldolgozásának vizsgálatához
1. Anavigációs ablaktáblán válassza a **Modulok > Kötelezettségek > Kifizetések > Kifizetési napló** elemre.
2. Válassza ki az **Új** lehetőséget egy új kifizetési napló létrehozásához.
3. A **Név** mezőbe írja be: **VendPay**.
4. **Sorok** kiválasztása.
5. A **Számla** mezőben adja meg a `GB_SI_000001` értéket.
6. Állítsa a **Terhelést** `1000` értékre.
7. Válassza az **Új** lehetőséget.
8. A **Számla** mezőben adja meg a `GB_SI_000005` értéket.
9. Állítsa a **Terhelést** `2000` értékre.
10. A **Pénznem** mezőben írja be az `EUR` szöveget.
11. Az **Ellenszámla** mezőben adja meg a `GBSI OPER` értékeket.
12. A **Fizetési mód** mezőbe írja be: `Electronic`.
13. Válassza a **Mentés** lehetőséget.
14. **Kifizetések létrehozása** kiválasztása.
15. A **Fizetési mód** mezőbe írja be: `Electronic`.
16. A **Fájlnév** mezőbe írja be a következőt: `Payments`.
17. A **Bankszámla** mezőben írja be a `GBSI OPER` szöveget.
18. Válassza az **OK** parancsot, majd válassza ismét az **OK** elemet. Tekintse át a létrehozott munkalapot, többek között a kifizetési sorok részleteit, valamint az ebben a fizetési üzenetben használt pénznemkódra vonatkozó összegeket is.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
