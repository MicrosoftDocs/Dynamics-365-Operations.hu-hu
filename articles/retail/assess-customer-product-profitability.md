---
title: A vevők és a termék nyereségesség felmérése
description: A cikk azt ismerteti, hogyan használhatja a memóriában lévő és a valós idejű analitikát az ügyfelek és a termék nyereségességének elérésére, böngészésére és megtekintésére a Microsoft Dynamics 365 for Retail adatokból.
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: SysOperationsTemplateForm, RetailStoreManagementWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 52902
ms.assetid: 1a77d04b-2985-4bee-9138-c216fe0483de
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 28d4eeaa3fcae33f817690ad496b4b123a5838ce
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "326009"
---
# <a name="assess-customer-and-product-profitability"></a><span data-ttu-id="e92d9-103">Vevők és termékek nyereségességének felmérése</span><span class="sxs-lookup"><span data-stu-id="e92d9-103">Assess customer and product profitability</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e92d9-104">A cikk azt ismerteti, hogyan használhatja a memóriában lévő és a valós idejű analitikát az ügyfelek és a termék nyereségességének elérésére, böngészésére és megtekintésére a Microsoft Dynamics 365 for Retail adatokból.</span><span class="sxs-lookup"><span data-stu-id="e92d9-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about customers and product profitability from your Microsoft Dynamics 365 for Retail data.</span></span>

<span data-ttu-id="e92d9-105">A Dynamics 365 for Retail részeként a felhasználók tanulmányozhatják a nyereségességet a legjobb vásárlók (10-től 100-ig) esetében, a szervezeti hierarchia különböző szintjein keresztül. Ez a következő kritériumok egyike alapján történik:</span><span class="sxs-lookup"><span data-stu-id="e92d9-105">As part of Dynamics 365 for Retail, users can study profitability for the top customers (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="e92d9-106">Értékesítési összeg</span><span class="sxs-lookup"><span data-stu-id="e92d9-106">Sales amount</span></span>
- <span data-ttu-id="e92d9-107">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="e92d9-107">Quantity</span></span>
- <span data-ttu-id="e92d9-108">Bruttó haszonkulcs</span><span class="sxs-lookup"><span data-stu-id="e92d9-108">Gross profit margin</span></span>
- <span data-ttu-id="e92d9-109">Árrés százalékosan</span><span class="sxs-lookup"><span data-stu-id="e92d9-109">Margin percentage</span></span>

<span data-ttu-id="e92d9-110">Ehhez az értékeléshez alkalmazhatja a nem beépített **Legjobb vásárlók** jelentést, melyet a következő helyek bármelyikéről megnyithat:</span><span class="sxs-lookup"><span data-stu-id="e92d9-110">For this assessment, you can use the out-of-box **Top customers** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="e92d9-111">**Kiskereskedelmi raktárkezelő** munkaterület &gt; **Kiskereskedelem** &gt; **Csatornák** &gt; **Kiskereskedelmi raktárkezelő** &gt; **Jelentések** &gt; **Legjobb vásárlók jelentés**</span><span class="sxs-lookup"><span data-stu-id="e92d9-111">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top customers report**</span></span>
- <span data-ttu-id="e92d9-112">**Lekérdezések és jelentések** szekció &gt; **Kiskereskedelem és forgalom** &gt; **Lekérdezések és jelentések** &gt; **Értékesítési jelentések** &gt; **Legjobb vásárlók jelentés**</span><span class="sxs-lookup"><span data-stu-id="e92d9-112">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top customers report**</span></span>

<span data-ttu-id="e92d9-113">Hasonlóan tanulmányozhatják a felhasználók a legjobb termékeket (10-től 100-ig) a szervezeti hierarchia különböző szintjein keresztül a következő kritériumok egyike alapján:</span><span class="sxs-lookup"><span data-stu-id="e92d9-113">Likewise, users can study profitability for the top products (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="e92d9-114">Értékesítési összeg</span><span class="sxs-lookup"><span data-stu-id="e92d9-114">Sales amount</span></span>
- <span data-ttu-id="e92d9-115">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="e92d9-115">Quantity</span></span>
- <span data-ttu-id="e92d9-116">Bruttó haszonkulcs</span><span class="sxs-lookup"><span data-stu-id="e92d9-116">Gross profit margin</span></span>
- <span data-ttu-id="e92d9-117">Árrés százalékosan</span><span class="sxs-lookup"><span data-stu-id="e92d9-117">Margin percentage</span></span>

<span data-ttu-id="e92d9-118">Ehhez az értékeléshez alkalmazhatja a nem beépített **Legjobb termékek** jelentést, melyet a következő helyek bármelyikéről megnyithat:</span><span class="sxs-lookup"><span data-stu-id="e92d9-118">For this assessment, you can use the out-of-box **Top products** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="e92d9-119">**Kiskereskedelmi raktárkezelő** munkaterület &gt; **Kiskereskedelem** &gt; **Csatornák** &gt; **Kiskereskedelmi raktárkezelő** &gt; **Jelentések** &gt; **Legjobb termékek jelentés**</span><span class="sxs-lookup"><span data-stu-id="e92d9-119">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="e92d9-120">**Kategória és termék kezelése** munkaterület &gt; **Kiskereskedelem** &gt; **Termékek és kategóriák** &gt; **Kiskereskedelmi raktárkezelő** &gt; **Jelentések** &gt; **Legjobb termékek jelentés**</span><span class="sxs-lookup"><span data-stu-id="e92d9-120">**Category and product management** workspace &gt; **Retail** &gt; **Products and categories** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="e92d9-121">**Lekérdezések és jelentések** szekció &gt; **Kiskereskedelem és forgalom** &gt; **Lekérdezések és jelentések** &gt; **Értékesítési jelentések** &gt; **Legjobb termékek jelentés**</span><span class="sxs-lookup"><span data-stu-id="e92d9-121">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top products report**</span></span>
