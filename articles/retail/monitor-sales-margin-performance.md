---
title: "Értékesítési és teljesítménykülönbözet figyelése"
description: "A Microsoft Dynamics 365 for Retail rendszerben valós időben tanulmányozhatja az értékesítést és teljesítménykülönbözetet."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85123
ms.assetid: ddd15820-c3e6-4607-819e-8cef744ce9c9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e1d4f693fa9712585593b9d3de43c3603588531c
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="monitor-sales-and-margin-performance"></a><span data-ttu-id="9f87e-103">Értékesítési és teljesítménykülönbözet megfigyelése</span><span class="sxs-lookup"><span data-stu-id="9f87e-103">Monitor sales and margin performance</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="9f87e-104">A Microsoft Dynamics 365 for Retail rendszerben valós időben tanulmányozhatja az értékesítést és teljesítménykülönbözetet.</span><span class="sxs-lookup"><span data-stu-id="9f87e-104">You can monitor sales and margin performance in real time using Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="9f87e-105">A Dynamics 365 for Retail részeként a felhasználók a szervezeti hierarchia különböző szintjein, valós időben figyelhetik az értékesítést és a teljesítménykülönbözetet az alábbi dimenzióknál:</span><span class="sxs-lookup"><span data-stu-id="9f87e-105">As part of Dynamics 365 for Retail, users can monitor sales and margin performance in real time across different levels of the organization hierarchy for the following dimensions:</span></span>

-   <span data-ttu-id="9f87e-106">Termékek</span><span class="sxs-lookup"><span data-stu-id="9f87e-106">Products</span></span>
-   <span data-ttu-id="9f87e-107">Kategóriák</span><span class="sxs-lookup"><span data-stu-id="9f87e-107">Categories</span></span>
-   <span data-ttu-id="9f87e-108">Kedvezmények</span><span class="sxs-lookup"><span data-stu-id="9f87e-108">Discounts</span></span>
-   <span data-ttu-id="9f87e-109">Évek időszaka</span><span class="sxs-lookup"><span data-stu-id="9f87e-109">Years as time period</span></span>
-   <span data-ttu-id="9f87e-110">Jegyzékek/terminálok</span><span class="sxs-lookup"><span data-stu-id="9f87e-110">Registers/terminals</span></span>
-   <span data-ttu-id="9f87e-111">Személyzet/alkalmazottak</span><span class="sxs-lookup"><span data-stu-id="9f87e-111">Staff/employees</span></span>
-   <span data-ttu-id="9f87e-112">Vevők</span><span class="sxs-lookup"><span data-stu-id="9f87e-112">Customers</span></span>
-   <span data-ttu-id="9f87e-113">Üzemi egységek</span><span class="sxs-lookup"><span data-stu-id="9f87e-113">Operating units</span></span>

<span data-ttu-id="9f87e-114">A legfelső kategória csomópontból induló, egészen az alapértelmezett kiskereskedelmi termékkategória hierarchiájában lévő egyéni levélcsomópontokig tartó leásás, valamint két olyan egyedi jelentés segítségével, amely kihasználja a hierarchiai rács struktúrát, a felhasználók figyelhetik az értékesítést és a teljesítménykülönbözetet.</span><span class="sxs-lookup"><span data-stu-id="9f87e-114">Additionally, two unique reports that take advantage of hierarchical grid structuring let users monitor sales and margin performance by drilling down from the top category node to individual leaf nodes of the category in the default retail product category hierarchy.</span></span> <span data-ttu-id="9f87e-115">A felhasználók kiskereskedelmi jelentés-hierarchiai célzattal leáshatnak a legfelső üzemi egységtől, az alapértelmezett szervezeti hierarchiaként meghatározott szervezeti hierarchia egyéni csatornájáig.</span><span class="sxs-lookup"><span data-stu-id="9f87e-115">Users can also drill-down from the top operating unit to an individual channel in the organization hierarchy that is defined as the default organization hierarchy for retail reporting hierarchy purposes.</span></span> <span data-ttu-id="9f87e-116">A jelentéseket az alábbi helyek bármelyikéről megnyithatja:</span><span class="sxs-lookup"><span data-stu-id="9f87e-116">You can open the reports from any of the following locations:</span></span>

-   <span data-ttu-id="9f87e-117">**Kiskereskedelmi raktárkezelő** munkaterület &gt; **Kiskereskedelem** &gt; **Csatornák** &gt; **Kiskereskedelmi raktárkezelő** &gt; **Jelentések**</span><span class="sxs-lookup"><span data-stu-id="9f87e-117">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports**</span></span>
-   <span data-ttu-id="9f87e-118">**Kategória- és termékkezelés** munkaterület &gt; **Kiskereskedelem** &gt; **Termék és kategóriák** &gt; **Kiskereskedelmi raktárkezelő** &gt; **Jelentések**</span><span class="sxs-lookup"><span data-stu-id="9f87e-118">**Category and product management** workspace &gt; **Retail** &gt; **Product and categories** &gt; **Retail store management** &gt; **Reports**</span></span>
-   <span data-ttu-id="9f87e-119">**Árképzés és engedmények kezelése** munkaterület &gt; **Kiskereskedelem** &gt; **Árképzés és engedmények** &gt; **Kiskereskedelmi üzlet kezelése** &gt; **Jelentések**</span><span class="sxs-lookup"><span data-stu-id="9f87e-119">**Pricing and discount management** workspace &gt; **Retail** &gt; **Pricing and discounts** &gt; **Retail store management** &gt; **Reports**</span></span>
-   <span data-ttu-id="9f87e-120">**Lekérdezések és jelentések** szekció &gt; **Kiskereskedelem** &gt; **Lekérdezések és jelentések** &gt; **Értékesítési jelentések**</span><span class="sxs-lookup"><span data-stu-id="9f87e-120">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports**</span></span>



