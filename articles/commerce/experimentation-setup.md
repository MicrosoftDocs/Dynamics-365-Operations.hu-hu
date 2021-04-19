---
title: Kísérlet beállítása
description: Ez a témakör azt mutatja be, hogyan állíthat be kísérletet egy harmadik fél szolgáltatásban.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 9976ca461f7e988c32b81565fa2d084709e5ad6e
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792510"
---
# <a name="set-up-an-experiment"></a><span data-ttu-id="fce36-103">Kísérlet beállítása</span><span class="sxs-lookup"><span data-stu-id="fce36-103">Set up an experiment</span></span>

<span data-ttu-id="fce36-104">Miután [meghatározott egy hipotézist, valamint a használni kívánt sikerességi mérőszámokat](experimentation-identify.md), be kell állítani a kísérletet a harmadik fél szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="fce36-104">After you [define a hypothesis and determine what success metrics you want to use](experimentation-identify.md), you'll need to set up your experiment in the third-party service.</span></span> <span data-ttu-id="fce36-105">A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó kísérletet lehet létrehozni és futtatni a Dynamics 365 Commerce rendszerben.</span><span class="sxs-lookup"><span data-stu-id="fce36-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="fce36-106">A további lépések külön témákban szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="fce36-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="fce36-107">[ ![Kísérletezés felhasználói interakciósorozata – Beállítás](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="fce36-107">[ ![Experimentation user journey - Setup](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)</span></span>


## <a name="set-up-your-experiment-in-the-third-party-service"></a><span data-ttu-id="fce36-108">A kísérlet beállítása a harmadik szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="fce36-108">Set up your experiment in the third-party service</span></span>
<span data-ttu-id="fce36-109">Eddigre már eldöntötte, hogy harmadik fél szolgáltatással futtatja és követi nyomon a kísérletet, és beállította a kísérlet-összekötőt.</span><span class="sxs-lookup"><span data-stu-id="fce36-109">By now you should have chosen your third-party service to run and monitor your experiment, and set up the experimentation connector.</span></span> <span data-ttu-id="fce36-110">Ezeket az előfeltételeket a [Kísérletezés a Dynamics 365 Commerce rendszerben](experimentation-overview.md) rész sorolja fel.</span><span class="sxs-lookup"><span data-stu-id="fce36-110">These prerequisites are listed in  [Experimentation in Dynamics 365 Commerce](experimentation-overview.md).</span></span>

<span data-ttu-id="fce36-111">Kövesse a kísérlet harmadik fél szolgáltatásban való létrehozásához szükséges lépéseket.</span><span class="sxs-lookup"><span data-stu-id="fce36-111">Follow the steps required to create your experiment in the third-party service.</span></span> <span data-ttu-id="fce36-112">Ha az összekötőt jól konfigurálta, a harmadik fél szolgáltatásban beállított kísérletek teljes listája mintegy 5 percen belül megjelenik a Commerce webhelykészítőben.</span><span class="sxs-lookup"><span data-stu-id="fce36-112">If the connector is configured properly, the complete list of experiments you set up in the third-party service will appear in Commerce site builder within about 5 minutes.</span></span>

## <a name="set-up-your-success-metrics"></a><span data-ttu-id="fce36-113">A sikerességi mérőszámok beállítása</span><span class="sxs-lookup"><span data-stu-id="fce36-113">Set up your success metrics</span></span>
<span data-ttu-id="fce36-114">Minden kísérlethez mérőszámok szükségesek a változatok hatásainak mérésére és a hipotézis ellenőrzésére.</span><span class="sxs-lookup"><span data-stu-id="fce36-114">Every experiment needs metrics to measure the impact of the variations and to validate the hypothesis.</span></span> <span data-ttu-id="fce36-115">Hajtsa végre az alábbi lépéseket, ha engedélyezni szeretné a mérőszámok számítását a harmadik fél szolgáltatásban a Dynamics 365 Commerce rendszerben élő telemetria eseményei segítségével.</span><span class="sxs-lookup"><span data-stu-id="fce36-115">Follow the steps below to enable the computation of metrics in the third-party service using live telemetry events from Dynamics 365 Commerce.</span></span>

<span data-ttu-id="fce36-116">A sikermutatók beállításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="fce36-116">To set up your success metrics, follow these steps.</span></span>

1. <span data-ttu-id="fce36-117">A Commerce webhelykészítőben a bal oldali navigációs ablakban válassza ki az **Oldalak** fület, majd válassza ki azt az oldalt, amelyhez a mérőszámokat gyűjteni szeretné.</span><span class="sxs-lookup"><span data-stu-id="fce36-117">In Commerce site builder, select **Pages** in the left navigation pane, and then select the page that you want to collect metrics for.</span></span> 
1. <span data-ttu-id="fce36-118">Lépjen a követni kívánt oldal vagy modul jobb oldali tulajdonságok panelján lévő **Követendő eseményazonosítók** szakaszra.</span><span class="sxs-lookup"><span data-stu-id="fce36-118">Go to the **Event IDs to track** section in the right property pane of the page or module you want to track.</span></span>
1. <span data-ttu-id="fce36-119">Válassza ki a **Nézet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fce36-119">Select **View**.</span></span> <span data-ttu-id="fce36-120">Megjelenik az összes eseményazonosító listája.</span><span class="sxs-lookup"><span data-stu-id="fce36-120">A list of all event IDs is displayed.</span></span> <span data-ttu-id="fce36-121">Másolja ki a nyomon követni kívánt eseményt, majd illessze be az eseménykulcsot a harmadik fél szolgáltatás által meghatározott helyre.</span><span class="sxs-lookup"><span data-stu-id="fce36-121">Copy the event you want to track, and paste the event key into the designated location in the third-party service.</span></span> <span data-ttu-id="fce36-122">Ha egynél több eseményre van szüksége, akkor egyenként másolja át a kulcsokat.</span><span class="sxs-lookup"><span data-stu-id="fce36-122">If you need more than one event, copy the keys one at a time.</span></span> 
    - <span data-ttu-id="fce36-123">A rendelkezésre álló események és attribútumok, köztük az oldalmegtekintések és a bevételek nyomon követése megtekintéséhez a következő témakör tartalmaz további tájékoztatást: [Commerce-összetevővel kapcsolatos események a diagnosztikához és a hibaelhárításhoz](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="fce36-123">To learn how to view all of the available events and attributes, including page views and revenue tracking, see [Commerce component events for diagnostics and troubleshooting](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span></span>
1. <span data-ttu-id="fce36-124">Hajtsa végre a szükséges lépéseket a mérőszámoknak a harmadik fél szolgáltatásban való nyomon követéséhez.</span><span class="sxs-lookup"><span data-stu-id="fce36-124">Take any other steps for tracking metrics as required in the third-party service.</span></span>

## <a name="previous-step"></a><span data-ttu-id="fce36-125">Előző lépés</span><span class="sxs-lookup"><span data-stu-id="fce36-125">Previous step</span></span>
[<span data-ttu-id="fce36-126">Hipotézis meghatározása és mérőszámok megadása egy kísérlethez</span><span class="sxs-lookup"><span data-stu-id="fce36-126">Identify a hypothesis and determine metrics for an experiment</span></span>](experimentation-identify.md) 


## <a name="next-step"></a><span data-ttu-id="fce36-127">Következő lépés</span><span class="sxs-lookup"><span data-stu-id="fce36-127">Next step</span></span>
[<span data-ttu-id="fce36-128">Kísérlet csatlakoztatása és szerkesztése</span><span class="sxs-lookup"><span data-stu-id="fce36-128">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]