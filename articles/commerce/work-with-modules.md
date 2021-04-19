---
title: Modulok használata
description: Ez a témakör azt mutatja be, hogyan és mikor lehet a modulokat a Microsoft Dynamics 365 Commerce rendszerben használni.
author: phinneyridge
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6d872719d3b1aa27ccfdcf36d7739c883e7b4996
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801361"
---
# <a name="work-with-modules"></a><span data-ttu-id="8190a-103">Modulok használata</span><span class="sxs-lookup"><span data-stu-id="8190a-103">Work with modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8190a-104">Ez a témakör azt mutatja be, hogyan és mikor lehet a modulokat a Microsoft Dynamics 365 Commerce rendszerben használni.</span><span class="sxs-lookup"><span data-stu-id="8190a-104">This topic describes how and when to use modules in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8190a-105">A modulok olyan logikai építőelemek, amelyek megalkotják a lap struktúráját, és különböző céljaik és hatóköreik vannak.</span><span class="sxs-lookup"><span data-stu-id="8190a-105">Modules are logical building blocks that make up your page structure, and they have various purposes and scopes.</span></span> <span data-ttu-id="8190a-106">Egyes modulok magas szintű tárolók, és egyetlen céljuk a többi modul (származtatott modulok) megtartása és rendszerezése.</span><span class="sxs-lookup"><span data-stu-id="8190a-106">Some modules are high-level containers, and their only purpose is to hold and organize other modules (child modules).</span></span> <span data-ttu-id="8190a-107">A többi modul – például egy egyszerű képelhelyezési modul – kifejezetten konkrét célt szolgál.</span><span class="sxs-lookup"><span data-stu-id="8190a-107">Other modules, such as a simple image placement module, have a very specific purpose.</span></span> <span data-ttu-id="8190a-108">Más modulok, például a körhinta-modul, valahová a két kategória közé esnek.</span><span class="sxs-lookup"><span data-stu-id="8190a-108">Other modules, such as a carousel module, fall somewhere between those two categories.</span></span>

<span data-ttu-id="8190a-109">Alapértelmezés szerint a Dynamics 365 Commerce webhely tartalmaz egy modulkönyvtárat, amely lehetővé teszi a legalapvetőbb e-kereskedelmi forgatókönyvek megvalósítását.</span><span class="sxs-lookup"><span data-stu-id="8190a-109">By default, your Dynamics 365 Commerce site includes a module library that lets you achieve most basic e-Commerce scenarios.</span></span> <span data-ttu-id="8190a-110">Kizárólag ezen modulok használatával is létrehozhat egy teljes körű e-kereskedelmi weboldalt.</span><span class="sxs-lookup"><span data-stu-id="8190a-110">You should be able to construct an end-to-end e-Commerce site just by using these modules.</span></span> <span data-ttu-id="8190a-111">Előfordulhat azonban, hogy testre szeretné szabni ezeket a modulokat, vagy új egyéni modulokat szeretne létrehozni adott igényekhez.</span><span class="sxs-lookup"><span data-stu-id="8190a-111">However, you might also want to customize these modules or build new, custom modules for specific needs.</span></span> <span data-ttu-id="8190a-112">Egyéni modulok készítéséhez egy modultervező szoftverfejlesztői készlet (SDK) érhető el, amely segítséget nyújt az egyéni modulkönyvtár létrehozásában.</span><span class="sxs-lookup"><span data-stu-id="8190a-112">If you want to build custom modules, a module design software development kit (SDK) is available to help you create a custom module library.</span></span>

## <a name="container-modules-and-slots"></a><span data-ttu-id="8190a-113">Tárolómodulok és helyek</span><span class="sxs-lookup"><span data-stu-id="8190a-113">Container modules and slots</span></span>

<span data-ttu-id="8190a-114">Ahogy korábban már említettük, néhány modul a származtatott modulok tárolásához van kialakítva.</span><span class="sxs-lookup"><span data-stu-id="8190a-114">As was mentioned earlier, some modules are designed to hold child modules.</span></span> <span data-ttu-id="8190a-115">Ezek a modulok *konténerként* ismertek, és lehetővé teszik a beágyazott modulok hierarchiájának létrehozását.</span><span class="sxs-lookup"><span data-stu-id="8190a-115">These modules are known as *containers*, and they allow for hierarchies of nested modules.</span></span> <span data-ttu-id="8190a-116">Tárolómodulok *helyeket* tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="8190a-116">Container modules include *slots*.</span></span> <span data-ttu-id="8190a-117">A helyek a származtatott modulok elrendezésének és céljának kezelésére szolgálnak a tárolóban.</span><span class="sxs-lookup"><span data-stu-id="8190a-117">Slots are used to handle the layout and purpose of child modules in the container.</span></span> <span data-ttu-id="8190a-118">Egy példa egy egyszerű laptároló modul (bármely lap felső szintű modulja), amely több fontos helyet határoz meg:</span><span class="sxs-lookup"><span data-stu-id="8190a-118">An example is a basic page container module (a top-level module for any page) that defines several important slots:</span></span>

- <span data-ttu-id="8190a-119">Fejléc hely</span><span class="sxs-lookup"><span data-stu-id="8190a-119">A header slot</span></span>
- <span data-ttu-id="8190a-120">Alfejléc hely</span><span class="sxs-lookup"><span data-stu-id="8190a-120">A sub-header slot</span></span>
- <span data-ttu-id="8190a-121">Fő hely</span><span class="sxs-lookup"><span data-stu-id="8190a-121">A main slot</span></span>
- <span data-ttu-id="8190a-122">Egy lábléc hely</span><span class="sxs-lookup"><span data-stu-id="8190a-122">A footer slot</span></span>
- <span data-ttu-id="8190a-123">Allábléc hely</span><span class="sxs-lookup"><span data-stu-id="8190a-123">A sub-footer slot</span></span>

<span data-ttu-id="8190a-124">A modul fejlesztői ezeket a helyeket definiálják, és meghatározzák, hogy mely származtatott modulokat és hány származtatott modult lehet közvetlenül benne elhelyezni.</span><span class="sxs-lookup"><span data-stu-id="8190a-124">The module's developer defines these slots, and determines which child modules and how many child modules can be put directly inside it.</span></span> <span data-ttu-id="8190a-125">Például a fejléc hely csak a **Fejlécmodul** típusú modult támogat, míg a törzs helyek korlátlan számú modult támogatnak (kivéve más oldaltároló modulokat).</span><span class="sxs-lookup"><span data-stu-id="8190a-125">For example, the header slot might support only one module of the **Header Module** type, whereas the body slot might support an unlimited number of modules of any type (except other page container modules).</span></span>

<span data-ttu-id="8190a-126">A szerkesztőeszközökben a lap szerzőjének nem kell előzetesen tudnia, hogy mely modulok helyezhetők el és nem helyezhetők el az egyes helyekre.</span><span class="sxs-lookup"><span data-stu-id="8190a-126">In the authoring tools, page authors don't have to know in advance which modules can and can't be put in each slot.</span></span> <span data-ttu-id="8190a-127">Amikor az oldalszerzők egy helyet kijelölnek majd megpróbálnak kiválasztani egy modult, akkor az adott helyhez tartozó modulok szűrt listáját látják.</span><span class="sxs-lookup"><span data-stu-id="8190a-127">When page authors select a slot and then try to select a module to add to it, they see a filtered view of module types that are supported for that slot.</span></span>

## <a name="content-modules"></a><span data-ttu-id="8190a-128">Tartalommodulok</span><span class="sxs-lookup"><span data-stu-id="8190a-128">Content modules</span></span>

<span data-ttu-id="8190a-129">A tartalmi modulok tartalmazzák a tartalmakat és a multimédiás elemeket, például a szöveget (például a fejléceket, a bekezdéseket és a hivatkozásokat) vagy az eszközhivatkozásokat (például képek, videók és PDF-állományok).</span><span class="sxs-lookup"><span data-stu-id="8190a-129">Content modules contain content and media elements, such as text (for example, headlines, paragraphs, and links) or asset references (for example, images, video, and PDFs).</span></span> <span data-ttu-id="8190a-130">A jellemző tartalmi modultípusok közé tartozik a tartalomblokk, a szövegterület és a promó bannermodulok.</span><span class="sxs-lookup"><span data-stu-id="8190a-130">Typical content module types include content block, text block, and promo banner modules.</span></span> <span data-ttu-id="8190a-131">Ezeknek a három típusnak a moduljai tartalmazhatnak szöveget vagy médiát, és nem igényelnek származtatott modulokat ahhoz, hogy láthatóvá tegyenek valamit egy oldalon.</span><span class="sxs-lookup"><span data-stu-id="8190a-131">Modules of these three types can contain text or media, and they don't require any child modules to make something visible on a page.</span></span>

<span data-ttu-id="8190a-132">Az általános, gyakran használt oldal- és tartalomszerkesztési tevékenységek többsége tartalmi modulokat tartalmaz elsősorban, mivel ezek a modulok határozzák meg a szülő tároló moduljukban megjelenített tényleges tartalmat.</span><span class="sxs-lookup"><span data-stu-id="8190a-132">The majority of typical, day-to-day page and content authoring activities involve content modules, primarily because these modules define the actual content that is rendered in their parent container modules.</span></span> <span data-ttu-id="8190a-133">Számos tartalmi modul érhető el, és ezek a modulok általában az utolsó darabok, amelyeket hozzáad az oldal beágyazott modulokból álló hierarchiájához.</span><span class="sxs-lookup"><span data-stu-id="8190a-133">Many content modules are available, and these modules are typically the last pieces that you will add to a page's hierarchy of nested modules.</span></span>

<span data-ttu-id="8190a-134">A következő ábra bemutatja, hogyan vannak a modulok a szülő tároló helyeire beágyazva.</span><span class="sxs-lookup"><span data-stu-id="8190a-134">The following illustration shows how modules are nested inside parent container module slots.</span></span>

![Modulok beágyazása](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a><span data-ttu-id="8190a-136">Modulok hozzáadása vagy eltávolítása</span><span class="sxs-lookup"><span data-stu-id="8190a-136">Add or remove modules</span></span>

<span data-ttu-id="8190a-137">A következő eljárások leírják a modulok hozzáadását és eltávolítását.</span><span class="sxs-lookup"><span data-stu-id="8190a-137">The following procedures describe how to add and remove modules.</span></span>

### <a name="add-a-module"></a><span data-ttu-id="8190a-138">Modul hozzáadása</span><span class="sxs-lookup"><span data-stu-id="8190a-138">Add a module</span></span>

<span data-ttu-id="8190a-139">A következő lépésekkel lehet hozzáadni egy modult egy helyhez vagy tárolóhoz egy lapon.</span><span class="sxs-lookup"><span data-stu-id="8190a-139">To add a module to a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="8190a-140">A bal oldali vázlat ablaktáblán vagy közvetlenül a fő vásznon, válassza ki azt a tárolót vagy helyet, amelyhez hozzá szeretné adni az alárendelt modult.</span><span class="sxs-lookup"><span data-stu-id="8190a-140">In the outline pane on the left or directly in the main canvas, select a container or slot to which a child module can be added.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8190a-141">A modultervező meghatározza azoknak a moduloknak a listáját, amelyek hozzáadhatók egy adott modulbővítőhelyhez.</span><span class="sxs-lookup"><span data-stu-id="8190a-141">The module designer defines the list of modules types that can be added to a specific module slot.</span></span> <span data-ttu-id="8190a-142">A sablon szerzője ezt követően finomíthatja az engedélyezett modul beállításait, így garantálva a következetes keresőmotor-optimalizálást (SEO) és szerkesztés hatékonyságát az összes olyan oldalhoz, amelyeket egy adott sablonból építettek fel.</span><span class="sxs-lookup"><span data-stu-id="8190a-142">Template authors can then refine the allowed module options to help guarantee consistent search engine optimization (SEO) and authoring efficiency for all the pages that are built from a specific template.</span></span> <span data-ttu-id="8190a-143">Amikor hozzáad egy modult egy helyhez, a **Modul hozzáadása** párbeszédpanelt a program automatikusan szűri, így csak a kiválasztott tárolóban vagy bővítőhelyen támogatott modulokat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="8190a-143">When adding a module to a slot, the **Add Module** dialog box is automatically filtered so that it shows only modules that are supported in the selected container or slot.</span></span> <span data-ttu-id="8190a-144">Az engedélyezett modulok listáját a lap sablonja vagy a tárolómodul definíciója határozza meg.</span><span class="sxs-lookup"><span data-stu-id="8190a-144">This list of allowed modules is determined by the page's template or the container's module definition.</span></span>

1. <span data-ttu-id="8190a-145">Ha a körvonal ablaktáblát használja, válassza ki a modul neve melletti három pontot (**...**), majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="8190a-145">If using the outline pane, select the ellipsis (**...**) next to the module name, and then select **Add Module**.</span></span> <span data-ttu-id="8190a-146">Ha közvetlenül a vásznon belül használja a vezérlőket, válassza ki a plusz jelet (**+**) egy üres helyen vagy a kiválasztott modul szomszédos helyen, majd válassza ki a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="8190a-146">If using the controls directly within the canvas, select the plus symbol (**+**) in an empty slot or adjacent to the currently selected module, and then select **Add Module**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8190a-147">Ha egy tároló vagy egy bővítőhely nem támogatja az új származtatott modulokat, akkor a **Modul hozzáadása** lehetőség nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="8190a-147">If a container or slot doesn't support new child modules, the **Add Module** option is unavailable.</span></span>

1. <span data-ttu-id="8190a-148">A **Modul hozzáadása** párbeszédpanelen válasszon ki egy modult, hogy hozzáadja az oldalhoz.</span><span class="sxs-lookup"><span data-stu-id="8190a-148">In the **Add Module** dialog box, select a module to add to your page.</span></span>

    > [!TIP]
    > <span data-ttu-id="8190a-149">A **Tartalomblokk** kezdőknek való modultípus.</span><span class="sxs-lookup"><span data-stu-id="8190a-149">**Content block** is a good module type for beginners to work with.</span></span>

1. <span data-ttu-id="8190a-150">Az **OK** gombra kattintva adja hozzá a kijelölt modult a kiválasztott tárolóhoz vagy helyhez a lapon.</span><span class="sxs-lookup"><span data-stu-id="8190a-150">Select **OK** to add the selected module to the selected container or slot on your page.</span></span>

### <a name="remove-a-module"></a><span data-ttu-id="8190a-151">Modul eltávolítása</span><span class="sxs-lookup"><span data-stu-id="8190a-151">Remove a module</span></span>

<span data-ttu-id="8190a-152">A következő lépésekkel lehet eltávolítani egy modult egy helyről vagy tárolóból az oldalon.</span><span class="sxs-lookup"><span data-stu-id="8190a-152">To remove a module from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="8190a-153">A bal oldali vázlat ablaktáblán válassza az eltávolítani kívánt modul neve melletti három pontot (**...**), majd válassza a kuka gombját.</span><span class="sxs-lookup"><span data-stu-id="8190a-153">In the outline pane on the left, select the ellipsis (**...**) next to the name of the module to be removed, and then select the trash can symbol.</span></span> <span data-ttu-id="8190a-154">Másik lehetőségként a fő vászonban is kijelölheti a kiválasztott modul eszköztárán lévő kuka szimbólumot.</span><span class="sxs-lookup"><span data-stu-id="8190a-154">Alternately, in the main canvas you can select the trash can symbol on a selected module's toolbar.</span></span>
1. <span data-ttu-id="8190a-155">Amikor a program megkérdezi, hogy szeretné-e eltávolítani a modult, válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8190a-155">When prompted to confirm that you want to remove the module, select **OK**.</span></span>

## <a name="move-a-module-to-a-new-position"></a><span data-ttu-id="8190a-156">Modul áthelyezése egy új pozícióba</span><span class="sxs-lookup"><span data-stu-id="8190a-156">Move a module to a new position</span></span>

<span data-ttu-id="8190a-157">Ha egy modult át szeretne helyezni egy új pozícióba a lapon belül, akkor használja az alábbi módszerek valamelyikét.</span><span class="sxs-lookup"><span data-stu-id="8190a-157">To move a module to a new position within your page, use any of the following methods.</span></span>

### <a name="move-a-module-using-the-outline-pane"></a><span data-ttu-id="8190a-158">Modul áthelyezése a körvonal ablaktábla használatával</span><span class="sxs-lookup"><span data-stu-id="8190a-158">Move a module using the outline pane</span></span>

<span data-ttu-id="8190a-159">Ha egy modult a körvonal ablaktáblával szeretne áthelyezni, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8190a-159">To move a module using the outline pane, follow these steps.</span></span>

1. <span data-ttu-id="8190a-160">Jelölje ki és tartsa lenyomva az áthelyezni kívánt modult a körvonal ablaktáblán, majd húzza át a modult a körvonalban szereplő új pozícióra.</span><span class="sxs-lookup"><span data-stu-id="8190a-160">Select and hold the module you want to move in the outline pane, then drag the module to a new position in the outline.</span></span> <span data-ttu-id="8190a-161">A körvonalon és a vásznon lévő kék sor jelzi, hogy hova helyezheti a modult.</span><span class="sxs-lookup"><span data-stu-id="8190a-161">The blue line in the outline and on the canvas indicates where the module can be placed.</span></span>
1. <span data-ttu-id="8190a-162">A modul kiadása, hogy át lehessen dobni az új pozícióba.</span><span class="sxs-lookup"><span data-stu-id="8190a-162">Release the module to drop it into the new position.</span></span>

### <a name="move-a-module-directly-within-the-canvas"></a><span data-ttu-id="8190a-163">Modul áthelyezése közvetlenül a vásznon belül</span><span class="sxs-lookup"><span data-stu-id="8190a-163">Move a module directly within the canvas</span></span>

<span data-ttu-id="8190a-164">Ha egy modult közvetlenül a vásznon belül szeretne áthelyezni, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8190a-164">To move a module directly within the canvas, follow these steps.</span></span>

1. <span data-ttu-id="8190a-165">Válassza ki azt a modult, amelyet át szeretne helyezni a vásznon belül.</span><span class="sxs-lookup"><span data-stu-id="8190a-165">Select the module you want to move in the canvas.</span></span> 
1. <span data-ttu-id="8190a-166">Válassza ki a modul eszköztárában a felfelé vagy lefelé mutató nyilat, majd húzza a nyilat a lap új helyére.</span><span class="sxs-lookup"><span data-stu-id="8190a-166">Select either an upward or downward pointing arrow symbol in the module's toolbar, and then drag the arrow to a new position on the page.</span></span> <span data-ttu-id="8190a-167">A vászonban és a körvonalban lévő kék sor jelzi, hogy hova helyezheti a modult.</span><span class="sxs-lookup"><span data-stu-id="8190a-167">The blue line in the canvas and outline indicates where the module can be placed.</span></span> <span data-ttu-id="8190a-168">Ha egy modult nem lehet felfelé vagy lefelé mozgatni, akkor a nyíl gomb szürkén jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="8190a-168">If a module cannot be moved up or down, that arrow symbol will be grayed out.</span></span> 
1. <span data-ttu-id="8190a-169">A modul kiadása, hogy át lehessen dobni az új pozícióba.</span><span class="sxs-lookup"><span data-stu-id="8190a-169">Release the module to drop it into the new position.</span></span>

### <a name="move-a-module-using-the-ellipsis-menu"></a><span data-ttu-id="8190a-170">Modul áthelyezése a három pont menü használatával</span><span class="sxs-lookup"><span data-stu-id="8190a-170">Move a module using the ellipsis menu</span></span>

<span data-ttu-id="8190a-171">Ha egy modult a három pont menüvel szeretne áthelyezni, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8190a-171">To move a module using the ellipsis menu, follow these steps.</span></span>

1. <span data-ttu-id="8190a-172">Válasszon ki egy modult a körvonalban vagy a vásznon.</span><span class="sxs-lookup"><span data-stu-id="8190a-172">Select a module in either the outline or the canvas.</span></span>
1. <span data-ttu-id="8190a-173">Válassza ki a modul neve mellett lévő a három pontot (**...**) a körvonal ablaktáblán vagy a modul eszköztárában található vásznon.</span><span class="sxs-lookup"><span data-stu-id="8190a-173">Select the ellipsis (**...**) next to the module's name in the outline pane, or in the module's toolbar in the canvas.</span></span>
1. <span data-ttu-id="8190a-174">Ha a modult a tárolóban vagy a helyen belül fel-le mozgathatja, akkor a **Mozgatás felfelé** vagy **Mozgatás lefelé** beállítások láthatók.</span><span class="sxs-lookup"><span data-stu-id="8190a-174">If the module can be moved up or down within the container or slot, you will see options for **Move up** or **Move down**.</span></span> <span data-ttu-id="8190a-175">Válassza ki a kívánt áthelyezési beállítást a modult származtatottjaihoz képest felfelé vagy lefelé mozgatásához.</span><span class="sxs-lookup"><span data-stu-id="8190a-175">Select the desired move option to move the module up or down relative to its siblings.</span></span>

## <a name="configure-modules"></a><span data-ttu-id="8190a-176">Modulok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="8190a-176">Configure modules</span></span>

<span data-ttu-id="8190a-177">A következő eljárások leírják a tartalom- és tárolómodulok konfigurálását.</span><span class="sxs-lookup"><span data-stu-id="8190a-177">The following procedures describe how to configure content and container modules.</span></span>

### <a name="configure-a-content-module"></a><span data-ttu-id="8190a-178">Tartalommodul konfigurálása</span><span class="sxs-lookup"><span data-stu-id="8190a-178">Configure a content module</span></span>

<span data-ttu-id="8190a-179">Egy tartalommodulnak egy lapon történő konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8190a-179">To configure a content module on a page, follow these steps.</span></span>

1. <span data-ttu-id="8190a-180">A bal oldali vázlat ablaktáblán bontsa ki a fastruktúrát, és válasszon ki egy bármilyen tartalommodult (például **Tartalomblokk**).</span><span class="sxs-lookup"><span data-stu-id="8190a-180">In the outline pane on the left, expand the tree and select any content module (for example, **Content block**).</span></span> <span data-ttu-id="8190a-181">Másik lehetőségként válassza ki azt a modult, amelyet át szeretne helyezni a fő vásznon belül.</span><span class="sxs-lookup"><span data-stu-id="8190a-181">Alternately, you can select the module in the main canvas.</span></span>
1. <span data-ttu-id="8190a-182">A jobb oldali modul tulajdonságai ablaktáblán írja be a kívánt modulvezérlők tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="8190a-182">In the module properties pane on the right, enter properties for any desired module controls.</span></span>
1. <span data-ttu-id="8190a-183">A parancssávon válassza a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="8190a-183">On the command bar, select **Save**.</span></span> <span data-ttu-id="8190a-184">Ennek hatására az előnézeti vászon is frissül.</span><span class="sxs-lookup"><span data-stu-id="8190a-184">This will also refresh the preview canvas.</span></span>

### <a name="edit-module-text-properties"></a><span data-ttu-id="8190a-185">Modul szövegtulajdonságainak szerkesztése</span><span class="sxs-lookup"><span data-stu-id="8190a-185">Edit module text properties</span></span>

<span data-ttu-id="8190a-186">A nem írásvédett modul szövegtulajdonságait közvetlenül a vásznon belül tudja szerkeszteni.</span><span class="sxs-lookup"><span data-stu-id="8190a-186">Module text properties that are not read-only can be edited directly in the canvas.</span></span>

<span data-ttu-id="8190a-187">A modul szövegtulajdonságainak szerkesztéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8190a-187">To edit module text properties, follow these steps.</span></span>

1. <span data-ttu-id="8190a-188">Válassza ki a vásznon a szövegvezérlőt, majd helyezze a mutatót oda, ahol szerkeszteni szeretné a szöveget.</span><span class="sxs-lookup"><span data-stu-id="8190a-188">Select the text control in the canvas, then place your cursor where you wish to edit text.</span></span>
1. <span data-ttu-id="8190a-189">Adja meg a szöveges tartalmat.</span><span class="sxs-lookup"><span data-stu-id="8190a-189">Enter your text content.</span></span>
1. <span data-ttu-id="8190a-190">Ha folytatni szeretné az egyéb tartalmak szerkesztését, bökjön a szövegtartalmon kívül bárhová.</span><span class="sxs-lookup"><span data-stu-id="8190a-190">Select anywhere outside the text content to continue editing other content.</span></span>

### <a name="inline-image-selection"></a><span data-ttu-id="8190a-191">Szövegközi kép kiválasztása</span><span class="sxs-lookup"><span data-stu-id="8190a-191">Inline image selection</span></span>

<span data-ttu-id="8190a-192">A nem írásvédett modul képeit közvetlenül a vászonból módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="8190a-192">Module images that are not read-only can be changed directly from the canvas.</span></span>

<span data-ttu-id="8190a-193">Egy új kép tartalommodulhoz való kiválasztásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8190a-193">To choose a new image for a content module, follow these steps.</span></span>

1. <span data-ttu-id="8190a-194">A vásznon kattintson duplán a képre.</span><span class="sxs-lookup"><span data-stu-id="8190a-194">In the canvas, double-click the image.</span></span> <span data-ttu-id="8190a-195">Ekkor megjelenik a médiaválasztó ablaka.</span><span class="sxs-lookup"><span data-stu-id="8190a-195">This will bring up the media picker window.</span></span>
1. <span data-ttu-id="8190a-196">Keresse meg és válassza ki a használni kívánt új képet, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="8190a-196">Find and select a new image you want to use, and then select **OK**.</span></span> <span data-ttu-id="8190a-197">Az új kép ezennel renderelve lett a vászonba.</span><span class="sxs-lookup"><span data-stu-id="8190a-197">The new image is now rendered in the canvas.</span></span>

### <a name="configure-a-container-module"></a><span data-ttu-id="8190a-198">Tárolómodul konfigurálása</span><span class="sxs-lookup"><span data-stu-id="8190a-198">Configure a container module</span></span>

<span data-ttu-id="8190a-199">Egy tárolómodulnak egy lapon történő konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8190a-199">To configure a container module on a page, follow these steps.</span></span>

1. <span data-ttu-id="8190a-200">Válasszon ki egy konténermodult az oldalon (például körhinta vagy folyékony tárolómodult).</span><span class="sxs-lookup"><span data-stu-id="8190a-200">Select a container module on your page (for example, a carousel or fluid container module).</span></span>
1. <span data-ttu-id="8190a-201">A jobb oldali tulajdonságok ablaktáblán bontsa ki a beágyazott vezérlőket a fejlécek kiválasztásával, és adja meg a szükséges vezérlő értékeket.</span><span class="sxs-lookup"><span data-stu-id="8190a-201">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="8190a-202">A bal oldali vázlat ablaktáblán válassza az eltávolítani tároló vagy a tároló bármelyik helye neve melletti három pont gombot, majd válassza ki a **Modul hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8190a-202">In the outline pane on the left, select the ellipsis button next to the name of either the container or any slots inside the container, and then select **Add Module**.</span></span> <span data-ttu-id="8190a-203">Ezután adja hozzá a származtatott modulokat a kiválasztott tárolóhoz.</span><span class="sxs-lookup"><span data-stu-id="8190a-203">Then, add child modules to the selected container.</span></span> <span data-ttu-id="8190a-204">A további tudnivalókat lásd: [Modulok használata](#add-a-module) rész a témakör korábbi részében.</span><span class="sxs-lookup"><span data-stu-id="8190a-204">For more information, see the [Work with modules](#add-a-module) section earlier in this topic.</span></span>
1. <span data-ttu-id="8190a-205">Ha több származtatott modul van egy szülő tárolóban, akkor a szülő tárolóban módosítható a megjelenítési sorrendjük.</span><span class="sxs-lookup"><span data-stu-id="8190a-205">If multiple child modules exist as siblings in a parent container, you can change their display order in the parent container.</span></span> <span data-ttu-id="8190a-206">Jelölje ki az egyik modulhoz tartozó három pont gombot, majd a fel és a le nyílbillentyűket.</span><span class="sxs-lookup"><span data-stu-id="8190a-206">Select the ellipsis button for a module, and then use the up arrow and down arrow buttons.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8190a-207">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8190a-207">Additional resources</span></span>

[<span data-ttu-id="8190a-208">Sablonok és elrendezések áttekintése</span><span class="sxs-lookup"><span data-stu-id="8190a-208">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="8190a-209">Sablonok használata</span><span class="sxs-lookup"><span data-stu-id="8190a-209">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="8190a-210">Előre beállított elrendezések használata</span><span class="sxs-lookup"><span data-stu-id="8190a-210">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="8190a-211">Töredékek használata</span><span class="sxs-lookup"><span data-stu-id="8190a-211">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="8190a-212">Tárolómodul hozzáadása egy oldalhoz</span><span class="sxs-lookup"><span data-stu-id="8190a-212">Add a container module to a page</span></span>](add-container-module.md)

[<span data-ttu-id="8190a-213">A közzétételi csoportokkal végzett munka</span><span class="sxs-lookup"><span data-stu-id="8190a-213">Work with publish groups</span></span>](publish-groups.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
