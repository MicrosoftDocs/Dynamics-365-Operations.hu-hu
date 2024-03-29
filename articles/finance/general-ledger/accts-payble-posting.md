---
title: Kötelezettségek feladása
description: Ez a cikk bemutatja a kötelezettségekben konfigurált feladásokat, és példákat mutat be a feladási konfigurációkra.
author: rachel-profitt
ms.date: 01/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendPosting, VendPaymMode, VendCashDiscount, MarkupTable\_Vend, VendPaymFee
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b3593e01ed4d0a88b5816803f1d67fa7ed5e0f6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908009"
---
# <a name="accounts-payable-posting"></a>Kötelezettségek feladása

[!include [banner](../includes/banner.md)]

A Kötelezettségek modul elsődleges feladási **profilja** a szállítói feladási profil. Ez a feladási profil határozza meg a szállítói egyenlegek főkönyvbe való feladott összegző számláját. Az összegző számla egy fő számla. Más néven Kötelezettségek kereskedelmi számla.

További információ a Szállítói feladási [profilokban található](../accounts-payable/vendor-posting-profiles.md).

A Kötelezettségeknél a szállítói feladási profilon kívül számos feladási konfiguráció érhető el. A következő szakaszok további tájékoztatást tartalmaznak az egyéb feladási konfigurációkról.

## <a name="methods-of-payment-posting-accounts"></a>Fizetési módok feladási számlái

A fizetési módok határozzák meg, hogyan történik a kifizetések feladása a főkönyvbe. A kifizetések kimenetének viselkedését is szabályozják. Általában minden egyes fizetéstípushoz (például készpénzhez, csekkhez, hitelkártyához, pénzrendeléshez és banki átutaláshoz) egy fizetési mód jön létre.

A Fizetési **módok** **·** **lap** Általános gyorslapJán található Általános gyorslap Feladás szakaszában (**Kötelezettségek > Fizetés beállítása >** Fizetési módok) mezői szabályják, hogyan történik a kifizetések feladása a főkönyvbe. Előbb ki kell választania egy értéket **a Számlatípus mezőben**. A kiválasztott számlatípus szabályozza a Fizetés számla **mező viselkedését**. Javasoljuk, hogy a **Számlatípus mezőben válassza** a **Bank** **lehetőséget, majd válassza ki a bankszámlát a Kifizetés számla mezőjében.** A megközelítésnek az az előnye, hogy a rendszer feladja a kifizetést a Bank akként, amely támogatja az egyeztetést és más, készpénzzel kapcsolatos folyamatokat. A következő táblázat a feladási profil **konfigurációját mutatja be a Készpénz- és bankkezelési modul** használata esetén.

| Feladás típusa | Számla típusa | Példa fizetési számlanévre | Számla típusa | Tartozik/követel? | Elszámolási számla | Leírás |
|--------------|--------------|------------------------------|--------------|---------------|------------------|-------------|
| Bank | Bank | Amerikai Bank | Eszközhöz kapcsolódó bankszámla | Terhelés | Nem | Mindegyik fizetési módhoz adja meg a fő számlát **a Kifizetés számla mezőjében**. |

Ha nem tervezi a Készpénz- és bankkezelés használatát, **·** **válassza a Főkönyv lehetőséget a Számlatípus** **mezőben, majd válassza ki a fő számlát a Kifizetés számla mezőjében.** A következő táblázat a feladási profil konfigurációját mutatja be, ha nem **használja a** Készpénz- és bankkezelést.

| Feladás típusa | Számla típusa |Példa a kifizetési számlára | Számla típusa | Tartozik/követel? | Elszámolási számla | Leírás |
|--------------|--------------|------------------------|--------------|---------------|------------------|-------------|
| Főkönyv | Főkönyv | 100100: Amerikai Bank | Eszközök | Terhelés | Nem | Mindegyik fizetési módhoz adja meg a fő számlát **a Kifizetés számla mezőjében**. |

## <a name="bridging-accounts"></a>Áthidaló számlák

Az áthidaló feladás két lépésből áll, amely a kifizetések feladása során használatos. Nem kötelező funkció, amely például nulla egyenlegű bankszámlákhoz használható. Ez a folyamat a banki egyeztetési folyamatok minél jobb és jobb idejét biztosítja. Az első lépésben a kifizetést egy ideiglenes számlára (az áthidaló számlára) feladja a rendszer. A második lépésben a feladott bejegyzés sztornírozható és feladható a bankszámlára, amikor a kifizetés törli a bankot. Az alábbi táblázat a feladási profil konfigurációját mutatja be az áthidaló feladáshoz.

| Feladás típusa | Példa a fő számlára | Példa a fő számlanévre | Számla típusa | Tartozik/követel? | Elszámolási számla | Leírás |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Főkönyvi napló | 130725 | Nem tisztázott készpénz | Kötelezettség | Terhelés | Igen | Mindegyik fizetési módhoz adja meg a fő számlát **az Áthidaló számla mezőben**. |

A további tudnivalókat lásd [Áthidalt kifizetések beállítása és feldolgozása.](../accounts-receivable/set-up-and-process-bridged-payments.md)

## <a name="customer-cash-discounts-posting-accounts"></a>Vevő készpénzfizetési engedményének feladási számlái

Ha a szervezet gyors fizetésért kap készpénzfizetési engedményeket a szállítóktól, be kell állítania a készpénzfizetési engedmények kódjait, és meg kell adnia, hogy hogyan kell az engedményeket a főkönyvbe adni. Számos lehetőség áll rendelkezésre a vevői készpénzfizetési engedmények feladható fő számlájának megadásához.

További tájékoztatás: Készpénzfizetési [engedmények](../cash-bank-management/cash-discounts.md).

## <a name="payment-fee-posting-accounts"></a>Kifizetési díj feladási számlái

A kifizetési díjakkal automatikusan díjat lehet hozzáadni a szállítói kifizetésekhez, ha egy adott feltételkészlet érvényes. A kifizetési díjak kifizetődnek a szállítónak, de költségként is feladható a bankszámlára. Íme néhány példa:

- Ha hitelkártyával fizet, akkor a szállító a teljes kifizetés 3 százalékát felszámja.
- A bank minden $1.00 átutalást külön számláz, és az illetéket költségként elszámolja a rendszer.

Ha szállítói kifizetési díjat konfigurál, és a Költség mezőt Szállító beállításra adja, **·** **·** **a** Fő számla mező nem érhető el, és a rendszer a szállítói feladási profil alapján adja fel a díjat. Ha a Költség mezőt **Főkönyv** **beállításra** adja meg, akkor a Fő számla mezőt arra a fő számlára kell beállítania, **ahová** a kifizetési díjat fel fogják adja. Ez a fő számla általában költségszámla. Az alábbi táblázat bemutatja a kifizetési díj feladásához szükséges feladási profil konfigurációját.

| Feladás típusa | Példa a fő számlára | Példa a fő számlanévre | Számla típusa | Tartozik/követel? | Elszámolási számla | Leírás |
|--------------|----------------------|---------------------------|--------------|----------------|------------------|-------------|
| Főkönyvi napló | 618190 | Banki díj ( költség) | Költség | Terhelés | Nem | Ha **a Költség** mezőben **a** Főkönyv beállítás van megjelölve, akkor ezt a számlát kell kiválasztani **a** **Kifizetési díj lap Fő számla mezőjében.** |

További információkért lásd: [Szállítói kifizetési díjak meghatározása](../accounts-payable/tasks/define-vendor-payment-fees.md).

## <a name="charges-code-posting-accounts"></a>Költségkód-feladási számlák

Ha a sorelemek mellett a beszerzési összegeket is nyomon kell követnie, használhat költségkódokat. Előfordulhat például, hogy a szállító fuvardíjat és kezelési költséget számít fel Önnek, illetve egyes fuvarozási és kezelési díjak belső költségeit. Megadhatja, hogy ezek az összegek fel vannak-e adva a költségszámlákra, vagy hozzáadják-e őket a cikkek költség ezekhez.

A Kinnlevőségek és a Kötelezettségek számára költségkódokat hozhat létre. A költségkódok konfigurálásakor meg kell határozni a feladást. A feladás a tartozik és a követel számlát is szabályozza. Költségkódok létrehozásakor kiválaszthatja az egyes költségkódok feladási típusát. Az alábbi táblázat példákat mutat be a Kötelezettségek jellemző költségkódjára a Költségkódok **lapon**.

| Feladás típusa | Példa a fő számlára | Példa a fő számlanévre | Számla típusa | Tartozik/követel? | Elszámolási számla | Leírás |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Beszerzési illeték | Hagyja üresen a mezőt. | Nem alkalmazható | Cikk | Terhelés | Nem | **Példa egy cikk beszerzési díjára:** </p><ul><li>**Tartozás típusa** mező = **Cikk**</li><li>  **Hiteltípus** mező = Vevő **/szállító**.</li><li> A cikk feladása a készletfeladási profil fő számláját használja. |
| Rendelés, fuvardíj | 600120 | Fuvar itt: | Bevétel | Terhelés | Nem | **Példa a szállítónak kifizetett fuvarra:** </p><ul><li>**Tartozás típusa** mező = Főkönyvi **számla**</li><li> **Hiteltípus mező** = Vevő **/szállító** |
| Visszatérítés\* | 503160 | Szállítói visszatérítés (Jpega ELÁBÉ)| Költség | Jóváírás | Nem | **Példa szállítói visszatérítésre:**</p><ul><li>**Tartozás típusa** mező = Vevő **/szállító**</li><li>**Hiteltípus** mező = Főkönyvi **számla** |

\* A visszatérítésre példa a feladást csak akkor használja a program, ha a költségkód hozzá van adva egy beszerzési rendelés fejlécéhez vagy sorhoz. A Microsoft Dynamics 365 Supply Chain Management speciális visszatérítési funkcióival jobban szabályozható és automatizálható a visszatérítés. A további tudnivalókat lásd a Szállítói [visszatérítések oldalon](../../supply-chain//procurement/vendor-rebates.md).

Az előző táblázat három jellemző feladási típust mutat be, amelyek költségkódokkal használhatók. Azt kell használni, mintákat, és csak egy irányban kell használni. Nem nyújt átfogó listát az összes használható kombinációról vagy feladási típusról.

További információ a Költségkód [létrehozása csoportban található](../accounts-receivable/create-charges-codes.md).
