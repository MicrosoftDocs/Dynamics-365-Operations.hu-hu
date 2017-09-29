--- 
title: "Igény-előrejelzés manuális módosítása"
description: "Ez az eljárás bemutatja egy cikk előrejelzésének módosítását."
author: YuyuScheller
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 2e269ef7b33b4d7e171d284d68d28c825c2fe86c
ms.contentlocale: hu-hu
ms.lasthandoff: 08/29/2017

---
# <a name="modify-a-demand-forecast-manually"></a><span data-ttu-id="a2641-103">Igény-előrejelzés manuális módosítása</span><span class="sxs-lookup"><span data-stu-id="a2641-103">Modify a demand forecast manually</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a2641-104">Ez az eljárás bemutatja egy cikk előrejelzésének módosítását.</span><span class="sxs-lookup"><span data-stu-id="a2641-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="a2641-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="a2641-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="a2641-106">Ezt a felvételt a termeléstervező használja.</span><span class="sxs-lookup"><span data-stu-id="a2641-106">This recording is intended for the production planner.</span></span> 


## <a name="modify-the-forecast-for-an-item"></a><span data-ttu-id="a2641-107">Cikk előrejelzésének módosítása</span><span class="sxs-lookup"><span data-stu-id="a2641-107">Modify the forecast for an item</span></span>
1. <span data-ttu-id="a2641-108">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a2641-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="a2641-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="a2641-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a2641-110">Válassza ki azt a cikket, amelynek módosítani szeretné az előrejelzését.</span><span class="sxs-lookup"><span data-stu-id="a2641-110">Select the item for which you want to modify the forecast.</span></span> <span data-ttu-id="a2641-111">Kiválaszthatja például a D0001 cikket.</span><span class="sxs-lookup"><span data-stu-id="a2641-111">For example, you can select item D0001.</span></span>  
3. <span data-ttu-id="a2641-112">A Művelet panelen kattintson a Terv elemre.</span><span class="sxs-lookup"><span data-stu-id="a2641-112">On the Action Pane, click Plan.</span></span>
4. <span data-ttu-id="a2641-113">Kattintson az Igény-előrejelzés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a2641-113">Click Demand forecast.</span></span>
5. <span data-ttu-id="a2641-114">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="a2641-114">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="a2641-115">Ha nincsenek előrejelzési sorok, hozzon létre egy újat úgy,</span><span class="sxs-lookup"><span data-stu-id="a2641-115">If there are no forecast lines, create a new line by  .</span></span> <span data-ttu-id="a2641-116">hogy az Új lehetőségre kattint az alkalmazássávon.</span><span class="sxs-lookup"><span data-stu-id="a2641-116">clicking New on the app bar.</span></span>  
6. <span data-ttu-id="a2641-117">Adjon meg egy számot az Értékesítési mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="a2641-117">In the Sales quantity field, enter a number.</span></span>
    * <span data-ttu-id="a2641-118">Ez a szám a cikk előre jelzett mennyiségét jelöli.</span><span class="sxs-lookup"><span data-stu-id="a2641-118">This number represents the forecasted quantity for the item.</span></span>  
7. <span data-ttu-id="a2641-119">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a2641-119">Click Save.</span></span>

## <a name="modify-the-forecast-in-excel"></a><span data-ttu-id="a2641-120">Előrejelzés módosítása az Excel programban</span><span class="sxs-lookup"><span data-stu-id="a2641-120">Modify the forecast in Excel</span></span>
1. <span data-ttu-id="a2641-121">Kattintson a Megnyitás lehetőségre a Microsoft Office programban.</span><span class="sxs-lookup"><span data-stu-id="a2641-121">Click Open in Microsoft Office.</span></span>
2. <span data-ttu-id="a2641-122">Kattintson az Igény-előrejelzés szerkesztése lehetőségre az Excel programban.</span><span class="sxs-lookup"><span data-stu-id="a2641-122">Click Edit Demand forecast in Excel.</span></span>
    * <span data-ttu-id="a2641-123">Az Excel programban hozzáadhatja, törölheti és szerkesztheti az igény-előrejelzés sorait.</span><span class="sxs-lookup"><span data-stu-id="a2641-123">In Excel, you can add, delete and edit demand forecast lines.</span></span> <span data-ttu-id="a2641-124">Ha nem lehet megtekinteni az adatokat Excelben, be kell jelentkeznie a Microsoft Dynamics 365 for Finance and Operations Enterprise kiadás szolgáltatásba bekapcsolt „Szeretnék bejelentkezve maradni” lehetőséggel, és engedélyeznie kell az adatkommunikációs alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="a2641-124">If you are not able to see the data in Excel, you need to sign in to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition with the "Keep me signed in" option enabled and you need to trust the data connection app.</span></span>  


