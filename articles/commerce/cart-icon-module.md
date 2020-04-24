---
title: Kosárikon modul
description: Ez a témakör a kosárikon modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8cc96e0476a9d8a46aed7011359dc65fbc678fbf
ms.sourcegitcommit: ac966ea3a6c557fb5f9634b187b0e788d3e82d4d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261570"
---
# <a name="cart-icon-module"></a><span data-ttu-id="f0ce8-103">Kosárikon modul</span><span class="sxs-lookup"><span data-stu-id="f0ce8-103">Cart icon module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f0ce8-104">Ez a témakör a kosárikon modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-104">This topic covers the cart icon module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f0ce8-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="f0ce8-105">Overview</span></span>

<span data-ttu-id="f0ce8-106">A kosárikon-modul a lap fejlécében a kosárat jelenti, és a kosárban található cikkek számát jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-106">The cart icon module represents the cart in the header module of the page, and shows the number of items in the cart.</span></span> <span data-ttu-id="f0ce8-107">A kosárikon modul a kosár összegzését (más néven minikosár) is megjelenít ,ha fölé viszik az egérmutatót.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-107">The cart icon module also displays a cart summary (also known as a mini cart) when the cart icon is hovered over.</span></span> <span data-ttu-id="f0ce8-108">A minikosár anélkül jeleníti meg a kosárban található cikkek összegzését a felhasználó számára, hogy a meg kellene nyitnia a kosár lapját.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-108">The mini cart provides the user with a summary of the items in the cart without having to navigate to the cart page.</span></span> <span data-ttu-id="f0ce8-109">Ezenkívül azt is lehetővé teszi a felhasználó számára, hogy közvetlenül a pénztár lapjára ugorjon, ha elégedett az összesítéssel.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-109">In addition, it also allows the user to directly go to checkout page if they are happy with the summary.</span></span> <span data-ttu-id="f0ce8-110">Ez csökkenti az oldalnavigációk számát és gyorsabban teszi a fizetést.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-110">This reduces the number of page navigations and makes checkout faster.</span></span> 

## <a name="module-properties"></a><span data-ttu-id="f0ce8-111">Modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="f0ce8-111">Module properties</span></span>

- <span data-ttu-id="f0ce8-112">**Mini-kosár megjelenítése** – Ha ennek értéke igaz, ez a tulajdonság lehetővé teszi a kosár összesítésének (mini kosár) megjelenítését, ha a kosár ikonja fölé viszik az egérmutatót.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-112">**Show mini cart** – When true, this property enables a cart summary (mini cart) to be displayed when the cart icon is hovered over.</span></span> <span data-ttu-id="f0ce8-113">Ez a funkció csak az asztali nézet portjain használható.</span><span class="sxs-lookup"><span data-stu-id="f0ce8-113">This functionality is only supported for desktop view ports.</span></span>


## <a name="add-a-cart-icon-module-to-a-page"></a><span data-ttu-id="f0ce8-114">Kosárikon modul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="f0ce8-114">Add a cart icon module to a page</span></span>

<span data-ttu-id="f0ce8-115">Egy kosárikon modul hozzáadásához lásd: [Fejléc modul](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="f0ce8-115">To add a cart icon module, see [Header module](author-header-module.md).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="f0ce8-116">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="f0ce8-116">Additional resources</span></span>

[<span data-ttu-id="f0ce8-117">Vásárlásmező-modul</span><span class="sxs-lookup"><span data-stu-id="f0ce8-117">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="f0ce8-118">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="f0ce8-118">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="f0ce8-119">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="f0ce8-119">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="f0ce8-120">Rendelésmegerősítési modul</span><span class="sxs-lookup"><span data-stu-id="f0ce8-120">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="f0ce8-121">Fejlécmodul</span><span class="sxs-lookup"><span data-stu-id="f0ce8-121">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="f0ce8-122">Láblécmodul</span><span class="sxs-lookup"><span data-stu-id="f0ce8-122">Footer module</span></span>](author-footer-module.md)
