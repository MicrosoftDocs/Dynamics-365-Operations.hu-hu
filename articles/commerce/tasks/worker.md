---
title: " Dolgozó konfigurálása"
description: Ez az eljárás bemutatja, hogyan konfigurálhatja a dolgozót pénztári eladási jutalékra jogosult üzletkötőként.
author: jblucher
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, HcmWorker
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 43e65de1fda223c2d0503848e7e57936898c1b73
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804065"
---
# <a name="configure-a-worker"></a> Dolgozó konfigurálása

[!include [banner](../includes/banner.md)]

Ez az eljárás bemutatja, hogyan konfigurálhatja a dolgozót pénztári eladási jutalékra jogosult üzletkötőként. Ez az eljárás az USRT bemutatócéget használja.


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
1. Nyissa meg a következőt: Retail és Commerce > Alkalmazottak > Dolgozók.
2. Keresse meg és jelölje ki a kívánt rekordot a listán.
3. A listában kattintson a kijelölt sorban lévő hivatkozásra.
4. Kattintson a Commerce fülre.
    * A dolgozók hozzárendelhetők egy alapértelmezett értékesítési csoporthoz. Az alapértelmezett értékesítési csoport automatikusan hozzáadódik a pénztár eladási soraihoz, ha a beállítás engedélyezve van az üzlet funkcióprofiljában.  
5. Kattintson a Szerkesztés lehetőségre.
6. Adjon meg vagy válasszon ki egy értéket az Alapértelmezett csoport mezőben.
7. Kattintson a Mentés gombra.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]