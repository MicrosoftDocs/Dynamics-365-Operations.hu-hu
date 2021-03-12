---
title: Igény-előrejelzés manuális módosítása
description: Ez az eljárás bemutatja egy cikk előrejelzésének módosítását.
author: ShylaThompson
manager: tfehr
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cd931a378b057026eff57b34c9f5740df8adacef
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999831"
---
# <a name="modify-a-demand-forecast-manually"></a><span data-ttu-id="a66d7-103">Igény-előrejelzés manuális módosítása</span><span class="sxs-lookup"><span data-stu-id="a66d7-103">Modify a demand forecast manually</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a66d7-104">Ez az eljárás bemutatja egy cikk előrejelzésének módosítását.</span><span class="sxs-lookup"><span data-stu-id="a66d7-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="a66d7-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="a66d7-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="a66d7-106">Ezt a felvételt a termeléstervező használja.</span><span class="sxs-lookup"><span data-stu-id="a66d7-106">This recording is intended for the production planner.</span></span> 


## <a name="modify-the-forecast-for-an-item"></a><span data-ttu-id="a66d7-107">Cikk előrejelzésének módosítása</span><span class="sxs-lookup"><span data-stu-id="a66d7-107">Modify the forecast for an item</span></span>
1. <span data-ttu-id="a66d7-108">A **Navigációs ablaktáblán** lépjen a **Modulok > Termékinformációk kezelése > Termékek > Kiadott termékek** részre.</span><span class="sxs-lookup"><span data-stu-id="a66d7-108">In the **Navigation pane**, go to **Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="a66d7-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="a66d7-109">In the list, find and select the desired record.</span></span> <span data-ttu-id="a66d7-110">Válassza ki azt a cikket, amelynek módosítani szeretné az előrejelzését.</span><span class="sxs-lookup"><span data-stu-id="a66d7-110">Select the item for which you want to modify the forecast.</span></span> <span data-ttu-id="a66d7-111">Kiválaszthatja például a D0001 cikket.</span><span class="sxs-lookup"><span data-stu-id="a66d7-111">For example, you can select item D0001.</span></span>  
3. <span data-ttu-id="a66d7-112">A **Művelet panelen** kattintson a **Tervezés** elemre.</span><span class="sxs-lookup"><span data-stu-id="a66d7-112">On the **Action Pane**, click **Plan**.</span></span>
4. <span data-ttu-id="a66d7-113">Kattintson az **Igény-előrejelzés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a66d7-113">Click **Demand forecast**.</span></span>
5. <span data-ttu-id="a66d7-114">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="a66d7-114">In the list, mark the selected row.</span></span> <span data-ttu-id="a66d7-115">Ha nincsenek előrejelzési sorok, hozzon létre egy újat: kattintson az Új elemre az alkalmazássávon.</span><span class="sxs-lookup"><span data-stu-id="a66d7-115">If there are no forecast lines, create a new line by clicking New on the app bar.</span></span>  
6. <span data-ttu-id="a66d7-116">Adjon meg egy számot az **Értékesítési mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a66d7-116">In the **Sales quantity** field, enter a number.</span></span> <span data-ttu-id="a66d7-117">Ez a szám a cikk előre jelzett mennyiségét jelöli.</span><span class="sxs-lookup"><span data-stu-id="a66d7-117">This number represents the forecasted quantity for the item.</span></span>  
7. <span data-ttu-id="a66d7-118">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a66d7-118">Click Save.</span></span>

## <a name="modify-the-forecast-in-excel"></a><span data-ttu-id="a66d7-119">Előrejelzés módosítása az Excel programban</span><span class="sxs-lookup"><span data-stu-id="a66d7-119">Modify the forecast in Excel</span></span>
1. <span data-ttu-id="a66d7-120">Kattintson a **Megnyitás** elemre a Microsoft Office-ban.</span><span class="sxs-lookup"><span data-stu-id="a66d7-120">Click **Open** in Microsoft Office.</span></span>
2. <span data-ttu-id="a66d7-121">Kattintson az **Igény-előrejelzés szerkesztése** elemre az Excel programban.</span><span class="sxs-lookup"><span data-stu-id="a66d7-121">Click **Edit Demand forecast** in Excel.</span></span> <span data-ttu-id="a66d7-122">Az Excel programban hozzáadhatja, törölheti és szerkesztheti az igény-előrejelzés sorait.</span><span class="sxs-lookup"><span data-stu-id="a66d7-122">In Excel, you can add, delete and edit demand forecast lines.</span></span> <span data-ttu-id="a66d7-123">Ha nem lehet megtekinteni az adatokat Excelben, be kell jelentkeznie bekapcsolt „Szeretnék bejelentkezve maradni” lehetőséggel, és engedélyeznie kell az adatkommunikációs alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="a66d7-123">If you are not able to see the data in Excel, you need to sign in with the "Keep me signed in" option enabled and you need to trust the data connection app.</span></span>  

