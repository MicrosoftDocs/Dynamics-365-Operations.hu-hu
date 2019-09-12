---
title: A kiskereskedelmi kimutatásokat befolyásoló kiskereskedelmi paraméterek konfigurálása
description: Ez a cikk a Kiskereskedelmi kimutatások létrehozásának és feladásának módját befolyásoló Kiskereskedelmi paraméterek konfigurációit mutatja be.
author: josaw1
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b9a0386a4d61395903e82d988244dd131c1febaf
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867271"
---
# <a name="configure-retail-parameters-that-affect-retail-statements"></a><span data-ttu-id="51e8b-103">A kiskereskedelmi kimutatásokat befolyásoló kiskereskedelmi paraméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="51e8b-103">Configure Retail parameters that affect retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="51e8b-104">Ez a cikk a Kiskereskedelmi kimutatások létrehozásának és feladásának módját befolyásoló Kiskereskedelmi paraméterek konfigurációit mutatja be.</span><span class="sxs-lookup"><span data-stu-id="51e8b-104">This topic demonstrates configurations for Retail parameters that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="51e8b-105">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="51e8b-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="51e8b-106">A navigációs ablaktáblán lépjen a **Modulok > Kiskereskedelem és kereskedelem > Központ beállítás > Paraméterek > Kiskereskedelmi paraméterek** részhez.</span><span class="sxs-lookup"><span data-stu-id="51e8b-106">In the navigation pane, go to **Modules > Retail and commerce > Headquarters setup  > Parameters > Retail parameters**.</span></span>
2. <span data-ttu-id="51e8b-107">Lépjen a **Feladás** lapra.</span><span class="sxs-lookup"><span data-stu-id="51e8b-107">Select the **Posting** tab.</span></span>
    - <span data-ttu-id="51e8b-108">Ha kifejezetten az időszaki engedmények összegét szeretné feladni, akkor válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="51e8b-108">Select **Yes** if you want to post the periodic discount amounts specifically.</span></span>  
    - <span data-ttu-id="51e8b-109">Válassza a **Normál** lehetőséget az alapértelmezett számlák használatához, vagy az **Időszakos** lehetőséget, ha Ön szeretné megadni az egyes időszakos engedményekhez használandó számlákat.</span><span class="sxs-lookup"><span data-stu-id="51e8b-109">Select **Standard** to use default accounts, or select **Periodic** if you want to define which account to use for each periodic discount.</span></span>  
      - <span data-ttu-id="51e8b-110">Válassza az **Összegzés** lehetőséget, ha szeretné, hogy a rendszer minden lehetséges alkalommal összesítse a készlet sorait.</span><span class="sxs-lookup"><span data-stu-id="51e8b-110">Select **Summary** if inventory lines should get aggregated whenever possible.</span></span>  
      - <span data-ttu-id="51e8b-111">Válassza az **Igen** lehetőséget, ha szeretné, hogy a rendszer automatikusan rendezze a számlákat és a kifizetéseket a Kimutatásfeladási folyamat során.</span><span class="sxs-lookup"><span data-stu-id="51e8b-111">Select **Yes** if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
      - <span data-ttu-id="51e8b-112">Válassza az **Igen** lehetőséget, ha összesíteni szeretné a széfes befizetéses tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="51e8b-112">Select **Yes** if Safe drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="51e8b-113">Válassza az **Igen** lehetőséget, ha összesíteni szeretné a banki fizetőeszközökkel végrehajtott tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="51e8b-113">Select **Yes** if Bank drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="51e8b-114">Válassza az **Igen** lehetőséget, ha a kimutatásfeladáshoz be szeretné kapcsolni az összesítést.</span><span class="sxs-lookup"><span data-stu-id="51e8b-114">Select **Yes** to turn aggregation on for Statement posting.</span></span>  
      - <span data-ttu-id="51e8b-115">Válassza az **Igen** lehetőséget, ha szeretne párhuzamos megrendeléseket létrehozni és feldolgozni a kimutatás feladása során.</span><span class="sxs-lookup"><span data-stu-id="51e8b-115">Select **Yes** to create and process orders in parallel when statements are posted.</span></span>  
      - <span data-ttu-id="51e8b-116">Adja meg a kötegelt feladatonként feldolgozandó megrendelések maximális számát.</span><span class="sxs-lookup"><span data-stu-id="51e8b-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="51e8b-117">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="51e8b-117">Select **Save**.</span></span>

