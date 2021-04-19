---
title: Értékesítési és teljesítménykülönbözet figyelése
description: A Dynamics 365 Commerce rendszerben valós időben tanulmányozhatja az értékesítést és teljesítménykülönbözetet.
author: ashishmsft
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailSales
audience: Application User
ms.reviewer: josaw
ms.custom: 85123
ms.assetid: ddd15820-c3e6-4607-819e-8cef744ce9c9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: a7ea2bd9388e2fcfc6ae5f17d61054092cbac58c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796946"
---
# <a name="monitor-sales-and-margin-performance"></a><span data-ttu-id="09837-103">Értékesítés és teljesítménykülönbözet megfigyelése</span><span class="sxs-lookup"><span data-stu-id="09837-103">Monitor sales and margin performance</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="09837-104">A Dynamics 365 Commerce rendszerben valós időben tanulmányozhatja az értékesítést és teljesítménykülönbözetet.</span><span class="sxs-lookup"><span data-stu-id="09837-104">You can monitor sales and margin performance in real time using Dynamics 365 Commerce.</span></span>

<span data-ttu-id="09837-105">A Commerce részeként a felhasználók a szervezeti hierarchia különböző szintjein, valós időben figyelhetik az értékesítést és a teljesítménykülönbözetet az alábbi dimenzióknál:</span><span class="sxs-lookup"><span data-stu-id="09837-105">As part of Commerce, users can monitor sales and margin performance in real time across different levels of the organization hierarchy for the following dimensions:</span></span>

- <span data-ttu-id="09837-106">Termékek</span><span class="sxs-lookup"><span data-stu-id="09837-106">Products</span></span>
- <span data-ttu-id="09837-107">Kategóriák</span><span class="sxs-lookup"><span data-stu-id="09837-107">Categories</span></span>
- <span data-ttu-id="09837-108">Kedvezmények</span><span class="sxs-lookup"><span data-stu-id="09837-108">Discounts</span></span>
- <span data-ttu-id="09837-109">Évek időszaka</span><span class="sxs-lookup"><span data-stu-id="09837-109">Years as time period</span></span>
- <span data-ttu-id="09837-110">Jegyzékek/terminálok</span><span class="sxs-lookup"><span data-stu-id="09837-110">Registers/terminals</span></span>
- <span data-ttu-id="09837-111">Személyzet/alkalmazottak</span><span class="sxs-lookup"><span data-stu-id="09837-111">Staff/employees</span></span>
- <span data-ttu-id="09837-112">Vevők</span><span class="sxs-lookup"><span data-stu-id="09837-112">Customers</span></span>
- <span data-ttu-id="09837-113">Üzemi egységek</span><span class="sxs-lookup"><span data-stu-id="09837-113">Operating units</span></span>

<span data-ttu-id="09837-114">A legfelső kategória csomópontból induló, egészen az alapértelmezett termékkategória hierarchiájában lévő egyéni levélcsomópontokig tartó leásás, valamint két olyan egyedi jelentés segítségével, amely kihasználja a hierarchiai rács struktúrát, a felhasználók figyelhetik az értékesítést és a teljesítménykülönbözetet.</span><span class="sxs-lookup"><span data-stu-id="09837-114">Additionally, two unique reports that take advantage of hierarchical grid structuring let users monitor sales and margin performance by drilling down from the top category node to individual leaf nodes of the category in the default product category hierarchy.</span></span> <span data-ttu-id="09837-115">A felhasználók jelentéskészítési célzattal leáshatnak a legfelső üzemi egységtől, az alapértelmezett szervezeti hierarchiaként meghatározott szervezeti hierarchia egyéni csatornájáig.</span><span class="sxs-lookup"><span data-stu-id="09837-115">Users can also drill-down from the top operating unit to an individual channel in the organization hierarchy that is defined as the default organization hierarchy for reporting.</span></span> <span data-ttu-id="09837-116">A jelentéseket az alábbi helyek bármelyikéről megnyithatja:</span><span class="sxs-lookup"><span data-stu-id="09837-116">You can open the reports from any of the following locations:</span></span>

- <span data-ttu-id="09837-117">**Üzletkezelő** munkaterület &gt; **Retail és Commerce** &gt; **Csatornák** &gt; **Üzletkezelő** &gt; **Jelentések**</span><span class="sxs-lookup"><span data-stu-id="09837-117">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports**</span></span>
- <span data-ttu-id="09837-118">**Kategória- és termékkezelés** munkaterület &gt; **Retail és Commerce** &gt; **Termék és kategóriák** &gt; **Üzletkezelő** &gt; **Jelentések**</span><span class="sxs-lookup"><span data-stu-id="09837-118">**Category and product management** workspace &gt; **Retail and Commerce** &gt; **Product and categories** &gt; **Store management** &gt; **Reports**</span></span>
- <span data-ttu-id="09837-119">**Árképzés és engedmények kezelése** munkaterület &gt; **Retail és Commerce** &gt; **Árképzés és engedmények** &gt; **Üzletkezelő** &gt; **Jelentések**</span><span class="sxs-lookup"><span data-stu-id="09837-119">**Pricing and discount management** workspace &gt; **Retail and Commerce** &gt; **Pricing and discounts** &gt; **Store management** &gt; **Reports**</span></span>
- <span data-ttu-id="09837-120">**Lekérdezések és jelentések** szekció &gt; **Retail és Commerce** &gt; **Lekérdezések és jelentések** &gt; **Értékesítési jelentések**</span><span class="sxs-lookup"><span data-stu-id="09837-120">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports**</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]