---
title: A CSS felülíró fájljainak használata
description: Ez a témakör ismerteti, hogy miért, mikor és hogyan kell használni az egymásba ágyazott stíluslapok (CSS) felülíró fájljait a Microsoft Dynamics 365 Commerce alkalmazásban.
author: phinneyridge
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ef96070fe77b46622667301c7c7c402909ee7dfc
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799493"
---
# <a name="work-with-css-override-files"></a><span data-ttu-id="a317f-103">A CSS felülíró fájljainak használata</span><span class="sxs-lookup"><span data-stu-id="a317f-103">Work with CSS override files</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a317f-104">Ez a témakör ismerteti, hogy miért, mikor és hogyan kell használni az egymásba ágyazott stíluslapok (CSS) felülíró fájljait a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="a317f-104">This topic describes why, when, and how to use Cascading Style Sheets (CSS) override files in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="a317f-105">Az állandó webhelystílusokat általában a webhely témáján keresztül kell kezelni.</span><span class="sxs-lookup"><span data-stu-id="a317f-105">Permanent site styles should usually be handled through a site's theme.</span></span> <span data-ttu-id="a317f-106">A témák biztosítják az alapvető CSS- és stílusbeállításokat a webhely minden oldala esetén.</span><span class="sxs-lookup"><span data-stu-id="a317f-106">Themes provide the foundational CSS and style settings for the modules on any page of your site.</span></span> <span data-ttu-id="a317f-107">A témák az Dynamics 365 Commerce online szoftverfejlesztői készlet (SDK) segítségével hozhatók létre, és a webhelyekre a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatáson keresztül vannak telepítve.</span><span class="sxs-lookup"><span data-stu-id="a317f-107">Themes are created by using the Dynamics 365 Commerce online software development kit (SDK), and they are deployed to your websites through Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="a317f-108">Az SDK téma-hibakeresés képességei és modulinterfész-konfigurációi segítenek a webhely fejlesztőinek testreszabható és összetartó webhelytervcsomagok létrehozásában.</span><span class="sxs-lookup"><span data-stu-id="a317f-108">Theme debugging capabilities and module interface configurations in the SDK help site developers create customizable and cohesive site design packages.</span></span> <span data-ttu-id="a317f-109">Ha ezeket a tervezési csomagokat egy webhelyre telepítik, a webhelykészítők a tartalom webhelyfejlesztés helyett a tartalom létrehozására, szerkesztésére és közzétételére összpontosíthatnak.</span><span class="sxs-lookup"><span data-stu-id="a317f-109">When these design packages are deployed to a site, site authors can focus on creating, editing, and publishing content instead of site development.</span></span>

<span data-ttu-id="a317f-110">Tekintettel egy téma szokásos életciklusára, a függőség a fejlesztőktől, hogy elvégezzék a stílusváltoztatásokat SDK- és LCS-telepítési folyamaton keresztül, bizonyos esetekben akadályozó tényező lehet.</span><span class="sxs-lookup"><span data-stu-id="a317f-110">Given the usual lifecycle of a theme, the dependency on developers to make style changes through the SDK and LCS deployment pipeline can be prohibitive in some scenarios.</span></span> <span data-ttu-id="a317f-111">A webhely prototípusai és gyorsjavításai nehézkesnek tűnhetnek, ha az SDK nincs konfigurálva, vagy nincs ideje megvárni az LCS telepítését.</span><span class="sxs-lookup"><span data-stu-id="a317f-111">Site prototypes or hotfixes can seem cumbersome if the SDK isn't configured, or if you don't have time to wait for an LCS deployment.</span></span>

<span data-ttu-id="a317f-112">Ezekben az esetekben a CSS felülbírálási fájljai segíthetnek.</span><span class="sxs-lookup"><span data-stu-id="a317f-112">In these scenarios, CSS override files can help.</span></span> <span data-ttu-id="a317f-113">A Commerce szerzői eszközeiben a hitelesített felhasználók feltölthetnek egy CSS fájlt, megtekinthetik az előnézetét, majd aktiválhatják a webhely témájának felülbírálásához.</span><span class="sxs-lookup"><span data-stu-id="a317f-113">In the Commerce authoring tools, authenticated users can upload a CSS file, preview it, and then activate it to override a site's theme.</span></span> <span data-ttu-id="a317f-114">Az e feletti SDK- vagy az LCS-telepítésre nincs szükség.</span><span class="sxs-lookup"><span data-stu-id="a317f-114">The overhead of SDK or LCS deployment isn't required.</span></span> <span data-ttu-id="a317f-115">A CSS felülírási fájlban megadott felülírások lehetnek olyan kicsik, mint egy szövegstílus módosítása vagy olyan széles körűek, mint a teljes márka átalakítása.</span><span class="sxs-lookup"><span data-stu-id="a317f-115">The overrides that are specified in a CSS override file can be as small as a change to a single text style or as wide-ranging as a complete brand overhaul.</span></span>

<span data-ttu-id="a317f-116">A CSS felülíró fájlok használata előtt vegye figyelembe a következő korlátozásokat:</span><span class="sxs-lookup"><span data-stu-id="a317f-116">Before you use CSS override files, be aware of the following limitations:</span></span>

- <span data-ttu-id="a317f-117">Egyszerre csak CSS felülíró fájl lehet aktív a webhelyen.</span><span class="sxs-lookup"><span data-stu-id="a317f-117">Only one CSS override file can be active on a site at a time.</span></span> <span data-ttu-id="a317f-118">Ezért az összes aktív felülírásnak fájlnak egyetlen felülíró fájlban kell lennie.</span><span class="sxs-lookup"><span data-stu-id="a317f-118">Therefore, all active overrides must be present in a single override file.</span></span>
- <span data-ttu-id="a317f-119">Bár megtekintheti a felülírásokat a Commerce szerzői eszközeiben, nincs dedikált hibakereső funkció, amely segít azonosítani a felülírási hibákat.</span><span class="sxs-lookup"><span data-stu-id="a317f-119">Although you can preview the overrides in the Commerce authoring tools, there are no dedicated debugging features to help identify any bugs that the overrides introduce.</span></span> <span data-ttu-id="a317f-120">Más szavakkal, ha CSS felülírási fájlokat használ, akkor nem ugyanazzal a eszközkészlettel rendelkezik, mint amit az SDK a modul- és a szerzői érvényesítéshez biztosít.</span><span class="sxs-lookup"><span data-stu-id="a317f-120">In other words, when you use CSS override files, you don't have the same toolset that the SDK provides for module and authoring validation.</span></span>

<span data-ttu-id="a317f-121">Mindazonáltal a CSS felülbíráló fájlok segítségével gyorsan elkészítheti egy terv prototípusát vagy végrehajthat egy gyorsjavítást a teljes téma frissítésének kifejlesztése és telepítése előtt.</span><span class="sxs-lookup"><span data-stu-id="a317f-121">Nevertheless, CSS override files provide a quick way to prototype a design or implement a hotfix before a full theme update is developed and deployed.</span></span>

## <a name="create-a-css-override-file"></a><span data-ttu-id="a317f-122">CSS felülíró fájl létrehozása</span><span class="sxs-lookup"><span data-stu-id="a317f-122">Create a CSS override file</span></span>

<span data-ttu-id="a317f-123">CSS felülírási fájl létrehozásához használhat bármilyen integrált fejlesztőkörnyezetet (IDE), szövegszerkesztőt vagy forráskód-szerkesztőt.</span><span class="sxs-lookup"><span data-stu-id="a317f-123">To create a CSS override file, you can use any integrated development environment (IDE), text editor, or source code editor.</span></span> <span data-ttu-id="a317f-124">A szokásos megközelítés szerint a böngészőben szabványos webes hibakeresőjének segítségével azonosíthatja a stílusválasztókat, tulajdonságokat és értékeket a meglévő webhelyen.</span><span class="sxs-lookup"><span data-stu-id="a317f-124">A typical approach is to use standard web debuggers in your browser to identify style selectors, properties, and values on your existing site.</span></span> <span data-ttu-id="a317f-125">A legtöbb böngésző lehetővé teszik az értékek módosítását és a hibakeresőben való előnézetét.</span><span class="sxs-lookup"><span data-stu-id="a317f-125">Most browsers let you change values and preview them in the debugger.</span></span> <span data-ttu-id="a317f-126">Miután azonosította a kívánt változtatásokat, mentheti azokat a saját CSS fájljába.</span><span class="sxs-lookup"><span data-stu-id="a317f-126">After you've identified the changes that you want to make, you can save them to your own CSS file.</span></span>

## <a name="upload-a-css-override-file"></a><span data-ttu-id="a317f-127">CSS felülírási fájl feltöltése</span><span class="sxs-lookup"><span data-stu-id="a317f-127">Upload a CSS override file</span></span>

<span data-ttu-id="a317f-128">Ha fel szeretne tölteni egy CSS fájlt a webhelyére a Commerce alkalmazásban, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a317f-128">To upload a CSS file to your site in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="a317f-129">A szerkesztési eszközökben nyissa meg a webhelyét.</span><span class="sxs-lookup"><span data-stu-id="a317f-129">In the authoring tools, go to your site.</span></span>
1. <span data-ttu-id="a317f-130">A bal oldali navigációs ablakban válassza ki a **Terv** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a317f-130">In the navigation pane on the left, select **Design**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a317f-131">A használt Commerce szerkesztési eszközök verziószámától függően előfordulhat, hogy ki kell bontania a **Beállítások** lehetőséget a navigációs ablaktáblán, mielőtt kiválasztaná a **Terv** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a317f-131">Depending on the version of the Commerce authoring tools that you're using, you might have to expand **Settings** in the navigation pane before you can select **Design**.</span></span>

1. <span data-ttu-id="a317f-132">A fő tervezőablak tetején jelölje ki a **CSS felülírás** lapot, ha még nincs bejelölve.</span><span class="sxs-lookup"><span data-stu-id="a317f-132">At the top of the main design pane, select the **CSS override** tab, if it isn't already selected.</span></span>
1. <span data-ttu-id="a317f-133">A **Rendelkezésre álló CSS felülírások** alatt válassza a **CSS fájl feltöltése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a317f-133">Under **Available CSS overrides**, select **Upload CSS file**.</span></span> <span data-ttu-id="a317f-134">Megjelenik egy fájlkezelő ablak.</span><span class="sxs-lookup"><span data-stu-id="a317f-134">A File Explorer window appears.</span></span>
1. <span data-ttu-id="a317f-135">A fájlkezelő programban tallózással keresse meg és válassza ki a CSS fájlt, majd kattintson a **Megnyitás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a317f-135">In File Explorer, browse to and select a CSS file, and then select **Open**.</span></span> <span data-ttu-id="a317f-136">A feltöltött CSS fájl most már a **Rendelkezésre álló CSS felülírások** alatt jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="a317f-136">The uploaded CSS file now appears under **Available CSS overrides**.</span></span>

## <a name="preview-a-css-override-file"></a><span data-ttu-id="a317f-137">CSS felülírási fájl előnézetének megtekintése</span><span class="sxs-lookup"><span data-stu-id="a317f-137">Preview a CSS override file</span></span>

<span data-ttu-id="a317f-138">A CSS felülírási fájl előzetes megtekintéséhez kövesse az alábbi lépéseket, mielőtt aktiválná az éles webhelyén.</span><span class="sxs-lookup"><span data-stu-id="a317f-138">To preview a CSS override file before you make it active on your live site, follow these steps.</span></span>

1. <span data-ttu-id="a317f-139">A bal oldali navigációs ablaktáblán válassza ki a **Terv** elemet, majd a **CSS felülírása** lapon, a **Rendelkezésre álló CSS felülírások** alatt keresse meg az előzetesként megtekinteni kívánt CSS-t.</span><span class="sxs-lookup"><span data-stu-id="a317f-139">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to preview.</span></span>
1. <span data-ttu-id="a317f-140">A CSS fájlnév mellett válassza ki a **Webhely előnézete** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a317f-140">Next to the CSS file name, select **Preview site**.</span></span>
1. <span data-ttu-id="a317f-141">A **Válasszon egy URL-t** párbeszédpanelen válassza ki annak a webhelynek az URL-címét, amelyre alkalmazni szeretné a felülírást, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="a317f-141">In the **Select a URL** dialog box, select the URL of the site that you want to see the override applied to, and then select **OK**.</span></span>
1. <span data-ttu-id="a317f-142">Ha a kiválasztott URL-címnek több változata van, válassza ki a kívánt változatot a megjelenő **Előnézet változatai** párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="a317f-142">If there are multiple variants for the selected URL, select the desired variant in the **Preview variations** dialog box that appears.</span></span>

<span data-ttu-id="a317f-143">Egy új böngésző fül vagy ablak nyílik meg, ahol érvényesítheti a stílusfelülírásokat a webhelyen.</span><span class="sxs-lookup"><span data-stu-id="a317f-143">A new browser tab or window is opened, where you can validate your style overrides against your site.</span></span> <span data-ttu-id="a317f-144">Az URL-címet megoszthatja más hitelesített Commerce-felhasználókkal véleményezés és visszajelzés céljából.</span><span class="sxs-lookup"><span data-stu-id="a317f-144">You can then share the URL with other authenticated Commerce users for review and feedback.</span></span>

## <a name="activate-a-css-override-file-on-your-live-site"></a><span data-ttu-id="a317f-145">A CSS felülírási fájl aktiválása az élő webhelyen</span><span class="sxs-lookup"><span data-stu-id="a317f-145">Activate a CSS override file on your live site</span></span>

<span data-ttu-id="a317f-146">Miután megtekintette és jóváhagyta a CSS felülbíráló fájlt, aktiválhatja azt az éles webhelyen.</span><span class="sxs-lookup"><span data-stu-id="a317f-146">After you've previewed and approved the CSS override file, you can activate it on your live site.</span></span>

> [!NOTE]
> <span data-ttu-id="a317f-147">Egyszerre csak egy CSS felülíró fájl lehet aktív a webhelyen.</span><span class="sxs-lookup"><span data-stu-id="a317f-147">Only one CSS override file can be active on your site at a time.</span></span> <span data-ttu-id="a317f-148">Ha aktivál egy új felülírási fájlt, az előző felülírási fájl inaktiválódik.</span><span class="sxs-lookup"><span data-stu-id="a317f-148">If you activate a new override file, the previous override file is inactivated.</span></span> <span data-ttu-id="a317f-149">Ezért győződjön meg arról, hogy minden szükséges felülírás megtalálható egyetlen CSS felülírási fájlban.</span><span class="sxs-lookup"><span data-stu-id="a317f-149">Therefore, make sure that all required overrides are present in a single CSS override file.</span></span>

<span data-ttu-id="a317f-150">Egy CSS felülírási fájl aktiválásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a317f-150">To activate a CSS override file, follow these steps.</span></span>

1. <span data-ttu-id="a317f-151">A bal oldali navigációs ablaktáblán válassza ki a **Terv** elemet, majd a **CSS felülírása** lapon, a **Rendelkezésre álló CSS felülírások** alatt keresse meg az előzetesként megtekinteni kívánt CSS-t.</span><span class="sxs-lookup"><span data-stu-id="a317f-151">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to activate.</span></span>
1. <span data-ttu-id="a317f-152">A CSS fájlnév alatt válassza ki az **Aktiválás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a317f-152">Under the CSS file name, select **Activate**.</span></span> <span data-ttu-id="a317f-153">A felülíró fájl azonnal aktívvá válik az éles webhelyen.</span><span class="sxs-lookup"><span data-stu-id="a317f-153">The override file immediately becomes active on your live site.</span></span>

## <a name="deactivate-a-css-override-file-on-your-live-site"></a><span data-ttu-id="a317f-154">A CSS felülírási fájl deaktiválása az élő webhelyen</span><span class="sxs-lookup"><span data-stu-id="a317f-154">Deactivate a CSS override file on your live site</span></span>

<span data-ttu-id="a317f-155">A webhelyén lévő CSS felülíró fájlok inaktiválásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a317f-155">To deactivate a CSS override file on your site, follow these steps.</span></span>

1. <span data-ttu-id="a317f-156">A bal oldali navigációs ablaktáblán válassza ki a **Terv** elemet, majd a **CSS felülírása** lapon, a **Rendelkezésre álló CSS felülírások** alatt keresse meg az inaktiválni kívánt CSS-t.</span><span class="sxs-lookup"><span data-stu-id="a317f-156">In the navigation pane on the left, select **Design**, and then, on the **CSS override** tab, under **Available CSS overrides**, find the CSS file that you want to deactivate.</span></span>
1. <span data-ttu-id="a317f-157">A CSS fájlnév alatt válassza ki az **Inaktiválás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a317f-157">Under the CSS file name, select **Deactivate**.</span></span> <span data-ttu-id="a317f-158">A felülíró fájl azonnal inaktívvá válik az éles webhelyen.</span><span class="sxs-lookup"><span data-stu-id="a317f-158">The override file immediately becomes inactive on your live site.</span></span>

> [!TIP]
> <span data-ttu-id="a317f-159">Az CSS felülíró fájlok további beállításainak eléréséhez jelölje ki a három pontot (**...**) a CSS fájl neve mellett.</span><span class="sxs-lookup"><span data-stu-id="a317f-159">To access additional options for CSS override files, select the ellipsis (**...**) next to the CSS file name.</span></span> <span data-ttu-id="a317f-160">A **Letöltés**, **Átnevezés** és **Csere** beállítások hasznosak a meglévő CSS felülíró fájlok gyors módosításnál.</span><span class="sxs-lookup"><span data-stu-id="a317f-160">The **Download**, **Rename**, and **Replace** options are useful for quick changes to an existing CSS override file.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a317f-161">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="a317f-161">Additional resources</span></span>

[<span data-ttu-id="a317f-162">Embléma hozzáadása</span><span class="sxs-lookup"><span data-stu-id="a317f-162">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="a317f-163">Webhely témájának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="a317f-163">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="a317f-164">Előre beállított stílusok használata</span><span class="sxs-lookup"><span data-stu-id="a317f-164">Work with style presets</span></span>](style-presets.md)

[<span data-ttu-id="a317f-165">Kedvencek ikon hozzáadása</span><span class="sxs-lookup"><span data-stu-id="a317f-165">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="a317f-166">Üdvözlő üzenet hozzáadása</span><span class="sxs-lookup"><span data-stu-id="a317f-166">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="a317f-167">Szerzői jogi értesítés hozzáadása</span><span class="sxs-lookup"><span data-stu-id="a317f-167">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="a317f-168">Nyelvek hozzáadása a webhelyhez</span><span class="sxs-lookup"><span data-stu-id="a317f-168">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="a317f-169">Parancsfájl hozzáadása a webhely oldalaihoz a telemetria támogatásához</span><span class="sxs-lookup"><span data-stu-id="a317f-169">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
