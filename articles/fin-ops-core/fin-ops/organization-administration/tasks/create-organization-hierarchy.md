---
title: Szervezeti hierarchia létrehozása.
description: A következő eljárás segítségével hozzon létre szervezeti hierarchiát.
author: sericks007
ms.date: 12/15/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OMHierarchyManager, OMHierarchyPurposeAssociation, OMHierarchySelection, HierarchyDesigner
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4d27bec86302f3e6cef8318a0d846f31d2d9c6a5
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747393"
---
# <a name="create-an-organization-hierarchy"></a><span data-ttu-id="175e2-103">Szervezeti hierarchia létrehozása.</span><span class="sxs-lookup"><span data-stu-id="175e2-103">Create an organization hierarchy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="175e2-104">A következő eljárás segítségével hozzon létre szervezeti hierarchiát.</span><span class="sxs-lookup"><span data-stu-id="175e2-104">Use the following procedure to create an organizational hierarchy.</span></span> <span data-ttu-id="175e2-105">A szervezeti hierarchia segítségével több nézőpontból is megtekintheti vállalatát, és jelentést is készíthet róla.</span><span class="sxs-lookup"><span data-stu-id="175e2-105">You can use organizational hierarchies to view and report on your business from various perspectives.</span></span> <span data-ttu-id="175e2-106">Például beállíthat egy hierarchiát adózási, jogi, illetve kötelezően előírt jelentésekhez.</span><span class="sxs-lookup"><span data-stu-id="175e2-106">For example, you can set up one hierarchy for tax, legal, or statutory reporting.</span></span> <span data-ttu-id="175e2-107">Utána beállíthat egy másik hierarchiát olyan pénzügyi információkat tartalmazó jelentéshez, mely jogilag nem kötelező, de a belső jelentésekhez használható.</span><span class="sxs-lookup"><span data-stu-id="175e2-107">You can then set up another hierarchy to report financial information that is not legally required, but that is used for internal reporting.</span></span> 

<span data-ttu-id="175e2-108">A szervezeti hierarchia létrehozása előtt létre kell hoznia a szervezeteket.</span><span class="sxs-lookup"><span data-stu-id="175e2-108">Before you create an organizational hierarchy, you must create organizations.</span></span> <span data-ttu-id="175e2-109">További tudnivalókért lásd a „Jogi személy létrehozása” vagy „Üzemi egység létrehozása” feladatokat.</span><span class="sxs-lookup"><span data-stu-id="175e2-109">For more information, see the "Create a legal entity" or "Create an operating unit" tasks.</span></span> <span data-ttu-id="175e2-110">Részlegeket és csoportokat is létrehozhat.</span><span class="sxs-lookup"><span data-stu-id="175e2-110">You can also create departments and teams.</span></span> 

<span data-ttu-id="175e2-111">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="175e2-111">The demo data company used to create this procedure is USMF.</span></span>

## <a name="create-a-hierarchy"></a><span data-ttu-id="175e2-112">Hierarchia létrehozása</span><span class="sxs-lookup"><span data-stu-id="175e2-112">Create a hierarchy</span></span>
1. <span data-ttu-id="175e2-113">Nyissa meg a következőt: **Navigációs lap > Modulok > Szervezeti adminisztráció > Szervezetek > Szervezeti hierarchiák**.</span><span class="sxs-lookup"><span data-stu-id="175e2-113">Go to **Navigation pane > Modules > Organization administration > Organizations > Organization hierarchies**.</span></span>
2. <span data-ttu-id="175e2-114">A **Műveleti panelen** kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="175e2-114">On the **Action pane**, click **New**.</span></span>
3. <span data-ttu-id="175e2-115">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="175e2-115">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="175e2-116">A **Cél** területen kattintson a **Cél hozzárendelése** elemre.</span><span class="sxs-lookup"><span data-stu-id="175e2-116">In the **Purpose** section, click **Assign purpose**.</span></span>
5. <span data-ttu-id="175e2-117">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="175e2-117">In the list, find and select the desired record.</span></span> <span data-ttu-id="175e2-118">Cél kiválasztása a szervezeti hierarchia hozzárendeléséhez.</span><span class="sxs-lookup"><span data-stu-id="175e2-118">Select a purpose to assign to your organization hierarchy.</span></span>  
6. <span data-ttu-id="175e2-119">A **Hozzárendelt hierarchiák** szakaszban kattintson a **Hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="175e2-119">In the **Assigned hierarchies** section, click **Add**.</span></span>
7. <span data-ttu-id="175e2-120">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="175e2-120">In the list, mark the selected row.</span></span> <span data-ttu-id="175e2-121">A most létrehozott hierarchia keresése.</span><span class="sxs-lookup"><span data-stu-id="175e2-121">Find the hierarchy you just created.</span></span>  
8. <span data-ttu-id="175e2-122">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="175e2-122">Click **OK**.</span></span>

## <a name="add-organizations-to-the-hierarchy"></a><span data-ttu-id="175e2-123">Szervezetek felvétele a hierarchiába</span><span class="sxs-lookup"><span data-stu-id="175e2-123">Add organizations to the hierarchy</span></span>
1. <span data-ttu-id="175e2-124">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="175e2-124">In the list, find and select the desired record.</span></span> <span data-ttu-id="175e2-125">A hierarchia kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="175e2-125">Select your hierarchy.</span></span>  
2. <span data-ttu-id="175e2-126">A **Hozzárendelt hierarchiák** szakaszban kattintson a **Hierarchia megtekintése** elemre.</span><span class="sxs-lookup"><span data-stu-id="175e2-126">In the **Assigned hierarchies** section, click **View hierarchy**.</span></span>
    - <span data-ttu-id="175e2-127">Szükség szerint adjon hozzá szervezeteket.</span><span class="sxs-lookup"><span data-stu-id="175e2-127">Add organizations, as necessary.</span></span>  
    - <span data-ttu-id="175e2-128">A szervezetek hozzáadásához kattintson a **Szerkesztés** majd a **Beszúrás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="175e2-128">To add an organization, click **Edit** and then **Insert** to add the organization.</span></span> <span data-ttu-id="175e2-129">Amikor befejezte a módosításokat **elmentheti** a vázlatot és/vagy **közzéteheti** a módosításokat.</span><span class="sxs-lookup"><span data-stu-id="175e2-129">When you are done making changes you can **Save** a draft and/or **Publish** the changes.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]