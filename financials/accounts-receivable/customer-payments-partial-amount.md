---
title: "Vevői kifizetések részösszegre"
description: "Bizonyos esetekben a vevő kisebb összeget fizet ki, mint a számlán szereplő összeg. Ez a cikk az ilyen helyzetek megoldásait taglalja. Az Ön számára elérhető beállítások az ön üzleti igényeitől és konfigurációitól függenek."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13011
ms.assetid: 20423a2d-6997-4e1c-a596-a77016600071
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: 7025072cd29aac4ceb13b5594c3e321350777cf1
ms.lasthandoff: 03/31/2017


---

# <a name="customer-payments-for-a-partial-amount"></a>Vevői kifizetések részösszegre

Bizonyos esetekben a vevő kisebb összeget fizet ki, mint a számlán szereplő összeg. Ez a cikk az ilyen helyzetek megoldásait taglalja. Az Ön számára elérhető beállítások az ön üzleti igényeitől és konfigurációitól függenek.

<a name="partial-payment-with-no-discount"></a>Részleges kifizetés engedmény nélkül
--------------------------------

Egy vevő olyankor kínálhat részletes fizetést, ha nem rendelkezik elegendő készpénzzel a számlat teljes kifizetéséhez, vagy ha vita áll fenn a számla egyik cikkével kapcsolatban. Ebben a helyzetben a számla részlegesen is kiegyenlíthető egy kifizetéssel. A számla továbbra nyitott marad, és egyenleget mutat.

## <a name="discount-amounts"></a>Engedményösszegek
Vevőinek készpénzfizetési engedményt kínálhat, ha a számla esedékességi dátuma előtt fizetnek. Példa: rögzít egy 100,00 értékű számlát, amely 2%-os készpénzfizetési engedményt biztosít, ha 10 napon belül kifizetik. A számla határideje 30 nap. Ha 10 napon belül megkapja a 98,00 összegű kifizetést, akkor 98,00 értékű fizetést rögzíthet a rendszerben. Ezt követően a számla meg lesz jelölve kiegyenlítésre, a készpénzfizetési engedményt a rendszer automatikusan beleszámítja.

## <a name="partial-payments-with-cash-discounts"></a>Részleges kifizetések készpénzfizetési engedménnyel
Ha a vevő részleges kifizetést teljesít, akkor valószínű, hogy egy későbbi részleges fizetéssel teljesen ki kívánja majd egyenlíteni a számlát. Részleges kifizetés készpénzfizetési engedményt veszi, meg kell a ** részfizetések készpénzfizetési engedményeinek számítása ** lehetőséggel **Igen** a a **Kinnlevőségek paraméterei** lap. 

Tegyük fel, hogy 2%-os készpénzfizetési engedmény kínál, ha a számla kifizetése a kiállítás után 10 napon belül megtörténik. Felad egy 100,00 értékű számlát. Ha 10 napon belül megkapja a 49,00 összegű kifizetést, akkor 49,00 értékű követel tételt rögzíthet egy fizetési naplóban. Amikor a részleges kifizetést kiegyenlíti a a **Tranzakciók kiegyenlítése** lapon, **1,00** érték jelenik meg az **Alkalmazandó készpénzfizetési engedmény összege** mezőben. Az engedmény összege egy készpénzfizetési engedmény számlára kerül feladásra. 

> [!NOTE] 
> Ha egy részleges kifizetést, és hagyja a számla teljes összege a **kiegyenlítendő összeg**, a mező a **készpénzfizetési engedmény összege** mező automatikusan frissül a tranzakciók könyvelésekor.

## <a name="credit-notes-with-discounts"></a>Jóváírások engedménnyel
Ha a vevők a számlán található cikkek közül visszaküldenek, akkor jóváírást állíthat ki. Ha készpénzfizetési engedmény volt az eredeti számlán, akkor a vevői jóváírás az általa kapott készpénzfizetési engedményhez képest nettó összeg kell legyen. Ha a **Jóváírások készpénzfizetési engedményeinek számítása** opció **Igen** beállításra van állítva a **Kinnlevőségek paraméterei** lapon, akkor a program az engedményt automatikusan kiszámítja a jóváíráshoz. 

Tegyük fel, hogy 2%-os készpénzfizetési engedmény kínált a feltételek között, ha a számla kifizetése a kiállítás után 10 napon belül megtörténik. Feladásra került egy 100,00 értékű számla, és a vevő kihasználta a készpénzfizetési engedményt. Ha a vevő visszaküldte a termékeket, így jóváírást bocsátottak ki a számára, akkor -100,00 értékű jóváírást adhat meg. A jóváírás megtekintésekor a **Nyitott tranzakciók kiegyenlítése** lapon **98,00** érték jelenik meg a **Kiegyenlítendő összeg** mezőben, és **-2.00** a **Készpénzfizetési engedmény összege** mezőben. Az engedmény összege egy készpénzfizetési engedmény számlára kerül feladásra.

## <a name="overpaymentunderpayment-amounts"></a>Túlfizetett/alulfizetett összegek
Amikor a vevő kifizetést küld, egyes esetekben visszamarad egy kisebb, még kiegyenlítendő összeg. Tegyük fel, hogy 1000,00 értékben számlázott a vevőnek, a vevő azonban 999,90 értéket fizetett ki. Ha a fennmaradó összeg kevesebb, mint a **Kinnlevőségek paramétereinek** lapon a túl- vagy alulfizetések esetére meghatározott összeg, akkor a különbséget a program automatikusan feladja a túl-/alulfizetés főkönyvi számlára.

## <a name="full-settlement"></a>Teljes kiegyenlítés
Felhasználók tehetik egy részfizetést, ahol a fennmaradó összeg nem fizetendő, de nagyobb, mint a megadott alulfizetés összegének a **figyelembe a Kötelezettségek paraméterei** oldalon. Szeretné megjelölni a teljesen kiegyenlített számla, ha a **teljes kiegyenlítés** a beállítás a **tranzakció** lap. (A teljes kiegyenlítési funkciót egy konfigurációs kulccsal engedélyezheti.) Tegyük fel, hogy egy 1000,00 értékű számlát ad fel, a vevő pedig 990,00 értéket fizet ki. Már elfogadott, hogy a vevő nem kell fizetni a fennmaradó 10,00. Miután a számla kiegyenlítésre, megjelölheti a select **teljes kiegyenlítés**. A számla ezután teljesen kiegyenlítettnek fog számítani. A 10,00 különbséget egy készpénzfizetési engedményszámlára adja fel a rendszer, mint további készpénzfizetési engedmény.


