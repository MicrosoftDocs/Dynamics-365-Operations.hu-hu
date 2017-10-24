---
title: "Üzletteljesítmény elemzés"
description: "Ez a cikk azt ismerteti, hogyan használhatja a memóriában lévő és a valós idejű analitikát az üzlet teljesítményéről a Microsoft Dynamics 365 for Retail adatai alapján."
author: ashishmsft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 57811
ms.assetid: 495a66f0-491a-4688-842d-51c33c37676f
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5cb5881cdb9c769bfc4272da85bc1c886a36705b
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="analyze-store-performance"></a><span data-ttu-id="8f29e-103">Az üzletteljesítmény elemzése</span><span class="sxs-lookup"><span data-stu-id="8f29e-103">Analyze store performance</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="8f29e-104">Ez a cikk azt ismerteti, hogyan használhatja a memóriában lévő és a valós idejű analitikát az üzlet teljesítményéről a Microsoft Dynamics 365 for Retail adatai alapján.</span><span class="sxs-lookup"><span data-stu-id="8f29e-104">This article explains how you can use the in-memory and real-time analytics to access, explore, and gain insight about store performance, based on your Microsoft Dynamics 365 for Retail data.</span></span> 

<span data-ttu-id="8f29e-105">A Microsoft Dynamics 365 for Retail részeként a felhasználók valós időben tanulmányozhatják az (kiválasztott idő alatti) üzletteljesítményt a szervezeti hierarchia különböző szintjein. Ezt úgy tehetik meg, hogy megnyitják a (nem beépített) **Csatorna összegzés** jelentést, a következő helyszínek egyikéről:</span><span class="sxs-lookup"><span data-stu-id="8f29e-105">As part of Dynamics 365 for Retail, users can study store performance in real time across different levels of the organization hierarchy over a selected period by opening the out-of-box **Channel summary** report from any of the following locations:</span></span>

-   <span data-ttu-id="8f29e-106">**Kiskereskedelmi raktárkezelő** munkaterület &gt; **Kiskereskedelem** &gt; **Csatornák** &gt; **Kiskereskedelmi raktárkezelő** &gt; **Jelentések** &gt; **Csatorna-összefoglaló jelentés**</span><span class="sxs-lookup"><span data-stu-id="8f29e-106">**Retail store management** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store management** &gt; **Reports** &gt; **Channel summary report**</span></span>
-   <span data-ttu-id="8f29e-107">**Kiskereskedelmi üzlet pénzügyei** munkaterület &gt; **Kiskereskedelem** &gt; **Csatornák** &gt; **Kiskereskedelmi üzlet pénzügyei** &gt; **Jelentések** &gt; **Csatorna-összefoglaló jelentés**</span><span class="sxs-lookup"><span data-stu-id="8f29e-107">**Retail store financials** workspace &gt; **Retail** &gt; **Channels** &gt; **Retail store financials** &gt; **Reports** &gt; **Channel summary report**</span></span>
-   <span data-ttu-id="8f29e-108">**Lekérdezések és jelentések** szekció &gt; **Kiskereskedelem** &gt; **Lekérdezések és jelentések** &gt; **Értékesítési jelentések** &gt; **Csatorna-összefoglaló jelentés**</span><span class="sxs-lookup"><span data-stu-id="8f29e-108">**Inquiries and reports** section &gt; **Retail** &gt; **Inquiries and reports** &gt; **Sales reports** &gt; **Channel summary report**</span></span>

<span data-ttu-id="8f29e-109">Ez a jelentés pillanatképet mutat a következő összegzésekről az üzletteljesítmény részeként:</span><span class="sxs-lookup"><span data-stu-id="8f29e-109">This report provides a snapshot of following summaries as part of store performance:</span></span>

-   <span data-ttu-id="8f29e-110">Bruttó értékesítés összesítése</span><span class="sxs-lookup"><span data-stu-id="8f29e-110">Gross sales summary</span></span>
-   <span data-ttu-id="8f29e-111">Fizetőeszköztípus-összesítő</span><span class="sxs-lookup"><span data-stu-id="8f29e-111">Tender type summary</span></span>
-   <span data-ttu-id="8f29e-112">Adóösszesítés</span><span class="sxs-lookup"><span data-stu-id="8f29e-112">Tax summary</span></span>
-   <span data-ttu-id="8f29e-113">Ár-felülbírálási összesítés</span><span class="sxs-lookup"><span data-stu-id="8f29e-113">Price overrides summary</span></span>
-   <span data-ttu-id="8f29e-114">Engedmények összesítése</span><span class="sxs-lookup"><span data-stu-id="8f29e-114">Discounts summary</span></span>


