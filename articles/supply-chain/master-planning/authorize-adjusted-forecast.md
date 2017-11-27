---
title: "Módosított előrejelzés engedélyezése"
description: "Nem szükséges minden előrejelzési adatot azonnal engedélyezni. Ez a cikk ismerteti, hogyan határozza meg azt a periódust, amelyre az előrejelzés engedélyezett. Továbbá azt is megmutatja, hogyan engedélyezheti az előrejelzést adott vállalatokra vagy előrejelzési modellekre vonatkozóan."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 5ce38e94ae4c7b28b4e182018add7c046f685e46
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="authorize-an-adjusted-forecast"></a><span data-ttu-id="7f299-105">Módosított előrejelzés engedélyezése</span><span class="sxs-lookup"><span data-stu-id="7f299-105">Authorize an adjusted forecast</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="7f299-106">Nem szükséges minden előrejelzési adatot azonnal engedélyezni.</span><span class="sxs-lookup"><span data-stu-id="7f299-106">Not all forecast data must be authorized immediately.</span></span> <span data-ttu-id="7f299-107">Ez a cikk ismerteti, hogyan határozza meg azt a periódust, amelyre az előrejelzés engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="7f299-107">This article explains how you can specify the period that a forecast is authorized for.</span></span> <span data-ttu-id="7f299-108">Továbbá azt is megmutatja, hogyan engedélyezheti az előrejelzést adott vállalatokra vagy előrejelzési modellekre vonatkozóan.</span><span class="sxs-lookup"><span data-stu-id="7f299-108">It also explains how you can authorize the forecast for specific companies and forecast models.</span></span>

<span data-ttu-id="7f299-109">Nem szükséges minden előrejelzési adatot azonnal engedélyezni.</span><span class="sxs-lookup"><span data-stu-id="7f299-109">Not all forecast data must be authorized immediately.</span></span> <span data-ttu-id="7f299-110">Meghatározhatja annak a periódusnak a kezdő és a záró dátumait amelyre az előrejelzés engedélyezett.</span><span class="sxs-lookup"><span data-stu-id="7f299-110">You can specify the start and end dates of the period that the forecast is authorized for.</span></span> <span data-ttu-id="7f299-111">Ennek a funkciónak a segítségével meghatározott időszakokat rögzíthet.</span><span class="sxs-lookup"><span data-stu-id="7f299-111">This functionality lets you freeze specific buckets.</span></span> 

<span data-ttu-id="7f299-112">A megadott kezdő és záró dátumoknak meg kell egyezniük annak az időszaknak a kezdő és záró dátumaival, amelyben az előrejelzés létrejön.</span><span class="sxs-lookup"><span data-stu-id="7f299-112">The start and end dates that you specify must correspond to the start and end dates of the bucket that the forecast is generated in.</span></span> <span data-ttu-id="7f299-113">A rendszer ezt a korlátozást kikényszeríti, és automatikusan kiigazítja a dátumokat, amennyiben ez szükséges.</span><span class="sxs-lookup"><span data-stu-id="7f299-113">The system enforces this restriction and automatically adjusts the dates, if adjustment is required.</span></span> 

<span data-ttu-id="7f299-114">Az **Engedélyezés** oldal **Részletek** lapján megtekintheti a legutóbb létrehozott előrejelzés részleteit.</span><span class="sxs-lookup"><span data-stu-id="7f299-114">On the **Details** tab of the **Authorization** page, you can view details about the forecast that was most recently generated.</span></span> 

<span data-ttu-id="7f299-115">Kiválaszthatja a vállalatokat és az előrejelzési modelleket, hogy engedélyezze az előrejelzés használatát.</span><span class="sxs-lookup"><span data-stu-id="7f299-115">You can select the companies and the forecast models to authorize the forecast for use.</span></span> <span data-ttu-id="7f299-116">Alapértelmezett állapotban a rács tartalmazza az összes olyan vállalatot, melynek számára előrejelzési igény lett kreálva.</span><span class="sxs-lookup"><span data-stu-id="7f299-116">By default, the grid includes all the companies that forecast demand has been created for.</span></span> <span data-ttu-id="7f299-117">Az alaptervezésben felállított jelenlegi előrejelzési tervek (melyek megfelelnek az előrejelzési modellnek), minden vállalat esetében előre ki vannak töltve.</span><span class="sxs-lookup"><span data-stu-id="7f299-117">For each company, the forecast model that corresponds to the current forecast plan that is set up in the master planning parameters is prefilled.</span></span> <span data-ttu-id="7f299-118">Ettől függetlenül, ezt az előrejelzési modellt megváltoztathatja bármelyik másik, ahhoz a vállalathoz tartozó előrejelzési modellre.</span><span class="sxs-lookup"><span data-stu-id="7f299-118">However, you can change this forecast model to any forecast model that belongs to that company.</span></span> <span data-ttu-id="7f299-119">Amennyiben egy kiválasztott vállalat számára nincs adat az előrejelzési igényről, az importáláskor hibaüzenet jelzi a hiányt.</span><span class="sxs-lookup"><span data-stu-id="7f299-119">If no forecast demand data has been generated for a selected company, you receive a warning message at import time.</span></span> 

<span data-ttu-id="7f299-120">Rendkívül fontos, hogy megértse hogyan működik a **Manuális beállítások mentése és az alapvető igény-előrejelzés beállítások felülírása** jelölőnégyzet.</span><span class="sxs-lookup"><span data-stu-id="7f299-120">It's very important that you understand how the **Save the manual adjustments made to the baseline demand forecast** check box works.</span></span> <span data-ttu-id="7f299-121">Amennyiben hajtott végre manuális beállításokat a statisztikai kiinduló előrejelzésen, a kiigazított értékek akkor is engedélyezve vannak használatra, ha ez a jelölőnégyzet nincs bejelölve.</span><span class="sxs-lookup"><span data-stu-id="7f299-121">If you've made manual adjustments to the statistical baseline forecast, the adjusted values are authorized for use, even if this check box is cleared.</span></span> <span data-ttu-id="7f299-122">A módosítások az engedélyezés után törlődnek.</span><span class="sxs-lookup"><span data-stu-id="7f299-122">However, the changes are discarded after the authorization.</span></span> <span data-ttu-id="7f299-123">Így amikor következő alkalommal előrejelzést hoz létre, az előrejelzés csak statisztikai lesz és nem lesznek benne manuális felülírások akkor sem, ha a **Manuális kiigazítások átvitele az igény-előrejelzésbe** jelölőnégyzet be van jelölve.</span><span class="sxs-lookup"><span data-stu-id="7f299-123">Therefore, the next time that a forecast is generated, that forecast is only a statistical forecast and doesn't have any manual overrides, even if **Transfer manual adjustments to the demand forecast** is selected.</span></span> <span data-ttu-id="7f299-124">Megfontolandó tehát a **Manuális beállítások mentése és az alapvető igény-előrejelzés beállítások felülírása** jelölőnégyzet használata, mivel az megengedi, hogy megtartsa vagy elvesse az összes manuális változtatást.</span><span class="sxs-lookup"><span data-stu-id="7f299-124">Therefore, you can consider the **Save the manual adjustments made to the baseline demand forecast** check box a mechanism that lets you keep or discard all manual changes.</span></span>

<a name="see-also"></a><span data-ttu-id="7f299-125">Lásd még</span><span class="sxs-lookup"><span data-stu-id="7f299-125">See also</span></span>
--------

[<span data-ttu-id="7f299-126">A kiinduló előrejelzés manuális kiigazítása</span><span class="sxs-lookup"><span data-stu-id="7f299-126">Making manual adjustments to the baseline forecast</span></span>](manual-adjustments-baseline-forecast.md)

[<span data-ttu-id="7f299-127">Az előrejelzési pontosság megfigyelése</span><span class="sxs-lookup"><span data-stu-id="7f299-127">Monitoring forecast accuracy</span></span>](monitor-forecast-accuracy.md)




