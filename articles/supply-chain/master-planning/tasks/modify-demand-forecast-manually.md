---
title: Igény-előrejelzés manuális módosítása
description: Ez az cikk bemutatja egy cikk előrejelzésének módosítását
author: ChristianRytt
ms.date: 08/12/2019
ms.topic: business-process
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5da1d5b1fbd91964e695a704681b1c9ee513a2f1
ms.sourcegitcommit: 4016c223a985c46e33f9941bf91ba5e1583e1cfd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889024"
---
# <a name="modify-a-demand-forecast-manually"></a><span data-ttu-id="a70c9-103">Igény-előrejelzés manuális módosítása</span><span class="sxs-lookup"><span data-stu-id="a70c9-103">Modify a demand forecast manually</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a70c9-104">Ez az eljárás bemutatja egy cikk előrejelzésének módosítását.</span><span class="sxs-lookup"><span data-stu-id="a70c9-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="a70c9-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="a70c9-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="a70c9-106">Ezt az eljárást a termeléstervező használja.</span><span class="sxs-lookup"><span data-stu-id="a70c9-106">This procedure is intended for the production planner.</span></span>

## <a name="modify-the-forecast-for-a-selected-item"></a><span data-ttu-id="a70c9-107">Egy kiválasztott cikk előrejelzésének módosítása</span><span class="sxs-lookup"><span data-stu-id="a70c9-107">Modify the forecast for a selected item</span></span>

<span data-ttu-id="a70c9-108">Egy kiválasztott cikk előrejelzésének módosítása:</span><span class="sxs-lookup"><span data-stu-id="a70c9-108">To modify the forecast for a selected item:</span></span>

1. <span data-ttu-id="a70c9-109">Kattintson a **Modulok \>Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a70c9-109">Go to **Modules \> Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="a70c9-110">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="a70c9-110">In the list, find and select the desired record.</span></span> <span data-ttu-id="a70c9-111">Válassza ki azt a cikket, amelynek módosítani szeretné az előrejelzését.</span><span class="sxs-lookup"><span data-stu-id="a70c9-111">Select the item for which you want to modify the forecast.</span></span>
1. <span data-ttu-id="a70c9-112">A műveletpanelen nyissa meg a **Terv** lapot, és válassza az **Igény-előrejelzés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a70c9-112">On the Action Pane, open the **Plan** tab and select **Demand forecast**.</span></span>
1. <span data-ttu-id="a70c9-113">Jelöljön ki egy sort a listában.</span><span class="sxs-lookup"><span data-stu-id="a70c9-113">In the list, select a row.</span></span> <span data-ttu-id="a70c9-114">Ha nincsenek előrejelzési sorok, hozzon létre egy újat: válassza az **Új** elemet a Művelet panelen.</span><span class="sxs-lookup"><span data-stu-id="a70c9-114">If there are no forecast lines, create a new line by selecting **New** on the Action Pane.</span></span>  
1. <span data-ttu-id="a70c9-115">Adjon meg egy pozitív számot az **Értékesítési mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a70c9-115">In the **Sales quantity** field, enter a positive number.</span></span> <span data-ttu-id="a70c9-116">Ez a szám a cikk előre jelzett mennyiségét jelöli.</span><span class="sxs-lookup"><span data-stu-id="a70c9-116">This number represents the forecasted quantity for the item.</span></span> <span data-ttu-id="a70c9-117">Ha negatív számot ad meg, a rendszer hibát jelez.</span><span class="sxs-lookup"><span data-stu-id="a70c9-117">An error will be shown if you enter a negative number.</span></span>
1. <span data-ttu-id="a70c9-118">Töltse ki a egyéb mezőket, ha szükséges.</span><span class="sxs-lookup"><span data-stu-id="a70c9-118">Fill out the other fields as needed.</span></span>
1. <span data-ttu-id="a70c9-119">A Művelet ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a70c9-119">Select **Save** on the Action Pane.</span></span>

## <a name="modify-the-forecast-for-one-or-more-items-microsoft-excel"></a><span data-ttu-id="a70c9-120">Egy vagy több cikk előrejelzésének módosítása Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="a70c9-120">Modify the forecast for one or more items Microsoft Excel</span></span>

<span data-ttu-id="a70c9-121">Egy vagy több cikk előrejelzésének módosításához Microsoft Excel:</span><span class="sxs-lookup"><span data-stu-id="a70c9-121">To modify the forecast for one or more items Microsoft Excel:</span></span>

1. <span data-ttu-id="a70c9-122">Válasszon az alábbi lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="a70c9-122">Do one of the following:</span></span>
    - <span data-ttu-id="a70c9-123">Nyissa meg bármelyik cikk **igény-előrejelzés** lapját (nem számít, melyiket) az előző szakaszban leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="a70c9-123">Open the **Demand forecast** page for any item (it doesn't matter which one) as described in the previous section.</span></span>
    - <span data-ttu-id="a70c9-124">Ugorjon az **Alaptervezés \> Előrejelzés \> Manuális előrejelzési bejegyzés \> Igény-előrejelzési sorok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a70c9-124">Go to **Master planning \> Forecasting \> Manual forecast entry \> Demand forecast lines**.</span></span>
1. <span data-ttu-id="a70c9-125">A műveletpanelen nyissa meg a **Megnyitás Microsoft Office-ban \> Igény-előrejelzési bejegyzések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a70c9-125">On the Action Pane, select **Open in Microsoft Office \> Demand forecast entries**.</span></span>
1. <span data-ttu-id="a70c9-126">Válassza ki a letöltés helyét, mentse, majd nyissa meg a letöltött fájlt az Excel programban.</span><span class="sxs-lookup"><span data-stu-id="a70c9-126">Select a download location, save, and then open the downloaded file in Excel.</span></span>
1. <span data-ttu-id="a70c9-127">Ha lát egy figyelmeztetést, válassza a **Szerkesztés engedélyezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a70c9-127">If you see a warning, choose to **Enable editing**.</span></span>
1. <span data-ttu-id="a70c9-128">Az Excel programban a Microsoft Dynamics munkaablak használatával jelentkezzen be a Supply Chain Management alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="a70c9-128">In Excel, sign in to Supply Chain Management using the Microsoft Dynamics task pane.</span></span> <span data-ttu-id="a70c9-129">Úgy kell bejelentkeznie, hogy engedélyezve van a **Bejelentkezve marad** beállítás, és meg kell bíznia az adatkapcsolati alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="a70c9-129">You must sign in with the **Keep me signed in** option enabled and you must trust the data connection app.</span></span>
1. <span data-ttu-id="a70c9-130">Az Excel-táblázat most a vállalat aktuális igény-előrejelzési sorait jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="a70c9-130">The Excel spreadsheet now shows all the current demand forecast lines for your company.</span></span>  <span data-ttu-id="a70c9-131">Szükség szerint hozzáadhatja, törölheti és szerkesztheti az igény-előrejelzés sorait.</span><span class="sxs-lookup"><span data-stu-id="a70c9-131">Add, delete, and edit demand forecast lines as needed.</span></span>
1. <span data-ttu-id="a70c9-132">Válassza a **Közzététel** lehetőséget a Microsoft Dynamics munkaablakban, ha vissza kell töltenie módosításait a Supply Chain Management eszközbe.</span><span class="sxs-lookup"><span data-stu-id="a70c9-132">Select **Publish** on the Microsoft Dynamics task pane to upload your changes back to Supply Chain Management.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
