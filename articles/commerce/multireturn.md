---
title: Több vevői rendelést és számlát érintő visszárucikkek
description: Ez a témakör azt mutatja be, hogy hogyan lehet több vevői rendelést és számlát érintő visszárukat engedélyezni a Dynamics 365 Commerce alkalmazásban.
author: josaw1
manager: AnnBe
ms.date: 08/27/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 4d1be6606793d498d01be91de6205e3a45c6dfdf
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251259"
---
# <a name="return-items-across-multiple-customer-orders-and-invoices"></a><span data-ttu-id="257f6-103">Több vevői rendelést és számlát érintő visszárucikkek</span><span class="sxs-lookup"><span data-stu-id="257f6-103">Return items across multiple customer orders and invoices</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="257f6-104">Ez a cikk a több számlán átívelő, vevői rendeléseket érintő visszárukat optimalizálja.</span><span class="sxs-lookup"><span data-stu-id="257f6-104">This article describes two features that optimize customer order returns over multiple invoices.</span></span> 

## <a name="enable-refunds-over-multiple-captures"></a><span data-ttu-id="257f6-105">Visszatérítések engedélyezése többszörös rögzítéseknél</span><span class="sxs-lookup"><span data-stu-id="257f6-105">Enable refunds over multiple captures</span></span>

<span data-ttu-id="257f6-106">Ez a funkció több, összekapcsolt visszatérítést tesz lehetővé ugyanarra a vevői rendelésre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="257f6-106">This feature enables multiple linked refunds against the same customer order.</span></span> 

1. <span data-ttu-id="257f6-107">Nyissa meg a **Funkciókezelés** munkaterületet, és keresse meg a következőt: **Visszatérítések engedélyezése többszörös rögzítéseknél**.</span><span class="sxs-lookup"><span data-stu-id="257f6-107">Go to the **Feature management** workspace and search for **Enable refunds over multiple captures**.</span></span>
2. <span data-ttu-id="257f6-108">Válassza ki a **Visszatérítések engedélyezése többszörös rögzítéseknél** lehetőséget, majd kattintson az **Engedélyezés** elemre.</span><span class="sxs-lookup"><span data-stu-id="257f6-108">Select **Enable refunds over multiple orders** and then click **Enable**.</span></span> 

## <a name="enable-proper-tax-calculation-for-returns-with-partial-quantity"></a><span data-ttu-id="257f6-109">A megfelelő adószámítás engedélyezése a részleges mennyiséggel történő visszáru esetében</span><span class="sxs-lookup"><span data-stu-id="257f6-109">Enable proper tax calculation for returns with partial quantity</span></span>

<span data-ttu-id="257f6-110">Ez a funkció biztosítja, hogy amikor egy rendelés visszáruja több számla igénybevételével történik, akkor az adók végső soron megegyezzenek az eredetileg felszámolt adó összegével.</span><span class="sxs-lookup"><span data-stu-id="257f6-110">This feature ensures that when an order is returned using multiple invoices, the taxes will ultimately be equal to the tax amount originally charged.</span></span> 

1. <span data-ttu-id="257f6-111">Nyissa meg a **Funkciókezelés** munkaterületet, és keresse meg a következőt: **A megfelelő adószámítás engedélyezése a részleges mennyiséggel történő visszáru esetében**.</span><span class="sxs-lookup"><span data-stu-id="257f6-111">Go to the **Feature management** workspace and search for **Enable proper tax calculation for returns with partial quantity**.</span></span>
2. <span data-ttu-id="257f6-112">Válassza az **A megfelelő adószámítás engedélyezése a részleges mennyiséggel történő visszáru esetében** elemet, és kattintson az **Engedélyezés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="257f6-112">Select **Enable proper tax calculation for returns with partial quantity** and then click **Enable**.</span></span> 


## <a name="process-returns"></a><span data-ttu-id="257f6-113">Visszáruk feldolgozása</span><span class="sxs-lookup"><span data-stu-id="257f6-113">Process returns</span></span>

<span data-ttu-id="257f6-114">Ezen funkciók engedélyezése és a módosítások üzletekkel történő szinkronizálása után az üzlet pénztárosa több értékesítési rendelést is kiválaszthat egy vevő visszáruihoz.</span><span class="sxs-lookup"><span data-stu-id="257f6-114">After these features are turned on and the changes are synchronized to the stores, the cashier in the store can select multiple sales orders for a customer for their return.</span></span>

<span data-ttu-id="257f6-115">Ha kijelölte a rendeléseket, megjelenik a rendelésekhez tartozó összes számlán szereplő összes visszaküldendő termék listája.</span><span class="sxs-lookup"><span data-stu-id="257f6-115">When the orders are selected, a list of all the returnable products across all the invoices for the orders will display.</span></span> <span data-ttu-id="257f6-116">A pénztáros ekkor kiválaszthatja a visszaküldendő termékeket.</span><span class="sxs-lookup"><span data-stu-id="257f6-116">The cashier can then select the products to return.</span></span> <span data-ttu-id="257f6-117">A rendszer az összes kiválasztott termékhez egyetlen visszárurendelést hoz létre.</span><span class="sxs-lookup"><span data-stu-id="257f6-117">A single return order will be created for all the selected products.</span></span>

<span data-ttu-id="257f6-118">Ha a rendelést teljes egészében visszaküldték, akkor a vevőnek visszatérített adók összege megegyezik az eredetileg felszámított adó összegével.</span><span class="sxs-lookup"><span data-stu-id="257f6-118">If the order is fully returned, the amount of taxes returned to the customer will be equal to the amount of tax originally charged.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]