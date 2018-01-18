--- 
title: "Online csatornák létrehozása és a csatorna attribútumainak meghatározása"
description: "Ezzel az eljárással bemutatja, hogyan hozhat létre új online csatornát, és ezt hogyan adhatja hozzá a szervezeti hierarchiához."
author: jashanno
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
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
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: d1cdb36b99abb9902f30a7a487a912f3a213dcf8
ms.contentlocale: hu-hu
ms.lasthandoff: 01/17/2018

---
# <a name="create-online-channels-and-define-channel-attributes"></a><span data-ttu-id="a265b-103">Online csatornák létrehozása és a csatorna attribútumainak meghatározása</span><span class="sxs-lookup"><span data-stu-id="a265b-103">Create online channels and define channel attributes</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="a265b-104">Ezzel az eljárással bemutatja, hogyan hozhat létre új online csatornát, és ezt hogyan adhatja hozzá a szervezeti hierarchiához.</span><span class="sxs-lookup"><span data-stu-id="a265b-104">This procedure walks through creating a new online channel and adding it to the organization hierarchy.</span></span> <span data-ttu-id="a265b-105">Új online csatorna létrehozása előtt létre kell hoznia a szervezeti hierarchiát.</span><span class="sxs-lookup"><span data-stu-id="a265b-105">You must create the organization hierarchy before you can create a new online channel.</span></span> <span data-ttu-id="a265b-106">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="a265b-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-new-online-channel"></a><span data-ttu-id="a265b-107">Hozzon létre egy új online csatornát.</span><span class="sxs-lookup"><span data-stu-id="a265b-107">Create a new online channel</span></span>
1. <span data-ttu-id="a265b-108">Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Csatornák > Online áruházak.</span><span class="sxs-lookup"><span data-stu-id="a265b-108">Go to Retail and commerce > Channels > Online stores.</span></span>
2. <span data-ttu-id="a265b-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a265b-109">Click New.</span></span>
3. <span data-ttu-id="a265b-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a265b-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="a265b-111">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a265b-111">In the Warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="a265b-112">Válasszon ki egy lehetőséget az Üzlet időzónája mezőben.</span><span class="sxs-lookup"><span data-stu-id="a265b-112">In the Store time zone field, select an option.</span></span>
6. <span data-ttu-id="a265b-113">Adjon meg vagy válasszon ki egy értéket az Alapértelmezett vevő mezőben.</span><span class="sxs-lookup"><span data-stu-id="a265b-113">In the Default customer field, enter or select a value.</span></span>
7. <span data-ttu-id="a265b-114">Adjon meg vagy válasszon ki egy értéket a Vevői címjegyzék mezőben.</span><span class="sxs-lookup"><span data-stu-id="a265b-114">In the Customer address book field, enter or select a value.</span></span>
8. <span data-ttu-id="a265b-115">Adjon meg vagy válasszon ki egy értéket a Fizetési feltételek mezőben.</span><span class="sxs-lookup"><span data-stu-id="a265b-115">In the Terms of payment field, enter or select a value.</span></span>
9. <span data-ttu-id="a265b-116">A Fizetési mód mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="a265b-116">In the Method of payment field, enter or select a value.</span></span>
10. <span data-ttu-id="a265b-117">Adjon meg vagy válasszon ki egy értéket az E-mail értesítési profil mezőben.</span><span class="sxs-lookup"><span data-stu-id="a265b-117">In the Email notification profile field, enter or select a value.</span></span>
11. <span data-ttu-id="a265b-118">Bontsa ki a Pénzügyi dimenziók szakaszt.</span><span class="sxs-lookup"><span data-stu-id="a265b-118">Expand the Financial dimensions section.</span></span>
12. <span data-ttu-id="a265b-119">Adjon meg vagy válasszon ki egy értéket az Üzleti egység mezőben.</span><span class="sxs-lookup"><span data-stu-id="a265b-119">In the BusinessUnit field, enter or select a value.</span></span>
    * <span data-ttu-id="a265b-120">Hasonlóképpen állítsa be az értéket minden más alapértelmezett dimenzióra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="a265b-120">Similarly set the value for all the other default dimensions.</span></span>  
13. <span data-ttu-id="a265b-121">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a265b-121">Click Save.</span></span>

## <a name="add-the-online-channel-to-organization-hierarchy"></a><span data-ttu-id="a265b-122">Az online csatorna hozzáadása szervezeti hierarchiához</span><span class="sxs-lookup"><span data-stu-id="a265b-122">Add the online channel to organization hierarchy</span></span>
1. <span data-ttu-id="a265b-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a265b-123">Close the page.</span></span>
2. <span data-ttu-id="a265b-124">Ugrás a Szervezet felügyelete > Szervezetek > Szervezeti hierarchiák menüpontokra.</span><span class="sxs-lookup"><span data-stu-id="a265b-124">Go to Organization administration > Organizations > Organization hierarchies.</span></span>
3. <span data-ttu-id="a265b-125">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="a265b-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="a265b-126">Kattintson a Megtekintés menüpontra.</span><span class="sxs-lookup"><span data-stu-id="a265b-126">Click View.</span></span>
5. <span data-ttu-id="a265b-127">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a265b-127">Click Edit.</span></span>
    * <span data-ttu-id="a265b-128">Az új csatornát bármely hierarchia-csomópont alá beillesztheti.</span><span class="sxs-lookup"><span data-stu-id="a265b-128">You can select any hierarchy node under which you want to insert the new channel.</span></span>  
6. <span data-ttu-id="a265b-129">Kattintson a Beszúrás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a265b-129">Click Insert.</span></span>
7. <span data-ttu-id="a265b-130">Kattintson a Kiskereskedelmi csatorna menüpontra.</span><span class="sxs-lookup"><span data-stu-id="a265b-130">Click Retail channel.</span></span>
8. <span data-ttu-id="a265b-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a265b-131">Click OK.</span></span>
9. <span data-ttu-id="a265b-132">A Közzététel gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="a265b-132">Click Publish to open the drop dialog.</span></span>
10. <span data-ttu-id="a265b-133">Az Érvényesség dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="a265b-133">In the Effective date field, enter a date and time.</span></span>
11. <span data-ttu-id="a265b-134">Kattintson a Közzététel parancsra.</span><span class="sxs-lookup"><span data-stu-id="a265b-134">Click Publish.</span></span>


