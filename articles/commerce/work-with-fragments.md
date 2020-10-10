---
title: Töredékek használata
description: Ez a témakör azt mutatja be, miért, hogyan és mikor lehet a töredékeket a Microsoft Dynamics 365 Commerce rendszerben használni.
author: phinneyridge
manager: annbe
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: retail
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 671caf1feeb7ac9e7d5a166c5de12540ab9b9792
ms.sourcegitcommit: 97ceb24f191161ca601e0889a539df665834ac3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/16/2020
ms.locfileid: "3818350"
---
# <a name="work-with-fragments"></a><span data-ttu-id="21bd9-103">Töredékek használata</span><span class="sxs-lookup"><span data-stu-id="21bd9-103">Work with fragments</span></span> 

[!include [banner](includes/banner.md)]

<span data-ttu-id="21bd9-104">Ez a témakör azt mutatja be, miért, hogyan és mikor lehet a töredékeket a Microsoft Dynamics 365 Commerce rendszerben használni.</span><span class="sxs-lookup"><span data-stu-id="21bd9-104">This topic describes why, when, and how to use fragments in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="21bd9-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="21bd9-105">Overview</span></span>

<span data-ttu-id="21bd9-106">A töredékek lehetővé teszik a modul-konfigurációk központosított szerkesztési élményének létrehozásár, amelyet a webhely minden területén újra fel lehet használni.</span><span class="sxs-lookup"><span data-stu-id="21bd9-106">Fragments allow for a centralized authoring experience for module configurations that must be reused throughout your site.</span></span> <span data-ttu-id="21bd9-107">Például a fejléceket, élőlábakat és szalagcímeket gyakran töredékként konfigurálják, mivel több oldal megosztva használja azokat.</span><span class="sxs-lookup"><span data-stu-id="21bd9-107">For example, headers, footers, and banners are often configured as fragments, because they are shared across many pages.</span></span> <span data-ttu-id="21bd9-108">A töredékeket úgy képzelje el, mint kicsiny weboldalakat, amelyek a webhely egyéb oldalaiba illeszthetők be.</span><span class="sxs-lookup"><span data-stu-id="21bd9-108">You can think of fragments as miniature webpages that can be inserted into other pages on your site.</span></span> <span data-ttu-id="21bd9-109">A töredékek saját életciklussal rendelkeznek.</span><span class="sxs-lookup"><span data-stu-id="21bd9-109">Fragments have their own lifecycle.</span></span> <span data-ttu-id="21bd9-110">Más szóval a létrehozásuk, hivatkozásuk, frissítése és törlése független entitásként történik a szerkesztőeszközökben.</span><span class="sxs-lookup"><span data-stu-id="21bd9-110">In other words, they are created, referenced, updated, and deleted as independent entities in the authoring tools.</span></span>

<span data-ttu-id="21bd9-111">A töredékek konfigurálását követően azok használhatók, ahol modulok használhatók a weboldal struktúrájában.</span><span class="sxs-lookup"><span data-stu-id="21bd9-111">After fragments are configured, they can be used wherever modules can be used in your site structure.</span></span> <span data-ttu-id="21bd9-112">A töredékekre a lapokon, az elrendezésekben, a sablonokban és más töredékekben is hivatkozni lehet.</span><span class="sxs-lookup"><span data-stu-id="21bd9-112">Fragments can be referenced on pages, in layouts, in templates, and in other fragments.</span></span>

> [!NOTE]
> <span data-ttu-id="21bd9-113">A töredékek a többi töredéken belül legfeljebb hét szint mélyen ágyazhatók be.</span><span class="sxs-lookup"><span data-stu-id="21bd9-113">Fragments can be nested up to seven levels deep inside other fragments.</span></span>

<span data-ttu-id="21bd9-114">Például, ha szeretné népszerűsíteni egy szezonális eseményt több oldalon a honlapon, akkor egy töredéket is használhat.</span><span class="sxs-lookup"><span data-stu-id="21bd9-114">For example, if you want to promote a seasonal event cross many pages on our site, you can use a fragment.</span></span> <span data-ttu-id="21bd9-115">Az új töredékek létrehozási folyamatának első lépése a kiinduló modul típusának kiválasztása.</span><span class="sxs-lookup"><span data-stu-id="21bd9-115">The first step in the process of creating a new fragment is to select the type of module that you want to start from.</span></span> <span data-ttu-id="21bd9-116">Ebben a példában egy hős modulból hozhat létre egy töredéket.</span><span class="sxs-lookup"><span data-stu-id="21bd9-116">For this example, you can build the fragment from a hero module.</span></span>

> [!NOTE]
> <span data-ttu-id="21bd9-117">A töredékeket bármilyen típusú modulból fel lehet építeni.</span><span class="sxs-lookup"><span data-stu-id="21bd9-117">Fragments can be built from any module type.</span></span>

<span data-ttu-id="21bd9-118">Ezt követően a hős töredéket konfigurálhatja az adott promóciós tartalommal.</span><span class="sxs-lookup"><span data-stu-id="21bd9-118">You can then configure the hero fragment with your specific promotional content.</span></span> <span data-ttu-id="21bd9-119">Igény szerint lokalizálhatja is azt.</span><span class="sxs-lookup"><span data-stu-id="21bd9-119">You can also localize it as you require.</span></span> <span data-ttu-id="21bd9-120">Ezt követően az új, önálló hős töredéket egy előre konfigurált modulként lehet használni a webhelyen.</span><span class="sxs-lookup"><span data-stu-id="21bd9-120">The new stand-alone hero fragment can then be consumed as a preconfigured module throughout your site.</span></span> <span data-ttu-id="21bd9-121">Egyszerűen hozzáadhatja azt sablonokhoz meghatározott oldalakhoz illetve a hero modulokat tartalmazó más töredékekhez.</span><span class="sxs-lookup"><span data-stu-id="21bd9-121">You can easily add it to templates, to specific pages, or to other fragments that can contain hero modules.</span></span>

<span data-ttu-id="21bd9-122">Minden olyan hely, ahová a töredéket hozzáadták, a létrehozott központi hős-töredékre hivatkozik.</span><span class="sxs-lookup"><span data-stu-id="21bd9-122">All the places where the fragment is added are references to the central hero fragment that you created.</span></span> <span data-ttu-id="21bd9-123">Ha a töredékekhez módosításokat tesz közzé, akkor ezek a módosítások azonnal megjelennek az összes olyan helyen, ahol a töredékre hivatkoznak a webhelyen.</span><span class="sxs-lookup"><span data-stu-id="21bd9-123">If you publish changes to the fragment, those changes are immediately reflected in all the places where the fragment is referenced across the site.</span></span> <span data-ttu-id="21bd9-124">Ennek megfelelően a töredékek hatékony módszert biztosítanak a webhely modul-konfigurációinak újrahasznosításához és központi kezeléséhez.</span><span class="sxs-lookup"><span data-stu-id="21bd9-124">Therefore, fragments provide a powerful and efficient way to reuse and centrally manage module configurations on a site.</span></span> <span data-ttu-id="21bd9-125">A hatékony használat révén jelentősen növelheti az agilitást, és csökkentheti a webhely tartalomkezelésének költségeit.</span><span class="sxs-lookup"><span data-stu-id="21bd9-125">By effectively using them, you can significantly increase agility and help reduce the cost that is associated with managing site content.</span></span>

<span data-ttu-id="21bd9-126">A következő ábra bemutatja, hogy hogyan használhatók a töredékek a megosztott modul-konfigurációk létrehozásához egy e-kereskedelmi webhely szintjén.</span><span class="sxs-lookup"><span data-stu-id="21bd9-126">The following illustration shows how fragments can be used to centralize authoring of shared module configurations across an e-Commerce site.</span></span>

![Egy ábra bemutatja, hogy hogyan használhatók a töredékek a megosztott modul-konfigurációk létrehozásához egy e-kereskedelmi webhely szintjén.](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a><span data-ttu-id="21bd9-128">Töredék létrehozása</span><span class="sxs-lookup"><span data-stu-id="21bd9-128">Create a fragment</span></span>

<span data-ttu-id="21bd9-129">Létrehozhat új töredéket hozhat, illetve egy meglévő modul konfigurációját mentheti töredékként.</span><span class="sxs-lookup"><span data-stu-id="21bd9-129">You can either create a new fragment or save an existing module configuration as a fragment.</span></span>

### <a name="save-an-existing-module-configuration-as-a-fragment"></a><span data-ttu-id="21bd9-130">Meglévő modulkonfiguráció mentése töredékként</span><span class="sxs-lookup"><span data-stu-id="21bd9-130">Save an existing module configuration as a fragment</span></span>

<span data-ttu-id="21bd9-131">Ha egy korábban konfigurált modult újra felhasználható töredékké szeretne átalakítani, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="21bd9-131">To convert a previously configured module to a reusable fragment, follow these steps.</span></span>

1. <span data-ttu-id="21bd9-132">Nyisson meg egy olyan lapot vagy sablont, amely a töredékké alakítandó modult tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="21bd9-132">Open a page or template that contains the module that you want to convert to a fragment.</span></span>
1. <span data-ttu-id="21bd9-133">A bal oldali vázlat ablaktáblán vagy közvetlenül a fő vásznon, válassza ki az előzőleg konfigurált modult.</span><span class="sxs-lookup"><span data-stu-id="21bd9-133">In the outline pane on the left or directly in the main canvas, select the previously configured module.</span></span>
1. <span data-ttu-id="21bd9-134">Válassza ki a modul neve mellett lévő azt a három pont (**...**) a vázlat ablaktáblán vagy a kiválasztott modul eszköztárában található vásznon.</span><span class="sxs-lookup"><span data-stu-id="21bd9-134">Select the ellipsis (**...**) next to the name of the module in either the outline pane or the selected module's toolbar in the canvas.</span></span> 
1. <span data-ttu-id="21bd9-135">Válassza ki a **Megosztás oldaltöredékként** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="21bd9-135">Select **Share as Page Fragment**.</span></span> 
1. <span data-ttu-id="21bd9-136">A **Mentés oldaltöredékként** párbeszédpanelen adjon nevet a töredéknek.</span><span class="sxs-lookup"><span data-stu-id="21bd9-136">In the **Save as Page Fragment** dialog box, enter a name for the fragment.</span></span>
1. <span data-ttu-id="21bd9-137">Az **OK** gombra kattintva mentheti a modulkonfigurációt olyan töredékként, amely más lapokhoz is hozzáadható.</span><span class="sxs-lookup"><span data-stu-id="21bd9-137">Select **OK** to save the module configuration as a fragment that can be added to other pages.</span></span>

<span data-ttu-id="21bd9-138">A következő kép azt ábrázolja, hogyan kell menteni a modulok konfigurációját töredékként.</span><span class="sxs-lookup"><span data-stu-id="21bd9-138">The following image shows how to save a module configuration as a fragment.</span></span>

![A modulok konfigurációjának töredékként való mentésének képernyőfelvétele](./media/save-as-fragment.png)

### <a name="create-a-new-fragment"></a><span data-ttu-id="21bd9-140">Új töredék létrehozása</span><span class="sxs-lookup"><span data-stu-id="21bd9-140">Create a new fragment</span></span>

<span data-ttu-id="21bd9-141">Új töredék létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="21bd9-141">To create a new fragment, follow these steps.</span></span>

1. <span data-ttu-id="21bd9-142">A bal oldali navigációs ablakban válassza ki a **Töredékek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="21bd9-142">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="21bd9-143">Válassza az **Új oldaltöredék** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="21bd9-143">Select **New Page Fragment**.</span></span> <span data-ttu-id="21bd9-144">Megjelenik egy párbeszédpanel, amelyen az összes elérhető modultípus látható.</span><span class="sxs-lookup"><span data-stu-id="21bd9-144">A dialog box appears that shows all the available module types.</span></span> <span data-ttu-id="21bd9-145">A korábban említetteknek megfelelően a töredékek bármilyen típusú modulból létrehozhatók.</span><span class="sxs-lookup"><span data-stu-id="21bd9-145">As was mentioned earlier, fragments can be created from any module type.</span></span>
1. <span data-ttu-id="21bd9-146">A modul típusának kiválasztása a töredékhez.</span><span class="sxs-lookup"><span data-stu-id="21bd9-146">Select a module type for your fragment.</span></span>

<span data-ttu-id="21bd9-147">A következő kép bemutatja, hogy hol hozzon létre új töredéket.</span><span class="sxs-lookup"><span data-stu-id="21bd9-147">The following image shows where to create a new fragment.</span></span>

![Új töredék létrehozási helyének képernyőfelvétele](./media/fragment-nav-menu.png)

> [!TIP]
> <span data-ttu-id="21bd9-149">Egy általános tárolómodul-típus kiválasztásával a legrugalmasabban frissítheti és konfigurálhatja a töredéket később.</span><span class="sxs-lookup"><span data-stu-id="21bd9-149">By selecting a generic container module type, you get the most flexibility when you need to update and configure your fragment later.</span></span>

## <a name="add-remove-or-edit-fragments-on-a-page"></a><span data-ttu-id="21bd9-150">Töredékek hozzáadása, eltávolítása vagy szerkesztése egy lapon</span><span class="sxs-lookup"><span data-stu-id="21bd9-150">Add, remove, or edit fragments on a page</span></span>

<span data-ttu-id="21bd9-151">A következő eljárások leírják a töredékek hozzáadását, eltávolítását és szerkesztését.</span><span class="sxs-lookup"><span data-stu-id="21bd9-151">The following procedures describe how to add, remove, and edit fragments.</span></span>

### <a name="add-a-fragment"></a><span data-ttu-id="21bd9-152">Töredék hozzáadása</span><span class="sxs-lookup"><span data-stu-id="21bd9-152">Add a fragment</span></span>

<span data-ttu-id="21bd9-153">Töredék hozzáadásához a oldalhoz tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="21bd9-153">To add a fragment to a page, follow these steps.</span></span>

1. <span data-ttu-id="21bd9-154">A bal oldali vázlat ablaktáblán vagy közvetlenül a fő vásznon, válassza ki azt a tárolót vagy helyet, amelyhez hozzá szeretné adni a származtatott modulokat.</span><span class="sxs-lookup"><span data-stu-id="21bd9-154">In the outline pane on the left or directly in the main canvas, select a container or slot to which child modules can be added.</span></span>
1. <span data-ttu-id="21bd9-155">Az online ablaktáblán válassza ki a tároló vagy a hely neve melletti három pontot (**...**).</span><span class="sxs-lookup"><span data-stu-id="21bd9-155">In the online pane, select the ellipsis (**...**) next to the name of the container or slot.</span></span>  <span data-ttu-id="21bd9-156">Másik lehetőségként, ha a fő vásznat használja, válassza ki a plusz jelet (**+**).</span><span class="sxs-lookup"><span data-stu-id="21bd9-156">Alternately, if using the main canvas, select the plus symbol (**+**).</span></span>  
1. <span data-ttu-id="21bd9-157">Válassza a **Töredék hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="21bd9-157">Select **Add Fragment**.</span></span>

    ![A meglévő töredékek bővítőhelyhez vagy konténerhez történő hozzáadásának képernyőfelvétele](./media/add-fragment.png)
 
    > [!NOTE]
    > <span data-ttu-id="21bd9-159">Ha a tároló vagy a bővítőhely nem támogatja az új származtatott modulokat, akkor a **Töredék hozzáadása** lehetőség nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="21bd9-159">If the container or slot doesn't support new child modules, the **Add Fragment** option is unavailable.</span></span>
    
1. <span data-ttu-id="21bd9-160">A **Töredék hozzáadása** párbeszédpanelen keressen meg és válasszon ki egy töredéket, hogy hozzáadja.</span><span class="sxs-lookup"><span data-stu-id="21bd9-160">In the **Add Fragment** dialog box, search for and select a fragment to add.</span></span> <span data-ttu-id="21bd9-161">Ha nincs elérhető töredék a listán, először létre kell hozni egy töredéket egy olyan modultípusból, amelyet a kiválasztott tároló vagy bővítőhely támogat.</span><span class="sxs-lookup"><span data-stu-id="21bd9-161">If no available fragments are listed, you might first have to create a fragment from a module type that the selected container or slot supports.</span></span>
1. <span data-ttu-id="21bd9-162">Válassza ki és adja hozzá a kívánt töredéket a tárolóhoz vagy helyhez a lapon.</span><span class="sxs-lookup"><span data-stu-id="21bd9-162">Select your desired fragment to add it to the container or slot on your page.</span></span>

    ![A töredékkiválasztó modális ablak képernyőfelvétele](./media/fragment-picker.png)

> [!NOTE]
> <span data-ttu-id="21bd9-164">A tárolókban vagy bővítőhelyekben engedélyezett modulokat a lapsablonja vagy a modulok saját definíciói határozzák meg.</span><span class="sxs-lookup"><span data-stu-id="21bd9-164">The modules that are allowed in a container or slot are defined by the page's template or the modules' own definitions.</span></span>

### <a name="remove-a-fragment"></a><span data-ttu-id="21bd9-165">Töredék eltávolítása</span><span class="sxs-lookup"><span data-stu-id="21bd9-165">Remove a fragment</span></span>

<span data-ttu-id="21bd9-166">A következő lépésekkel lehet eltávolítani egy töredéket egy helyről vagy tárolóból az oldalon.</span><span class="sxs-lookup"><span data-stu-id="21bd9-166">To remove a fragment from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="21bd9-167">A bal oldali vázlat ablaktáblán válassza az eltávolítani kívánt töredék neve melletti három pontot (**...**), majd válassza a kuka gombját.</span><span class="sxs-lookup"><span data-stu-id="21bd9-167">In the outline pane on the left, select the ellipsis (**...**) next to the name of the fragment to be removed, and then select the trash can symbol.</span></span>  <span data-ttu-id="21bd9-168">Másik lehetőségként kiválaszthatja a töredéket a vásznon, és kiválaszthatja a kuka lehetőséget a töredék eszköztárában.</span><span class="sxs-lookup"><span data-stu-id="21bd9-168">Alternately, you can select the fragment in the canvas and select the trash can symbol in the fragment's toolbar.</span></span>
1. <span data-ttu-id="21bd9-169">Amikor a program megkérdezi, hogy szeretné-e eltávolítani a töredéket, válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="21bd9-169">When you're prompted to confirm that you want to remove the fragment, select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="21bd9-170">Ha eltávolít egy töredéket egy lapról, akkor csak az adott oldalról távolítja el a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="21bd9-170">When you remove a fragment from a page, you just remove the reference to it from that page.</span></span> <span data-ttu-id="21bd9-171">**Nem** törli a töredéket az oldalról.</span><span class="sxs-lookup"><span data-stu-id="21bd9-171">You do **not** delete the fragment from your site.</span></span> <span data-ttu-id="21bd9-172">Ha törölni szeretne egy töredékeket a webhelyről, akkor a töredékvizsgáló felhasználói felülteét kell használnia.</span><span class="sxs-lookup"><span data-stu-id="21bd9-172">To delete fragments from your site, you must use the fragment inspector user interface (UI).</span></span> <span data-ttu-id="21bd9-173">A webhely töredékeit csak akkor törölheti, ha a lapok, sablonok vagy más töredékek jelenleg nem hivatkoznak rájuk.</span><span class="sxs-lookup"><span data-stu-id="21bd9-173">You can delete fragments from a site only if they aren't currently referenced by any pages, templates, or other fragments.</span></span>

### <a name="edit-a-fragment"></a><span data-ttu-id="21bd9-174">Töredék szerkesztése</span><span class="sxs-lookup"><span data-stu-id="21bd9-174">Edit a fragment</span></span>

<span data-ttu-id="21bd9-175">A töredékek szerkesztéséhez a töredék-szerkesztő felhasználói felületét kell használnia.</span><span class="sxs-lookup"><span data-stu-id="21bd9-175">To edit fragments, you must use the fragment editor UI.</span></span> <span data-ttu-id="21bd9-176">Ez korlátozás szándékos.</span><span class="sxs-lookup"><span data-stu-id="21bd9-176">This restriction is by design.</span></span> <span data-ttu-id="21bd9-177">Ez segít szavatolni, hogy a szerzők nem tévesztik össze a modulok szerkesztési folyamatát a több lapon megosztott töredékek szerkesztési folyamatával.</span><span class="sxs-lookup"><span data-stu-id="21bd9-177">It helps guarantee that authors don't confuse the process of editing the modules for a specific page with the process of editing fragments that might be shared across many pages.</span></span>

<span data-ttu-id="21bd9-178">Egy töredék szerkesztéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="21bd9-178">To edit a fragment, follow these steps.</span></span>

1. <span data-ttu-id="21bd9-179">A bal oldali navigációs ablakban válassza ki a **Töredékek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="21bd9-179">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="21bd9-180">A **Töredékek** alatt válassza ki a szerkeszteni kívánt töredéket.</span><span class="sxs-lookup"><span data-stu-id="21bd9-180">Under **Fragments**, select the fragment to edit.</span></span>
1. <span data-ttu-id="21bd9-181">Igény szerint szerkesztheti a töredék moduljának jellemzőit és szerkezetét.</span><span class="sxs-lookup"><span data-stu-id="21bd9-181">Edit the fragment's module properties and structure as you require.</span></span> <span data-ttu-id="21bd9-182">A folyamat hasonló a modulok szerkesztési folyamataihoz a lap szerkesztőnézetében.</span><span class="sxs-lookup"><span data-stu-id="21bd9-182">The process resembles the process for editing modules are edited in the page editor view.</span></span>

<span data-ttu-id="21bd9-183">A töredékeket úgy is szerkesztheti, hogy kijelöli azt egy lapon, egy sablonban vagy egy szülő töredékben, majd a jobb oldali Tulajdonságok ablaktáblában kiválasztja a **Töredék szerkesztése** elemet.</span><span class="sxs-lookup"><span data-stu-id="21bd9-183">You can also edit a fragment by selecting it on a page, in a template, or in a parent fragment, and then selecting **Edit Fragment** in the properties pane on the right.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="21bd9-184">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="21bd9-184">Additional resources</span></span>

[<span data-ttu-id="21bd9-185">Sablonok és elrendezések áttekintése</span><span class="sxs-lookup"><span data-stu-id="21bd9-185">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="21bd9-186">Sablonok használata</span><span class="sxs-lookup"><span data-stu-id="21bd9-186">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="21bd9-187">Előre beállított elrendezések használata</span><span class="sxs-lookup"><span data-stu-id="21bd9-187">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="21bd9-188">A közzétételi csoportokkal végzett munka</span><span class="sxs-lookup"><span data-stu-id="21bd9-188">Work with publish groups</span></span>](publish-groups.md)
