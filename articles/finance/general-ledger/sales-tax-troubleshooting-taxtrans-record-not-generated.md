---
title: A TaxTrans-rekord nem jön létre
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítséget nyújtnak, arra az esetre ha egy TaxTrans rekord nem jön létre.
author: qire
ms.date: 04/13/2021
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
ms.openlocfilehash: 82b00387e39b88e1ab2bc27d9dbc4e36aac3a7a605c04669171997ba236ae39a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751302"
---
# <a name="taxtrans-record-isnt-generated"></a>A TaxTrans-rekord nem jön létre

[!include [banner](../includes/banner.md)]

Ha egy tranzakcióhoz a **Feladott áfa** lehetőséget választja, de a **Feladott áfa** lapon vagy nincsenek adósorok, vagy hiányzik egy adósor, akkor előfordulhat, hogy a **TaxTrans** rekord nem lett létrehozva.

[![Feladott, sorelemeket nem tartalmazó áfaoldal.](./media/taxtrans-is-not-generated-Picture1.png)](./media/taxtrans-is-not-generated-Picture1.png)

A probléma elhárításához igény szerint kövesse az alábbi szakaszok lépéseit.

## <a name="check-the-sales-tax-before-you-post-the-transaction"></a>Az áfa ellenőrzése a tranzakció feladása előtt

1. Mielőtt feladja a tranzakciót, a **Számla feladása** lapon válassza az **Áfa** lehetőséget a számítás ellenőrzéséhez.

    [![Áfa gomb a Számla feladása lapon.](./media/taxtrans-is-not-generated-Picture2.png)](./media/taxtrans-is-not-generated-Picture2.png)

2. Az **Ideiglenes áfatranzakciók** lapon ellenőrizze a számítás eredményét. Ha nincs kiszámítva adó, akkor lásd: [Az adó nincs kiszámítva, vagy az adó összege nulla](sales-tax-troubleshooting-tax-not-calculated-amount-zero.md).

## <a name="find-the-taxtrans-record-in-all-posted-sales-tax"></a>A TaxTrans rekord megkeresése az összes feladott áfa között

1. Ugorjon az **Adó** \> **Igénylések és jelentések** \> **Áfaigénylések** > **Feladott áfa** pontra.
2. A **Bizonylat** oszlop fejlécében válassza ki a szűrőszimbólumot a **TaxTrans** rekord megkereséséhez.
3. Ha a keresett áfarekordokat megtalálja, ellenőrizze a dátumot. Ha a dátum eltér a naplófejléc dátumától, hozzon létre egy Microsoft szolgáltatáskérést további segítségért.

    [![Feladott áfa oldal.](./media/taxtrans-is-not-generated-Picture4.png)](./media/taxtrans-is-not-generated-Picture4.png)

## <a name="debug-to-check-details"></a>Hibakeresés a részletek ellenőrzéshez

1. További információért a hibakeresésről és annak megállapításához, hogy a **TmpTaxWorkTrans** és a **TaxUncommitted** helyesen van-e létrehozva lásd a [TaxTrans mezőértéke helytelen](sales-tax-troubleshooting-field-value-taxtrans-incorrect.md) részt.
2. Ha a **TaxTmpWorkTrans** vagy a **TaxUncommitted** helyesen van létrehozva, adjon meg egy töréspontot a **TaxPost::SaveAndPost()** és a **Tax::SaveAndPost()** helyen, hogy meghatározza, miért nem lett beszúrva a **TaxTrans**.

    [![Kódhoz hozzáadott töréspontok.](./media/taxtrans-is-not-generated-Picture5.png)](./media/taxtrans-is-not-generated-Picture5.png)

    [![A hozzáadott töréspontok eredményei.](./media/taxtrans-is-not-generated-Picture6.png)](./media/taxtrans-is-not-generated-Picture6.png)

## <a name="determine-whether-customization-exists"></a>Annak meghatározása, hogy létezik-e testreszabás

Ha az előző szakaszokban már befejezte a lépéseket, de nem találta meg a problémát, határozza meg, hogy van-e testreszabás. Ha nem létezik testreszabás, hozzon létre egy Microsoft szolgáltatáskérést további segítségért.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
