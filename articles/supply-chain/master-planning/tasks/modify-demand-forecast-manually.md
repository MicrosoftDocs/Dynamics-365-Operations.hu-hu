---
title: Igény-előrejelzés manuális módosítása
description: Ez az eljárás bemutatja egy cikk előrejelzésének módosítását.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 063554c98b8a6261ebe69073f214a8e45850c623
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560736"
---
# <a name="modify-a-demand-forecast-manually"></a><span data-ttu-id="06451-103">Igény-előrejelzés manuális módosítása</span><span class="sxs-lookup"><span data-stu-id="06451-103">Modify a demand forecast manually</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="06451-104">Ez az eljárás bemutatja egy cikk előrejelzésének módosítását.</span><span class="sxs-lookup"><span data-stu-id="06451-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="06451-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="06451-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="06451-106">Ezt a felvételt a termeléstervező használja.</span><span class="sxs-lookup"><span data-stu-id="06451-106">This recording is intended for the production planner.</span></span> 


## <a name="modify-the-forecast-for-an-item"></a><span data-ttu-id="06451-107">Cikk előrejelzésének módosítása</span><span class="sxs-lookup"><span data-stu-id="06451-107">Modify the forecast for an item</span></span>
1. <span data-ttu-id="06451-108">Kattintson a Termékinformációk kezelése > Termékek > Kiadott termékek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="06451-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="06451-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="06451-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="06451-110">Válassza ki azt a cikket, amelynek módosítani szeretné az előrejelzését.</span><span class="sxs-lookup"><span data-stu-id="06451-110">Select the item for which you want to modify the forecast.</span></span> <span data-ttu-id="06451-111">Kiválaszthatja például a D0001 cikket.</span><span class="sxs-lookup"><span data-stu-id="06451-111">For example, you can select item D0001.</span></span>  
3. <span data-ttu-id="06451-112">A Művelet panelen kattintson a Terv elemre.</span><span class="sxs-lookup"><span data-stu-id="06451-112">On the Action Pane, click Plan.</span></span>
4. <span data-ttu-id="06451-113">Kattintson az Igény-előrejelzés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="06451-113">Click Demand forecast.</span></span>
5. <span data-ttu-id="06451-114">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="06451-114">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="06451-115">Ha nincsenek előrejelzési sorok, hozzon létre egy újat úgy,</span><span class="sxs-lookup"><span data-stu-id="06451-115">If there are no forecast lines, create a new line by  .</span></span> <span data-ttu-id="06451-116">hogy az Új lehetőségre kattint az alkalmazássávon.</span><span class="sxs-lookup"><span data-stu-id="06451-116">clicking New on the app bar.</span></span>  
6. <span data-ttu-id="06451-117">Adjon meg egy számot az Értékesítési mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="06451-117">In the Sales quantity field, enter a number.</span></span>
    * <span data-ttu-id="06451-118">Ez a szám a cikk előre jelzett mennyiségét jelöli.</span><span class="sxs-lookup"><span data-stu-id="06451-118">This number represents the forecasted quantity for the item.</span></span>  
7. <span data-ttu-id="06451-119">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="06451-119">Click Save.</span></span>

## <a name="modify-the-forecast-in-excel"></a><span data-ttu-id="06451-120">Előrejelzés módosítása az Excel programban</span><span class="sxs-lookup"><span data-stu-id="06451-120">Modify the forecast in Excel</span></span>
1. <span data-ttu-id="06451-121">Kattintson a Megnyitás a Microsoft Office-ban gombra.</span><span class="sxs-lookup"><span data-stu-id="06451-121">Click Open in Microsoft Office.</span></span>
2. <span data-ttu-id="06451-122">Kattintson az Igény-előrejelzés szerkesztése lehetőségre az Excel programban.</span><span class="sxs-lookup"><span data-stu-id="06451-122">Click Edit Demand forecast in Excel.</span></span>
    * <span data-ttu-id="06451-123">Az Excel programban hozzáadhatja, törölheti és szerkesztheti az igény-előrejelzés sorait.</span><span class="sxs-lookup"><span data-stu-id="06451-123">In Excel, you can add, delete and edit demand forecast lines.</span></span> <span data-ttu-id="06451-124">Ha nem lehet megtekinteni az adatokat Excelben, be kell jelentkeznie a Microsoft Dynamics 365 for Finance and Operations, Enterprise kiadás szolgáltatásba bekapcsolt „Szeretnék bejelentkezve maradni” lehetőséggel, és engedélyeznie kell az adatkommunikációs alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="06451-124">If you are not able to see the data in Excel, you need to sign in to Microsoft Dynamics 365 for Finance and Operations, Enterprise edition with the "Keep me signed in" option enabled and you need to trust the data connection app.</span></span>  

