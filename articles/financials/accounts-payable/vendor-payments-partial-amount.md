---
title: Szállítói kifizetések részösszegre
description: Bizonyos esetekben előfordulhat, hogy Ön kisebb összeget fizet ki a szállítónak, mint a számlán szereplő összeg. Ez a cikk az ilyen helyzetek megoldásait taglalja.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 617aa35cf1510e90c8c0b5dcfcff070d7db075b8
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1512145"
---
# <a name="vendor-payments-for-a-partial-amount"></a>Szállítói kifizetések részösszegre

[!include [banner](../includes/banner.md)]

Bizonyos esetekben előfordulhat, hogy Ön kisebb összeget fizet ki a szállítónak, mint a számlán szereplő összeg. Ez a cikk az ilyen helyzetek megoldásait taglalja. Az Ön számára elérhető beállítások az ön üzleti igényeitől és konfigurációitól függenek. 

<a name="cash-discount-amounts"></a>Készpénzfizetési engedmények
---------------------

Szállítója készpénzfizetési engedményt kínálhat cégének, ha a számla esedékességi dátuma előtt fizet. Példa: egy 100,00 értékű számlát rögzít, amely 2%-os készpénzfizetési engedményt biztosít, ha 10 napon belül kifizetik. A számla határideje 30 nap. Ha egy fizetési javaslatot készpénzfizetési engedményt használ feltételként a számla kiválasztásához, és a javaslatot a készpénzfizetési engedmény dátumánál nem később futtatják, a számla ki lesz jelölve fizetésre, és 98,00 értékű kifizetési javaslat jön létre. A készpénzfizetési engedmény egy manuálisan létrehozott egyszeri fizetésre is alkalmazható.

## <a name="partial-payments-with-cash-discounts"></a>Részleges kifizetések készpénzfizetési engedménnyel
Amikor cége részleges kifizetést teljesít, akkor valószínű, hogy egy későbbi részleges fizetéssel teljesen ki kívánja majd egyenlíteni a számlát. Ahhoz, hogy a részleges fizetésre is tudjon készpénzfizetési engedményt alkalmazni, a **Részleges kifizetések készpénzfizetési engedményeinek számítása** opciót **Igen** beállításra kell állítani a **Kötelezettségek paraméterei** lapon. 

Tegyük fel, hogy 2%-os készpénzfizetési engedmény kapott a szállítótól, ha a számla kifizetése a kiállítás után 10 napon belül megtörténik. Felad egy 100,00 értékű számlát. Ha 10 napon belül elküldi a 49,00 összegű kifizetést, akkor 49,00 értékű tartozik tételt rögzíthet egy fizetési naplóban. Amikor a részleges kifizetést kiegyenlíti a a **Nyitott tranzakciók kiegyenlítése** lapon, **1,00** érték jelenik meg az **Alkalmazandó készpénzfizetési engedmény összege** mezőben. 

> [!NOTE] 
> Ha részleges fizetést rögzít a rendszerben, és meghagyja a számla teljes összegét a **Kiegyenlítendő összeg** mezőben, akkor az **Alkalmazandó készpénzfizetési engedmény összege** mezőt a program a tranzakciók feladásakor automatikusan újraszámítja.

## <a name="credit-notes-with-cash-discounts"></a>Jóváírások készpénzfizetési engedménnyel
Ha a számlán található cikkek közül visszaküld valamit, akkor jóváírást kap a szállítótól. Ha készpénzfizetési engedményt vett igénybe az eredeti számlára, akkor levonhatja az engedmény érétkét levonhatja, és a helyes összegre vonatkozóan kaphatja meg a visszatérítést. Ha a **Jóváírások készpénzfizetési engedményeinek számítása** opció **Igen** beállításra van állítva a **Kötelezettségek paraméterei** lapon, akkor a program az engedményt automatikusan kiszámítja a jóváíráshoz. 

Tegyük fel, hogy 2%-os készpénzfizetési engedmény kapott a szállítótól, ha a számla kifizetése a kiállítás után 10 napon belül megtörténik. Felad egy 100,00 értékű számlát. Ha visszaküldi az árut és kap egy jóváírást, akkor ezt rögzítheti az eredeti számla teljes összegére, ami 100,00 volt, a 2%-os készpénzfizetési engedménnyel együtt, amely szintén szerepel a jóváíráson.  A jóváírás megtekintésekor a **Tranzakciók kiegyenlítése** lapon **98,00** érték jelenik meg a **Kiegyenlítendő összeg** mezőben, és **-2.00** a **Készpénzfizetési engedmény összege** mezőben. Az engedmény összege egy készpénzfizetési engedmény számlára kerül feladásra.

## <a name="overpaymentunderpayment-amounts"></a>Túlfizetett/alulfizetett összegek
Egyes esetekben olyan részleges fizetést hajthat végre, amelyet követően csak egy nagyon kis összeg marad fenn. Tegyük fel, hogy a szállítói számla összege 1000,00, cége pedig 999,90 értéket fizet. Ha a fennmaradó összeg kevesebb, mint a **Kötelezettségek paraméterei** lapon a túl- vagy alulfizetések esetére meghatározott összeg, akkor a különbséget a program automatikusan feladja a túl-/alulfizetés főkönyvi számlára.


További információkért lásd: [Szállítói fizetési áttekintés](../cash-bank-management/tasks/vendor-payment-overview.md).
