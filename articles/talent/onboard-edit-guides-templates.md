---
title: Bevezetési útmutatók és sablonok szerkesztése a Dynamics 365 Talent – Onboard szolgáltatásban
description: Ez a témakör azt mutatja be, hogyan lehet tevékenységeket és egyéb információkat hozzáadni a Microsoft Dynamics 365 Talent – Onboard felvételi útmutatóihoz és sablonjaihoz.
author: andreabichsel
manager: ''
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-06-19
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 291f7aefac61c26dfab81cfff28c1c6580d46de5
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897120"
---
# <a name="edit-onboarding-guides-and-templates"></a><span data-ttu-id="182b0-103">Bevezetési útmutatók és sablonok szerkesztése</span><span class="sxs-lookup"><span data-stu-id="182b0-103">Edit onboarding guides and templates</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="182b0-104">Miután létrehozta a felvételi útmutatót vagy sablont a Microsoft Dynamics 365 Talent: Onboard szolgáltatásban, hozzá kell adnia egy bevezetést, a tevékenységeket, a kapcsolattartókat és az erőforrásokat.</span><span class="sxs-lookup"><span data-stu-id="182b0-104">After you create an onboarding guide or template in Microsoft Dynamics 365 Talent: Onboard, you must add an introduction, activities, contacts, and resources.</span></span> <span data-ttu-id="182b0-105">Az Onboard segítségével multimédiás tartalmakat adhat felvételi útmutatóihoz, például a következő lehetőségek közül választhat:</span><span class="sxs-lookup"><span data-stu-id="182b0-105">Onboard lets you include rich content in your onboarding guides, including:</span></span>

- <span data-ttu-id="182b0-106">YouTube-videók</span><span class="sxs-lookup"><span data-stu-id="182b0-106">YouTube videos</span></span>
- <span data-ttu-id="182b0-107">Microsoft Sway-bemutatók</span><span class="sxs-lookup"><span data-stu-id="182b0-107">Microsoft Sway presentations</span></span>
- <span data-ttu-id="182b0-108">Microsoft PowerApps-alkalmazásoknak</span><span class="sxs-lookup"><span data-stu-id="182b0-108">Microsoft PowerApps apps</span></span>
- <span data-ttu-id="182b0-109">Microsoft Stream-videók</span><span class="sxs-lookup"><span data-stu-id="182b0-109">Microsoft Stream videos</span></span>
- <span data-ttu-id="182b0-110">Microsoft Forms-űrlapok</span><span class="sxs-lookup"><span data-stu-id="182b0-110">Microsoft Forms forms</span></span>
- <span data-ttu-id="182b0-111">Iframe elemek webes tartalommal</span><span class="sxs-lookup"><span data-stu-id="182b0-111">Iframes that contains web content</span></span>

## <a name="edit-introductions-or-activities-imported-from-a-template"></a><span data-ttu-id="182b0-112">Sablonból importált bevezetések és tevékenységek szerkesztése</span><span class="sxs-lookup"><span data-stu-id="182b0-112">Edit introductions or activities imported from a template</span></span>

<span data-ttu-id="182b0-113">Ha sablon alapján hoz létre felvételi útmutatót, vagy ha egy sablonból tevékenységeket importál egy másikba, akkor az importált tevékenységeknél **Zárolás** gomb látható.</span><span class="sxs-lookup"><span data-stu-id="182b0-113">If you create an onboarding guide from a template, or if you import activities from one template into another, you'll notice a **Lock** button on the imported activities.</span></span> <span data-ttu-id="182b0-114">Ezeket *felügyelt tevékenységeknek* nevezzük.</span><span class="sxs-lookup"><span data-stu-id="182b0-114">These are called *managed activities*.</span></span>

<span data-ttu-id="182b0-115">[![Felügyelt tevékenységek](./media/onboard-edit-guide-managed-activities.png)](./media/onboard-edit-guide-managed-activities.png)</span><span class="sxs-lookup"><span data-stu-id="182b0-115">[![Managed activities](./media/onboard-edit-guide-managed-activities.png)](./media/onboard-edit-guide-managed-activities.png)</span></span>

<span data-ttu-id="182b0-116">Felügyelt tevékenység kiválasztása esetén a tevékenység tetején látható a forrássablon.</span><span class="sxs-lookup"><span data-stu-id="182b0-116">When you select a managed activity, you can see the source template at the top of the activity.</span></span>

<span data-ttu-id="182b0-117">[![Felügyelt tevékenység forrása](./media/onboard-edit-guide-managed-activity-source.png)](./media/onboard-edit-guide-managed-activity-source.png)</span><span class="sxs-lookup"><span data-stu-id="182b0-117">[![Managed activity source](./media/onboard-edit-guide-managed-activity-source.png)](./media/onboard-edit-guide-managed-activity-source.png)</span></span>

<span data-ttu-id="182b0-118">Ha egy sablonban szerkeszt egy tevékenységet, az Onboard a sablonon alapuló összes sablonnál és elküldetlen útmutatónál érvényesíti a módosításokat.</span><span class="sxs-lookup"><span data-stu-id="182b0-118">If you edit an activity in a template, Onboard will push the changes to all templates and unsent guides that are based on that template.</span></span> <span data-ttu-id="182b0-119">Ha egy Ön által szerkesztett sablon alapján kiválasz egy nem elküldött útmutatót, majd kiválasztja a **Tevékenységek** lapot az útmutatóban, akkor értesítés jelenik meg arról, hogy módosult az útmutató.</span><span class="sxs-lookup"><span data-stu-id="182b0-119">If you select an unsent guide based on a template you edited and then select the **Activities** tab in the guide, you will see a notice that your guide has changed.</span></span> <span data-ttu-id="182b0-120">Az értesítés elvetéséhez kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="182b0-120">To dismiss the notification, select **OK**.</span></span> 

<span data-ttu-id="182b0-121">[![Értesítés módosításról](./media/onboard-edit-guide-change-notification.png)](./media/onboard-edit-guide-change-notification.png)</span><span class="sxs-lookup"><span data-stu-id="182b0-121">[![Change notification](./media/onboard-edit-guide-change-notification.png)](./media/onboard-edit-guide-change-notification.png)</span></span>

<span data-ttu-id="182b0-122">A frissített tevékenységek mellett megjelenik egy fekete pötty.</span><span class="sxs-lookup"><span data-stu-id="182b0-122">You'll see a black dot next to the updated activities.</span></span>

<span data-ttu-id="182b0-123">[![Módosult tevékenység](./media/onboard-edit-guide-changed-activity.png)](./media/onboard-edit-guide-changed-activity.png)</span><span class="sxs-lookup"><span data-stu-id="182b0-123">[![Changed activity](./media/onboard-edit-guide-changed-activity.png)](./media/onboard-edit-guide-changed-activity.png)</span></span>

<span data-ttu-id="182b0-124">Az eredeti sablonon kívül nem szerkesztheti a felügyelt tevékenységeket, kivéve, ha hozzá kíván adni egy megbízottat, egy esedékességi dátumot vagy más információt a tevékenység jobb oldali szakaszában.</span><span class="sxs-lookup"><span data-stu-id="182b0-124">You can't edit managed activities outside of the original template, except to add an assignee, due date, or other information in the right-hand section of the activity.</span></span>

<span data-ttu-id="182b0-125">Ha egy felügyelt tevékenységet szeretne szerkeszteni, vagy ha nem szeretné, hogy egy tevékenység frissítéseket kapjon a sablonból, válassza ki a **Zárolás** gombot az adott tevékenységnél.</span><span class="sxs-lookup"><span data-stu-id="182b0-125">If you want to edit a managed activity, or if you don't want an activity to receive updates from the template it came from, select the **Lock** button for that activity.</span></span> <span data-ttu-id="182b0-126">A **Zárolás** gomb eltűnik.</span><span class="sxs-lookup"><span data-stu-id="182b0-126">The **Lock** button will disappear.</span></span> <span data-ttu-id="182b0-127">A tevékenység kezelését a továbbiakban már nem az eredeti sablon végzi, és a továbbiakban nem fog kapni a sablonból származó frissítéseket.</span><span class="sxs-lookup"><span data-stu-id="182b0-127">The activity will no longer be managed by the original template, and it will no longer receive updates from that template.</span></span> <span data-ttu-id="182b0-128">A tevékenységhez tartozó módosítások nincsenek hatással az eredeti sablonra.</span><span class="sxs-lookup"><span data-stu-id="182b0-128">Updates you make to an activity do not affect the original template.</span></span>

<span data-ttu-id="182b0-129">Ha egy tevékenységet töröl egy útmutatóból, és átküldi az adott útmutató sablonjának változásait, akkor a program az útmutatóban is törli a tevékenységet.</span><span class="sxs-lookup"><span data-stu-id="182b0-129">If you delete an activity from a guide and push changes from that guide's template, the activity will remain deleted in the guide.</span></span>

> [!NOTE]
> <span data-ttu-id="182b0-130">A kapcsolattartók és az erőforrások nem kezelhetők a sablonokkal.</span><span class="sxs-lookup"><span data-stu-id="182b0-130">Contacts and resources aren't managed by templates.</span></span> <span data-ttu-id="182b0-131">Ezenkívül a szakaszok nem kezelhetők, így ha egy sablonban hozzáad vagy szerkeszt egy szakaszt, akkor a módosítások nem kerülnek át a sablont használó egyik útmutatóba vagy sablonba sem.</span><span class="sxs-lookup"><span data-stu-id="182b0-131">In addition, sections aren't managed, so if you add or edit a section in a template, the changes won't be pushed to any guides or templates that use that template.</span></span>
> 
> <span data-ttu-id="182b0-132">Ha új tevékenységeket ad egy sablonhoz, akkor az új tevékenységeket a program a sablon alapján átirányítja az útmutatókhoz és a sablonokhoz, és az új tevékenységek a lap tetején jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="182b0-132">If you add new activities to a template, the new activities are pushed to guides and templates based on that template, and the new activities display at the top.</span></span>

## <a name="import-activities-from-another-template"></a><span data-ttu-id="182b0-133">Tevékenységek importálása egy másik sablonból</span><span class="sxs-lookup"><span data-stu-id="182b0-133">Import activities from another template</span></span>

<span data-ttu-id="182b0-134">Egy vagy több sablonból származó tevékenységeket importálhat egy útmutatóba vagy sablonba.</span><span class="sxs-lookup"><span data-stu-id="182b0-134">You can import activities from one or more templates into a guide or template.</span></span>

1. <span data-ttu-id="182b0-135">Jelölje ki a szerkeszteni kívánt sablont vagy útmutatót.</span><span class="sxs-lookup"><span data-stu-id="182b0-135">Select the guide or template you want to edit.</span></span>

2. <span data-ttu-id="182b0-136">Válassza ki a **Tevékenységek** lapot.</span><span class="sxs-lookup"><span data-stu-id="182b0-136">Select the **Activities** tab.</span></span>

3. <span data-ttu-id="182b0-137">Válassza az **Importálás** lapot a jobb oldali szakaszon.</span><span class="sxs-lookup"><span data-stu-id="182b0-137">Select the **Import** tab in the section on the right.</span></span>

   <span data-ttu-id="182b0-138">[![Tevékenységek importálása](./media/onboard-edit-guide-import-activities.png)](./media/onboard-edit-guide-import-activities.png)</span><span class="sxs-lookup"><span data-stu-id="182b0-138">[![Import activities](./media/onboard-edit-guide-import-activities.png)](./media/onboard-edit-guide-import-activities.png)</span></span>

4. <span data-ttu-id="182b0-139">A feladatok új lapon történő előnézetéhez válassza ki a **Megnyitás új lapon** gombot bármelyik sablonon.</span><span class="sxs-lookup"><span data-stu-id="182b0-139">To preview the tasks in a new tab in your browser, select the **Open in new tab** button on any template.</span></span>

   <span data-ttu-id="182b0-140">[![Tevékenységek importálása](./media/onboard-edit-guide-preview-activities.png)](./media/onboard-edit-guide-preview-activities.png)</span><span class="sxs-lookup"><span data-stu-id="182b0-140">[![Import activities](./media/onboard-edit-guide-preview-activities.png)](./media/onboard-edit-guide-preview-activities.png)</span></span>

5. <span data-ttu-id="182b0-141">Húzza a kívánt sablont az útmutató azon részére, ahol szeretné, hogy a tevékenységek megjelenjenek.</span><span class="sxs-lookup"><span data-stu-id="182b0-141">Drag and drop the desired template to the place in your guide template where you want the activities to appear.</span></span> <span data-ttu-id="182b0-142">Folytassa az útmutató vagy a sablon szerkesztését.</span><span class="sxs-lookup"><span data-stu-id="182b0-142">Continue editing your guide or template.</span></span>

<span data-ttu-id="182b0-143">Az importált tevékenységek **Zárolás** gombot tartalmaznak, amely jelzi, hogy az adott tevékenységeket az a sablon kezeli, ahonnan az importálást végezte.</span><span class="sxs-lookup"><span data-stu-id="182b0-143">The imported activities will contain a **Lock** button, which indicates those activities are managed by the template you imported from.</span></span> <span data-ttu-id="182b0-144">Ha módosítja az importált sablont, akkor ezek a tevékenységek frissülnek abban a sablonban is, amelyikbe importálta őket.</span><span class="sxs-lookup"><span data-stu-id="182b0-144">When you make changes to the template you imported, those activities will update in the template you imported them to.</span></span> <span data-ttu-id="182b0-145">A változtatások azonban nem kerülnek át automatikusan minden olyan útmutatóba, amely az importált sablonból jön létre.</span><span class="sxs-lookup"><span data-stu-id="182b0-145">However, the changes will not be pushed automatically to any guides created from the template you imported to.</span></span>

## <a name="push-changes-from-a-template-to-other-templates-or-guides"></a><span data-ttu-id="182b0-146">Sablonbeli módosítások elküldése más sablonokba vagy útmutatókba</span><span class="sxs-lookup"><span data-stu-id="182b0-146">Push changes from a template to other templates or guides</span></span>

<span data-ttu-id="182b0-147">Ha szerkeszt egy olyan sablont, amely más sablonok vagy útmutatók által használt tevékenységeket tartalmaz, akkor a változtatásokat érvényesítenie kell, ha azt szeretné, hogy megjelenjenek a többi sablonban vagy útmutatóban.</span><span class="sxs-lookup"><span data-stu-id="182b0-147">If you edit a template that contains activities that are used in other templates or guides, you must push the changes if you want them to appear in the other templates or guides.</span></span>

<span data-ttu-id="182b0-148">Ha nem tudja biztosan, hogy a sablonban szereplő tevékenységeket használják-e más sablonok vagy útmutatók, akkor válassza az **Itt használatos** lehetőséget annak megtekintéséhez, hogy hol jelennek meg az adott tevékenységek.</span><span class="sxs-lookup"><span data-stu-id="182b0-148">If you're not sure whether your template's activities are used in other templates or guides, select the **Used in** tab to view where those activities appear.</span></span>

   <span data-ttu-id="182b0-149">[![Azon útmutatók és sablonok megtekintése, melyekben szerepelnek tevékenységek](./media/onboard-edit-guide-view-used-in.png)](./media/onboard-edit-guide-view-used-in.png)</span><span class="sxs-lookup"><span data-stu-id="182b0-149">[![View guides and templates activities are used in](./media/onboard-edit-guide-view-used-in.png)](./media/onboard-edit-guide-view-used-in.png)</span></span>

<span data-ttu-id="182b0-150">A módosítások érvényesítése:</span><span class="sxs-lookup"><span data-stu-id="182b0-150">To push your changes:</span></span>

1. <span data-ttu-id="182b0-151">A változtatások mentéséhez kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="182b0-151">Save your changes by selecting the **Save** button.</span></span> <span data-ttu-id="182b0-152">Ha ezt nem teszi meg, a program a következő lépésben megkérdezi, hogy menti-e a változtatásokat.</span><span class="sxs-lookup"><span data-stu-id="182b0-152">If you don't do this, you'll be prompted to save your changes in the next step.</span></span>

2. <span data-ttu-id="182b0-153">Válassza a **Módosítások áttolása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="182b0-153">Select **Push these changes**.</span></span>

   
## <a name="add-or-edit-an-introduction"></a><span data-ttu-id="182b0-154">Bevezetés hozzáadása vagy szerkesztése</span><span class="sxs-lookup"><span data-stu-id="182b0-154">Add or edit an introduction</span></span>

1. <span data-ttu-id="182b0-155">A **Bevezetés** lapon adja meg az útmutató címét és egy nyitó üzenetet.</span><span class="sxs-lookup"><span data-stu-id="182b0-155">On the **Introduction** tab, enter a title for your guide and an opening message.</span></span> <span data-ttu-id="182b0-156">A minta szövegének használatához válassza az **Adott üzenet használata** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="182b0-156">To use the sample text, select **Use this message**.</span></span>

    <span data-ttu-id="182b0-157">[![Bevezetés lap az Onboard sablonban](./media/onboard-template-introduction.png)](./media/onboard-template-introduction.png)</span><span class="sxs-lookup"><span data-stu-id="182b0-157">[![Introduction tab in an Onboard template](./media/onboard-template-introduction.png)](./media/onboard-template-introduction.png)</span></span>

2. <span data-ttu-id="182b0-158">A formázás gombjaival a szükséges szöveget kiemelhet, valamint képeket és hivatkozásokat is felvehet.</span><span class="sxs-lookup"><span data-stu-id="182b0-158">Use the formatting buttons to call out text as you require, or to add images or links.</span></span>
3. <span data-ttu-id="182b0-159">A munka mentéséhez válassza a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="182b0-159">Select **Save** to save your work.</span></span>

## <a name="add-or-edit-activities"></a><span data-ttu-id="182b0-160">Tevékenységek hozzáadása és szerkesztése</span><span class="sxs-lookup"><span data-stu-id="182b0-160">Add or edit activities</span></span>

1. <span data-ttu-id="182b0-161">A **Tevékenységek** lapon húzza a jobb oldali elemeket a szerkesztési területre.</span><span class="sxs-lookup"><span data-stu-id="182b0-161">On the **Activities** tab, drag items from the right to the editing area.</span></span>
2. <span data-ttu-id="182b0-162">Az útmutató szakaszokba történő rendezéséhez húzza az **Új szakasz** elemet a szerkesztési területre, és adjon meg egy nevet és opcionálisan egy leírást a szakaszhoz.</span><span class="sxs-lookup"><span data-stu-id="182b0-162">To organize your guide into sections, drag the **New section** item to the editing area, and enter a name and an optional description for the section.</span></span>

    ![[<span data-ttu-id="182b0-163">Új szakasz hozzáadása egy felvételi útmutatóhoz vagy sablonhoz</span><span class="sxs-lookup"><span data-stu-id="182b0-163">Adding a new section to an onboarding guide or template</span></span>](./media/onboard-edit-add-section.png)](./media/onboard-edit-add-section.png)

3. <span data-ttu-id="182b0-164">Ha az új alkalmazott számára elvégzendő tevékenységeket szeretne hozzáadni, húzza az **Új tevékenység** elemet a szerkesztési területre, és adja meg a tevékenység nevét és leírását.</span><span class="sxs-lookup"><span data-stu-id="182b0-164">To add activities for your new hire to complete, drag the **New activity** item to the editing area, and enter a name and description for the activity.</span></span>

    ![[<span data-ttu-id="182b0-165">Új tevékenység hozzáadása egy felvételi útmutatóhoz vagy sablonhoz</span><span class="sxs-lookup"><span data-stu-id="182b0-165">Adding a new activity to an onboarding guide or template</span></span>](./media/onboard-edit-add-activity.png)](./media/onboard-edit-add-activity.png)

4. <span data-ttu-id="182b0-166">Multimédiás tartalom hozzáadása a felvételi útmutatóhoz:</span><span class="sxs-lookup"><span data-stu-id="182b0-166">Add rich content to your onboarding guide:</span></span>

    - <span data-ttu-id="182b0-167">A YouTube-videoklipek hozzáadásához húzza a **YouTube** elemet a szerkesztési területre, adja meg a tevékenység nevét és leírását, és adja meg a YouTube-videoklip URL-címét.</span><span class="sxs-lookup"><span data-stu-id="182b0-167">To add a YouTube video, drag the **YouTube** item to the editing area, enter a name and description for the activity, and enter the URL for the YouTube video.</span></span>
    - <span data-ttu-id="182b0-168">A Sway-bemutató vagy -hírlevél hozzáadásához húzza a **Sway** elemet a szerkesztési területre, adja meg a tevékenység nevét és leírását, és adja meg az Sway-bemutató vagy -hírlevél beágyazott URL-jét.</span><span class="sxs-lookup"><span data-stu-id="182b0-168">To add a Sway presentation or newsletter, drag the **Sway** item to the editing area, enter a name and description for the activity, and enter the embedded URL for the Sway presentation or newsletter.</span></span>
    - <span data-ttu-id="182b0-169">Ha Microsoft Power Apps-alkalmazást szeretne hozzáadni, húzza át a **Power Apps** elemet a szerkesztési területre, adja meg a tevékenység nevét és leírását, majd válassza ki a Power Apps-alkalmazást, illetve írja be a Power Apps-alkalmazásazonosítót.</span><span class="sxs-lookup"><span data-stu-id="182b0-169">To add a Microsoft Power Apps app, drag the **Power Apps** item to the editing area, enter a name and description for the activity, and either select the Power Apps app or enter the Power Apps app ID.</span></span>
    - <span data-ttu-id="182b0-170">A Microsoft Stream-videoklipek hozzáadásához húzza a **Microsoft Stream** elemet a szerkesztési területre, adja meg a tevékenység nevét és leírását, és adja meg a Microsoft Stream-videoklip URL-címét.</span><span class="sxs-lookup"><span data-stu-id="182b0-170">To add a Microsoft Stream video, drag the **Microsoft Stream** item to the editing area, enter a name and description for the activity, and enter the URL for the Microsoft Stream video.</span></span>
    - <span data-ttu-id="182b0-171">Microsoft Forms-űrlap hozzáadásához húzza a **Microsoft Forms** elemet a szerkesztési területre, adja meg a tevékenység nevét és leírását, adja meg a Microsoft Forms-űrlap URL-címét, majd adja meg a képernyőterület méretét.</span><span class="sxs-lookup"><span data-stu-id="182b0-171">To add a Microsoft Forms form, drag the **Microsoft Forms** item to the editing area, enter a name and description for the activity, enter the URL for the Microsoft Forms form, and specify the size of the screen area.</span></span>
    - <span data-ttu-id="182b0-172">Webes tartalmat tartalmazó iframe hozzáadásához húzza a **Webes tartalom (iframe)** elemet a szerkesztési területre, adja meg a tevékenység nevét és leírását, adja meg a webes tartalom URL-címét, majd adja meg a képernyőterület méretét.</span><span class="sxs-lookup"><span data-stu-id="182b0-172">To add an iframe that contains web content, drag the **Web Content (iframe)** item to the editing area, enter a name and description for the activity, enter the URL for the web content, and specify the size of the screen area.</span></span>

    ![[<span data-ttu-id="182b0-173">Multimédiás tartalom hozzáadása egy felvételi útmutatóhoz vagy sablonhoz</span><span class="sxs-lookup"><span data-stu-id="182b0-173">Adding rich content to an onboarding guide or template</span></span>](./media/onboard-edit-add-rich-content.png)](./media/onboard-edit-add-rich-content.png)

2. <span data-ttu-id="182b0-174">Nem kötelező: az egyes tevékenységektől jobbra található területen a tevékenységet hozzárendelheti egy adott személyhez vagy szerepkörhöz, hozzáadhatja a határidőt és a kapcsolattartót, és hozzárendelheti a kategória színét.</span><span class="sxs-lookup"><span data-stu-id="182b0-174">Optional: In the area on the right of each activity, assign the activity to a specific person or role, add a due date and contact person, and assign a category color.</span></span> <span data-ttu-id="182b0-175">Ha egy tevékenységet egy személyhez vagy egy szerepkörhöz rendel, akkor minden egyes személyhez létrejön egy-egy feladat.</span><span class="sxs-lookup"><span data-stu-id="182b0-175">When you assign an activity to a person or role, a task is created for each individual.</span></span> <span data-ttu-id="182b0-176">Ez a feladat az Onboard **Feladatok** menüjében jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="182b0-176">This task appears on the **Tasks** menu in Onboard.</span></span>

    <span data-ttu-id="182b0-177">[![Tevékenység hozzárendelése a felvételi útmutatóban vagy sablonban](./media/onboard-assign-activity.png)](./media/onboard-assign-activity.png)</span><span class="sxs-lookup"><span data-stu-id="182b0-177">[![Assigning an activity in an onboarding guide or template](./media/onboard-assign-activity.png)](./media/onboard-assign-activity.png)</span></span>

3. <span data-ttu-id="182b0-178">A munka mentéséhez válassza a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="182b0-178">Select **Save** to save your work.</span></span>

<span data-ttu-id="182b0-179">Tevékenység vagy szakasz törléséhez válassza a **Törlés** gombot (kuka szimbólum) a tevékenység vagy szakasz jobb felső sarkában.</span><span class="sxs-lookup"><span data-stu-id="182b0-179">To delete an activity or section, select the **Delete** button (the trash can symbol) in the upper-right corner of the activity or section.</span></span>

<span data-ttu-id="182b0-180">A tevékenységek és szakaszok átrendezéséhez húzza át őket egy új helyre.</span><span class="sxs-lookup"><span data-stu-id="182b0-180">To rearrange activities and sections, drag them to a new location.</span></span>

## <a name="add-or-edit-contacts"></a><span data-ttu-id="182b0-181">Névjegyek hozzáadása és szerkesztése</span><span class="sxs-lookup"><span data-stu-id="182b0-181">Add or edit contacts</span></span>

<span data-ttu-id="182b0-182">Felvehet kapcsolattartókat, akik segíthetik az új alkalmazott sikerességét már az első naptól kezdve.</span><span class="sxs-lookup"><span data-stu-id="182b0-182">You can add contact people who can help your new hire succeed from day one.</span></span> <span data-ttu-id="182b0-183">Ezek a kapcsolattartók lehetnek toborzók, csapattársak, segítők, mentorok, adminisztrátorok és informatikai szakemberek is.</span><span class="sxs-lookup"><span data-stu-id="182b0-183">These contacts can be recruiters, teammates, onboarding buddies, mentors, admins, and IT support staff.</span></span>

1. <span data-ttu-id="182b0-184">A **Névjegyek** lapon válassza az **Új névjegy** elemet.</span><span class="sxs-lookup"><span data-stu-id="182b0-184">On the **Contacts** tab, select **New contact**.</span></span>
2. <span data-ttu-id="182b0-185">A **Csapattag hozzáadása** párbeszédpanelen írja be a kapcsolattartó nevét vagy e-mail-címét, adja meg azt a rövid leírást, amely leírja, hogy a kapcsolattartó milyen módon segít az új alkalmazottnak, majd válassza a **Hozzáadás** elemet.</span><span class="sxs-lookup"><span data-stu-id="182b0-185">In the **Add team member** dialog box, enter the contact person's name or email address, enter a short description that explains how the contact person can help the new hire, and then select **Add**.</span></span> 

    ![[<span data-ttu-id="182b0-186">Kapcsolattartók hozzáadása egy felvételi útmutatóhoz vagy sablonhoz</span><span class="sxs-lookup"><span data-stu-id="182b0-186">Adding contacts to an onboarding guide or template</span></span>](./media/onboard-edit-add-contact.png)](./media/onboard-edit-add-contact.png)

    <span data-ttu-id="182b0-187">Másik megoldásként a **Javaslatok** között kiválaszthat egy vagy több kapcsolattartót.</span><span class="sxs-lookup"><span data-stu-id="182b0-187">Alternately, you can select one or more contacts under **Suggestions**.</span></span>

3. <span data-ttu-id="182b0-188">A munka mentéséhez válassza a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="182b0-188">Select **Save** to save your work.</span></span>

<span data-ttu-id="182b0-189">Ha törölni szeretne egy névjegyet, válassza a **Törlés** gombot (a kuka szimbólumot) a névjegytől jobbra.</span><span class="sxs-lookup"><span data-stu-id="182b0-189">To delete a contact, select the **Delete** button (the trash can symbol) to the right of the contact.</span></span>

<span data-ttu-id="182b0-190">Ha szerkeszteni szeretne egy névjegyet, válassza a **Szerkesztés** gombot (a ceruza szimbólumot) a névjegytől jobbra.</span><span class="sxs-lookup"><span data-stu-id="182b0-190">To edit a contact, select the **Edit** button (the pencil symbol) to the right of the contact.</span></span>

## <a name="add-or-edit-resources"></a><span data-ttu-id="182b0-191">Erőforrások hozzáadása és szerkesztése</span><span class="sxs-lookup"><span data-stu-id="182b0-191">Add or edit resources</span></span>

<span data-ttu-id="182b0-192">Hasznos fájlokat, térképeket és hivatkozásokat adhat a felvételi útmutató **Erőforrások** szakaszához.</span><span class="sxs-lookup"><span data-stu-id="182b0-192">You can add useful files, maps, and links to the **Resources** section of your onboarding guide.</span></span>

1. <span data-ttu-id="182b0-193">Az **Erőforrások** lapon válassza az **Új erőforrás** elemet.</span><span class="sxs-lookup"><span data-stu-id="182b0-193">On the **Resources** tab, select **New resource**.</span></span>
2. <span data-ttu-id="182b0-194">Tegye a következők egyikét:</span><span class="sxs-lookup"><span data-stu-id="182b0-194">Follow one of these steps:</span></span>

    - <span data-ttu-id="182b0-195">Fájl hozzáadásához válassza ki a **Fájlok** lapot, és húzza a fájlt a kívánt területre.</span><span class="sxs-lookup"><span data-stu-id="182b0-195">To add a file, select the **File** tab, and drag the file into the designated area.</span></span> <span data-ttu-id="182b0-196">(Másik lehetőségként kattintson a területen bárhová a számítógépen található fájlok tallózásához, vagy válassza a **OneDrive tallózása** parancsot.) Írjon be egy nevet a fájlnak, majd válassza a **Hozzáadás** elemet.</span><span class="sxs-lookup"><span data-stu-id="182b0-196">(Alternatively, click anywhere in that area to browse for the file on your computer, or select **Browse OneDrive**.) Enter a name for the file, and then select **Add**.</span></span>
    - <span data-ttu-id="182b0-197">Hivatkozás hozzáadásához válassza a **Hivatkozás** lapot, adja meg a hivatkozás nevét és címét, majd válassza a **Hozzáadás** elemet.</span><span class="sxs-lookup"><span data-stu-id="182b0-197">To add a link, select the **Link** tab, enter a name and address for the link, and then select **Add**.</span></span>
    - <span data-ttu-id="182b0-198">Térkép hozzáadásához válassza a **Térkép** lapot, adja meg a térkép nevét és címét, majd válassza a **Hozzáadás** elemet.</span><span class="sxs-lookup"><span data-stu-id="182b0-198">To add a map, select the **Map** tab, enter a name and address for the map, and then select **Add**.</span></span> <span data-ttu-id="182b0-199">Az Onboard tartalmazni fogja a megadott cím térképét.</span><span class="sxs-lookup"><span data-stu-id="182b0-199">Onboard will include a map of the address that you specify.</span></span>

    ![[<span data-ttu-id="182b0-200">Erőforrás hozzáadása egy felvételi útmutatóhoz vagy sablonhoz</span><span class="sxs-lookup"><span data-stu-id="182b0-200">Adding a resource to an onboarding guide or template</span></span>](./media/onboard-edit-add-resource.png)](./media/onboard-edit-add-resource.png)

3. <span data-ttu-id="182b0-201">A munka mentéséhez válassza a **Mentés** elemet.</span><span class="sxs-lookup"><span data-stu-id="182b0-201">Select **Save** to save your work.</span></span>

<span data-ttu-id="182b0-202">Ha törölni szeretne egy erőforrást, válassza a **Törlés** gombot (a kuka szimbólumot) az erőforrástól jobbra.</span><span class="sxs-lookup"><span data-stu-id="182b0-202">To delete a resource, select the **Delete** button (the trash can symbol) to the right of the resource.</span></span>

<span data-ttu-id="182b0-203">Ha szerkeszteni szeretne egy névjegyet, válassza a **Szerkesztés** gombot (a ceruza szimbólumot) az erőforrástól jobbra.</span><span class="sxs-lookup"><span data-stu-id="182b0-203">To edit a contact, select the **Edit** button (the pencil symbol) to the right of the resource.</span></span>

## <a name="next-steps"></a><span data-ttu-id="182b0-204">Következő lépések</span><span class="sxs-lookup"><span data-stu-id="182b0-204">Next steps</span></span>

- [<span data-ttu-id="182b0-205">Osszon meg tartalmakat más közreműködőkkel</span><span class="sxs-lookup"><span data-stu-id="182b0-205">Share content with other contributors</span></span>](./onboard-share-template.md)
- [<span data-ttu-id="182b0-206">A feladatok és az alkalmazottak és bevezetési állapotának megtekintése</span><span class="sxs-lookup"><span data-stu-id="182b0-206">View the status of tasks and onboarding employees</span></span>](./onboard-view-status.md)
- [<span data-ttu-id="182b0-207">Toborzócsoportok létrehozása az Onboard alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="182b0-207">Create hiring teams in Onboard</span></span>](./onboard-create-team.md)

### <a name="see-also"></a><span data-ttu-id="182b0-208">Lásd még</span><span class="sxs-lookup"><span data-stu-id="182b0-208">See also</span></span>

- [<span data-ttu-id="182b0-209">Próbálja ki vagy vásárolja meg az Onboard alkalmazást</span><span class="sxs-lookup"><span data-stu-id="182b0-209">Try or buy the Onboard app</span></span>](https://dynamics.microsoft.com/talent/onboard/)
- [<span data-ttu-id="182b0-210">Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="182b0-210">What's new or changed in Dynamics 365 Talent</span></span>](./whats-new.md)
- [<span data-ttu-id="182b0-211">Kiadási tervek</span><span class="sxs-lookup"><span data-stu-id="182b0-211">Release plans</span></span>](https://docs.microsoft.com/business-applications-release-notes/index)
- [<span data-ttu-id="182b0-212">Támogatás kérése a Microsoft Dynamics 365 Talent alkalmazáshoz</span><span class="sxs-lookup"><span data-stu-id="182b0-212">Get support for Microsoft Dynamics 365 Talent</span></span>](./talent-support.md)
