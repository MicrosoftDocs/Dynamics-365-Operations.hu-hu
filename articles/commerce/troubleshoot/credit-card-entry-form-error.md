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
ms.openlocfilehash: ea9105481e6c5812565f0d3604906c905bcb5443
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018506"
---
# <a name="credit-card-entry-page-shows-an-error-at-checkout"></a><span data-ttu-id="1ac6f-103">A hitelkártya-beviteli oldal hibát jelez a pénztárnál</span><span class="sxs-lookup"><span data-stu-id="1ac6f-103">Credit card entry page shows an error at checkout</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1ac6f-104">Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha a **Fizetési mód** szakasz nincs betöltve és hibaüzenetet tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="1ac6f-104">This topic provides troubleshooting guidance that can help when the **Payment method** section isn't loaded and shows an error message.</span></span>

## <a name="description"></a><span data-ttu-id="1ac6f-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="1ac6f-105">Description</span></span>

<span data-ttu-id="1ac6f-106">Amikor megnyitja egy online áruház pénztári oldalát, a **Fizetési mód** szakasz nem töltődik be, és a következő hibaüzenet jelenik meg: „Valamilyen hiba történt.</span><span class="sxs-lookup"><span data-stu-id="1ac6f-106">When you open the checkout page of an online store, the **Payment method** section isn't loaded, and the following error message is shown: "Something went wrong.</span></span> <span data-ttu-id="1ac6f-107">Próbálkozzon újra később.”</span><span class="sxs-lookup"><span data-stu-id="1ac6f-107">Please try again later."</span></span>

![Fizetési modul hibája](media/payment-module-error.jpg)

## <a name="resolution"></a><span data-ttu-id="1ac6f-109">Felbontás</span><span class="sxs-lookup"><span data-stu-id="1ac6f-109">Resolution</span></span>

### <a name="wait-for-the-commerce-scale-unit-cache-to-expire"></a><span data-ttu-id="1ac6f-110">Várja meg a Commerce Scale Unit gyorsítótár lejáratát</span><span class="sxs-lookup"><span data-stu-id="1ac6f-110">Wait for the Commerce Scale Unit cache to expire</span></span>

<span data-ttu-id="1ac6f-111">Az online áruház pénztároldalán található fizetési szolgáltatások beállításait a rendszer a Commerce Scale Unit szolgáltatásban gyorsítótárazza, és akár 15 percig is eltarthat, hogy megjelenjen az e-kereskedelmi webhelyen.</span><span class="sxs-lookup"><span data-stu-id="1ac6f-111">The payment service settings on the online store's checkout page are cached on the Commerce Scale Unit and can take up to 15 minutes to appear on the e-commerce site.</span></span> <span data-ttu-id="1ac6f-112">Ezen fizetési szolgáltatások beállításai tartalmazzák a kereskedői számla azonosítójának, a felhő API-kulcsának és a fizetési módhoz kapcsolódó különféle konfigurációs beállítások módosításait.</span><span class="sxs-lookup"><span data-stu-id="1ac6f-112">These payment service settings include changes to the merchant account ID, cloud API key, and various configuration settings that are related to the payment method.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1ac6f-113">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1ac6f-113">Additional resources</span></span>

[<span data-ttu-id="1ac6f-114">Online csatorna beállítása</span><span class="sxs-lookup"><span data-stu-id="1ac6f-114">Set up an online channel</span></span>](../channel-setup-online.md)
