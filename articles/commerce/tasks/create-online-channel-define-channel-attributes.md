---
title: Online csatorna létrehozása és a csatorna attribútumainak meghatározása
description: Ezzel az eljárással bemutatja, hogyan hozhat létre új online csatornát, és ezt hogyan adhatja hozzá a szervezeti hierarchiához.
author: jashanno
manager: AnnBe
ms.date: 06/04/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailSPOnlineStoreDetailPage, SysLookupMultiSelectGrid, DimensionLookup, OMHierarchyManager, HierarchyDesigner, OMNodeSelection, HierarchyPublishAndCloseForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f15b035c01801041d637a2d315d8a3ddcc9d6540
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140941"
---
# <a name="create-online-channel-and-define-channel-attributes"></a><span data-ttu-id="8a73e-103">Online csatorna létrehozása és a csatorna attribútumainak meghatározása</span><span class="sxs-lookup"><span data-stu-id="8a73e-103">Create online channel and define channel attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8a73e-104">Ezzel az eljárással bemutatja, hogyan hozhat létre új online csatornát, és ezt hogyan adhatja hozzá a szervezeti hierarchiához.</span><span class="sxs-lookup"><span data-stu-id="8a73e-104">This procedure walks through creating a new online channel and adding it to the organization hierarchy.</span></span> <span data-ttu-id="8a73e-105">Új online csatorna létrehozása előtt létre kell hoznia a szervezeti hierarchiát.</span><span class="sxs-lookup"><span data-stu-id="8a73e-105">You must create the organization hierarchy before you can create a new online channel.</span></span> <span data-ttu-id="8a73e-106">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="8a73e-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-new-online-channel"></a><span data-ttu-id="8a73e-107">Hozzon létre egy új online csatornát.</span><span class="sxs-lookup"><span data-stu-id="8a73e-107">Create a new online channel</span></span>
1. <span data-ttu-id="8a73e-108">Nyissa meg a következőt: Kiskereskedelem és kereskedelem > Csatornák > Online áruházak.</span><span class="sxs-lookup"><span data-stu-id="8a73e-108">Go to Retail and Commerce > Channels > Online stores.</span></span>
2. <span data-ttu-id="8a73e-109">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="8a73e-109">Click New.</span></span>
3. <span data-ttu-id="8a73e-110">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="8a73e-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="8a73e-111">A Raktár mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8a73e-111">In the Warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="8a73e-112">Válasszon ki egy lehetőséget az Üzlet időzónája mezőben.</span><span class="sxs-lookup"><span data-stu-id="8a73e-112">In the Store time zone field, select an option.</span></span>
6. <span data-ttu-id="8a73e-113">Adjon meg vagy válasszon ki egy értéket az Alapértelmezett vevő mezőben.</span><span class="sxs-lookup"><span data-stu-id="8a73e-113">In the Default customer field, enter or select a value.</span></span>
7. <span data-ttu-id="8a73e-114">Adjon meg vagy válasszon ki egy értéket a Vevői címjegyzék mezőben.</span><span class="sxs-lookup"><span data-stu-id="8a73e-114">In the Customer address book field, enter or select a value.</span></span>
8. <span data-ttu-id="8a73e-115">Adjon meg vagy válasszon ki egy értéket a Fizetési feltételek mezőben.</span><span class="sxs-lookup"><span data-stu-id="8a73e-115">In the Terms of payment field, enter or select a value.</span></span>
9. <span data-ttu-id="8a73e-116">A Fizetési mód mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="8a73e-116">In the Method of payment field, enter or select a value.</span></span>
10. <span data-ttu-id="8a73e-117">Adjon meg vagy válasszon ki egy értéket az E-mail értesítési profil mezőben.</span><span class="sxs-lookup"><span data-stu-id="8a73e-117">In the Email notification profile field, enter or select a value.</span></span>
11. <span data-ttu-id="8a73e-118">Bontsa ki a Pénzügyi dimenziók szakaszt.</span><span class="sxs-lookup"><span data-stu-id="8a73e-118">Expand the Financial dimensions section.</span></span>
12. <span data-ttu-id="8a73e-119">Adjon meg vagy válasszon ki egy értéket az Üzleti egység mezőben.</span><span class="sxs-lookup"><span data-stu-id="8a73e-119">In the BusinessUnit field, enter or select a value.</span></span>
    * <span data-ttu-id="8a73e-120">Hasonlóképpen állítsa be az értéket minden más alapértelmezett dimenzióra vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="8a73e-120">Similarly set the value for all the other default dimensions.</span></span>  
13. <span data-ttu-id="8a73e-121">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="8a73e-121">Click Save.</span></span>

## <a name="add-the-online-channel-to-organization-hierarchy"></a><span data-ttu-id="8a73e-122">Az online csatorna hozzáadása szervezeti hierarchiához</span><span class="sxs-lookup"><span data-stu-id="8a73e-122">Add the online channel to organization hierarchy</span></span>
1. <span data-ttu-id="8a73e-123">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="8a73e-123">Close the page.</span></span>
2. <span data-ttu-id="8a73e-124">Ugrás a Szervezet felügyelete > Szervezetek > Szervezeti hierarchiák menüpontokra.</span><span class="sxs-lookup"><span data-stu-id="8a73e-124">Go to Organization administration > Organizations > Organization hierarchies.</span></span>
3. <span data-ttu-id="8a73e-125">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="8a73e-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="8a73e-126">Kattintson a Megtekintés menüpontra.</span><span class="sxs-lookup"><span data-stu-id="8a73e-126">Click View.</span></span>
5. <span data-ttu-id="8a73e-127">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a73e-127">Click Edit.</span></span>
    * <span data-ttu-id="8a73e-128">Az új csatornát bármely hierarchia-csomópont alá beillesztheti.</span><span class="sxs-lookup"><span data-stu-id="8a73e-128">You can select any hierarchy node under which you want to insert the new channel.</span></span>  
6. <span data-ttu-id="8a73e-129">Kattintson a Beszúrás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a73e-129">Click Insert.</span></span>
7. <span data-ttu-id="8a73e-130">Kattintson a Commerce csatorna elemre.</span><span class="sxs-lookup"><span data-stu-id="8a73e-130">Click Commerce channel.</span></span>
8. <span data-ttu-id="8a73e-131">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="8a73e-131">Click OK.</span></span>
9. <span data-ttu-id="8a73e-132">A Közzététel gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="8a73e-132">Click Publish to open the drop dialog.</span></span>
10. <span data-ttu-id="8a73e-133">Az Érvényesség dátuma mezőben adjon meg egy dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="8a73e-133">In the Effective date field, enter a date and time.</span></span>
11. <span data-ttu-id="8a73e-134">Kattintson a Közzététel parancsra.</span><span class="sxs-lookup"><span data-stu-id="8a73e-134">Click Publish.</span></span>

## <a name="configure-orders-for-near-real-time-notification"></a><span data-ttu-id="8a73e-135">Megrendelések konfigurálása a szinte valós idejű értesítésekhez</span><span class="sxs-lookup"><span data-stu-id="8a73e-135">Configure orders for near real-time notification</span></span>
1. <span data-ttu-id="8a73e-136">Menjen a Kiskereskedelem és kereskedelem > Központ beállítása > Paraméterek > Kiskereskedelmi paraméterek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8a73e-136">Go to Retail and Commerce  > Headquarters setup > Parameters > Commerce parameters.</span></span>
2. <span data-ttu-id="8a73e-137">A Valós idejű szolgáltatás használata az elektronikus kereskedelmi megrendelés létrehozásához beállítást állítsa „Igen” értékre.</span><span class="sxs-lookup"><span data-stu-id="8a73e-137">Set Use realtime service for eCommerce order creation to "Yes".</span></span>
3. <span data-ttu-id="8a73e-138">Futtassa a 1070 elosztási ütemezést a módosítások szinkronizálására a csatornaadatbázisba.</span><span class="sxs-lookup"><span data-stu-id="8a73e-138">Run the 1070 distribution schedule to sync changes to the channel database.</span></span> 


