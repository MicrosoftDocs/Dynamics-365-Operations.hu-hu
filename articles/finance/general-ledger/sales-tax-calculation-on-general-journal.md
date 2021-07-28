---
title: Áfa számítása az általános naplósorokhoz
description: Ez a témakör azt mutatja be, hogy hogyan történik az ÁFA számítása a főkönyvi naplósorokban a különböző típusú számlákhoz (szállító, vevő, főkönyv és projekt).
author: EricWang
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: EricWang
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: c019c597f4734f92f5d9aacdff1cbb30f9fb0a60
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6358833"
---
# <a name="sales-tax-calculation-on-general-journal-lines"></a>Áfa számítása az általános naplósorokhoz
[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogy hogyan történik az ÁFA számítása a főkönyvi naplósorokban a különböző típusú számlákhoz (szállító, vevő, főkönyv és projekt).

A folyamat három lépésből állhat:

- Az áfa irányának meghatározása.

- Annak az áfa-összegnek a meghatározása, amely az ideiglenes forgalmi adó táblába kerül.

- Az áfa összegének és számlájának meghatározása a bizonylaton.

## <a name="determine-the-sales-tax-direction"></a>Az áfa irányának meghatározása

Az ÁFA irányának meghatározási módja a bizonylaton szereplő számla típusától függ. Az ÁFA irányát a számlatípus és az áfakód kombinációja határozza meg. A következő szakaszok részletezik a lehetőségeket. 

### <a name="account-type-is-project"></a>Számla típusa projekt

Ha egy bizonylat olyan naplósorral rendelkezik, amelyben a számlatípus a **Projekt**, akkor a bizonylat minden naplója ugyanarra az adózási irányra vonatkozik. Az alábbi ábra bemutatja a szabályt. A következő pontok a lehetséges adóügyi irányokat mutatják a projekt számlái esetében.

• Ha az áfakód importadó, akkor a forgalmi adó iránya importadó.

• Ha az áfakód adómentes, akkor a forgalmi adó iránya adómentes vásárlás.

• Ha az áfakód közösségen belüli áfa, akkor a forgalmi adó iránya fizetendő áfa.

• Ha az áfakód fordított áfa, akkor a forgalmi adó iránya fizetendő áfa.

Ellenkező esetben az áfa iránya a visszaigényelhető áfa.

A következő ábra grafikusan illusztrálja a szabályt.

![A projektekhez tartozó számlák adózási irányának lehetőségei.](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-vendor"></a>Számla típusa szállító

Ha egy bizonylat olyan naplósorral rendelkezik, amelyben a számlatípus a **Szállító**, akkor a bizonylat minden naplója ugyanarra az adózási irányra vonatkozik. A következő pontok a lehetséges adóügyi irányokat mutatják a szállító számlái esetében. 

• Ha az áfakód importadó, akkor a forgalmi adó iránya importadó.

• Ha az áfakód adómentes, akkor a forgalmi adó iránya adómentes vásárlás.

• Ha az áfakód közösségen belüli áfa, akkor a forgalmi adó iránya fizetendő áfa.

• Ha az áfakód fordított áfa, akkor a forgalmi adó iránya fizetendő áfa.

Ellenkező esetben az áfa iránya a visszaigényelhető áfa.

A következő ábra grafikusan illusztrálja a szabályt.

![A szállítóhoz tartozó számlák adózási irányának lehetőségei.](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-customer"></a>Számla típusa ügyfél

Ha egy bizonylat olyan naplósorral rendelkezik, amelyben a számlatípus a **Ügyfél**, akkor a bizonylat minden naplója ugyanarra az adózási irányra vonatkozik. A következő pontok a lehetséges adóügyi irányokat mutatják az ügyfél számlái esetében.

• Ha az áfakód adómentes, akkor a forgalmi adó iránya adómentes vásárlás.

• Ha az áfakód közösségen belüli áfa, akkor a forgalmi adó iránya visszaigényelhető áfa.

• Ha az áfakód fordított áfa, akkor a forgalmi adó iránya visszaigényelhető áfa.

Ellenkező esetben az áfa iránya a fizetendő áfa.

A következő ábra grafikusan illusztrálja a szabályt.

![Az ügyfélhez tartozó számlák adózási irányának lehetőségei.](media/Sales-Tax-Direction-Customer.jpg)

### <a name="account-type-is-ledger"></a>Számla típusa Főkönyv

A következő ábra bemutatja azt a szabályt, amelyet akkor kell alkalmazni, ha egy bizonylathoz csak olyan naplósorok vannak, amelyeknél a számla típusa **Főkönyv**. A következő pontok a lehetséges adóügyi irányokat mutatják a főkönyvi számlák esetében.

• Ha az áfakód importadó, akkor a forgalmi adó iránya importadó.

• Ha az áfakód adómentes, akkor a forgalmi adó iránya adómentes vásárlás.

Ellenkező esetben, ha a napló összege tartozik (pozitív), akkor az áfa iránya a visszaigényelhető áfa. Ha a napló összege követel (negatív), akkor a forgalmi adó iránya fizetendő.

A következő ábra grafikusan illusztrálja a szabályt.

![A főkönyvi számlák adózási irányának lehetőségei.](media/Sales-Tax-Direction-Ledger.jpg)

#### <a name="override-the-sales-tax-direction"></a>Az áfa irányának felülírása

Az áfa irányát felülbírálhatja, ha a bizonylat csak olyan sorokat tartalmaz, amelyekben a számla típusa **Főkönyv**.

Nyissa meg a **Főkönyv \> Számlatükör \> Számlák \> Főszámlák**, és válassza ki a **Jogi személy felülbírálások** gyorslapját.

## <a name="determine-the-sales-tax-amount"></a>Az áfa összegének meghatározása.

Ez a szakasz bemutatja az áfa összeg jel kiszámításának módját.

![Áfatranzakciók lap.](media/sales-tax-amount-sign.jpg)

A következő táblázat bemutatja az általános szabályt, amely meghatározza az áfa irányát és az áfa összegének az ideiglenes áfa táblába történő megjelölését.

| Naplósor összege | Áfa iránya  | Áfaösszeg jel |
|---------------------|----------------------|-----------------------|
| Pozitív            | Visszaigényelhető áfa | Pozitív              |
| Pozitív            | Fizetendő áfa    | Negatív              |
| Negatív            | Visszaigényelhető áfa | Negatív              |
| Negatív            | Fizetendő áfa    | Pozitív              |

Speciális szabály van az olyan bizonylatokhoz, amelyeknél csak **Projekt** vagy **Főkönyv** sor van, amikor a **Főkönyv** sorban be van jelölve egy áfacsoport vagy egy cikkáfacsoport. Ezt a szabályt a **Független áfaszámítási funkciónak a főkönyvi naplókhoz való engedélyezése** funkció vezérli. Ha ez a funkció le van tiltva, akkor a **Főkönyv** sor áfaösszege a **projekt** sorában szereplő tartozik/követel irányt használja. Ha ez a funkció be van kapcsolva, akkor a **Főkönyv** sor áfaösszege a saját tartozik/követel irányát használja. A következő táblázatokban mindegyik eset szabálya látható. 

**Szabály, amikor a funkció be van kapcsolva**

| A projekt naplósor összege | Áfa iránya  | Áfaösszeg jel |
|--------------------------------|----------------------|-----------------------|
| Pozitív                       | Visszaigényelhető áfa | Pozitív              |
| Negatív                       | Visszaigényelhető áfa | Negatív              |

**Szabály, amikor a funkció ki van kapcsolva**

| A főkönyv naplósor összege  | Áfa iránya  | Áfaösszeg jel |
|--------------------------------|----------------------|-----------------------|
| Pozitív                       | Visszaigényelhető áfa | Pozitív              |
| Negatív                       | Visszaigényelhető áfa | Negatív              |

## <a name="determine-the-sales-tax-amount-and-account-on-the-voucher"></a>Az áfa összegének és számlájának meghatározása a bizonylaton

Az áfa feladása alkalmával a fő számlát a főkönyvi feladási csoport profiljából olvassa be a rendszer. Ha a forgalmi adók visszaigényelhetők, akkor a rendszer a profilban megadott visszaigényelhető áfa számlát használja. Ha a forgalmi adók fizetendők, akkor a rendszer a profilban megadott fizetendő áfa számlát használja.

A következő táblázat az általános szabályt mutatja be.

| Áfa iránya  | Áfaösszeg jel | Áfaszámla      | Bizonylat összege |
|----------------------|-----------------------|------------------------|-------------------|
| Visszaigényelhető áfa | Pozitív              | Adó kinnlevőségek számla | Pozitív (tartozik)  |
| Visszaigényelhető áfa | Negatív              | Kinnlevőségek számla | Negatív (követel)  |
| Fizetendő áfa    | Pozitív              | Adó kötelezettségek számla    | Negatív (követel)  |
| Fizetendő áfa    | Negatív              | Adó kötelezettségek számla    | Pozitív (tartozik)  |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
