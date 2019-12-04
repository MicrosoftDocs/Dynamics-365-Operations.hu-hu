---
title: Alkalmazás-metaadatokhoz való hozzáférés összekapcsolt alkalmazások használatával
description: Az ebben a témakörben leírt lépések azt mutatják be, hogy a Regulatory Configuration Service (RCS) felhasználói hogyan tervezhetik meg egy új elektronikus jelentési (ER) modell hozzárendelését a Finance and Operations metaadatainak használatával.
author: NickSelin
manager: AnnBe
ms.date: 06/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5020b523ca5d76d36f7436a8f43e8629c029e3e8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769878"
---
# <a name="access-application-metadata-by-using-connected-applications"></a><span data-ttu-id="26b00-103">Alkalmazás-metaadatokhoz való hozzáférés összekapcsolt alkalmazások használatával</span><span class="sxs-lookup"><span data-stu-id="26b00-103">Access application metadata by using connected applications</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="26b00-104">A következő lépések leírják, hogy a Regulatory Configuration Service (RCS) Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként tervezhetnek új Elektronikus jelentés (ER) modell hozzárendelést a Finance and Operations alkalmazás metaadatainak használatával.</span><span class="sxs-lookup"><span data-stu-id="26b00-104">The following steps explain how a Regulatory configuration service (RCS) user in the System Administrator or Electronic Reporting Developer role can design a new Electronic reporting (ER) model mapping by using metadata in Finance and Operations.</span></span> <span data-ttu-id="26b00-105">Alkalmazás-metaadatokhoz való hozzáférés online RCS összekapcsolt alkalmazások használatával történik</span><span class="sxs-lookup"><span data-stu-id="26b00-105">Application metadata will be accessed online by using the RCS connected application.</span></span> <span data-ttu-id="26b00-106">A minta ER-modell-hozzárendelést a külföldi kereskedelmi tranzakciók elérése érdekében konfigurálja a program.</span><span class="sxs-lookup"><span data-stu-id="26b00-106">Sample ER model mapping will be configured to access foreign trade transactions.</span></span> <span data-ttu-id="26b00-107">Az alábbi lépések végrehajtásához először hajtsa végre a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](er-configuration-provider-mark-it-active-2016-11.md) cikk lépéseit az RCS-ben.</span><span class="sxs-lookup"><span data-stu-id="26b00-107">To complete these steps, in RCS you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="26b00-108">Ha nem végezte el a témakör lépéseit [Alkalmazás-metaadatokhoz való hozzáférés ER-konfiguráció használatával](access-application-metadata-er-configuration.md), nyissa meg az [Elektronikus jelentéskészítési példák lapot](https://go.microsoft.com/fwlink/?linkid=862266) a következő ER-konfigurációk letöltéséhez és mentéséhez: Foreign trade metadata.xml; Foreign trade model.xml; Foreign trade mapping.xml, majd hajtsa végre az eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="26b00-108">If you have not completed the steps in the topic, [Access application metadata by using ER configuration](access-application-metadata-er-configuration.md), go to the [Electronic reporting examples page](https://go.microsoft.com/fwlink/?linkid=862266) to download and save the following ER configurations: Foreign trade metadata.xml; Foreign trade model.xml; Foreign trade mapping.xml, and then complete the steps in the procedure.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="26b00-109">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="26b00-109">Prerequisites</span></span>
1. <span data-ttu-id="26b00-110">Ugorjon **Az összes munkaterület** > **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="26b00-110">Go to **All workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="26b00-111">Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és **aktívként** van megjelölve a konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="26b00-111">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="26b00-112">Ha nem látja a konfigurációszolgáltatót, végezze el a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](er-configuration-provider-mark-it-active-2016-11.md) cikk lépéseit.</span><span class="sxs-lookup"><span data-stu-id="26b00-112">If you don’t see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 

## <a name="get-required-er-configurations"></a><span data-ttu-id="26b00-113">Szükséges elektronikus jelentéskészítés-konfigurációk lekérése</span><span class="sxs-lookup"><span data-stu-id="26b00-113">Get required ER configurations</span></span>
1. <span data-ttu-id="26b00-114">Kattintson a **Jelentéskészítés konfigurációi** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="26b00-114">Click **Reporting configurations**.</span></span> 
2. <span data-ttu-id="26b00-115">Ha már végrehajtotta az [Alkalmazás-metaadatokhoz való hozzáférés ER-konfiguráció használatával](access-application-metadata-er-configuration.md) eljárásban megadott lépéseket, akkor az aktuális RCS-példány már rendelkezik az összes szükséges ER konfigurációval (külkereskedelmi metaadatok, modell-hozzárendelési konfigurációk).</span><span class="sxs-lookup"><span data-stu-id="26b00-115">If you already completed the steps in the [Access application metadata by using ER configuration](access-application-metadata-er-configuration.md) procedure, you already have all necessary ER configurations (foreign trade metadata, model and mapping configurations) in the current RCS instance.</span></span> <span data-ttu-id="26b00-116">Az alfeladat többi műveletét kihagyhatja.</span><span class="sxs-lookup"><span data-stu-id="26b00-116">You can skip all the remaining steps of this sub-task.</span></span> 
3. <span data-ttu-id="26b00-117">Kattintson az **Átváltás** elemre.</span><span class="sxs-lookup"><span data-stu-id="26b00-117">Click **Exchange**.</span></span> 
4. <span data-ttu-id="26b00-118">Kattintson a **Betöltés XML-fájlból** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="26b00-118">Click **Load from XML file**.</span></span> 
5. <span data-ttu-id="26b00-119">A **Tallózás** használatával válassza ki a **Foreign trade metadata.xml** fájlt.</span><span class="sxs-lookup"><span data-stu-id="26b00-119">Click **Browse** and select the **Foreign trade metadata.xml** file.</span></span> 
6. <span data-ttu-id="26b00-120">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="26b00-120">Click **OK**.</span></span> 
7. <span data-ttu-id="26b00-121">Kattintson az **Átváltás** elemre.</span><span class="sxs-lookup"><span data-stu-id="26b00-121">Click **Exchange**.</span></span> 
8. <span data-ttu-id="26b00-122">Kattintson a **Betöltés XML-fájlból** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="26b00-122">Click **Load from XML file**.</span></span> 
9. <span data-ttu-id="26b00-123">A **Tallózás** használatával válassza ki a **Foreign trade model.xml** fájlt.</span><span class="sxs-lookup"><span data-stu-id="26b00-123">Click **Browse** and select the **Foreign trade model.xml** file.</span></span> 
10. <span data-ttu-id="26b00-124">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="26b00-124">Click **OK**.</span></span> 
11. <span data-ttu-id="26b00-125">Kattintson az **Átváltás** elemre.</span><span class="sxs-lookup"><span data-stu-id="26b00-125">Click **Exchange**.</span></span> 
12. <span data-ttu-id="26b00-126">Kattintson a **Betöltés XML-fájlból** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="26b00-126">Click **Load from XML file**.</span></span> 
13. <span data-ttu-id="26b00-127">A **Tallózás** használatával válassza ki a **Foreign trade mapping.xml** fájlt.</span><span class="sxs-lookup"><span data-stu-id="26b00-127">Click **Browse** and select the **Foreign trade mapping.xml** file.</span></span> 
14. <span data-ttu-id="26b00-128">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="26b00-128">Click **OK**.</span></span> 

## <a name="register-a-connected-application"></a><span data-ttu-id="26b00-129">Egy összekapcsolt alkalmazás regisztrálása</span><span class="sxs-lookup"><span data-stu-id="26b00-129">Register a connected application</span></span>
1. <span data-ttu-id="26b00-130">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="26b00-130">Close the page.</span></span> 
2. <span data-ttu-id="26b00-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="26b00-131">Close the page.</span></span> 
3. <span data-ttu-id="26b00-132">Ugorjon **Az összes munkaterület** > **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="26b00-132">Go to **All workspaces** > **Electronic reporting**.</span></span> 
4. <span data-ttu-id="26b00-133">Kattintson az **Összekapcsolt alkalmazások** elemre.</span><span class="sxs-lookup"><span data-stu-id="26b00-133">Click **Connected applications**.</span></span> 
5. <span data-ttu-id="26b00-134">Győződjön meg róla, hogy a konfigurált alkalmazás Azura alapú és elérhető az aktuális RCS-felhasználó számára.</span><span class="sxs-lookup"><span data-stu-id="26b00-134">Make sure that the configured application is Azura based and accessible for the current RCS user.</span></span> <span data-ttu-id="26b00-135">Azt is meg kell adni, hogy az aktuális RCS felhasználó hozzáférjen a kiválasztott alkalmazáshoz, és az alkalmazás felhasználóként regisztrálva van az alkalmazás metaadatainak elérése érdekében.</span><span class="sxs-lookup"><span data-stu-id="26b00-135">It is also required that the current RCS user has access to the selected application and has been registered as a user of this application playing a role giving him privileges to access application’s metadata.</span></span> 
6. <span data-ttu-id="26b00-136">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="26b00-136">Click **New**.</span></span> 
7. <span data-ttu-id="26b00-137">A **Név** mezőbe írja be a „MyConnectedApp” szöveget.</span><span class="sxs-lookup"><span data-stu-id="26b00-137">In the **Name** field, type 'MyConnectedApp'.</span></span> 
8. <span data-ttu-id="26b00-138">Az **Alkalmazás** mezőbe írja be a: https:// mycompany.operations.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="26b00-138">In the **Application** field, type 'https:// mycompany.operations.dynamics.com'.</span></span> 
9. <span data-ttu-id="26b00-139">A **Bérlő** mezőbe írja be a következőt: „mycompany.onmicrosoft.com”.</span><span class="sxs-lookup"><span data-stu-id="26b00-139">In the **Tenant** field, type ‘mycompany.onmicrosoft.com’.</span></span> 
10. <span data-ttu-id="26b00-140">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="26b00-140">Click **Save**.</span></span> 
11. <span data-ttu-id="26b00-141">Ha ellenőrzi a kapcsolatot a konfigurált alkalmazással, akkor a **Csatlakozás a távoli alkalmazáshoz** lapon kattintson a **Kattintson ide a kijelölt távoli alkalmazáshoz való kapcsolódáshoz** elemre.</span><span class="sxs-lookup"><span data-stu-id="26b00-141">When you check connection to configured application, on the **Connect to remote application** page click **Click here to connect to selected remote application** link.</span></span> 
12. <span data-ttu-id="26b00-142">Kattintson a **Kapcsolat ellenőrzése** elemre.</span><span class="sxs-lookup"><span data-stu-id="26b00-142">Click **Check connection**.</span></span> 
13. <span data-ttu-id="26b00-143">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="26b00-143">Click **Close**.</span></span> 
14. <span data-ttu-id="26b00-144">Amikor a kapcsolat ellenőrzése sikeres volt, a program frissíti a verziószámot és a bérlő adatait a konfigurált alkalmazáshoz az aktuális rácsban.</span><span class="sxs-lookup"><span data-stu-id="26b00-144">When the connection validation succeeded, version and tenant details will be updated for the configured application in the current grid.</span></span> 

## <a name="review-existing-model-mapping-configuration"></a><span data-ttu-id="26b00-145">Meglévő modell leképezés konfiguráció áttekintése</span><span class="sxs-lookup"><span data-stu-id="26b00-145">Review existing model mapping configuration</span></span>
1. <span data-ttu-id="26b00-146">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="26b00-146">Close the page.</span></span> 
2. <span data-ttu-id="26b00-147">Kattintson a **Jelentéskészítés konfigurációi** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="26b00-147">Click **Reporting configurations**.</span></span> 
3. <span data-ttu-id="26b00-148">A fában bontsa ki a **Foreign trade model** elemet.</span><span class="sxs-lookup"><span data-stu-id="26b00-148">In the tree, expand **Foreign trade model**.</span></span> 
4. <span data-ttu-id="26b00-149">A fán válassza ki a **Foreign trade model\Foreign trade mapping** elemet.</span><span class="sxs-lookup"><span data-stu-id="26b00-149">In the tree, select **Foreign trade model\Foreign trade mapping**.</span></span> 
5. <span data-ttu-id="26b00-150">Bontsa ki az **Előfeltételek** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="26b00-150">Expand the **Prerequisites** section.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="26b00-151">Ez a leképezés jelenleg a metaadat-konfigurációra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="26b00-151">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="26b00-152">A konfiguráció alkalmazás metaadatait a program felkínálja, miközben a modell hozzárendelését tervezik.</span><span class="sxs-lookup"><span data-stu-id="26b00-152">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 

6. <span data-ttu-id="26b00-153">Kattintson a **Tervező** pontra.</span><span class="sxs-lookup"><span data-stu-id="26b00-153">Click **Designer**.</span></span> 
7. <span data-ttu-id="26b00-154">Kattintson a **Tervező** pontra.</span><span class="sxs-lookup"><span data-stu-id="26b00-154">Click **Designer**.</span></span> 
8. <span data-ttu-id="26b00-155">A fastruktúrában válassza ki a következőt: **Dynamics 365 for Operations„\Tábla rekordjai** csomópont.</span><span class="sxs-lookup"><span data-stu-id="26b00-155">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
9. <span data-ttu-id="26b00-156">Kattintson a **Gyökér hozzáadása** gombra.</span><span class="sxs-lookup"><span data-stu-id="26b00-156">Click **Add root**.</span></span> 
10. <span data-ttu-id="26b00-157">A **Tábla** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="26b00-157">In the **Table** field, enter or select a value.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="26b00-158">Ez a leképezés jelenleg a metaadat-konfigurációra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="26b00-158">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="26b00-159">A konfiguráció alkalmazás metaadatait a program felkínálja, miközben a modell hozzárendelését tervezik.</span><span class="sxs-lookup"><span data-stu-id="26b00-159">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 

11. <span data-ttu-id="26b00-160">Kattintson a **Mégse** gombra.</span><span class="sxs-lookup"><span data-stu-id="26b00-160">Click **Cancel**.</span></span> 
12. <span data-ttu-id="26b00-161">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="26b00-161">Close the page.</span></span> 
13. <span data-ttu-id="26b00-162">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="26b00-162">Close the page.</span></span> 

## <a name="assign-connected-application-to-model-mapping"></a><span data-ttu-id="26b00-163">Csatlakoztatott alkalmazás társítása a modell-hozzárendeléshez</span><span class="sxs-lookup"><span data-stu-id="26b00-163">Assign connected application to model mapping</span></span> 
1. <span data-ttu-id="26b00-164">Kattintson a **Szerkesztés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="26b00-164">Click **Edit**.</span></span> 
2. <span data-ttu-id="26b00-165">Válassza ki a **MyConnectedApp** alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="26b00-165">Select **MyConnectedApp** application.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="26b00-166">Ez a leképezés jelenleg a kiválasztott összekapcsolt alkalmazás metaadataira vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="26b00-166">Currently, this mapping refers to the metadata of the selected connected application.</span></span> <span data-ttu-id="26b00-167">Amikor ugyanaz a leképezés a metaadatok konfigurációját és a kapcsolódó alkalmazást egyszerre hivatkozza, a program a csatlakoztatott alkalmazás metaadatait fogja használni.</span><span class="sxs-lookup"><span data-stu-id="26b00-167">When the same mapping refers to metadata configuration and connected application at the same time, metadata of the connected application will be used.</span></span> 

3. <span data-ttu-id="26b00-168">Kattintson a **Tervező** pontra.</span><span class="sxs-lookup"><span data-stu-id="26b00-168">Click **Designer**.</span></span> 
4. <span data-ttu-id="26b00-169">Kattintson a **Tervező** pontra.</span><span class="sxs-lookup"><span data-stu-id="26b00-169">Click **Designer**.</span></span> 
5. <span data-ttu-id="26b00-170">A fastruktúrában válassza ki a következőt: **Dynamics 365 for Operations„\Tábla rekordjai** csomópont.</span><span class="sxs-lookup"><span data-stu-id="26b00-170">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
6. <span data-ttu-id="26b00-171">Kattintson a **Gyökér hozzáadása** gombra.</span><span class="sxs-lookup"><span data-stu-id="26b00-171">Click **Add root**.</span></span> 
7. <span data-ttu-id="26b00-172">A **Tábla** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="26b00-172">In the **Table** field, enter or select a value.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="26b00-173">Már több, mint két alkalmazástábla szerepelt, mivel ez a leképezés a társított alkalmazás összes metaadatát felhasználja.</span><span class="sxs-lookup"><span data-stu-id="26b00-173">More than two application tables were offered now as this mapping uses all the metadata of the connected application that has been assigned for it.</span></span> 

8. <span data-ttu-id="26b00-174">Kattintson a **Mégse** gombra.</span><span class="sxs-lookup"><span data-stu-id="26b00-174">Click **Cancel**.</span></span> 
9. <span data-ttu-id="26b00-175">Kattintson az **Érvényesítés** gombra.</span><span class="sxs-lookup"><span data-stu-id="26b00-175">Click **Validate**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="26b00-176">Az adatmodell elemeit az adatforrások olyan cikkeihez társítottuk sikeresen, amelyek leírása az ehhez a leképezéshez hozzárendelt összekapcsolt alkalmazás metaadatainak részleteivel történik.</span><span class="sxs-lookup"><span data-stu-id="26b00-176">We successfully bound elements of data model with items of data sources that are described by using details of metadata of the connected application that has been assigned for this mapping.</span></span> 

10. <span data-ttu-id="26b00-177">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="26b00-177">Close the page.</span></span> 
11. <span data-ttu-id="26b00-178">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="26b00-178">Close the page.</span></span> 

<span data-ttu-id="26b00-179">Ha egy másik verziójú alkalmazás metaadatainak használatával szeretné értékelni ezt a modellt, akkor regisztráljon egy másik összekapcsolt alkalmazást, rendelje hozzá a modell hozzárendeléséhez, és ellenőrizze az új metaadatokkal összevetve.</span><span class="sxs-lookup"><span data-stu-id="26b00-179">When you need to evaluate this model mapping by using metadata of a different version application, register another connected application, assign it to this model mapping and validate it against new metadata.</span></span>
