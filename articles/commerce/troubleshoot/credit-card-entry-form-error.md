---
title: A hitelkártya-beviteli oldal hibát jelez a pénztárnál
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha a Fizetési mód szakasz nincs betöltve és hibaüzenetet tartalmaz.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 593c1bdb502330c5dc9f26254dbed809cea7651b
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6347392"
---
# <a name="credit-card-entry-page-shows-an-error-at-checkout"></a>A hitelkártya-beviteli oldal hibát jelez a pénztárnál

[!include [banner](../../includes/banner.md)]

Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha a **Fizetési mód** szakasz nincs betöltve és hibaüzenetet tartalmaz.

## <a name="description"></a>Leírás

Amikor megnyitja egy online áruház pénztári oldalát, a **Fizetési mód** szakasz nem töltődik be, és a következő hibaüzenet jelenik meg: „Valamilyen hiba történt. Próbálkozzon újra később.”

![Fizetési modul hibája.](media/payment-module-error.jpg)

## <a name="resolution"></a>Megoldás

### <a name="wait-for-the-commerce-scale-unit-cache-to-expire"></a>Várja meg a Commerce Scale Unit gyorsítótár lejáratát

Az online áruház pénztároldalán található fizetési szolgáltatások beállításait a rendszer a Commerce Scale Unit szolgáltatásban gyorsítótárazza, és akár 15 percig is eltarthat, hogy megjelenjen az e-kereskedelmi webhelyen. Ezen fizetési szolgáltatások beállításai tartalmazzák a kereskedői számla azonosítójának, a felhő API-kulcsának és a fizetési módhoz kapcsolódó különféle konfigurációs beállítások módosításait.

## <a name="additional-resources"></a>További erőforrások

[Online csatorna beállítása](../channel-setup-online.md)
