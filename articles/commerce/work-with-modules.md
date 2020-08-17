---
title: Modulok használata
description: Ez a témakör azt mutatja be, hogyan és mikor lehet a modulokat a Microsoft Dynamics 365 Commerce rendszerben használni.
author: v-chgri
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
ms.search.industry: ''
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: da430857801d8007244c04aadd325e99c0b882c5
ms.sourcegitcommit: 078befcd7f3531073ab2c08b365bcf132d6477b0
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/31/2020
ms.locfileid: "3646015"
---
# <a name="work-with-modules"></a><span data-ttu-id="1f09c-103">Modulok használata</span><span class="sxs-lookup"><span data-stu-id="1f09c-103">Work with modules</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="1f09c-104">Ez a témakör azt mutatja be, hogyan és mikor lehet a modulokat a Microsoft Dynamics 365 Commerce rendszerben használni.</span><span class="sxs-lookup"><span data-stu-id="1f09c-104">This topic describes how and when to use modules in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="1f09c-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="1f09c-105">Overview</span></span>

<span data-ttu-id="1f09c-106">A modulok olyan logikai építőelemek, amelyek megalkotják a lap struktúráját, és különböző céljaik és hatóköreik vannak.</span><span class="sxs-lookup"><span data-stu-id="1f09c-106">Modules are logical building blocks that make up your page structure, and they have various purposes and scopes.</span></span> <span data-ttu-id="1f09c-107">Egyes modulok magas szintű tárolók, és egyetlen céljuk a többi modul (származtatott modulok) megtartása és rendszerezése.</span><span class="sxs-lookup"><span data-stu-id="1f09c-107">Some modules are high-level containers, and their only purpose is to hold and organize other modules (child modules).</span></span> <span data-ttu-id="1f09c-108">A többi modul – például egy egyszerű képelhelyezési modul – kifejezetten konkrét célt szolgál.</span><span class="sxs-lookup"><span data-stu-id="1f09c-108">Other modules, such as a simple image placement module, have a very specific purpose.</span></span> <span data-ttu-id="1f09c-109">Más modulok, például a körhinta-modul, valahová a két kategória közé esnek.</span><span class="sxs-lookup"><span data-stu-id="1f09c-109">Other modules, such as a carousel module, fall somewhere between those two categories.</span></span>

<span data-ttu-id="1f09c-110">Alapértelmezés szerint a Dynamics 365 Commerce webhely tartalmaz egy kezdőszett modul könyvtárat, amely lehetővé teszi a legalapvetőbb e-kereskedelmi forgatókönyvek megvalósítását.</span><span class="sxs-lookup"><span data-stu-id="1f09c-110">By default, your Dynamics 365 Commerce site includes a starter kit module library that lets you achieve most basic e-Commerce scenarios.</span></span> <span data-ttu-id="1f09c-111">Kizárólag ezen modulok használatával is létrehozhat egy teljes körű e-kereskedelmi weboldalt.</span><span class="sxs-lookup"><span data-stu-id="1f09c-111">You should be able to construct an end-to-end e-Commerce site just by using these modules.</span></span> <span data-ttu-id="1f09c-112">Előfordulhat azonban, hogy testre szeretné szabni ezeket a modulokat, vagy új egyéni modulokat szeretne létrehozni adott igényekhez.</span><span class="sxs-lookup"><span data-stu-id="1f09c-112">However, you might also want to customize these modules or build new, custom modules for specific needs.</span></span> <span data-ttu-id="1f09c-113">Egyéni modulok készítéséhez egy modultervező szoftverfejlesztői készlet (SDK) érhető el, amely segítséget nyújt az egyéni modulkönyvtár létrehozásában.</span><span class="sxs-lookup"><span data-stu-id="1f09c-113">If you want to build custom modules, a module design software development kit (SDK) is available to help you create a custom module library.</span></span>

## <a name="container-modules-and-slots"></a><span data-ttu-id="1f09c-114">Tárolómodulok és helyek</span><span class="sxs-lookup"><span data-stu-id="1f09c-114">Container modules and slots</span></span>

<span data-ttu-id="1f09c-115">Ahogy korábban már említettük, néhány modul a származtatott modulok tárolásához van kialakítva.</span><span class="sxs-lookup"><span data-stu-id="1f09c-115">As was mentioned earlier, some modules are designed to hold child modules.</span></span> <span data-ttu-id="1f09c-116">Ezek a modulok *konténerként*ismertek, és lehetővé teszik a beágyazott modulok hierarchiájának létrehozását.</span><span class="sxs-lookup"><span data-stu-id="1f09c-116">These modules are known as *containers*, and they allow for hierarchies of nested modules.</span></span> <span data-ttu-id="1f09c-117">Tárolómodulok *helyeket* tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="1f09c-117">Container modules include *slots*.</span></span> <span data-ttu-id="1f09c-118">A helyek a származtatott modulok elrendezésének és céljának kezelésére szolgálnak a tárolóban.</span><span class="sxs-lookup"><span data-stu-id="1f09c-118">Slots are used to handle the layout and purpose of child modules in the container.</span></span> <span data-ttu-id="1f09c-119">Egy példa egy egyszerű laptároló modul (bármely lap felső szintű modulja), amely több fontos helyet határoz meg:</span><span class="sxs-lookup"><span data-stu-id="1f09c-119">An example is a basic page container module (a top-level module for any page) that defines several important slots:</span></span>

- <span data-ttu-id="1f09c-120">Fejléc hely</span><span class="sxs-lookup"><span data-stu-id="1f09c-120">A header slot</span></span>
- <span data-ttu-id="1f09c-121">Alfejléc hely</span><span class="sxs-lookup"><span data-stu-id="1f09c-121">A sub-header slot</span></span>
- <span data-ttu-id="1f09c-122">Fő hely</span><span class="sxs-lookup"><span data-stu-id="1f09c-122">A main slot</span></span>
- <span data-ttu-id="1f09c-123">Egy lábléc hely</span><span class="sxs-lookup"><span data-stu-id="1f09c-123">A footer slot</span></span>
- <span data-ttu-id="1f09c-124">Allábléc hely</span><span class="sxs-lookup"><span data-stu-id="1f09c-124">A sub-footer slot</span></span>

<span data-ttu-id="1f09c-125">A modul fejlesztői ezeket a helyeket definiálják, és meghatározzák, hogy mely származtatott modulokat és hány származtatott modult lehet közvetlenül benne elhelyezni.</span><span class="sxs-lookup"><span data-stu-id="1f09c-125">The module's developer defines these slots, and determines which child modules and how many child modules can be put directly inside it.</span></span> <span data-ttu-id="1f09c-126">Például a fejléc hely csak a **Fejlécmodul** típusú modult támogat, míg a törzs helyek korlátlan számú modult támogatnak (kivéve más oldaltároló modulokat).</span><span class="sxs-lookup"><span data-stu-id="1f09c-126">For example, the header slot might support only one module of the **Header Module** type, whereas the body slot might support an unlimited number of modules of any type (except other page container modules).</span></span>

<span data-ttu-id="1f09c-127">A szerkesztőeszközökben a lap szerzőjének nem kell előzetesen tudnia, hogy mely modulok helyezhetők el és nem helyezhetők el az egyes helyekre.</span><span class="sxs-lookup"><span data-stu-id="1f09c-127">In the authoring tools, page authors don't have to know in advance which modules can and can't be put in each slot.</span></span> <span data-ttu-id="1f09c-128">Amikor az oldalszerzők egy helyet kijelölnek majd megpróbálnak kiválasztani egy modult, akkor az adott helyhez tartozó modulok szűrt listáját látják.</span><span class="sxs-lookup"><span data-stu-id="1f09c-128">When page authors select a slot and then try to select a module to add to it, they see a filtered view of module types that are supported for that slot.</span></span>

## <a name="content-modules"></a><span data-ttu-id="1f09c-129">Tartalommodulok</span><span class="sxs-lookup"><span data-stu-id="1f09c-129">Content modules</span></span>

<span data-ttu-id="1f09c-130">A tartalmi modulok tartalmazzák a tartalmakat és a multimédiás elemeket, például a szöveget (például a fejléceket, a bekezdéseket és a hivatkozásokat) vagy az eszközhivatkozásokat (például képek, videók és PDF-állományok).</span><span class="sxs-lookup"><span data-stu-id="1f09c-130">Content modules contain content and media elements, such as text (for example, headlines, paragraphs, and links) or asset references (for example, images, video, and PDFs).</span></span> <span data-ttu-id="1f09c-131">A jellemző tartalmi modultípusok közé tartozik a tartalomblokk, a szövegterület és a promó bannermodulok.</span><span class="sxs-lookup"><span data-stu-id="1f09c-131">Typical content module types include content block, text block, and promo banner modules.</span></span> <span data-ttu-id="1f09c-132">Ezeknek a három típusnak a moduljai tartalmazhatnak szöveget vagy médiát, és nem igényelnek származtatott modulokat ahhoz, hogy láthatóvá tegyenek valamit egy oldalon.</span><span class="sxs-lookup"><span data-stu-id="1f09c-132">Modules of these three types can contain text or media, and they don't require any child modules to make something visible on a page.</span></span>

<span data-ttu-id="1f09c-133">Az általános, gyakran használt oldal- és tartalomszerkesztési tevékenységek többsége tartalmi modulokat tartalmaz elsősorban, mivel ezek a modulok határozzák meg a szülő tároló moduljukban megjelenített tényleges tartalmat.</span><span class="sxs-lookup"><span data-stu-id="1f09c-133">The majority of typical, day-to-day page and content authoring activities involve content modules, primarily because these modules define the actual content that is rendered in their parent container modules.</span></span> <span data-ttu-id="1f09c-134">Számos tartalmi modul érhető el, és ezek a modulok általában az utolsó darabok, amelyeket hozzáad az oldal beágyazott modulokból álló hierarchiájához.</span><span class="sxs-lookup"><span data-stu-id="1f09c-134">Many content modules are available, and these modules are typically the last pieces that you will add to a page's hierarchy of nested modules.</span></span>

<span data-ttu-id="1f09c-135">A következő ábra bemutatja, hogyan vannak a modulok a szülő tároló helyeire beágyazva.</span><span class="sxs-lookup"><span data-stu-id="1f09c-135">The following illustration shows how modules are nested inside parent container module slots.</span></span>

![Modulok beágyazása](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a><span data-ttu-id="1f09c-137">Modulok hozzáadása vagy eltávolítása</span><span class="sxs-lookup"><span data-stu-id="1f09c-137">Add or remove modules</span></span>

<span data-ttu-id="1f09c-138">A következő eljárások leírják a modulok hozzáadását és eltávolítását.</span><span class="sxs-lookup"><span data-stu-id="1f09c-138">The following procedures describe how to add and remove modules.</span></span>

### <a name="add-a-module"></a><span data-ttu-id="1f09c-139">Modul hozzáadása</span><span class="sxs-lookup"><span data-stu-id="1f09c-139">Add a module</span></span>

<span data-ttu-id="1f09c-140">A következő lépésekkel lehet hozzáadni egy modult egy helyhez vagy tárolóhoz egy lapon.</span><span class="sxs-lookup"><span data-stu-id="1f09c-140">To add a module to a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="1f09c-141">A bal oldali vázlat ablaktáblán vagy közvetlenül a fő vásznon, válassza ki azt a tárolót vagy helyet, amelyhez hozzá szeretné adni az alárendelt modult.</span><span class="sxs-lookup"><span data-stu-id="1f09c-141">In the outline pane on the left or directly in the main canvas, select a container or slot to which a child module can be added.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1f09c-142">A modultervező meghatározza azoknak a moduloknak a listáját, amelyek hozzáadhatók egy adott modulbővítőhelyhez.</span><span class="sxs-lookup"><span data-stu-id="1f09c-142">The module designer defines the list of modules types that can be added to a specific module slot.</span></span> <span data-ttu-id="1f09c-143">A sablon szerzője ezt követően finomíthatja az engedélyezett modul beállításait, így garantálva a következetes keresőmotor-optimalizálást (SEO) és szerkesztés hatékonyságát az összes olyan oldalhoz, amelyeket egy adott sablonból építettek fel.</span><span class="sxs-lookup"><span data-stu-id="1f09c-143">Template authors can then refine the allowed module options to help guarantee consistent search engine optimization (SEO) and authoring efficiency for all the pages that are built from a specific template.</span></span> <span data-ttu-id="1f09c-144">Amikor hozzáad egy modult egy helyhez, a **Modul hozzáadása** párbeszédpanelt a program automatikusan szűri, így csak a kiválasztott tárolóban vagy bővítőhelyen támogatott modulokat jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="1f09c-144">When adding a module to a slot, the **Add Module** dialog box is automatically filtered so that it shows only modules that are supported in the selected container or slot.</span></span> <span data-ttu-id="1f09c-145">Az engedélyezett modulok listáját a lap sablonja vagy a tárolómodul definíciója határozza meg.</span><span class="sxs-lookup"><span data-stu-id="1f09c-145">This list of allowed modules is determined by the page's template or the container's module definition.</span></span>

1. <span data-ttu-id="1f09c-146">Ha a körvonal ablaktáblát használja, válassza ki a modul neve melletti három pontot (**...**), majd válassza a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="1f09c-146">If using the outline pane, select the ellipsis (**...**) next to the module name, and then select **Add Module**.</span></span> <span data-ttu-id="1f09c-147">Ha közvetlenül a vásznon belül használja a vezérlőket, válassza ki a plusz jelet (**+**) egy üres helyen vagy a kiválasztott modul szomszédos helyen, majd válassza ki a **Modul hozzáadása** elemet.</span><span class="sxs-lookup"><span data-stu-id="1f09c-147">If using the controls directly within the canvas, select the plus symbol (**+**) in an empty slot or adjacent to the currently selected module, and then select **Add Module**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1f09c-148">Ha egy tároló vagy egy bővítőhely nem támogatja az új származtatott modulokat, akkor a **Modul hozzáadása** lehetőség nem érhető el.</span><span class="sxs-lookup"><span data-stu-id="1f09c-148">If a container or slot doesn't support new child modules, the **Add Module** option is unavailable.</span></span>

1. <span data-ttu-id="1f09c-149">A **Modul hozzáadása** párbeszédpanelen válasszon ki egy modult, hogy hozzáadja az oldalhoz.</span><span class="sxs-lookup"><span data-stu-id="1f09c-149">In the **Add Module** dialog box, select a module to add to your page.</span></span>

    > [!TIP]
    > <span data-ttu-id="1f09c-150">A **Tartalomblokk** kezdőknek való modultípus.</span><span class="sxs-lookup"><span data-stu-id="1f09c-150">**Content block** is a good module type for beginners to work with.</span></span>

1. <span data-ttu-id="1f09c-151">Az **OK** gombra kattintva adja hozzá a kijelölt modult a kiválasztott tárolóhoz vagy helyhez a lapon.</span><span class="sxs-lookup"><span data-stu-id="1f09c-151">Select **OK** to add the selected module to the selected container or slot on your page.</span></span>

### <a name="remove-a-module"></a><span data-ttu-id="1f09c-152">Modul eltávolítása</span><span class="sxs-lookup"><span data-stu-id="1f09c-152">Remove a module</span></span>

<span data-ttu-id="1f09c-153">A következő lépésekkel lehet eltávolítani egy modult egy helyről vagy tárolóból az oldalon.</span><span class="sxs-lookup"><span data-stu-id="1f09c-153">To remove a module from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="1f09c-154">A bal oldali vázlat ablaktáblán válassza az eltávolítani kívánt modul neve melletti három pontot (**...**), majd válassza a kuka gombját.</span><span class="sxs-lookup"><span data-stu-id="1f09c-154">In the outline pane on the left, select the ellipsis (**...**) next to the name of the module to be removed, and then select the trash can symbol.</span></span> <span data-ttu-id="1f09c-155">Másik lehetőségként a fő vászonban is kijelölheti a kiválasztott modul eszköztárán lévő kuka szimbólumot.</span><span class="sxs-lookup"><span data-stu-id="1f09c-155">Alternately, in the main canvas you can select the trash can symbol on a selected module's toolbar.</span></span>
1. <span data-ttu-id="1f09c-156">Amikor a program megkérdezi, hogy szeretné-e eltávolítani a modult, válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f09c-156">When prompted to confirm that you want to remove the module, select **OK**.</span></span>

## <a name="move-a-module-to-a-new-position"></a><span data-ttu-id="1f09c-157">Modul áthelyezése egy új pozícióba</span><span class="sxs-lookup"><span data-stu-id="1f09c-157">Move a module to a new position</span></span>

<span data-ttu-id="1f09c-158">Ha egy modult át szeretne helyezni egy új pozícióba a lapon belül, akkor használja az alábbi módszerek valamelyikét.</span><span class="sxs-lookup"><span data-stu-id="1f09c-158">To move a module to a new position within your page, use any of the following methods.</span></span>

### <a name="move-a-module-using-the-outline-pane"></a><span data-ttu-id="1f09c-159">Modul áthelyezése a körvonal ablaktábla használatával</span><span class="sxs-lookup"><span data-stu-id="1f09c-159">Move a module using the outline pane</span></span>

<span data-ttu-id="1f09c-160">Ha egy modult a körvonal ablaktáblával szeretne áthelyezni, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1f09c-160">To move a module using the outline pane, follow these steps.</span></span>

1. <span data-ttu-id="1f09c-161">Jelölje ki és tartsa lenyomva az áthelyezni kívánt modult a körvonal ablaktáblán, majd húzza át a modult a körvonalban szereplő új pozícióra.</span><span class="sxs-lookup"><span data-stu-id="1f09c-161">Select and hold the module you want to move in the outline pane, then drag the module to a new position in the outline.</span></span> <span data-ttu-id="1f09c-162">A körvonalon és a vásznon lévő kék sor jelzi, hogy hova helyezheti a modult.</span><span class="sxs-lookup"><span data-stu-id="1f09c-162">The blue line in the outline and on the canvas indicates where the module can be placed.</span></span>
1. <span data-ttu-id="1f09c-163">A modul kiadása, hogy át lehessen dobni az új pozícióba.</span><span class="sxs-lookup"><span data-stu-id="1f09c-163">Release the module to drop it into the new position.</span></span>

### <a name="move-a-module-directly-within-the-canvas"></a><span data-ttu-id="1f09c-164">Modul áthelyezése közvetlenül a vásznon belül</span><span class="sxs-lookup"><span data-stu-id="1f09c-164">Move a module directly within the canvas</span></span>

<span data-ttu-id="1f09c-165">Ha egy modult közvetlenül a vásznon belül szeretne áthelyezni, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1f09c-165">To move a module directly within the canvas, follow these steps.</span></span>

1. <span data-ttu-id="1f09c-166">Válassza ki azt a modult, amelyet át szeretne helyezni a vásznon belül.</span><span class="sxs-lookup"><span data-stu-id="1f09c-166">Select the module you want to move in the canvas.</span></span> 
1. <span data-ttu-id="1f09c-167">Válassza ki a modul eszköztárában a felfelé vagy lefelé mutató nyilat, majd húzza a nyilat a lap új helyére.</span><span class="sxs-lookup"><span data-stu-id="1f09c-167">Select either an upward or downward pointing arrow symbol in the module's toolbar, and then drag the arrow to a new position on the page.</span></span> <span data-ttu-id="1f09c-168">A vászonban és a körvonalban lévő kék sor jelzi, hogy hova helyezheti a modult.</span><span class="sxs-lookup"><span data-stu-id="1f09c-168">The blue line in the canvas and outline indicates where the module can be placed.</span></span> <span data-ttu-id="1f09c-169">Ha egy modult nem lehet felfelé vagy lefelé mozgatni, akkor a nyíl gomb szürkén jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="1f09c-169">If a module cannot be moved up or down, that arrow symbol will be grayed out.</span></span> 
1. <span data-ttu-id="1f09c-170">A modul kiadása, hogy át lehessen dobni az új pozícióba.</span><span class="sxs-lookup"><span data-stu-id="1f09c-170">Release the module to drop it into the new position.</span></span>

### <a name="move-a-module-using-the-ellipsis-menu"></a><span data-ttu-id="1f09c-171">Modul áthelyezése a három pont menü használatával</span><span class="sxs-lookup"><span data-stu-id="1f09c-171">Move a module using the ellipsis menu</span></span>

<span data-ttu-id="1f09c-172">Ha egy modult a három pont menüvel szeretne áthelyezni, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1f09c-172">To move a module using the ellipsis menu, follow these steps.</span></span>

1. <span data-ttu-id="1f09c-173">Válasszon ki egy modult a körvonalban vagy a vásznon.</span><span class="sxs-lookup"><span data-stu-id="1f09c-173">Select a module in either the outline or the canvas.</span></span>
1. <span data-ttu-id="1f09c-174">Válassza ki a modul neve mellett lévő a három pontot (**...**) a körvonal ablaktáblán vagy a modul eszköztárában található vásznon.</span><span class="sxs-lookup"><span data-stu-id="1f09c-174">Select the ellipsis (**...**) next to the module's name in the outline pane, or in the module's toolbar in the canvas.</span></span>
1. <span data-ttu-id="1f09c-175">Ha a modult a tárolóban vagy a helyen belül fel-le mozgathatja, akkor a **Mozgatás felfelé** vagy **Mozgatás lefelé** beállítások láthatók.</span><span class="sxs-lookup"><span data-stu-id="1f09c-175">If the module can be moved up or down within the container or slot, you will see options for **Move up** or **Move down**.</span></span> <span data-ttu-id="1f09c-176">Válassza ki a kívánt áthelyezési beállítást a modult származtatottjaihoz képest felfelé vagy lefelé mozgatásához.</span><span class="sxs-lookup"><span data-stu-id="1f09c-176">Select the desired move option to move the module up or down relative to its siblings.</span></span>

## <a name="configure-modules"></a><span data-ttu-id="1f09c-177">Modulok konfigurálása</span><span class="sxs-lookup"><span data-stu-id="1f09c-177">Configure modules</span></span>

<span data-ttu-id="1f09c-178">A következő eljárások leírják a tartalom- és tárolómodulok konfigurálását.</span><span class="sxs-lookup"><span data-stu-id="1f09c-178">The following procedures describe how to configure content and container modules.</span></span>

### <a name="configure-a-content-module"></a><span data-ttu-id="1f09c-179">Tartalommodul konfigurálása</span><span class="sxs-lookup"><span data-stu-id="1f09c-179">Configure a content module</span></span>

<span data-ttu-id="1f09c-180">Egy tartalommodulnak egy lapon történő konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1f09c-180">To configure a content module on a page, follow these steps.</span></span>

1. <span data-ttu-id="1f09c-181">A bal oldali vázlat ablaktáblán bontsa ki a fastruktúrát, és válasszon ki egy bármilyen tartalommodult (például **Tartalomblokk**).</span><span class="sxs-lookup"><span data-stu-id="1f09c-181">In the outline pane on the left, expand the tree and select any content module (for example, **Content block**).</span></span> <span data-ttu-id="1f09c-182">Másik lehetőségként válassza ki azt a modult, amelyet át szeretne helyezni a fő vásznon belül.</span><span class="sxs-lookup"><span data-stu-id="1f09c-182">Alternately, you can select the module in the main canvas.</span></span>
1. <span data-ttu-id="1f09c-183">A jobb oldali modul tulajdonságai ablaktáblán írja be a kívánt modulvezérlők tulajdonságait.</span><span class="sxs-lookup"><span data-stu-id="1f09c-183">In the module properties pane on the right, enter properties for any desired module controls.</span></span>
1. <span data-ttu-id="1f09c-184">A parancssávon válassza a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="1f09c-184">On the command bar, select **Save**.</span></span> <span data-ttu-id="1f09c-185">Ennek hatására az előnézeti vászon is frissül.</span><span class="sxs-lookup"><span data-stu-id="1f09c-185">This will also refresh the preview canvas.</span></span>

### <a name="edit-module-text-properties"></a><span data-ttu-id="1f09c-186">Modul szövegtulajdonságainak szerkesztése</span><span class="sxs-lookup"><span data-stu-id="1f09c-186">Edit module text properties</span></span>

<span data-ttu-id="1f09c-187">A nem írásvédett modul szövegtulajdonságait közvetlenül a vásznon belül tudja szerkeszteni.</span><span class="sxs-lookup"><span data-stu-id="1f09c-187">Module text properties that are not read-only can be edited directly in the canvas.</span></span>

<span data-ttu-id="1f09c-188">A modul szövegtulajdonságainak szerkesztéséhez kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1f09c-188">To edit module text properties, follow these steps.</span></span>

1. <span data-ttu-id="1f09c-189">Válassza ki a vásznon a szövegvezérlőt, majd helyezze a mutatót oda, ahol szerkeszteni szeretné a szöveget.</span><span class="sxs-lookup"><span data-stu-id="1f09c-189">Select the text control in the canvas, then place your cursor where you wish to edit text.</span></span>
1. <span data-ttu-id="1f09c-190">Adja meg a szöveges tartalmat.</span><span class="sxs-lookup"><span data-stu-id="1f09c-190">Enter your text content.</span></span>
1. <span data-ttu-id="1f09c-191">Ha folytatni szeretné az egyéb tartalmak szerkesztését, bökjön a szövegtartalmon kívül bárhová.</span><span class="sxs-lookup"><span data-stu-id="1f09c-191">Select anywhere outside the text content to continue editing other content.</span></span>

### <a name="inline-image-selection"></a><span data-ttu-id="1f09c-192">Szövegközi kép kiválasztása</span><span class="sxs-lookup"><span data-stu-id="1f09c-192">Inline image selection</span></span>

<span data-ttu-id="1f09c-193">A nem írásvédett modul képeit közvetlenül a vászonból módosíthatja.</span><span class="sxs-lookup"><span data-stu-id="1f09c-193">Module images that are not read-only can be changed directly from the canvas.</span></span>

<span data-ttu-id="1f09c-194">Egy új kép tartalommodulhoz való kiválasztásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1f09c-194">To choose a new image for a content module, follow these steps.</span></span>

1. <span data-ttu-id="1f09c-195">A vásznon kattintson duplán a képre.</span><span class="sxs-lookup"><span data-stu-id="1f09c-195">In the canvas, double-click the image.</span></span> <span data-ttu-id="1f09c-196">Ekkor megjelenik a médiaválasztó ablaka.</span><span class="sxs-lookup"><span data-stu-id="1f09c-196">This will bring up the media picker window.</span></span>
1. <span data-ttu-id="1f09c-197">Keresse meg és válassza ki a használni kívánt új képet, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="1f09c-197">Find and select a new image you want to use, and then select **OK**.</span></span> <span data-ttu-id="1f09c-198">Az új kép ezennel renderelve lett a vászonba.</span><span class="sxs-lookup"><span data-stu-id="1f09c-198">The new image is now rendered in the canvas.</span></span>

### <a name="configure-a-container-module"></a><span data-ttu-id="1f09c-199">Tárolómodul konfigurálása</span><span class="sxs-lookup"><span data-stu-id="1f09c-199">Configure a container module</span></span>

<span data-ttu-id="1f09c-200">Egy tárolómodulnak egy lapon történő konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="1f09c-200">To configure a container module on a page, follow these steps.</span></span>

1. <span data-ttu-id="1f09c-201">Válasszon ki egy konténermodult az oldalon (például körhinta vagy folyékony tárolómodult).</span><span class="sxs-lookup"><span data-stu-id="1f09c-201">Select a container module on your page (for example, a carousel or fluid container module).</span></span>
1. <span data-ttu-id="1f09c-202">A jobb oldali tulajdonságok ablaktáblán bontsa ki a beágyazott vezérlőket a fejlécek kiválasztásával, és adja meg a szükséges vezérlő értékeket.</span><span class="sxs-lookup"><span data-stu-id="1f09c-202">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="1f09c-203">A bal oldali vázlat ablaktáblán válassza az eltávolítani tároló vagy a tároló bármelyik helye neve melletti három pont gombot, majd válassza ki a **Modul hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1f09c-203">In the outline pane on the left, select the ellipsis button next to the name of either the container or any slots inside the container, and then select **Add Module**.</span></span> <span data-ttu-id="1f09c-204">Ezután adja hozzá a származtatott modulokat a kiválasztott tárolóhoz.</span><span class="sxs-lookup"><span data-stu-id="1f09c-204">Then, add child modules to the selected container.</span></span> <span data-ttu-id="1f09c-205">A további tudnivalókat lásd: [Modulok használata](#add-a-module) rész a témakör korábbi részében.</span><span class="sxs-lookup"><span data-stu-id="1f09c-205">For more information, see the [Work with modules](#add-a-module) section earlier in this topic.</span></span>
1. <span data-ttu-id="1f09c-206">Ha több származtatott modul van egy szülő tárolóban, akkor a szülő tárolóban módosítható a megjelenítési sorrendjük.</span><span class="sxs-lookup"><span data-stu-id="1f09c-206">If multiple child modules exist as siblings in a parent container, you can change their display order in the parent container.</span></span> <span data-ttu-id="1f09c-207">Jelölje ki az egyik modulhoz tartozó három pont gombot, majd a fel és a le nyílbillentyűket.</span><span class="sxs-lookup"><span data-stu-id="1f09c-207">Select the ellipsis button for a module, and then use the up arrow and down arrow buttons.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1f09c-208">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1f09c-208">Additional resources</span></span>

[<span data-ttu-id="1f09c-209">Sablonok és elrendezések áttekintése</span><span class="sxs-lookup"><span data-stu-id="1f09c-209">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="1f09c-210">Sablonok használata</span><span class="sxs-lookup"><span data-stu-id="1f09c-210">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="1f09c-211">Előre beállított elrendezések használata</span><span class="sxs-lookup"><span data-stu-id="1f09c-211">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="1f09c-212">Töredékek használata</span><span class="sxs-lookup"><span data-stu-id="1f09c-212">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="1f09c-213">Tárolómodul hozzáadása egy oldalhoz</span><span class="sxs-lookup"><span data-stu-id="1f09c-213">Add a container module to a page</span></span>](add-container-module.md)

[<span data-ttu-id="1f09c-214">A közzétételi csoportokkal végzett munka</span><span class="sxs-lookup"><span data-stu-id="1f09c-214">Work with publish groups</span></span>](publish-groups.md)

