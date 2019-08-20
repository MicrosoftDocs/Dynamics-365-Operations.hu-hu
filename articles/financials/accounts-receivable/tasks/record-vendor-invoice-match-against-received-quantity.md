---
title: A szállítói számlák rögzítése és összevetése a bevételezett mennyiséggel
description: Amikor egy beszerzési rendelés után egy termékekről vagy szolgáltatásokról kiállított szállítói számlát fogad be, az üzleti folyamat megkövetelheti, hogy a számla kifizetésének a jóváhagyását megelőzően az áruk és szolgáltatások be legyenek vételezve.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 66d84f497775ce4f988242dd2b327bf4854faef5
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834391"
---
# <a name="record-vendor-invoice-and-match-against-received-quantity"></a>A szállítói számlák rögzítése és összevetése a bevételezett mennyiséggel

[!include [task guide banner](../../includes/task-guide-banner.md)]

Amikor egy beszerzési rendelés után egy termékekről vagy szolgáltatásokról kiállított szállítói számlát fogad be, az üzleti folyamat megkövetelheti, hogy a számla kifizetésének a jóváhagyását megelőzően az áruk és szolgáltatások be legyenek vételezve. Mielőtt elkezdené a beállítást, győződjön meg arról, hogy a Számlaegyeztetés konfigurációs kulcs be van állítva. 

A Kötelezettségek paraméterei lapon győződjön meg róla, hogy a Számlaegyeztetés ellenőrzés beállítás van kiválasztva, a Számla feladása eltérésekkel mező Jóváhagyás szükséges értékű, és a Soregyeztetés irányelv mező Háromirányú egyeztetés értékű.

Ez az eljárás az USMF bemutatócéget használja. A kötelezettségeket kezelő vezető vagy a könyvelésért felelős vezető ezeket a lépéseket hajtja végre.


## <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása
1. Ugrás az összes beszerzési rendelésre.
2. Kattintson az Új lehetőségre.
3. A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
4. Írjon be egy értéket a Szállítói számla mezőbe.
5. Kattintson az OK gombra.
6. Kattintson az Új sor hozzáadása lehetőségre.
7. A cikkmezőbe írjon egy értéket.
8. A Művelet panelen kattintson a Beszerzés elemre.
9. Kattintson a Megerősítés gombra.

## <a name="post-a-product-receipt"></a>Egy Termékbevételezés feladása
1. A Művelet panelen kattintson a Bevételezés elemre.
2. Kattintson a Termékbevételezés elemre.
3. A listában jelölje meg a kiválasztott sort.
4. Írjon be egy értéket a Termékbevételezés mezőbe.
5. Kattintson az OK gombra.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>Szállítói számla rögzítése és egyeztetése a termékbevételezésekkel
1. A Művelet panelen kattintson a Számla lehetőségre.
2. Kattintson a Számla lehetőségre.
3. Érték beírása a Szám mezőbe.
4. Kattintson az Alapértelmezett forrás: Rendelt mennyiségre a legördülő párbeszédablak megnyitásához.
5. Egy lehetőség kiválasztása a Sorok alapértelmezett mennyisége mezőben.
6. Kattintson az OK gombra.
7. Kattintson az Igen gombra.
8. Kattintson a Termékbevételezések egyeztetése lehetőségre.
9. Kattintson az OK gombra.
10. A Művelet panelen kattintson az Áttekintés lehetőségre.
11. Kattintson a Részletek egyeztetése elemre.

