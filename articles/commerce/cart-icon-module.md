---
title: Kosárikon modul
description: Ez a témakör a kosárikon modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: 137debe3f4cad3948d20b2902ea80e66fa74ffd4
ms.sourcegitcommit: ae0843763a8b6b232bb71db326fab28605ac6c53
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2020
ms.locfileid: "3661147"
---
# <a name="cart-icon-module"></a><span data-ttu-id="7d724-103">Kosárikon modul</span><span class="sxs-lookup"><span data-stu-id="7d724-103">Cart icon module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7d724-104">Ez a témakör a kosárikon modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="7d724-104">This topic covers the cart icon module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="7d724-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="7d724-105">Overview</span></span>

<span data-ttu-id="7d724-106">A kosárikon-modul a lap fejlécében a kosárat jelenti, és a kosárban található cikkek számát jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="7d724-106">The cart icon module represents the cart in the header module of the page, and shows the number of items in the cart.</span></span> <span data-ttu-id="7d724-107">A kosárikon modul a kosár összegzését (más néven minikosár) is megjelenít ,ha fölé viszik az egérmutatót.</span><span class="sxs-lookup"><span data-stu-id="7d724-107">The cart icon module also displays a cart summary (also known as a mini cart) when the cart icon is hovered over.</span></span> <span data-ttu-id="7d724-108">A minikosár anélkül jeleníti meg a kosárban található cikkek összegzését a felhasználó számára, hogy a meg kellene nyitnia a kosár lapját.</span><span class="sxs-lookup"><span data-stu-id="7d724-108">The mini cart provides the user with a summary of the items in the cart without having to navigate to the cart page.</span></span> <span data-ttu-id="7d724-109">Ezenkívül azt is lehetővé teszi a felhasználó számára, hogy közvetlenül a pénztár lapjára ugorjon, ha elégedett az összesítéssel.</span><span class="sxs-lookup"><span data-stu-id="7d724-109">In addition, it also allows the user to directly go to checkout page if they are happy with the summary.</span></span> <span data-ttu-id="7d724-110">Ez csökkenti az oldalnavigációk számát és gyorsabban teszi a fizetést.</span><span class="sxs-lookup"><span data-stu-id="7d724-110">This reduces the number of page navigations and makes checkout faster.</span></span> 

<span data-ttu-id="7d724-111">A következő képen egy példa látható a kosárikon modulra, amely egy minikosarat jelenít meg a Fabrikam címsorban.</span><span class="sxs-lookup"><span data-stu-id="7d724-111">The following image shows an example of a cart icon module that displays a mini cart in the Fabrikam header.</span></span>

![Példa egy kosárikon modulra](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a><span data-ttu-id="7d724-113">Modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="7d724-113">Module properties</span></span>

- <span data-ttu-id="7d724-114">**Mini-kosár megjelenítése** – Ha ennek értéke igaz, ez a tulajdonság lehetővé teszi a kosár összesítésének (mini kosár) megjelenítését, ha a kosár ikonja fölé viszik az egérmutatót.</span><span class="sxs-lookup"><span data-stu-id="7d724-114">**Show mini cart** – When true, this property enables a cart summary (mini cart) to be displayed when the cart icon is hovered over.</span></span> <span data-ttu-id="7d724-115">Ez a funkció csak az asztali nézet portjain használható.</span><span class="sxs-lookup"><span data-stu-id="7d724-115">This functionality is only supported for desktop view ports.</span></span>

## <a name="add-a-cart-icon-module-to-a-page"></a><span data-ttu-id="7d724-116">Kosárikon modul felvétele egy oldalra</span><span class="sxs-lookup"><span data-stu-id="7d724-116">Add a cart icon module to a page</span></span>

<span data-ttu-id="7d724-117">Egy kosárikon modul hozzáadásához lásd: [Fejléc modul](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="7d724-117">To add a cart icon module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7d724-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="7d724-118">Additional resources</span></span>

[<span data-ttu-id="7d724-119">Kosármodul</span><span class="sxs-lookup"><span data-stu-id="7d724-119">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="7d724-120">Fizetésmodul</span><span class="sxs-lookup"><span data-stu-id="7d724-120">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="7d724-121">Fizetési modul</span><span class="sxs-lookup"><span data-stu-id="7d724-121">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="7d724-122">Szállítási cím modul</span><span class="sxs-lookup"><span data-stu-id="7d724-122">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="7d724-123">Szállítási lehetőségek modul</span><span class="sxs-lookup"><span data-stu-id="7d724-123">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="7d724-124">Rendelési részletek modul</span><span class="sxs-lookup"><span data-stu-id="7d724-124">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="7d724-125">Ajándékutalvány modul</span><span class="sxs-lookup"><span data-stu-id="7d724-125">Gift card module</span></span>](add-giftcard.md)
