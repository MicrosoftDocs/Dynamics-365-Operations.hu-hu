---
title: Értékesítési trendek és mintázatok elemzése
description: A Dynamics 365 Retail-rendszerben valós időben tanulmányozhatja az értékesítési trendeket és mintákat.
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailChannelReport, SysReportViewerForm, RetailStoreManagementWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85183
ms.assetid: df9c62a2-6f13-4a08-bdca-07d041172c1b
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: c54e707d312d7ac3bbcad71a914e528859038a13
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/24/2019
ms.locfileid: "2025817"
---
# <a name="analyze-sales-trends-and-patterns"></a><span data-ttu-id="9a732-103">Értékesítési trendek és mintázatok elemzése</span><span class="sxs-lookup"><span data-stu-id="9a732-103">Analyze sales trends and patterns</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9a732-104">A Dynamics 365 Retail-rendszerben valós időben tanulmányozhatja az értékesítési trendeket és mintákat.</span><span class="sxs-lookup"><span data-stu-id="9a732-104">You can study sales trends and patterns in real time in Dynamics 365 Retail.</span></span>

<span data-ttu-id="9a732-105">A Retail részeként a felhasználók valós időben tanulmányozhatják az értékesítési trendeket és mintázatokat szervezeti hierarchia különböző szintjein éveken keresztül a kulcsrakész **Csatorna értékesítése** év szerint jelentés segítségével.</span><span class="sxs-lookup"><span data-stu-id="9a732-105">As part of Retail, users can study sales trends and patterns in real time across different levels of the organization hierarchy over a period of years by using the out-of-box **Channel sales by year** report.</span></span> <span data-ttu-id="9a732-106">Ezt a jelentést az alábbi helyek bármelyikéről megnyithatja:</span><span class="sxs-lookup"><span data-stu-id="9a732-106">You can open this report from any of the following locations:</span></span>

- <span data-ttu-id="9a732-107">**Kiskereskedelmi raktárkezelő** munkaterület &gt; **Kiskereskedelem** &gt; **Csatornák** &gt; **Kiskereskedelmi raktárkezelő** &gt; **Jelentések** &gt; **Csatorna értékesítése év szerint jelentés**</span><span class="sxs-lookup"><span data-stu-id="9a732-107">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Channel sales by year report**</span></span>
- <span data-ttu-id="9a732-108">**Kiskereskedelmi üzlet pénzügyei** munkaterület &gt; **Kiskereskedelem** &gt; **Csatornák** &gt; **Kiskereskedelmi üzlet pénzügyei** &gt; **Jelentések** &gt; **Csatorna értékesítése év szerint jelentés**</span><span class="sxs-lookup"><span data-stu-id="9a732-108">**Retail store financials** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store financials** &gt; **Reports** &gt; **Channel sales by year report**</span></span>
- <span data-ttu-id="9a732-109">**Lekérdezések és jelentések** szekció &gt; **Kiskereskedelem és forgalom** &gt; **Lekérdezések és jelentések** &gt; **Értékesítési jelentések** &gt; **Csatorna értékesítése év szerint jelentés**</span><span class="sxs-lookup"><span data-stu-id="9a732-109">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Channel sales by year report**</span></span>

<span data-ttu-id="9a732-110">A felhasználók órákra bontva tanulmányozhatják az értékesítési trendeket és mintázatokat szervezeti hierarchia különböző szintjein a kijelölt időszakban a kulcsrakész **Csatorna értékesítése óra szerint** jelentés segítségével.</span><span class="sxs-lookup"><span data-stu-id="9a732-110">Users can also study sales trends and patterns by hour across different levels of the organization hierarchy over a selected period by using the out-of-box **Channel sales by hour** report.</span></span> <span data-ttu-id="9a732-111">Ezt a jelentést az alábbi helyek bármelyikéről megnyithatja:</span><span class="sxs-lookup"><span data-stu-id="9a732-111">You can open this report from any of the following locations:</span></span>

- <span data-ttu-id="9a732-112">**Kiskereskedelmi raktárkezelő** munkaterület &gt; **Kiskereskedelem** &gt; **Csatornák** &gt; **Kiskereskedelmi raktárkezelő** &gt; **Jelentések** &gt; **Csatorna értékesítése óra szerint jelentés**</span><span class="sxs-lookup"><span data-stu-id="9a732-112">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Channel sales by hour report**</span></span>
- <span data-ttu-id="9a732-113">**Kiskereskedelmi üzlet pénzügyei** munkaterület &gt; **Kiskereskedelem** &gt; **Csatornák** &gt; **Kiskereskedelmi üzlet pénzügyei** &gt; **Jelentések** &gt; **Csatorna értékesítése óra szerint jelentés**</span><span class="sxs-lookup"><span data-stu-id="9a732-113">**Retail store financials** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store financials** &gt; **Reports** &gt; **Channel sales by hour report**</span></span>
- <span data-ttu-id="9a732-114">**Lekérdezések és jelentések** szekció &gt; **Kiskereskedelem és forgalom** &gt; **Lekérdezések és jelentések** &gt; **Értékesítési jelentések** &gt; **Csatorna értékesítése óra szerint jelentés**</span><span class="sxs-lookup"><span data-stu-id="9a732-114">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Channel sales by hour report**</span></span>
