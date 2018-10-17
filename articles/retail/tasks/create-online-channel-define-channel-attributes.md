--- 
title: "Online csatorna létrehozása és a csatorna attribútumainak meghatározása"
description: "Ezzel az eljárással bemutatja, hogyan hozhat létre új online csatornát, és ezt hogyan adhatja hozzá a szervezeti hierarchiához."
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: RetailSPOnlineStoreDetailPage, SysLookupMultiSelectGrid, DimensionLookup, OMHierarchyManager, HierarchyDesigner, OMNodeSelection, HierarchyPublishAndCloseForm
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
ms.openlocfilehash: e066e9901a97bd5b72815a7af472247ef519ecb9
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="create-online-channel-and-define-channel-attributes"></a><span data-ttu-id="b36fa-103">Online csatorna létrehozása és a csatorna attribútumainak meghatározása</span><span class="sxs-lookup"><span data-stu-id="b36fa-103">Create online channel and define channel attributes</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="b36fa-104">Ezzel az eljárással bemutatja, hogyan hozhat létre új online csatornát, és ezt hogyan adhatja hozzá a szervezeti hierarchiához.</span><span class="sxs-lookup"><span data-stu-id="b36fa-104">This procedure walks through creating a new online channel and adding it to the organization hierarchy.</span></span> <span data-ttu-id="b36fa-105">Új online csatorna létrehozása előtt létre kell hoznia a szervezeti hierarchiát.</span><span class="sxs-lookup"><span data-stu-id="b36fa-105">You must create the organization hierarchy before you can create a new online channel.</span></span> <span data-ttu-id="b36fa-106">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="b36fa-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-new-online-channel"></a><span data-ttu-id="b36fa-107">Hozzon létre egy új online csatornát.</span><span class="sxs-lookup"><span data-stu-id="b36fa-107">Create a new online channel</span></span>
1. <span data-ttu-id="b36fa-108">Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Csatornák > Online áruházak.</span><span class="sxs-lookup"><span data-stu-id="b36fa-108">Go to Retail and commerce > Channels > Online stores.</span></span>
2. <span data-ttu-id="b36fa-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b36fa-109">Click New.</span></span>
3. <span data-ttu-id="b36fa-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="b36fa-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="b36fa-111">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b36fa-111">In the Warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="b36fa-112">Válasszon ki egy lehetőséget az Üzlet időzónája mezőben.</span><span class="sxs-lookup"><span data-stu-id="b36fa-112">In the Store time zone field, select an option.</span></span>
6. <span data-ttu-id="b36fa-113">Adjon meg vagy válasszon ki egy értéket az Alapértelmezett vevő mezőben.</span><span class="sxs-lookup"><span data-stu-id="b36fa-113">In the Default customer field, enter or select a value.</span></span>
7. <span data-ttu-id="b36fa-114">Adjon meg vagy válasszon ki egy értéket a Vevői címjegyzék mezőben.</span><span class="sxs-lookup"><span data-stu-id="b36fa-114">In the Customer address book field, enter or select a value.</span></span>
8. <span data-ttu-id="b36fa-115">Adjon meg vagy válasszon ki egy értéket a Fizetési feltételek mezőben.</span><span class="sxs-lookup"><span data-stu-id="b36fa-115">In the Terms of payment field, enter or select a value.</span></span>
9. <span data-ttu-id="b36fa-116">A Fizetési mód mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="b36fa-116">In the Method of payment field, enter or select a value.</span></span>
10. <span data-ttu-id="b36fa-117">Adjon meg vagy válasszon ki egy értéket az E-mail értesítési profil mezőben.</span><span class="sxs-lookup"><span data-stu-id="b36fa-117">In the Email notification profile field, enter or select a value.</span></span>
11. <span data-ttu-id="b36fa-118">Bontsa ki a Pénzügyi dimenziók szakaszt.</span><span class="sxs-lookup"><span data-stu-id="b36fa-118">Expand the Financial dimensions section.</span></span>
12. <span data-ttu-id="b36fa-119">Adjon meg vagy válasszon ki egy értéket az Üzleti egység mezőben.</span><span class="sxs-lookup"><span data-stu-id="b36fa-119">In the BusinessUnit field, enter or select a value.</span></span>
    * <span data-ttu-id="b36fa-120">Hasonlóképpen állítsa be az értéket minden más alapértelmezett dimenzióra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="b36fa-120">Similarly set the value for all the other default dimensions.</span></span>  
13. <span data-ttu-id="b36fa-121">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="b36fa-121">Click Save.</span></span>

## <a name="add-the-online-channel-to-organization-hierarchy"></a><span data-ttu-id="b36fa-122">Az online csatorna hozzáadása szervezeti hierarchiához</span><span class="sxs-lookup"><span data-stu-id="b36fa-122">Add the online channel to organization hierarchy</span></span>
1. <span data-ttu-id="b36fa-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b36fa-123">Close the page.</span></span>
2. <span data-ttu-id="b36fa-124">Ugrás a Szervezet felügyelete > Szervezetek > Szervezeti hierarchiák menüpontokra.</span><span class="sxs-lookup"><span data-stu-id="b36fa-124">Go to Organization administration > Organizations > Organization hierarchies.</span></span>
3. <span data-ttu-id="b36fa-125">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="b36fa-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="b36fa-126">Kattintson a Megtekintés menüpontra.</span><span class="sxs-lookup"><span data-stu-id="b36fa-126">Click View.</span></span>
5. <span data-ttu-id="b36fa-127">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b36fa-127">Click Edit.</span></span>
    * <span data-ttu-id="b36fa-128">Az új csatornát bármely hierarchia-csomópont alá beillesztheti.</span><span class="sxs-lookup"><span data-stu-id="b36fa-128">You can select any hierarchy node under which you want to insert the new channel.</span></span>  
6. <span data-ttu-id="b36fa-129">Kattintson a Beszúrás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b36fa-129">Click Insert.</span></span>
7. <span data-ttu-id="b36fa-130">Kattintson a Kiskereskedelmi csatorna menüpontra.</span><span class="sxs-lookup"><span data-stu-id="b36fa-130">Click Retail channel.</span></span>
8. <span data-ttu-id="b36fa-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="b36fa-131">Click OK.</span></span>
9. <span data-ttu-id="b36fa-132">A Közzététel gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="b36fa-132">Click Publish to open the drop dialog.</span></span>
10. <span data-ttu-id="b36fa-133">Az Érvényesség dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="b36fa-133">In the Effective date field, enter a date and time.</span></span>
11. <span data-ttu-id="b36fa-134">Kattintson a Közzététel parancsra.</span><span class="sxs-lookup"><span data-stu-id="b36fa-134">Click Publish.</span></span>


