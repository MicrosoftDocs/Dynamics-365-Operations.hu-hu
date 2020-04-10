---
title: A kiskereskedelmi kimutatásokat befolyásoló paraméterek konfigurálása
description: Ez a cikk a kimutatások létrehozásának és feladásának módját befolyásoló Commerce paraméterek konfigurációit mutatja be.
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
ms.openlocfilehash: 7892a216d836ebcc297a5b7eb87bc996dd9b91bf
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140835"
---
# <a name="configure-parameters-that-affect-retail-statements"></a><span data-ttu-id="d6f6a-103">A kiskereskedelmi kimutatásokat befolyásoló paraméterek konfigurálása</span><span class="sxs-lookup"><span data-stu-id="d6f6a-103">Configure parameters that affect retail statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d6f6a-104">Ez a cikk a kimutatások létrehozásának és feladásának módját befolyásoló Commerce paraméterek konfigurációit mutatja be.</span><span class="sxs-lookup"><span data-stu-id="d6f6a-104">This topic demonstrates configurations for Commerce parameters that affect how statements get created and posted.</span></span> <span data-ttu-id="d6f6a-105">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="d6f6a-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="d6f6a-106">A navigációs ablaktáblán lépjen a **Modulok > Retail és Commerce > Központ beállítás > Paraméterek > Commerce paraméterek** részhez.</span><span class="sxs-lookup"><span data-stu-id="d6f6a-106">In the navigation pane, go to **Modules > Retail and Commerce > Headquarters setup  > Parameters > Commerce parameters**.</span></span>
2. <span data-ttu-id="d6f6a-107">Lépjen a **Feladás** lapra.</span><span class="sxs-lookup"><span data-stu-id="d6f6a-107">Select the **Posting** tab.</span></span>
    - <span data-ttu-id="d6f6a-108">Ha kifejezetten az időszaki engedmények összegét szeretné feladni, akkor válassza az **Igen** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d6f6a-108">Select **Yes** if you want to post the periodic discount amounts specifically.</span></span>  
    - <span data-ttu-id="d6f6a-109">Válassza a **Normál** lehetőséget az alapértelmezett számlák használatához, vagy az **Időszakos** lehetőséget, ha Ön szeretné megadni az egyes időszakos engedményekhez használandó számlákat.</span><span class="sxs-lookup"><span data-stu-id="d6f6a-109">Select **Standard** to use default accounts, or select **Periodic** if you want to define which account to use for each periodic discount.</span></span>  
      - <span data-ttu-id="d6f6a-110">Válassza az **Összegzés** lehetőséget, ha szeretné, hogy a rendszer minden lehetséges alkalommal összesítse a készlet sorait.</span><span class="sxs-lookup"><span data-stu-id="d6f6a-110">Select **Summary** if inventory lines should get aggregated whenever possible.</span></span>  
      - <span data-ttu-id="d6f6a-111">Válassza az **Igen** lehetőséget, ha szeretné, hogy a rendszer automatikusan rendezze a számlákat és a kifizetéseket a Kimutatásfeladási folyamat során.</span><span class="sxs-lookup"><span data-stu-id="d6f6a-111">Select **Yes** if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
      - <span data-ttu-id="d6f6a-112">Válassza az **Igen** lehetőséget, ha összesíteni szeretné a széfes befizetéses tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="d6f6a-112">Select **Yes** if Safe drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="d6f6a-113">Válassza az **Igen** lehetőséget, ha összesíteni szeretné a banki fizetőeszközökkel végrehajtott tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="d6f6a-113">Select **Yes** if Bank drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="d6f6a-114">Válassza az **Igen** lehetőséget, ha a kimutatásfeladáshoz be szeretné kapcsolni az összesítést.</span><span class="sxs-lookup"><span data-stu-id="d6f6a-114">Select **Yes** to turn aggregation on for Statement posting.</span></span>  
      - <span data-ttu-id="d6f6a-115">Válassza az **Igen** lehetőséget, ha szeretne párhuzamos megrendeléseket létrehozni és feldolgozni a kimutatás feladása során.</span><span class="sxs-lookup"><span data-stu-id="d6f6a-115">Select **Yes** to create and process orders in parallel when statements are posted.</span></span>  
      - <span data-ttu-id="d6f6a-116">Adja meg a kötegelt feladatonként feldolgozandó megrendelések maximális számát.</span><span class="sxs-lookup"><span data-stu-id="d6f6a-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="d6f6a-117">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="d6f6a-117">Select **Save**.</span></span>

