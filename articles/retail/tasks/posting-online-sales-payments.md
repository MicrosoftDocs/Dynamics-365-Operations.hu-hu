--- 
title: " Online értékesítések és kifizetések feladása"
description: "Ez az eljárás végigveszi egy ismétlődő kötegelt feladat konfigurálásának és futtatásának lépéseit, amellyel értékesítési rendeléseket és kifizetéseket hozhat létre online üzletek tranzakcióihoz."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e8c3f861a53a3f5c2de29248523ff4efd5e1d072
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="post-online-sales-and-payments"></a><span data-ttu-id="1c470-103"> Online értékesítések és kifizetések feladása</span><span class="sxs-lookup"><span data-stu-id="1c470-103">Post online sales and payments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="1c470-104">Ez az eljárás végigveszi egy ismétlődő kötegelt feladat konfigurálásának és futtatásának lépéseit, amellyel értékesítési rendeléseket és kifizetéseket hozhat létre online üzletek tranzakcióihoz.</span><span class="sxs-lookup"><span data-stu-id="1c470-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="1c470-105">Ez az eljárás az USRT cég adatait használja, mint bemutatóadatokat.</span><span class="sxs-lookup"><span data-stu-id="1c470-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="1c470-106">Ugorjon a következő oldalra: Összes munkaterület > Kiskereskedelmi üzlet pénzügyei.</span><span class="sxs-lookup"><span data-stu-id="1c470-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="1c470-107">Kattintson Rendelések szinkronizálása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1c470-107">Click Synchronize orders.</span></span>
3. <span data-ttu-id="1c470-108">A Szervezeti hierarchia mezőben válassza ki a „Kiskereskedelmi áruházak régiók szerint” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1c470-108">In the Organization hierarchy field, select 'Retail Stores by Region'.</span></span>
    * <span data-ttu-id="1c470-109">Válasszon ki egy bizonyos online üzletet vagy egy csomópontot abban az esetben, ha az üzletek egy csoportjához szeretné létrehozni a kötegelt feladatot.</span><span class="sxs-lookup"><span data-stu-id="1c470-109">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="1c470-110">Kattintson a nyílra a kiválasztás hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="1c470-110">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="1c470-111">Kattintson a Futtatás a háttérben lapra.</span><span class="sxs-lookup"><span data-stu-id="1c470-111">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="1c470-112">Jelölje be vagy törölje a jelölést a Kötegelt feldolgozás jelölőnégyzetben.</span><span class="sxs-lookup"><span data-stu-id="1c470-112">Check or uncheck the Batch processing checkbox.</span></span>
6. <span data-ttu-id="1c470-113">Kattintson az Ismétlődésre.</span><span class="sxs-lookup"><span data-stu-id="1c470-113">Click Recurrence.</span></span>
7. <span data-ttu-id="1c470-114">Válassza a Nincs záró dátum lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1c470-114">Select the No end date option.</span></span>
8. <span data-ttu-id="1c470-115">Írjon be egy számot a Számítás mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1c470-115">In the Count field, enter a number.</span></span>
9. <span data-ttu-id="1c470-116">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="1c470-116">Click OK.</span></span>
10. <span data-ttu-id="1c470-117">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="1c470-117">Click OK.</span></span>


