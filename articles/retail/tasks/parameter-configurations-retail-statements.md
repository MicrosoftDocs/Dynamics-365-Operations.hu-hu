--- 
title: "Paraméter-konfiguráció kiskereskedelmi kimutatásokhoz"
description: "Ez az eljárás a Kiskereskedelmi kimutatások létrehozásának és feladásának módját befolyásoló Kiskereskedelmi paraméterek konfigurációit mutatja be."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: aafccb5c1a3fd98d5f88e450fe138ca7fde44982
ms.contentlocale: hu-hu
ms.lasthandoff: 01/19/2018

---
# <a name="parameter-configurations-for-retail-statements"></a><span data-ttu-id="91b4a-103">Paraméter-konfiguráció kiskereskedelmi kimutatásokhoz</span><span class="sxs-lookup"><span data-stu-id="91b4a-103">Parameter configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="91b4a-104">Ez az eljárás a Kiskereskedelmi kimutatások létrehozásának és feladásának módját befolyásoló Kiskereskedelmi paraméterek konfigurációit mutatja be.</span><span class="sxs-lookup"><span data-stu-id="91b4a-104">This procedure demonstrates configurations for Retail parameters that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="91b4a-105">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="91b4a-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="91b4a-106">Ugrás a Kiskereskedelem > Központ beállítás > Paraméterek > Kiskereskedelmi paraméterek elemre.</span><span class="sxs-lookup"><span data-stu-id="91b4a-106">Go to Retail and commerce > Headquarters setup  > Parameters > Retail parameters.</span></span>
2. <span data-ttu-id="91b4a-107">Kattintson a Feladás lapra.</span><span class="sxs-lookup"><span data-stu-id="91b4a-107">Click the Posting tab.</span></span>
    * <span data-ttu-id="91b4a-108">Ha kifejezetten az időszaki kedvezmények összegét szeretné feladni, akkor válassza az „Igen” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91b4a-108">Select "Yes" if you want to post the periodic discount amounts specifically.</span></span>  
    * <span data-ttu-id="91b4a-109">Válassza a „Normál” lehetőséget alapértelmezett számlák használatához, vagy az „Időszakos” lehetőséget, ha Ön szeretné megadni az egyes időszakos kedvezményekhez használandó számlákat.</span><span class="sxs-lookup"><span data-stu-id="91b4a-109">Select "Standard" to use default accounts, or select "Periodic" if you want to define which account to use for each periodic discount.</span></span>  
    * <span data-ttu-id="91b4a-110">Válassza az „Összegzés” lehetőséget, ha szeretné, hogy a rendszer minden lehetséges alkalommal összesítse a sorokat.</span><span class="sxs-lookup"><span data-stu-id="91b4a-110">Select "Summary" if inventory lines should get aggregated whenever possible.</span></span>  
    * <span data-ttu-id="91b4a-111">Válassza az „Igen” lehetőséget, ha szeretné, hogy a Számlák és a Kifizetések a Kimutatás feladási folyamat során automatikusan rendezésre kerüljenek.</span><span class="sxs-lookup"><span data-stu-id="91b4a-111">Select "Yes" if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
    * <span data-ttu-id="91b4a-112">Válassza az „Igen” lehetőséget, ha szeretné, hogy a Széfes befizetéses tranzakciók összesítésre kerüljenek.</span><span class="sxs-lookup"><span data-stu-id="91b4a-112">Select "Yes" if Safe drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="91b4a-113">Válassza az „Igen” lehetőséget, ha szeretné, hogy a Banki-fizetőeszköz tranzakciók összesítésre kerüljenek.</span><span class="sxs-lookup"><span data-stu-id="91b4a-113">Select "Yes" if Bank drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="91b4a-114">Válassza az „Igen” lehetőséget, ha a Kimutatás-feladásnál szeretné bekapcsolni az összesítést.</span><span class="sxs-lookup"><span data-stu-id="91b4a-114">Select "Yes" to turn aggregation on for Statement posting.</span></span>  
    * <span data-ttu-id="91b4a-115">Válassza az „Igen” lehetőséget, ha szeretne párhuzamosan megrendeléseket hozni létre és dolgozni fel, amikor a kimutatás feladásra kerül.</span><span class="sxs-lookup"><span data-stu-id="91b4a-115">Select "Yes" to create and process orders in parallel when statements are posted.</span></span>  
    * <span data-ttu-id="91b4a-116">Adja meg a kötegelt feladatonként feldolgozandó megrendelések maximális számát.</span><span class="sxs-lookup"><span data-stu-id="91b4a-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="91b4a-117">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="91b4a-117">Click Save.</span></span>


