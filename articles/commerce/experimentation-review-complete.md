---
title: Változat előléptetése és egy kísérlet végrehajtása
description: Ez a témakör azt mutatja be, hogyan lehet egy sikeres változatot előléptetni és egy kísérletet végrehajtani a Dynamics 365 Commerce rendszerben.
author: sushma-rao
manager: AnnBe
ms.date: 09/15/2020
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
ms.openlocfilehash: 2e011f10e908d6a2efe2e928fc5e0abc7659cb8b
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930208"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a><span data-ttu-id="1ec53-103">Változat előléptetése és egy kísérlet végrehajtása</span><span class="sxs-lookup"><span data-stu-id="1ec53-103">Promote a variation and complete an experiment</span></span>

<span data-ttu-id="1ec53-104">Ez a témakör azt mutatja be, hogyan lehet előléptetni a kísérletek legjobb eredményeit hozó változatokat, valamint a kísérleteket végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="1ec53-104">This topic describes how to promote the variation that produced the best results in your experiment, and how to complete the experiment.</span></span> <span data-ttu-id="1ec53-105">A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó kísérletet lehet létrehozni és futtatni a Dynamics 365 Commerce rendszerben.</span><span class="sxs-lookup"><span data-stu-id="1ec53-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="1ec53-106">A további lépések külön témákban szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="1ec53-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="1ec53-107">[ ![Kísérletezés felhasználói interakciósorozata – Áttekintés és befejezés](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="1ec53-107">[ ![Experimentation user journey - Review & Complete](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span></span>

<span data-ttu-id="1ec53-108">Miután [elvégezte a kísérletet](experimentation-run-monitor.md), és összegyűjtötte a szükséges adatokat annak meghatározására, hogy melyik változatot szeretné használni az élő webhelyén, előléptetheti a változatot, és befejezheti a kísérletet.</span><span class="sxs-lookup"><span data-stu-id="1ec53-108">After you've [run your experiment](experimentation-run-monitor.md) and collected sufficient data to determine which variation you want to use on your live site, you'll promote the variation and end the experiment.</span></span>

## <a name="promote-a-variation"></a><span data-ttu-id="1ec53-109">Változat előléptetése</span><span class="sxs-lookup"><span data-stu-id="1ec53-109">Promote a variation</span></span>
<span data-ttu-id="1ec53-110">A harmadik fél szolgáltatásban a kísérlethez kapcsolódó adatok és analitika alapján döntheti el, hogy melyik változat hozta létre a legjobb eredményt.</span><span class="sxs-lookup"><span data-stu-id="1ec53-110">Use the data and analytics related to the experiment in the third-party service to decide which variation produced the best results.</span></span> <span data-ttu-id="1ec53-111">Ha az aktuális tartalmat a legjobbnak tartott változattal szeretné helyettesíteni a webhely összes felhasználója számára, akkor tegye a következőket.</span><span class="sxs-lookup"><span data-stu-id="1ec53-111">To replace the current content on the live site with the winning variation so that it's available to all users of your website, do the following.</span></span> 

1. <span data-ttu-id="1ec53-112">Lépjen a webhelykészítő **Kísérletek** fülére, és válassza ki a kísérletet.</span><span class="sxs-lookup"><span data-stu-id="1ec53-112">Go to the **Experiments** tab in site builder and select the experiment.</span></span>
1. <span data-ttu-id="1ec53-113">Válassza ki a felső sávon lévő **Teljes kísérlet** elemet.</span><span class="sxs-lookup"><span data-stu-id="1ec53-113">Select **Complete experiment** on the top bar.</span></span>
1. <span data-ttu-id="1ec53-114">A **Teljes kísérlet** párbeszédpanel menüjében válassza ki a **Kísérletadatok áttekintése** elemet.</span><span class="sxs-lookup"><span data-stu-id="1ec53-114">In the **Complete the experiment** dialog menu, select **Review the experiment data** .</span></span> <span data-ttu-id="1ec53-115">A harmadik fél szolgáltatás megnyílik, és Ön ellenőrizheti a mérőszámokat, és meghatározhatja, hogy melyik változat teljesített a legjobban.</span><span class="sxs-lookup"><span data-stu-id="1ec53-115">The third-party service opens where you can validate the metrics and determine which variation performed the best.</span></span>
1. <span data-ttu-id="1ec53-116">Válassza ki a legjobbnak tartott változatot a webhelykészítő **Teljes kísérlet** párbeszédpanel menüjében, majd válassza a **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1ec53-116">In the **Complete the experiment** dialog menu in site builder, select the winning variation and then select **Next** .</span></span>
1. <span data-ttu-id="1ec53-117">Nyissa meg a harmadik fél szolgáltatást, és állítsa le a kísérletet.</span><span class="sxs-lookup"><span data-stu-id="1ec53-117">Open the third-party service and stop the experiment.</span></span>
1. <span data-ttu-id="1ec53-118">A webhelykészítőben válassza ki a **Befejezés** lehetőséget az eredeti élő oldal felülírásához és a legjobbnak tartott változat közzétételéhez úgy, hogy a webhely minden felhasználója számára elérhető legyen.</span><span class="sxs-lookup"><span data-stu-id="1ec53-118">In site builder, select **Complete** to overwrite the original live page and publish the winning variation so that it's available to all users of your website.</span></span> 

> [!NOTE]
> <span data-ttu-id="1ec53-119">Ha úgy dönt, hogy megtartja az aktuális élő oldalt, és nem tesz közzé egy változatot, jelölje be az **Eredeti oldal ismételt közzététele** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="1ec53-119">If you choose to keep the current live page and not publish a variation, select **Republish the original page** .</span></span>

## <a name="delete-your-experiment"></a><span data-ttu-id="1ec53-120">A kísérlet törlése</span><span class="sxs-lookup"><span data-stu-id="1ec53-120">Delete your experiment</span></span>
<span data-ttu-id="1ec53-121">A Commerce rendszerből ugyan nem kell kitörölni a befejezett kísérletet, erre azonban lehetőség van tárhely felszabadítása vagy a munkatér megtisztítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="1ec53-121">While it's not required that you delete a completed experiment in Commerce, you may choose to delete it to save space or clean up your workspace.</span></span> <span data-ttu-id="1ec53-122">Egy kísérlet törléséhez a következő műveleteket hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="1ec53-122">To delete an experiment, do the following.</span></span>

1. <span data-ttu-id="1ec53-123">Lépjen a webhelykészítő **Kísérletek** fülére, és válassza ki a kísérletet.</span><span class="sxs-lookup"><span data-stu-id="1ec53-123">Go to the **Experiments** tab in site builder and select the experiment.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="1ec53-124">Ha a kísérlet továbbra is aktív, akkor a továbblépés előtt állítsa le a kísérletet a harmadik fél szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="1ec53-124">If the experiment is still active, stop the experiment in the third-party service before proceeding.</span></span>
1. <span data-ttu-id="1ec53-125">A parancssoron található **Közzététel megszüntetése** lehetőség kiválasztásával eltávolíthatja a változat tartalmát az élő webhelyről.</span><span class="sxs-lookup"><span data-stu-id="1ec53-125">Select **Unpublish** in the command bar to remove the variation content from the live site.</span></span>
1. <span data-ttu-id="1ec53-126">A parancssoron található **Törlés** lehetőség kiválasztásával törölheti a kísérletet.</span><span class="sxs-lookup"><span data-stu-id="1ec53-126">Select **Delete** in the command bar to delete the experiment.</span></span>

## <a name="previous-step"></a><span data-ttu-id="1ec53-127">Előző lépés</span><span class="sxs-lookup"><span data-stu-id="1ec53-127">Previous step</span></span>
[<span data-ttu-id="1ec53-128">Kísérlet futtatása és nyomon követése</span><span class="sxs-lookup"><span data-stu-id="1ec53-128">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)
