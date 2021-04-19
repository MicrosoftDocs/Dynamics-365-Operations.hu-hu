---
title: A vevők és a termék nyereségesség felmérése
description: A cikk azt ismerteti, hogyan használhatja a memóriában lévő és a valós idejű analitikát az ügyfelek és a termék nyereségességének elérésére, böngészésére és megtekintésére a Dynamics 365 Commerce adatokból.
author: ashishmsft
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationsTemplateForm, RetailStoreManagementWorkspace
audience: Application User
ms.reviewer: josaw
ms.custom: 52902
ms.assetid: 1a77d04b-2985-4bee-9138-c216fe0483de
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 80a2f38f2b3f039b17556116d6aea738faa1db50
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797329"
---
# <a name="assess-customer-and-product-profitability"></a><span data-ttu-id="f0219-103">Vevők és termékek nyereségességének felmérése</span><span class="sxs-lookup"><span data-stu-id="f0219-103">Assess customer and product profitability</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f0219-104">A cikk azt ismerteti, hogyan használhatja a memóriában lévő és a valós idejű analitikát az ügyfelek és a termék nyereségességének elérésére, böngészésére és megtekintésére a Dynamics 365 Commerce adatokból.</span><span class="sxs-lookup"><span data-stu-id="f0219-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about customers and product profitability from your Dynamics 365 Commerce data.</span></span>

<span data-ttu-id="f0219-105">A Commerce részeként a felhasználók tanulmányozhatják a nyereségességet a legjobb vásárlók (10-től 100-ig) esetében, a szervezeti hierarchia különböző szintjein keresztül. Ez a következő kritériumok egyike alapján történik:</span><span class="sxs-lookup"><span data-stu-id="f0219-105">As part of Commerce, users can study profitability for the top customers (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="f0219-106">Értékesítési összeg</span><span class="sxs-lookup"><span data-stu-id="f0219-106">Sales amount</span></span>
- <span data-ttu-id="f0219-107">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="f0219-107">Quantity</span></span>
- <span data-ttu-id="f0219-108">Bruttó haszonkulcs</span><span class="sxs-lookup"><span data-stu-id="f0219-108">Gross profit margin</span></span>
- <span data-ttu-id="f0219-109">Árrés százalékosan</span><span class="sxs-lookup"><span data-stu-id="f0219-109">Margin percentage</span></span>

<span data-ttu-id="f0219-110">Ehhez az értékeléshez alkalmazhatja a nem beépített **Legjobb vásárlók** jelentést, melyet a következő helyek bármelyikéről megnyithat:</span><span class="sxs-lookup"><span data-stu-id="f0219-110">For this assessment, you can use the out-of-box **Top customers** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="f0219-111">**Üzletkezelő** munkaterület &gt; **Kiskereskedelem és kereskedelem** &gt; **Csatornák** &gt; **Üzletkezelő** &gt; **Jelentések** &gt; **Legjobb vásárlók jelentés**</span><span class="sxs-lookup"><span data-stu-id="f0219-111">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports** &gt; **Top customers report**</span></span>
- <span data-ttu-id="f0219-112">**Lekérdezések és jelentések** szakasz &gt; **Kiskereskedelem és kereskedelem** &gt; **Lekérdezések és jelentések** &gt; **Értékesítési jelentések** &gt; **Legjobb vásárlók jelentés**</span><span class="sxs-lookup"><span data-stu-id="f0219-112">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top customers report**</span></span>

<span data-ttu-id="f0219-113">Hasonlóan tanulmányozhatják a felhasználók a legjobb termékeket (10-től 100-ig) a szervezeti hierarchia különböző szintjein keresztül a következő kritériumok egyike alapján:</span><span class="sxs-lookup"><span data-stu-id="f0219-113">Likewise, users can study profitability for the top products (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="f0219-114">Értékesítési összeg</span><span class="sxs-lookup"><span data-stu-id="f0219-114">Sales amount</span></span>
- <span data-ttu-id="f0219-115">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="f0219-115">Quantity</span></span>
- <span data-ttu-id="f0219-116">Bruttó haszonkulcs</span><span class="sxs-lookup"><span data-stu-id="f0219-116">Gross profit margin</span></span>
- <span data-ttu-id="f0219-117">Árrés százalékosan</span><span class="sxs-lookup"><span data-stu-id="f0219-117">Margin percentage</span></span>

<span data-ttu-id="f0219-118">Ehhez az értékeléshez alkalmazhatja a nem beépített **Legjobb termékek** jelentést, melyet a következő helyek bármelyikéről megnyithat:</span><span class="sxs-lookup"><span data-stu-id="f0219-118">For this assessment, you can use the out-of-box **Top products** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="f0219-119">**Üzletkezelő** munkaterület &gt; **Kiskereskedelem és kereskedelem** &gt; **Csatornák** &gt; **Üzletkezelő** &gt; **Jelentések** &gt; **Legjobb termékek jelentés**</span><span class="sxs-lookup"><span data-stu-id="f0219-119">**Store management** workspace &gt; **Retail and Commerce** &gt; **Channels** &gt; **Store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="f0219-120">**Kategória és termék kezelése** munkaterület &gt; **Kiskereskedelem és kiskereskedelem** &gt; **Termékek és kategóriák** &gt; **Üzletkezelő** &gt; **Jelentések** &gt; **Legjobb termékek jelentés**</span><span class="sxs-lookup"><span data-stu-id="f0219-120">**Category and product management** workspace &gt; **Retail and Commerce** &gt; **Products and categories** &gt; **Store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="f0219-121">**Lekérdezések és jelentések** szakasz &gt; **Kiskereskedelem és kereskedelem** &gt; **Lekérdezések és jelentések** &gt; **Értékesítési jelentések** &gt; **Legjobb termékek jelentés**</span><span class="sxs-lookup"><span data-stu-id="f0219-121">**Inquiries and reports** section &gt; **Retail and Commerce** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top products report**</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]