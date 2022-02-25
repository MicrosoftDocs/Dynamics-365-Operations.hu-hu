---
title: A szállítói számlák rögzítése és összevetése a bevételezett mennyiséggel
description: Amikor egy beszerzési rendelés után egy termékekről vagy szolgáltatásokról kiállított szállítói számlát fogad be, az üzleti folyamat megkövetelheti, hogy a számla kifizetésének a jóváhagyását megelőzően az áruk és szolgáltatások be legyenek vételezve.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8a3f1463821a43af0d8d5f15225944b080414e4c
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109918"
---
# <a name="record-vendor-invoice-and-match-against-received-quantity"></a>A szállítói számlák rögzítése és összevetése a bevételezett mennyiséggel

[!include [banner](../../includes/banner.md)]

Amikor egy beszerzési rendelés után egy termékekről vagy szolgáltatásokról kiállított szállítói számlát fogad be, az üzleti folyamat megkövetelheti, hogy a számla kifizetésének a jóváhagyását megelőzően az áruk és szolgáltatások be legyenek vételezve. Mielőtt elkezdené a beállítást, győződjön meg arról, hogy a Számlaegyeztetés konfigurációs kulcs be van állítva. 

**A Kötelezettségek paraméterei** lapon győződjön meg arról, **hogy** be van jelölve a Számlaegyeztetéses ellenőrzés engedélyezése beállítás, **·** **az** Eltéréseket fel adó számlák feladása mező beállítása Kötelező jóváhagyás, **·** **a** Soregyeztetési irányelv mező pedig háromoldalas egyeztetésre van beállítva.

Ez az eljárás az USMF bemutatócéget használja. A kötelezettségeket kezelő vezető vagy a könyvelésért felelős vezető ezeket a lépéseket hajtja végre.


## <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása
1. Ugrás az összes beszerzési rendelésre.
2. Kattintson az **Új** elemre.
3. A **Szállítói számla** mezőben kattintson a legördülő gombra a keresés megnyitásához.
4. A **Szállítói számla** mezőben adjon meg egy értéket.
5. Kattintson az **OK** gombra.
6. Kattintson az **Új sor hozzáadása** elemre.
7. A **Cikkszám** mezőbe írjon egy értéket.
8. A Művelet panelen kattintson a **Beszerzés** elemre.
9. Kattintson a **Megerősítés** gombra.

## <a name="post-a-product-receipt"></a>Egy Termékbevételezés feladása
1. A Művelet panelen kattintson a **Fogadás** elemre.
2. Kattintson a **Termékbevételezés** lehetőségre.
3. A listában jelölje meg a kiválasztott sort.
4. Írjon be egy értéket a **Termékbevételezés** mezőbe.
5. Kattintson az **OK** gombra.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>Szállítói számla rögzítése és egyeztetése a termékbevételezésekkel
1. A Műveleti ablaktáblán kattintson a **Számla** elemre.
2. Kattintson a **Számla** pontra.
3. Adjon meg egy értéket a **Szám** mezőben.
4. Kattintson az **Alapértelmezett forrás: Rendelt mennyiség** elemre a legördülő párbeszédablak megnyitásához.
5. Válasszon egy lehetőséget a **Sorokhoz tartozó alapértelmezett mennyiség** mezőben.
6. Kattintson az **OK** gombra.
7. Kattintson az **Igen** gombra.
8. Kattintson a **Termékbevételezések egyeztetése** lehetőségre.
9. Kattintson az **OK** gombra.
10. A Művelet panelen kattintson az **Áttekintés** lehetőségre.
11. Kattintson a **Részletek egyeztetése** elemre.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
