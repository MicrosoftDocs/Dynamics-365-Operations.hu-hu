--- 
title: "Szervezeti hierarchia létrehozása."
description: "A következő eljárás segítségével hozzon létre szervezeti hierarchiát."
author: sericks007
manager: AnnBe
ms.date: 06/09/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 2aea56a549131745b2636392561176bf0f87097c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="create-an-organization-hierarchy"></a><span data-ttu-id="20cac-103">Szervezeti hierarchia létrehozása.</span><span class="sxs-lookup"><span data-stu-id="20cac-103">Create an organization hierarchy</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="20cac-104">A következő eljárás segítségével hozzon létre szervezeti hierarchiát.</span><span class="sxs-lookup"><span data-stu-id="20cac-104">Use the following procedure to create an organizational hierarchy.</span></span> <span data-ttu-id="20cac-105">A szervezeti hierarchia segítségével több nézőpontból is megtekintheti vállalatát, és jelentést is készíthet róla.</span><span class="sxs-lookup"><span data-stu-id="20cac-105">You can use organizational hierarchies to view and report on your business from various perspectives.</span></span> <span data-ttu-id="20cac-106">Például beállíthat egy hierarchiát adózási, jogi, illetve kötelezően előírt jelentésekhez.</span><span class="sxs-lookup"><span data-stu-id="20cac-106">For example, you can set up one hierarchy for tax, legal, or statutory reporting.</span></span> <span data-ttu-id="20cac-107">Utána beállíthat egy másik hierarchiát olyan pénzügyi információkat tartalmazó jelentéshez, mely jogilag nem kötelező, de a belső jelentésekhez használható.</span><span class="sxs-lookup"><span data-stu-id="20cac-107">You can then set up another hierarchy to report financial information that is not legally required, but that is used for internal reporting.</span></span> 



<span data-ttu-id="20cac-108">A szervezeti hierarchia létrehozása előtt létre kell hoznia a szervezeteket.</span><span class="sxs-lookup"><span data-stu-id="20cac-108">Before you create an organizational hierarchy, you must create organizations.</span></span> <span data-ttu-id="20cac-109">További tudnivalókért lásd a „Jogi személy létrehozása” vagy „Üzemi egység létrehozása” feladatokat.</span><span class="sxs-lookup"><span data-stu-id="20cac-109">For more information, see the “Create a legal entity” or “Create an operating unit” tasks.</span></span> <span data-ttu-id="20cac-110">Részlegeket és csoportokat is létrehozhat.</span><span class="sxs-lookup"><span data-stu-id="20cac-110">You can also create departments and teams.</span></span> 



<span data-ttu-id="20cac-111">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="20cac-111">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-hierarchy"></a><span data-ttu-id="20cac-112">Hierarchia létrehozása</span><span class="sxs-lookup"><span data-stu-id="20cac-112">Create a hierarchy</span></span>
1. <span data-ttu-id="20cac-113">Ugrás a Szervezet felügyelete > Szervezetek > Szervezeti hierarchiák menüpontokra.</span><span class="sxs-lookup"><span data-stu-id="20cac-113">Go to Organization administration > Organizations > Organization hierarchies.</span></span>
2. <span data-ttu-id="20cac-114">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="20cac-114">Click New.</span></span>
3. <span data-ttu-id="20cac-115">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="20cac-115">In the Name field, type a value.</span></span>
4. <span data-ttu-id="20cac-116">Kattintás a Cél hozzárendelése menüpontra.</span><span class="sxs-lookup"><span data-stu-id="20cac-116">Click Assign purpose.</span></span>
5. <span data-ttu-id="20cac-117">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="20cac-117">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="20cac-118">Cél kiválasztása a szervezeti hierarchia hozzárendeléséhez.</span><span class="sxs-lookup"><span data-stu-id="20cac-118">Select a purpose to assign to your organization hierarchy.</span></span>  
6. <span data-ttu-id="20cac-119">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="20cac-119">Click Add.</span></span>
7. <span data-ttu-id="20cac-120">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="20cac-120">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="20cac-121">A most létrehozott hierarchia keresése.</span><span class="sxs-lookup"><span data-stu-id="20cac-121">Find the hierarchy you just created.</span></span>  
8. <span data-ttu-id="20cac-122">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="20cac-122">Click OK.</span></span>

## <a name="add-organizations-to-the-hierarchy"></a><span data-ttu-id="20cac-123">Szervezetek felvétele a hierarchiába</span><span class="sxs-lookup"><span data-stu-id="20cac-123">Add organizations to the hierarchy</span></span>
1. <span data-ttu-id="20cac-124">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="20cac-124">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="20cac-125">A hierarchia kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="20cac-125">Select your hierarchy.</span></span>  
2. <span data-ttu-id="20cac-126">Kattintson a Hierarchia megtekintése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="20cac-126">Click View hierarchy.</span></span>
    * <span data-ttu-id="20cac-127">Szükség szerint adjon hozzá szervezeteket.</span><span class="sxs-lookup"><span data-stu-id="20cac-127">Add organizations, as necessary.</span></span>  
    * <span data-ttu-id="20cac-128">A szervezetek hozzáadásához kattintson a Szerkesztés majd a Beszúrás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="20cac-128">To add an organization, click Edit and then Insert to add the organization.</span></span>     <span data-ttu-id="20cac-129">Amikor befejezte a módosításokat elmentheti a vázlatot és/vagy közzé teheti a módosításokat.</span><span class="sxs-lookup"><span data-stu-id="20cac-129">When you are done making changes you can save a draft and/or publish the changes.</span></span>  


