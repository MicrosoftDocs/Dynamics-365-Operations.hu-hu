---
title: Áfameghatározás főkönyvi tranzakció jelentésenként
description: Ez a témakör azt mutatja be, hogyan lehet a főkönyvi tranzakció jelentés alapján az ÁFA-specifikációt az ÁFA kiszámításához használt főkönyvi tranzakciókra vonatkozó adatok megjelenítésére és kinyomtatására használni.
author: ericwang
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-19
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: f835f06c190f1d174fbde6b68f189b0484a7b39610bc2edc0676a3e2fa320268
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6721755"
---
# <a name="sales-tax-specification-by-ledger-transaction-report"></a>Áfameghatározás főkönyvi tranzakció jelentésenként
[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet a **főkönyvi tranzakció jelentés alapján az ÁFA-specifikációt** az ÁFA kiszámításához használt főkönyvi tranzakciókra vonatkozó adatok megjelenítésére és kinyomtatására használni.

## <a name="tax-accounts-vs-non-tax-accounts"></a>Adóügyi és nem adóügyi számlák

A **főkönyvi tranzakció jelentés szerinti ÁFA-meghatározás** mind az adóügyi, mind a nem adóügyi számlákra vonatkozó adózási tranzakciókat jeleníti meg. Ezeket a számlákat a következő módon sorolják be:

- **Adóügyi számla** – A számlát adóügyi számlának kell tekinteni, amikor egy adózási tranzakció fel van adva, és az **áfakód** sorában a fő számla egy adóügyi számla, például egy fizetendő forgalmiadó-számla vagy egy visszaigényelhető forgalmiadó számla.
- **Nem adóügyi számla** – A számlát nem adóügyi számlának kell tekinteni, amikor egy adózási tranzakció fel van adva, és az eredeti tranzakció fő számlája nem adóügyi számla, például egy forgalmi számla vagy egy költségszámla.

Az adóbevallások esetében a jelentés **Eredet**, **Visszaigényelhető áfa** és **Fizetendő áfa** oszlopa **0** (nulla). A nem adóügyi számláknál az oszlopok összegeket jelenítenek meg.

## <a name="filtering-the-data-on-the-report"></a>A jelentésen látható adatok szűrése

Ennek a jelentésnek a létrehozásakor a következő alapértelmezett mezők állnak rendelkezésre. Ezekkel a mezőkkel szűrheti a jelentésben megjelenített adatokat.

| Mező                      | Leírás |
|----------------------------|-------------|
| Dátum                       | A **Kezdő** és a **Záró** szakasz mezőivel meghatározhatja az adózási tranzakciók dátumtartományát. |
| Fő számla               | A **Kezdő** és a **Záró** szakasz mezőivel meghatározhatja a fő számlák tartományát. |
| Áfakód             | A **Kezdő** és a **Záró** szakasz mezőivel meghatározhatja az áfakódok tartományát. |
| Csoportosítás                   | Annak megadása, hogy a jelentést főkönyvi számla vagy áfakód szerint kell csoportosítani. |
| Részösszeg áfakód szerint | Ez a beállítás **Igen** értékre állítható a részösszegek áfakód szerinti megjelenítéséhez. |
| Csak összegek                | Az **Igen** értékre állítása esetén csak az összesítések jelennek meg. |
| Csak a fő számlák         | Ezt a beállítást **Igen** értékre állítva a jelentésben csak a fő számlák szerepelnek. |

## <a name="showing-only-non-tax-accounts-on-the-report"></a>Csak a nem adóügyi számlák megjelenítése a jelentésben

Ha csak a nem adóügyi számlákat szeretné megjeleníteni a jelentésben, állítsa be a szűrési feltételt, például csillag (\*), ahogy az a következő ábrán látható.

![Nem adóügyi számlákat mutató jelentés.](media/taxspecperledgertrans.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]