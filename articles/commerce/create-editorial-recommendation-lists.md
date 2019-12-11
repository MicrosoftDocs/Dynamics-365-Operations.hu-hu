---
title: Válogatott termékek ajánlati listájának létrehozása
description: Ez a témakör azt mutatja be, hogyan tudnak a kereskedők manuális terméklistákat létrehozni a Microsoft Dynamics 365 Commerce-ügyfelek számára.
author: bebeale
manager: AnnBe
ms.date: 10/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 6d075635b7b986cc854550d15f7e941a9ea9cf72
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770413"
---
# <a name="create-curated-product-recommendation-lists"></a><span data-ttu-id="4dc77-103">Válogatott termékek ajánlati listájának létrehozása</span><span class="sxs-lookup"><span data-stu-id="4dc77-103">Create curated product recommendation lists</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="4dc77-104">Ez a témakör azt mutatja be, hogyan tudnak a kereskedők manuális terméklistákat létrehozni a Microsoft Dynamics 365 Commerce-ügyfelek számára.</span><span class="sxs-lookup"><span data-stu-id="4dc77-104">This topic explains how merchandizers can create and manage manual product lists for Microsoft Dynamics 365 Commerce customers.</span></span>

<span data-ttu-id="4dc77-105">A válogatott listák egyéni tartalmak olyan gyűjteménye, amelyet emberek hoztak létre és válogattak.</span><span class="sxs-lookup"><span data-stu-id="4dc77-105">Curated lists are collections of individual content created and curated by people.</span></span>  

## <a name="create-a-new-list"></a><span data-ttu-id="4dc77-106">Új lista létrehozása</span><span class="sxs-lookup"><span data-stu-id="4dc77-106">Create a new list</span></span>

<span data-ttu-id="4dc77-107">Válogatott termékajánlási lista létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="4dc77-107">To create a curated product recommendation list, follow these steps.</span></span>

1. <span data-ttu-id="4dc77-108">Válassza a **Retail** &gt; **Termékjavaslatok** &gt; **Ajánlási listák** elemet.</span><span class="sxs-lookup"><span data-stu-id="4dc77-108">Go to **Retail** &gt; **Product recommendations** &gt; **Recommendation lists**.</span></span>
1. <span data-ttu-id="4dc77-109">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4dc77-109">Select **New**.</span></span>
1. <span data-ttu-id="4dc77-110">A **Listaazonosító** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4dc77-110">In the **List Id** field, enter a value.</span></span>
1. <span data-ttu-id="4dc77-111">A **Listanév** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4dc77-111">In the **List name** field, enter a value.</span></span>
    - <span data-ttu-id="4dc77-112">A **Listanév** a lista címe, amely megjelenik majd a **Termékgyűjtési** modul válogatott listák szakaszában.</span><span class="sxs-lookup"><span data-stu-id="4dc77-112">The **List name** is the title of the list that will appear in the curated lists section of the **Product collection** module.</span></span>
1. <span data-ttu-id="4dc77-113">Ha termékeket szeretne hozzáadni a listához, válassza a **Termékek hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4dc77-113">To add products to the list, select **Add products**.</span></span>
1. <span data-ttu-id="4dc77-114">Ha módosítani szeretné a listán szereplő termékek sorrendjét, írjon be egy értéket a **Megjelenítési sorrend** oszlopában.</span><span class="sxs-lookup"><span data-stu-id="4dc77-114">To change the order of the products in the list, enter a value in the **Display order** column.</span></span>
    - <span data-ttu-id="4dc77-115">Ha két terméknél ugyanaz megjelenítési sorrend értéke, akkor a két eredmény végső sorrendje eltérhet a háttéroldaltól.</span><span class="sxs-lookup"><span data-stu-id="4dc77-115">If two products have the same display order value, then the final order of those two results may differ from the back office.</span></span>
1. <span data-ttu-id="4dc77-116">A lista mentéséhez válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="4dc77-116">Select **Save** to save the list.</span></span>

## <a name="example-list"></a><span data-ttu-id="4dc77-117">Példa listára</span><span class="sxs-lookup"><span data-stu-id="4dc77-117">Example List</span></span>

![Példa – Válogatott lista a háttérirodában](./media/examplecuratedrecolist.png)

## <a name="additional-resources"></a><span data-ttu-id="4dc77-119">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="4dc77-119">Additional resources</span></span>

[<span data-ttu-id="4dc77-120">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="4dc77-120">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="4dc77-121">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="4dc77-121">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="4dc77-122">Termékjavaslat-listák hozzáadása az oldalakhoz</span><span class="sxs-lookup"><span data-stu-id="4dc77-122">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)
