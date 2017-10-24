--- 
title: "Formátum létrehozása dokumentumkezelési fájlok használatára formátumkimenetekben elektronikus jelentéskészítéshez (ER)"
description: "A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben."
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
ms.openlocfilehash: 71e40351e8b54092d1bbcbc73c6da69073791b74
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-format-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a>Formátum létrehozása dokumentumkezelési fájlok használatára formátumkimenetekben elektronikus jelentéskészítéshez (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben. Ezeket a lépéseket bármely vállalatban végrehajthatja.

A lépések végrehajtásához először végre kell hajtania az „ER Dokumentumkezelési fájlok használata formátumkimenetekben (2. rész: Adatmodell előkészítése)” eljárás lépéseit.

Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.


## <a name="create-a-format-to-process-invoices"></a>Formátum létrehozása számlák feldolgozásához
1. Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.
2. Kattintson a Jelentéskészítés konfigurációi lehetőségre.
3. A fastruktúrában bontsa ki a „Vevői számlamodell” lehetőséget.
4. A fastruktúrában válassza ki a következőt: Vevői számlamodell\Vevői számlamodell (egyéni).
    * Létre fog hozni egy formátumot olyan elektronikus üzenetek generálásához, amelyek információkat tartalmaznak az összes olyan fájlról, amelyeket az elektronikusan feldolgozott számlához kapcsolódó értékesítési rendelésekhez mellékeltek.  
5. A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.
6. Az Új mezőbe írja be a „Formátum alapja a következő adatmodell: Vevői számlamodell (egyéni)” kifejezést.
7. A Név mezőbe írja be a következőt: „Elektronikus számla mintaüzenet”.
    * Elektronikus számla mintaüzenet  
8. Az Adatmodell mezőben adjon meg vagy válasszon ki egy értéket.
    * InvoiceCustomer  
9. Kattintson a Konfiguráció létrehozása lehetőségre.

## <a name="design-a-format-to-populate-attachments-into-generating-a-message-in-mime-format"></a>Tervezzen a mellékleteket feltöltő formátumot MIME-formátumú üzenetek generálására
1. Kattintson a Tervező pontra.
2. Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.
3. A fában válassza ki az XML\Element csomópontot.
4. A Név mezőbe írja be a következőt: „Számla”.
    * Számla  
5. Kattintson az OK gombra.
6. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
7. A fastruktúrában válassza ki az XML\Attribute elemet.
8. A Név mezőbe írja be a következőt: „SalesOrder”.
    * SalesOrder  
9. Kattintson az OK gombra.
10. Kattintson az Attribútum hozzáadása lehetőségre.
11. A Név mezőbe írja be a következőt: „InvoiceNumber”.
    * InvoiceNumber  
12. Kattintson az OK gombra.
13. Kattintson az Attribútum hozzáadása lehetőségre.
14. A Név mezőbe írja be a következőt: „InvoiceAmount”.
    * InvoiceAmount  
15. Kattintson az OK gombra.
16. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
17. A fában válassza ki az XML\Element csomópontot.
18. A Név mezőbe írja be a következőt: „EnclosedDocs”.
    * EnclosedDocs  
19. Kattintson az OK gombra.
20. A fastruktúrában válassza ki a „Számla\EnclosedDocs” lehetőséget.
21. Kattintson az Elem hozzáadása lehetőségre.
22. A Név mezőbe írja be a következőt: „Dokumentum”.
    * Bizonylat  
23. Kattintson az OK gombra.
24. A fastruktúrában válassza ki a „Számla\EnclosedDocs\Dokumentum” lehetőséget.
25. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
26. A fastruktúrában válassza ki az XML\Attribute elemet.
27. A Név mezőbe írja be a következőt: „FileName”.
    * FileName  
28. Kattintson az OK gombra.
29. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
30. A fában válassza ki az XML\Element csomópontot.
31. A Név mezőbe írja be a következőt: „FileContent”.
    * FileContent  
32. Kattintson az OK gombra.
33. A fastruktúrában válassza ki a „Számla\EnclosedDocs\Dokumentum\FileContent” lehetőséget.
34. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
35. A fastruktúrában válassza ki ezt: „Szöveg\Base64”.
36. Kattintson az OK gombra.

## <a name="map-format-elements-to-data-model-as-data-source"></a>Formátumelemek leképezése az adatmodellre adatforrásként
1. A fastruktúrában válassza ki a „Számla\SalesOrder” lehetőséget.
2. Kattintson a Hozzárendelés fülre.
3. A fában bontsa ki a „model” elemet.
4. A fastruktúrában válassza ki a következőt: „modell\Értékesítési rendelés száma(SalesId)”.
5. Kattintson a Kötés gombra.
6. A fastruktúrában válassza ki a „Számla\InvoiceNumber” lehetőséget.
7. A fastruktúrában bontsa ki a „modell\Számlaalap(InvoiceBase)” lehetőséget.
8. A fastruktúrában válassza ki a következőt: „modell\Számlaalap(InvoiceBase) \Számlaszám(Id)”.
9. Kattintson a Kötés gombra.
10. A fastruktúrában válassza ki a „Számla\InvoiceAmount” lehetőséget.
11. A fastruktúrában válassza ki a következőt: „modell\Számlaalap(InvoiceBase) \Számlaösszeg(Amount)”.
12. Kattintson a Kötés gombra.
13. A fastruktúrában bontsa ki a „modell\Számlamellékletek” lehetőséget.
14. A fastruktúrában válassza ki a „modell\Számlamellékletek\Fájltartalom” lehetőséget.
15. A fastruktúrában válassza ki a „Számla\EnclosedDocs\Dokumentum\FileContent\Base64” lehetőséget.
16. Kattintson a Kötés gombra.
17. A fastruktúrában válassza ki a „modell\Számlamellékletek\Fájlnév” lehetőséget.
18. A fastruktúrában válassza ki a „Számla\EnclosedDocs\Dokumentum\FileName” lehetőséget.
19. Kattintson a Kötés gombra.
20. A fastruktúrában válassza ki a „modell\Számlamellékletek” lehetőséget.
21. A fastruktúrában válassza ki a „Számla\EnclosedDocs\Dokumentum” lehetőséget.
22. Kattintson a Kötés gombra.
23. Kattintson a Mentés gombra.
24. Zárja be a lapot.


