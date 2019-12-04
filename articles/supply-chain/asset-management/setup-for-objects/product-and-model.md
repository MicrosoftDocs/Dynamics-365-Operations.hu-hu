---
title: Eszközgyártók és modellek
description: Ez a témakör azt mutatja be, hogyan lehet eszközgyártókat és kapcsolódó modelleket beállítani az Eszközkezelés modulban.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b77605070387871335c480e25cbe23af1155d6e8
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812168"
---
# <a name="asset-manufacturers-and-models"></a><span data-ttu-id="11efd-103">Eszközgyártók és modellek</span><span class="sxs-lookup"><span data-stu-id="11efd-103">Asset manufacturers and models</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="11efd-104">Ez a témakör azt mutatja be, hogyan lehet eszközgyártókat és kapcsolódó modelleket beállítani az Eszközkezelés modulban.</span><span class="sxs-lookup"><span data-stu-id="11efd-104">This topic explains how to set up asset manufacturers and related models in Asset Management.</span></span> <span data-ttu-id="11efd-105">A modellek az eszköztípusokhoz kapcsolhatók.</span><span class="sxs-lookup"><span data-stu-id="11efd-105">Models can be related to asset types.</span></span>

## <a name="set-up-product-model-relations"></a><span data-ttu-id="11efd-106">Termék-modell kapcsolatok beállítása</span><span class="sxs-lookup"><span data-stu-id="11efd-106">Set up product-model relations</span></span>

1. <span data-ttu-id="11efd-107">Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszközök** \> **Gyártó és modell** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="11efd-107">Select **Asset management** \> **Setup** \> **Assets** \> **Manufacturer and model**.</span></span>
2. <span data-ttu-id="11efd-108">Válassza ki az **Új** lehetőséget egy új termék létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="11efd-108">Select **New** to create a new product.</span></span>
3. <span data-ttu-id="11efd-109">Az **Gyártó** mezőben adja meg az eszközgyártó nevét.</span><span class="sxs-lookup"><span data-stu-id="11efd-109">In the **Manufacturer** field, enter a name for the asset manufacturer.</span></span>
4. <span data-ttu-id="11efd-110">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="11efd-110">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="11efd-111">A **Modellek** gyorslap **Hozzáadás** elemét választva hozzon létre egy eszközmodellt, amely az eszköz gyártójához kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="11efd-111">On the **Models** FastTab, select **Add** to create an asset model that should be related to the asset manufacturer.</span></span>
6. <span data-ttu-id="11efd-112">A **Modell** mezőben adja meg az eszközmodell nevét.</span><span class="sxs-lookup"><span data-stu-id="11efd-112">In the **Model** field, enter a name for the asset model.</span></span>
7. <span data-ttu-id="11efd-113">Adjon meg egy leírást a **Leírás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="11efd-113">In the **Description** field, enter a description.</span></span>
8. <span data-ttu-id="11efd-114">Az **Eszköztípus** mezőben válassza ki az eszköztípust, amelyhez a gyártómodell kapcsolódjon.</span><span class="sxs-lookup"><span data-stu-id="11efd-114">In the **Asset type** field, select the asset type that the manufacturer model should be related to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="11efd-115">Az **Eszköztípusok** keresésben beállíthat eszköztípusok, gyártók és modellek közti kapcsolatokat.</span><span class="sxs-lookup"><span data-stu-id="11efd-115">You can also set up relations for asset types, manufacturers, and models in the **Asset types** lookup.</span></span> <span data-ttu-id="11efd-116">További tudnivalókért lásd: [Eszköztípusok](../setup-for-objects/object-types.md).</span><span class="sxs-lookup"><span data-stu-id="11efd-116">For more information, see [Asset types](../setup-for-objects/object-types.md).</span></span>

    <span data-ttu-id="11efd-117">A **Részletek** gyorslapon a **Modellek** mezőben látható a kiválasztott eszközgyártónál beállított eszközmodellek száma.</span><span class="sxs-lookup"><span data-stu-id="11efd-117">In the **Details** FastTab, the **Models** field shows the number of asset models that are set up on the selected asset manufacturer.</span></span> <span data-ttu-id="11efd-118">Az **Eszközök** mező a kiválasztott gyártó által használt eszközök számát jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="11efd-118">The **Assets** field shows the number of assets that are using the selected manufacturer.</span></span>
    
    <span data-ttu-id="11efd-119">Az **Eszközök** mező a kiválasztott gyártói modell által használt objektumok számát jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="11efd-119">The **Assets** field shows the number of objects that are using the manufacturer model.</span></span>

> [!NOTE]
> <span data-ttu-id="11efd-120">Egy eszköztípus nem rendelkezhet eszközgyártó-modell kapcsolatokkal, kapcsolódhat az egyik eszközgyártói modellhez, vagy több eszközgyártói modellhez.</span><span class="sxs-lookup"><span data-stu-id="11efd-120">An asset type can have no asset manufacturer model relations, it can be related to one asset manufacturer model, or it can be related multiple asset manufacturer models.</span></span> <span data-ttu-id="11efd-121">Ha egy eszköztípus legalább egy gyártó modelljéhez kapcsolódik, akkor csak a **Gyártói modell** keresésben megadott kombinációk közül lehet választani azokon az Eszközkezelési oldalakon, ahol az eszköztípus, gyártó és modell kombinációi beállíthatók.</span><span class="sxs-lookup"><span data-stu-id="11efd-121">If an asset type is related to at least one manufacturer model, only the combinations that are set up in the **Manufacturer model** lookup can be selected on those Asset Management pages where a combination of an asset type, manufacturer, and model can be set up.</span></span> <span data-ttu-id="11efd-122">Ezek a lapok tartalmazzák az **Összes eszköz**, **Eszköz szolgáltatási szintje**, **Alapértelmezett feladattípusok** és **Karbantartási költségvetés sorai** mezőket.</span><span class="sxs-lookup"><span data-stu-id="11efd-122">These pages include **All assets**, **Asset service levels**, **Job type defaults**, and **Maintenance budget lines**.</span></span> <span data-ttu-id="11efd-123">Ha bizonyos típusú eszközök nem kapcsolódnak egyik gyártói modellhez sem, akkor csak ezek az eszköztípusok, valamint az eszköztípusokhoz nem kapcsolódó gyártói modellek jelennek meg az oldalakon.</span><span class="sxs-lookup"><span data-stu-id="11efd-123">If some asset types aren't related to any manufacturer model, only those asset types, and manufacturer models that also have no relation to asset types, are shown on the pages.</span></span>

## <a name="select-a-manufacturer-and-model-on-an-object"></a><span data-ttu-id="11efd-124">Egy tárgy gyártójának és modelljének kiválasztása</span><span class="sxs-lookup"><span data-stu-id="11efd-124">Select a manufacturer and model on an object</span></span>

1. <span data-ttu-id="11efd-125">Válassza ki az **Eszközkezelés** \> **Általános** \> **Eszközök** \> **Összes eszköz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="11efd-125">Select **Asset management** \> **Common** \> **Assets** \> **All assets**.</span></span>
2. <span data-ttu-id="11efd-126">Az **Eszköz** oszlopban válassza ki az eszköz hivatkozását.</span><span class="sxs-lookup"><span data-stu-id="11efd-126">In the **Asset** column, select the link for the asset.</span></span> <span data-ttu-id="11efd-127">Megjelenik a **Részletek** oldal.</span><span class="sxs-lookup"><span data-stu-id="11efd-127">The **Details** page appears.</span></span>
3. <span data-ttu-id="11efd-128">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="11efd-128">Select **Edit**.</span></span>
4. <span data-ttu-id="11efd-129">Az **Általános** gyorslapon válassza ki a **Gyártó** és **Modell** mezők értékeit.</span><span class="sxs-lookup"><span data-stu-id="11efd-129">On the **General** FastTab, select values in the **Manufacturer** and **Model** fields.</span></span>
