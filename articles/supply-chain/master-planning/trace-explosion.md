---
title: Nyomkövetés használata az alábontáshoz
description: Ez a cikk ismerteti, hogyan alkalmazhatja a nyomkövetést a rendelés alábontás eredményeinek alapjául szolgáló okok felfedezésére.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19231
ms.assetid: 9bc9bfbe-a7a9-437b-a947-826229b0585a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5c7166063e7865e02eb4ee914f7984fa78a51e4a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011406"
---
# <a name="use-tracing-for-explosion"></a><span data-ttu-id="1730b-103">Nyomkövetés használata az alábontáshoz</span><span class="sxs-lookup"><span data-stu-id="1730b-103">Use tracing for explosion</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1730b-104">Ez a cikk ismerteti, hogyan alkalmazhatja a nyomkövetést a rendelés alábontás eredményeinek alapjául szolgáló okok felfedezésére.</span><span class="sxs-lookup"><span data-stu-id="1730b-104">This article explains how you can use tracing to explore the causes behind the outcome of an order explosion.</span></span>

<span data-ttu-id="1730b-105">Nyomkövetés engedélyezésével megtekintheti az információt a tényezőkről, amelyek hozzájárulnak adott rendelés alábontásának kimeneteléhez.</span><span class="sxs-lookup"><span data-stu-id="1730b-105">By enabling tracing, you can view information about the factors that contributed to the outcome of the explosion of a particular order.</span></span> <span data-ttu-id="1730b-106">A következő példák bemutatják, hogyan használhatja a nyomkövetési információt:</span><span class="sxs-lookup"><span data-stu-id="1730b-106">The following examples show how you can use the tracing information:</span></span>

-   <span data-ttu-id="1730b-107">Tekintse meg a kapcsolatokat a műveletek és a tervezett rendelések között, hogy optimalizálja az ellátási láncot és a készletfoglalásokat.</span><span class="sxs-lookup"><span data-stu-id="1730b-107">View relations between the actions on planned orders to optimize the supply chain and inventory reservations.</span></span>
-   <span data-ttu-id="1730b-108">Megtekintheti a már jóváhagyott rendelések kapcsolatait.</span><span class="sxs-lookup"><span data-stu-id="1730b-108">View relations to orders that are already approved.</span></span> <span data-ttu-id="1730b-109">Fókuszálhat az automatikusan megerősített származtatott követelményekre, ami után pontosabban állíthatja fel a rendelések fontossági sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="1730b-109">You can focus on automatically firming derived requirements and then prioritize orders more accurately.</span></span>
-   <span data-ttu-id="1730b-110">Szimulálhatja a tervezési eredményeket, hogy meghatározza, hogy a tervezési paraméterek optimálisak-e.</span><span class="sxs-lookup"><span data-stu-id="1730b-110">Simulate planning results to determine whether the planning parameters are optimal.</span></span>
-   <span data-ttu-id="1730b-111">Azonosíthatja, hogy az olyan információ, mint például termelési dátumok, mennyiségek és prioritások hogyan lett meghatározva egy rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="1730b-111">Identify how information such as production dates, quantities, and priorities for an order were determined.</span></span>

<span data-ttu-id="1730b-112">Részleteket tekinthet meg egy kijelölt rendelés határidőiről és műveleteiről.</span><span class="sxs-lookup"><span data-stu-id="1730b-112">You can view details about futures and actions for a selected order.</span></span> <span data-ttu-id="1730b-113">Az **Alábontás** lapon a nyomkövetési információ elérhető a **magyarázat** lapon, a felső ablakban.</span><span class="sxs-lookup"><span data-stu-id="1730b-113">On the **Explosion** page, tracing information is available on the **Explanation** tab in the upper pane.</span></span> <span data-ttu-id="1730b-114">A nyomkövetés akkor történik meg, amikor alábont egy rendelést.</span><span class="sxs-lookup"><span data-stu-id="1730b-114">Tracing occurs when you explode an order.</span></span> <span data-ttu-id="1730b-115">Hogy megkezdje a nyomkövetést egy rendeléshez kattintson a **frissítés** gombra, majd válassza ki a **nyomkövetés engedélyezése** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="1730b-115">To start tracing for the order, click **Update**, and then select the **Enable trace** check box.</span></span> <span data-ttu-id="1730b-116">Használhatja a **Szöveg keresése** mezőt, hogy megkeresse az adott információt a naplóban.</span><span class="sxs-lookup"><span data-stu-id="1730b-116">You can use the **Find text** field to search the log for specific information.</span></span> <span data-ttu-id="1730b-117">A keresési eredmények ki lesznek emelve a fában.</span><span class="sxs-lookup"><span data-stu-id="1730b-117">Search results are highlighted in the tree.</span></span>

<a name="additional-resources"></a><span data-ttu-id="1730b-118">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1730b-118">Additional resources</span></span>
--------

[<span data-ttu-id="1730b-119">Alaptervek áttekintése</span><span class="sxs-lookup"><span data-stu-id="1730b-119">Master plans overview</span></span>](master-plans.md)



