---
title: Változat előléptetése és egy kísérlet végrehajtása
description: Ez a témakör azt mutatja be, hogyan lehet egy sikeres változatot előléptetni és egy kísérletet végrehajtani a Dynamics 365 Commerce rendszerben.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
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
ms.openlocfilehash: c7da601323663d4c1ea76f7cad7bdab8e7632d1c
ms.sourcegitcommit: cd83f2bc0e52e13071ad306e07e4c255fc65cb03
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/22/2020
ms.locfileid: "4413005"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a><span data-ttu-id="38092-103">Változat előléptetése és egy kísérlet végrehajtása</span><span class="sxs-lookup"><span data-stu-id="38092-103">Promote a variation and complete an experiment</span></span>

<span data-ttu-id="38092-104">Ez a témakör azt mutatja be, hogyan lehet előléptetni a kísérletek legjobb eredményeit hozó változatokat, valamint a kísérleteket végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="38092-104">This topic describes how to promote the variation that produced the best results in your experiment, and how to complete the experiment.</span></span> <span data-ttu-id="38092-105">A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó kísérletet lehet létrehozni és futtatni a Dynamics 365 Commerce rendszerben.</span><span class="sxs-lookup"><span data-stu-id="38092-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="38092-106">A további lépések külön témákban szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="38092-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="38092-107">[ ![Kísérletezés felhasználói interakciósorozata – Áttekintés és befejezés](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="38092-107">[ ![Experimentation user journey - Review & Complete](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span></span>

<span data-ttu-id="38092-108">Miután [elvégezte a kísérletet](experimentation-run-monitor.md), és összegyűjtötte a szükséges adatokat annak meghatározására, hogy melyik változatot szeretné használni az élő webhelyén, előléptetheti a változatot, és befejezheti a kísérletet.</span><span class="sxs-lookup"><span data-stu-id="38092-108">After you've [run your experiment](experimentation-run-monitor.md) and collected sufficient data to determine which variation you want to use on your live site, you'll promote the variation and end the experiment.</span></span>

## <a name="promote-a-variation"></a><span data-ttu-id="38092-109">Változat előléptetése</span><span class="sxs-lookup"><span data-stu-id="38092-109">Promote a variation</span></span>
<span data-ttu-id="38092-110">A harmadik fél szolgáltatásban a kísérlethez kapcsolódó adatok és analitika alapján döntheti el, hogy melyik változat hozta létre a legjobb eredményt.</span><span class="sxs-lookup"><span data-stu-id="38092-110">Use the data and analytics related to the experiment in the third-party service to decide which variation produced the best results.</span></span> <span data-ttu-id="38092-111">Ezután az aktuális tartalom lecserélésével előléptetheti az élő webhelyen a legjobbnak tartott változattal, hogy a webhely összes felhasználója számára elérhető legyen.</span><span class="sxs-lookup"><span data-stu-id="38092-111">You can then promote it by replacing the current content on the live site with the winning variation so that it's available to all users of your website.</span></span>

<span data-ttu-id="38092-112">A nyerő változat előléptetéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="38092-112">To promote the winning variation, follow these steps.</span></span> 

1. <span data-ttu-id="38092-113">A Commerce webhelykészítőben lépjen a **Kísérletek** fülre a bal oldali navigációs panelen, majd válassza ki a kísérletet.</span><span class="sxs-lookup"><span data-stu-id="38092-113">In Commerce site builder, select **Experiments** in the left navigation pane, and then select the experiment.</span></span>
1. <span data-ttu-id="38092-114">A parancssávon válassza ki a **Teljes kísérlet** elemet.</span><span class="sxs-lookup"><span data-stu-id="38092-114">On the command bar, select **Complete experiment**.</span></span>
1. <span data-ttu-id="38092-115">A **Teljes kísérlet** párbeszédpanel menüjében válassza ki a **Kísérletadatok áttekintése** elemet.</span><span class="sxs-lookup"><span data-stu-id="38092-115">In the **Complete the experiment** dialog box, select **Review the experiment data**.</span></span> <span data-ttu-id="38092-116">A harmadik fél szolgáltatás megnyílik, és Ön ellenőrizheti a mérőszámokat, és meghatározhatja, hogy melyik változat teljesített a legjobban.</span><span class="sxs-lookup"><span data-stu-id="38092-116">The third-party service opens where you can validate the metrics and determine which variation performed the best.</span></span>
1. <span data-ttu-id="38092-117">Válassza ki a legjobbnak tartott változatot a **Teljes kísérlet** párbeszédpanel menüjében, majd válassza a **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="38092-117">In the **Complete the experiment** dialog box, select the winning variation, and then select **Next**.</span></span>
1. <span data-ttu-id="38092-118">Nyissa meg a harmadik fél szolgáltatást, és állítsa le a kísérletet.</span><span class="sxs-lookup"><span data-stu-id="38092-118">Open the third-party service and stop the experiment.</span></span>
1. <span data-ttu-id="38092-119">A webhelykészítőben válassza ki a **Befejezés** lehetőséget az eredeti élő oldal felülírásához és a legjobbnak tartott változat közzétételéhez úgy, hogy a webhely minden felhasználója számára elérhető legyen.</span><span class="sxs-lookup"><span data-stu-id="38092-119">In site builder, select **Complete** to overwrite the original live page and publish the winning variation so that it's available to all users of your website.</span></span> 

> [!NOTE]
> <span data-ttu-id="38092-120">Ha úgy dönt, hogy megtartja az aktuális élő oldalt, és nem tesz közzé egy változatot, jelölje be az **Eredeti oldal ismételt közzététele** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="38092-120">If you choose to keep the current live page and not publish a variation, select **Republish the original page**.</span></span>

## <a name="delete-your-experiment"></a><span data-ttu-id="38092-121">A kísérlet törlése</span><span class="sxs-lookup"><span data-stu-id="38092-121">Delete your experiment</span></span>
<span data-ttu-id="38092-122">A Commerce rendszerből ugyan nem kell kitörölni a befejezett kísérletet, erre azonban lehetőség van tárhely felszabadítása vagy a munkatér megtisztítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="38092-122">While it's not required that you delete a completed experiment in Commerce, you may choose to delete it to save space or clean up your workspace.</span></span> 

<span data-ttu-id="38092-123">A következő lépésekkel törölhet egy kísérletet a Commerce webhelyszerkesztőben.</span><span class="sxs-lookup"><span data-stu-id="38092-123">To delete an experiment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="38092-124">Lépjen a **Kísérletek** fülre a bal oldali navigációs panelen, majd válassza ki a kísérletet.</span><span class="sxs-lookup"><span data-stu-id="38092-124">Select **Experiments** in the left navigation pane, and then select the experiment.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="38092-125">Ha a kísérlet továbbra is aktív, akkor a továbblépés előtt állítsa le a kísérletet a harmadik fél szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="38092-125">If the experiment is still active, stop the experiment in the third-party service before proceeding.</span></span>
1. <span data-ttu-id="38092-126">A parancssoron a **Közzététel megszüntetése** lehetőség kiválasztásával eltávolíthatja a változat tartalmát az élő webhelyről.</span><span class="sxs-lookup"><span data-stu-id="38092-126">On the command bar, select **Unpublish**  to remove the variation content from the live site.</span></span>
1. <span data-ttu-id="38092-127">A kísérlet törléséhez válassza a **törlés** elemet.</span><span class="sxs-lookup"><span data-stu-id="38092-127">Select **Delete** to delete the experiment.</span></span>

## <a name="previous-step"></a><span data-ttu-id="38092-128">Előző lépés</span><span class="sxs-lookup"><span data-stu-id="38092-128">Previous step</span></span>
[<span data-ttu-id="38092-129">Kísérlet futtatása és nyomon követése</span><span class="sxs-lookup"><span data-stu-id="38092-129">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)
