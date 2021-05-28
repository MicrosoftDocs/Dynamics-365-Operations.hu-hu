---
title: Az adószámítás teljesítménye hatással van a tranzakciókra
description: Ez a témakör az adószámítás teljesítményével és a tranzakciókra gyakorolt hatásával kapcsolatos hibaelhárítási információkat tartalmaz.
author: shtao
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 6fce4e2cb8c5507769533a875e23ccc4531abf51
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020139"
---
# <a name="tax-calculation-performance-affects-transactions"></a>Az adószámítás teljesítménye hatással van a tranzakciókra

[!include [banner](../includes/banner.md)]

Bizonyos esetekben egy tranzakcióra hatással vannak az adószámítást teljesítménybeli problémái. A probléma elhárításához igény szerint kövesse az alábbi szakaszok lépéseit.

## <a name="review-the-transaction-line-count"></a>Ellenőrizze a tranzakciósorok számát

Határozza meg, hogy a tranzakcióban nagy számú sor van-e (például több száznál is több). Ha nem, lépjen tovább a következő szakaszra. Ha a tranzakcióban több száz sor van, késleltesse az adószámítást. A további tudnivalókat lásd: [Késleltetett adószámítás engedélyezése a naplókban](enable-delayed-tax-calculation.md). 

Ezután meghatározhatja, hogy teljesülnek-e a következő feltételek:

- Nagy fájlokból importált tranzakciók vannak.
- Több munkamenet ugyanazt a tranzakciós adószámítást egyszerre dolgozza fel.
- A tranzakciónak több sora van, és a nézetek valós időben frissülnek. Például az **Általános napló** lap **Számított áfaösszeg** mezőjét a program valós időben frissíti, amikor egy sor mezői megváltoznak.

   [![Számított áfaösszeg mezője a Naplóbizonylat oldalon](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture1.png)

Ha bármelyik feltétel teljesül, késleltesse az adószámítást.

## <a name="review-the-call-stack"></a>A hívásverem áttekintése

Tekintse át a hívásvermet annak megállapításához, hogy az adószámítás többször meg van-e hívva. Ha nem, lépjen tovább a következő szakaszra. Ha a hívásverem többször is meghívott, a következő lépések segítségével csökkentheti az adószámítási időket.

1. Ha a napló figyelembe vette a tranzakciót, késleltesse az adószámítást. A további tudnivalókat lásd: [Késleltetett adószámítás engedélyezése a naplókban](enable-delayed-tax-calculation.md).
2. Ha a tranzakció beszerzési rendelés, és az alkalmazás verziója újabb, mint 10.0.15, akkor az adószámítást elhalaszthatja a végső számításig, ha engedélyezi a **PurchTableChangeMgmtDistributionUpdateOnToggle_KillSwitch** tesztelését.

## <a name="review-the-call-stack-timeline"></a>A hívásverem idősorának áttekintése

Tekintse át a hívásverem idősorát, és ellenőrizze, hogy felmerülnek-e a következő problémák. Ha ezt teszi, engedélyezze a **TaxUncommittedDoIsolateScopeFlighting** tesztelését a probléma megoldásához.

- A tranzakció következtében a rendszer ne válaszol a munkamenet befejeződéséig. Emiatt a tranzakció nem tudja kiszámítani az adóeredményt. A következő ábra megjeleníti a "Munkamenet befejeződött" üzenetmezőt, ami megjelenik.

    [![Munkamenet befejeződött üzenet](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture2.png)

- A **TaxUncommitted** metódusok több időt vesznek igénybe, mint a többi metódus. Például, az alábbi ábrán a **TaxUncommitted::updateTaxUncommitted()** metódus 43 347,42 másodpercet vesz igénybe, a többi metódus azonban 0,09 másodpercet.

    [![Metódusok időtartamai](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)](./media/tax-calculation-bad-performance-impacts-transaction-Picture3.png)

## <a name="customizing-and-calling-tax-calculation"></a>Adószámítás testreszabása és hívása

Testreszabáskor ne hívja meg az adószámítást az **insert()** vagy **update()** metódusnál minden sorhoz. Az adószámítást tranzakció szintjén kell meghívni.

## <a name="determine-whether-customization-exists"></a>Annak meghatározása, hogy létezik-e testreszabás

Ha az előző szakaszokban már befejezte a lépéseket, de nem találta meg a problémát, határozza meg, hogy van-e testreszabás. Ha nem létezik testreszabás, hozzon létre egy Microsoft szolgáltatáskérést további segítségért.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
