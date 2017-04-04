---
title: "Szállítói kifizetések részösszegre"
description: "Bizonyos esetekben előfordulhat, hogy Ön kisebb összeget fizet ki a szállítónak, mint a számlán szereplő összeg. Ez a cikk az ilyen helyzetek megoldásait taglalja. Az Ön számára elérhető beállítások az ön üzleti igényeitől és konfigurációitól függenek."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: 4d243e6a9a68b69a6b32748344fc606ff3f2d965
ms.lasthandoff: 03/31/2017


---

# <a name="vendor-payments-for-a-partial-amount"></a>Szállítói kifizetések részösszegre

Bizonyos esetekben előfordulhat, hogy Ön kisebb összeget fizet ki a szállítónak, mint a számlán szereplő összeg. Ez a cikk az ilyen helyzetek megoldásait taglalja. Az Ön számára elérhető beállítások az ön üzleti igényeitől és konfigurációitól függenek. 

<a name="cash-discount-amounts"></a>Készpénzfizetési engedmények
---------------------

Szállítója készpénzfizetési engedményt kínálhat cégének, ha a számla esedékességi dátuma előtt fizet. Példa: egy 100,00 értékű számlát rögzít, amely 2%-os készpénzfizetési engedményt biztosít, ha 10 napon belül kifizetik. A számla határideje 30 nap. Ha kifizetési javaslat készpénzfizetési engedmény feltételként számla kiválasztásának, és a javaslat és a készpénzfizetési engedmény dátumát megelőző fut, fizetés a számla ki van jelölve, és a fizetési 98.00 jön létre. A készpénzfizetési engedmény a manuálisan létrehozott egyszeri kifizetés is kell venni.

## <a name="partial-payments-with-cash-discounts"></a>Részleges kifizetések készpénzfizetési engedménnyel
Amikor cége részleges kifizetést teljesít, akkor valószínű, hogy egy későbbi részleges fizetéssel teljesen ki kívánja majd egyenlíteni a számlát. Részleges kifizetés készpénzfizetési engedményt veszi, meg kell a ** részfizetések készpénzfizetési engedményeinek számítása ** lehetőséggel **Igen** a a **számla a Kötelezettségek paraméterei** lap. 

Tegyük fel, hogy 2%-os készpénzfizetési engedmény kapott a szállítótól, ha a számla kifizetése a kiállítás után 10 napon belül megtörténik. Felad egy 100,00 értékű számlát. Ha 10 napon belül 49.00 megfizetése, a kifizetési napló megadása 49.00 tartozik. Ha a részleges fizetés kiegyenlítése a **nyitott tranzakciók kiegyenlítése** lap **1,00** jelenik meg a **készpénzfizetési engedmény összege** mező. 

> [!NOTE] 
> Ha egy részleges kifizetést, és hagyja a számla teljes összege a **kiegyenlítendő összeg**, a mező a **készpénzfizetési engedmény összege** mező automatikusan frissül a tranzakciók könyvelésekor.

## <a name="credit-notes-with-cash-discounts"></a>Jóváírások készpénzfizetési engedménnyel
Ha a számlán található cikkek közül visszaküld valamit, akkor jóváírást kap a szállítótól. Ha készpénzfizetési engedményt vett igénybe az eredeti számlára, akkor levonhatja az engedmény érétkét levonhatja, és a helyes összegre vonatkozóan kaphatja meg a visszatérítést. Ha a ** jóváírások készpénzfizetési engedményeinek számítása ** beállítás **Igen** meg a **fizetendő paramétereinek** lap, az engedményt automatikusan számítja ki a jóváírásra. 

Tegyük fel, hogy 2%-os készpénzfizetési engedmény kapott a szállítótól, ha a számla kifizetése a kiállítás után 10 napon belül megtörténik. Felad egy 100,00 értékű számlát. Vissza az árut, és jóváírási értesítést kap, ha a jóváírás adja meg az eredeti számla 100,00 és a 2 %-os készpénzfizetési engedmény is a jóváíráson megadott teljes összegét.  Akkor láthatjuk, ha a jóváírás a a **tranzakciók kiegyenlítése** lap **98.00** jelenik meg a **kiegyenlítendő összeg** mező, és **-2.00** jelenik meg a **készpénzfizetési engedmény összege** mezőben. Az engedmény összege egy készpénzfizetési engedmény számlára kerül feladásra.

## <a name="overpaymentunderpayment-amounts"></a>Túlfizetett/alulfizetett összegek
Egyes esetekben olyan részleges fizetést hajthat végre, amelyet követően csak egy nagyon kis összeg marad fenn. Tegyük fel, hogy a szállítói számla összege 1000,00, cége pedig 999,90 értéket fizet. Ha a fennmaradó összeg kevesebb, mint a **Kötelezettségek paraméterei** lapon a túl- vagy alulfizetések esetére meghatározott összeg, akkor a különbséget a program automatikusan feladja a túl-/alulfizetés főkönyvi számlára.


