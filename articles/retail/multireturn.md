---
title: Több vevői rendelést és számlát érintő visszárucikkek
description: Ez a témakör azt mutatja be, hogy hogyan lehet több vevői rendelést és számlát érintő visszárukat engedélyezni a Dynamics 365 Retail alkalmazásban.
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
ms.openlocfilehash: 25a1081e5f903076e23089c41dda7437f8a70124
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2019
ms.locfileid: "2017989"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="efaf1-103">Több vevői rendelést és számlát érintő visszárucikkek</span><span class="sxs-lookup"><span data-stu-id="efaf1-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="efaf1-104">A visszáruk több rendelést és számlát is érinthetnek.</span><span class="sxs-lookup"><span data-stu-id="efaf1-104">Returns can be made across multiple orders and invoices.</span></span> 

## <a name="configure-retail-to-support-returns-across-multiple-customer-order-and-invoices"></a><span data-ttu-id="efaf1-105">A Retail konfigurálása a több vevői rendelést és számlát érintő visszáruk támogatásához</span><span class="sxs-lookup"><span data-stu-id="efaf1-105">Configure Retail to support returns across multiple customer order and invoices</span></span>

1. <span data-ttu-id="efaf1-106">Lépjen a **Kiskereskedelmi paraméterek \> Vevői rendelések** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="efaf1-106">Go to **Retail parameters \> Customer orders**.</span></span>
1. <span data-ttu-id="efaf1-107">Kapcsolja be a **Visszáruk engedélyezése több rendelésre vonatkozóan** paramétert.</span><span class="sxs-lookup"><span data-stu-id="efaf1-107">Turn on the **Enable returns for multiple orders** parameter.</span></span> 

## <a name="process-returns"></a><span data-ttu-id="efaf1-108">Visszáruk feldolgozása</span><span class="sxs-lookup"><span data-stu-id="efaf1-108">Process returns</span></span>

<span data-ttu-id="efaf1-109">A paraméter engedélyezése és a módosítások üzletekkel történő szinkronizálása után az üzlet pénztárosa több értékesítési rendelést is kiválaszthat egy vevő visszáruihoz.</span><span class="sxs-lookup"><span data-stu-id="efaf1-109">After the parameter is turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="efaf1-110">Ha kijelölte a rendeléseket, megjelenik a rendelésekhez tartozó összes számlán szereplő összes visszaküldendő termék listája.</span><span class="sxs-lookup"><span data-stu-id="efaf1-110">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="efaf1-111">A pénztáros ekkor kiválaszthatja a visszaküldendő termékeket.</span><span class="sxs-lookup"><span data-stu-id="efaf1-111">The cashier can then select the products to return.</span></span> <span data-ttu-id="efaf1-112">A rendszer az összes kiválasztott termékhez egyetlen visszárurendelést hoz létre.</span><span class="sxs-lookup"><span data-stu-id="efaf1-112">A single return order will be created for all the selected products.</span></span>
