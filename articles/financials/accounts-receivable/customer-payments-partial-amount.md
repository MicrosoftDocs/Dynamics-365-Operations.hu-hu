---
title: "Vevői kifizetések részösszegre"
description: "Bizonyos esetekben a vevő kisebb összeget fizet ki, mint a számlán szereplő összeg. Ez a cikk az ilyen helyzetek megoldásait taglalja. Az Ön számára elérhető beállítások az ön üzleti igényeitől és konfigurációitól függenek."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13011
ms.assetid: 20423a2d-6997-4e1c-a596-a77016600071
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6e4fac197e75b80609486be7ea7c50c4b48beeb7
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="customer-payments-for-a-partial-amount"></a>Vevői kifizetések részösszegre

[!include[banner](../includes/banner.md)]


Bizonyos esetekben a vevő kisebb összeget fizet ki, mint a számlán szereplő összeg. Ez a cikk az ilyen helyzetek megoldásait taglalja. Az Ön számára elérhető beállítások az ön üzleti igényeitől és konfigurációitól függenek.

<a name="partial-payment-with-no-discount"></a>Részleges kifizetés engedmény nélkül
--------------------------------

Egy vevő olyankor kínálhat részletes fizetést, ha nem rendelkezik elegendő készpénzzel a számlat teljes kifizetéséhez, vagy ha vita áll fenn a számla egyik cikkével kapcsolatban. Ebben a helyzetben a számla részlegesen is kiegyenlíthető egy kifizetéssel. A számla továbbra nyitott marad, és egyenleget mutat.

## <a name="discount-amounts"></a>Engedményösszegek
Vevőinek készpénzfizetési engedményt kínálhat, ha a számla esedékességi dátuma előtt fizetnek. Példa: rögzít egy 100,00 értékű számlát, amely 2%-os készpénzfizetési engedményt biztosít, ha 10 napon belül kifizetik. A számla határideje 30 nap. Ha 10 napon belül megkapja a 98,00 összegű kifizetést, akkor 98,00 értékű fizetést rögzíthet a rendszerben. Ezt követően a számla meg lesz jelölve kiegyenlítésre, a készpénzfizetési engedményt a rendszer automatikusan beleszámítja.

## <a name="partial-payments-with-cash-discounts"></a>Részleges kifizetések készpénzfizetési engedménnyel
Ha a vevő részleges kifizetést teljesít, akkor valószínű, hogy egy későbbi részleges fizetéssel teljesen ki kívánja majd egyenlíteni a számlát. Ahhoz, hogy a részleges fizetésre is tudjon készpénzfizetési engedményt alkalmazni, a **Részleges kifizetések készpénzfizetési engedményeinek számítása** opciót **Igen** beállításra kell állítani a **Kinnlevőségek paraméterei** lapon. 

Tegyük fel, hogy 2%-os készpénzfizetési engedmény kínál, ha a számla kifizetése a kiállítás után 10 napon belül megtörténik. Felad egy 100,00 értékű számlát. Ha 10 napon belül megkapja a 49,00 összegű kifizetést, akkor 49,00 értékű követel tételt rögzíthet egy fizetési naplóban. Amikor a részleges kifizetést kiegyenlíti a a **Tranzakciók kiegyenlítése** lapon, **1,00** érték jelenik meg az **Alkalmazandó készpénzfizetési engedmény összege** mezőben. Az engedmény összege egy készpénzfizetési engedmény számlára kerül feladásra. 

> [!NOTE] 
> Ha részleges fizetést rögzít a rendszerben, és meghagyja a számla teljes összegét a **Kiegyenlítendő összeg** mezőben, akkor az **Alkalmazandó készpénzfizetési engedmény összege** mezőt a program a tranzakciók feladásakor automatikusan újraszámítja.

## <a name="credit-notes-with-discounts"></a>Jóváírások engedménnyel
Ha a vevők a számlán található cikkek közül visszaküldenek, akkor jóváírást állíthat ki. Ha készpénzfizetési engedmény volt az eredeti számlán, akkor a vevői jóváírás az általa kapott készpénzfizetési engedményhez képest nettó összeg kell legyen. Ha a **Jóváírások készpénzfizetési engedményeinek számítása** opció **Igen** beállításra van állítva a **Kinnlevőségek paraméterei** lapon, akkor a program az engedményt automatikusan kiszámítja a jóváíráshoz. 

Tegyük fel, hogy 2%-os készpénzfizetési engedmény kínált a feltételek között, ha a számla kifizetése a kiállítás után 10 napon belül megtörténik. Feladásra került egy 100,00 értékű számla, és a vevő kihasználta a készpénzfizetési engedményt. Ha a vevő visszaküldte a termékeket, így jóváírást bocsátottak ki a számára, akkor -100,00 értékű jóváírást adhat meg. A jóváírás megtekintésekor a **Nyitott tranzakciók kiegyenlítése** lapon **98,00** érték jelenik meg a **Kiegyenlítendő összeg** mezőben, és **-2.00** a **Készpénzfizetési engedmény összege** mezőben. Az engedmény összege egy készpénzfizetési engedmény számlára kerül feladásra.

## <a name="overpaymentunderpayment-amounts"></a>Túlfizetett/alulfizetett összegek
Amikor a vevő kifizetést küld, egyes esetekben visszamarad egy kisebb, még kiegyenlítendő összeg. Tegyük fel, hogy 1000,00 értékben számlázott a vevőnek, a vevő azonban 999,90 értéket fizetett ki. Ha a fennmaradó összeg kevesebb, mint a **Kinnlevőségek paramétereinek** lapon a túl- vagy alulfizetések esetére meghatározott összeg, akkor a különbséget a program automatikusan feladja a túl-/alulfizetés főkönyvi számlára.

## <a name="full-settlement"></a>Teljes kiegyenlítés
A vevők részleges kifizetést is végezhetnek, amelynél a fennmaradó összeget nem fizeti ki, viszont az összeg nagyobb, mint a **Kötelezettségek paraméterei** oldalon megadott alulfizetési összeg. Ha szeretné a számlát teljesen kiegyenlítettként megjelölni, használja a **Teljes kiegyenlítés** beállítást a **Tranzakció kiegyenlítése** lapon. (A teljes kiegyenlítési funkciót egy konfigurációs kulccsal engedélyezheti.) Tegyük fel, hogy egy 1000,00 értékű számlát ad fel, a vevő pedig 990,00 értéket fizet ki. Már elfogadta, hogy a vevőnek nem kell kifizetnie a fennmaradó 10,00-et. A számla kiegyenlítésre való megjelölése után megjelölheti a **Teljes kiegyenlítés** opciót is. A számla ezután teljesen kiegyenlítettnek fog számítani. A 10,00 különbséget egy készpénzfizetési engedményszámlára adja fel a rendszer, mint további készpénzfizetési engedmény.


További információkért lásd: [Vevői kifizetések letétele](tasks/deposit-customer-payments.md).

