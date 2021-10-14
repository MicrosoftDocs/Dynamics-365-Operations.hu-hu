---
title: Vállalatközi kereskedelem beállítása
description: Ez a témakör a vállalatközi kereskedelem beállítását ismerteti
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 75d6679152a056f6883658911f93464252e5fe87
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548298"
---
# <a name="set-up-intercompany-trade"></a>Vállalatközi kereskedelem beállítása

[!include [banner](../../includes/banner.md)]

A Microsoft Dynamics 365 Supply Chain Management vállalatközi kereskedelem működésének engedélyezéséhez be kell állítani a vevők és szállítók vállalatközi kereskedelmét. Be kell állítania a Beszerzés és forrás, Kötelezettségek, Kinnlevőségek és Értékesítés és marketing funkciókat is.

## <a name="before-you-set-up-intercompany-trade"></a>A vállalatközi kereskedelem beállítása előtt

A vállalatközi kereskedelem beállítása előtt el kell döntenie, hogy vevői közül melyek vállalatközi vevők, illetve a szállítók közül melyek vállalatközi szállítók. A Microsoft Dynamics 365 Supply Chain Management minden egyes jogi személyére egyenként meg kell határoznia, hogy az adott vállalatközi vevő vagy szállító esetén a vállalatközi kereskedelmi kapcsolatra melyik kereskedelmi szabály vonatkozzon.

Különösen ajánljuk, hogy Ön és szervezete ismerkedjen meg a vállalatközi paraméterekkel.

- A beállítások következményeit tárgyalja meg az egyes jogi személyek vállalatközi kereskedelemért felelős vezetőkkel.
- Állítsa be az egyes jogi személyekhez a megfelelő értékeket.

## <a name="set-up-trading-relations"></a>Kereskedelmi kapcsolatok beállítása

A vállalatközi kereskedelem beállításához az ügyfelekhez és szállítókhoz, kövesse az alábbi lépéseket.

1. Nyissa meg a **Kinnlevőségek \> Vevők \> Minden vevő** lehetőséget.
1. Válasszon ki egy vevőt.
1. A Műveleti ablaktábla **Általános** lapján válassza a **Vállalatközi** menüpontot.
1. Vállalatközi beállítási paraméterek megadása a vevői fiókhoz. A paraméterek közé tartozik a megfelelő szállítót és a szállítói számlát tartalmazó jogi személy. A paraméterek közé tartoznak továbbá a beszerzési rendelések irányelvei, az értékesítési rendelések irányelvei, az értékleképezés, valamint az értékesítési és beszerzési szerződésekre vonatkozó irányelvek. Megadhatja azt is, hogy a vevői számláról vagy a másik jogi személy szállítói számlájáról származó alapadatokat használja-e.
1. Ismételje meg az 1–4. lépéseket a jogi személy fennmaradó vállalatközi vevői kapcsán.
1. Nyissa meg a következőt: **Kötelezettségek \> Szállítók \> Minden szállító**.
1. Válasszon ki egy szállítói számlát.
1. A Műveleti ablaktábla **Általános** lapján válassza a **Vállalatközi** menüpontot.
1. Vállalatközi beállítási paraméterek megadása a szállítói fiókhoz. A paraméterek közé tartozik a megfelelő vevőt és a vevőfiókot tartalmazó jogi személy. A paraméterek közé tartoznak továbbá az értékesítési rendelések irányelvei, a beszerzési rendelések irányelvei, az értékleképezés, valamint a beszerzési és értékesítési szerződésekre vonatkozó irányelvek. Megadhatja azt is, hogy a szállítói számláról vagy a másik jogi személy vevői számlájáról származó alapadatokat használja-e.
1. Ismételje meg az 6–9. lépéseket a jogi személy fennmaradó vállalatközi szállítói kapcsán.

## <a name="set-up-products"></a>Termékek beállítása

A vállalatközi kereskedelem beállításához az ügyfelekhez és szállítókhoz, kövesse az alábbi lépéseket.

1. Lépjen a **Termékinformációk kezelése \> Termékek \> Minden termék és alaptermék** részre.
1. Definiálja azokat a termékeket, amelyek ki vannak adva a vállalatközi kereskedelemben használni kívánt jogi személyeknek.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
