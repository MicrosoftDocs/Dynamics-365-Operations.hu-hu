---
title: Kísérlet előnézetének megtekintése és közzététele
description: Ez a témakör azt mutatja be, hogyan tekinthető meg és tehető közzé egy kísérlet a Dynamics 365 Commerce rendszerből.
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
ms.openlocfilehash: 52ca23e5aaeb7058853fed2241d5804180fa7f8d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798963"
---
# <a name="preview-and-publish-an-experiment"></a><span data-ttu-id="41ddd-103">Kísérlet előnézetének megtekintése és közzététele</span><span class="sxs-lookup"><span data-stu-id="41ddd-103">Preview and publish an experiment</span></span>

<span data-ttu-id="41ddd-104">Ez a témakör azt mutatja be, hogyan tekinthető meg és tehető közzé egy kísérlet a Dynamics 365 Commerce rendszerből, miután [csatlakoztatta a kísérletet és szerkesztette a változatokat](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="41ddd-104">This topic describes how to preview and publish your experiment in Dynamics 365 Commerce after you've [connected your experiment and edited your variations](experimentation-connect-edit.md).</span></span> <span data-ttu-id="41ddd-105">A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó kísérletet lehet létrehozni és futtatni a Dynamics 365 Commerce rendszerben.</span><span class="sxs-lookup"><span data-stu-id="41ddd-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="41ddd-106">A további lépések külön témákban szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="41ddd-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="41ddd-107">[ ![Kísérletezés felhasználói interakciósorozata – Előnézet és közzététel](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="41ddd-107">[ ![Experimentation user journey - Preview & Publish](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span></span>

## <a name="preview-your-experiment-variations"></a><span data-ttu-id="41ddd-108">A kísérletek változatainak előnézete</span><span class="sxs-lookup"><span data-stu-id="41ddd-108">Preview your experiment variations</span></span>
<span data-ttu-id="41ddd-109">Megtekintheti a változatokat, és folytathatja a szerkesztést egészen addig, amíg azok el nem nyerik a tetszőleges állapotot.</span><span class="sxs-lookup"><span data-stu-id="41ddd-109">You can preview your variations and continue editing them until they look the way you want them to.</span></span>

<span data-ttu-id="41ddd-110">A Commerce webhelykészítőben a kísérlet változatai előnézetének megtekintéséhez hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="41ddd-110">To preview your experiment variations in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="41ddd-111">A parancssáv alatti változatok legördülő menü segítségével kiválaszthatja az előnézetben megtekinteni kívánt tartalmat.</span><span class="sxs-lookup"><span data-stu-id="41ddd-111">From the variations drop-down menu below the command bar, select the content you want to preview.</span></span> 
1. <span data-ttu-id="41ddd-112">Válassza a parancssáv **Előnézet** elemét.</span><span class="sxs-lookup"><span data-stu-id="41ddd-112">On the command bar, select **Preview**.</span></span> <span data-ttu-id="41ddd-113">Annak az előnézete, hogy hogyan fog festeni a tartalom a közzététel utáni megjelenítéskor.</span><span class="sxs-lookup"><span data-stu-id="41ddd-113">A preview of what the content will look like when it's published is displayed.</span></span>
1. <span data-ttu-id="41ddd-114">A különböző változatok előnézetéhez válassza ki az adott elemet a változatok legördülő menüből, majd újból válassza ki az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="41ddd-114">To preview a different variation, select it from the variation drop-down menu and select **Preview** again.</span></span>

## <a name="publish-your-experiment"></a><span data-ttu-id="41ddd-115">A kísérlet közzététele</span><span class="sxs-lookup"><span data-stu-id="41ddd-115">Publish your experiment</span></span>
<span data-ttu-id="41ddd-116">Ha nem használ közzétételi csoportot annak ütemezéséhez, hogy mikor lépjen életbe a kísérlet, és azonnali közzétételt szeretne végezni, akkor a **Közzététel** parancsot válassza ki a parancssorban.</span><span class="sxs-lookup"><span data-stu-id="41ddd-116">If you aren't using a publish group to schedule when your experiment goes live and you want to publish immediately, select **Publish** in the command bar.</span></span> <span data-ttu-id="41ddd-117">A program az összes, a kísérlethez tartozó változatot közzéteszi.</span><span class="sxs-lookup"><span data-stu-id="41ddd-117">All variations that belong to the experiment will be published.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="41ddd-118">Ha az oldal nem közzétett URL-címmel rendelkezik, akkor először közzé kell tennie az URL-címet, ellenkező esetben nem lesz látható a webhely felhasználói számára.</span><span class="sxs-lookup"><span data-stu-id="41ddd-118">If the page has an unpublished URL, you must first publish the URL or it won't be visible to your website users.</span></span> <span data-ttu-id="41ddd-119">A részletekért lásd: [Oldal mentése, előnézete és közzététele](save-preview-publish-page.md).</span><span class="sxs-lookup"><span data-stu-id="41ddd-119">For details, see [Save, preview, and publish a page](save-preview-publish-page.md).</span></span>
    
### <a name="use-publish-groups-to-schedule-when-your-experiment-goes-live"></a><span data-ttu-id="41ddd-120">A közzétételi csoportokat annak ütemezéséhez használhatja, hogy mikor lépjen életbe a kísérlet.</span><span class="sxs-lookup"><span data-stu-id="41ddd-120">Use publish groups to schedule when your experiment goes live</span></span>
<span data-ttu-id="41ddd-121">A webhelykészítőben létrehozott változatok közzététele egy közzétételi csoport segítségével ütemezhető be.</span><span class="sxs-lookup"><span data-stu-id="41ddd-121">Variations created in site builder can be scheduled for publishing by using a publish group.</span></span> <span data-ttu-id="41ddd-122">A közzétételi csoporton belül a bal oldali navigációs ablak **Kísérletek** elemét kiválasztva egy oldalt vagy egy töredéket is csatlakoztathat a kísérlethez.</span><span class="sxs-lookup"><span data-stu-id="41ddd-122">Within a publish group, you can connect a page or fragment to your experiment by selecting **Experiments** in the left navigation pane.</span></span> <span data-ttu-id="41ddd-123">Ezt úgy is megteheti, hogy kiválasztja az **Oldalak** vagy **Töredékek** elemet, és követi az útmutatót a [Kísérlet csatlakoztatása és változatok szerkesztése](experimentation-connect-edit.md) részben.</span><span class="sxs-lookup"><span data-stu-id="41ddd-123">You can also do this by selecting **Pages** or **Fragments** and following the instructions in [Connect an experiment and edit variations](experimentation-connect-edit.md).</span></span> <span data-ttu-id="41ddd-124">A közzétételi csoportokkal kapcsolatos további tudnivalókat lásd: [Munka a közzétételi csoportokkal](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="41ddd-124">For information about publish groups, see [Work with publish groups](publish-groups.md).</span></span>

<span data-ttu-id="41ddd-125">Ha a kísérletekhez közzétételi csoportokat használ, akkor figyelembe kell vennie néhány fontos szempontot.</span><span class="sxs-lookup"><span data-stu-id="41ddd-125">When using publish groups with experiments, there are some important considerations to be aware of.</span></span>
- <span data-ttu-id="41ddd-126">Amikor olyan oldalt vagy töredéket ad hozzá egy közzétételi csoporthoz, amelyen egy kísérlet fut, a kísérletet eltávolítja a program a közzétételi csoportban lévő oldalról vagy töredékből.</span><span class="sxs-lookup"><span data-stu-id="41ddd-126">When you add a page or fragment that has an experiment running on it to a publish group, the experiment will be removed from the page or fragment in the publish group.</span></span>
- <span data-ttu-id="41ddd-127">Az élő webhely oldalaihoz kapcsolódó kísérletek nem érhetők el a közzétételi csoportokon belüli oldalakhoz, és fordítva.</span><span class="sxs-lookup"><span data-stu-id="41ddd-127">Experiments that are connected to pages in a live site aren't available to pages within publish groups and vice-versa.</span></span> <span data-ttu-id="41ddd-128">Hasonlóképpen az élő webhelyen futó kísérleteket tartalmazó oldalak nem érhetők el a közzétételi csoportok egyéb kísérleteihez, és fordítva.</span><span class="sxs-lookup"><span data-stu-id="41ddd-128">Similarly, pages that have experiments running on them in a live site aren't available to other experiments in publish groups and vice versa.</span></span>
- <span data-ttu-id="41ddd-129">Közzétételi csoport közzététele vagy ütemezése során a közzétételi csoport minden tartalmát közzéteszi a program, függetlenül attól, hogy van-e a közzétételi csoporthoz kapcsolt kísérlet.</span><span class="sxs-lookup"><span data-stu-id="41ddd-129">When you publish or schedule a publish group, all content in the publish group is published, regardless of whether there's an experiment associated with the publish group.</span></span>
- <span data-ttu-id="41ddd-130">Mivel a közzétételi csoport azt követően is létezik, hogy élő webhelyen közzétették, a közzétételi csoport kísérletei is megmaradnak.</span><span class="sxs-lookup"><span data-stu-id="41ddd-130">Because a publish group continues to persist after it's been published to a live site, experiments in the publish group will also persist.</span></span> <span data-ttu-id="41ddd-131">Emiatt más kísérleteket nem lehet ugyanazzal az oldalhoz vagy töredékhez társítani.</span><span class="sxs-lookup"><span data-stu-id="41ddd-131">Therefore, you won't be able to associate other experiments with the same page or fragment.</span></span> <span data-ttu-id="41ddd-132">E korlátozás elkerülése érdekében törölje a megmaradó kísérletekkel rendelkező közzétételi csoportokat.</span><span class="sxs-lookup"><span data-stu-id="41ddd-132">To avoid this limitation, delete any publish groups with persisting experiments.</span></span> <span data-ttu-id="41ddd-133">Hasonlóképpen, ha törölni szeretne egy olyan kísérletet egy élő webhelyről, amely a közzétételi csoportban is szerepel, akkor először törölje azt a közzétételi csoportból.</span><span class="sxs-lookup"><span data-stu-id="41ddd-133">Similarly, if you want to delete an experiment in a live site that also exists in a publish group, delete it from the publish group first.</span></span>

## <a name="previous-step"></a><span data-ttu-id="41ddd-134">Előző lépés</span><span class="sxs-lookup"><span data-stu-id="41ddd-134">Previous step</span></span>
[<span data-ttu-id="41ddd-135">Kísérlet csatlakoztatása és szerkesztése</span><span class="sxs-lookup"><span data-stu-id="41ddd-135">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)

## <a name="next-step"></a><span data-ttu-id="41ddd-136">Következő lépés</span><span class="sxs-lookup"><span data-stu-id="41ddd-136">Next step</span></span>
[<span data-ttu-id="41ddd-137">Kísérlet futtatása és nyomon követése</span><span class="sxs-lookup"><span data-stu-id="41ddd-137">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]