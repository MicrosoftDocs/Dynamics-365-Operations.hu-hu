---
title: A CSS felülíró fájljainak használata
description: Ez a témakör ismerteti, hogy miért, mikor és hogyan kell használni az egymásba ágyazott stíluslapok (CSS) felülíró fájljait a Microsoft Dynamics 365 Commerce alkalmazásban.
author: phinneyridge
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3ec43b16b1df07400cffe597378ad4035e4d07e0
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411247"
---
# <a name="work-with-css-override-files"></a><span data-ttu-id="6f326-103">A CSS felülíró fájljainak használata</span><span class="sxs-lookup"><span data-stu-id="6f326-103">Work with CSS override files</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="6f326-104">Ez a témakör ismerteti, hogy miért, mikor és hogyan kell használni az egymásba ágyazott stíluslapok (CSS) felülíró fájljait a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="6f326-104">This topic describes why, when, and how to use Cascading Style Sheets (CSS) override files in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6f326-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="6f326-105">Overview</span></span>

<span data-ttu-id="6f326-106">Az állandó webhelystílusokat általában a webhely témáján keresztül kell kezelni.</span><span class="sxs-lookup"><span data-stu-id="6f326-106">Permanent site styles should usually be handled through a site's theme.</span></span> <span data-ttu-id="6f326-107">A témák biztosítják az alapvető CSS- és stílusbeállításokat a webhely minden oldala esetén.</span><span class="sxs-lookup"><span data-stu-id="6f326-107">Themes provide the foundational CSS and style settings for the modules on any page of your site.</span></span> <span data-ttu-id="6f326-108">A témák az Dynamics 365 Commerce online szoftverfejlesztői készlet (SDK) segítségével hozhatók létre, és a webhelyekre a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatáson keresztül vannak telepítve.</span><span class="sxs-lookup"><span data-stu-id="6f326-108">Themes are created by using the Dynamics 365 Commerce online software development kit (SDK), and they are deployed to your websites through Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="6f326-109">Az SDK téma-hibakeresés képességei és modulinterfész-konfigurációi segítenek a webhely fejlesztőinek testreszabható és összetartó webhelytervcsomagok létrehozásában.</span><span class="sxs-lookup"><span data-stu-id="6f326-109">Theme debugging capabilities and module interface configurations in the SDK help site developers create customizable and cohesive site design packages.</span></span> <span data-ttu-id="6f326-110">Ha ezeket a tervezési csomagokat egy webhelyre telepítik, a webhelykészítők a tartalom webhelyfejlesztés helyett a tartalom létrehozására, szerkesztésére és közzétételére összpontosíthatnak.</span><span class="sxs-lookup"><span data-stu-id="6f326-110">When these design packages are deployed to a site, site authors can focus on creating, editing, and publishing content instead of site development.</span></span>

<span data-ttu-id="6f326-111">Tekintettel egy téma szokásos életciklusára, a függőség a fejlesztőktől, hogy elvégezzék a stílusváltoztatásokat SDK- és LCS-telepítési folyamaton keresztül, bizonyos esetekben akadályozó tényező lehet.</span><span class="sxs-lookup"><span data-stu-id="6f326-111">Given the usual lifecycle of a theme, the dependency on developers to make style changes through the SDK and LCS deployment pipeline can be prohibitive in some scenarios.</span></span> <span data-ttu-id="6f326-112">A webhely prototípusai és gyorsjavításai nehézkesnek tűnhetnek, ha az SDK nincs konfigurálva, vagy nincs ideje megvárni az LCS telepítését.</span><span class="sxs-lookup"><span data-stu-id="6f326-112">Site prototypes or hotfixes can seem cumbersome if the SDK isn't configured, or if you don't have time to wait for an LCS deployment.</span></span>

<span data-ttu-id="6f326-113">Ezekben az esetekben a CSS felülbírálási fájljai segíthetnek.</span><span class="sxs-lookup"><span data-stu-id="6f326-113">In these scenarios, CSS override files can help.</span></span> <span data-ttu-id="6f326-114">A Commerce szerzői eszközeiben a hitelesített felhasználók feltölthetnek egy CSS fájlt, megtekinthetik az előnézetét, majd aktiválhatják a webhely témájának felülbírálásához.</span><span class="sxs-lookup"><span data-stu-id="6f326-114">In the Commerce authoring tools, authenticated users can upload a CSS file, preview it, and then activate it to override a site's theme.</span></span> <span data-ttu-id="6f326-115">Az e feletti SDK- vagy az LCS-telepítésre nincs szükség.</span><span class="sxs-lookup"><span data-stu-id="6f326-115">The overhead of SDK or LCS deployment isn't required.</span></span> <span data-ttu-id="6f326-116">A CSS felülírási fájlban megadott felülírások lehetnek olyan kicsik, mint egy szövegstílus módosítása vagy olyan széles körűek, mint a teljes márka átalakítása.</span><span class="sxs-lookup"><span data-stu-id="6f326-116">The overrides that are specified in a CSS override file can be as small as a change to a single text style or as wide-ranging as a complete brand overhaul.</span></span>

<span data-ttu-id="6f326-117">A CSS felülíró fájlok használata előtt vegye figyelembe a következő korlátozásokat:</span><span class="sxs-lookup"><span data-stu-id="6f326-117">Before you use CSS override files, be aware of the following limitations:</span></span>

- <span data-ttu-id="6f326-118">Egyszerre csak CSS felülíró fájl lehet aktív a webhelyen.</span><span class="sxs-lookup"><span data-stu-id="6f326-118">Only one CSS override file can be active on a site at a time.</span></span> <span data-ttu-id="6f326-119">Ezért az összes aktív felülírásnak fájlnak egyetlen felülíró fájlban kell lennie.</span><span class="sxs-lookup"><span data-stu-id="6f326-119">Therefore, all active overrides must be present in a single override file.</span></span>
- <span data-ttu-id="6f326-120">Bár megtekintheti a felülírásokat a Commerce szerzői eszközeiben, nincs dedikált hibakereső funkció, amely segít azonosítani a felülírási hibákat.</span><span class="sxs-lookup"><span data-stu-id="6f326-120">Although you can preview the overrides in the Commerce authoring tools, there are no dedicated debugging features to help identify any bugs that the overrides introduce.</span></span> <span data-ttu-id="6f326-121">Más szavakkal, ha CSS felülírási fájlokat használ, akkor nem ugyanazzal a eszközkészlettel rendelkezik, mint amit az SDK a modul- és a szerzői érvényesítéshez biztosít.</span><span class="sxs-lookup"><span data-stu-id="6f326-121">In other words, when you use CSS override files, you don't have the same toolset that the SDK provides for module and authoring validation.</span></span>

<span data-ttu-id="6f326-122">Mindazonáltal a CSS felülbíráló fájlok segítségével gyorsan elkészítheti egy terv prototípusát vagy végrehajthat egy gyorsjavítást a teljes téma frissítésének kifejlesztése és telepítése előtt.</span><span class="sxs-lookup"><span data-stu-id="6f326-122">Nevertheless, CSS override files provide a quick way to prototype a design or implement a hotfix before a full theme update is developed and deployed.</span></span>

## <a name="create-a-css-override-file"></a><span data-ttu-id="6f326-123">CSS felülíró fájl létrehozása</span><span class="sxs-lookup"><span data-stu-id="6f326-123">Create a CSS override file</span></span>

<span data-ttu-id="6f326-124">CSS felülírási fájl létrehozásához használhat bármilyen integrált fejlesztőkörnyezetet (IDE), szövegszerkesztőt vagy forráskód-szerkesztőt.</span><span class="sxs-lookup"><span data-stu-id="6f326-124">To create a CSS override file, you can use any integrated development environment (IDE), text editor, or source code editor.</span></span> <span data-ttu-id="6f326-125">A szokásos megközelítés szerint a böngészőben szabványos webes hibakeresőjének segítségével azonosíthatja a stílusválasztókat, tulajdonságokat és értékeket a meglévő webhelyen.</span><span class="sxs-lookup"><span data-stu-id="6f326-125">A typical approach is to use standard web debuggers in your browser to identify style selectors, properties, and values on your existing site.</span></span> <span data-ttu-id="6f326-126">A legtöbb böngésző lehetővé teszik az értékek módosítását és a hibakeresőben való előnézetét.</span><span class="sxs-lookup"><span data-stu-id="6f326-126">Most browsers let you change values and preview them in the debugger.</span></span> <span data-ttu-id="6f326-127">Miután azonosította a kívánt változtatásokat, mentheti azokat a saját CSS fájljába.</span><span class="sxs-lookup"><span data-stu-id="6f326-127">After you've identified the changes that you want to make, you can save them to your own CSS file.</span></span>

## <a name="upload-a-css-override-file"></a><span data-ttu-id="6f326-128">CSS felülírási fájl feltöltése</span><span class="sxs-lookup"><span data-stu-id="6f326-128">Upload a CSS override file</span></span>

<span data-ttu-id="6f326-129">Ha fel szeretne tölteni egy CSS fájlt a webhelyére a Commerce alkalmazásban, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6f326-129">To upload a CSS file to your site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="6f326-130">A szerkesztési eszközökben nyissa meg a webhelyét.</span><span class="sxs-lookup"><span data-stu-id="6f326-130">In the authoring tools, go to your site.</span></span>
1. <span data-ttu-id="6f326-131">A bal oldali navigációs ablakban válassza ki a **Terv** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6f326-131">In the navigation pane on the left, select **Design**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6f326-132">A használt Commerce szerkesztési eszközök verziószámától függően előfordulhat, hogy ki kell bontania a **Beállítások** lehetőséget a navigációs ablaktáblán, mielőtt kiválasztaná a **Terv** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6f326-132">Depending on the version of the Commerce authoring tools that you're using, you might have to expand **Settings** in the navigation pane before you can select **Design**.</span></span>

1. <span data-ttu-id="6f326-133">A fő tervezőablak tetején jelölje ki a **CSS felülírás** lapot, ha még nincs bejelölve.</span><span class="sxs-lookup"><span data-stu-id="6f326-133">At the top of the main design pane, select the **CSS override** tab, if it isn't already selected.</span></span>
1. <span data-ttu-id="6f326-134">A **Rendelkezésre álló CSS felülírások** alatt válassza a **CSS fájl feltöltése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6f326-134">Under **Available CSS overrides**, select **Upload CSS file**.</span></span> <span data-ttu-id="6f326-135">Megjelenik egy fájlkezelő ablak.</span><span class="sxs-lookup"><span data-stu-id="6f326-135">A File Explorer window appears.</span></span>
1. <span data-ttu-id="6f326-136">A fájlkezelő programban tallózással keresse meg és válassza ki a CSS fájlt, majd kattintson a **Megnyitás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6f326-136">In File Explorer, browse to and select a CSS file, and then select **Open**.</span></span> <span data-ttu-id="6f326-137">A feltöltött CSS fájl most már a **Rendelkezésre álló CSS felülírások** alatt jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="6f326-137">The uploaded CSS file now appears under **Available CSS overrides**.</span></span>

## <a name="preview-a-css-override-file"></a><span data-ttu-id="6f326-138">CSS felülírási fájl előnézetének megtekintése</span><span class="sxs-lookup"><span data-stu-id="6f326-138">Preview a CSS override file</span></span>

<span data-ttu-id="6f326-139">A CSS felülírási fájl előzetes megtekintéséhez kövesse az alábbi lépéseket, mielőtt aktiválná az éles webhelyén.</span><span class="sxs-lookup"><span data-stu-id="6f326-139">To preview a CSS override file before you make it active on your live site, follow these steps.</span></span>

1. <span data-ttu-id="6f326-140">A bal oldali navigációs ablaktáblán válassza ki a **Terv** elemet, majd a **CSS felülírása** lapon, a **Rendelkezésre álló CSS felülírások** alatt keresse meg az előzetesként megtekinteni kívánt CSS-t.</span><span class="sxs-lookup"><span data-stu-id="6f326-140">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to preview.</span></span>
1. <span data-ttu-id="6f326-141">A CSS fájlnév mellett válassza ki a **Webhely előnézete** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6f326-141">Next to the CSS file name, select **Preview site**.</span></span>
1. <span data-ttu-id="6f326-142">A **Válasszon egy URL-t** párbeszédpanelen válassza ki annak a webhelynek az URL-címét, amelyre alkalmazni szeretné a felülírást, majd kattintson az **OK**gombra.</span><span class="sxs-lookup"><span data-stu-id="6f326-142">In the **Select a URL** dialog box, select the URL of the site that you want to see the override applied to, and then select **OK**.</span></span>
1. <span data-ttu-id="6f326-143">Ha a kiválasztott URL-címnek több változata van, válassza ki a kívánt változatot a megjelenő **Előnézet változatai** párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="6f326-143">If there are multiple variants for the selected URL, select the desired variant in the **Preview variations** dialog box that appears.</span></span>

<span data-ttu-id="6f326-144">Egy új böngésző fül vagy ablak nyílik meg, ahol érvényesítheti a stílusfelülírásokat a webhelyen.</span><span class="sxs-lookup"><span data-stu-id="6f326-144">A new browser tab or window is opened, where you can validate your style overrides against your site.</span></span> <span data-ttu-id="6f326-145">Az URL-címet megoszthatja más hitelesített Commerce-felhasználókkal véleményezés és visszajelzés céljából.</span><span class="sxs-lookup"><span data-stu-id="6f326-145">You can then share the URL with other authenticated Commerce users for review and feedback.</span></span>

## <a name="activate-a-css-override-file-on-your-live-site"></a><span data-ttu-id="6f326-146">A CSS felülírási fájl aktiválása az élő webhelyen</span><span class="sxs-lookup"><span data-stu-id="6f326-146">Activate a CSS override file on your live site</span></span>

<span data-ttu-id="6f326-147">Miután megtekintette és jóváhagyta a CSS felülbíráló fájlt, aktiválhatja azt az éles webhelyen.</span><span class="sxs-lookup"><span data-stu-id="6f326-147">After you've previewed and approved the CSS override file, you can activate it on your live site.</span></span>

> [!NOTE]
> <span data-ttu-id="6f326-148">Egyszerre csak egy CSS felülíró fájl lehet aktív a webhelyen.</span><span class="sxs-lookup"><span data-stu-id="6f326-148">Only one CSS override file can be active on your site at a time.</span></span> <span data-ttu-id="6f326-149">Ha aktivál egy új felülírási fájlt, az előző felülírási fájl inaktiválódik.</span><span class="sxs-lookup"><span data-stu-id="6f326-149">If you activate a new override file, the previous override file is inactivated.</span></span> <span data-ttu-id="6f326-150">Ezért győződjön meg arról, hogy minden szükséges felülírás megtalálható egyetlen CSS felülírási fájlban.</span><span class="sxs-lookup"><span data-stu-id="6f326-150">Therefore, make sure that all required overrides are present in a single CSS override file.</span></span>

<span data-ttu-id="6f326-151">Egy CSS felülírási fájl aktiválásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6f326-151">To activate a CSS override file, follow these steps.</span></span>

1. <span data-ttu-id="6f326-152">A bal oldali navigációs ablaktáblán válassza ki a **Terv** elemet, majd a **CSS felülírása** lapon, a **Rendelkezésre álló CSS felülírások** alatt keresse meg az előzetesként megtekinteni kívánt CSS-t.</span><span class="sxs-lookup"><span data-stu-id="6f326-152">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to activate.</span></span>
1. <span data-ttu-id="6f326-153">A CSS fájlnév alatt válassza ki az **Aktiválás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6f326-153">Under the CSS file name, select **Activate**.</span></span> <span data-ttu-id="6f326-154">A felülíró fájl azonnal aktívvá válik az éles webhelyen.</span><span class="sxs-lookup"><span data-stu-id="6f326-154">The override file immediately becomes active on your live site.</span></span>

## <a name="deactivate-a-css-override-file-on-your-live-site"></a><span data-ttu-id="6f326-155">A CSS felülírási fájl deaktiválása az élő webhelyen</span><span class="sxs-lookup"><span data-stu-id="6f326-155">Deactivate a CSS override file on your live site</span></span>

<span data-ttu-id="6f326-156">A webhelyén lévő CSS felülíró fájlok inaktiválásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="6f326-156">To deactivate a CSS override file on your site, follow these steps.</span></span>

1. <span data-ttu-id="6f326-157">A bal oldali navigációs ablaktáblán válassza ki a **Terv** elemet, majd a **CSS felülírása** lapon, a **Rendelkezésre álló CSS felülírások** alatt keresse meg az inaktiválni kívánt CSS-t.</span><span class="sxs-lookup"><span data-stu-id="6f326-157">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to deactivate.</span></span>
1. <span data-ttu-id="6f326-158">A CSS fájlnév alatt válassza ki az **Inaktiválás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6f326-158">Under the CSS file name, select **Deactivate**.</span></span> <span data-ttu-id="6f326-159">A felülíró fájl azonnal inaktívvá válik az éles webhelyen.</span><span class="sxs-lookup"><span data-stu-id="6f326-159">The override file immediately becomes inactive on your live site.</span></span>

> [!TIP]
> <span data-ttu-id="6f326-160">Az CSS felülíró fájlok további beállításainak eléréséhez jelölje ki a három pontot (**...**) a CSS fájl neve mellett.</span><span class="sxs-lookup"><span data-stu-id="6f326-160">To access additional options for CSS override files, select the ellipsis (**...**) next to the CSS file name.</span></span> <span data-ttu-id="6f326-161">A **Letöltés**, **Átnevezés** és **Csere** beállítások hasznosak a meglévő CSS felülíró fájlok gyors módosításnál.</span><span class="sxs-lookup"><span data-stu-id="6f326-161">The **Download**, **Rename**, and **Replace** options are useful for quick changes to an existing CSS override file.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6f326-162">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="6f326-162">Additional resources</span></span>

[<span data-ttu-id="6f326-163">Embléma hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6f326-163">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="6f326-164">Webhely témájának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="6f326-164">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="6f326-165">Előre beállított stílusok használata</span><span class="sxs-lookup"><span data-stu-id="6f326-165">Work with style presets</span></span>](style-presets.md)

[<span data-ttu-id="6f326-166">Kedvencek ikon hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6f326-166">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="6f326-167">Üdvözlő üzenet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6f326-167">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="6f326-168">Szerzői jogi értesítés hozzáadása</span><span class="sxs-lookup"><span data-stu-id="6f326-168">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="6f326-169">Nyelvek hozzáadása a webhelyhez</span><span class="sxs-lookup"><span data-stu-id="6f326-169">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="6f326-170">Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához</span><span class="sxs-lookup"><span data-stu-id="6f326-170">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)
