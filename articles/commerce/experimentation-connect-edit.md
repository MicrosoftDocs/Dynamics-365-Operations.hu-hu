---
title: Kísérlet csatlakoztatása és változatok szerkesztése
description: Ez a témakör azt mutatja be, hogyan lehet egy külső szolgáltatásból származó kísérletet csatlakoztatni a Dynamics 365 Commerce rendszerhez, illetve hogyan lehet szerkeszteni a kísérlet változatait.
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
ms.openlocfilehash: 030640ba8907ae52c198ac96ad2c243b533d8c53
ms.sourcegitcommit: cd83f2bc0e52e13071ad306e07e4c255fc65cb03
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/22/2020
ms.locfileid: "4413002"
---
# <a name="connect-an-experiment-and-edit-variations"></a><span data-ttu-id="4603a-103">Kísérlet csatlakoztatása és változatok szerkesztése</span><span class="sxs-lookup"><span data-stu-id="4603a-103">Connect an experiment and edit variations</span></span>

<span data-ttu-id="4603a-104">Ez a témakör azt mutatja be, kísérletét hogyan csatlakoztathatja a Commerce modulban, illetve hogyan módosíthatja az egyes változatokat úgy, hogy azok egybevágjanak a hipotézisével.</span><span class="sxs-lookup"><span data-stu-id="4603a-104">This topic describes how to connect your experiment in Commerce and make changes to your variations so that they align with your hypothesis.</span></span> 

<span data-ttu-id="4603a-105">A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó kísérletet lehet létrehozni és futtatni a Dynamics 365 Commerce rendszerben.</span><span class="sxs-lookup"><span data-stu-id="4603a-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="4603a-106">A további lépések külön témákban szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="4603a-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="4603a-107">[![Kísérletezés felhasználói interakciósorozata – Csatlakoztatás és szerkesztés](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="4603a-107">[ ![Experimentation user journey - Connect & Edit](./media/experimentation_connect_edit.svg) ](./media/experimentation_connect_edit.svg#lightbox)</span></span>

<span data-ttu-id="4603a-108">Miután a [kísérletet beállította](experimentation-setup.md) egy harmadik fél szolgáltatásban, csatlakoztathatja a kísérletet a Dynamics 365 Commerce rendszerben, és szerkesztheti a kísérlet változatait.</span><span class="sxs-lookup"><span data-stu-id="4603a-108">After you've [set up your experiment](experimentation-setup.md) in a third-party service, you'll connect the experiment in Dynamics 365 Commerce and edit the experiment variations.</span></span>

## <a name="planning-considerations"></a><span data-ttu-id="4603a-109">Tervezési szempontok</span><span class="sxs-lookup"><span data-stu-id="4603a-109">Planning considerations</span></span>

<span data-ttu-id="4603a-110">Mielőtt a kísérletet a Commerce modulban csatlakoztatja, el kell döntenie, hogy milyen módon kezelje a Commerce a tartalmat.</span><span class="sxs-lookup"><span data-stu-id="4603a-110">Before you connect your experiment in Commerce, you'll need to make some decisions that impact the way Commerce manages your content.</span></span>

### <a name="determine-the-scope-of-your-experiment"></a><span data-ttu-id="4603a-111">A kísérlet hatókörének meghatározása</span><span class="sxs-lookup"><span data-stu-id="4603a-111">Determine the scope of your experiment</span></span>
<span data-ttu-id="4603a-112">Amikor egy kísérletet csatlakoztat, a program felkéri arra, hogy határozza meg a kísérlet hatókörét.</span><span class="sxs-lookup"><span data-stu-id="4603a-112">When you connect an experiment, you are prompted to define the scope of the experiment.</span></span> <span data-ttu-id="4603a-113">A kísérletek rendelkezhetnek **részleges** vagy **teljes** hatókörrel.</span><span class="sxs-lookup"><span data-stu-id="4603a-113">Experiments are defined as **partial** scope or **entire** scope.</span></span>
- <span data-ttu-id="4603a-114">A **részleges** lehetőséget akkor válassza, ha a kísérletet egy oldal meghatározott részén kívánja végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="4603a-114">Choose **partial** if you want to conduct an experiment on a specific portion of a page.</span></span> <span data-ttu-id="4603a-115">Ha ezt a lehetőséget választja, akkor meg kell adnia, hogy mely modulok szerepeljenek a kísérletben.</span><span class="sxs-lookup"><span data-stu-id="4603a-115">If you select this option, you must identify which modules are included in the experiment.</span></span> <span data-ttu-id="4603a-116">Az alapértelmezett oldal vagy töredék azon részein végrehajtott változtatások, amelyek nem kapcsolódnak a kísérlethez, automatikusan szinkronizáltak lesznek a változatok között.</span><span class="sxs-lookup"><span data-stu-id="4603a-116">Changes that are made to parts of the default page or fragment that aren't related to the experiment are automatically synchronized across variations.</span></span>
- <span data-ttu-id="4603a-117">A **teljes** lehetőséget akkor válassza, ha egy teljes oldalon vagy töredéken szeretne kísérletet végezni.</span><span class="sxs-lookup"><span data-stu-id="4603a-117">Choose **entire** if you want to conduct an experiment on an entire page or fragment.</span></span> <span data-ttu-id="4603a-118">Az alapértelmezett oldal vagy töredék külön példányai jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="4603a-118">Separate copies of the default page or fragment are created.</span></span> <span data-ttu-id="4603a-119">Azt nem kell kiválasztania, hogy mely modulok kerüljenek a kísérletbe, mivel a szerkesztési felület egésze módosítható.</span><span class="sxs-lookup"><span data-stu-id="4603a-119">You won't have to select which modules are included in the experiment because the whole editing surface is available to change.</span></span> <span data-ttu-id="4603a-120">Szükség szerint modulokat adhat hozzá, törölhet vagy rendelhet újra.</span><span class="sxs-lookup"><span data-stu-id="4603a-120">You can add, delete, or re-order modules as needed.</span></span> <span data-ttu-id="4603a-121">Ha azonban a kísérlethez társított alapértelmezett oldalon vagy töredékben módosítások történnek, akkor ezeket a módosításokat manuálisan kell szinkronizálni a változatok között.</span><span class="sxs-lookup"><span data-stu-id="4603a-121">However, if any changes are made to the default page or fragment that the experiment is associated with, those changes have to be manually synchronized across all variations.</span></span>

<!-- not to editors, we're adding an image here to illustrate the difference. it will help.) -->

> [!NOTE]
> <span data-ttu-id="4603a-122">Ha egy elrendezést használó oldalhoz társítja a kísérletet, akkor a kísérlet hatóköre csak **egészre** állítható.</span><span class="sxs-lookup"><span data-stu-id="4603a-122">If you associate your experiment with a page that uses a layout, you can only scope the experiment as **entire**.</span></span>

### <a name="decide-if-you-want-to-schedule-when-your-experiment-is-published"></a><span data-ttu-id="4603a-123">Döntse el, hogy a kísérlet közzétételét be kívánja-e ütemezni</span><span class="sxs-lookup"><span data-stu-id="4603a-123">Decide if you want to schedule when your experiment is published</span></span>
<span data-ttu-id="4603a-124">Ha szeretné beütemezni, hogy kísérlete mikor kerüljön ki az élő webhelyre, akkor ellenőrizze, hogy a kísérlethez társítani kívánt tartalom elérhető-e egy közzétételi csoportban, még *mielőtt* csatlakoztatná a kísérletet.</span><span class="sxs-lookup"><span data-stu-id="4603a-124">If you want to schedule when your experiment is published to your live site, make sure the content you want to associate with the experiment is available in a publish group *before* you connect the experiment.</span></span> 

<span data-ttu-id="4603a-125">A közzétételi csoportokkal kapcsolatos további tudnivalókat lásd: [Munka a közzétételi csoportokkal](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="4603a-125">For more information about publish groups, refer to [Work with publish groups](publish-groups.md).</span></span>


## <a name="connect-your-experiment"></a><span data-ttu-id="4603a-126">A kísérlet csatlakoztatása</span><span class="sxs-lookup"><span data-stu-id="4603a-126">Connect your experiment</span></span>
<span data-ttu-id="4603a-127">A kísérlet csatlakoztatásához a **Kísérlet csatlakoztatása** varázslót indítsa el.</span><span class="sxs-lookup"><span data-stu-id="4603a-127">To connect your experiment, you'll launch the **Connect experiment** wizard.</span></span> <span data-ttu-id="4603a-128">A varázsló végigvezeti a kísérlet csatlakoztatásához szükséges lépéseken.</span><span class="sxs-lookup"><span data-stu-id="4603a-128">The wizard walks you through the steps required to connect your experiment.</span></span> <span data-ttu-id="4603a-129">Amikor a varázsló végére ér, a kísérlet csatlakoztatottá válik, és a változatok jönnek létre, amelyek készen állnak a szerkesztésre.</span><span class="sxs-lookup"><span data-stu-id="4603a-129">When you complete the wizard, your experiment is connected and variations are created and ready to be edited.</span></span>

<span data-ttu-id="4603a-130">A Commerce webhelykészítőben a kísérlethez történő csatlakozás elkezdéséhez hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="4603a-130">To get started connecting your experiment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="4603a-131">A **Kísérlet csatlakoztatása** varázsló indításához válassza a bal oldali navigációs panel **Kísérletek** elemét, majd a **Csatlakozás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4603a-131">To launch the **Connect experiment** wizard, select **Experiments** in the left navigation pane, and then select **Connect**.</span></span> <span data-ttu-id="4603a-132">Azt is megteheti, hogy a varázslót az oldal vagy a töredék szerkesztőjéből nyitja meg úgy, hogy szerkeszti, és kiválasztja a **Kísérlet csatlakoztatása** elemet a parancssorból.</span><span class="sxs-lookup"><span data-stu-id="4603a-132">Alternatively, you can access the wizard from a page or fragment editor by editing it and selecting **Connect experiment** on the command bar.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4603a-133">Egy oldal egyszerre csak egy kísérlethez kapcsolható.</span><span class="sxs-lookup"><span data-stu-id="4603a-133">A page can only be connected to one experiment at a time.</span></span> <span data-ttu-id="4603a-134">Ha egy másik kísérlethez szeretne egy oldalt csatlakoztatni, először törölje azt a kísérletet, amelyhez az oldal aktuálisan kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="4603a-134">To connect a page to a different experiment, first delete the experiment that the page is currently connected to.</span></span>

1. <span data-ttu-id="4603a-135">Válassza ki azt az oldalt vagy töredéket, amelyen futtatni szeretné a kísérletet.</span><span class="sxs-lookup"><span data-stu-id="4603a-135">Choose the page or fragment you want to run your experiment on.</span></span>
1. <span data-ttu-id="4603a-136">A kísérletezési hatókört **részlegesre** vagy **egészre** kell állítani a fenti [Kísérlet hatókörének meghatározása](#determine-the-scope-of-your-experiment) szakaszban kiválasztott beállítástól függően.</span><span class="sxs-lookup"><span data-stu-id="4603a-136">Set the experimentation scope to **partial** or **entire**, based on the choice you made in the [Determine the scope of your experiment](#determine-the-scope-of-your-experiment) section above.</span></span>
    > [!NOTE]
    > <span data-ttu-id="4603a-137">Ha teljes oldalon vagy töredéken szeretne kísérletezni, akkor engedélyezni kell a **Kísérlet oldalakon vagy töredékeken** zászlót.</span><span class="sxs-lookup"><span data-stu-id="4603a-137">The **Experiment on pages or fragments** feature flag must be enabled if you want to experiment on a full page or fragment.</span></span> <span data-ttu-id="4603a-138">További tudnivalókért lásd a [Kísérletezés a Dynamics 365 Commerce rendszerben](experimentation-overview.md) témakört.</span><span class="sxs-lookup"><span data-stu-id="4603a-138">Refer to the [Experimentation in Dynamics 365 Commerce](experimentation-overview.md) topic for more information.</span></span>
    
1. <span data-ttu-id="4603a-139">A varázsló utolsó lépésében válassza ki a **Változatok létrehozása és kilépés a varázslóból**.</span><span class="sxs-lookup"><span data-stu-id="4603a-139">In the final step of the wizard, select **Generate variations and exit wizard**.</span></span> <span data-ttu-id="4603a-140">A kísérlethez változatok jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="4603a-140">Variations are created for the experiment.</span></span> 

## <a name="edit-your-variations"></a><span data-ttu-id="4603a-141">A változatok szerkesztése</span><span class="sxs-lookup"><span data-stu-id="4603a-141">Edit your variations</span></span>
<span data-ttu-id="4603a-142">A varázslóból való kilépéskor a változatok jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="4603a-142">When you exit the wizard, variations are created for you.</span></span> 

<span data-ttu-id="4603a-143">Ezt követően úgy szerkesztheti a változatokat, hogy azok tükrözzék azokat a választásokat, amelyeket igazolni szeretne a kísérlet hipotézisében.</span><span class="sxs-lookup"><span data-stu-id="4603a-143">Next, you'll edit the variations so they reflect the choices that you need to verify in the experiment hypothesis.</span></span> <span data-ttu-id="4603a-144">Válassza ki a következő eljárások közül azt, amelyik megfelel a kísérlethez a fenti [Kísérlet hatókörének meghatározása](#determine-the-scope-of-your-experiment) szakaszban választott hatókörnek.</span><span class="sxs-lookup"><span data-stu-id="4603a-144">Choose one of following procedures that corresponds to the scope you chose for your experiment in the [Determine the scope of your experiment](#determine-the-scope-of-your-experiment) section above.</span></span>

### <a name="edit-variations-for-experiments-with-partial-scope"></a><span data-ttu-id="4603a-145">Részleges hatókörű kísérletek változatainak szerkesztése</span><span class="sxs-lookup"><span data-stu-id="4603a-145">Edit variations for experiments with partial scope</span></span>
<span data-ttu-id="4603a-146">Ha a **Kísérlet csatlakoztatása** varázslóban a kísérlet hatókörét **részlegesre** állította, akkor a következő lépéseket hajtsa végre.</span><span class="sxs-lookup"><span data-stu-id="4603a-146">Follow these steps if you defined the scope of your experiment as **partial** in the **Connect experiment** wizard.</span></span>

1. <span data-ttu-id="4603a-147">A szerkesztő nézetben a parancssor alatt található változatok legördülő menü segítségével szerkessze az egyes változatokat az eredeti hipotézisének megfelelően.</span><span class="sxs-lookup"><span data-stu-id="4603a-147">In editor view, use the variations drop-down menu below the command bar to edit each variation based on your original hypothesis.</span></span> <span data-ttu-id="4603a-148">Egy ellenőrző- vagy alapváltozatot is létre lehet hozni úgy, hogy a változatok valamelyikét változatlanul hagyja.</span><span class="sxs-lookup"><span data-stu-id="4603a-148">You may also want to establish a control or base variation by leaving one of the variations unchanged.</span></span>
1. <span data-ttu-id="4603a-149">Válassza ki azt a modult, amelyen a kísérletet el szeretné végezni, aztán a kipontozást (...) és a **Kísérlet hozzáadása** elemet válassza ki.</span><span class="sxs-lookup"><span data-stu-id="4603a-149">Select the module to be experimented on, select the ellipsis (...), and then select **Add to experiment**.</span></span>

### <a name="edit-variations-for-experiments-with-entire-scope"></a><span data-ttu-id="4603a-150">Teljes hatókörű kísérletek változatainak szerkesztése</span><span class="sxs-lookup"><span data-stu-id="4603a-150">Edit variations for experiments with entire scope</span></span>
<span data-ttu-id="4603a-151">Ha a kísérlethez **teljes** hatókört állított be a **Kísérlet csatlakoztatása** varázslóban, akkor szerkesztő nézetben a parancssor alatti változatok legördülő menü segítségével szerkessze az egyes változatokat az eredeti hipotézisének megfelelően.</span><span class="sxs-lookup"><span data-stu-id="4603a-151">If you defined the scope of your experiment as **entire** in the **Connect experiment** wizard, while in editor view, use the variations drop-down menu below the command bar to edit each variation based on your original hypothesis.</span></span> 

> [!NOTE]
> <span data-ttu-id="4603a-152">Mindkét esetben létrehozhat egy ellenőrző- vagy alapváltozatot úgy, hogy a változatok valamelyikét változatlanul hagyja.</span><span class="sxs-lookup"><span data-stu-id="4603a-152">In either case, you may also want to establish a control or base variation by leaving one of the variations unchanged.</span></span>

## <a name="previous-step"></a><span data-ttu-id="4603a-153">Előző lépés</span><span class="sxs-lookup"><span data-stu-id="4603a-153">Previous step</span></span>
[<span data-ttu-id="4603a-154">Kísérlet beállítása</span><span class="sxs-lookup"><span data-stu-id="4603a-154">Set up an experiment</span></span>](experimentation-setup.md) 


## <a name="next-step"></a><span data-ttu-id="4603a-155">Következő lépés</span><span class="sxs-lookup"><span data-stu-id="4603a-155">Next step</span></span>
[<span data-ttu-id="4603a-156">Kísérlet előnézetének megtekintése és közzététele</span><span class="sxs-lookup"><span data-stu-id="4603a-156">Preview and publish an experiment</span></span>](experimentation-preview-publish.md)
