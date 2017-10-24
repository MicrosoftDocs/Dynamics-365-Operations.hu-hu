--- 
title: "Adatmodell kibővítése dokumentumkezelési fájlok használatára formátumkimenetekben elektronikus jelentéskészítéshez (ER)"
description: "A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f3d494cc83b273eef071b23d0948b283ba85c17e
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="extend-data-model-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a>Adatmodell kibővítése dokumentumkezelési fájlok használatára formátumkimenetekben elektronikus jelentéskészítéshez (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben. Ezeket a lépéseket bármely vállalatban végrehajthatja.

A lépések végrehajtásához először végre kell hajtania az „ER Dokumentumkezelési fájlok használata formátumkimenetekben (1. rész: Adatmodell előkészítése)” feladat-útmutató lépéseit.

Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.


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

## <a name="map-new-data-model-elements-to-dynamics-365-for-finance-and-operations-enterprise-edition-data-sources"></a>Az új adatmodellelemek leképezése a Dynamics 365 for Finance and Operations Enterprise kiadás adatforrásokra
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


