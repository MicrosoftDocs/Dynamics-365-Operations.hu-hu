---
title: Fuvarlevél egyeztetése manuálisan
description: Ez az eljárás bemutatja, hogyan lehet manuálisan elvégezni a fuvaregyeztetést.
author: Weijiesa
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily, TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8afec41cdb10185077d39a665d0153df1c9bdb9f
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672738"
---
# <a name="reconcile-freight-manually"></a>Fuvarlevél egyeztetése manuálisan

[!include [banner](../../includes/banner.md)]]

Ez az eljárás bemutatja, hogyan lehet manuálisan elvégezni a fuvaregyeztetést. Ezt általában egy szállítási koordinátor végzi. Az USMF bemutatócég adataiban használhatja ezt az eljárást.


## <a name="select-a-load-to-reconcile"></a>Válassza ki a rakományt az egyeztetéshez
1. Ugorjon a Szállításkezelés > Tervezés > Rakománytervező munkaterület elemre.
2. Törölje a Szállított és bevételezett elrejtése jelölőnégyzet jelölését. 
3. A listában jelölje ki a rakományt, amelynek a rakományazonosítója 00006.

## <a name="create-a-carrier-invoice"></a>Szállítói számla létrehozása
Ha manuálisan végzi a fuvaregyeztetést, és nem kapja meg automatikusan a szállítói számlákat, a fuvarlevél alapján számlát hozhat létre.  
1. Kattintson a Kapcsolódó információ lehetőségre.
2. Kattintson a Fuvarlevél részletei lehetőségre.
3. Kattintson a Fuvarlevélszámla generálása lehetőségre.
4. Érték beírása a Számla mezőbe.
5. Kattintson az OK gombra.

## <a name="reconcile-the-invoice"></a>Számla egyeztetése
Ha a fuvarlevél és a szállítói számla egyeztetését végzi, ez soronként történik.  
1. Kattintson a Fuvarlevelek és számlák egyeztetése lehetőségre.
2. Bontsa ki a Számla részletei szakaszt.
3. Bontsa ki a Nem egyeztetett fuvarlevél-adatok szakaszt.
4. A listában jelölje meg a kiválasztott sort.
5. Kattintson az Egyeztetés lehetőségre.
6. Bontsa ki az Egyeztetett fuvarlevél-adatok szakaszt.

## <a name="submit-the-invoice-for-approval"></a>A számla elküldése jóváhagyásra
1. Kattintson az Elküldés jóváhagyásra elemre.
2. Zárja be a lapot.
3. Szüntesse meg a Jóváhagyott elrejtése jelölőnégyzet bejelölését. 
4. Kattintson a Szállítói számlanaplók elemre.
5. Kattintson a Hivatkozási naplószám mezőben található hivatkozás megnyitásához.
6. Kattintson a Sorok pontra.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]