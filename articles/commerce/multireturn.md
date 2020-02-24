---
title: Több vevői rendelést és számlát érintő visszárucikkek
description: Ez a témakör azt mutatja be, hogy hogyan lehet több vevői rendelést és számlát érintő visszárukat engedélyezni a Dynamics 365 Commerce alkalmazásban.
author: josaw1
manager: AnnBe
ms.date: 03/05/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: c5f17424f0837344030f9ce2d2d037cde08c4e49
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004458"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="fde3f-103">Több vevői rendelést és számlát érintő visszárucikkek</span><span class="sxs-lookup"><span data-stu-id="fde3f-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="fde3f-104">A visszáruk több rendelést és számlát is érinthetnek.</span><span class="sxs-lookup"><span data-stu-id="fde3f-104">Returns can be made across multiple orders and invoices.</span></span> 

## <a name="configure-commerce-to-support-returns-across-multiple-customer-order-and-invoices"></a><span data-ttu-id="fde3f-105">A Commerce konfigurálása a több vevői rendelést és számlát érintő visszáruk támogatásához</span><span class="sxs-lookup"><span data-stu-id="fde3f-105">Configure Commerce to support returns across multiple customer order and invoices</span></span>

1. <span data-ttu-id="fde3f-106">Lépjen a **Commerce paraméterek \> Vevői rendelések** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="fde3f-106">Go to **Commerce parameters \> Customer orders**.</span></span>
1. <span data-ttu-id="fde3f-107">Kapcsolja be a **Visszáruk engedélyezése több rendelésre vonatkozóan** paramétert.</span><span class="sxs-lookup"><span data-stu-id="fde3f-107">Turn on the **Enable returns for multiple orders** parameter.</span></span> 

## <a name="process-returns"></a><span data-ttu-id="fde3f-108">Visszáruk feldolgozása</span><span class="sxs-lookup"><span data-stu-id="fde3f-108">Process returns</span></span>

<span data-ttu-id="fde3f-109">A paraméter engedélyezése és a módosítások üzletekkel történő szinkronizálása után az üzlet pénztárosa több értékesítési rendelést is kiválaszthat egy vevő visszáruihoz.</span><span class="sxs-lookup"><span data-stu-id="fde3f-109">After the parameter is turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="fde3f-110">Ha kijelölte a rendeléseket, megjelenik a rendelésekhez tartozó összes számlán szereplő összes visszaküldendő termék listája.</span><span class="sxs-lookup"><span data-stu-id="fde3f-110">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="fde3f-111">A pénztáros ekkor kiválaszthatja a visszaküldendő termékeket.</span><span class="sxs-lookup"><span data-stu-id="fde3f-111">The cashier can then select the products to return.</span></span> <span data-ttu-id="fde3f-112">A rendszer az összes kiválasztott termékhez egyetlen visszárurendelést hoz létre.</span><span class="sxs-lookup"><span data-stu-id="fde3f-112">A single return order will be created for all the selected products.</span></span>
