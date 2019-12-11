---
title: Modulok használata
description: Ez a témakör azt mutatja be, hogyan és mikor lehet a modulokat a Microsoft Dynamics 365 Commerce rendszerben használni.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 06a26e5dfd35bf229e67ed27213210d0da726bdf
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698073"
---
# <a name="work-with-modules"></a><span data-ttu-id="03b66-103">Modulok használata</span><span class="sxs-lookup"><span data-stu-id="03b66-103">Work with modules</span></span>

<span data-ttu-id="03b66-104">Ez a témakör azt mutatja be, hogyan és mikor lehet a modulokat a Microsoft Dynamics 365 Commerce rendszerben használni.</span><span class="sxs-lookup"><span data-stu-id="03b66-104">This topic describes how and when to use modules in Microsoft Dynamics 365 Commerce.</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="03b66-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="03b66-105">Overview</span></span>

<span data-ttu-id="03b66-106">A modulok olyan logikai építőelemek, amelyek megalkotják a lap struktúráját, és különböző céljaik és hatóköreik vannak.</span><span class="sxs-lookup"><span data-stu-id="03b66-106">Modules are logical building blocks that make up your page structure, and they have various purposes and scopes.</span></span> <span data-ttu-id="03b66-107">Egyes modulok magas szintű tárolók, és egyetlen céljuk a többi modul (származtatott modulok) megtartása és rendszerezése.</span><span class="sxs-lookup"><span data-stu-id="03b66-107">Some modules are high-level containers, and their only purpose is to hold and organize other modules (child modules).</span></span> <span data-ttu-id="03b66-108">A többi modul – például egy egyszerű képelhelyezési modul – kifejezetten konkrét célt szolgál.</span><span class="sxs-lookup"><span data-stu-id="03b66-108">Other modules, such as a simple image placement module, have a very specific purpose.</span></span> <span data-ttu-id="03b66-109">Más modulok, például a körhinta-modul, valahová a két kategória közé esnek.</span><span class="sxs-lookup"><span data-stu-id="03b66-109">Other modules, such as a carousel module, fall somewhere between those two categories.</span></span>

<span data-ttu-id="03b66-110">Alapértelmezés szerint a Dynamics 365 Commerce webhely tartalmaz egy kezdőszett modul könyvtárat, amely lehetővé teszi a legalapvetőbb e-kereskedelmi forgatókönyvek megvalósítását.</span><span class="sxs-lookup"><span data-stu-id="03b66-110">By default, your Dynamics 365 Commerce site includes a starter kit module library that lets you achieve most basic e-Commerce scenarios.</span></span> <span data-ttu-id="03b66-111">Kizárólag ezen modulok használatával is létrehozhat egy teljes körű e-kereskedelmi weboldalt.</span><span class="sxs-lookup"><span data-stu-id="03b66-111">You should be able to construct an end-to-end e-Commerce site just by using these modules.</span></span> <span data-ttu-id="03b66-112">Előfordulhat azonban, hogy testre szeretné szabni ezeket a modulokat, vagy új egyéni modulokat szeretne létrehozni adott igényekhez.</span><span class="sxs-lookup"><span data-stu-id="03b66-112">However, you might also want to customize these modules or build new, custom modules for specific needs.</span></span> <span data-ttu-id="03b66-113">Egyéni modulok készítéséhez egy modultervező szoftverfejlesztői készlet (SDK) érhető el, amely segítséget nyújt az egyéni modulkönyvtár létrehozásában.</span><span class="sxs-lookup"><span data-stu-id="03b66-113">If you want to build custom modules, a module design software development kit (SDK) is available to help you create a custom module library.</span></span>

## <a name="container-modules-and-slots"></a><span data-ttu-id="03b66-114">Tárolómodulok és helyek</span><span class="sxs-lookup"><span data-stu-id="03b66-114">Container modules and slots</span></span>

<span data-ttu-id="03b66-115">Ahogy korábban már említettük, néhány modul a származtatott modulok tárolásához van kialakítva.</span><span class="sxs-lookup"><span data-stu-id="03b66-115">As was mentioned earlier, some modules are designed to hold child modules.</span></span> <span data-ttu-id="03b66-116">Ezek a modulok *konténerként*ismertek, és lehetővé teszik a beágyazott modulok hierarchiájának létrehozását.</span><span class="sxs-lookup"><span data-stu-id="03b66-116">These modules are known as *containers*, and they allow for hierarchies of nested modules.</span></span> <span data-ttu-id="03b66-117">Tárolómodulok *helyeket* tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="03b66-117">Container modules include *slots*.</span></span> <span data-ttu-id="03b66-118">A helyek a származtatott modulok elrendezésének és céljának kezelésére szolgálnak a tárolóban.</span><span class="sxs-lookup"><span data-stu-id="03b66-118">Slots are used to handle the layout and purpose of child modules in the container.</span></span> <span data-ttu-id="03b66-119">Egy példa egy egyszerű laptároló modul (bármely lap felső szintű modulja), amely több fontos helyet határoz meg:</span><span class="sxs-lookup"><span data-stu-id="03b66-119">An example is a basic page container module (a top-level module for any page) that defines several important slots:</span></span>

- <span data-ttu-id="03b66-120">Fejléc hely</span><span class="sxs-lookup"><span data-stu-id="03b66-120">A header slot</span></span>
- <span data-ttu-id="03b66-121">Egy törzsszöveg hely</span><span class="sxs-lookup"><span data-stu-id="03b66-121">A body slot</span></span>
- <span data-ttu-id="03b66-122">Egy lábléc hely</span><span class="sxs-lookup"><span data-stu-id="03b66-122">A footer slot</span></span>

<span data-ttu-id="03b66-123">A modul fejlesztői ezeket a helyeket definiálják, és meghatározzák, hogy mely származtatott modulokat és hány származtatott modult lehet közvetlenül benne elhelyezni.</span><span class="sxs-lookup"><span data-stu-id="03b66-123">The module's developer defines these slots, and determines which child modules and how many child modules can be put directly inside it.</span></span> <span data-ttu-id="03b66-124">Például a fejléc hely csak a **Fejlécmodul** típusú modult támogat, míg a törzs helyek korlátlan számú modult támogatnak (kivéve más oldaltároló modulokat).</span><span class="sxs-lookup"><span data-stu-id="03b66-124">For example, the header slot might support only one module of the **Header Module** type, whereas the body slot might support an unlimited number of modules of any type (except other page container modules).</span></span>

<span data-ttu-id="03b66-125">A szerkesztőeszközökben a lap szerzőjének nem kell előzetesen tudnia, hogy mely modulok helyezhetők el és nem helyezhetők el az egyes helyekre.</span><span class="sxs-lookup"><span data-stu-id="03b66-125">In the authoring tools, page authors don't have to know in advance which modules can and can't be put in each slot.</span></span> <span data-ttu-id="03b66-126">Amikor az oldalszerzők egy helyet kijelölnek majd megpróbálnak kiválasztani egy modult, akkor az adott helyhez tartozó modulok szűrt listáját látják.</span><span class="sxs-lookup"><span data-stu-id="03b66-126">When page authors select a slot and then try to select a module to add to it, they see a filtered view of module types that are supported for that slot.</span></span>

## <a name="content-modules"></a><span data-ttu-id="03b66-127">Tartalommodulok</span><span class="sxs-lookup"><span data-stu-id="03b66-127">Content modules</span></span>

<span data-ttu-id="03b66-128">A tartalmi modulok tartalmazzák a tartalmakat és a multimédiás elemeket, például a szöveget (például a fejléceket, a bekezdéseket és a hivatkozásokat) vagy az eszközhivatkozásokat (például képek, videók és PDF-állományok).</span><span class="sxs-lookup"><span data-stu-id="03b66-128">Content modules contain content and media elements, such as text (for example, headlines, paragraphs, and links) or asset references (for example, images, video, and PDFs).</span></span> <span data-ttu-id="03b66-129">A tipikus tartalmi modul típusokra példa a **Hős** ,a **Szolgáltatás** és **Szalagcím**.</span><span class="sxs-lookup"><span data-stu-id="03b66-129">Examples of typical content module types are **Hero**, **Feature**, and **Banner**.</span></span> <span data-ttu-id="03b66-130">Ezeknek a három típusnak a moduljai tartalmazhatnak szöveget vagy médiát, és nem igényelnek származtatott modulokat ahhoz, hogy láthatóvá tegyenek valamit egy oldalon.</span><span class="sxs-lookup"><span data-stu-id="03b66-130">Modules of these three types can contain text or media, and they don't require any child modules to make something visible on a page.</span></span>

<span data-ttu-id="03b66-131">Az általános, gyakran használt oldal- és tartalomszerkesztési tevékenységek többsége tartalmi modulokat tartalmaz elsősorban, mivel ezek a modulok határozzák meg a szülő tároló moduljukban megjelenített tényleges tartalmat.</span><span class="sxs-lookup"><span data-stu-id="03b66-131">The majority of typical, day-to-day page and content authoring activities involve content modules, primarily because these modules define the actual content that is rendered in their parent container modules.</span></span> <span data-ttu-id="03b66-132">Számos tartalmi modul érhető el, és ezek a modulok általában az utolsó darabok, amelyeket hozzáad az oldal beágyazott modulokból álló hierarchiájához.</span><span class="sxs-lookup"><span data-stu-id="03b66-132">Many content modules are available, and these modules are typically the last pieces that you will add to a page's hierarchy of nested modules.</span></span>

<span data-ttu-id="03b66-133">A következő ábra bemutatja, hogyan vannak a modulok a szülő tároló helyeire beágyazva.</span><span class="sxs-lookup"><span data-stu-id="03b66-133">The following illustration shows how modules are nested inside parent container module slots.</span></span>

![Modulok beágyazása](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a><span data-ttu-id="03b66-135">Modulok hozzáadása vagy eltávolítása</span><span class="sxs-lookup"><span data-stu-id="03b66-135">Add or remove modules</span></span>

<span data-ttu-id="03b66-136">A következő eljárások leírják a modulok hozzáadását és eltávolítását.</span><span class="sxs-lookup"><span data-stu-id="03b66-136">The following procedures describe how to add and remove modules.</span></span>

### <a name="add-a-module"></a><span data-ttu-id="03b66-137">Modul hozzáadása</span><span class="sxs-lookup"><span data-stu-id="03b66-137">Add a module</span></span>

<span data-ttu-id="03b66-138">A következő lépésekkel lehet hozzáadni egy modult egy helyhez vagy tárolóhoz egy lapon.</span><span class="sxs-lookup"><span data-stu-id="03b66-138">To add a module to a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="03b66-139">A bal oldali vázlat ablaktáblán válassza ki azt a tárolóhelyet vagy bővítőhelyet, amelyhez hozzá szeretné adni a származtatott modult.</span><span class="sxs-lookup"><span data-stu-id="03b66-139">In the outline pane on the left, select a container or slot that a child module can be added to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="03b66-140">A modultervező meghatározza azoknak a moduloknak a listáját, amelyek hozzáadhatók egy adott modulbővítőhelyhez.</span><span class="sxs-lookup"><span data-stu-id="03b66-140">The module designer defines the list of modules types that can be added to a specific module slot.</span></span> <span data-ttu-id="03b66-141">A sablon szerzője ezt követően finomíthatja az engedélyezett modul beállításait, így garantálva a következetes keresőmotor-optimalizálást (SEO) és szerkesztés hatékonyságát az összes olyan oldalhoz, amelyeket egy adott sablonból építettek fel.</span><span class="sxs-lookup"><span data-stu-id="03b66-141">Template authors can then refine the allowed module options to help guarantee consistent search engine optimization (SEO) and authoring efficiency for all the pages pages that are built from a specific template.</span></span>

1. <span data-ttu-id="03b66-142">Válassza ki a modulhoz tartozó három pont gombot (**…**), majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="03b66-142">Select the ellipsis button (**...**) for the module, and then select **Add Module**.</span></span> <span data-ttu-id="03b66-143">Megjelenik a **Modul hozzáadása** párbeszédpanel.</span><span class="sxs-lookup"><span data-stu-id="03b66-143">The **Add Module** dialog box appears.</span></span> <span data-ttu-id="03b66-144">Ezt a párbeszédpanelt a program automatikusan szűri, így csak a kiválasztott tárolóban vagy bővítőhelyen támogatott modulokat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="03b66-144">This dialog box is automatically filtered so that it shows only modules that are supported in the selected container or slot.</span></span> <span data-ttu-id="03b66-145">A modulok listáját a lap sablonja vagy a tárolómodul definíciója határozza meg.</span><span class="sxs-lookup"><span data-stu-id="03b66-145">The list of modules is determined by the page's template or the container module definition.</span></span>

    > [!NOTE]
    > <span data-ttu-id="03b66-146">Ha egy tároló vagy egy bővítőhely nem támogatja az új származtatott modulokat, akkor a **Modul hozzáadása** lehetőség nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="03b66-146">If a container or slot doesn't support new child modules, the **Add Module** option is unavailable.</span></span>

1. <span data-ttu-id="03b66-147">A párbeszédpanelen keressen meg. és válasszon ki egy modult, hogy hozzáadja az oldalhoz.</span><span class="sxs-lookup"><span data-stu-id="03b66-147">In the dialog box, search for and select a module to add to your page.</span></span>

    > [!TIP]
    > <span data-ttu-id="03b66-148">A **Szolgáltatás** és a **Hős** jó modulok kezdők számára.</span><span class="sxs-lookup"><span data-stu-id="03b66-148">**Feature** and **Hero** are good module types for beginners to work with.</span></span>

1. <span data-ttu-id="03b66-149">Az **OK** gombra kattintva adja hozzá a kijelölt modult a kiválasztott tárolóhoz vagy helyhez a lapon.</span><span class="sxs-lookup"><span data-stu-id="03b66-149">Select **OK** to add the selected module to the selected container or slot on your page.</span></span>

### <a name="remove-a-module"></a><span data-ttu-id="03b66-150">Modul eltávolítása</span><span class="sxs-lookup"><span data-stu-id="03b66-150">Remove a module</span></span>

<span data-ttu-id="03b66-151">A következő lépésekkel lehet eltávolítani egy modult egy helyről vagy tárolóból az oldalon.</span><span class="sxs-lookup"><span data-stu-id="03b66-151">To remove a module from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="03b66-152">A bal oldali vázlat ablaktáblán válassza az eltávolítani kívánt modul neve melletti három pont gombot, majd válassza a kuka gombját.</span><span class="sxs-lookup"><span data-stu-id="03b66-152">In the outline pane on the left, select the ellipsis button next to the name of the module to remove, and then select the trash can button.</span></span>
1. <span data-ttu-id="03b66-153">Amikor a program megkérdezi, hogy szeretné-e eltávolítani a modult, válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="03b66-153">When you're prompted to confirm that you want to remove the module, select **OK**.</span></span>

## <a name="configure-modules"></a><span data-ttu-id="03b66-154">Modulok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="03b66-154">Configure modules</span></span>

<span data-ttu-id="03b66-155">A következő eljárások leírják a tartalom- és tárolómodulok konfigurálását.</span><span class="sxs-lookup"><span data-stu-id="03b66-155">The following procedures describe how to configure content and container modules.</span></span>

### <a name="configure-a-content-module"></a><span data-ttu-id="03b66-156">Tartalommodul konfigurálása</span><span class="sxs-lookup"><span data-stu-id="03b66-156">Configure a content module</span></span>

<span data-ttu-id="03b66-157">Egy tartalommodulnak egy lapon történő konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="03b66-157">To configure a content module on a page, follow these steps.</span></span>

1. <span data-ttu-id="03b66-158">A bal oldali vázlat ablaktáblán válasszon ki egy tartalommodul típust (például **Funkció**, **Hős** vagy **Szalagcím**).</span><span class="sxs-lookup"><span data-stu-id="03b66-158">In the outline pane on the left, select a content module type (for example, **Feature**, **Hero**, or **Banner**).</span></span>
1. <span data-ttu-id="03b66-159">A jobb oldali tulajdonságok ablaktáblán bontsa ki a beágyazott vezérlőket a fejlécek kiválasztásával, és adja meg a szükséges vezérlő értékeket.</span><span class="sxs-lookup"><span data-stu-id="03b66-159">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="03b66-160">Ha a tulajdonságok ablaktáblán van egy **Adatkonfiguráció** szakasz, jelölje ki azt a kibontáshoz.</span><span class="sxs-lookup"><span data-stu-id="03b66-160">If the properties pane has a **Data Configuration** section, select it to expand it.</span></span> <span data-ttu-id="03b66-161">Máskülönben folytassa az 5. lépéssel.</span><span class="sxs-lookup"><span data-stu-id="03b66-161">Otherwise, go to step 5.</span></span>
1. <span data-ttu-id="03b66-162">Ha van egy **Adatforrás hozzáadása** gomb, válassza ki azt majd válassza ki a hozzáadni kívánt tartalomelemeket.</span><span class="sxs-lookup"><span data-stu-id="03b66-162">If there is a **Add Data Source** button, select it, and then select the content items to add.</span></span>
1. <span data-ttu-id="03b66-163">Adja meg a szükséges vagy a kívánt modulvezérlőket.</span><span class="sxs-lookup"><span data-stu-id="03b66-163">Enter settings for any required or desired module controls.</span></span>
1. <span data-ttu-id="03b66-164">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="03b66-164">Select **Save**.</span></span>

### <a name="configure-a-container-module"></a><span data-ttu-id="03b66-165">Tárolómodul konfigurálása</span><span class="sxs-lookup"><span data-stu-id="03b66-165">Configure a container module</span></span>

<span data-ttu-id="03b66-166">Egy tárolómodulnak egy lapon történő konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="03b66-166">To configure a container module on a page, follow these steps.</span></span>

1. <span data-ttu-id="03b66-167">Válasszon ki egy konténermodult az oldalon (például körhinta vagy folyékony tárolómodult).</span><span class="sxs-lookup"><span data-stu-id="03b66-167">Select a container module on your page (for example, a carousel or fluid container module).</span></span>
1. <span data-ttu-id="03b66-168">A jobb oldali tulajdonságok ablaktáblán bontsa ki a beágyazott vezérlőket a fejlécek kiválasztásával, és adja meg a szükséges vezérlő értékeket.</span><span class="sxs-lookup"><span data-stu-id="03b66-168">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="03b66-169">A bal oldali vázlat ablaktáblán válassza az eltávolítani tároló vagy a tároló bármelyik helye neve melletti három pont gombot, majd válassza ki a **Modul hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="03b66-169">In the outline pane on the left, select the ellipsis button next to the name of either the container or any slots inside the container, and then select **Add Module**.</span></span> <span data-ttu-id="03b66-170">Ezután adja hozzá a származtatott modulokat a kiválasztott tárolóhoz.</span><span class="sxs-lookup"><span data-stu-id="03b66-170">Then add child modules to the selected container.</span></span> <span data-ttu-id="03b66-171">A további tudnivalókat lásd: [Modul hozzáadása](#add-a-module) eljárást a témakör korábbi részében.</span><span class="sxs-lookup"><span data-stu-id="03b66-171">For more information, see the [Add a module](#add-a-module) procedure earlier in this topic.</span></span>
1. <span data-ttu-id="03b66-172">Ha több származtatott modul van egy szülő tárolóban, akkor a szülő tárolóban módosítható a megjelenítési sorrendjük.</span><span class="sxs-lookup"><span data-stu-id="03b66-172">If multiple child modules exist as siblings in a parent container, you can change their display order in the parent container.</span></span> <span data-ttu-id="03b66-173">Jelölje ki az egyik modulhoz tartozó három pont gombot, majd a fel és a le nyílbillentyűket.</span><span class="sxs-lookup"><span data-stu-id="03b66-173">Select the ellipsis button for a module, and then use the up arrow and down arrow buttons.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="03b66-174">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="03b66-174">Additional resources</span></span>

[<span data-ttu-id="03b66-175">Sablonok és elrendezések áttekintése</span><span class="sxs-lookup"><span data-stu-id="03b66-175">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="03b66-176">Sablonok használata</span><span class="sxs-lookup"><span data-stu-id="03b66-176">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="03b66-177">Előre beállított elrendezések használata</span><span class="sxs-lookup"><span data-stu-id="03b66-177">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="03b66-178">Töredékek használata</span><span class="sxs-lookup"><span data-stu-id="03b66-178">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="03b66-179">Tárolómodul hozzáadása egy oldalhoz</span><span class="sxs-lookup"><span data-stu-id="03b66-179">Add a container module to a page</span></span>](add-container-module.md)

[<span data-ttu-id="03b66-180">Tartalomelhelyezési modul hozzáadása oldalhoz</span><span class="sxs-lookup"><span data-stu-id="03b66-180">Add content placement modules to a page</span></span>](add-content-placement-modules.md)

