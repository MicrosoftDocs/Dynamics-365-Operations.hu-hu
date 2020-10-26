---
title: Kísérlet beállítása
description: Ez a témakör azt mutatja be, hogyan állíthat be kísérletet egy harmadik fél szolgáltatásban.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 0f7db0ce009f6ee7603952891aacfdc16fcde016
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930212"
---
# <a name="set-up-an-experiment"></a><span data-ttu-id="141f4-103">Kísérlet beállítása</span><span class="sxs-lookup"><span data-stu-id="141f4-103">Set up an experiment</span></span>

<span data-ttu-id="141f4-104">Miután [meghatározott egy hipotézist, valamint a használni kívánt sikerességi mérőszámokat](experimentation-identify.md), be kell állítani a kísérletet a harmadik fél szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="141f4-104">After you [define a hypothesis and determine what success metrics you want to use](experimentation-identify.md), you'll need to set up your experiment in the third-party service.</span></span> <span data-ttu-id="141f4-105">A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó kísérletet lehet létrehozni és futtatni a Dynamics 365 Commerce rendszerben.</span><span class="sxs-lookup"><span data-stu-id="141f4-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="141f4-106">A további lépések külön témákban szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="141f4-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="141f4-107">[ ![Kísérletezés felhasználói interakciósorozata – Beállítás](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="141f4-107">[ ![Experimentation user journey - Setup](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)</span></span>


## <a name="set-up-your-experiment-in-the-third-party-service"></a><span data-ttu-id="141f4-108">A kísérlet beállítása a harmadik szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="141f4-108">Set up your experiment in the third-party service</span></span>
<span data-ttu-id="141f4-109">Eddigre már eldöntötte, hogy harmadik fél szolgáltatással futtatja és követi nyomon a kísérletet, és beállította a kísérlet-összekötőt.</span><span class="sxs-lookup"><span data-stu-id="141f4-109">By now you should have chosen your third-party service to run and monitor your experiment, and set up the experimentation connector.</span></span> <span data-ttu-id="141f4-110">Ezeket az előfeltételeket a [Kísérletezés a Dynamics 365 Commerce rendszerben](experimentation-overview.md) rész sorolja fel.</span><span class="sxs-lookup"><span data-stu-id="141f4-110">These prerequisites are listed in  [Experimentation in Dynamics 365 Commerce](experimentation-overview.md).</span></span>

<span data-ttu-id="141f4-111">Kövesse a kísérlet harmadik fél szolgáltatásban való létrehozásához szükséges lépéseket.</span><span class="sxs-lookup"><span data-stu-id="141f4-111">Follow the steps required to create your experiment in the third-party service.</span></span> <span data-ttu-id="141f4-112">Ha az összekötőt jól konfigurálta, a harmadik fél szolgáltatásban beállított kísérletek teljes listája mintegy 5 percen belül megjelenik a webhelykészítőben.</span><span class="sxs-lookup"><span data-stu-id="141f4-112">If the connector is configured properly, the complete list of experiments you set up in the third-party service will surface in site builder within about 5 minutes.</span></span>

## <a name="set-up-your-success-metrics"></a><span data-ttu-id="141f4-113">A sikerességi mérőszámok beállítása</span><span class="sxs-lookup"><span data-stu-id="141f4-113">Set up your success metrics</span></span>
<span data-ttu-id="141f4-114">Minden kísérlethez mérőszámok szükségesek a változatok hatásainak mérésére és a hipotézis ellenőrzésére.</span><span class="sxs-lookup"><span data-stu-id="141f4-114">Every experiment needs metrics to measure the impact of the variations and to validate the hypothesis.</span></span> <span data-ttu-id="141f4-115">Hajtsa végre az alábbi lépéseket, ha engedélyezni szeretné a mérőszámok számítását a harmadik fél szolgáltatásban a Dynamics 365 Commerce rendszerben élő telemetria eseményei segítségével.</span><span class="sxs-lookup"><span data-stu-id="141f4-115">Follow the steps below to enable the computation of metrics in the third-party service using live telemetry events from Dynamics 365 Commerce.</span></span>

1. <span data-ttu-id="141f4-116">A webhelykészítőben a bal oldali navigációs ablakban válassza ki az **Oldalak** fület, majd válassza ki azt az oldalt, amelyen a mérőszámokat gyűjteni szeretné.</span><span class="sxs-lookup"><span data-stu-id="141f4-116">In site builder, select the **Pages** tab in the left navigation pane and then select the page that you want to collect metrics on.</span></span> 
1. <span data-ttu-id="141f4-117">Lépjen a követni kívánt oldal vagy modul jobb oldali tulajdonságok panelján lévő **Követendő eseményazonosítók** szakaszra.</span><span class="sxs-lookup"><span data-stu-id="141f4-117">Go to the **Event IDs to track** section in the right property pane of the page or module you want to track.</span></span>
1. <span data-ttu-id="141f4-118">Válassza ki a **Nézet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="141f4-118">Select **View** .</span></span> <span data-ttu-id="141f4-119">Megjelenik az összes eseményazonosító listája.</span><span class="sxs-lookup"><span data-stu-id="141f4-119">A list of all event IDs is displayed.</span></span> <span data-ttu-id="141f4-120">Másolja ki a nyomon követni kívánt eseményt, majd illessze be az eseménykulcsot a harmadik fél szolgáltatás által meghatározott helyre.</span><span class="sxs-lookup"><span data-stu-id="141f4-120">Copy the event you want to track, and paste the event key into the designated location in the third-party service.</span></span> <span data-ttu-id="141f4-121">Ha egynél több eseményre van szüksége, akkor egyenként másolja át a kulcsokat.</span><span class="sxs-lookup"><span data-stu-id="141f4-121">If you need more than one event, copy the keys one at a time.</span></span> 
    - <span data-ttu-id="141f4-122">A rendelkezésre álló események és attribútumok, köztük az oldalmegtekintések és a bevételek nyomon követése megtekintéséhez a következő témakör tartalmaz további tájékoztatást: [Commerce-összetevővel kapcsolatos események a diagnosztikához és a hibaelhárításhoz](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="141f4-122">To learn how to view all of the available events and attributes, including page views and revenue tracking, see [Commerce component events for diagnostics and troubleshooting](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span></span>
1. <span data-ttu-id="141f4-123">Hajtsa végre a szükséges lépéseket a mérőszámoknak a harmadik fél szolgáltatásban való nyomon követéséhez.</span><span class="sxs-lookup"><span data-stu-id="141f4-123">Take any other steps for tracking metrics as required in the third-party service.</span></span>

## <a name="previous-step"></a><span data-ttu-id="141f4-124">Előző lépés</span><span class="sxs-lookup"><span data-stu-id="141f4-124">Previous step</span></span>
[<span data-ttu-id="141f4-125">Hipotézis meghatározása és mérőszámok megadása egy kísérlethez</span><span class="sxs-lookup"><span data-stu-id="141f4-125">Identify a hypothesis and determine metrics for an experiment</span></span>](experimentation-identify.md) 


## <a name="next-step"></a><span data-ttu-id="141f4-126">Következő lépés</span><span class="sxs-lookup"><span data-stu-id="141f4-126">Next step</span></span>
[<span data-ttu-id="141f4-127">Kísérlet csatlakoztatása és szerkesztése</span><span class="sxs-lookup"><span data-stu-id="141f4-127">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)
