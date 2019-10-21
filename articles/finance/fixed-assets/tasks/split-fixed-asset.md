---
title: Tárgyi eszköz felosztása
description: Ez a témakör azt ismerteti, hogyan kell egy eszközkönyv egy részét egy másik eszközkönyvhöz rendeli.
author: saraschi2
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a4e001a6fdf390c6211ba85aa327b60dcdf16d9e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178066"
---
# <a name="split-a-fixed-asset"></a>Tárgyi eszköz felosztása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a témakör azt ismerteti, hogyan kell egy eszközkönyv egy részét egy másik eszközkönyvhöz rendeli. A Könyvelői szerepkört és a USMF bemutató adatokat használja.


## <a name="create-a-new-fixed-asset"></a>Új tárgyi eszköz létrehozása
1. A navigációs ablaktáblán ugorjon a **Modulok > Tárgyi eszközök > Tárgyi eszközök > Tárgyi eszközök** elemre.
2. Válassza az **Új** lehetőséget.
3. A **Tárgyieszköz-csoport** mezőben adjon meg vagy válasszon ki egy értéket. Jegyezze fel a tárgyi eszköz számát, a felosztás során későbbi felhasználás céljából.  
4. Írjon be egy értéket a **Név** mezőbe.
5. Zárja be az űrlapot.

## <a name="split-a-fixed-asset"></a>Tárgyi eszköz felosztása
1. A listában keresse meg és válassza ki a felosztani kívánt tárgyi eszköz hivatkozását.
2. Válassza ki a **Könyvek** lehetőséget. Válassza ki az új tárgyi eszközhöz hozzárendelni kívánt könyvet.  
3. Válassza a **Funkciók** lehetőséget.
4. Válassza ki a **Tárgyi eszköz felosztása** lehetőséget.
5. A **Záró tárgyi eszköz** mezőben adjon meg vagy válasszon ki egy értéket.
6. A **Könyvhöz** mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
7. A **Tranzakció dátuma** mezőben adjon meg egy dátumot.
8. Adjon meg egy számot a  **Százalék** mezőben.
9. A **Napló neve** mezőben adjon meg vagy válasszon ki egy értéket.
10. Válassza ki az **OK** lehetőséget.

## <a name="post-the-journal-transaction"></a>Naplótranzakciók feladása
1. A navigációs ablaktáblán nyissa meg a **Modulok > Tárgyi eszközök > Naplóbejegyzések > Tárgyi eszközök naplója** elemet.
2. A listában válassza ki a felosztással létrehozott naplót.
3. **Sorok** kiválasztása.

    - Erősítse meg a létrehozott naplósorokat.  
    - Egy beszerzés-helyesbítési tranzakció jön létre az eredeti tárgyi eszközhöz az értéknek a felosztás során generált százalékkal történő csökkentéséhez.  
    - Egy Beszerzési tranzakció jön létre az új eszközhöz ugyanazzal az összeggel.  

4. Válassza a **Feladás** parancsot.

