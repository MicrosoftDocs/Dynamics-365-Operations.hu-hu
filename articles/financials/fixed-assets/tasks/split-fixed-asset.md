--- 
title: "Tárgyi eszköz felosztása"
description: "Ez a feladat-útmutató az egyik eszközkönyv egy részét egy másik eszközkönyvhöz rendeli."
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b4c1b39bcae1fa3830f3a217d1ad89e84cd72134
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="split-a-fixed-asset"></a>Tárgyi eszköz felosztása

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a feladat-útmutató az egyik eszközkönyv egy részét egy másik eszközkönyvhöz rendeli.  A Könyvelői szerepkört és a USMF bemutató adatokat használja.


## <a name="create-a-new-fixed-asset"></a>Új tárgyi eszköz létrehozása
1. Nyissa meg a következőt: Tárgyi eszközök > Tárgyi eszközök > Tárgyi eszközök.
2. Kattintson az Új lehetőségre.
3. A Tárgyieszköz-csoport mezőben adjon meg vagy válasszon ki egy értéket.
4. Jegyezze fel a tárgyi eszköz számát, a felosztás során későbbi felhasználás céljából.
5. Írjon be egy értéket a Név mezőbe.
6. Zárja be az űrlapot.

## <a name="split-a-fixed-asset"></a>Tárgyi eszköz felosztása
1. A listában keresse meg és válassza ki a felosztani kívánt tárgyi eszközt.
2. A listában kattintson a kijelölt sorban lévő hivatkozásra.
3. Kattintson a Könyvek elemre.
    * Válassza ki az új tárgyi eszközhöz hozzárendelni kívánt könyvet.  
4. Kattintson a Funkciók elemre.
5. Kattintson a Tárgyi eszköz értékének felosztása gombra.
6. A Cél tárgyi eszköz mezőben adjon meg vagy válasszon ki egy értéket.
7. A Könyvbe mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
8. A Tranzakció dátuma mezőben adjon meg egy dátumot.
9. A Százalék mezőbe írjon be egy számot.
10. A Napló neve mezőben adjon meg vagy válasszon ki egy értéket.
11. Kattintson az OK gombra.

## <a name="post-the-journal-transaction"></a>Naplótranzakciók feladása
1. Ugorjon a Tárgyi eszközök > Naplóbejegyzések > Tárgyi eszközök naplója pontra.
2. A listában válassza ki a felosztással létrehozott naplót.
3. Kattintson a Sorok pontra.
    * Erősítse meg a létrehozott naplósorokat.  Egy beszerzés-helyesbítési tranzakció jön létre az eredeti tárgyi eszközhöz az értéknek a felosztás során generált százalékkal történő csökkentéséhez.  Egy Beszerzési tranzakció jön létre az új eszközhöz ugyanazzal az összeggel.  
4. Kattintson a Feladás lehetőségre.


