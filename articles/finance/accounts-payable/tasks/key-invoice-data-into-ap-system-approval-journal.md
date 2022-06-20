---
title: Fő számlaadatok a kötelezettségekbe jóváhagyási napló használatával
description: Ez a cikk bemutatja, hogy hogyan használható a számlajegyzék a számlák létrehozására, majd a jóváhagyási napló segítségével frissítheti a költségszámlákat.
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: afe1471949bbf892f4e28ed3bea830ee491a517f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909214"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a>Fő számlaadatok a kötelezettségekbe jóváhagyási napló használatával

[!include [banner](../../includes/banner.md)]

Ez a cikk bemutatja, hogy hogyan használható a számlajegyzék a számlák létrehozására, majd a jóváhagyási napló segítségével frissítheti a költségszámlákat.

## <a name="create-and-post-and-invoice"></a>Számla létrehozása és feladása
1. Anavigációs ablaktáblán válassza a **Modulok > Kötelezettségek > számlák > Számlajegyzék** elemre.
2. Válassza az **Új** lehetőséget.
3. Válassza ki a használni kívánt számlajegyzék nevét.
4. Kattintson a **Sorokra** a jegyzék megnyitásához, adjon meg költségsorokat.
5. Válasszon ki egy szállítót. Például adja a `US-104` értéket
6. Írjon be egy értéket a **Számla** mezőbe.
7. Írjon egy értéket a **Leírás** mezőbe.
8. A **Hitelkeret** mezőben adjon meg egy számot.
9. Az **Jóváhagyó** mezőben válasszon ki egy jóváhagyót a legördülő menüben.
10. Válassza a **Feladás** parancsot.

## <a name="approve-an-invoice"></a>Számla jóváhagyása
1. Anavigációs ablaktáblán válassza a **Modulok > Kötelezettségek > számlák > Számlajóváhagyás** elemre.
2. Válassza az **Új** lehetőséget.
3. Válassza ki a használni kívánt számlajóváhagyás-jegyzék nevét.
4. Kattintson a **Sorokra** az oldal megjelenítéséhez, ahol kiválaszthatja a jóváhagyni kívánt számlákat.
5. Válassza ki a **Bizonylatok keresése** lehetőséget az összes jóváhagyható számla megjelenítéséhez.
6. Jelölje meg a létrehozott számlát, majd kattintson a **Kiválasztás** gombra. A fent kiválasztott bizonylatok erre a listára kerülnek.  
7. Válassza ki az **OK** lehetőséget.
8. Kattintson a **számlaszám mezőre**, ha szeretne a számlához költségszámlát adni.
9. Adjon meg egy számlaszámot és lépjen ki a mezőből. Például írja be, hogy `600120`.
10. Válassza a **Feladás** parancsot.
11. Kattintson a **Bizonylat** lehetőségre, hogy megtekintse hova kerültek feladásra a bejegyzések. A Függőben lévő számla visszavonásra kerül és egy tényleges költségszámla jön létre helyette.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
