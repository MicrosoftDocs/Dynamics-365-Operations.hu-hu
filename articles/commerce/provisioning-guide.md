---
title: Dynamics 365 Commerce értékelési környezet kiépítése
description: Ez a témakör bemutatja, hogyan lehet egy Microsoft Dynamics 365 Commerce értékelési környezetet létesíteni.
author: psimolin
ms.date: 12/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 19cedf01d1b916de785454d55448f41d1f5db1df
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792291"
---
# <a name="provision-a-dynamics-365-commerce-evaluation-environment"></a><span data-ttu-id="c4bc7-103">Dynamics 365 Commerce értékelési környezet kiépítése</span><span class="sxs-lookup"><span data-stu-id="c4bc7-103">Provision a Dynamics 365 Commerce evaluation environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c4bc7-104">Ez a témakör bemutatja, hogyan lehet egy Microsoft Dynamics 365 Commerce értékelési környezetet létesíteni.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-104">This topic explains how to provision a Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

<span data-ttu-id="c4bc7-105">A művelet elkezdése előtt ajánljuk, hogy a jelen témakörben keressen egy rövid áttekintést, hogy megtudja, mire van szüksége a folyamatnak.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-105">Before you begin, we recommend that you take a quick scan through this topic to get an idea of what the process requires.</span></span>

> [!NOTE]
> <span data-ttu-id="c4bc7-106">A Commerce értékelési környezetek általában nem állnak rendelkezésre, és a partnerek és a vevők számára a kérelem alapján biztosítják.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-106">Commerce evaluation environments aren't generally available, and are granted to partners and customers on a per-request basis.</span></span> <span data-ttu-id="c4bc7-107">További információért lépjen kapcsolatba Microsoft-partnerének kapcsolattartójával.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-107">For more information, reach out to your Microsoft partner contact.</span></span>

<span data-ttu-id="c4bc7-108">A Commerce értékelési környezetének sikeres létrehozásához létre kell hoznia egy projektet, amely egy adott terméknévvel és típussal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-108">To successfully provision a Commerce evaluation environment, you must create a project that has a specific product name and type.</span></span> <span data-ttu-id="c4bc7-109">A környezet és a Commerce Scale Unit (CSU) szintén rendelkezik bizonyos paraméterekkel, amelyeket későbbiekben, az e-kereskedelem létesítésekor használnia kell.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-109">The environment and Commerce Scale Unit (CSU) also have some specific parameters that you must use when you expect to provision e-Commerce later.</span></span> <span data-ttu-id="c4bc7-110">Az ebben a témakörben szereplő útmutatás leírja a létesítéshez szükséges összes lépést és a használandó paramétereket.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-110">The instructions in this topic describe all the steps that are required to complete provisioning and the parameters that you must use.</span></span>

<span data-ttu-id="c4bc7-111">A Kereskedelem értékelési környezetének sikeres létesítését követően meg kell tennie néhány létesítést követő lépést a felkészítéséhez.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-111">After you successfully provision your Commerce evaluation environment, you must complete a few post-provisioning steps to prepare it for use.</span></span> <span data-ttu-id="c4bc7-112">Bizonyos lépések nem kötelezők, az értékelni kívánt rendszer bizonyos szempontjaitól függően.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-112">Some steps are optional, depending on the aspects of the system that you want to evaluate.</span></span> <span data-ttu-id="c4bc7-113">A választható lépéseket a későbbiekben bármikor befejezheti.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-113">You can always complete the optional steps later.</span></span>

<span data-ttu-id="c4bc7-114">A Kereskedelem értékelési környezetének létesítés utáni konfigurálásáról további információt a következő témakörben talál: [Kereskedelem értékelési környezetének konfigurálása](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="c4bc7-114">For information about how to configure your Commerce evaluation environment after you provision it, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span> <span data-ttu-id="c4bc7-115">A Kereskedelem értékelési környezete nem kötelező funkcióinak konfigurálásáról további információt a következő témakörben talál: [Kereskedelem értékelési környezete nem kötelező funkcióinak konfigurálása](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="c4bc7-115">For information about how to configure optional features for your Commerce evaluation environment, see [Configure optional features for a Commerce evaluation environment](cpe-optional-features.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c4bc7-116">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="c4bc7-116">Prerequisites</span></span>

<span data-ttu-id="c4bc7-117">A következő előfeltételeknek kell érvényben lenniük a Kereskedelem értékelési környezetének létesítése előtt:</span><span class="sxs-lookup"><span data-stu-id="c4bc7-117">The following prerequisites must be in place before you can provision your Commerce evaluation environment:</span></span>

- <span data-ttu-id="c4bc7-118">Önt már beléptették az értékelési programba, és kapacitást biztosítottak egy értékelési környezethez.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-118">You have been onboarded into the evaluation program and granted capacity for an evaluation environment.</span></span>
- <span data-ttu-id="c4bc7-119">Elérhetővé teszi a Microsoft Dynamics Lifecycle Services (LCS) portál elérését.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-119">You have access to the Microsoft Dynamics Lifecycle Services (LCS) portal.</span></span>
- <span data-ttu-id="c4bc7-120">Ön meglévő Microsoft Dynamics 365 partner vagy vevő, és létre tud hozni egy Dynamics 365 Commerce projektet.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-120">You are an existing Microsoft Dynamics 365 partner or customer and are able to create a Dynamics 365 Commerce project.</span></span>
- <span data-ttu-id="c4bc7-121">Rendszergazdai jogosultsággal rendelkezik a Microsoft Azure-előfizetéshez, vagy kapcsolatba lép egy előfizetési adminisztrátorral, aki a szükség esetén segítséget nyújthat.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-121">You have administrator access to your Microsoft Azure subscription, or you're in contact with a subscription administrator who can assist you if required.</span></span>
- <span data-ttu-id="c4bc7-122">Rendelkezésére áll az Azure Active Directory (Azure AD) bérlői azonosító.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-122">You have your Azure Active Directory (Azure AD) tenant ID available.</span></span>
- <span data-ttu-id="c4bc7-123">Létrehozott egy Azure AD biztonsági csoportot, amelyet az e-kereskedelmi rendszeradminisztrátori csoportként használhat, és a rendelkezésére áll annak azonosítója.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-123">You've created an Azure AD security group that can be used as an e-Commerce system admin group, and you have its ID available.</span></span>
- <span data-ttu-id="c4bc7-124">Létrehozott egy Azure AD biztonsági csoportot, amelyet minősítési vagy értékelési moderátori csoportként használhat, és a rendelkezésére áll annak azonosítója.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-124">You've created an Azure AD security group that can be used as a Ratings and Reviews moderator group, and you have its ID available.</span></span> <span data-ttu-id="c4bc7-125">(Ez a biztonsági csoport lehet ugyanaz, mint az e-kereskedelmi rendszeradminisztrátori csoport.)</span><span class="sxs-lookup"><span data-stu-id="c4bc7-125">(This security group can be the same as the e-Commerce system admin group.)</span></span>

<span data-ttu-id="c4bc7-126">Ne felejtse el, hogy ez a lista nem teljes.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-126">Note that this list isn't exhaustive.</span></span> <span data-ttu-id="c4bc7-127">Ha bármilyen problémába ütközik forduljon a Microsoft-partnere kapcsolattartójához.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-127">If you experience any issues, reach out to your Microsoft partner contact for assistance.</span></span>

## <a name="provision-your-commerce-evaluation-environment"></a><span data-ttu-id="c4bc7-128">Commerce értékelési környezet kiépítése</span><span class="sxs-lookup"><span data-stu-id="c4bc7-128">Provision your Commerce evaluation environment</span></span>

<span data-ttu-id="c4bc7-129">Ezek az eljárások ismertetik a Commerce értékelési környezet kiépítését.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-129">These procedures explain how to provision a Commerce evaluation environment.</span></span> <span data-ttu-id="c4bc7-130">A sikeres befejezést követően a Commerce értékelési környezete készen áll a konfigurációra.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-130">After you successfully complete them, the Commerce evaluation environment will be ready for configuration.</span></span> <span data-ttu-id="c4bc7-131">Az itt ismertetett tevékenységek az LCS portálon történnek.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-131">All the activities that are described here occur in the LCS portal.</span></span>

### <a name="create-a-new-project"></a><span data-ttu-id="c4bc7-132">Új projekt létrehozása</span><span class="sxs-lookup"><span data-stu-id="c4bc7-132">Create a new project</span></span>

<span data-ttu-id="c4bc7-133">Új LCS projekt létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-133">To create a new project in LCS, follow these steps.</span></span>

1. <span data-ttu-id="c4bc7-134">Az LCS-kezdőlapon válassza a pluszjelet (**+**) a projekt létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-134">On the LCS home page, select the plus sign (**+**) to create a project.</span></span>
1. <span data-ttu-id="c4bc7-135">A jobb oldali panelen kövesse az alábbi lépések egyikét:</span><span class="sxs-lookup"><span data-stu-id="c4bc7-135">In the right pane, follow one of these steps:</span></span>

    - <span data-ttu-id="c4bc7-136">Ha Ön partner, válassza az **Áttelepítés, megoldások létrehozása és tanulás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-136">If you're a partner, select **Migrate, create solutions, and learn**.</span></span>
    - <span data-ttu-id="c4bc7-137">Ha Ön ügyfél, válassza ki **Lehetséges előértékesítések** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-137">If you're a customer, select **Prospective presales**.</span></span>

1. <span data-ttu-id="c4bc7-138">Adja meg a nevet, leírást és iparágat.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-138">Enter a name, description, and industry.</span></span>
1. <span data-ttu-id="c4bc7-139">A **Terméknév** mezőben válassza a **Dynamics 365 Commerce** elemet.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-139">In the **Product name** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="c4bc7-140">A **Termék verziója** mezőben válassza a **Dynamics 365 Commerce** elemet.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-140">In the **Product version** field, select **Dynamics 365 Commerce**.</span></span>
1. <span data-ttu-id="c4bc7-141">A **Módszertan** mezőben válassza a **Dynamics Retail-implementáció módszertana** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-141">In the **Methodology** field, select **Dynamics Retail implementation methodology**.</span></span>
1. <span data-ttu-id="c4bc7-142">Nem kötelező: Szerepköröket és felhasználókat létező projektből is importálhat.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-142">Optional: You can import roles and users from an existing project.</span></span>
1. <span data-ttu-id="c4bc7-143">Válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-143">Select **Create**.</span></span> <span data-ttu-id="c4bc7-144">Megjelenik a projektnézet.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-144">The project view appears.</span></span>

### <a name="add-the-azure-connector"></a><span data-ttu-id="c4bc7-145">Azure-összekötő hozzáadása</span><span class="sxs-lookup"><span data-stu-id="c4bc7-145">Add the Azure Connector</span></span>

<span data-ttu-id="c4bc7-146">Az Azure összekötőnek az LCS-projekthez történő hozzáadásához kövesse az [Azure Resource Manager felvételi folyamat teljesítése](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding) lépéseit.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-146">To add the Azure Connector to your LCS project, follow the steps in [Complete the Azure Resource Manager (ARM) onboarding process](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/deployment/arm-onboarding).</span></span>

### <a name="deploy-the-environment"></a><span data-ttu-id="c4bc7-147">Környezet telepítése</span><span class="sxs-lookup"><span data-stu-id="c4bc7-147">Deploy the environment</span></span>

<span data-ttu-id="c4bc7-148">Tegye a következőket a környezet telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-148">To deploy the environment, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="c4bc7-149">Előfordulhat, hogy nem kell a 6., 7. és/vagy 8. lépést végrehajtania, mert az egyetlen lehetőséggel rendekező oldalakat a rendszer átugorja.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-149">You might not have to complete steps 6, 7, and/or 8, because pages that have a single option are skipped.</span></span> <span data-ttu-id="c4bc7-150">Amikor a **Környezeti paraméterek** nézetben van, erősítse meg, hogy a **Dynamics 365 Commerce – bemutató (10.0.* x* a Platform update *xx* frissítéssel)\*\* szöveg közvetlenül a **Környezet neve** mező felett jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-150">When you're in the **Environment parameters** view, confirm that the text **Dynamics 365 Commerce - Demo (10.0.* x* with Platform update *xx*)\*\* appears directly above the **Environment name** field.</span></span> <span data-ttu-id="c4bc7-151">További részletekért lásd a 8. lépés után megjelenő ábrát.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-151">For details, see the illustration that appears after step 8.</span></span>

1. <span data-ttu-id="c4bc7-152">Válassza a felső menü **Felhőalapú környezetek** pontját.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-152">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="c4bc7-153">Környezet hozzáadásához kattintson a **+ hozzáadás** gombra.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-153">Select **Add** to add an environment.</span></span>
1. <span data-ttu-id="c4bc7-154">Válassza ki az **Alkalmazás verziószáma** mezőben a legfrissebb verziót.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-154">In the **Application version** field, select the most current version.</span></span> <span data-ttu-id="c4bc7-155">Ha a legfrissebb verziótól különböző verziót kell kijelölni, akkor ne válasszon **10.0.14** előtti verziót.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-155">If you have a specific need to select an application version other than the most current version, do not select a version prior to **10.0.14**.</span></span>
1. <span data-ttu-id="c4bc7-156">A **Platform verziószáma** mezőben használja a kiválasztott alkalmazás verziójának automatikusan kiválasztott platform verzióját.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-156">In the **Platform version** field, use the platform version that is automatically chosen for the application version you selected.</span></span> 

    ![Válassza ki az alkalmazás- és a platformverziókat](./media/project1.png)

1. <span data-ttu-id="c4bc7-158">Válassza ki **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-158">Select **Next**.</span></span>
1. <span data-ttu-id="c4bc7-159">**Demó** kiválasztása környezeti topológiaként.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-159">Select **Demo** as the environment topology.</span></span>

    ![1. környezeti topológia kiválasztása](./media/project2.png)

1. <span data-ttu-id="c4bc7-161">A **Környezet telepítése** oldalán adja meg a környezet nevét.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-161">On the **Deploy environment** page, enter an environment name.</span></span> <span data-ttu-id="c4bc7-162">A Speciális beállításokat ne módosítsa.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-162">Leave the advanced settings as they are.</span></span>

    ![Környezet telepítése oldal](./media/project4.png)

1. <span data-ttu-id="c4bc7-164">Szükség szerint állítsa be a virtuális gép méretét.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-164">Adjust the VM size as required.</span></span> <span data-ttu-id="c4bc7-165">(A következő virtuálisgép-raktározási egységet javasoljuk: \[SKU\] **D13 v2**.)</span><span class="sxs-lookup"><span data-stu-id="c4bc7-165">(We recommend VM stock keeping unit \[SKU\] **D13 v2**.)</span></span>
1. <span data-ttu-id="c4bc7-166">Tekintse át az árképzési és licencelési feltételeket, majd jelölje be a jelölőnégyzetet annak jelzésére, hogy elfogadja azokat.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-166">Review the pricing and licensing terms, and then select the check box to indicate that you agree to them.</span></span>
1. <span data-ttu-id="c4bc7-167">Válassza ki **Következő** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-167">Select **Next**.</span></span>
1. <span data-ttu-id="c4bc7-168">A telepítési visszaigazolás oldalán győződjön meg róla, hogy az adatok helyesek, majd kattintson a **Telepítés** gombra.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-168">On the deployment confirmation page, verify that the details are correct, and then select **Deploy**.</span></span> <span data-ttu-id="c4bc7-169">Vissza fog térni a **Felhőalapú környezetek** nézethez, és a környezetnek meg kell jelennie a listán.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-169">You're returned to the **Cloud-hosted environments** view, and your environment should appear in the list.</span></span>

    <span data-ttu-id="c4bc7-170">A kért környezet várólistán jelenik meg, majd telepíthető.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-170">Your requested environment will appear as queued and then deploying.</span></span> <span data-ttu-id="c4bc7-171">A környezeti munkafolyamatok némi időt fognak igénybe venni.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-171">The environment workflows will take some time to be completed.</span></span> <span data-ttu-id="c4bc7-172">Ezért nézzen vissza körülbelül 6–9 óra múlva.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-172">Therefore, check back after approximately six to nine hours.</span></span>

1. <span data-ttu-id="c4bc7-173">A folytatás előtt győződjön meg arról, hogy a környezet állapota **Telepített**.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-173">Before you continue, make sure that the status of your environment is **Deployed**.</span></span>

### <a name="initialize-the-commerce-scale-unit-cloud"></a><span data-ttu-id="c4bc7-174">A Commerce Scale Unit (felhő) inicializálása</span><span class="sxs-lookup"><span data-stu-id="c4bc7-174">Initialize the Commerce Scale Unit (cloud)</span></span>

<span data-ttu-id="c4bc7-175">A CSU-cím inicializálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-175">To initialize the CSU, follow these steps.</span></span>

1. <span data-ttu-id="c4bc7-176">A **felhőalapú környezetek** nézetben válassza ki a saját környezetét a listából.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-176">In the **Cloud-hosted environments** view, select your environment in the list.</span></span>
1. <span data-ttu-id="c4bc7-177">Kattintson a jobb oldalon található környezeti nézet **Minden részlet** elemére.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-177">In the environment view on the right, select **Full details**.</span></span> <span data-ttu-id="c4bc7-178">Megjelenik a környezeti részletek nézet.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-178">The environment details view appears.</span></span>
1. <span data-ttu-id="c4bc7-179">A **Környezeti funkciók** területen kattintson a **Kezelés** elemre.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-179">Under **Environment features**, select **Manage**.</span></span>
1. <span data-ttu-id="c4bc7-180">A **Commerce** lapon válassza az **Inicializálás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-180">On the **Commerce** tab, select **Initialize**.</span></span> <span data-ttu-id="c4bc7-181">Megjelenik a CSU inicializálási paraméterei nézet.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-181">The CSU initialization parameters view appears.</span></span>
1. <span data-ttu-id="c4bc7-182">A **Régió** mezőben válassza ki azt a régiót, amely ugyanazon vagy azon a területen vagy annak közelében van, amelybe a környezetet telepítették.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-182">In the **Region** field, select the region that is the same or close to the region that you deployed the environment to.</span></span>
1. <span data-ttu-id="c4bc7-183">Hagyja a **Verzió** mező értékét változatlanul.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-183">Leave the **Version** field as it is.</span></span>
1. <span data-ttu-id="c4bc7-184">Válassza az **Inicializálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-184">Select **Initialize**.</span></span>
1. <span data-ttu-id="c4bc7-185">A telepítési visszaigazolás oldalán győződjön meg róla, hogy az adatok helyesek, majd kattintson az **Igen** gombra.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-185">On the deployment confirmation page, verify that the details are correct, and then select **Yes**.</span></span> <span data-ttu-id="c4bc7-186">Újra megjelenik a **Commerce Management** nézet, amelyen a **Commerce** lap ki van választva.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-186">The **Commerce management** view displays again, where the **Commerce** tab is selected.</span></span> <span data-ttu-id="c4bc7-187">A CSU várólistára került a létesítéshez.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-187">Your CSU has been queued for provisioning.</span></span>
1. <span data-ttu-id="c4bc7-188">A folytatás előtt győződjön meg arról, hogy az CSU állapota **Sikeres**.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-188">Before you continue, make sure that the status of your CSU is **Success**.</span></span> <span data-ttu-id="c4bc7-189">Az inicializálás körülbelül két-öt órát vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-189">Initialization takes approximately two to five hours.</span></span>

<span data-ttu-id="c4bc7-190">Ha nem találja a **Kezelés** hivatkozást a környezet részletei nézetben, kérjen segítséget a Microsoft kapcsolattartótól.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-190">If you can't find the **Manage** link in the environment details view, reach out to your Microsoft contact for assistance.</span></span>

<span data-ttu-id="c4bc7-191">A következő hibaüzenet jelenhet meg a rendszerbe állítási folyamat során:</span><span class="sxs-lookup"><span data-stu-id="c4bc7-191">During the deployment process, you might receive the following error message:</span></span>

> <span data-ttu-id="c4bc7-192">A kiértékelési (demó-/teszt-) környezetekben regisztrálni kell a skálázásiegység-csatlakoztató alkalmazást \<application ID\> a központi felületen.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-192">Evaluation (demo/test) environments need to register the scale unit connector application \<application ID\> in headquarters.</span></span>

<span data-ttu-id="c4bc7-193">Ha a CSU inicializálása sikertelen, és megjelenik ez a hibaüzenet, jegyezze fel az alkalmazásazonosítót, amely globálisan egyedi azonosító (GUID), majd hajtsa végre a következő szakaszban található lépéseket a CSU telepítési alkalmazásnak a Commerce központi felületén való regisztrálásához.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-193">If the CSU initialization fails and you receive this error message, make a note of the application ID, which is a globally unique identifier (GUID), and then follow the steps in the next section to register the CSU deployment application in Commerce headquarters.</span></span>

### <a name="register-the-csu-deployment-application-in-commerce-headquarters-if-required"></a><span data-ttu-id="c4bc7-194">Regisztrálja a CSU telepítési alkalmazást a Commerce központi felületén (ha szükséges)</span><span class="sxs-lookup"><span data-stu-id="c4bc7-194">Register the CSU deployment application in Commerce headquarters (if required)</span></span>

<span data-ttu-id="c4bc7-195">A CSU telepítési alkalmazás Commerce központi felületén történő regisztrációjához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-195">To register the CSU deployment application in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="c4bc7-196">A Commerce központi felületén lépjen a **Rendszerfelügyelet \> Beállítás \> Azure Active Directory-alkalmazások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-196">In Commerce headquarters, go to **System administration \> Setup \> Azure Active Directory applications**.</span></span>
1. <span data-ttu-id="c4bc7-197">Az **Ügyfélazonosító** oszlopban adja meg a CSU inicializálásakor kapott hibaüzenet alkalmazásazonosítóját.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-197">In the **Client Id** column, enter the application ID from the CSU initialization error message that you received.</span></span>
1. <span data-ttu-id="c4bc7-198">A **Név** oszlopban adjon meg egy leíró szöveget (például **CSU Eval**).</span><span class="sxs-lookup"><span data-stu-id="c4bc7-198">In the **Name** column, enter any descriptive text (for example, **CSU Eval**).</span></span>
1. <span data-ttu-id="c4bc7-199">A **Felhasználói azonosító** oszlopba írja be a **RetailServiceAccount** szöveget.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-199">In the **User ID** column, enter **RetailServiceAccount**.</span></span>
1. <span data-ttu-id="c4bc7-200">Próbálja meg újra a CSU inicializálását és telepítését az LCS-ről.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-200">Retry the CSU initialization and deployment from LCS.</span></span>

### <a name="initialize-e-commerce"></a><span data-ttu-id="c4bc7-201">Az elektronikus kereskedelem inicializálása</span><span class="sxs-lookup"><span data-stu-id="c4bc7-201">Initialize e-Commerce</span></span>

<span data-ttu-id="c4bc7-202">Az e-kereskedelem inicializálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-202">To initialize e-Commerce, follow these steps.</span></span>

1. <span data-ttu-id="c4bc7-203">Az **e-kereskedelem** lapon tekintse át az értékelési verzió jóváhagyását, majd válassza a **Beállítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-203">On the **e-Commerce** tab, review the evaluation consent, and then select **Setup**.</span></span>
1. <span data-ttu-id="c4bc7-204">Az **E-kereskedelmi környezet neve** mezőben adjon meg egy nevet.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-204">In the **e-Commerce environment name** field, enter a name.</span></span> <span data-ttu-id="c4bc7-205">Fontos megjegyezni, hogy ez a név az e-kereskedelem példányra mutató néhány URL-címen látható lesz.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-205">Be aware that this name will appear in some of the URLs that point to your e-Commerce instance.</span></span>
1. <span data-ttu-id="c4bc7-206">A **Commerce Scale Unit neve** mezőben válassza ki az CSU-t a listából.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-206">In the **Commerce Scale Unit name** field, select your CSU in the list.</span></span> <span data-ttu-id="c4bc7-207">(A listában csak egy opciónak kell lennie.)</span><span class="sxs-lookup"><span data-stu-id="c4bc7-207">(The list should have only one option.)</span></span>

    <span data-ttu-id="c4bc7-208">Az **e-commerce földrajz** mező automatikusan be van állítva.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-208">The **e-Commerce geography** field is set automatically.</span></span>

1. <span data-ttu-id="c4bc7-209">A folytatáshoz kattintson a **Tovább** gombra.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-209">Select **Next** to continue.</span></span>
1. <span data-ttu-id="c4bc7-210">A **Támogatott állomásnevek** mezőbe írjon be egy tetszőleges érvényes tartományt, például `www.fabrikam.com`.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-210">In the **Supported host names** field, enter any valid domain, such as `www.fabrikam.com`.</span></span>
1. <span data-ttu-id="c4bc7-211">Írja be a használni kívánt biztonsági csoport nevének első néhány betűjét az **AAD biztonsági csoportja rendszergazdának** mezőbe, majd válassza ki a nagyító szimbólumot a keresési eredmények megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-211">In the **AAD security group for system admin** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="c4bc7-212">Válassza ki a megfelelő biztonsági csoportot a listából.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-212">Select the correct security group in the list.</span></span>
1.  <span data-ttu-id="c4bc7-213">Írja be a használni kívánt biztonsági csoport nevének első néhány betűjét az **AAD biztonsági csoport minősítési és értékelési moderátornak** mezőbe, majd válassza ki a nagyító szimbólumot a keresési eredmények megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-213">In the **AAD security group for ratings and review moderator** field, enter the first few letters of the name of the security group that you want to use, and then select the magnifying glass symbol to view the search results.</span></span> <span data-ttu-id="c4bc7-214">Válassza ki a megfelelő biztonsági csoportot a listából.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-214">Select the correct security group in the list.</span></span>
1. <span data-ttu-id="c4bc7-215">Hagyja az **Értékelések és vélemények szolgáltatás engedélyezése** beállítást **Igen** értéken.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-215">Leave the **Enable ratings and review service** option set to **Yes**.</span></span>
1. <span data-ttu-id="c4bc7-216">Válassza az **Inicializálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-216">Select **Initialize**.</span></span> <span data-ttu-id="c4bc7-217">Újra megjelenik a **Commerce Management** nézet, amelyen a **e-kereskedelem** lap ki van választva.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-217">The **Commerce management** view displays again, where the **e-Commerce** tab is selected.</span></span> <span data-ttu-id="c4bc7-218">Az e-kereskedelem inicializálása elindult.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-218">E-Commerce initialization has started.</span></span>
1. <span data-ttu-id="c4bc7-219">A folytatás előtt várja meg, amíg az e-kereskedelem inicializálási állapota **Az inicializálás sikerült** állapotra nem vált.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-219">Before you continue, wait until the status of e-Commerce initialization is **Initialization successful**.</span></span>
1. <span data-ttu-id="c4bc7-220">A jobb alsó sarokban található **Hivatkozások** részben jegyezze fel a következő hivatkozások URL-címeit:</span><span class="sxs-lookup"><span data-stu-id="c4bc7-220">Under **Links** in the lower right, make a note of the URLs for the following links:</span></span>

    * <span data-ttu-id="c4bc7-221">**e-kereskedelmi webhely** -Az e-kereskedelmi webhely gyökerére mutató hivatkozás.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-221">**e-Commerce site** – The link to the root of your e-Commerce site.</span></span>
    * <span data-ttu-id="c4bc7-222">**e-kereskedelmi webhelykészítő** - A webhelykezelési eszközre mutató eszköz.</span><span class="sxs-lookup"><span data-stu-id="c4bc7-222">**Commerce site builder** – The link to the site management tool.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c4bc7-223">További lépések</span><span class="sxs-lookup"><span data-stu-id="c4bc7-223">Next steps</span></span>

<span data-ttu-id="c4bc7-224">A Kereskedelem értékelési környezetének létesítési és konfigurálási folyamatának folytatásához lásd: [Kereskedelem értékelési környezetének konfigurálása](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="c4bc7-224">To continue the process of provisioning and configuring your Commerce evaluation environment, see [Configure a Commerce evaluation environment](cpe-post-provisioning.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c4bc7-225">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="c4bc7-225">Additional resources</span></span>

[<span data-ttu-id="c4bc7-226">Dynamics 365 Commerce értékelési környezet áttekintése</span><span class="sxs-lookup"><span data-stu-id="c4bc7-226">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="c4bc7-227">Dynamics 365 Commerce értékelési környezet konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c4bc7-227">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="c4bc7-228">BOPIS konfigurálása Dynamics 365 Commerce értékelési környezetben</span><span class="sxs-lookup"><span data-stu-id="c4bc7-228">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="c4bc7-229">Dynamics 365 Commerce értékelési környezet választható funkcióinak konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c4bc7-229">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="c4bc7-230">Dynamics 365 Commerce értékelési környezet GYIK</span><span class="sxs-lookup"><span data-stu-id="c4bc7-230">Dynamics 365 Commerce evaluation environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="c4bc7-231">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="c4bc7-231">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="c4bc7-232">Commerce Scale Unit (felhő)</span><span class="sxs-lookup"><span data-stu-id="c4bc7-232">Commerce Scale Unit (cloud)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="c4bc7-233">Microsoft Azure-portál</span><span class="sxs-lookup"><span data-stu-id="c4bc7-233">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="c4bc7-234">Dynamics 365 Commerce-webhely</span><span class="sxs-lookup"><span data-stu-id="c4bc7-234">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
