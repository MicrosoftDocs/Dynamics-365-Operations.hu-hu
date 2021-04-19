---
title: A Vevőrekordok nem jelennek meg a Commerce központi felületén
description: Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha a vevőrekordok nem jelennek meg azonnal a Commerce központi felületén.
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
ms.openlocfilehash: 5499e3c059c9e735df87ef8b462d446e0710d90c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801795"
---
# <a name="customer-records-dont-appear-in-commerce-headquarters"></a><span data-ttu-id="56160-103">A Vevőrekordok nem jelennek meg a Commerce központi felületén</span><span class="sxs-lookup"><span data-stu-id="56160-103">Customer records don't appear in Commerce headquarters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="56160-104">Ez a témakör olyan hibaelhárítási útmutatást tartalmaz, amely segítséget nyújt abban az esetben, ha a vevőrekordok nem jelennek meg azonnal a Commerce központi felületén.</span><span class="sxs-lookup"><span data-stu-id="56160-104">This topic provides troubleshooting guidance that can help when customer records don't immediately appear in Commerce headquarters.</span></span>

## <a name="description"></a><span data-ttu-id="56160-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="56160-105">Description</span></span>

<span data-ttu-id="56160-106">Amikor új vevőrekordot hoz létre az e-kereskedelmi üzlet bejelentkezési folyamatának használatával, a megfelelő vevőrekord nem jelenik meg azonnal a Commerce központi felületén.</span><span class="sxs-lookup"><span data-stu-id="56160-106">When you create a new customer record by using the sign-up flow in the e-commerce storefront, the corresponding customer record doesn't immediately appear in Commerce headquarters.</span></span>

## <a name="resolution"></a><span data-ttu-id="56160-107">Felbontás</span><span class="sxs-lookup"><span data-stu-id="56160-107">Resolution</span></span>

### <a name="disable-customer-creation-in-async-mode"></a><span data-ttu-id="56160-108">Vevő létrehozásának letiltása aszinkron módban</span><span class="sxs-lookup"><span data-stu-id="56160-108">Disable customer creation in async mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56160-109">Ha letiltja az aszinkron vevőlétrehozást, ez hatással lehet a rendszer teljesítményére, mivel minden rekord létrehozása valós idejű igénylést eredményez a Commerce központi felülete felé.</span><span class="sxs-lookup"><span data-stu-id="56160-109">If you disable asynchronous customer creation, system performance could be affected, because creation of each record will produce a real-time request to Commerce headquarters.</span></span> <span data-ttu-id="56160-110">Ezenkívül ha a Commerce központi felülete nem üzemel (például a szervizelési folyamatok közben), az új vevőlétrehozási folyamatok hibákat okoznak.</span><span class="sxs-lookup"><span data-stu-id="56160-110">In addition, if Commerce headquarters is down (for example, during servicing flows), any new customer creation flows will produce errors.</span></span>

<span data-ttu-id="56160-111">A következő lépésekkel tilthatja le az aszinkron vevőlétrehozást a Commerce központi felületén.</span><span class="sxs-lookup"><span data-stu-id="56160-111">To disable customer creation in async mode in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="56160-112">Ugorjon a következő elemre: **Retail és Commerce \> Csatorna beállítása \> Online üzet beállítása \> Funkcióprofilok**.</span><span class="sxs-lookup"><span data-stu-id="56160-112">Go to **Retail and Commerce \> Channel setup \> Online store setup \> Functionality profiles**.</span></span>
1. <span data-ttu-id="56160-113">Ha még nem használ funkcióprofilt az online csatornához, hozzon létre egyet.</span><span class="sxs-lookup"><span data-stu-id="56160-113">If you aren't already using a functionality profile for your online channel, create one.</span></span>
1. <span data-ttu-id="56160-114">Győződjön meg arról, hogy a **Vevő létrehozása aszinkron módban** beállítás értéke **Nem** legyen.</span><span class="sxs-lookup"><span data-stu-id="56160-114">Make sure that the **Create customer in async mode** option is set to **No**.</span></span>
1. <span data-ttu-id="56160-115">Nyissa meg a következőt: **Retail és Commerce \> Csatornák \> Online áruházak**.</span><span class="sxs-lookup"><span data-stu-id="56160-115">Go to **Retail and Commerce \> Channels \> Online stores**.</span></span>
1. <span data-ttu-id="56160-116">Válassza ki azt az online áruházat, amelynél le szeretné tiltani az aszinkron vevőlétrehozást.</span><span class="sxs-lookup"><span data-stu-id="56160-116">Select the online store to disable asynchronous customer creation for.</span></span>
1. <span data-ttu-id="56160-117">Az **Általános** lapon győződjön meg arról, hogy a **Funkcióprofil** mezőben az online csatorna által használt funkcióprofil legyen beállítva.</span><span class="sxs-lookup"><span data-stu-id="56160-117">On the **General** tab, make sure that the **Functionality profile** field is set to the functionality profile that you're using for your online channel.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="56160-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="56160-118">Additional resources</span></span>

[<span data-ttu-id="56160-119">B2C-bérlő beállítása a Commerce alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="56160-119">Setup a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)
