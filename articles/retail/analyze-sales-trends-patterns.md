---
title: Értékesítési trendek és mintázatok elemzése
description: A Microsoft Dynamics 365 for Retail-rendszerben valós időben tanulmányozhatja az értékesítési trendeket és mintákat.
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
ms.openlocfilehash: 7ea5efd1fcde233145e97aea30d312bbe70b20ac
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "358002"
---
# <a name="analyze-sales-trends-and-patterns"></a><span data-ttu-id="c3e86-103">Értékesítési trendek és mintázatok elemzése</span><span class="sxs-lookup"><span data-stu-id="c3e86-103">Analyze sales trends and patterns</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c3e86-104">A Microsoft Dynamics 365 for Retail-rendszerben valós időben tanulmányozhatja az értékesítési trendeket és mintákat.</span><span class="sxs-lookup"><span data-stu-id="c3e86-104">You can study sales trends and patterns in real time in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="c3e86-105">A Dynamics 365 for Retail részeként a felhasználók valós időben tanulmányozhatják az értékesítési trendeket és mintázatokat szervezeti hierarchia különböző szintjein éveken keresztül a kulcsrakész **Csatorna értékesítése év szerint** jelentés segítségével.</span><span class="sxs-lookup"><span data-stu-id="c3e86-105">As part of Dynamics 365 for Retail, users can study sales trends and patterns in real time across different levels of the organization hierarchy over a period of years by using the out-of-box **Channel sales by year** report.</span></span> <span data-ttu-id="c3e86-106">Ezt a jelentést az alábbi helyek bármelyikéről megnyithatja:</span><span class="sxs-lookup"><span data-stu-id="c3e86-106">You can open this report from any of the following locations:</span></span>

- <span data-ttu-id="c3e86-107">**Kiskereskedelmi raktárkezelő** munkaterület &gt; **Kiskereskedelem** &gt; **Csatornák** &gt; **Kiskereskedelmi raktárkezelő** &gt; **Jelentések** &gt; **Csatorna értékesítése év szerint jelentés**</span><span class="sxs-lookup"><span data-stu-id="c3e86-107">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Channel sales by year report**</span></span>
- <span data-ttu-id="c3e86-108">**Kiskereskedelmi üzlet pénzügyei** munkaterület &gt; **Kiskereskedelem** &gt; **Csatornák** &gt; **Kiskereskedelmi üzlet pénzügyei** &gt; **Jelentések** &gt; **Csatorna értékesítése év szerint jelentés**</span><span class="sxs-lookup"><span data-stu-id="c3e86-108">**Retail store financials** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store financials** &gt; **Reports** &gt; **Channel sales by year report**</span></span>
- <span data-ttu-id="c3e86-109">**Lekérdezések és jelentések** szekció &gt; **Kiskereskedelem és forgalom** &gt; **Lekérdezések és jelentések** &gt; **Értékesítési jelentések** &gt; **Csatorna értékesítése év szerint jelentés**</span><span class="sxs-lookup"><span data-stu-id="c3e86-109">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Channel sales by year report**</span></span>

<span data-ttu-id="c3e86-110">A felhasználók órákra bontva tanulmányozhatják az értékesítési trendeket és mintázatokat szervezeti hierarchia különböző szintjein a kijelölt időszakban a kulcsrakész **Csatorna értékesítése óra szerint** jelentés segítségével.</span><span class="sxs-lookup"><span data-stu-id="c3e86-110">Users can also study sales trends and patterns by hour across different levels of the organization hierarchy over a selected period by using the out-of-box **Channel sales by hour** report.</span></span> <span data-ttu-id="c3e86-111">Ezt a jelentést az alábbi helyek bármelyikéről megnyithatja:</span><span class="sxs-lookup"><span data-stu-id="c3e86-111">You can open this report from any of the following locations:</span></span>

- <span data-ttu-id="c3e86-112">**Kiskereskedelmi raktárkezelő** munkaterület &gt; **Kiskereskedelem** &gt; **Csatornák** &gt; **Kiskereskedelmi raktárkezelő** &gt; **Jelentések** &gt; **Csatorna értékesítése óra szerint jelentés**</span><span class="sxs-lookup"><span data-stu-id="c3e86-112">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Channel sales by hour report**</span></span>
- <span data-ttu-id="c3e86-113">**Kiskereskedelmi üzlet pénzügyei** munkaterület &gt; **Kiskereskedelem** &gt; **Csatornák** &gt; **Kiskereskedelmi üzlet pénzügyei** &gt; **Jelentések** &gt; **Csatorna értékesítése óra szerint jelentés**</span><span class="sxs-lookup"><span data-stu-id="c3e86-113">**Retail store financials** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store financials** &gt; **Reports** &gt; **Channel sales by hour report**</span></span>
- <span data-ttu-id="c3e86-114">**Lekérdezések és jelentések** szekció &gt; **Kiskereskedelem és forgalom** &gt; **Lekérdezések és jelentések** &gt; **Értékesítési jelentések** &gt; **Csatorna értékesítése óra szerint jelentés**</span><span class="sxs-lookup"><span data-stu-id="c3e86-114">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Channel sales by hour report**</span></span>
