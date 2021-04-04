---
title: Az alapértelmezett fizetési szolgáltatáshoz kapcsolódó rendelésszinkronizálási hiba
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt az online rendelés szinkronizálása során esetleg előforduló hiba kijavítása érdekében.
author: Reza-Assadi
manager: AnnBe
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
ms.openlocfilehash: dd7c400f26b6fc7fbe1d4fec43a52295eb363333
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585351"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a><span data-ttu-id="d5a20-103">Az alapértelmezett fizetési szolgáltatáshoz kapcsolódó rendelésszinkronizálási hiba</span><span class="sxs-lookup"><span data-stu-id="d5a20-103">Order synchronization error related to the default payment service</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d5a20-104">Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt az online rendelés szinkronizálása során esetleg előforduló hiba kijavítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="d5a20-104">This topic provides troubleshooting guidance that can help fix an error that might occur when an online order is synced.</span></span>

## <a name="description"></a><span data-ttu-id="d5a20-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="d5a20-105">Description</span></span>

<span data-ttu-id="d5a20-106">Online rendelés szinkronizálása esetén a következő hibaüzenet jelenik meg: „A hitelkártyás tranzakciók feldolgozásához szükség van egy alapértelmezett fizetési szolgáltatásra.”</span><span class="sxs-lookup"><span data-stu-id="d5a20-106">When you sync an online order, you receive the following error message: "There must be a default payment service to process credit card transactions."</span></span>

![Hiányzó alapértelmezett fizetési szolgáltatással kapcsolatos hiba](media/default-payment-method-error.jpg)

## <a name="resolution"></a><span data-ttu-id="d5a20-108">Felbontás</span><span class="sxs-lookup"><span data-stu-id="d5a20-108">Resolution</span></span>

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a><span data-ttu-id="d5a20-109">Az alapértelmezett fizetési szolgáltatás megerősítése vagy beállítása a Commerce központi felületén</span><span class="sxs-lookup"><span data-stu-id="d5a20-109">Confirm or set the default payment service in Commerce headquarters</span></span>

<span data-ttu-id="d5a20-110">Kövesse az alábbi lépéseket az alapértelmezett fizetési szolgáltatás megerősítéséhez vagy beállításához a Commerce központi felületén.</span><span class="sxs-lookup"><span data-stu-id="d5a20-110">To confirm or set the default payment service in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="d5a20-111">Ugorjon a következő oldalra: **Kinnlevőségek \> Fizetési beállítások \> Fizetési szolgáltatások**.</span><span class="sxs-lookup"><span data-stu-id="d5a20-111">Go to **Accounts receivable \> Payment setup \> Payment services**.</span></span>
1. <span data-ttu-id="d5a20-112">Győződjön meg arról, hogy az **Új hitelkártyák alapértelmezett feldolgozója** beállítás értéke **Igen** legyen egy fizetési szolgáltatás esetén.</span><span class="sxs-lookup"><span data-stu-id="d5a20-112">Make sure that the **Default processor for new credit cards** option is set to **Yes** for one payment service.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d5a20-113">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="d5a20-113">Additional resources</span></span>

[<span data-ttu-id="d5a20-114">Hitelkártya beállítása, engedélyezése és rögzítése</span><span class="sxs-lookup"><span data-stu-id="d5a20-114">Credit card setup, authorization, and capture</span></span>](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/credit-card-authorizations)
