---
title: Töredékek használata
description: Ez a témakör azt mutatja be, miért, hogyan és mikor lehet a töredékeket a Microsoft Dynamics 365 Commerce rendszerben használni.
author: phinneyridge
manager: annbe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3df2d99ef10f909cedef16167fb8d5a0024683b3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210947"
---
# <a name="work-with-fragments"></a><span data-ttu-id="98db0-103">Töredékek használata</span><span class="sxs-lookup"><span data-stu-id="98db0-103">Work with fragments</span></span> 

[!include [banner](includes/banner.md)]

<span data-ttu-id="98db0-104">Ez a témakör azt mutatja be, miért, hogyan és mikor lehet a töredékeket a Microsoft Dynamics 365 Commerce rendszerben használni.</span><span class="sxs-lookup"><span data-stu-id="98db0-104">This topic describes why, when, and how to use fragments in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="98db0-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="98db0-105">Overview</span></span>

<span data-ttu-id="98db0-106">A töredékek lehetővé teszik a modul-konfigurációk központosított szerkesztési élményének létrehozásár, amelyet a webhely minden területén újra fel lehet használni.</span><span class="sxs-lookup"><span data-stu-id="98db0-106">Fragments allow for a centralized authoring experience for module configurations that must be reused throughout your site.</span></span> <span data-ttu-id="98db0-107">Például a fejléceket, élőlábakat és szalagcímeket gyakran töredékként konfigurálják, mivel több oldal megosztva használja azokat.</span><span class="sxs-lookup"><span data-stu-id="98db0-107">For example, headers, footers, and banners are often configured as fragments, because they are shared across many pages.</span></span> <span data-ttu-id="98db0-108">A töredékeket úgy képzelje el, mint kicsiny weboldalakat, amelyek a webhely egyéb oldalaiba illeszthetők be.</span><span class="sxs-lookup"><span data-stu-id="98db0-108">You can think of fragments as miniature webpages that can be inserted into other pages on your site.</span></span> <span data-ttu-id="98db0-109">A töredékek saját életciklussal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="98db0-109">Fragments have their own lifecycle.</span></span> <span data-ttu-id="98db0-110">Más szóval a létrehozásuk, hivatkozásuk, frissítése és törlése független entitásként történik a szerkesztőeszközökben.</span><span class="sxs-lookup"><span data-stu-id="98db0-110">In other words, they are created, referenced, updated, and deleted as independent entities in the authoring tools.</span></span>

<span data-ttu-id="98db0-111">A töredékek konfigurálását követően azok használhatók, ahol modulok használhatók a weboldal struktúrájában.</span><span class="sxs-lookup"><span data-stu-id="98db0-111">After fragments are configured, they can be used wherever modules can be used in your site structure.</span></span> <span data-ttu-id="98db0-112">A töredékekre a lapokon, az elrendezésekben, a sablonokban és más töredékekben is hivatkozni lehet.</span><span class="sxs-lookup"><span data-stu-id="98db0-112">Fragments can be referenced on pages, in layouts, in templates, and in other fragments.</span></span>

> [!NOTE]
> <span data-ttu-id="98db0-113">A töredékek a többi töredéken belül legfeljebb hét szint mélyen ágyazhatók be.</span><span class="sxs-lookup"><span data-stu-id="98db0-113">Fragments can be nested up to seven levels deep inside other fragments.</span></span>

<span data-ttu-id="98db0-114">Például, ha szeretné népszerűsíteni egy szezonális eseményt több oldalon a honlapon, akkor egy töredéket is használhat.</span><span class="sxs-lookup"><span data-stu-id="98db0-114">For example, if you want to promote a seasonal event cross many pages on our site, you can use a fragment.</span></span> <span data-ttu-id="98db0-115">Az új töredékek létrehozási folyamatának első lépése a kiinduló modul típusának kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="98db0-115">The first step in the process of creating a new fragment is to select the type of module that you want to start from.</span></span> <span data-ttu-id="98db0-116">Ebben a példában egy hős modulból hozhat létre egy töredéket.</span><span class="sxs-lookup"><span data-stu-id="98db0-116">For this example, you can build the fragment from a hero module.</span></span>

> [!NOTE]
> <span data-ttu-id="98db0-117">A töredékeket bármilyen típusú modulból fel lehet építeni.</span><span class="sxs-lookup"><span data-stu-id="98db0-117">Fragments can be built from any module type.</span></span>

<span data-ttu-id="98db0-118">Ezt követően a hős töredéket konfigurálhatja az adott promóciós tartalommal.</span><span class="sxs-lookup"><span data-stu-id="98db0-118">You can then configure the hero fragment with your specific promotional content.</span></span> <span data-ttu-id="98db0-119">Igény szerint lokalizálhatja is azt.</span><span class="sxs-lookup"><span data-stu-id="98db0-119">You can also localize it as you require.</span></span> <span data-ttu-id="98db0-120">Ezt követően az új, önálló hős töredéket egy előre konfigurált modulként lehet használni a webhelyen.</span><span class="sxs-lookup"><span data-stu-id="98db0-120">The new stand-alone hero fragment can then be consumed as a preconfigured module throughout your site.</span></span> <span data-ttu-id="98db0-121">Egyszerűen hozzáadhatja azt sablonokhoz meghatározott oldalakhoz illetve a hero modulokat tartalmazó más töredékekhez.</span><span class="sxs-lookup"><span data-stu-id="98db0-121">You can easily add it to templates, to specific pages, or to other fragments that can contain hero modules.</span></span>

<span data-ttu-id="98db0-122">Minden olyan hely, ahová a töredéket hozzáadták, a létrehozott központi hős-töredékre hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="98db0-122">All the places where the fragment is added are references to the central hero fragment that you created.</span></span> <span data-ttu-id="98db0-123">Ha a töredékekhez módosításokat tesz közzé, akkor ezek a módosítások azonnal megjelennek az összes olyan helyen, ahol a töredékre hivatkoznak a webhelyen.</span><span class="sxs-lookup"><span data-stu-id="98db0-123">If you publish changes to the fragment, those changes are immediately reflected in all the places where the fragment is referenced across the site.</span></span> <span data-ttu-id="98db0-124">Ennek megfelelően a töredékek hatékony módszert biztosítanak a webhely modul-konfigurációinak újrahasznosításához és központi kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="98db0-124">Therefore, fragments provide a powerful and efficient way to reuse and centrally manage module configurations on a site.</span></span> <span data-ttu-id="98db0-125">A hatékony használat révén jelentősen növelheti az agilitást, és csökkentheti a webhely tartalomkezelésének költségeit.</span><span class="sxs-lookup"><span data-stu-id="98db0-125">By effectively using them, you can significantly increase agility and help reduce the cost that is associated with managing site content.</span></span>

<span data-ttu-id="98db0-126">A következő ábra bemutatja, hogy hogyan használhatók a töredékek a megosztott modul-konfigurációk létrehozásához egy e-kereskedelmi webhely szintjén.</span><span class="sxs-lookup"><span data-stu-id="98db0-126">The following illustration shows how fragments can be used to centralize authoring of shared module configurations across an e-Commerce site.</span></span>

![Egy ábra bemutatja, hogy hogyan használhatók a töredékek a megosztott modul-konfigurációk létrehozásához egy e-kereskedelmi webhely szintjén.](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a><span data-ttu-id="98db0-128">Töredék létrehozása</span><span class="sxs-lookup"><span data-stu-id="98db0-128">Create a fragment</span></span>

<span data-ttu-id="98db0-129">Létrehozhat új töredéket hozhat, illetve egy meglévő modul konfigurációját mentheti töredékként.</span><span class="sxs-lookup"><span data-stu-id="98db0-129">You can either create a new fragment or save an existing module configuration as a fragment.</span></span>

### <a name="save-an-existing-module-configuration-as-a-fragment"></a><span data-ttu-id="98db0-130">Meglévő modulkonfiguráció mentése töredékként</span><span class="sxs-lookup"><span data-stu-id="98db0-130">Save an existing module configuration as a fragment</span></span>

<span data-ttu-id="98db0-131">Ha egy korábban konfigurált modult újra felhasználható töredékké szeretne átalakítani a Commerce webhelykészítőben, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="98db0-131">To convert a previously configured module to a reusable fragment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="98db0-132">Nyisson meg egy olyan lapot vagy sablont, amely a töredékké alakítandó modult tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="98db0-132">Open a page or template that contains the module that you want to convert to a fragment.</span></span>
1. <span data-ttu-id="98db0-133">A bal oldali vázlat ablaktáblán vagy közvetlenül a vizuális oldalkészítőben, válassza ki az előzőleg konfigurált modult.</span><span class="sxs-lookup"><span data-stu-id="98db0-133">In the outline pane on the left or directly in visual page builder, select the previously configured module.</span></span>
1. <span data-ttu-id="98db0-134">Válassza ki a modul neve mellett lévő azt a három pont (**...**) a vázlat ablaktáblán vagy a kiválasztott modul eszköztárában, a vizuális oldalkészítőben.</span><span class="sxs-lookup"><span data-stu-id="98db0-134">Select the ellipsis (**...**) next to the name of the module in either the outline pane or the selected module's toolbar in visual page builder.</span></span> 
1. <span data-ttu-id="98db0-135">Válassza ki a **Megosztást töredékként** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98db0-135">Select **Share as fragment**.</span></span> 
1. <span data-ttu-id="98db0-136">A **Mentés töredékként** párbeszédpanelen adjon nevet a töredéknek.</span><span class="sxs-lookup"><span data-stu-id="98db0-136">In the **Save as fragment** dialog box, enter a name for the fragment.</span></span>
1. <span data-ttu-id="98db0-137">Az **OK** gombra kattintva mentheti a modulkonfigurációt olyan töredékként, amely más lapokhoz is hozzáadható.</span><span class="sxs-lookup"><span data-stu-id="98db0-137">Select **OK** to save the module configuration as a fragment that can be added to other pages.</span></span>
<!-- The following image shows how to save a module configuration as a fragment.-->
<!--![A screen capture of how to save a module configuration as a fragment](./media/save-as-fragment.png)-->

### <a name="create-a-new-fragment"></a><span data-ttu-id="98db0-138">Új töredék létrehozása</span><span class="sxs-lookup"><span data-stu-id="98db0-138">Create a new fragment</span></span>

<span data-ttu-id="98db0-139">A következő lépésekkel hozhat létre új töredéket a Commerce webhelykészítőben.</span><span class="sxs-lookup"><span data-stu-id="98db0-139">To create a new fragment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="98db0-140">A bal oldali navigációs ablakban válassza ki a **Töredékek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98db0-140">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="98db0-141">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98db0-141">Select **New**.</span></span> <span data-ttu-id="98db0-142">Megjelenik az **Új töredék** párbeszédpanel, amelyen az összes elérhető modultípus látható.</span><span class="sxs-lookup"><span data-stu-id="98db0-142">A **New fragment** dialog box appears that shows all the available module types.</span></span> <span data-ttu-id="98db0-143">A korábban említetteknek megfelelően a töredékek bármilyen típusú modulból létrehozhatók.</span><span class="sxs-lookup"><span data-stu-id="98db0-143">As was mentioned earlier, fragments can be created from any module type.</span></span>
1. <span data-ttu-id="98db0-144">A modul típusának kiválasztása a töredékhez.</span><span class="sxs-lookup"><span data-stu-id="98db0-144">Select a module type for your fragment.</span></span>

<!-- The following image shows where to create a new fragment.-->
<!-- ![A screen capture of where to create a new fragment](./media/fragment-nav-menu.png)-->
> [!TIP]
> <span data-ttu-id="98db0-145">Egy általános tárolómodul-típus kiválasztásával a legrugalmasabban frissítheti és konfigurálhatja a töredéket később.</span><span class="sxs-lookup"><span data-stu-id="98db0-145">By selecting a generic container module type, you get the most flexibility when you need to update and configure your fragment later.</span></span>

## <a name="add-remove-or-edit-fragments-on-a-page"></a><span data-ttu-id="98db0-146">Töredékek hozzáadása, eltávolítása vagy szerkesztése egy lapon</span><span class="sxs-lookup"><span data-stu-id="98db0-146">Add, remove, or edit fragments on a page</span></span>

<span data-ttu-id="98db0-147">A következő eljárások leírják a töredékek hozzáadását, eltávolítását és szerkesztését.</span><span class="sxs-lookup"><span data-stu-id="98db0-147">The following procedures describe how to add, remove, and edit fragments.</span></span>

### <a name="add-a-fragment"></a><span data-ttu-id="98db0-148">Töredék hozzáadása</span><span class="sxs-lookup"><span data-stu-id="98db0-148">Add a fragment</span></span>

<span data-ttu-id="98db0-149">A következő lépésekkel adhat hozzá új töredéket egy oldalhoz a Commerce webhelykészítőben.</span><span class="sxs-lookup"><span data-stu-id="98db0-149">To add a fragment to a page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="98db0-150">A bal oldali vázlat ablaktáblán vagy közvetlenül a vizuális oldalkészítőben, válassza ki azt a tárolót vagy helyet, amelyhez hozzá szeretné adni a származtatott modulokat.</span><span class="sxs-lookup"><span data-stu-id="98db0-150">In the outline pane on the left or directly in visual page builder, select a container or slot to which child modules can be added.</span></span>
1. <span data-ttu-id="98db0-151">Válassza ki a tároló vagy a hely neve melletti három pontot (**...**).</span><span class="sxs-lookup"><span data-stu-id="98db0-151">Select the ellipsis (**...**) next to the name of the container or slot.</span></span>  <span data-ttu-id="98db0-152">Másik lehetőségként, ha a vizuális oldalkészítőt használja, válassza ki a pluszjelet (**+**).</span><span class="sxs-lookup"><span data-stu-id="98db0-152">Alternately, if using visual page builder, select the plus symbol (**+**).</span></span>  
1. <span data-ttu-id="98db0-153">Válassza a **Töredék hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98db0-153">Select **Add fragment**.</span></span>
    <!-- ![A screen capture of how to add an existing fragment to a slot or container](./media/add-fragment.png)-->
 
    > [!NOTE]
    > <span data-ttu-id="98db0-154">Ha a tároló vagy a bővítőhely nem támogatja az új származtatott modulokat, akkor a **Töredék hozzáadása** lehetőség nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="98db0-154">If the container or slot doesn't support new child modules, the **Add fragment** option is unavailable.</span></span>
    
1. <span data-ttu-id="98db0-155">A **Töredék kiválasztása** párbeszédpanelen keressen meg és válasszon ki egy töredéket a hozzáadáshoz.</span><span class="sxs-lookup"><span data-stu-id="98db0-155">In the **Select fragment** dialog box, search for and select a fragment to add.</span></span> <span data-ttu-id="98db0-156">Ha nincs elérhető töredék a listán, először létre kell hozni egy töredéket egy olyan modultípusból, amelyet a kiválasztott tároló vagy bővítőhely támogat.</span><span class="sxs-lookup"><span data-stu-id="98db0-156">If no available fragments are listed, you might first have to create a fragment from a module type that the selected container or slot supports.</span></span>
1. <span data-ttu-id="98db0-157">Válassza ki és adja hozzá a kívánt töredéket a tárolóhoz vagy helyhez a lapon.</span><span class="sxs-lookup"><span data-stu-id="98db0-157">Select your desired fragment to add it to the container or slot on your page.</span></span>
<!--    ![A screen capture of the fragment picker modal window](./media/fragment-picker.png)-->

> [!NOTE]
> <span data-ttu-id="98db0-158">A tárolókban vagy bővítőhelyekben engedélyezett modulokat a lapsablonja vagy a modulok saját definíciói határozzák meg.</span><span class="sxs-lookup"><span data-stu-id="98db0-158">The modules that are allowed in a container or slot are defined by the page's template or the modules' own definitions.</span></span>

### <a name="remove-a-fragment"></a><span data-ttu-id="98db0-159">Töredék eltávolítása</span><span class="sxs-lookup"><span data-stu-id="98db0-159">Remove a fragment</span></span>

<span data-ttu-id="98db0-160">A Commerce webhelykészítő egy lapján lévő bővítőhelyen vagy tárolóban levő töredék eltávolításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="98db0-160">To remove a fragment from a slot or container on a page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="98db0-161">A bal oldali vázlat ablaktáblán válassza az eltávolítani kívánt töredék neve melletti három pontot (**...**), majd válassza a kuka gombját.</span><span class="sxs-lookup"><span data-stu-id="98db0-161">In the outline pane on the left, select the ellipsis (**...**) next to the name of the fragment to be removed, and then select the trash can symbol.</span></span>  <span data-ttu-id="98db0-162">Másik lehetőségként kiválaszthatja a töredéket a vizuális oldalkészítőben, és kiválaszthatja a kuka lehetőséget a töredék eszköztárában.</span><span class="sxs-lookup"><span data-stu-id="98db0-162">Alternately, you can select the fragment in visual page builder and select the trash can symbol in the fragment's toolbar.</span></span>
1. <span data-ttu-id="98db0-163">Amikor a program megkérdezi, hogy szeretné-e eltávolítani a töredéket, válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98db0-163">When you're prompted to confirm that you want to remove the fragment, select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="98db0-164">Ha eltávolít egy töredéket egy lapról, akkor csak az adott oldalról távolítja el a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="98db0-164">When you remove a fragment from a page, you just remove the reference to it from that page.</span></span> <span data-ttu-id="98db0-165">**Nem** törli a töredéket az oldalról.</span><span class="sxs-lookup"><span data-stu-id="98db0-165">You do **not** delete the fragment from your site.</span></span> <span data-ttu-id="98db0-166">Ha törölni szeretne egy töredékeket a webhelyről, akkor a töredékvizsgáló felhasználói felülteét kell használnia.</span><span class="sxs-lookup"><span data-stu-id="98db0-166">To delete fragments from your site, you must use the fragment inspector user interface (UI).</span></span> <span data-ttu-id="98db0-167">A webhely töredékeit csak akkor törölheti, ha a lapok, sablonok vagy más töredékek jelenleg nem hivatkoznak rájuk.</span><span class="sxs-lookup"><span data-stu-id="98db0-167">You can delete fragments from a site only if they aren't currently referenced by any pages, templates, or other fragments.</span></span>

### <a name="edit-a-fragment"></a><span data-ttu-id="98db0-168">Töredék szerkesztése</span><span class="sxs-lookup"><span data-stu-id="98db0-168">Edit a fragment</span></span>

<span data-ttu-id="98db0-169">A töredékek szerkesztéséhez a töredék-szerkesztő felhasználói felületét kell használnia.</span><span class="sxs-lookup"><span data-stu-id="98db0-169">To edit fragments, you must use the fragment editor UI.</span></span> <span data-ttu-id="98db0-170">Ez korlátozás szándékos.</span><span class="sxs-lookup"><span data-stu-id="98db0-170">This restriction is by design.</span></span> <span data-ttu-id="98db0-171">Ez segít szavatolni, hogy a szerzők nem tévesztik össze a modulok szerkesztési folyamatát a több lapon megosztott töredékek szerkesztési folyamatával.</span><span class="sxs-lookup"><span data-stu-id="98db0-171">It helps guarantee that authors don't confuse the process of editing the modules for a specific page with the process of editing fragments that might be shared across many pages.</span></span>

<span data-ttu-id="98db0-172">A következő lépésekkel szerkeszthet új töredéket a Commerce webhelykészítőben.</span><span class="sxs-lookup"><span data-stu-id="98db0-172">To edit a fragment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="98db0-173">A bal oldali navigációs ablakban válassza ki a **Töredékek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="98db0-173">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="98db0-174">A **Töredékek** alatt válassza ki a szerkeszteni kívánt töredéket.</span><span class="sxs-lookup"><span data-stu-id="98db0-174">Under **Fragments**, select the fragment to edit.</span></span>
1. <span data-ttu-id="98db0-175">Igény szerint szerkesztheti a töredék moduljának jellemzőit és szerkezetét.</span><span class="sxs-lookup"><span data-stu-id="98db0-175">Edit the fragment's module properties and structure as you require.</span></span> <span data-ttu-id="98db0-176">A folyamat hasonló a modulok szerkesztési folyamataihoz a lap szerkesztőnézetében.</span><span class="sxs-lookup"><span data-stu-id="98db0-176">The process resembles the process for editing modules are edited in the page editor view.</span></span>

<span data-ttu-id="98db0-177">A töredékeket úgy is szerkesztheti, hogy kijelöli azt egy lapon, egy sablonban vagy egy szülő töredékben, majd a jobb oldali Tulajdonságok ablaktáblában kiválasztja a **Töredék szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="98db0-177">You can also edit a fragment by selecting it on a page, in a template, or in a parent fragment, and then selecting **Edit Fragment** in the properties pane on the right.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="98db0-178">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="98db0-178">Additional resources</span></span>

[<span data-ttu-id="98db0-179">Sablonok és elrendezések áttekintése</span><span class="sxs-lookup"><span data-stu-id="98db0-179">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="98db0-180">Sablonok használata</span><span class="sxs-lookup"><span data-stu-id="98db0-180">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="98db0-181">Előre beállított elrendezések használata</span><span class="sxs-lookup"><span data-stu-id="98db0-181">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="98db0-182">A közzétételi csoportokkal végzett munka</span><span class="sxs-lookup"><span data-stu-id="98db0-182">Work with publish groups</span></span>](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]