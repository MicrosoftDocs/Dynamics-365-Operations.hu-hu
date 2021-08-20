---
title: ER Dokumentumkezelési fájlok használata formátumkimenetekben (3. rész –Formátum létrehozása)
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni egy Elektronikus jelentéskészítési formátumot a dokumentumkezelési fájlok használatára az ER-kimenetben. (3. rész)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0cb052e2895cd0eb7f5c3bea9f33d988ef54dfb11e2e31c4212706b7fdaada79
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6766385"
---
# <a name="er-use-document-management-files-in-format-outputs-part-3---create-format"></a>ER Dokumentumkezelési fájlok használata formátumkimenetekben (3. rész –Formátum létrehozása)

[!include [banner](../../includes/banner.md)]

A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben. Ezeket a lépéseket bármely vállalatban végrehajthatja.

A lépések végrehajtásához először végre kell hajtania az „ER Dokumentumkezelési fájlok használata formátumkimenetekben (2. rész: Adatmodell előkészítése)” eljárás lépéseit.

Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.


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



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]