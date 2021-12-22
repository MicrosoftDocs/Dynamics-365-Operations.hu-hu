---
title: Tárgyi eszköz felosztása
description: Ez a témakör azt ismerteti, hogyan kell egy eszközkönyv egy részét egy másik eszközkönyvhöz rendeli.
author: moaamer
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a2fbca50342196dd9f5acb53027fb9c0052a81de
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/03/2021
ms.locfileid: "7883543"
---
# <a name="split-a-fixed-asset"></a>Tárgyi eszköz felosztása

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan kell egy eszközkönyv egy részét egy másik eszközkönyvhöz rendeli. 

## <a name="create-a-new-fixed-asset"></a>Új tárgyi eszköz létrehozása

1. A navigációs ablaktáblán ugorjon a **Modulok \> Tárgyi eszközök \> Tárgyi eszközök \> Tárgyi eszközök** elemre.
2. Válassza az **Új** lehetőséget.
3. A **Tárgyieszköz-csoport** mezőben adjon meg vagy válasszon ki egy értéket. Jegyezze fel a tárgyi eszköz számát, a felosztás során későbbi felhasználás céljából.
4. A **Név** mezőben adjon meg egy értéket.
5. Zárja be az űrlapot.

## <a name="split-a-fixed-asset"></a>Tárgyi eszköz felosztása

A teljes mértékben értékcsökkentett eszköz felosztása előtt a tárgyi eszköz állapotát manuálisan módosítani kell **Lezárt** értékről **Nyitott** értékre. Ezt a lépést kötelező végrehajtani, mert a könyv állapotának **Nyitottnak** kell lennie, ha a tárgyi eszközhöz tranzakciókat kell feladnia (például egy értékesítéses kivezetés esetében). A **Főkönyvi paraméterek** lap **Általános** fülön be kell kapcsolnia a **Több tranzakció engedélyezése egy bizonylat** paramétert. Miután az eszközkönyv állapota megváltozott, és egy bizonylaton belül több tranzakció is engedélyezett, hajtsa végre a következő lépéseket az eszköz felosztásához.

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

1. A navigációs ablaktáblán nyissa meg a **Modulok \> Tárgyi eszközök \> Naplóbejegyzések \> Tárgyi eszközök naplója** elemet.
2. A listában válassza ki a felosztással létrehozott naplót.
3. **Sorok** kiválasztása.

    - Erősítse meg a létrehozott naplósorokat.
    - Egy beszerzés-helyesbítési tranzakció jön létre az eredeti tárgyi eszközhöz az értéknek a felosztás során generált százalékkal történő csökkentéséhez.
    - Egy Beszerzési tranzakció jön létre az új eszközhöz ugyanazzal az összeggel.

4. Válassza a **Feladás** parancsot.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
