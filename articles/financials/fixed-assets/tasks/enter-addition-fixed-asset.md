---
title: Tárgyi eszköz kiegészítésének bevitele
description: Ez az eljárás bemutatja, hogy hogyan adhat hozzá kiegészítést egy meglévő tárgyi eszközhöz.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetAddition
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fe1a1d4db696ac013afee05b697b301383232134
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839953"
---
# <a name="enter-an-addition-to-a-fixed-asset"></a><span data-ttu-id="d29d8-103">Tárgyi eszköz kiegészítésének bevitele</span><span class="sxs-lookup"><span data-stu-id="d29d8-103">Enter an addition to a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d29d8-104">Ez az eljárás bemutatja, hogy hogyan adhat hozzá kiegészítést egy meglévő tárgyi eszközhöz.</span><span class="sxs-lookup"><span data-stu-id="d29d8-104">This procedure shows how to add an addition to an existing fixed asset.</span></span> <span data-ttu-id="d29d8-105">A Tárgyieszköz-kiegészítések tájékoztató jellegűek, és az cikk-kiegészítések, a karbantartás vagy a fejlesztések nyomon követését szolgálják.</span><span class="sxs-lookup"><span data-stu-id="d29d8-105">The purpose of Fixed asset additions is to track item additions, maintenance, or improvements for an asset, and is informational only.</span></span> <span data-ttu-id="d29d8-106">A tárgyi eszköz értékét vagy élettartamát érintő módosításokat külön kell végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="d29d8-106">Any changes to the fixed asset value or service life must be made separately.</span></span>   

<span data-ttu-id="d29d8-107">Az eljárás a Könyvelői szerepkört, illetve bemutató adatokat használ a USMF jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="d29d8-107">The procedure uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="d29d8-108">A Navigációs ablaktáblán ugorjon a **Modulok > Tárgyi eszközök > Tárgyi eszközök > Tárgyi eszközök** elemre.</span><span class="sxs-lookup"><span data-stu-id="d29d8-108">In the Navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="d29d8-109">A listában keresse meg és válassza ki, hogy a kiegészítés melyik tárgyi eszközhöz tartozik.</span><span class="sxs-lookup"><span data-stu-id="d29d8-109">In the list, find and select the fixed asset for the addition.</span></span>
3. <span data-ttu-id="d29d8-110">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="d29d8-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="d29d8-111">A Műveleti ablaktáblán kattintson a **Tárgyi eszköz** elemre.</span><span class="sxs-lookup"><span data-stu-id="d29d8-111">On the Action Pane, click **Fixed asset**.</span></span>
5. <span data-ttu-id="d29d8-112">Kattintson a **Tárgyieszköz-tartozékok** elemre.</span><span class="sxs-lookup"><span data-stu-id="d29d8-112">Click **Fixed asset additions**.</span></span>
6. <span data-ttu-id="d29d8-113">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="d29d8-113">Click **New**.</span></span>
7. <span data-ttu-id="d29d8-114">Írjon be egy értéket a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d29d8-114">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="d29d8-115">A **Beszerzési dátum** mezőben adja meg a további vásárlás vagy szolgáltatás dátumát.</span><span class="sxs-lookup"><span data-stu-id="d29d8-115">In the **Acquisition date** field, set the date of the addition purchase or service.</span></span>
9. <span data-ttu-id="d29d8-116">Az **Egységköltség** mezőbe írja be a cikknek, a karbantartásnak vagy az eszköz továbbfejlesztésének a költségét.</span><span class="sxs-lookup"><span data-stu-id="d29d8-116">In the **Unit cost** field, enter the cost of the item, maintenance, or other improvement for the asset.</span></span>
10. <span data-ttu-id="d29d8-117">Adjon meg egy számot a **Mennyiség** mezőben.</span><span class="sxs-lookup"><span data-stu-id="d29d8-117">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="d29d8-118">A teljes költség kizárólag tájékoztató jellegű, illetve a nyomon követést szolgálja, és nincs kihatással a tárgyi eszköz értékére.</span><span class="sxs-lookup"><span data-stu-id="d29d8-118">The total cost will have no impact on the value of the fixed asset and is for tracking and informational purposes only.</span></span> <span data-ttu-id="d29d8-119">Amennyiben a költség tőkésítésre kerül, úgy külön fel kell adni egy felértékelési tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="d29d8-119">If the cost will be capitalized, then a write-up adjustment transaction must be posted separately.</span></span>  
11. <span data-ttu-id="d29d8-120">Kattintson az **Általános** fülre.</span><span class="sxs-lookup"><span data-stu-id="d29d8-120">Click the **General** tab.</span></span>

    * <span data-ttu-id="d29d8-121">A **Megnöveli az élettartamot** beállításnál adja meg az **Igen** értéket, ha a kiegészítés megnöveli az eszköz élettartamát.</span><span class="sxs-lookup"><span data-stu-id="d29d8-121">Set **Increases service life** to **Yes** if the addition increases the service life of the asset.</span></span>  
    * <span data-ttu-id="d29d8-122">Ez a mező csak tájékoztatásra szolgál.</span><span class="sxs-lookup"><span data-stu-id="d29d8-122">This field is informational only.</span></span> <span data-ttu-id="d29d8-123">Az élettartam növelése, illetve az Élettartam az Értékmodellen és/vagy az eszköz Értékcsökkenés könyvében történő módosítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="d29d8-123">To increase the service life, modify the Service life on the Value models and/or Depreciation books for the asset.</span></span>  

