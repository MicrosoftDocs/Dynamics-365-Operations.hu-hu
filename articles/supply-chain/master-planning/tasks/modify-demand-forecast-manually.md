---
title: 'Útmutató: Igény-előrejelzés manuális módosítása'
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
ms.openlocfilehash: 1e12ccf90b9971379e8931bd48d6243a855bb795
ms.sourcegitcommit: 15aacd0e109b05c7281407b5bba4e6cd99116c28
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/10/2021
ms.locfileid: "6224010"
---
# <a name="guide-modify-a-demand-forecast-manually"></a><span data-ttu-id="b4534-103">Útmutató: Igény-előrejelzés manuális módosítása</span><span class="sxs-lookup"><span data-stu-id="b4534-103">Guide: Modify a demand forecast manually</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b4534-104">Ez az eljárás bemutatja egy cikk előrejelzésének módosítását.</span><span class="sxs-lookup"><span data-stu-id="b4534-104">This procedure shows how to modify the forecast for an item.</span></span> <span data-ttu-id="b4534-105">Ezt az eljárást a termeléstervező használja.</span><span class="sxs-lookup"><span data-stu-id="b4534-105">This procedure is intended for the production planner.</span></span>

## <a name="modify-the-forecast-for-a-selected-item"></a><span data-ttu-id="b4534-106">Egy kiválasztott cikk előrejelzésének módosítása</span><span class="sxs-lookup"><span data-stu-id="b4534-106">Modify the forecast for a selected item</span></span>

<span data-ttu-id="b4534-107">Egy kiválasztott cikk előrejelzésének módosítása:</span><span class="sxs-lookup"><span data-stu-id="b4534-107">To modify the forecast for a selected item:</span></span>

1. <span data-ttu-id="b4534-108">Kattintson a **Modulok \>Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b4534-108">Go to **Modules \> Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="b4534-109">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="b4534-109">In the list, find and select the desired record.</span></span> <span data-ttu-id="b4534-110">Válassza ki azt a cikket, amelynek módosítani szeretné az előrejelzését.</span><span class="sxs-lookup"><span data-stu-id="b4534-110">Select the item for which you want to modify the forecast.</span></span>
1. <span data-ttu-id="b4534-111">A műveletpanelen nyissa meg a **Terv** lapot, és válassza az **Igény-előrejelzés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4534-111">On the Action Pane, open the **Plan** tab and select **Demand forecast**.</span></span>
1. <span data-ttu-id="b4534-112">Jelöljön ki egy sort a listában.</span><span class="sxs-lookup"><span data-stu-id="b4534-112">In the list, select a row.</span></span> <span data-ttu-id="b4534-113">Ha nincsenek előrejelzési sorok, hozzon létre egy újat: válassza az **Új** elemet a Művelet panelen.</span><span class="sxs-lookup"><span data-stu-id="b4534-113">If there are no forecast lines, create a new line by selecting **New** on the Action Pane.</span></span>  
1. <span data-ttu-id="b4534-114">Adjon meg egy pozitív számot az **Értékesítési mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="b4534-114">In the **Sales quantity** field, enter a positive number.</span></span> <span data-ttu-id="b4534-115">Ez a szám a cikk előre jelzett mennyiségét jelöli.</span><span class="sxs-lookup"><span data-stu-id="b4534-115">This number represents the forecasted quantity for the item.</span></span> <span data-ttu-id="b4534-116">Ha negatív számot ad meg, a rendszer hibát jelez.</span><span class="sxs-lookup"><span data-stu-id="b4534-116">An error will be shown if you enter a negative number.</span></span>
1. <span data-ttu-id="b4534-117">Töltse ki a egyéb mezőket, ha szükséges.</span><span class="sxs-lookup"><span data-stu-id="b4534-117">Fill out the other fields as needed.</span></span>
1. <span data-ttu-id="b4534-118">A Művelet ablaktáblán válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4534-118">Select **Save** on the Action Pane.</span></span>

## <a name="modify-the-forecast-for-one-or-more-items-with-microsoft-excel"></a><span data-ttu-id="b4534-119">Egy vagy több cikk előrejelzésének módosításához a Microsoft Excel segítségével</span><span class="sxs-lookup"><span data-stu-id="b4534-119">Modify the forecast for one or more items with Microsoft Excel</span></span>

<span data-ttu-id="b4534-120">Egy vagy több cikk előrejelzésének módosításához a Microsoft Excel segítségével:</span><span class="sxs-lookup"><span data-stu-id="b4534-120">To modify the forecast for one or more items with Microsoft Excel:</span></span>

1. <span data-ttu-id="b4534-121">Válasszon az alábbi lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="b4534-121">Do one of the following:</span></span>
    - <span data-ttu-id="b4534-122">Nyissa meg bármelyik cikk **igény-előrejelzés** lapját (nem számít, melyiket) az előző szakaszban leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="b4534-122">Open the **Demand forecast** page for any item (it doesn't matter which one) as described in the previous section.</span></span>
    - <span data-ttu-id="b4534-123">Ugorjon az **Alaptervezés \> Előrejelzés \> Manuális előrejelzési bejegyzés \> Igény-előrejelzési sorok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b4534-123">Go to **Master planning \> Forecasting \> Manual forecast entry \> Demand forecast lines**.</span></span>
1. <span data-ttu-id="b4534-124">A műveletpanelen nyissa meg a **Megnyitás Microsoft Office-ban \> Igény-előrejelzési bejegyzések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4534-124">On the Action Pane, select **Open in Microsoft Office \> Demand forecast entries**.</span></span>
1. <span data-ttu-id="b4534-125">Válassza ki a letöltés helyét, mentse, majd nyissa meg a letöltött fájlt az Excel programban.</span><span class="sxs-lookup"><span data-stu-id="b4534-125">Select a download location, save, and then open the downloaded file in Excel.</span></span>
1. <span data-ttu-id="b4534-126">Ha lát egy figyelmeztetést, válassza a **Szerkesztés engedélyezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b4534-126">If you see a warning, choose to **Enable editing**.</span></span>
1. <span data-ttu-id="b4534-127">Az Excel programban a Microsoft Dynamics munkaablak használatával jelentkezzen be a Supply Chain Management alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="b4534-127">In Excel, sign in to Supply Chain Management using the Microsoft Dynamics task pane.</span></span> <span data-ttu-id="b4534-128">Úgy kell bejelentkeznie, hogy engedélyezve van a **Bejelentkezve marad** beállítás, és meg kell bíznia az adatkapcsolati alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="b4534-128">You must sign in with the **Keep me signed in** option enabled and you must trust the data connection app.</span></span>
1. <span data-ttu-id="b4534-129">Az Excel-táblázat most a vállalat aktuális igény-előrejelzési sorait jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="b4534-129">The Excel spreadsheet now shows all the current demand forecast lines for your company.</span></span>  <span data-ttu-id="b4534-130">Szükség szerint hozzáadhatja, törölheti és szerkesztheti az igény-előrejelzés sorait.</span><span class="sxs-lookup"><span data-stu-id="b4534-130">Add, delete, and edit demand forecast lines as needed.</span></span>
1. <span data-ttu-id="b4534-131">Válassza a **Közzététel** lehetőséget a Microsoft Dynamics munkaablakban, ha vissza kell töltenie módosításait a Supply Chain Management eszközbe.</span><span class="sxs-lookup"><span data-stu-id="b4534-131">Select **Publish** on the Microsoft Dynamics task pane to upload your changes back to Supply Chain Management.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
