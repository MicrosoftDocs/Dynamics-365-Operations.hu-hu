---
title: A vevők és a termék nyereségesség felmérése
description: A cikk azt ismerteti, hogyan használhatja a memóriában lévő és a valós idejű analitikát az ügyfelek és a termék nyereségességének elérésére, böngészésére és megtekintésére a Dynamics 365 Retail adatokból.
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
ms.openlocfilehash: 5a9bebf948bd4602556f70a5a79690621a03261e
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2019
ms.locfileid: "2023590"
---
# <a name="assess-customer-and-product-profitability"></a><span data-ttu-id="702a4-103">Vevők és termékek nyereségességének felmérése</span><span class="sxs-lookup"><span data-stu-id="702a4-103">Assess customer and product profitability</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="702a4-104">A cikk azt ismerteti, hogyan használhatja a memóriában lévő és a valós idejű analitikát az ügyfelek és a termék nyereségességének elérésére, böngészésére és megtekintésére a Dynamics 365 Retail adatokból.</span><span class="sxs-lookup"><span data-stu-id="702a4-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about customers and product profitability from your Dynamics 365 Retail data.</span></span>

<span data-ttu-id="702a4-105">A Retail részeként a felhasználók tanulmányozhatják a nyereségességet a legjobb vásárlók (10-től 100-ig) esetében, a szervezeti hierarchia különböző szintjein keresztül. Ez a következő kritériumok egyike alapján történik:</span><span class="sxs-lookup"><span data-stu-id="702a4-105">As part of Retail, users can study profitability for the top customers (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="702a4-106">Értékesítési összeg</span><span class="sxs-lookup"><span data-stu-id="702a4-106">Sales amount</span></span>
- <span data-ttu-id="702a4-107">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="702a4-107">Quantity</span></span>
- <span data-ttu-id="702a4-108">Bruttó haszonkulcs</span><span class="sxs-lookup"><span data-stu-id="702a4-108">Gross profit margin</span></span>
- <span data-ttu-id="702a4-109">Árrés százalékosan</span><span class="sxs-lookup"><span data-stu-id="702a4-109">Margin percentage</span></span>

<span data-ttu-id="702a4-110">Ehhez az értékeléshez alkalmazhatja a nem beépített **Legjobb vásárlók** jelentést, melyet a következő helyek bármelyikéről megnyithat:</span><span class="sxs-lookup"><span data-stu-id="702a4-110">For this assessment, you can use the out-of-box **Top customers** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="702a4-111">**Kiskereskedelmi raktárkezelő** munkaterület &gt; **Kiskereskedelem** &gt; **Csatornák** &gt; **Kiskereskedelmi raktárkezelő** &gt; **Jelentések** &gt; **Legjobb vásárlók jelentés**</span><span class="sxs-lookup"><span data-stu-id="702a4-111">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top customers report**</span></span>
- <span data-ttu-id="702a4-112">**Lekérdezések és jelentések** szekció &gt; **Kiskereskedelem és forgalom** &gt; **Lekérdezések és jelentések** &gt; **Értékesítési jelentések** &gt; **Legjobb vásárlók jelentés**</span><span class="sxs-lookup"><span data-stu-id="702a4-112">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top customers report**</span></span>

<span data-ttu-id="702a4-113">Hasonlóan tanulmányozhatják a felhasználók a legjobb termékeket (10-től 100-ig) a szervezeti hierarchia különböző szintjein keresztül a következő kritériumok egyike alapján:</span><span class="sxs-lookup"><span data-stu-id="702a4-113">Likewise, users can study profitability for the top products (10 to 100) across different levels of the organization hierarchy, based on one of the following criteria:</span></span>

- <span data-ttu-id="702a4-114">Értékesítési összeg</span><span class="sxs-lookup"><span data-stu-id="702a4-114">Sales amount</span></span>
- <span data-ttu-id="702a4-115">Mennyiség</span><span class="sxs-lookup"><span data-stu-id="702a4-115">Quantity</span></span>
- <span data-ttu-id="702a4-116">Bruttó haszonkulcs</span><span class="sxs-lookup"><span data-stu-id="702a4-116">Gross profit margin</span></span>
- <span data-ttu-id="702a4-117">Árrés százalékosan</span><span class="sxs-lookup"><span data-stu-id="702a4-117">Margin percentage</span></span>

<span data-ttu-id="702a4-118">Ehhez az értékeléshez alkalmazhatja a nem beépített **Legjobb termékek** jelentést, melyet a következő helyek bármelyikéről megnyithat:</span><span class="sxs-lookup"><span data-stu-id="702a4-118">For this assessment, you can use the out-of-box **Top products** report, which you can open from any of the following locations:</span></span>

- <span data-ttu-id="702a4-119">**Kiskereskedelmi raktárkezelő** munkaterület &gt; **Kiskereskedelem** &gt; **Csatornák** &gt; **Kiskereskedelmi raktárkezelő** &gt; **Jelentések** &gt; **Legjobb termékek jelentés**</span><span class="sxs-lookup"><span data-stu-id="702a4-119">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="702a4-120">**Kategória és termék kezelése** munkaterület &gt; **Kiskereskedelem** &gt; **Termékek és kategóriák** &gt; **Kiskereskedelmi raktárkezelő** &gt; **Jelentések** &gt; **Legjobb termékek jelentés**</span><span class="sxs-lookup"><span data-stu-id="702a4-120">**Category and product management** workspace &gt; **Retail** &gt; **Products and categories** &gt; **Retail store management** &gt; **Reports** &gt; **Top products report**</span></span>
- <span data-ttu-id="702a4-121">**Lekérdezések és jelentések** szekció &gt; **Kiskereskedelem és forgalom** &gt; **Lekérdezések és jelentések** &gt; **Értékesítési jelentések** &gt; **Legjobb termékek jelentés**</span><span class="sxs-lookup"><span data-stu-id="702a4-121">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Top products report**</span></span>
