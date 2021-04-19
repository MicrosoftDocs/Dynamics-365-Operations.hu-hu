---
title: Az alapértelmezett fizetési szolgáltatáshoz kapcsolódó rendelésszinkronizálási hiba
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt az online rendelés szinkronizálása során esetleg előforduló hiba kijavítása érdekében.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: 45eeae751051b58e1c9e725eb4ed4b5240026e7f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801435"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a><span data-ttu-id="be83a-103">Az alapértelmezett fizetési szolgáltatáshoz kapcsolódó rendelésszinkronizálási hiba</span><span class="sxs-lookup"><span data-stu-id="be83a-103">Order synchronization error related to the default payment service</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="be83a-104">Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt az online rendelés szinkronizálása során esetleg előforduló hiba kijavítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="be83a-104">This topic provides troubleshooting guidance that can help fix an error that might occur when an online order is synced.</span></span>

## <a name="description"></a><span data-ttu-id="be83a-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="be83a-105">Description</span></span>

<span data-ttu-id="be83a-106">Online rendelés szinkronizálása esetén a következő hibaüzenet jelenik meg: „A hitelkártyás tranzakciók feldolgozásához szükség van egy alapértelmezett fizetési szolgáltatásra.”</span><span class="sxs-lookup"><span data-stu-id="be83a-106">When you sync an online order, you receive the following error message: "There must be a default payment service to process credit card transactions."</span></span>

![Hiányzó alapértelmezett fizetési szolgáltatással kapcsolatos hiba](media/default-payment-method-error.jpg)

## <a name="resolution"></a><span data-ttu-id="be83a-108">Felbontás</span><span class="sxs-lookup"><span data-stu-id="be83a-108">Resolution</span></span>

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a><span data-ttu-id="be83a-109">Az alapértelmezett fizetési szolgáltatás megerősítése vagy beállítása a Commerce központi felületén</span><span class="sxs-lookup"><span data-stu-id="be83a-109">Confirm or set the default payment service in Commerce headquarters</span></span>

<span data-ttu-id="be83a-110">Kövesse az alábbi lépéseket az alapértelmezett fizetési szolgáltatás megerősítéséhez vagy beállításához a Commerce központi felületén.</span><span class="sxs-lookup"><span data-stu-id="be83a-110">To confirm or set the default payment service in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="be83a-111">Ugorjon a következő oldalra: **Kinnlevőségek \> Fizetési beállítások \> Fizetési szolgáltatások**.</span><span class="sxs-lookup"><span data-stu-id="be83a-111">Go to **Accounts receivable \> Payment setup \> Payment services**.</span></span>
1. <span data-ttu-id="be83a-112">Győződjön meg arról, hogy az **Új hitelkártyák alapértelmezett feldolgozója** beállítás értéke **Igen** legyen egy fizetési szolgáltatás esetén.</span><span class="sxs-lookup"><span data-stu-id="be83a-112">Make sure that the **Default processor for new credit cards** option is set to **Yes** for one payment service.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="be83a-113">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="be83a-113">Additional resources</span></span>

[<span data-ttu-id="be83a-114">Hitelkártya beállítása, engedélyezése és rögzítése</span><span class="sxs-lookup"><span data-stu-id="be83a-114">Credit card setup, authorization, and capture</span></span>](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/credit-card-authorizations)
