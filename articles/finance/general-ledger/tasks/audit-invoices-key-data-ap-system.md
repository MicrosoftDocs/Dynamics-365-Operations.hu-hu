---
title: A kötelezettségkezelésben levő számlák és kulcsfontosságú adatok vizsgálata
description: Ez a témakör a kötelezettségkezelésben levő számlák és kulcsfontosságú adatok vizsgálatát mutatja be.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6188b10327e4827cf5752fa56c3d491ef315b955
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204761"
---
# <a name="audit-invoices-and-key-data-in-accounts-payable"></a>A kötelezettségkezelésben levő számlák és kulcsfontosságú adatok vizsgálata

[!include [banner](../../includes/banner.md)]

Amikor egy beszerzési rendelés után egy termékekről vagy szolgáltatásokról kiállított szállítói számlát fogad be, az üzleti folyamat megkövetelheti, hogy a számla kifizetésének a jóváhagyását megelőzően az áruk és szolgáltatások be legyenek vételezve. Mielőtt elkezdené a beállítást, győződjön meg arról, hogy a Számlaegyeztetés konfigurációs kulcs be van állítva. 

A **Kötelezettségek paraméterei** lapon győződjön meg róla, hogy a Számlaegyeztetés ellenőrzés beállítás van kiválasztva, a **Számla feladása** eltérésekkel mező **Jóváhagyás szükséges** értékű, és a **Soregyeztetés irányelv** mező **Háromirányú egyeztetés** értékű.

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