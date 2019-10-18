---
title: ER Dokumentumkezelési fájlok használata formátumkimenetekben (5. rész – Formátum módosítása és futtatása)
description: A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERComponentTypeDropDialog, ERExpressionDesignerFormula, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba9cc4dcdfcfbc1bdb933336e85da9b4b6d97a40
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182508"
---
# <a name="er-use-document-management-files-in-format-outputs-part-5-modify-and-run-format"></a>ER Dokumentumkezelési fájlok használata formátumkimenetekben (5. rész: Formátum módosítása és futtatása)

[!include [task guide banner](../../includes/task-guide-banner.md)]

A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben. Ezeket a lépéseket a DEMF vállalatban hajthatja végre.

A lépések végrehajtásához először végre kell hajtani az „ER Dokumentumkezelési fájlok használata formátumkimenetekben (4. rész: formátum futtatása)” eljárás lépéseit.

Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a>Módosítsa a mellékleteket feltöltő formátumot bináris formátumú üzenetek generálására
1. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
2. A fastruktúrában bontsa ki a „Vevői számlamodell” lehetőséget.
3. A fastruktúrában bontsa ki a következőt: Vevői számlamodell\Vevői számlamodell (egyéni).
4. A fastruktúrában válassza ki a következőt: Vevői számlamodell\Vevői számlamodell (egyéni)\Elektronikus számla mintaüzenet.
5. Kattintson a Tervező pontra.
    * A generált kimenetben a számlaüzenet UNICODE-kódolású XML-fájlként lesz feltöltve.  
6. Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.
7. A fában válassza ki a Common\File csomópontot.
8. A Név mezőbe írja be a következőt: „XML-üzenet”.
    * XML-üzenet  
9. A Kódolás mezőbe írja be az UTF-8 szót.
    * UTF-8  
10. Kattintson az OK gombra.
    * Állítsa be a generált kimenetet tömörített fájlként.  
11. Kattintson a Gyökér hozzáadása lehetőségre a legördülő párbeszédpanel megnyitásához.
12. A fastruktúrában válassza ki következőt: Közös\Mappa.
13. A Név mezőbe írja be a következőt: „Zip-kimenet”.
    * Zip-kimenet  
14. Kattintson az OK gombra.
15. A fastruktúrában válassza ki ezt: „Zip-kimenet”.
    * Adja hozzá a mellékleteket a generált tömörített fájlhoz az eredeti nevükkel és kiterjesztésükkel rendelkező fájlokként.  
16. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
17. A fában válassza ki a Common\File csomópontot.
18. A Név mezőbe írja be a következőt: „Csatolt fájl”.
    * Csatolt fájl  
19. Kattintson az OK gombra.
20. A fastruktúrában válassza ki ezt: „Zip-kimenet\Csatolt fájl”.
21. A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.
22. A fastruktúrában válassza ki ezt: „Szöveg\Base64”.
23. Kattintson az OK gombra.

## <a name="map-new-format-elements-to-data-model"></a>Új formátum-összetevők leképezése az adatmodellre
1. Kattintson a Hozzárendelés fülre.
2. A fában bontsa ki a „model” elemet.
3. A fastruktúrában bontsa ki a „modell\Számlamellékletek” lehetőséget.
4. A fastruktúrában válassza ki ezt: „Zip-kimenet\Csatolt fájl\Base64”.
5. A fastruktúrában válassza ki a „modell\Számlamellékletek\Fájltartalom” lehetőséget.
6. Kattintson a Kötés gombra.
7. A fastruktúrában válassza ki ezt: „Zip-kimenet\Csatolt fájl”.
8. Kattintson a Fájlnév szerkesztése elemre.
9. A fában bontsa ki a „model” elemet.
10. A fastruktúrában bontsa ki a „modell\Számlamellékletek” lehetőséget.
11. A fastruktúrában válassza ki a „modell\Számlamellékletek\Fájlnév” lehetőséget.
12. Kattintson az Adatforrás hozzáadása pontra.
13. Kattintson a Mentés gombra.
14. Zárja be a lapot.
15. A fastruktúrában válassza ki a „modell\Számlamellékletek” lehetőséget.
16. Kattintson a Kötés gombra.
17. Kattintson a Mentés gombra.
18. Zárja be a lapot.

## <a name="run-the-designed-report-for-the-selected-invoice"></a>A tervezett jelentés futtatása a kijelölt számlához
1. Kattintson a Futtatás elemre.
2. Bontsa ki a Belefoglalandó rekordok () szakaszt.
3. Kattintson a Szűrő parancsra.
4. Válassza ki a Vevői számlanapló sorát és a Értékesítési rendelés mezőt.
5. A Feltétel mezőben, az „Eladási rendelés” feltétel mezőjébe írja be a 000148 rendelési számot.
    * 000148  
6. Kattintson az OK gombra.
7. Kattintson az OK gombra.
    * Tekintse át a létrehozott kimenetet. Megjegyzendő, hogy az XML-formátumú számlaüzeneten kívül az összes melléklet számára létrejön egy fájl. A mellékletfájlok feltöltése a tömörített kimenettel bináris formátumban történik.  

