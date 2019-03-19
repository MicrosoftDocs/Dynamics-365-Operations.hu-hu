---
title: Kötelezettségek kezdőlap
description: Ez a témakör a Kötelezettségekről nyújt áttekintést.
author: ShylaThompson
manager: AnnBe
ms.date: 02/15/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 21901
ms.assetid: 1e4c2ac4-077b-4678-8733-5cec8f6ff659
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: f1acf2bade2bb279a35fdf4689bbbcc49e64101f
ms.sourcegitcommit: afab5269613d1d1dfd79cd39370b747dee13d3fc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/19/2019
ms.locfileid: "403285"
---
# <a name="accounts-payable-home-page"></a>Kötelezettségek kezdőlap

[!include [banner](../includes/banner.md)]

Ez a témakör a Kötelezettségekről nyújt áttekintést. 

Megadhat szállítói számlákat kézzel, vagy egy adatentitáson keresztül elektronikusan is megkaphatja azokat. A számlák rögzítése vagy fogadása után áttekintheti és jóváhagyhatja a számlákat egy számlajóváhagyási napló vagy a **Szállítói számla** oldal használatával. Számlaegyeztetés, a szállítói számlára vonatkozó irányelvek és munkafolyamat segítségével automatizálhatja az ellenőrzési folyamatot, úgy, hogy a rendszer automatikusan jóváhagyja a számlákat, amelyek megfelelnek bizonyos feltételeknek, a fennmaradó számlákat pedig megjelölje ellenőrzésre egy erre jogosult felhasználó számára.

**Üzleti folyamatok**

[![Üzleti folyamat](./media/AP-process.PNG)](./media/AP-process.PNG)

## <a name="set-up-accounts-payable"></a>A Kötelezettségek beállítása

Lehetőség van szállítócsoportok, szállítók, feladási profilok, különböző fizetési lehetőségek, a szállítókra vonatkozó paraméterek, árak és engedmények, költségek, szállítások és célok, kötelezvények, valamint egyéb kötelezettségadatok beállítására. 

[Kötelezettségek konfigurálása](accounts-payable-overview.md)

[Könyvelési felosztások és analitikusnapló-bejegyzések szállítói számlákhoz](accounting-distributions-subledger-journal-entries-vendor-invoices.md) 

[A Kötelezettségek és a Kinnlevőségek modul devizaátértékelései](../cash-bank-management/foreign-currency-revaluation-accounts-payable-accounts-receivable.md)

## <a name="configure-vendor-invoices"></a>Szállítói számlák konfigurálása

A Kötelezettségek modulban nyomon követheti a számlákat és a szállítóknak fizetendő költségeket.

[Kötelezettségek számlaegyeztetése](accounts-payable-invoice-matching.md)

[Szállítói feladási profilok](vendor-posting-profiles.md)

[A kötelezettségek számlaegyeztetésének hitelesítésbeállítása](tasks/set-up-accounts-payable-invoice-matching-validation.md)

[Háromirányú egyeztetési irányelvek](three-way-matching-policies.md)

[Számlaegyeztetés és vállalatközi beszerzési rendelés](invoice-matching-intercompany-purchase-orders.md)

[Számlaösszegek számlaegyeztetési eltéréseinek feloldása](resolve-invoice-totals-invoice-matching-discrepancies.md)

[Alapértelmezett ellenszámlák szállítóiszámla-naplók és számla-jóváhagyási naplók számára](default-offset-accounts-vendor-invoice-journals.md)

[Mobil számlajóváhagyások](mobile-invoice-approvals.md)

[Szállítói együttműködés számlázási munkaterülete](vendor-portal-invoicing-workspace.md)

[Szállítói számla automatizálása](vendor-invoice-automation.md)

## <a name="configure-vendor-payments"></a>Szállítói kifizetések beállítása 

A rendszerben definiált kifizetéstípusokat, például a csekket, az elektronikus fizetést, vagy a kötelezvényt bármilyen felhasználói fizetési módhoz hozzárendelheti. A kifizetéstípusok opcionálisak, de hasznosak, ha elektronikus kifizetéseket kell érvényesíteni, és meg szeretné határozni, hogy egy adott kifizetés melyik kifizetéstípust használja. 

[Szállítói kifizetések munkaterület](vendor-payments-workspace.md)

[Szállítói kifizetési díjak meghatározása](tasks/define-vendor-payment-fees.md)

[Szállítói kifizetési feltételek meghatározása](tasks/define-vendor-payment-terms.md)

[Ellenőrzött fizetési áttekintés](positive-pay-overview.md)

[Fizetési ellenőrző fájlok beállítása és létrehozása](set-up-generate-positive-pay-files.md)

[Szállítói kifizetések készítése fizetési javaslat segítségével](create-vendor-payments-payment-proposal.md)

[Szállítói kifizetések részösszegre](vendor-payments-partial-amount.md)

[A szállítói kifizetésre vonatkozóan kiszámított engedménynél nagyobb engedmény alkalmazása](take-discount-more-calculated-discount-vendor-payment.md)

[Készpénzfizetési engedmény érvényesítése a készpénzfizetési engedményes időszakon kívül](take-cash-discount-outside-cash-discount-timeframe.md)

[Elektronikus jelentéskészítés szállítói csekkekhez](electronic-reporting-sample-vendor-checks.md)

[Szállítói kifizetés sztornózása](reverse-vendor-payment.md)

[Előlegszámlák és előlegek áttekintése](prepayments-invoices-vs-prepayments.md)

[A Kötelezettségek modul központosított kifizetései](centralized-payments-accounts-payable.md)

## <a name="settlements"></a>Kiegyenlítések

A következő témakörök a kiegyenlítésekről nyújtanak információkat. A kiegyenlítés a kifizetések rendezésének folyamata számlákkal. 

[Kiegyenlítés konfigurálása](../cash-bank-management/configure-settlement.md)

[Részleges szállítói kifizetés rendezése az engedmény dátuma előtt](settle-partial-vendor-payment-before-discount-or-final-payment-after.md)

[Részleges szállítói kifizetés rendezése, amely szállítói jóváírásokra vonatkozó engedménnyel rendelkezik](settle-partial-vendor-payment-discounts-vendor-credit-notes.md)

[Részleges szállítói kifizetés egy részének rendezése, amely több engedményes időszakkal rendelkezik](settle-partial-vendor-payment-multiple-discount-periods.md)

[Részleges szállítói kifizetés vagy végleges kifizetés rendezése az engedmény dátuma előtt](settle-partial-vendor-payment-or-final-payment-before-discount.md)

[Egyetlen bizonylat több vevő- vagy szállítórekorddal](single-voucher-multiple-customer-vendor-records.md)



### <a name="additional-resources"></a>További erőforrások

#### <a name="whats-new-and-in-development"></a>Újdonságok és fejlesztés alatt levő megoldások

Lépjen a [Microsoft Dynamics 365 Kibocsátási megjegyzések](https://go.microsoft.com/fwlink/?linkid=2010158) oldalára a tervezett új funkciók megtekintéséhez. 

#### <a name="blogs"></a>Blogok

A [Microsoft Dynamics 365 blogon](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise) és a [Microsoft Dynamics 365 Finance and Operations – Pénzügyek blogon](https://community.dynamics.com/365/financeandoperations/b/financials) véleményeket, híreket és egyéb információkat talál a Kötelezettségekkel és egyéb megoldásokkal kapcsolatban.

A [Microsoft Dynamics Operations Partner közösségi blog](https://community.dynamics.com/partner/b/operationspartnercommunityblog) egyetlen erőforrás segítségével tájékoztatja a Microsoft Dynamics-partnereket az MBS Operations új és népszerű fejlesztéseiről.

#### <a name="community-blogs"></a>Közösségi blogok

[A kötelezettségek kezelése a Dynamics 365 for Finance and Operations alkalmazásban](https://financefunction.tech/2019/02/15/how-to-manage-payables-in-dynamics-365-for-finance-and-operations)

#### <a name="task-guides"></a>Feladat-útmutatók
Feladat-útmutatók formájában további segítség áll rendelkezésre a Finance and Operations alkalmazásban. A feladat-útmutatók eléréséhez kattintson bármelyik lapon a Súgó gombjára.

#### <a name="videos"></a>Videók

Tekintse meg az útmutató-videókat, amelyek a [Microsoft Dynamics 365 YouTube csatornáján](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ) láthatók.




