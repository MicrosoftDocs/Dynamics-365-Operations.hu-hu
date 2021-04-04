---
title: ER Dokumentumkezelési fájlok használata formátumkimenetekben (2. rész – Adatmodell kibővítése)
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni egy Elektronikus jelentéskészítési (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatára az ER-kimenetben. (2. rész)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b47c35790ce04a494b6c58f6e04fa9b829d2ab93
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559773"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2---extend-data-model"></a>ER Dokumentumkezelési fájlok használata formátumkimenetekben (2. rész – Adatmodell kibővítése)

[!include [banner](../../includes/banner.md)]

A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben. Ezeket a lépéseket bármely vállalatban végrehajthatja.

A lépések végrehajtásához először végre kell hajtania az „ER Dokumentumkezelési fájlok használata formátumkimenetekben (1. rész: Adatmodell előkészítése)” feladat-útmutató lépéseit.

Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a>Az adatmodell kibővítése a benne található Dokumentumkezelés fájlok megjelenítéséhez
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
2. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
3. A fastruktúrában bontsa ki a „Vevői számlamodell” lehetőséget.
4. A fastruktúrában válassza ki a következőt: Vevői számlamodell\Vevői számlamodell (egyéni).
5. Kattintson a Tervező pontra.
6. A fastruktúrában válassza ki a „Vevői számla (InvoiceCustomer)” lehetőséget.
    * Ki fogjuk terjeszteni ezt az adatmodellt, hogy az összes olyan fájlt megjelenítsük benne, amelyet olyan értékesítési rendeléshez mellékeltek, amely egy elektronikusan feldolgozott számlához kapcsolódik.  
7. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
8. A Név mezőbe írja be a következőt: „Számlamellékletek”.
    * Számlamellékletek  
9. A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.
10. Kattintson a Hozzáadás gombra.
11. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
12. A Név mezőbe írja be a következőt: „Fájltartalom”.
    * Fájl tartalma  
13. A Cikktípus mezőben válassza ki a „Tároló” lehetőséget.
14. Kattintson a Hozzáadás gombra.
15. Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.
16. A Név mezőbe írja be a következőt: „Fájlnév”.
    * Fájlnév  
17. A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.
18. Kattintson a Hozzáadás gombra.

## <a name="map-new-data-model-elements-to-data-sources"></a>Az új adatmodellelemek leképezése adatforrásokra
1. Kattintson a Modell hozzárendelése adatforráshoz gombra.
2. A gyorsszűrő használatával keresse meg azokat a rekordokat, ahol a Definíció mezőben az „InvoiceCustomer” érték szerepel.
    * InvoiceCustomer  
    * Az új modellelemeket hozzá fogjuk rendelni a megfelelő adatforrásokhoz.  
3. Kattintson a Tervező pontra.
4. A fastruktúrában válassza ki a „Számlamellékletek” lehetőséget.
5. A fastruktúrában bontsa ki a „Számlamellékletek” lehetőséget.
6. A fastruktúrában válassza ki a „Számlamellékletek\Fájlnév” lehetőséget.
7. Kattintson a Szerkesztés lehetőségre.
8. A Képlet mezőbe írja be következőt: 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'  
9. Kattintson a Mentés gombra.
10. Zárja be a lapot.
11. A fastruktúrában válassza ki a „Számlamellékletek\Fájltartalom” lehetőséget.
12. Kattintson a Szerkesztés lehetőségre.
13. A Képlet mezőbe írja be következőt: 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'  
14. Kattintson a Mentés gombra.
15. Zárja be a lapot.
16. A fastruktúrában válassza ki a „Számlamellékletek” lehetőséget.
17. Kattintson a Szerkesztés lehetőségre.
18. A Képlet mezőbe írja be következőt: 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'  
19. Kattintson a Mentés gombra.
20. Zárja be a lapot.
21. Kattintson a Mentés gombra.
22. Zárja be a lapot.
23. Zárja be a lapot.
24. Zárja be a lapot.
25. Kattintson az Állapot módosítása elemre.
26. Kattintson a Befejezés gombra.
27. Kattintson az OK gombra.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]