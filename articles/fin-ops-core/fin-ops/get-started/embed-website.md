---
title: Harmadik fél alkalmazások beágyazása
description: Ez a témakör azt mutatja be, hogyan végezhető el a harmadik fél alkalmazások beágyazása a termék funkcionalitásának kibővítése érdekében.
author: jasongre
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, UserWorkspaceAdd, UserWorkspaceConfigureWebsite
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2021-04-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: d348683e0a2ed35f26830a6ce05c0bf9ca5970bd
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944838"
---
# <a name="embed-third-party-apps"></a><span data-ttu-id="ad03b-103">Harmadik fél alkalmazások beágyazása</span><span class="sxs-lookup"><span data-stu-id="ad03b-103">Embed third-party apps</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="ad03b-104">Sok ügyfél különféle alkalmazások használatával végzi üzleti tevékenységét.</span><span class="sxs-lookup"><span data-stu-id="ad03b-104">Many customers use a range of applications to run their business.</span></span> <span data-ttu-id="ad03b-105">Az alkalmazások közül vannak olyan harmadik fél alkalmazások, amelyek a Finance and Operations alkalmazásokkal együtt működnek.</span><span class="sxs-lookup"><span data-stu-id="ad03b-105">Some of those applications are third-party web apps that work in conjunction with Finance and Operations apps.</span></span> <span data-ttu-id="ad03b-106">A felhasználói felület problémamentesebb használata érdekében az **(Előzetes verzió) Teljes oldalas alkalmazások** funkció használatával közvetlenül beágyazhatja ezeket a harmadik fél alkalmazásokat a saját Finance and Operations alkalmazásaiba (feltéve, hogy a harmadik fél alkalmazások engedélyezik a beágyazásukat).</span><span class="sxs-lookup"><span data-stu-id="ad03b-106">To provide a more seamless user experience, you can use the **(Preview) Full page apps** feature to embed those third-party apps directly into your Finance and Operations apps (provided that the third-party apps allow themselves to be embedded).</span></span> <span data-ttu-id="ad03b-107">Így a felhasználók anélkül is elérhetik a szükséges webhelyeket és alkalmazásokat, hogy a fülek vagy ablakok között kellene ingázniuk.</span><span class="sxs-lookup"><span data-stu-id="ad03b-107">In this way, users can access the websites and apps that they require without having to switch tabs or windows.</span></span>

<span data-ttu-id="ad03b-108">Mielőtt harmadik fél alkalmazásokat ágyazna be a termékbe, be kell kapcsolnia a Funkciókezelésben az **(Előzetes verzió) Teljes oldalas alkalmazások** funkciót.</span><span class="sxs-lookup"><span data-stu-id="ad03b-108">Before you can embed third-party apps into the product, you must turn on the **(Preview) Full page apps** feature in Feature management.</span></span> <span data-ttu-id="ad03b-109">Ezután a következő módszerek egyikével beágyazhat egy harmadik fél alkalmazást vagy webhelyet.</span><span class="sxs-lookup"><span data-stu-id="ad03b-109">You can then use one of the following methods to embed a third-party app or website.</span></span> <span data-ttu-id="ad03b-110">Ezek a módszerek hasonlóak ahhoz a módszerhez, amely a vászonalapú alkalmazásokat beágyazza a Microsoft Power Apps szolgáltatásból a Finance and Operations alkalmazásokba.</span><span class="sxs-lookup"><span data-stu-id="ad03b-110">These methods are analogous to the methods that are used to embed canvas apps from Microsoft Power Apps into Finance and Operations apps.</span></span>

- <span data-ttu-id="ad03b-111">Az alkalmazás vagy webhely beágyazása meglévő lapra új lapként (kimutatás fül, gyorslap, panel vagy munkaterület rész).</span><span class="sxs-lookup"><span data-stu-id="ad03b-111">Embed the app or website on an existing page as a new tab page (pivot tab, FastTab, blade, or workspace section).</span></span>
- <span data-ttu-id="ad03b-112">Új teljes képernyős élmény létrehozása alkalmazáshoz vagy webhelyhez az irányítópulton.</span><span class="sxs-lookup"><span data-stu-id="ad03b-112">Create a new full-page experience for the app or website from the dashboard.</span></span>

## <a name="embed-a-website-on-an-existing-page"></a><span data-ttu-id="ad03b-113">Webhely beágyazása meglévő lapra</span><span class="sxs-lookup"><span data-stu-id="ad03b-113">Embed a website on an existing page</span></span>

<span data-ttu-id="ad03b-114">Ezt az eljárást akkor használja, ha a rendszerben egy létező oldalt ki szeretne egészíteni egy alkalmazás beágyazásával.</span><span class="sxs-lookup"><span data-stu-id="ad03b-114">Use this procedure if you want to supplement an existing page in the system with an embedded app.</span></span>

1. <span data-ttu-id="ad03b-115">Menjen arra az oldalra, ahol be szeretné ágyazni az alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="ad03b-115">Open the page where you want to embed the app.</span></span>
2. <span data-ttu-id="ad03b-116">Nyissa meg az **Alkalmazás hozzáadása** lapot:</span><span class="sxs-lookup"><span data-stu-id="ad03b-116">Open the **Add an app** pane:</span></span>

    1. <span data-ttu-id="ad03b-117">Válassza a **Beállítások**, majd a **Személyre szabás** lehetőséget a **Személyre szabábi** eszközsáv megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ad03b-117">Select **Settings** and then **Personalize** to open the **Personalization** toolbar.</span></span>
    2. <span data-ttu-id="ad03b-118">Válassza a **További \> alkalmazás hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ad03b-118">Select **More \> Add an app**.</span></span>

3. <span data-ttu-id="ad03b-119">Válassza ki az oldal régióját, ahova az alkalmazást hozzá kívánja adni.</span><span class="sxs-lookup"><span data-stu-id="ad03b-119">Select the region of the page where you want to add the app.</span></span> <span data-ttu-id="ad03b-120">Ennek a régiónak egy kimutatáslap, gyorslap, panel vagy munkaterület rész *fültárolójának* kell lennie.</span><span class="sxs-lookup"><span data-stu-id="ad03b-120">This region must be a *tab container* for a pivot tab, FastTab, blade, or workspace section.</span></span>
4. <span data-ttu-id="ad03b-121">Válassza ki a **Webhely** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ad03b-121">Select **Website**.</span></span>
5. <span data-ttu-id="ad03b-122">Beágyazott alkalmazás konfigurálása:</span><span class="sxs-lookup"><span data-stu-id="ad03b-122">Configure the embedded app:</span></span>

    - <span data-ttu-id="ad03b-123">**Név** – Írja be a szöveget, amit szeretne, ha a beágyazott alkalmazást tartalmazó lapnál megjelenne.</span><span class="sxs-lookup"><span data-stu-id="ad03b-123">**Name** – Enter the text that should be shown for the tab that contains the embedded app.</span></span> <span data-ttu-id="ad03b-124">Gyakran hasznos, ha ez a szöveg az alkalmazás neve.</span><span class="sxs-lookup"><span data-stu-id="ad03b-124">Often, you will want this text to be the name of the app.</span></span>
    - <span data-ttu-id="ad03b-125">**URL** – Adja meg az alkalmazás helyét.</span><span class="sxs-lookup"><span data-stu-id="ad03b-125">**URL** – Specify the location of the app.</span></span>

    > [!IMPORTANT]
    > - <span data-ttu-id="ad03b-126">Biztonsági okokból az URL-címnek HTTPS-t (Hypertext Transfer Protocol Secure) kell használnia.</span><span class="sxs-lookup"><span data-stu-id="ad03b-126">For security reasons, the URL must use Hypertext Transfer Protocol Secure (HTTPS).</span></span>
    > - <span data-ttu-id="ad03b-127">Az alkalmazást vagy webhelyet úgy kell konfigurálni, hogy lehetővé tegye a saját beágyazását.</span><span class="sxs-lookup"><span data-stu-id="ad03b-127">The app or website must be configured to allow itself to be embedded.</span></span>

6. <span data-ttu-id="ad03b-128">Válassza a **Mentés** lehetőséget az alkalmazás lapon történő beágyazásához.</span><span class="sxs-lookup"><span data-stu-id="ad03b-128">Select **Save** to embed the app on the page.</span></span> <span data-ttu-id="ad03b-129">Az alkalmazás a csoport utolsó füleként vagy részeként lesz hozzáadva.</span><span class="sxs-lookup"><span data-stu-id="ad03b-129">The app is added as the last tab or section in the group.</span></span>
7. <span data-ttu-id="ad03b-130">Győződjön meg arról, hogy az alkalmazás a vártnak megfelelően jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="ad03b-130">Confirm that the app appears as expected.</span></span> <span data-ttu-id="ad03b-131">Ha az alkalmazás nincs renderelve, akkor tekintse meg témakör későbbi [Hibaelhárítás](#troubleshooting) szakaszát.</span><span class="sxs-lookup"><span data-stu-id="ad03b-131">If the app isn't rendered, see the [Troubleshooting](#troubleshooting) section later in this topic.</span></span>
8. <span data-ttu-id="ad03b-132">Nyissa meg a nézetválasztót, és válassza a **Mentés** (ha az alkalmazást az aktuális nézethez kell társítani) vagy a **Mentés másként** lehetőséget (ha az alkalmazást másik nézetbe szeretné menteni).</span><span class="sxs-lookup"><span data-stu-id="ad03b-132">Open the view selector, and select either **Save** (if the app should be associated with the current view) or **Save as** (to save the app to a different view).</span></span>

    <span data-ttu-id="ad03b-133">Ha az oldalnak nincs nézetválasztója (például párbeszédpanel vagy munkaterület), ezt a lépést kihagyhatja.</span><span class="sxs-lookup"><span data-stu-id="ad03b-133">If the page doesn't have a view selector (for example, if the page is a dialog box or a workspace), you can skip this step.</span></span>

## <a name="embed-a-website-as-a-full-page-experience-from-the-dashboard"></a><span data-ttu-id="ad03b-134">Webhely beágyazása teljes képernyős élményként az irányítópultból</span><span class="sxs-lookup"><span data-stu-id="ad03b-134">Embed a website as a full-page experience from the dashboard</span></span>

<span data-ttu-id="ad03b-135">Akkor használja ezt az eljárást, ha a beágyazni kívánt alkalmazás nem létező laphoz kapcsolódik, vagy ha a Finance and Operations alkalmazáson belül teljes képernyős élményre van szükség.</span><span class="sxs-lookup"><span data-stu-id="ad03b-135">Use this procedure if the app that you want to embed isn't related to an existing page, or if you just want a full-page experience for the app inside the Finance and Operations app.</span></span>

1. <span data-ttu-id="ad03b-136">Nyissa meg az irányítópultot.</span><span class="sxs-lookup"><span data-stu-id="ad03b-136">Open the dashboard.</span></span>
2. <span data-ttu-id="ad03b-137">Jelölje ki és tartsa lenyomva (vagy kattintson a jobb egérgombra) az oldalt, válassza a **Személyre szabás** lehetőséget, majd válassza a **Lap hozzáadása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ad03b-137">Select and hold (or right-click) the page, select **Personalize**, and then select **Add a page**.</span></span>
3. <span data-ttu-id="ad03b-138">A **Lap hozzáadása** panelen válassza a **Webhely** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ad03b-138">In the **Add a page** pane, select **Website**.</span></span>
4. <span data-ttu-id="ad03b-139">Beágyazott alkalmazás konfigurálása:</span><span class="sxs-lookup"><span data-stu-id="ad03b-139">Configure the embedded app:</span></span>

    - <span data-ttu-id="ad03b-140">**Név** – Adja meg azt a szöveget, amelyet az irányítópult beágyazott alkalmazásához hozzáadott csempén szeretne megjelentetni.</span><span class="sxs-lookup"><span data-stu-id="ad03b-140">**Name** – Enter the text that should be shown on the tile that is added for the embedded app on the dashboard.</span></span> <span data-ttu-id="ad03b-141">Gyakran hasznos, ha ez a szöveg az alkalmazás neve.</span><span class="sxs-lookup"><span data-stu-id="ad03b-141">Often, you will want this text to be the name of the app.</span></span>
    - <span data-ttu-id="ad03b-142">**URL** – Adja meg az alkalmazás helyét.</span><span class="sxs-lookup"><span data-stu-id="ad03b-142">**URL** – Specify the location of the app.</span></span>

    > [!IMPORTANT]
    > - <span data-ttu-id="ad03b-143">Biztonsági okokból az URL-címnek HTTPS-t kell használnia.</span><span class="sxs-lookup"><span data-stu-id="ad03b-143">For security reasons, the URL must use HTTPS.</span></span>
    > - <span data-ttu-id="ad03b-144">Az alkalmazást vagy webhelyet úgy kell konfigurálni, hogy lehetővé tegye a saját beágyazását.</span><span class="sxs-lookup"><span data-stu-id="ad03b-144">The app or website must be configured to allow itself to be embedded.</span></span>

5. <span data-ttu-id="ad03b-145">A **Mentés** gombra kattintva új csempeként hozzáadhatja az alkalmazást a irányítópulthoz.</span><span class="sxs-lookup"><span data-stu-id="ad03b-145">Select **Save** to add the app to the dashboard as a new tile.</span></span>
6. <span data-ttu-id="ad03b-146">Válassza ki az új csempét az irányítópult, és győződjön meg arról, hogy az alkalmazás a vártnak megfelelően jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="ad03b-146">Select the new tile on the dashboard, and confirm that the app appears as expected.</span></span> <span data-ttu-id="ad03b-147">Ha az alkalmazás nincs renderelve, akkor tekintse meg témakör későbbi [Hibaelhárítás](#troubleshooting) szakaszát.</span><span class="sxs-lookup"><span data-stu-id="ad03b-147">If the app isn't rendered, see the [Troubleshooting](#troubleshooting) section later in this topic.</span></span>

## <a name="sharing-embedded-apps"></a><span data-ttu-id="ad03b-148">A beágyazott alkalmazások megosztása</span><span class="sxs-lookup"><span data-stu-id="ad03b-148">Sharing embedded apps</span></span>

<span data-ttu-id="ad03b-149">Miután az előző részekben ismertetett valamelyik módszerrel beágyazott egy alkalmazást, érdemes lehet a nézetet megosztani a rendszer más felhasználóival.</span><span class="sxs-lookup"><span data-stu-id="ad03b-149">After you've embedded an app by using one of the methods that are described in the previous sections, you might want to share the view with other users in the system.</span></span> <span data-ttu-id="ad03b-150">Beágyazott alkalmazás megosztásához használja a következő módszerek egyikét:</span><span class="sxs-lookup"><span data-stu-id="ad03b-150">To share an embedded app, use one of the following methods:</span></span>

- <span data-ttu-id="ad03b-151">**Nézet közzététele (Ajánlott):** Ha a beágyazott alkalmazást elmentették egy nézetbe, a megosztás javasolt és preferált módja a nézet közzétételének a megfelelő biztonsági szerepkörekkel rendelkező felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="ad03b-151">**Publish the view (Recommended):** If the embedded app has been saved to a view, the recommended and preferred way to share it is to publish the view to users who have the appropriate security roles.</span></span> <span data-ttu-id="ad03b-152">Majd minden olyan felhasználó, aki a közzétett nézet által tervezett biztonsági szerepkörökkel rendelkezik, látja az alkalmazást a Finance and Operations alkalmazások képernyőjén.</span><span class="sxs-lookup"><span data-stu-id="ad03b-152">Then, all users who have the security roles that are targeted by the published view will see the app in Finance and Operations apps.</span></span> <span data-ttu-id="ad03b-153">További információért a nézet közzétételéhez lásd a [Nézetek közzététele](saved-views.md#publishing-views) lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ad03b-153">For more information about how to publish a view, see [Publishing views](saved-views.md#publishing-views).</span></span>

    <span data-ttu-id="ad03b-154">Olyan alkalmazást is közzé lehet tenni, amely teljes képernyős élményként van beágyazva az irányítópultról.</span><span class="sxs-lookup"><span data-stu-id="ad03b-154">You can also publish an app that has been embedded as a full-page experience from the dashboard.</span></span> <span data-ttu-id="ad03b-155">Az irányítópulton jelölje ki és tartsa lenyomva (vagy kattintson a jobb egérgombbal) az alkalmazáshoz társított csempét, válassza a **Személyre szabás** lehetőséget, majd válassza a **Lap közzététele** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ad03b-155">On the dashboard, select and hold (or right-click) the tile that is associated with the app, select **Personalize**, and then select **Publish page**.</span></span> <span data-ttu-id="ad03b-156">Jelenleg csak biztonsági szerepkörökhöz tud közzétenni.</span><span class="sxs-lookup"><span data-stu-id="ad03b-156">Currently, you can publish only to security roles.</span></span> <span data-ttu-id="ad03b-157">A jogi személyek számára való közzétételt azonban csak azt megelőzően lehet hozzáadni, hogy a funkció általánosan elérhetővé válik.</span><span class="sxs-lookup"><span data-stu-id="ad03b-157">However, the capability to publish to legal entities will be added before the feature becomes generally available.</span></span>

- <span data-ttu-id="ad03b-158">**Személyre szabás másolása:** Olyan lapok esetén, amelyek nem támogatják a nézeteket (például párbeszédpanelek vagy munkaterületek), vagy a teljes oldalas alkalmazással való használatnál, átmásolhatja a személyre szabást a megfelelő felhasználókhoz.</span><span class="sxs-lookup"><span data-stu-id="ad03b-158">**Copy the personalization:** For pages that don't support views (for example, dialog boxes or workspaces), or for the full-page app experience, you can copy the personalization to the appropriate users.</span></span> <span data-ttu-id="ad03b-159">A további tudnivalókat lásd: [Személyre szabások megosztása](personalize-user-experience.md#sharing-personalizations).</span><span class="sxs-lookup"><span data-stu-id="ad03b-159">For more information, see [Sharing personalizations](personalize-user-experience.md#sharing-personalizations).</span></span>

## <a name="viewing-embedded-apps"></a><span data-ttu-id="ad03b-160">A beágyazott alkalmazások megtekintése</span><span class="sxs-lookup"><span data-stu-id="ad03b-160">Viewing embedded apps</span></span>

<span data-ttu-id="ad03b-161">Egy beágyazott alkalmazás megtekintéséhez egy lapon a Finance and Operations alkalmazásokban, nyissa meg a beágyazott alkalmazást tartalmazó oldalt.</span><span class="sxs-lookup"><span data-stu-id="ad03b-161">To view an embedded app on a page in Finance and Operations apps, open the page that has the embedded app.</span></span> <span data-ttu-id="ad03b-162">Ne felejtse el, hogy egyes oldalakon a beágyazott alkalmazásokat a szokásos Művelet ablaktábla **Power Apps** gombján keresztül érheti el.</span><span class="sxs-lookup"><span data-stu-id="ad03b-162">Remember that, on some pages, embedded apps can be accessed by using the **Power Apps** button on the standard Action Pane.</span></span> <span data-ttu-id="ad03b-163">Másik lehetőségként megjelenhetnek közvetlenül egy oldalon új lap, gyorslap vagy lapát, illetve a munkaterület új szakasza formájában.</span><span class="sxs-lookup"><span data-stu-id="ad03b-163">Alternatively, they might appear directly on the page as a new tab, FastTab, or blade, or as a new section in a workspace.</span></span>

## <a name="editing-or-removing-embedded-apps"></a><span data-ttu-id="ad03b-164">Beágyazott alkalmazások szerkesztése vagy eltávolítása</span><span class="sxs-lookup"><span data-stu-id="ad03b-164">Editing or removing embedded apps</span></span>

<span data-ttu-id="ad03b-165">Miután az alkalmazás be lett ágyazva egy lapra, lehet, hogy módosítania kell a konfigurációját (például a szakasz címkéjének vagy URL-címének módosításával).</span><span class="sxs-lookup"><span data-stu-id="ad03b-165">After an app has been embedded on a page, you might have to edit its configuration (for example, by changing the section label or the URL).</span></span> <span data-ttu-id="ad03b-166">Arra is lehetőség van, hogy eltávolítsa az oldalról.</span><span class="sxs-lookup"><span data-stu-id="ad03b-166">Alternatively, you might have to remove it from the page.</span></span> <span data-ttu-id="ad03b-167">A következő eljárások valamelyikével szerkesztheti egy beágyazott alkalmazás konfigurációját, vagy teljesen el is távolíthatja azt.</span><span class="sxs-lookup"><span data-stu-id="ad03b-167">Use one of the following procedures to edit the configuration of an embedded app or remove it completely.</span></span>

### <a name="apps-that-are-embedded-on-existing-pages"></a><span data-ttu-id="ad03b-168">A meglévő lapokra ágyazott alkalmazások</span><span class="sxs-lookup"><span data-stu-id="ad03b-168">Apps that are embedded on existing pages</span></span>

1. <span data-ttu-id="ad03b-169">Menjen arra az oldalra, ahol be van ágyazva az alkalmazás.</span><span class="sxs-lookup"><span data-stu-id="ad03b-169">Open the page where the app is embedded.</span></span>
2. <span data-ttu-id="ad03b-170">Válassza a **Beállítások**, majd a **Személyre szabás** lehetőséget a **Személyre szabábi** eszközsáv megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="ad03b-170">Select **Settings** and then **Personalize** to open the **Personalization** toolbar.</span></span>
3. <span data-ttu-id="ad03b-171">Válassza ki a **Kijelölés** eszközt, majd válassza ki a beágyazott alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="ad03b-171">Select the **Select** tool, and then select the embedded app.</span></span>
4. <span data-ttu-id="ad03b-172">Az alkalmazás szerkesztéséhez módosítsa a konfigurációját a szükséges változtatásokkal, majd kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="ad03b-172">To edit the app, make the required changes to its configuration, and then select **Save**.</span></span>

    <span data-ttu-id="ad03b-173">Vagy válassza a **Törlés** lehetőséget az alkalmazás eltávolításához.</span><span class="sxs-lookup"><span data-stu-id="ad03b-173">Alternatively, to remove the app, select **Delete**.</span></span>

5. <span data-ttu-id="ad03b-174">A nézet ismételt mentése vagy ismételt közzététele.</span><span class="sxs-lookup"><span data-stu-id="ad03b-174">Re-save or republish the view.</span></span> <span data-ttu-id="ad03b-175">Ne feledje, hogy ha a nézet explicit mentése nélkül elhagyja a lapot, a **Webhely szerkesztése** ablakban végrehajtott műveletek egyike sem lesz megtartva.</span><span class="sxs-lookup"><span data-stu-id="ad03b-175">Note that if you leave the page without explicitly saving the view, none of the actions that you performed in the **Edit website** pane will be maintained.</span></span>

### <a name="apps-that-are-embedded-from-the-dashboard"></a><span data-ttu-id="ad03b-176">Az irányítópultr=l beágyazott alkalmazások</span><span class="sxs-lookup"><span data-stu-id="ad03b-176">Apps that are embedded from the dashboard</span></span>

1. <span data-ttu-id="ad03b-177">Nyissa meg az irányítópultot.</span><span class="sxs-lookup"><span data-stu-id="ad03b-177">Open the dashboard.</span></span>
2. <span data-ttu-id="ad03b-178">Jelölje ki és tartsa lenyomva (vagy kattintson a jobb egérgombbal) a beágyazott alkalmazáshoz társított csempét, majd válassza a **Személyre szabás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ad03b-178">Select and hold (or right-click) the tile that is associated with the embedded app, and then select **Personalize**.</span></span>
3. <span data-ttu-id="ad03b-179">Az alkalmazás szerkesztéséhez válassza a **Lap szerkesztése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ad03b-179">To edit the app, select **Edit page**.</span></span> <span data-ttu-id="ad03b-180">A **Weboldal szerkesztése** panelen módosítsa az alkalmazás konfigurációját a szükséges változtatásokkal, majd kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="ad03b-180">In the **Edit website** pane, make the required changes to the app configuration, and then select **Save**.</span></span>

    <span data-ttu-id="ad03b-181">Vagy válassza a **Lap eltávolítása** lehetőséget az alkalmazás eltávolításához.</span><span class="sxs-lookup"><span data-stu-id="ad03b-181">Alternatively, to remove the app, select **Remove page**.</span></span>

## <a name="appendix"></a><span data-ttu-id="ad03b-182">Melléklet</span><span class="sxs-lookup"><span data-stu-id="ad03b-182">Appendix</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="ad03b-183">Hibaelhárítás</span><span class="sxs-lookup"><span data-stu-id="ad03b-183">Troubleshooting</span></span>

<span data-ttu-id="ad03b-184">Ha egy webhely nem jelenik meg megfelelően a Finance and Operation alkalmazásba való beágyazás után, vagy ha egy hibaüzenet jelenik meg arról, hogy az URL-cím egy kapcsolata meg lett tagadva, akkor a webhely valószínűleg úgy van beállítva, hogy megakadályozza, hogy be legyen ágyazva egy iFrame-be.</span><span class="sxs-lookup"><span data-stu-id="ad03b-184">If a website isn't rendered correctly after it's embedded in a Finance and Operation app, or if you receive an error message that states that the URL was denied a connection, the website is probably configured to prevent itself from being embedded in an iframe.</span></span> <span data-ttu-id="ad03b-185">Kövesse az alábbi lépéseket ahhoz, hogy eldöntse, egy webhely beágyazható-e vagy sem.</span><span class="sxs-lookup"><span data-stu-id="ad03b-185">Follow these steps to determine whether the website can be embedded.</span></span>

1. <span data-ttu-id="ad03b-186">Nyissa meg a használt böngésző fejlesztői eszközeit.</span><span class="sxs-lookup"><span data-stu-id="ad03b-186">Open the developer tools for the browser that you're using.</span></span>
2. <span data-ttu-id="ad03b-187">A **Hálózat** lapon keresse meg és válassza ki a választ a beágyazott webhelyről.</span><span class="sxs-lookup"><span data-stu-id="ad03b-187">On the **Network** tab, find and select the response from the embedded site.</span></span>
3. <span data-ttu-id="ad03b-188">A **Fejlécek** fülön, a **Válaszfejlécek** alatt keresse meg az **x-keret beállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ad03b-188">On the **Headers** tab, under **Response Headers**, look for **x-frame-options**.</span></span> <span data-ttu-id="ad03b-189">Ha az **x-keret beállítások** a válaszfejlécben vannak, és a **DENY** vagy **SAMEORIGIN** értékkel rendelkezik, akkor a webhely jelenleg nem ágyazható be.</span><span class="sxs-lookup"><span data-stu-id="ad03b-189">If **x-frame-options** exists in the response headers, and has a value of **DENY** or **SAMEORIGIN**, the website can't currently be embedded.</span></span> <span data-ttu-id="ad03b-190">A biztonságos beágyazás engedélyezéséhez együtt kell működnie az alkalmazás tulajdonosával.</span><span class="sxs-lookup"><span data-stu-id="ad03b-190">You will have to work with the owner of the app to enable it to be safely embedded.</span></span>

### <a name="developer-modeling-a-website-on-a-form"></a><span data-ttu-id="ad03b-191">[Fejlesztő] Webhely modellezése egy űrlapon</span><span class="sxs-lookup"><span data-stu-id="ad03b-191">[Developer] Modeling a website on a form</span></span>

<span data-ttu-id="ad03b-192">Bár ez a témakör a harmadik fél alkalmazások és webhelyek személyre szabáson keresztüli beágyazására összpontosít, a fejlesztők a Visual Studio fejlesztői élmény segítségével egy űrlapba is beágyazhatják őket.</span><span class="sxs-lookup"><span data-stu-id="ad03b-192">Although this topic is focused on embedding third-party apps or websites through personalization, developers can also embed them in a form by using the Visual Studio development experience.</span></span> <span data-ttu-id="ad03b-193">Csak adjon hozzá a **WebsiteHostControl** vezérlőt az űrlaphoz.</span><span class="sxs-lookup"><span data-stu-id="ad03b-193">Just add a **WebsiteHostControl** control to the form.</span></span> <span data-ttu-id="ad03b-194">A vezérlőhöz elérhető metaadat-tulajdonságok a személyre szabási élményekkel azonos lehetőségeket biztosítanak.</span><span class="sxs-lookup"><span data-stu-id="ad03b-194">The metadata properties that are available for the control provide the same capabilities as the personalization experience.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]