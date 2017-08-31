--- 
title: "Formátum futtatása dokumentumkezelési fájlok használatára formátumkimenetekben elektronikus jelentéskészítéshez (ER)"
description: "A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben."
author: NickSelin
manager: AnnBe
ms.date: 10/31/2016
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
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 6e1d7a54055829a1e9215a44f8eba346291f6717
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---
# <a name="run-format-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a>Formátum futtatása dokumentumkezelési fájlok használatára formátumkimenetekben elektronikus jelentéskészítéshez (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben. Ezeket a lépéseket a DEMF vállalatban hajthatja végre.

A lépések végrehajtásához először végre kell hajtania az „ER Dokumentumkezelési fájlok használata formátumkimenetekben (3. rész: Formátum létrehozása)” eljárás lépéseit.

Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a>Egyetlen számla értékesítési rendeléshez szükséges mellékleteinek hozzáadása
1. Ugorjon a Kinnlévőségek > Számlák > Nyitott vevői számlák pontra.
2. Rekordok kereséséhez használja a gyorsszűrőt. Például szűrje a Számla mezőt a „CIV-000148” értéket beírva.
    * CIV-000148  
3. Ide kattintva nyithatja meg a kijelölt számla hivatkozását.
    * CIV-000148  
4. Kattintson az Értékesítési rendelés mezőben található hivatkozás megnyitásához.
    * 000148  
5. A Sorok vagy fejléc mezőben válassza a Fejléc lehetőséget.
    * Válassza ki a fejlécet annak a jelzésére, hogy ez lesz a cél a mellékletek hozzáadásához.  
6. Kattintson a Csatolás elemre.
    * Adjon hozzá néhány fájlt az értékesítési rendeléshez mellékletként. A Dokumentumkezelés által támogatott típusú dokumentumfájlokat használja (a fájlkiterjesztés DOCX, DPF, XML, JPG stb.). Keresse meg és válassza ki a fájlokat csatolásra és további feldolgozásra a kapcsolódó számlával az ER elektronikus üzenetben.  
7. Kattintson az Új lehetőségre.
8. Kattintson a Fájlra.
9. Kattintson az Új lehetőségre.
10. Kattintson a Fájlra.
11. Zárja be a lapot.
12. Zárja be a lapot.
13. Zárja be a lapot.
14. Zárja be a lapot.

## <a name="run-the-designed-report-for-the-selected-invoice"></a>A tervezett jelentés futtatása a kijelölt számlához
1. Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.
2. A fastruktúrában bontsa ki a „Vevői számlamodell” lehetőséget.
3. A fastruktúrában bontsa ki a következőt: Vevői számlamodell\Vevői számlamodell (egyéni).
4. A fastruktúrában válassza ki a következőt: Vevői számlamodell\Vevői számlamodell (egyéni)\Elektronikus számla mintaüzenet.
5. Kattintson a Futtatás elemre.
6. Bontsa ki a Belefoglalandó rekordok () szakaszt.
7. Kattintson a Szűrő parancsra.
8. Válassza ki a Vevői számlanapló sorát és a Értékesítési rendelés mezőt.
9. A Feltétel mezőbe írja be a „000148” értéket.
    * Az „Értékesítési rendelés” mezőbe feltételként írja be a 000148-es rendelésszámot.  
10. Kattintson az OK gombra.
11. Kattintson az OK gombra.
    * Tekintse át a létrehozott kimenetet. Fontos megjegyezni, hogy az összes melléklethez létrejött egy XML-csomópont. A melléklet tartalma a MIME (base64) szövegformátumú XML-kimenethez van feltöltve.  


