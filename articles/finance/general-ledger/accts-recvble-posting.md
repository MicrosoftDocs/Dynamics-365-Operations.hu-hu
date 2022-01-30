---
title: Kinnlevőségek feladása
description: Ez a témakör bemutatja a kinnlevőségekben konfigurált feladásokat, és példákkal szolgál a feladási konfigurációkra.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustPaymMode, CustCashDiscount, CommissionPosting, MarkupTable\_Cust, CustPaymFee
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e664c42461e4f2995cac9a747d85d0f2a0fdf85
ms.sourcegitcommit: 96f936267d3f314f06da6ce6f809eba2ec3b205f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/24/2022
ms.locfileid: "8021588"
---
# <a name="accounts-receivable-posting"></a>Kinnlevőségek feladása

[!include [banner](../includes/banner.md)]

A Kinnlevőségek modul elsődleges feladási **profilja** a vevői feladási profil. Ez a feladási profil határozza meg a vevői egyenlegek főkönyvbe való feladott összegző számláját. Az összegző számla egy fő számla. Kinnlevőségek kereskedelmi számlának is nevezik.

A további információkat lásd: [Vevői feladási profilok](../accounts-receivable/customer-posting-profiles.md).

A Kinnlevőségek között a vevői feladási profilon kívül több feladási konfiguráció is elérhető. A következő szakaszok további tájékoztatást tartalmaznak az egyéb feladási konfigurációkról.

## <a name="posting-accounts-for-methods-of-payment"></a>Fizetési módok feladási számlái

A fizetési módok határozzák meg, hogyan történik a kifizetések feladása a főkönyvbe. A kifizetések kimenetének viselkedését is szabályozják. Általában minden olyan fizetési típushoz létrehoznak egy fizetési módot, amit a szervezet elfogad (például készpénz, csekk, hitelkártya, pénzrendelés és átutalás).

Az Általános gyorsábra Feladás szakaszának mezői szabályják a kifizetéseknek **a** főkönyvbe történő **feladását**. Előbb ki kell választania egy értéket a **Számlatípus** mezőben. A kiválasztott számlatípus szabályozza a Fizetés számla mező **viselkedését**. Javasoljuk, hogy a Számlatípus mezőben válassza a Bank lehetőséget, majd válassza ki a bankszámlát a Kifizetés **számla** **·** **mezőjében**. Ennek a megközelítésnek az az előnye, hogy a rendszer feladja a kifizetést a Bank akként, amely támogatja az egyeztetést és más, készpénzzel kapcsolatos folyamatokat. A következő táblázat a feladási profil konfigurációját mutatja be a Készpénz- és **bankkezelési modul** használata esetén.

| Feladás típusa | Számla típusa | Példa a fő számlanévre | Számla típusa | Tartozik/követel? | Elszámolási számla | Leírás |
|--------------|--------------|---------------------------|--------------|---------------|------------------|-------------|
| Bank | Bank | Contosoi Bank | Eszközhöz kapcsolódó bankszámla | Követel | Nem | Mindegyik fizetési módhoz adja meg a fő számlát a Kifizetés számla **mezőjében**. |

Ha nem tervezi a Készpénz- és bankkezelés használatát, akkor a Számlatípus mezőben válassza a Főkönyv lehetőséget, majd válassza ki a fő számlát a Kifizetés **számla** **·** **mezőjében**. A következő táblázat a feladási profil konfigurációját mutatja be, ha nem használja a Készpénz- és bankkezelést.

| Feladás típusa | Számla típusa | Példa a fő számlanévre | Számla típusa | Tartozik/követel? | Elszámolási számla | Leírás |
|--------------|--------------|---------------------------|--------------|---------------|------------------|-------------|
| Ledger | Ledger | 100100: Contoso Bank | Eszközök | Követel | Nem | Mindegyik fizetési módhoz adja meg a fő számlát a Kifizetés számla **mezőjében**. |

## <a name="bridging-accounts"></a>Áthidaló számlák

Az áthidaló feladás két lépésből áll, amely a kifizetések feladása során használatos. Nem kötelező funkció, amely például nulla egyenlegű bankszámlákhoz használható. Ez a folyamat a banki egyeztetési folyamatok minél jobb és jobb idejét biztosítja. Az első lépésben a kifizetést egy ideiglenes számlára (az áthidaló számlára) feladja a rendszer. A második lépésben a feladott bejegyzés sztornírozható és feladható a bankszámlára, amikor a kifizetés törli a bankot. Az alábbi táblázat a feladási profil konfigurációját mutatja be az áthidaló feladáshoz.

| Feladás típusa | Példa a fő számlára | Példa a fő számlanévre | Számla típusa | Tartozik/követel? | Elszámolási számla | Leírás |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Főkönyvi napló | 130725 | Nem tisztázott készpénz | Kötelezettség | Tartozik | Igen | Mindegyik fizetési módhoz adja meg a fő számlát az **Áthidaló számla** mezőben. |

További tájékoztatás: Áthidalt kifizetések beállítása [és](../accounts-receivable/set-up-and-process-bridged-payments.md) feldolgozása.

## <a name="posting-accounts-for-customer-cash-discounts"></a>Vevői készpénzfizetési engedmények feladási számlái

Ha a szervezet gyors fizetésért készpénzfizetési engedményeket kínál a vevőknek, be kell állítania a készpénzfizetési engedmények kódjait, és meg kell adnia, hogy hogyan kell az engedményeket a főkönyvbe adni. Számos lehetőség áll rendelkezésre a vevői készpénzfizetési engedmények feladható fő számlájának megadásához.

A további tudnivalókat lásd: [Készpénzfizetési](../cash-bank-management/cash-discounts.md) engedmények.

## <a name="posting-accounts-for-payment-fees"></a>Kifizetési díjak feladási számlái

A kifizetési díjakkal automatikusan díjat lehet hozzáadni a vevői kifizetéshez, ha a feltételek egy része érvényes. A kifizetési díjak a vevőnek, illetve a bankszámlára is feladhatóak költségként. Íme néhány példa:

- Ha hitelkártyával fizet, a vevőknek a teljes kifizetés 3 százalékát kell felszám fizetnie.
- A bank minden $1.00 átutalást külön számláz, és az átutalási díjat külön költségként elszámolja a rendszer.

A vevői kifizetési díjak konfigurálásakor a Költség mező Beállítása Vevő, a Fő számla mező nem érhető el, és a rendszer a vevői feladási profil alapján adja fel **a** **·** **díjat**. Ha a Költség mezőt Főkönyv beállításra adja meg, akkor a Fő számla mezőt arra a fő számlára kell beállítania, ahová a kifizetési díjat **fel** fogják **·** **adja**. Ez a fő számla általában költségszámla. Az alábbi táblázat bemutatja a kifizetési díj feladásához szükséges feladási profil konfigurációját.

| Feladás típusa | Példa a fő számlára | Példa a fő számlanévre | Számla típusa | Tartozik/követel? | Elszámolási számla | Leírás |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Főkönyvi napló | 618190 | Banki díj ( költség) | Költség | Tartozik | Nem |  Ha a Költség mezőben a Főkönyv beállítás van megjelölve, akkor ezt a számlát kell kiválasztani a kifizetési **díj** **·** **főszámla** mezőjében. |

További információkért lásd: [Vevői kifizetési díjak kialakítása](../accounts-receivable/tasks/establish-customer-payment-fees.md).

## <a name="posting-accounts-for-charges-codes"></a>Költségkódok feladási számlái

Ha a sorelemek mellett az értékesítési összegeket is nyomon kell követnie, használhat költségkódokat. A vevőknek például fel lehet fizetni a szállítási és kezelési díjakat, illetve egyes fuvarozási és kezelési díjak belső költségeit is. Megadhatja, hogy ezek az összegek fel vannak-e adva a költségszámlákra, vagy hozzáadják-e őket a cikkek költség ezekhez.

A Kinnlevőségek és a Kötelezettségek számára költségkódokat hozhat létre. A költségkódok konfigurálásakor meg kell határozni a feladást. A feladás a tartozik és a követel számlát is szabályozza. Minden létrehozott költségkódhoz ki lehet választani a használt feladási típust. Az alábbi táblázat a Kinnlevőségek között található jellemző költségkódokat mutatja be.

| Feladás típusa | Példa a fő számlára | Példa a fő számlanévre | Számla típusa | Tartozik/követel? | Elszámolási számla | Leírás |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Kifizetési illeték | 411400 | Bevétel - díjak | Bevétel | Követel | Nem | **Példa nem elegendő fedezetre:** tartozik vevői/szállítói és követel főkönyvi számla |
| Rendelés, fuvardíj | 403500 | Bevétel - fuvardíj | Bevétel | Követel | Nem | **Példa a vevőnek terhelt szállításra:** tartozik vevői/szállítói és követel főkönyvi számla |
| Visszatérítés\* | 403200 | Kedvezmény | Bevétel | Tartozik | Nem | **Példa vevői visszatérítésre:** tartozik főkönyvi számla és követel vevő/szállító |

\* A visszatérítésre példa a feladást csak akkor használja a program, ha a költségkód hozzá van adva egy beszerzési rendelés fejlécéhez vagy sorhoz. A Microsoft speciális visszatérítési funkcióival jobban szabályozható és Dynamics 365 Supply Chain Management automatizálható a visszatérítés. További információ a Vevői [visszatérítések oldalon](../../supply-chain/sales-marketing/tasks/process-customer-rebates.md) található.

Az előző táblázat három jellemző feladási típust mutat be, amelyek költségkódokkal használhatók. Azt kell használni, mint egy irányt és egy minta. Nem nyújt átfogó listát az összes használható kombinációról vagy feladási típusról.

További információ a Költségkód [létrehozása csoportban](../accounts-receivable/create-charges-codes.md) található.

## <a name="posting-accounts-for-commissions"></a>Jutalékok feladási számlái

A rendszer tetszés szerint úgy is beállítható, hogy az adott értékesítési rendelés esetén az üzletkötők vagy üzletkötők egy csoportja jutalékát számítsa ki. Ha engedélyezi ezt a funkciót, be kell állítania a jutalék kiszámításához használt feladási számlát. Ezt a konfigurációt az Értékesítés és marketing modul Jutalék **feladási** **lapján lehet** elkönyvelni.

A további tudnivalókat [lásd: Értékesítési jutalékszabályok](../../supply-chain/sales-marketing/tasks/set-up-sales-commission-rules.md) beállítása.
