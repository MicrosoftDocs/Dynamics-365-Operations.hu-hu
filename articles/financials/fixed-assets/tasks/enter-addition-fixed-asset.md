--- 
title: "Tárgyi eszköz kiegészítésének bevitele"
description: "Ez az eljárás bemutatja, hogy hogyan adhat hozzá kiegészítést egy meglévő tárgyi eszközhöz."
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: bf87c968e940c730082eb1dba6745de2d1ca367a
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---
# <a name="enter-an-addition-to-a-fixed-asset"></a><span data-ttu-id="506ad-103">Tárgyi eszköz kiegészítésének bevitele</span><span class="sxs-lookup"><span data-stu-id="506ad-103">Enter an addition to a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="506ad-104">Ez az eljárás bemutatja, hogy hogyan adhat hozzá kiegészítést egy meglévő tárgyi eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="506ad-104">This procedure shows how to add an addition to an existing fixed asset.</span></span> <span data-ttu-id="506ad-105">A Tárgyieszköz-kiegészítések tájékoztató jellegűek, és az cikk-kiegészítések, a karbantartás vagy a fejlesztések nyomon követését szolgálják.</span><span class="sxs-lookup"><span data-stu-id="506ad-105">The purpose of Fixed asset additions is to track item additions, maintenance, or improvements for an asset, and is informational only.</span></span> <span data-ttu-id="506ad-106">A tárgyi eszköz értékét vagy élettartamát érintő módosításokat külön kell végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="506ad-106">Any changes to the fixed asset value or service life must be made separately.</span></span>   



<span data-ttu-id="506ad-107">Az eljárás a Könyvelői szerepkört, illetve bemutató adatokat használ a USMF jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="506ad-107">The procedure uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="506ad-108">Nyissa meg a következőt: Tárgyi eszközök > Tárgyi eszközök > Tárgyi eszközök.</span><span class="sxs-lookup"><span data-stu-id="506ad-108">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="506ad-109">A listában keresse meg és válassza ki, hogy a kiegészítés melyik tárgyi eszközhöz tartozik.</span><span class="sxs-lookup"><span data-stu-id="506ad-109">In the list, find and select the fixed asset for the addition.</span></span>
3. <span data-ttu-id="506ad-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="506ad-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="506ad-111">A Műveleti ablaktáblában kattintson a Tárgyi eszköz elemre.</span><span class="sxs-lookup"><span data-stu-id="506ad-111">On the Action Pane, click Fixed asset.</span></span>
5. <span data-ttu-id="506ad-112">Kattintson a Tárgyieszköz-kiegészítésekre.</span><span class="sxs-lookup"><span data-stu-id="506ad-112">Click Fixed asset additions.</span></span>
6. <span data-ttu-id="506ad-113">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="506ad-113">Click New.</span></span>
7. <span data-ttu-id="506ad-114">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="506ad-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="506ad-115">Állítsa be a kiegészítés-beszerzés vagy a szolgáltatás dátumát.</span><span class="sxs-lookup"><span data-stu-id="506ad-115">Set the date of the addition purchase or service.</span></span>
9. <span data-ttu-id="506ad-116">A cikk, karbantartás vagy az eszközt érintő más fejlesztés költségének megadása.</span><span class="sxs-lookup"><span data-stu-id="506ad-116">Enter the cost of the item, maintenance, or other improvement for the asset.</span></span>
10. <span data-ttu-id="506ad-117">Adjon meg egy számot a Mennyiség mezőben.</span><span class="sxs-lookup"><span data-stu-id="506ad-117">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="506ad-118">A teljes költség kizárólag tájékoztató jellegű, illetve a nyomon követést szolgálja, és nincs kihatással a tárgyi eszköz értékére.</span><span class="sxs-lookup"><span data-stu-id="506ad-118">The total cost will have no impact on the value of the fixed asset and is for tracking and informational purposes only.</span></span> <span data-ttu-id="506ad-119">Amennyiben a költség tőkésítésre kerül, úgy külön fel kell adni egy felértékelési tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="506ad-119">If the cost will be capitalized, then a write-up adjustment transaction must be posted separately.</span></span>  
11. <span data-ttu-id="506ad-120">Kattintson az Általános fülre.</span><span class="sxs-lookup"><span data-stu-id="506ad-120">Click the General tab.</span></span>
    * <span data-ttu-id="506ad-121">Állítsa be a Megnöveli az élettartamot lehetőséget, ha a kiegészítés megnöveli a tárgyi eszköz élettartamát.</span><span class="sxs-lookup"><span data-stu-id="506ad-121">Set Increases service life if the addition increases the service life of the asset.</span></span>  
    * <span data-ttu-id="506ad-122">Ez a mező csak tájékoztatásra szolgál.</span><span class="sxs-lookup"><span data-stu-id="506ad-122">This field is informational only.</span></span> <span data-ttu-id="506ad-123">Az élettartam növelése, illetve az Élettartam az Értékmodellen és/vagy az eszköz Értékcsökkenés könyvében történő módosítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="506ad-123">To increase the service life, modify the Service life on the Value models and/or Depreciation books for the asset.</span></span>  


