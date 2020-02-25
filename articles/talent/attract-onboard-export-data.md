---
title: Adatok exportálása az Attract és az Onboard modulból
description: Adatok exportálása a Dynamics 365 Talent Attract és az Onboard modulból.
author: andreabichsel
manager: AnnBe
ms.date: 01/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Talent October 2019 update
ms.openlocfilehash: eb97a16c15476c2f34ec581a32a677fa6fee8739
ms.sourcegitcommit: acdd93637385246f9c5c652cccdf2cbfb263cc33
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/23/2020
ms.locfileid: "2975934"
---
# <a name="export-data-from-attract-and-onboard"></a><span data-ttu-id="af0ad-103">Adatok exportálása az Attract és az Onboard modulból</span><span class="sxs-lookup"><span data-stu-id="af0ad-103">Export data from Attract and Onboard</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="af0ad-104">Ahogy azt bejelentettük a [Dynamics 365 Talent: Attract és Dynamics 365 Talent: Onboard alkalmazások megszüntetése](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps) című bejegyzésben, megszüntetjük a Dynamics 365 Talent: Attract és Dynamics 365 Talent: Onboard alkalmazásokat 2022. február 1-jén.</span><span class="sxs-lookup"><span data-stu-id="af0ad-104">As announced in [Retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard Apps](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps), we're retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard on February 1, 2022.</span></span> <span data-ttu-id="af0ad-105">Hogy segítséget nyújtsunk másik termékbe való áttelepítéssel, mindkét alkalmazásban találhatók adatexportálási lehetőségek.</span><span class="sxs-lookup"><span data-stu-id="af0ad-105">To help with your migration to another product, both apps now provide data export capabilities.</span></span>

## <a name="export-data-from-attract"></a><span data-ttu-id="af0ad-106">Adatok exportálása az Attract modulból</span><span class="sxs-lookup"><span data-stu-id="af0ad-106">Export data from Attract</span></span>

<span data-ttu-id="af0ad-107">Az adatok az Ön környezetéhez való hozzáférés korlátozása nélkül exportálhatók.</span><span class="sxs-lookup"><span data-stu-id="af0ad-107">You can export your data without restricting access to your environment.</span></span> <span data-ttu-id="af0ad-108">Erre akkor lehet szükség, ha tesztelési célokra vagy az adatstruktúránk megértésére lenne szükség.</span><span class="sxs-lookup"><span data-stu-id="af0ad-108">You might want to do this for testing purposes or to understand our data structure.</span></span> <span data-ttu-id="af0ad-109">Ha készen áll az áttelepítésre, korlátozza a hozzáférést az Attract környezethez az eljárás utáni utasítások alapján.</span><span class="sxs-lookup"><span data-stu-id="af0ad-109">When you're ready to migrate, restrict access to your Attract environment using the instructions after this procedure.</span></span> <span data-ttu-id="af0ad-110">Mindenképpen exportálja az adatokat ismét.</span><span class="sxs-lookup"><span data-stu-id="af0ad-110">Be sure to export your data again.</span></span> 

1. <span data-ttu-id="af0ad-111">Ugorjon ide: [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span><span class="sxs-lookup"><span data-stu-id="af0ad-111">Go to [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span></span>

2. <span data-ttu-id="af0ad-112">Az **adatexportálás** területen válassza az **Adatexportálás kérése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="af0ad-112">Under **Data export**, select **Request a data export**.</span></span>

   ![[<span data-ttu-id="af0ad-113">Adatexportálás kérése az Attract modulból</span><span class="sxs-lookup"><span data-stu-id="af0ad-113">Request a data export from Attract</span></span>](./media/attract-onboard-export-data-attract-request.png)](./media/attract-onboard-export-data-attract-request.png)

3. <span data-ttu-id="af0ad-114">Ha megjelenik a **Kérelem feldolgozása folyamatban van** üzenetablak, válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="af0ad-114">When the **Your request is being processed** message box appears, select **OK**.</span></span> <span data-ttu-id="af0ad-115">Az adatexportálás akár 20 percig is tarthat, attól függően, hogy milyen méretű az exportálás.</span><span class="sxs-lookup"><span data-stu-id="af0ad-115">The data export can take up to 20 minutes, depending on the size of your export.</span></span>

4. <span data-ttu-id="af0ad-116">Az Exportálás befejeződése után válassza ki a mellette található **Letöltés** gombot.</span><span class="sxs-lookup"><span data-stu-id="af0ad-116">When your export completes, select the **Download** button next to it.</span></span> 

   >[!NOTE]
   ><span data-ttu-id="af0ad-117">Az összes adatexportálás 7 napig elérhető, ami után a **Letöltés** hivatkozás elévül.</span><span class="sxs-lookup"><span data-stu-id="af0ad-117">All data exports are available for seven days, at which point the **Download** link expires.</span></span></br>
   
<span data-ttu-id="af0ad-118">A letöltés tartalmaz egy .zip fájlt az Attract adatokkal, többek között a következő mappákat:</span><span class="sxs-lookup"><span data-stu-id="af0ad-118">The download contains a .zip file with your Attract data, including the following folders:</span></span>

| <span data-ttu-id="af0ad-119">Mappa neve</span><span class="sxs-lookup"><span data-stu-id="af0ad-119">Folder name</span></span> | <span data-ttu-id="af0ad-120">Leírás</span><span class="sxs-lookup"><span data-stu-id="af0ad-120">Description</span></span> |
| --- | --- |
| <span data-ttu-id="af0ad-121">Adminisztratív beállítások</span><span class="sxs-lookup"><span data-stu-id="af0ad-121">Admin settings</span></span> | <span data-ttu-id="af0ad-122">Attract felügyeleti központ konfigurációi.</span><span class="sxs-lookup"><span data-stu-id="af0ad-122">Attract admin center configurations.</span></span> |
| <span data-ttu-id="af0ad-123">Jelöltek</span><span class="sxs-lookup"><span data-stu-id="af0ad-123">Candidates</span></span> | <span data-ttu-id="af0ad-124">Az összes jelölt, akiket állásokhoz vagy tehetségállományokhoz hozzáadtak.</span><span class="sxs-lookup"><span data-stu-id="af0ad-124">All candidates that were added to jobs or talent pools.</span></span> |
| <span data-ttu-id="af0ad-125">E-mail-sablonok</span><span class="sxs-lookup"><span data-stu-id="af0ad-125">Email templates</span></span> | <span data-ttu-id="af0ad-126">A környezethez konfigurált összes e-mail-sablon.</span><span class="sxs-lookup"><span data-stu-id="af0ad-126">All email templates that were configured for the environment.</span></span> |
| <span data-ttu-id="af0ad-127">Állásajánlati csomagok sablonjai</span><span class="sxs-lookup"><span data-stu-id="af0ad-127">Job offer package templates</span></span> | <span data-ttu-id="af0ad-128">A létrehozott összes állásajánlat-csomagsablon, valamint a társított konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="af0ad-128">All job offer package templates that were created, plus their associated configurations.</span></span> |
| <span data-ttu-id="af0ad-129">Állásajánlat-szabályegyüttesek</span><span class="sxs-lookup"><span data-stu-id="af0ad-129">Job offer rule sets</span></span> |  <span data-ttu-id="af0ad-130">Minden szabályegyüttes-fájl, amelyet az ajánlatkezeléshez feltöltöttek.</span><span class="sxs-lookup"><span data-stu-id="af0ad-130">All rule set files that were uploaded for offer management.</span></span> |
| <span data-ttu-id="af0ad-131">Állásajánlat-sablonok</span><span class="sxs-lookup"><span data-stu-id="af0ad-131">Job offer templates</span></span> | <span data-ttu-id="af0ad-132">A környezethez létrehozott összes állásajánlat-dokumentumsablon.</span><span class="sxs-lookup"><span data-stu-id="af0ad-132">All job offer document templates created for the environment.</span></span> |
| <span data-ttu-id="af0ad-133">Álláslehetőségek</span><span class="sxs-lookup"><span data-stu-id="af0ad-133">Job openings</span></span> | <span data-ttu-id="af0ad-134">Minden létrehozott állás.</span><span class="sxs-lookup"><span data-stu-id="af0ad-134">All created jobs.</span></span> <span data-ttu-id="af0ad-135">A törölt állások nem exportálhatók.</span><span class="sxs-lookup"><span data-stu-id="af0ad-135">Deleted jobs aren't exported.</span></span> <span data-ttu-id="af0ad-136">Az almappákban szerepelnek a jelöltek pályázatai, további almappákkal a jelölti pályázatok mellékletei és ajánlati csomagok számára, ha szükséges.</span><span class="sxs-lookup"><span data-stu-id="af0ad-136">The sub-folders contain candidate applications, with sub-folders for candidate application attachments and offer packages, where applicable.</span></span> |
| <span data-ttu-id="af0ad-137">Munkalehetőség-sablonok</span><span class="sxs-lookup"><span data-stu-id="af0ad-137">Job opening templates</span></span> | <span data-ttu-id="af0ad-138">A környezetben konfigurált összes munkafolyamat-sablon.</span><span class="sxs-lookup"><span data-stu-id="af0ad-138">Job process templates that were configured in the environment.</span></span> |
| <span data-ttu-id="af0ad-139">Tehetségállományok</span><span class="sxs-lookup"><span data-stu-id="af0ad-139">Talent pools</span></span> | <span data-ttu-id="af0ad-140">Az összes létrehozott tehetségállomány, a közreműködőik listája, és a tehetségállomány jelölti listája.</span><span class="sxs-lookup"><span data-stu-id="af0ad-140">All created talent pools, their contributors lists, and the candidates lists for the talent pools.</span></span> |
| <span data-ttu-id="af0ad-141">Dolgozók</span><span class="sxs-lookup"><span data-stu-id="af0ad-141">Workers</span></span> | <span data-ttu-id="af0ad-142">A környezetben jelenlévő összes dolgozó listája, valamint a szerepköreik.</span><span class="sxs-lookup"><span data-stu-id="af0ad-142">List of all the workers who are present in the environment, plus their roles.</span></span> |
| <span data-ttu-id="af0ad-143">(gyökérmappa)</span><span class="sxs-lookup"><span data-stu-id="af0ad-143">(root folder)</span></span> | <span data-ttu-id="af0ad-144">A JSON-séma fájlja, amely az adatszerkezet mezőit írja le.</span><span class="sxs-lookup"><span data-stu-id="af0ad-144">A JSON schema file that describes the data structure fields.</span></span> |

### <a name="restrict-access-to-attract"></a><span data-ttu-id="af0ad-145">Hozzáférés korlátozása az Attract modulhoz</span><span class="sxs-lookup"><span data-stu-id="af0ad-145">Restrict access to Attract</span></span>

<span data-ttu-id="af0ad-146">Ha készen áll az áttelepítésre, korlátozza a nem rendszergazdák hozzáférését az Attract környezethez, és exportálja adatait.</span><span class="sxs-lookup"><span data-stu-id="af0ad-146">When you're ready to migrate, restrict non-admins from accessing your Attract environment and export your data.</span></span>

>[!IMPORTANT]
><span data-ttu-id="af0ad-147">Az Attract környezethez való hozzáférés korlátozása végleges, és nem vonható vissza.</span><span class="sxs-lookup"><span data-stu-id="af0ad-147">Restricting access to your Attract environment is permanent and can't be undone.</span></span> <span data-ttu-id="af0ad-148">Ha azt szeretné, hogy a nem rendszergazda felhasználók továbbra is hozzáférjenek a környezethez, hagyja ki ezt a lépést.</span><span class="sxs-lookup"><span data-stu-id="af0ad-148">If you want non-admin users to continue accessing your environment, skip this step.</span></span>

1. <span data-ttu-id="af0ad-149">Ugorjon ide: [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span><span class="sxs-lookup"><span data-stu-id="af0ad-149">Go to [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span></span>

2. <span data-ttu-id="af0ad-150">Ha korlátozni szeretné a nem rendszergazdák számára az Attract környezethez való hozzáférést, akkor a **Hozzáférés korlátozása ennél az alkalmazásnál** pontban válassza a **Hozzáférés korlátozása most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="af0ad-150">To restrict non-admins from accessing your Attract environment, under **Restrict access to this app**, select **Restrict access now**.</span></span> <span data-ttu-id="af0ad-151">A hozzáférés korlátozásával visszavonja az összes közzétett aktív állás közzétételét.</span><span class="sxs-lookup"><span data-stu-id="af0ad-151">Restricting access also unposts any active jobs that have been posted.</span></span>

   ![[<span data-ttu-id="af0ad-152">Nem rendszergazdai hozzáférés korlátozása az Attract modulhoz</span><span class="sxs-lookup"><span data-stu-id="af0ad-152">Restrict non-admin access to Attract</span></span>](./media/attract-onboard-export-data-attract-restrict-access.png)](./media/attract-onboard-export-data-attract-restrict-access.png)

3. <span data-ttu-id="af0ad-153">Amikor megjelenik az **Ez végleges módosítás** figyelmeztetés, válassza a **Hozzáférés korlátozása** lehetőséget a környezethez való végleges korlátozáshoz nem rendszergazda felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="af0ad-153">When you see the warning **This is a permanent change**, select **Restrict access** to permanently restrict non-admin users from this environment.</span></span> <span data-ttu-id="af0ad-154">Ha nem szeretné végrehajtani ezt a lépést, válassza a **mégse** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="af0ad-154">If you're not ready to complete this step, select **Cancel**.</span></span>

   ![[<span data-ttu-id="af0ad-155">Figyelmeztetés, hogy a hozzáférés korlátozása végleges módosítás</span><span class="sxs-lookup"><span data-stu-id="af0ad-155">Warning that restricting access is a permanent change</span></span>](./media/attract-onboard-export-data-attract-warning.png)](./media/attract-onboard-export-data-attract-warning.png)

   >[!NOTE]
   ><span data-ttu-id="af0ad-156">A rendszergaudák továbbra is hozzáférhetnek az adatok exportálásához és a személyek jelentéséhez szükséges oldalakhoz, miután korlátozza a hozzáférést az Attract környezethez.</span><span class="sxs-lookup"><span data-stu-id="af0ad-156">Admins can continue to access the data export and person report pages after you restrict access to the Attract environment.</span></span>

## <a name="export-data-from-onboard"></a><span data-ttu-id="af0ad-157">Adatok exportálása az Onboard modulból</span><span class="sxs-lookup"><span data-stu-id="af0ad-157">Export data from Onboard</span></span>

<span data-ttu-id="af0ad-158">Ha készenáll, letöltheti a sablonokat, útmutatókat és a jelöltek adatait az Onboard modulból.</span><span class="sxs-lookup"><span data-stu-id="af0ad-158">When you're ready, you can download templates, guides, and candidate data from Onboard.</span></span>

1. <span data-ttu-id="af0ad-159">Ugorjon ide: [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).</span><span class="sxs-lookup"><span data-stu-id="af0ad-159">Go to [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).</span></span>

2. <span data-ttu-id="af0ad-160">Az **adatexportálás** területen válassza az **Adatexportálás kérése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="af0ad-160">Under **Data export**, select **Request a data export**.</span></span> 

   ![[<span data-ttu-id="af0ad-161">Adatexportálás kérése az Onboard modulból</span><span class="sxs-lookup"><span data-stu-id="af0ad-161">Request a data export from Onboard</span></span>](./media/attract-onboard-export-data-onboard-request.png)](./media/attract-onboard-export-data-onboard-request.png)

3. <span data-ttu-id="af0ad-162">Ha megjelenik a **Kérelem feldolgozása folyamatban van** üzenetablak, válassza az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="af0ad-162">When the **Your request is being processed** message box appears, select **OK**.</span></span> <span data-ttu-id="af0ad-163">Az adatexportálás akár 20 percig is tarthat, attól függően, hogy milyen méretű az exportálás.</span><span class="sxs-lookup"><span data-stu-id="af0ad-163">The data export can take up to 20 minutes, depending on the size of your export.</span></span>

4. <span data-ttu-id="af0ad-164">Az Exportálás befejeződése után válassza ki a mellette található **Letöltés** gombot.</span><span class="sxs-lookup"><span data-stu-id="af0ad-164">When your export completes, select the **Download** button next to it.</span></span> 

   ![[<span data-ttu-id="af0ad-165">Adatok exportálásának letöltése az Onboard modulból</span><span class="sxs-lookup"><span data-stu-id="af0ad-165">Download data export from Onboard</span></span>](./media/attract-onboard-export-data-onboard-download.png)](./media/attract-onboard-export-data-onboard-download.png)

   >[!NOTE]
   ><span data-ttu-id="af0ad-166">Az adatexportálás hét napig áll rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="af0ad-166">Your data export is available for seven days.</span></span> <span data-ttu-id="af0ad-167">Hét nap után a **Letöltés** hivatkozás lejár, és új exportálást kell kérnie, ha ismét szeretné letölteni adatait.</span><span class="sxs-lookup"><span data-stu-id="af0ad-167">After seven days, the **Download** link expires, and you must request a new export if you need to download your data again.</span></span> <span data-ttu-id="af0ad-168">Új adatexportálás indításakor az új export sikeres végrehajtása után minden létező már meglévő letöltés elévül.</span><span class="sxs-lookup"><span data-stu-id="af0ad-168">When you start a new data export, any existing downloads will expire after the new export succeeds.</span></span>

<span data-ttu-id="af0ad-169">A letöltés egy .zip-fájl, amely a következőket tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="af0ad-169">The download is a .zip file that contains:</span></span>

- <span data-ttu-id="af0ad-170">A **Sablonok** mappát, amely az Onboard-sablonokat Word-formátumban tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="af0ad-170">A **Templates** folder that contains your Onboard templates in Word document format.</span></span>

- <span data-ttu-id="af0ad-171">Az **Útmutatók** mappát, amely az Onboard-útmutatókat Word-formátumban tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="af0ad-171">A **Guides** folder that contains your Onboard guides in Word document format.</span></span>

## <a name="see-also"></a><span data-ttu-id="af0ad-172">Lásd még</span><span class="sxs-lookup"><span data-stu-id="af0ad-172">See also</span></span>

[<span data-ttu-id="af0ad-173">Dynamics 365 Talent: Attract és Dynamics 365 Talent: Onboard alkalmazások megszüntetése</span><span class="sxs-lookup"><span data-stu-id="af0ad-173">Retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard Apps</span></span>](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)