--- 
title: "Online csatornák létrehozása és a csatorna attribútumainak meghatározása"
description: "Ezzel az eljárással bemutatja, hogyan hozhat létre új online csatornát, és ezt hogyan adhatja hozzá a szervezeti hierarchiához."
author: jashanno
manager: AnnBe
ms.date: 03/02/2016
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 748c536692043a4cfe7d8b087066e12b3e7ddadc
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="create-online-channels-and-define-channel-attributes"></a><span data-ttu-id="14fb3-103">Online csatornák létrehozása és a csatorna attribútumainak meghatározása</span><span class="sxs-lookup"><span data-stu-id="14fb3-103">Create online channels and define channel attributes</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="14fb3-104">Ezzel az eljárással bemutatja, hogyan hozhat létre új online csatornát, és ezt hogyan adhatja hozzá a szervezeti hierarchiához.</span><span class="sxs-lookup"><span data-stu-id="14fb3-104">This procedure walks through creating a new online channel and adding it to the organization hierarchy.</span></span> <span data-ttu-id="14fb3-105">Új online csatorna létrehozása előtt létre kell hoznia a szervezeti hierarchiát.</span><span class="sxs-lookup"><span data-stu-id="14fb3-105">You must create the organization hierarchy before you can create a new online channel.</span></span> <span data-ttu-id="14fb3-106">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="14fb3-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-new-online-channel"></a><span data-ttu-id="14fb3-107">Hozzon létre egy új online csatornát.</span><span class="sxs-lookup"><span data-stu-id="14fb3-107">Create a new online channel</span></span>
1. <span data-ttu-id="14fb3-108">Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Csatornák > Online áruházak.</span><span class="sxs-lookup"><span data-stu-id="14fb3-108">Go to Retail and commerce > Channels > Online stores.</span></span>
2. <span data-ttu-id="14fb3-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="14fb3-109">Click New.</span></span>
3. <span data-ttu-id="14fb3-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="14fb3-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="14fb3-111">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="14fb3-111">In the Warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="14fb3-112">Válasszon ki egy lehetőséget az Üzlet időzónája mezőben.</span><span class="sxs-lookup"><span data-stu-id="14fb3-112">In the Store time zone field, select an option.</span></span>
6. <span data-ttu-id="14fb3-113">Adjon meg vagy válasszon ki egy értéket az Alapértelmezett vevő mezőben.</span><span class="sxs-lookup"><span data-stu-id="14fb3-113">In the Default customer field, enter or select a value.</span></span>
7. <span data-ttu-id="14fb3-114">Adjon meg vagy válasszon ki egy értéket a Vevői címjegyzék mezőben.</span><span class="sxs-lookup"><span data-stu-id="14fb3-114">In the Customer address book field, enter or select a value.</span></span>
8. <span data-ttu-id="14fb3-115">Adjon meg vagy válasszon ki egy értéket a Fizetési feltételek mezőben.</span><span class="sxs-lookup"><span data-stu-id="14fb3-115">In the Terms of payment field, enter or select a value.</span></span>
9. <span data-ttu-id="14fb3-116">A Fizetési mód mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="14fb3-116">In the Method of payment field, enter or select a value.</span></span>
10. <span data-ttu-id="14fb3-117">Adjon meg vagy válasszon ki egy értéket az E-mail értesítési profil mezőben.</span><span class="sxs-lookup"><span data-stu-id="14fb3-117">In the Email notification profile field, enter or select a value.</span></span>
11. <span data-ttu-id="14fb3-118">Bontsa ki a Pénzügyi dimenziók szakaszt.</span><span class="sxs-lookup"><span data-stu-id="14fb3-118">Expand the Financial dimensions section.</span></span>
12. <span data-ttu-id="14fb3-119">Adjon meg vagy válasszon ki egy értéket az Üzleti egység mezőben.</span><span class="sxs-lookup"><span data-stu-id="14fb3-119">In the BusinessUnit field, enter or select a value.</span></span>
    * <span data-ttu-id="14fb3-120">Hasonlóképpen állítsa be az értéket minden más alapértelmezett dimenzióra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="14fb3-120">Similarly set the value for all the other default dimensions.</span></span>  
13. <span data-ttu-id="14fb3-121">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="14fb3-121">Click Save.</span></span>

## <a name="add-the-online-channel-to-organization-hierarchy"></a><span data-ttu-id="14fb3-122">Az online csatorna hozzáadása szervezeti hierarchiához</span><span class="sxs-lookup"><span data-stu-id="14fb3-122">Add the online channel to organization hierarchy</span></span>
1. <span data-ttu-id="14fb3-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="14fb3-123">Close the page.</span></span>
2. <span data-ttu-id="14fb3-124">Ugrás a Szervezet felügyelete > Szervezetek > Szervezeti hierarchiák menüpontokra.</span><span class="sxs-lookup"><span data-stu-id="14fb3-124">Go to Organization administration > Organizations > Organization hierarchies.</span></span>
3. <span data-ttu-id="14fb3-125">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="14fb3-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="14fb3-126">Kattintson a Megtekintés menüpontra.</span><span class="sxs-lookup"><span data-stu-id="14fb3-126">Click View.</span></span>
5. <span data-ttu-id="14fb3-127">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="14fb3-127">Click Edit.</span></span>
    * <span data-ttu-id="14fb3-128">Az új csatornát bármely hierarchia-csomópont alá beillesztheti.</span><span class="sxs-lookup"><span data-stu-id="14fb3-128">You can select any hierarchy node under which you want to insert the new channel.</span></span>  
6. <span data-ttu-id="14fb3-129">Kattintson a Beszúrás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="14fb3-129">Click Insert.</span></span>
7. <span data-ttu-id="14fb3-130">Kattintson a Kiskereskedelmi csatorna menüpontra.</span><span class="sxs-lookup"><span data-stu-id="14fb3-130">Click Retail channel.</span></span>
8. <span data-ttu-id="14fb3-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="14fb3-131">Click OK.</span></span>
9. <span data-ttu-id="14fb3-132">A Közzététel gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="14fb3-132">Click Publish to open the drop dialog.</span></span>
10. <span data-ttu-id="14fb3-133">Az Érvényesség dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="14fb3-133">In the Effective date field, enter a date and time.</span></span>
11. <span data-ttu-id="14fb3-134">Kattintson a Közzététel parancsra.</span><span class="sxs-lookup"><span data-stu-id="14fb3-134">Click Publish.</span></span>


