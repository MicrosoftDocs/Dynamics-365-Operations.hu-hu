---
title: Válogatott ajánlások manuális létrehozása
description: Ez a témakör azt mutatja be, hogyan tudnak a kereskedők manuálisan terméklistákat létrehozni a Microsoft Dynamics 365 Commerce-ügyfelek számára.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
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
ms.openlocfilehash: 0b866704b419fb07dcf1ddd386af2f7d6cfa02e2
ms.sourcegitcommit: fdc5dd9eb784c7d8e75692c8cdba083fe0dd87ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/26/2020
ms.locfileid: "3404116"
---
# <a name="manually-create-curated-recommendations"></a><span data-ttu-id="5de7e-103">Válogatott ajánlások manuális létrehozása</span><span class="sxs-lookup"><span data-stu-id="5de7e-103">Manually create curated recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5de7e-104">Ez a témakör azt mutatja be, hogyan tudnak a kereskedők manuálisan termékajánlásokat létrehozni a Microsoft Dynamics 365 Commerce-ügyfelek számára.</span><span class="sxs-lookup"><span data-stu-id="5de7e-104">This topic explains how merchandizers can manually create and manage product recommendations lists for Microsoft Dynamics 365 Commerce customers.</span></span>

<span data-ttu-id="5de7e-105">A válogatott listák egyéni tartalmak olyan gyűjteményei, amelyet emberek hoztak létre és válogattak.</span><span class="sxs-lookup"><span data-stu-id="5de7e-105">Curated lists are collections of individual content, created and curated by people.</span></span>  

## <a name="create-a-new-list"></a><span data-ttu-id="5de7e-106">Új lista létrehozása</span><span class="sxs-lookup"><span data-stu-id="5de7e-106">Create a new list</span></span>

<span data-ttu-id="5de7e-107">Válogatott termékajánlási lista létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="5de7e-107">To create a curated product recommendation list, follow these steps.</span></span>

1. <span data-ttu-id="5de7e-108">Válassza a **Retail and Commerce &gt; Termékjavaslatok &gt; Ajánlási listák** elemet.</span><span class="sxs-lookup"><span data-stu-id="5de7e-108">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation lists**.</span></span>
1. <span data-ttu-id="5de7e-109">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5de7e-109">Select **New**.</span></span>
1. <span data-ttu-id="5de7e-110">A **Listaazonosító** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5de7e-110">In the **List Id** field, enter a value.</span></span>
1. <span data-ttu-id="5de7e-111">A **Listanév** mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="5de7e-111">In the **List name** field, enter a value.</span></span>
    - <span data-ttu-id="5de7e-112">A **Listanév** a lista címe, amely megjelenik majd a **Termékgyűjtési** modul válogatott listák szakaszában.</span><span class="sxs-lookup"><span data-stu-id="5de7e-112">The **List name** is the title of the list that will appear in the curated lists section of the **Product collection** module.</span></span>
1. <span data-ttu-id="5de7e-113">Ha termékeket szeretne hozzáadni a listához, válassza a **Termékek hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5de7e-113">To add products to the list, select **Add products**.</span></span>
1. <span data-ttu-id="5de7e-114">Ha módosítani szeretné a listán szereplő termékek sorrendjét, írjon be egy értéket a **Megjelenítési sorrend** oszlopában.</span><span class="sxs-lookup"><span data-stu-id="5de7e-114">To change the order of the products in the list, enter a value in the **Display order** column.</span></span>
    - <span data-ttu-id="5de7e-115">Ha két terméknél ugyanaz megjelenítési sorrend értéke, akkor a két eredmény végső sorrendje eltérhet a háttéroldaltól.</span><span class="sxs-lookup"><span data-stu-id="5de7e-115">If two products have the same display order value, then the final order of those two results may differ from the back office.</span></span>
1. <span data-ttu-id="5de7e-116">A lista mentéséhez válassza a **Mentés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="5de7e-116">Select **Save** to save the list.</span></span>

## <a name="example-list"></a><span data-ttu-id="5de7e-117">Példa listára</span><span class="sxs-lookup"><span data-stu-id="5de7e-117">Example List</span></span>

![Példa – Válogatott lista a háttérirodában](./media/examplecuratedrecolist.png)

## <a name="additional-resources"></a><span data-ttu-id="5de7e-119">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="5de7e-119">Additional resources</span></span>

[<span data-ttu-id="5de7e-120">Termékajánlatok áttekintése</span><span class="sxs-lookup"><span data-stu-id="5de7e-120">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="5de7e-121">Az Azure Data Lake Storage engedélyezése a Dynamics 365 Commerce környezetben</span><span class="sxs-lookup"><span data-stu-id="5de7e-121">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="5de7e-122">Termékajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="5de7e-122">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="5de7e-123">Személyre szabott ajánlatok engedélyezése</span><span class="sxs-lookup"><span data-stu-id="5de7e-123">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="5de7e-124">Személyre szabott termékajánlatok kikapcsolása</span><span class="sxs-lookup"><span data-stu-id="5de7e-124">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="5de7e-125">Termékajánlások hozzáadása a pénztárnál</span><span class="sxs-lookup"><span data-stu-id="5de7e-125">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="5de7e-126">Ajánlatok hozzáadása a tranzakció képernyőjéhez</span><span class="sxs-lookup"><span data-stu-id="5de7e-126">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="5de7e-127">AI-ML ajánlások eredményeinek helyesbítése</span><span class="sxs-lookup"><span data-stu-id="5de7e-127">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="5de7e-128">Ajánlások létrehozása bemutató adatokkal</span><span class="sxs-lookup"><span data-stu-id="5de7e-128">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="5de7e-129">Termékajánlatok GYIK-je</span><span class="sxs-lookup"><span data-stu-id="5de7e-129">Product recommendations FAQ</span></span>](faq-recommendations.md)
