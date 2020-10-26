---
title: Kísérlet előnézetének megtekintése és közzététele
description: Ez a témakör azt mutatja be, hogyan tekinthető meg és tehető közzé egy kísérlet a Dynamics 365 Commerce rendszerből.
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
ms.openlocfilehash: 91e2e4840a2d53f195d881279050b6415d48b070
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930213"
---
# <a name="preview-and-publish-an-experiment"></a><span data-ttu-id="d577e-103">Kísérlet előnézetének megtekintése és közzététele</span><span class="sxs-lookup"><span data-stu-id="d577e-103">Preview and publish an experiment</span></span>

<span data-ttu-id="d577e-104">Ez a témakör azt mutatja be, hogyan tekinthető meg és tehető közzé egy kísérlet a Dynamics 365 Commerce rendszerből, miután [csatlakoztatta a kísérletet és szerkesztette a változatokat](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="d577e-104">This topic describes how to preview and publish your experiment in Dynamics 365 Commerce after you've [connected your experiment and edited your variations](experimentation-connect-edit.md).</span></span> <span data-ttu-id="d577e-105">A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó kísérletet lehet létrehozni és futtatni a Dynamics 365 Commerce rendszerben.</span><span class="sxs-lookup"><span data-stu-id="d577e-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="d577e-106">A további lépések külön témákban szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="d577e-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="d577e-107">[ ![Kísérletezés felhasználói interakciósorozata – Előnézet és közzététel](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d577e-107">[ ![Experimentation user journey - Preview & Publish](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span></span>

## <a name="preview-your-experiment-variations"></a><span data-ttu-id="d577e-108">A kísérletek változatainak előnézete</span><span class="sxs-lookup"><span data-stu-id="d577e-108">Preview your experiment variations</span></span>
<span data-ttu-id="d577e-109">Megtekintheti a változatokat, és folytathatja a szerkesztést egészen addig, amíg azok el nem nyerik a tetszőleges állapotot.</span><span class="sxs-lookup"><span data-stu-id="d577e-109">You can preview your variations and continue editing them until they look the way you want them to.</span></span>

1. <span data-ttu-id="d577e-110">A webhelykészítőben a parancssáv alatti változatok legördülő menü segítségével kiválaszthatja az előnézetben megtekinteni kívánt tartalmat.</span><span class="sxs-lookup"><span data-stu-id="d577e-110">In site builder, use the variations drop-down menu below the command bar to select the content you want to preview.</span></span> 
1. <span data-ttu-id="d577e-111">Válassza ki a felső sávon található **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="d577e-111">Select **Preview** in the top bar.</span></span> <span data-ttu-id="d577e-112">Annak az előnézete, hogy hogyan fog festeni a tartalom a közzététel utáni megjelenítéskor.</span><span class="sxs-lookup"><span data-stu-id="d577e-112">A preview of what the content will look like when it's published is displayed.</span></span>
1. <span data-ttu-id="d577e-113">A különböző változatok előnézetéhez válassza ki az adott elemet a változatok legördülő menüből, majd újból válassza ki az **Előnézet** elemet.</span><span class="sxs-lookup"><span data-stu-id="d577e-113">To preview a different variation, select it from the variation drop-down and select **Preview** again.</span></span>

## <a name="publish-your-experiment"></a><span data-ttu-id="d577e-114">A kísérlet közzététele</span><span class="sxs-lookup"><span data-stu-id="d577e-114">Publish your experiment</span></span>
<span data-ttu-id="d577e-115">Ha nem használ közzétételi csoportot annak ütemezéséhez, hogy mikor lépjen életbe a kísérlet, és azonnali közzétételt szeretne végezni, akkor a **Közzététel** parancsot válassza ki a parancssorban.</span><span class="sxs-lookup"><span data-stu-id="d577e-115">If you aren't using a publish group to schedule when your experiment goes live and you want to publish immediately, select **Publish** in the command bar.</span></span> <span data-ttu-id="d577e-116">A program az összes, a kísérlethez tartozó változatot közzéteszi.</span><span class="sxs-lookup"><span data-stu-id="d577e-116">All variations that belong to the experiment will be published.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="d577e-117">Ha az oldal nem közzétett URL-címmel rendelkezik, akkor először közzé kell tennie az URL-címet, ellenkező esetben nem lesz látható a webhely felhasználói számára.</span><span class="sxs-lookup"><span data-stu-id="d577e-117">If the page has an unpublished URL, you must first publish the URL or it won't be visible to your website users.</span></span> <span data-ttu-id="d577e-118">A részletekért lásd: [Oldal mentése, előnézete és közzététele](save-preview-publish-page.md).</span><span class="sxs-lookup"><span data-stu-id="d577e-118">For details, see [Save, preview, and publish a page](save-preview-publish-page.md).</span></span>
    
### <a name="use-publish-groups-to-schedule-when-your-experiment-goes-live"></a><span data-ttu-id="d577e-119">A közzétételi csoportokat annak ütemezéséhez használhatja, hogy mikor lépjen életbe a kísérlet.</span><span class="sxs-lookup"><span data-stu-id="d577e-119">Use publish groups to schedule when your experiment goes live</span></span>
<span data-ttu-id="d577e-120">A webhelykészítőben létrehozott változatok közzététele egy közzétételi csoport segítségével ütemezhető be.</span><span class="sxs-lookup"><span data-stu-id="d577e-120">Variations created in site builder can be scheduled for publishing by using a publish group.</span></span> <span data-ttu-id="d577e-121">A közzétételi csoporton belül a **Kísérletek** , illetve az **Oldalak** vagy a **Töredékek** fülre kattintva oldalt vagy töredéket kapcsolhat a kísérlethez. További tudnivalókért lásd a [Kísérlet csatlakoztatása és a változatok szerkesztése](experimentation-connect-edit.md) témakört.</span><span class="sxs-lookup"><span data-stu-id="d577e-121">Within a publish group, you can connect a page or fragment to your experiment by going to the **Experiments** tab or the **Pages** or **Fragments** tab. For more information, see [Connect an experiment and edit variations](experimentation-connect-edit.md) topic.</span></span> <span data-ttu-id="d577e-122">A közzétételi csoportokkal kapcsolatos további tudnivalókat lásd: [Munka a közzétételi csoportokkal](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="d577e-122">For information about publish groups, see [Work with publish groups](publish-groups.md).</span></span>

<span data-ttu-id="d577e-123">Ha a kísérletekhez közzétételi csoportokat használ, akkor figyelembe kell vennie néhány fontos szempontot.</span><span class="sxs-lookup"><span data-stu-id="d577e-123">When using publish groups with experiments, there are some important considerations to be aware of.</span></span>
- <span data-ttu-id="d577e-124">Amikor olyan oldalt vagy töredéket ad hozzá egy közzétételi csoporthoz, amelyen egy kísérlet fut, a kísérletet eltávolítja a program a közzétételi csoportban lévő oldalról vagy töredékből.</span><span class="sxs-lookup"><span data-stu-id="d577e-124">When you add a page or fragment that has an experiment running on it to a publish group, the experiment will be removed from the page or fragment in the publish group.</span></span>
- <span data-ttu-id="d577e-125">Az élő webhely oldalaihoz kapcsolódó kísérletek nem érhetők el a közzétételi csoportokon belüli oldalakhoz, és fordítva.</span><span class="sxs-lookup"><span data-stu-id="d577e-125">Experiments that are connected to pages in a live site aren't available to pages within publish groups and vice-versa.</span></span> <span data-ttu-id="d577e-126">Hasonlóképpen az élő webhelyen futó kísérleteket tartalmazó oldalak nem érhetők el a közzétételi csoportok egyéb kísérleteihez, és fordítva.</span><span class="sxs-lookup"><span data-stu-id="d577e-126">Similarly, pages that have experiments running on them in a live site aren't available to other experiments in publish groups and vice versa.</span></span>
- <span data-ttu-id="d577e-127">Közzétételi csoport közzététele vagy ütemezése során a közzétételi csoport minden tartalmát közzéteszi a program, függetlenül attól, hogy van-e a közzétételi csoporthoz kapcsolt kísérlet.</span><span class="sxs-lookup"><span data-stu-id="d577e-127">When you publish or schedule a publish group, all content in the publish group is published, regardless of whether there's an experiment associated with the publish group.</span></span>
- <span data-ttu-id="d577e-128">Mivel a közzétételi csoport azt követően is létezik, hogy élő webhelyen közzétették, a közzétételi csoport kísérletei is megmaradnak.</span><span class="sxs-lookup"><span data-stu-id="d577e-128">Because a publish group continues to persist after it's been published to a live site, experiments in the publish group will also persist.</span></span> <span data-ttu-id="d577e-129">Emiatt más kísérleteket nem lehet ugyanazzal az oldalhoz vagy töredékhez társítani.</span><span class="sxs-lookup"><span data-stu-id="d577e-129">Therefore, you won't be able to associate other experiments with the same page or fragment.</span></span> <span data-ttu-id="d577e-130">E korlátozás elkerülése érdekében törölje a megmaradó kísérletekkel rendelkező közzétételi csoportokat.</span><span class="sxs-lookup"><span data-stu-id="d577e-130">To avoid this limitation, delete any publish groups with persisting experiments.</span></span> <span data-ttu-id="d577e-131">Hasonlóképpen, ha törölni szeretne egy olyan kísérletet egy élő webhelyről, amely a közzétételi csoportban is szerepel, akkor először törölje azt a közzétételi csoportból.</span><span class="sxs-lookup"><span data-stu-id="d577e-131">Similarly, if you want to delete an experiment in a live site that also exists in a publish group, delete it from the publish group first.</span></span>

## <a name="previous-step"></a><span data-ttu-id="d577e-132">Előző lépés</span><span class="sxs-lookup"><span data-stu-id="d577e-132">Previous step</span></span>
[<span data-ttu-id="d577e-133">Kísérlet csatlakoztatása és szerkesztése</span><span class="sxs-lookup"><span data-stu-id="d577e-133">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)

## <a name="next-step"></a><span data-ttu-id="d577e-134">Következő lépés</span><span class="sxs-lookup"><span data-stu-id="d577e-134">Next step</span></span>
[<span data-ttu-id="d577e-135">Kísérlet futtatása és nyomon követése</span><span class="sxs-lookup"><span data-stu-id="d577e-135">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)
