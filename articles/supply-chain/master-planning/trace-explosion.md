---
title: "Nyomkövetés használata az alábontáshoz"
description: "Ez a cikk ismerteti, hogyan alkalmazhatja a nyomkövetést a rendelés alábontás eredményeinek alapjául szolgáló okok felfedezésére."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19231
ms.assetid: 9bc9bfbe-a7a9-437b-a947-826229b0585a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4e7f765f31ba34481cca78155e77eca61b106d50
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="use-tracing-for-explosion"></a><span data-ttu-id="4f616-103">Nyomkövetés használata az alábontáshoz</span><span class="sxs-lookup"><span data-stu-id="4f616-103">Use tracing for explosion</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4f616-104">Ez a cikk ismerteti, hogyan alkalmazhatja a nyomkövetést a rendelés alábontás eredményeinek alapjául szolgáló okok felfedezésére.</span><span class="sxs-lookup"><span data-stu-id="4f616-104">This article explains how you can use tracing to explore the causes behind the outcome of an order explosion.</span></span>

<span data-ttu-id="4f616-105">Nyomkövetés engedélyezésével megtekintheti az információt a tényezőkről, amelyek hozzájárulnak adott rendelés alábontásának kimeneteléhez.</span><span class="sxs-lookup"><span data-stu-id="4f616-105">By enabling tracing, you can view information about the factors that contributed to the outcome of the explosion of a particular order.</span></span> <span data-ttu-id="4f616-106">A következő példák bemutatják, hogyan használhatja a nyomkövetési információt:</span><span class="sxs-lookup"><span data-stu-id="4f616-106">The following examples show how you can use the tracing information:</span></span>

-   <span data-ttu-id="4f616-107">Tekintse meg a kapcsolatokat a műveletek és a tervezett rendelések között, hogy optimalizálja az ellátási láncot és a készletfoglalásokat.</span><span class="sxs-lookup"><span data-stu-id="4f616-107">View relations between the actions on planned orders to optimize the supply chain and inventory reservations.</span></span>
-   <span data-ttu-id="4f616-108">Megtekintheti a már jóváhagyott rendelések kapcsolatait.</span><span class="sxs-lookup"><span data-stu-id="4f616-108">View relations to orders that are already approved.</span></span> <span data-ttu-id="4f616-109">Fókuszálhat az automatikusan megerősített származtatott követelményekre, ami után pontosabban állíthatja fel a rendelések fontossági sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="4f616-109">You can focus on automatically firming derived requirements and then prioritize orders more accurately.</span></span>
-   <span data-ttu-id="4f616-110">Szimulálhatja a tervezési eredményeket, hogy meghatározza, hogy a tervezési paraméterek optimálisak-e.</span><span class="sxs-lookup"><span data-stu-id="4f616-110">Simulate planning results to determine whether the planning parameters are optimal.</span></span>
-   <span data-ttu-id="4f616-111">Azonosíthatja, hogy az olyan információ, mint például termelési dátumok, mennyiségek és prioritások hogyan lett meghatározva egy rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="4f616-111">Identify how information such as production dates, quantities, and priorities for an order were determined.</span></span>

<span data-ttu-id="4f616-112">Részleteket tekinthet meg egy kijelölt rendelés határidőiről és műveleteiről.</span><span class="sxs-lookup"><span data-stu-id="4f616-112">You can view details about futures and actions for a selected order.</span></span> <span data-ttu-id="4f616-113">Az **Alábontás** lapon a nyomkövetési információ elérhető a **magyarázat** lapon, a felső ablakban.</span><span class="sxs-lookup"><span data-stu-id="4f616-113">On the **Explosion** page, tracing information is available on the **Explanation** tab in the upper pane.</span></span> <span data-ttu-id="4f616-114">A nyomkövetés akkor történik meg, amikor alábont egy rendelést.</span><span class="sxs-lookup"><span data-stu-id="4f616-114">Tracing occurs when you explode an order.</span></span> <span data-ttu-id="4f616-115">Hogy megkezdje a nyomkövetést egy rendeléshez kattintson a **frissítés** gombra, majd válassza ki a **nyomkövetés engedélyezése** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="4f616-115">To start tracing for the order, click **Update**, and then select the **Enable trace** check box.</span></span> <span data-ttu-id="4f616-116">Használhatja a **Szöveg keresése** mezőt, hogy megkeresse az adott információt a naplóban.</span><span class="sxs-lookup"><span data-stu-id="4f616-116">You can use the **Find text** field to search the log for specific information.</span></span> <span data-ttu-id="4f616-117">A keresési eredmények ki lesznek emelve a fában.</span><span class="sxs-lookup"><span data-stu-id="4f616-117">Search results are highlighted in the tree.</span></span>

<a name="see-also"></a><span data-ttu-id="4f616-118">Lásd még</span><span class="sxs-lookup"><span data-stu-id="4f616-118">See also</span></span>
--------

[<span data-ttu-id="4f616-119">Alaptervek</span><span class="sxs-lookup"><span data-stu-id="4f616-119">Master plans</span></span>](master-plans.md)




