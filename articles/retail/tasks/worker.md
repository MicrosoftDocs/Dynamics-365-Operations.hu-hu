--- 
title: " Dolgozó konfigurálása"
description: "Ez az eljárás bemutatja, hogyan konfigurálhatja a kiskereskedelmi dolgozót pénztári eladási jutalékra jogosult üzletkötőként."
author: jblucher
manager: AnnBe
ms.date: 02/22/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 09c5d263f3ad0bade6b7dd8f099dd3f62a1ddf5d
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="configure-a-worker"></a> Dolgozó konfigurálása

[!include[task guide banner](../includes/task-guide-banner.md)]

Ez az eljárás bemutatja, hogyan konfigurálhatja a kiskereskedelmi dolgozót pénztári eladási jutalékra jogosult üzletkötőként. Ez az eljárás az USRT bemutatócéget használja.


## <a name="create-a-commission-sales-group-for-the-worker"></a>Jutalék értékesítési csoportjának létrehozása a dolgozóhoz
1. Ugrás a Értékesítés és marketing> Jutalékok > Érékesítési csoportok lehetőségre.
    * A dolgozók egy vagy több értékesítési csoporthoz rendelhetők. A pénztárban lehetőség van bármely értékesítési csoport kiválasztására, amely az áruház címjegyzékében megtalálható dolgozókat tartalmaz.  
2. Kattintson az Új lehetőségre.
3. Érték beírása a Csoport mezőbe.
4. Írjon be egy értéket a Név mezőbe.
5. Kattintson a Mentés gombra.
6. A Művelet panelen kattintson az Általános elemre.
7. Kattintson az Üzletkötő lehetőségre.
    * Az értékesítési csoport több dolgozót is tartalmazhat. A jutalékok feloszthatók a dolgozók között attól függően, hogyan határozza meg jutalékok felosztását.  
8. A Név mezőben adjon meg vagy válasszon ki egy értéket.
9. Adjon meg egy számot a Jutalékfelosztások mezőben.
10. Kattintson a Mentés gombra.
11. Zárja be a lapot.
12. Zárja be a lapot.

## <a name="assign-the-workers-default-sales-group"></a>A dolgozók alapértelmezett értékesítési csoportjának hozzárendelése
1. Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Alkalmazottak > Dolgozók.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Kattintson a Kiskereskedelem fülre.
    * A dolgozók hozzárendelhetők egy alapértelmezett értékesítési csoporthoz. Az alapértelmezett értékesítési csoport automatikusan hozzáadódik a pénztár eladási soraihoz, ha a beállítás engedélyezve van az üzlet funkcióprofiljában.  
5. Kattintson a Szerkesztés lehetőségre.
6. Adjon meg vagy válasszon ki egy értéket az Alapértelmezett csoport mezőben.
7. Kattintson a Mentés gombra.


