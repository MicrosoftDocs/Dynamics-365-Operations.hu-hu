---
title: Fő számlaadatok a Kintlevőségek rendszerbe, jóváhagyási napló használatával
description: Ez a feladat-útmutató bemutatja hogy kell használni a számlajegyzéket számlák létrehozásához, majd hogyan kell a kiadási számlákat frissíteni a jóváhagyási napló segítségével.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 048eda77064b6aa3f666e998a8e551d2f7adc385
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550374"
---
# <a name="key-invoice-data-into-ap-system-using-approval-journal"></a>Fő számlaadatok a Kintlevőségek rendszerbe, jóváhagyási napló használatával

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ez a feladat-útmutató bemutatja hogy kell használni a számlajegyzéket számlák létrehozásához, majd hogyan kell a kiadási számlákat frissíteni a jóváhagyási napló segítségével.


## <a name="create-and-post-and-invoice"></a>Számla létrehozása és feladása
1. Ugorjon a Kötelezettségek > Számlák > Számlajegyzék elemre.
2. Kattintson az Új lehetőségre.
3. Válassza ki a használni kívánt számlajegyzék nevét.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Kattintson a Sorokra a jegyzék megnyitásához, adjon meg költségsorokat.
6. Válasszon ki egy szállítót. Például adja a US-104 értéket
7. Érték beírása a Számla mezőbe.
8. Írjon egy értéket a „Leírás” mezőbe.
9. A Hitelkeret mezőben adjon meg egy számot.
10. A Jóváhagyó mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.
11. Jelöljön ki egy jóváhagyót és kattintson a Kijelölés gombra a jóváhagyó kiválasztásához.
12. Kattintson a Feladás lehetőségre.
13. Zárja be a lapot.
14. Zárja be a lapot.

## <a name="approve-an-invoice"></a>Számla jóváhagyása
1. Ugorjon a Kötelezettségek > Számlák > Számlajóváhagyás elemre.
2. Kattintson az Új lehetőségre.
3. Válassza ki a használni kívánt számlajóváhagyás-jegyzék nevét.
4. A listában kattintson a kijelölt sorban lévő hivatkozásra.
5. Kattintson a sorokra az oldal megjelenítéséhez, ahol kiválaszthatja a jóváhagyni kívánt számlákat.
6. Válassza ki a Bizonylatok keresése lehetőséget az összes jóváhagyható számla megjelenítéséhez.
7. Jelölje ki a létrehozott számlát.
8. Kattintson a Kiválasztás lehetőségre.
    * A fent kiválasztott bizonylatok erre a listára kerülnek.  
9. Kattintson az OK gombra.
10. Kattintson a számlaszám mezőre, ha szeretne a számlához költségszámlát adni.
11. Adjon meg egy számlaszámot és lépjen ki a mezőből. Például írja be, hogy 600120.
12. Kattintson a Feladás lehetőségre.
13. Kattintson a Bizonylat lehetőségre, hogy megtekintse hova kerültek feladásra a bejegyzések.
    * A Függőben lévő számla visszavonásra kerül és egy tényleges költségszámla jön létre helyette.  

