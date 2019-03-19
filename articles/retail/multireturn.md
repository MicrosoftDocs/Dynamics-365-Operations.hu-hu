---
title: Több vevői rendelést és számlát érintő visszárucikkek
description: Ez a témakör azt mutatja be, hogy hogyan lehet több vevői rendelést és számlát érintő visszárukat engedélyezni a Microsoft Dynamics 365 for Retail alkalmazásban.
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
ms.openlocfilehash: c201311028b11121d626e93859a2b98497c047d1
ms.sourcegitcommit: bacec397ee48ac583596be156c87ead474ee07df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/05/2019
ms.locfileid: "777226"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="764ac-103">Több vevői rendelést és számlát érintő visszárucikkek</span><span class="sxs-lookup"><span data-stu-id="764ac-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="764ac-104">A Dynamics 365 for Finance and Operations 10.0-s verziójában lehetővé vált a több rendelést és számlát érintő visszáruk végrehajtása, míg a 10.0-s verzió előtti kiadásokban a visszárukat egyszerre egyetlen számlára vonatkozóan lehetett csak elvégezni.</span><span class="sxs-lookup"><span data-stu-id="764ac-104">In Dynamics 365 for Finance and Operations version 10.0, returns can be made across multiple orders and invoices, whereas in releases prior to 10.0, returns could only be processed by a single invoice at a time.</span></span> 

## <a name="configure-retail-to-support-returns-across-multiple-customer-order-and-invoices"></a><span data-ttu-id="764ac-105">A Retail konfigurálása annak érdekében, hogy támogassa a több vevői rendelést és számlát érintő visszárukat</span><span class="sxs-lookup"><span data-stu-id="764ac-105">Configure Retail to support returns across multiple customer order and invoices</span></span>

1. <span data-ttu-id="764ac-106">Lépjen a **Kiskereskedelmi paraméterek \> Vevői rendelések** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="764ac-106">Go to **Retail parameters \> Customer orders**.</span></span>
1. <span data-ttu-id="764ac-107">Kapcsolja be a **Visszáruk engedélyezése több rendelésre vonatkozóan** paramétert.</span><span class="sxs-lookup"><span data-stu-id="764ac-107">Turn on the **Enable returns for multiple orders** parameter.</span></span> 

## <a name="process-returns"></a><span data-ttu-id="764ac-108">Visszáruk feldolgozása</span><span class="sxs-lookup"><span data-stu-id="764ac-108">Process returns</span></span>

<span data-ttu-id="764ac-109">A paraméter engedélyezése és a módosítások üzletekkel történő szinkronizálása után az üzlet pénztárosa több értékesítési rendelést is kiválaszthat egy vevő visszáruihoz.</span><span class="sxs-lookup"><span data-stu-id="764ac-109">After the parameter is turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="764ac-110">Ha kijelölte a rendeléseket, megjelenik a rendelésekhez tartozó összes számlán szereplő összes visszaküldendő termék listája.</span><span class="sxs-lookup"><span data-stu-id="764ac-110">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="764ac-111">A pénztáros ekkor kiválaszthatja a visszaküldendő termékeket.</span><span class="sxs-lookup"><span data-stu-id="764ac-111">The cashier can then select the products to return.</span></span> <span data-ttu-id="764ac-112">A rendszer az összes kiválasztott termékhez egyetlen visszárurendelést hoz létre.</span><span class="sxs-lookup"><span data-stu-id="764ac-112">A single return order will be created for all the selected products.</span></span>
