--- 
title: "Online értékesítések és kifizetések feladása"
description: "Ez az eljárás végigveszi egy ismétlődő kötegelt feladat konfigurálásának és futtatásának lépéseit, amellyel értékesítési rendeléseket és kifizetéseket hozhat létre online üzletek tranzakcióihoz."
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 13839bbe6ca03f3cfc7036fce87477bf7d5af2a7
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="posting-of-online-sales-and-payments"></a><span data-ttu-id="1604d-103">Online értékesítések és kifizetések feladása</span><span class="sxs-lookup"><span data-stu-id="1604d-103">Posting of online sales and payments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="1604d-104">Ez az eljárás végigveszi egy ismétlődő kötegelt feladat konfigurálásának és futtatásának lépéseit, amellyel értékesítési rendeléseket és kifizetéseket hozhat létre online üzletek tranzakcióihoz.</span><span class="sxs-lookup"><span data-stu-id="1604d-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="1604d-105">Ez az eljárás az USRT cég adatait használja, mint bemutatóadatokat.</span><span class="sxs-lookup"><span data-stu-id="1604d-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="1604d-106">Ugorjon a következő oldalra: Összes munkaterület > Kiskereskedelmi üzlet pénzügyei.</span><span class="sxs-lookup"><span data-stu-id="1604d-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="1604d-107">Kattintson Rendelések szinkronizálása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1604d-107">Click Synchronize orders.</span></span>
3. <span data-ttu-id="1604d-108">A Szervezeti hierarchia mezőben válassza ki a „Kiskereskedelmi áruházak régiók szerint” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1604d-108">In the Organization hierarchy field, select 'Retail Stores by Region'.</span></span>
    * <span data-ttu-id="1604d-109">Válasszon ki egy bizonyos online üzletet vagy egy csomópontot abban az esetben, ha az üzletek egy csoportjához szeretné létrehozni a kötegelt feladatot.</span><span class="sxs-lookup"><span data-stu-id="1604d-109">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="1604d-110">Kattintson a nyílra a kiválasztás hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="1604d-110">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="1604d-111">Kattintson a Futtatás a háttérben lapra.</span><span class="sxs-lookup"><span data-stu-id="1604d-111">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="1604d-112">Jelölje be vagy törölje a jelölést a Kötegelt feldolgozás jelölőnégyzetben.</span><span class="sxs-lookup"><span data-stu-id="1604d-112">Check or uncheck the Batch processing checkbox.</span></span>
6. <span data-ttu-id="1604d-113">Kattintson az Ismétlődésre.</span><span class="sxs-lookup"><span data-stu-id="1604d-113">Click Recurrence.</span></span>
7. <span data-ttu-id="1604d-114">Válassza a Nincs záró dátum lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1604d-114">Select the No end date option.</span></span>
8. <span data-ttu-id="1604d-115">Írjon be egy számot a Számítás mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1604d-115">In the Count field, enter a number.</span></span>
9. <span data-ttu-id="1604d-116">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="1604d-116">Click OK.</span></span>
10. <span data-ttu-id="1604d-117">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="1604d-117">Click OK.</span></span>


