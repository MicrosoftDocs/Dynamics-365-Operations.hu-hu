---
title: A kötelezettségkezelésben levő számlák és kulcsfontosságú adatok vizsgálata
description: Ez a cikk bemutatja, hogyan lehet könyvvizsgálati számlákat és a kötelezettségekben szereplő kulcsadatokat könyvvizsgálatra.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4525534f906322c7fe4c232f0f6da5b308829087
ms.sourcegitcommit: 9740f9b41a7dcf1821c6baccb2e05b9865ac2966
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/15/2022
ms.locfileid: "9775215"
---
# <a name="audit-invoices-and-key-data-in-accounts-payable"></a>A kötelezettségkezelésben levő számlák és kulcsfontosságú adatok vizsgálata

[!include [banner](../../includes/banner.md)]

Amikor egy beszerzési rendelés után egy termékekről vagy szolgáltatásokról kiállított szállítói számlát fogad be, az üzleti folyamat megkövetelheti, hogy a számla kifizetésének a jóváhagyását megelőzően az áruk és szolgáltatások be legyenek vételezve. Mielőtt elkezdené a beállítást, győződjön meg arról, hogy a Számlaegyeztetés konfigurációs kulcs be van állítva. 

**A Kötelezettségek paraméterei** lapon győződjön meg arról, **hogy** be van jelölve a Számlaegyeztetéses ellenőrzés engedélyezése beállítás, **·** **az** Eltéréseket fel adó számlák feladása mező beállítása Kötelező jóváhagyás, **·** **a** Soregyeztetési irányelv mező pedig háromoldalas egyeztetésre van beállítva.

Ez az eljárás az USMF bemutatócéget használja. A kötelezettségeket kezelő vezető vagy a könyvelésért felelős vezető ezeket a lépéseket hajtja végre.


## <a name="create-a-purchase-order"></a>Beszerzési rendelés létrehozása
1. Lépjen az **Összes beszerzési rendelés** lehetőségre.
2. Kattintson az **Új** elemre.
3. A **Szállítói számla** mezőben adjon meg egy értéket.
4. Kattintson az **OK** gombra.
5. Kattintson az **Új sor hozzáadása** elemre.
6. A **Cikkszám** mezőbe írjon egy értéket.
7. A Művelet panelen kattintson a **Beszerzés** elemre.
8. Kattintson a **Megerősítés** gombra.

## <a name="post-a-product-receipt"></a>Egy Termékbevételezés feladása
1. A Művelet panelen kattintson a **Fogadás** elemre.
2. Kattintson a **Termékbevételezés** lehetőségre.
3. Írjon be egy értéket a **Termékbevételezés** mezőbe.
4. Kattintson az **OK** gombra.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>Szállítói számla rögzítése és egyeztetése a termékbevételezésekkel
1. A Művelet panelen kattintson a **Számla > Számla** lehetőségre.
2. Adjon meg egy értéket a **Szám** mezőben.
3. Kattintson az **Alapértelmezett forrás: Rendelt mennyiség** elemre a legördülő párbeszédablak megnyitásához.
4. Válasszon egy lehetőséget a **Sorokhoz tartozó alapértelmezett mennyiség** mezőben.
5. Kattintson az **OK** gombra.
6. Kattintson az **Igen** gombra.
7. Kattintson a **Termékbevételezések egyeztetése** lehetőségre.
8. Kattintson az **OK** gombra.
9. A Művelet panelen kattintson az **Áttekintés** lehetőségre.
10. Kattintson a **Részletek egyeztetése** elemre.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
