---
title: Az alapértelmezett fizetési szolgáltatáshoz kapcsolódó rendelésszinkronizálási hiba
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt az online rendelés szinkronizálása során esetleg előforduló hiba kijavítása érdekében.
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
ms.openlocfilehash: fa174bbb257379f6ce906dd21180bbcb19f8bc3f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021127"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a><span data-ttu-id="02c48-103">Az alapértelmezett fizetési szolgáltatáshoz kapcsolódó rendelésszinkronizálási hiba</span><span class="sxs-lookup"><span data-stu-id="02c48-103">Order synchronization error related to the default payment service</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="02c48-104">Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt az online rendelés szinkronizálása során esetleg előforduló hiba kijavítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="02c48-104">This topic provides troubleshooting guidance that can help fix an error that might occur when an online order is synced.</span></span>

## <a name="description"></a><span data-ttu-id="02c48-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="02c48-105">Description</span></span>

<span data-ttu-id="02c48-106">Online rendelés szinkronizálása esetén a következő hibaüzenet jelenik meg: „A hitelkártyás tranzakciók feldolgozásához szükség van egy alapértelmezett fizetési szolgáltatásra.”</span><span class="sxs-lookup"><span data-stu-id="02c48-106">When you sync an online order, you receive the following error message: "There must be a default payment service to process credit card transactions."</span></span>

![Hiányzó alapértelmezett fizetési szolgáltatással kapcsolatos hiba](media/default-payment-method-error.jpg)

## <a name="resolution"></a><span data-ttu-id="02c48-108">Felbontás</span><span class="sxs-lookup"><span data-stu-id="02c48-108">Resolution</span></span>

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a><span data-ttu-id="02c48-109">Az alapértelmezett fizetési szolgáltatás megerősítése vagy beállítása a Commerce központi felületén</span><span class="sxs-lookup"><span data-stu-id="02c48-109">Confirm or set the default payment service in Commerce headquarters</span></span>

<span data-ttu-id="02c48-110">Kövesse az alábbi lépéseket az alapértelmezett fizetési szolgáltatás megerősítéséhez vagy beállításához a Commerce központi felületén.</span><span class="sxs-lookup"><span data-stu-id="02c48-110">To confirm or set the default payment service in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="02c48-111">Ugorjon a következő oldalra: **Kinnlevőségek \> Fizetési beállítások \> Fizetési szolgáltatások**.</span><span class="sxs-lookup"><span data-stu-id="02c48-111">Go to **Accounts receivable \> Payment setup \> Payment services**.</span></span>
1. <span data-ttu-id="02c48-112">Győződjön meg arról, hogy az **Új hitelkártyák alapértelmezett feldolgozója** beállítás értéke **Igen** legyen egy fizetési szolgáltatás esetén.</span><span class="sxs-lookup"><span data-stu-id="02c48-112">Make sure that the **Default processor for new credit cards** option is set to **Yes** for one payment service.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="02c48-113">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="02c48-113">Additional resources</span></span>

[<span data-ttu-id="02c48-114">Hitelkártya beállítása, engedélyezése és rögzítése</span><span class="sxs-lookup"><span data-stu-id="02c48-114">Credit card setup, authorization, and capture</span></span>](../../finance/accounts-receivable/credit-card-authorizations.md)