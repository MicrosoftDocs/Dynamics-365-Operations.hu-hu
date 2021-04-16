---
title: Ismétlődő adatexportálási alkalmazás létrehozása
description: Ez a cikk azt mutatja be, hogyan lehet olyan Microsoft Azure logikai alkalmazást létrehozni, amely a Microsoft Dynamics 365 Human Resources adatait ismétlődő ütemezéssel exportálja.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3d7fc01906a017d4214d4794097a11b4a3416b95
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801119"
---
# <a name="create-a-recurring-data-export-app"></a><span data-ttu-id="1d19d-103">Ismétlődő adatexportálási alkalmazás létrehozása</span><span class="sxs-lookup"><span data-stu-id="1d19d-103">Create a recurring data export app</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="1d19d-104">Ez a cikk azt mutatja be, hogyan lehet olyan Microsoft Azure logikai alkalmazást létrehozni, amely a Microsoft Dynamics 365 Human Resources adatait ismétlődő ütemezéssel exportálja.</span><span class="sxs-lookup"><span data-stu-id="1d19d-104">This article shows how to create a Microsoft Azure logic app that exports data from Microsoft Dynamics 365 Human Resources on a recurring schedule.</span></span> <span data-ttu-id="1d19d-105">Az oktatóanyag kihasználja a Human Resources DMF-csomagjának REST alkalmazásprogramozási felületét (API) az adatok exportálásához.</span><span class="sxs-lookup"><span data-stu-id="1d19d-105">The tutorial takes advantage of Human Resources' DMF package REST application programming interface (API) to export the data.</span></span> <span data-ttu-id="1d19d-106">Az adatok exportálása után a logikai alkalmazás az exportált adatcsomagot a Microsoft OneDrive for Business mappába menti.</span><span class="sxs-lookup"><span data-stu-id="1d19d-106">After the data has been exported, the logic app saves the exported data package to a Microsoft OneDrive for Business folder.</span></span>

## <a name="business-scenario"></a><span data-ttu-id="1d19d-107">Üzleti eset</span><span class="sxs-lookup"><span data-stu-id="1d19d-107">Business scenario</span></span>

<span data-ttu-id="1d19d-108">A Microsoft Dynamics 365 integrációkkal kapcsolatos tipikus üzleti forgatókönyv esetében az adatokat ismétlődő ütemezéshez kell exportálni egy alsóbb rétegbeli rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="1d19d-108">In one typical business scenario for Microsoft Dynamics 365 integrations, data must be exported to a downstream system on a recurring schedule.</span></span> <span data-ttu-id="1d19d-109">Ez az oktatóanyag bemutatja, hogy hogyan lehet exportálni az összes dolgozói rekordot a Microsoft Dynamics 365 Human Resources rendszerből, és menteni a dolgozók listáját egy OneDrive for Business mappába.</span><span class="sxs-lookup"><span data-stu-id="1d19d-109">This tutorial shows how to export all worker records from Microsoft Dynamics 365 Human Resources and save the list of workers in a OneDrive for Business folder.</span></span>

> [!TIP]
> <span data-ttu-id="1d19d-110">Az ebben az oktatóanyagban exportált konkrét adatok, valamint az exportált adatok célja csupán példák.</span><span class="sxs-lookup"><span data-stu-id="1d19d-110">The specific data that is exported in this tutorial and the destination of the exported data are only examples.</span></span> <span data-ttu-id="1d19d-111">Ezeket egyszerűen megváltoztathatja az üzleti szükségletek kielégítése érdekében.</span><span class="sxs-lookup"><span data-stu-id="1d19d-111">You can easily change them to meet your business needs.</span></span>

## <a name="technologies-used"></a><span data-ttu-id="1d19d-112">Használt technológiák</span><span class="sxs-lookup"><span data-stu-id="1d19d-112">Technologies used</span></span>

<span data-ttu-id="1d19d-113">Ez az oktatóanyag a következő technológiákat használja:</span><span class="sxs-lookup"><span data-stu-id="1d19d-113">This tutorial uses the following technologies:</span></span>

- <span data-ttu-id="1d19d-114">**[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)** – Az exportálandó dolgozók alapadatforrása.</span><span class="sxs-lookup"><span data-stu-id="1d19d-114">**[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)** – The master data source for workers that will be exported.</span></span>
- <span data-ttu-id="1d19d-115">**[Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)** – az ismétlődő export vezénylését és ütemezését biztosító technológia.</span><span class="sxs-lookup"><span data-stu-id="1d19d-115">**[Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)** – The technology that provides orchestration and scheduling of the recurring export.</span></span>

    - <span data-ttu-id="1d19d-116">**[Csatlakozók](https://docs.microsoft.com/azure/connectors/apis-list)** – a logikai alkalmazás a szükséges végpontokhoz való csatlakoztatásához használt technológia.</span><span class="sxs-lookup"><span data-stu-id="1d19d-116">**[Connectors](https://docs.microsoft.com/azure/connectors/apis-list)** – The technology that is used to connect the logic app to the required endpoints.</span></span>

        - <span data-ttu-id="1d19d-117">[HTTP Azure AD](https://docs.microsoft.com/connectors/webcontents/) csatlakozóval</span><span class="sxs-lookup"><span data-stu-id="1d19d-117">[HTTP with Azure AD](https://docs.microsoft.com/connectors/webcontents/) connector</span></span>
        - <span data-ttu-id="1d19d-118">[OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness) csatlakozó</span><span class="sxs-lookup"><span data-stu-id="1d19d-118">[OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness) connector</span></span>

- <span data-ttu-id="1d19d-119">**[DMF-csomag REST API](../dev-itpro/data-entities/data-management-api.md)** – az exportálás elindításához és a folyamat nyomon követéséhez használt technológia.</span><span class="sxs-lookup"><span data-stu-id="1d19d-119">**[DMF package REST API](../dev-itpro/data-entities/data-management-api.md)** – The technology that is used to trigger the export and monitor its progress.</span></span>
- <span data-ttu-id="1d19d-120">**[OneDrive for Business](https://onedrive.live.com/about/business/)** – az exportált dolgozók célhelye.</span><span class="sxs-lookup"><span data-stu-id="1d19d-120">**[OneDrive for Business](https://onedrive.live.com/about/business/)** – The destination for the exported workers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1d19d-121">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="1d19d-121">Prerequisites</span></span>

<span data-ttu-id="1d19d-122">Mielőtt elkezdené a feladatot ebben az oktatóanyagban, a következő elemekkel kell rendelkeznie:</span><span class="sxs-lookup"><span data-stu-id="1d19d-122">Before you begin the exercise in this tutorial, you must have the following items:</span></span>

- <span data-ttu-id="1d19d-123">Olyan Human Resources-környezet, amely rendszergazdai engedélyekkel rendelkezik a környezetben</span><span class="sxs-lookup"><span data-stu-id="1d19d-123">A Human Resources environment that has admin-level permissions in the environment</span></span>
- <span data-ttu-id="1d19d-124">Egy [Azure-előfizetés](https://azure.microsoft.com/free/) a logikai alkalmazás tárolásához</span><span class="sxs-lookup"><span data-stu-id="1d19d-124">An [Azure subscription](https://azure.microsoft.com/free/) to host the logic app</span></span>

## <a name="the-exercise"></a><span data-ttu-id="1d19d-125">A feladat</span><span class="sxs-lookup"><span data-stu-id="1d19d-125">The exercise</span></span>

<span data-ttu-id="1d19d-126">A feladat végén talál egy logikai alkalmazást, amely kapcsolódik a Human Resources-környezetéhez és a OneDrive for Business fiókjához.</span><span class="sxs-lookup"><span data-stu-id="1d19d-126">At the end of this exercise, you will have a logic app that is connected to your Human Resources environment and your OneDrive for Business account.</span></span> <span data-ttu-id="1d19d-127">A logikai alkalmazás egy adatcsomagot exportál a Human Resources-alkalmazásból, várja meg, hogy befejeződjön az exportálás, töltse le az exportált adatcsomagot, majd mentse az adatcsomagot a megadott OneDrive for Business mappába.</span><span class="sxs-lookup"><span data-stu-id="1d19d-127">The logic app will export a data package from Human Resources, wait for the export to be completed, download the exported data package, and save the data package in the OneDrive for Business folder that you specified.</span></span>

<span data-ttu-id="1d19d-128">A befejeződött logikai alkalmazás a következő ábrához fog hasonlítani.</span><span class="sxs-lookup"><span data-stu-id="1d19d-128">The completed logic app will resemble the following illustration.</span></span>

![Logikai alkalmazás áttekintése](media/integration-logic-app-overview.png)

### <a name="step-1-create-a-data-export-project-in-human-resources"></a><span data-ttu-id="1d19d-130">1. lépés: adatexportálási projekt létrehozása a Human Resources alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="1d19d-130">Step 1: Create a data export project in Human Resources</span></span>

<span data-ttu-id="1d19d-131">Olyan adatexportálási projekt létrehozása a Human Resources alkalmazásban, amely exportálja a dolgozókat.</span><span class="sxs-lookup"><span data-stu-id="1d19d-131">In Human Resources, create a data export project that exports workers.</span></span> <span data-ttu-id="1d19d-132">Nevezze el a projektet a következőre: **Dolgozók exportálása**, és győződjön meg arról, hogy az **Adatcsomag létrehozása** beállítás **Igen** értéken legyen.</span><span class="sxs-lookup"><span data-stu-id="1d19d-132">Name the project **Export Workers**, and make sure that the **Generate data package** option is set to **Yes**.</span></span> <span data-ttu-id="1d19d-133">Adjon hozzá a projekthez egyetlen entitást (**Dolgozó**), majd válassza ki azt a formátumot, amelyben exportálni szeretne.</span><span class="sxs-lookup"><span data-stu-id="1d19d-133">Add a single entity (**Worker**) to the project, and select the format to export in.</span></span> <span data-ttu-id="1d19d-134">(Az oktatóanyag Microsoft Excel-formátumot használ.)</span><span class="sxs-lookup"><span data-stu-id="1d19d-134">(Microsoft Excel format is used in this tutorial.)</span></span>

![Dolgozói adatok projekt exportálása](media/integration-logic-app-export-workers-project.png)

> [!IMPORTANT]
> <span data-ttu-id="1d19d-136">Jegyezze meg az adatexportálási projekt nevét.</span><span class="sxs-lookup"><span data-stu-id="1d19d-136">Remember the name of the data export project.</span></span> <span data-ttu-id="1d19d-137">Erre akkor lesz szükség, amikor a következő lépésben létrehozza a logikai alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="1d19d-137">You will need it when you create the logic app in the next step.</span></span>

### <a name="step-2-create-the-logic-app"></a><span data-ttu-id="1d19d-138">2. lépés: a logikai alkalmazás létrehozása</span><span class="sxs-lookup"><span data-stu-id="1d19d-138">Step 2: Create the logic app</span></span>

<span data-ttu-id="1d19d-139">A feladat nagy része a logikai alkalmazás létrehozása lesz.</span><span class="sxs-lookup"><span data-stu-id="1d19d-139">The bulk of the exercise involves creating the logic app.</span></span>

1. <span data-ttu-id="1d19d-140">Hozzon létre egy logikai alkalmazást az Azure-portálon.</span><span class="sxs-lookup"><span data-stu-id="1d19d-140">In the Azure portal, create a logic app.</span></span>

    ![Logikai alkalmazás létrehozása lap](media/integration-logic-app-creation-1.png)

2. <span data-ttu-id="1d19d-142">A Logic Apps Designer programban kezdje a munkát egy üres logikai alkalmazással.</span><span class="sxs-lookup"><span data-stu-id="1d19d-142">In the Logic Apps Designer, start with a blank logic app.</span></span>
3. <span data-ttu-id="1d19d-143">Adjon hozzá egy [Ismétlődésütemezési indítót](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) a logikai alkalmazás 24 óránként történő futtatásához (vagy az Ön által kiválasztott ütemezéshez).</span><span class="sxs-lookup"><span data-stu-id="1d19d-143">Add a [Recurrence Schedule trigger](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) to run the logic app every 24 hours (or according to a schedule of your choice).</span></span>

    ![Ismétlődés párbeszédpanel](media/integration-logic-app-recurrence-step.png)

4. <span data-ttu-id="1d19d-145">Hívja az [ExportToPackage](../dev-itpro/data-entities/data-management-api.md#exporttopackage) DMF REST API-t az adatcsomag exportálásának ütemezése érdekében.</span><span class="sxs-lookup"><span data-stu-id="1d19d-145">Call the [ExportToPackage](../dev-itpro/data-entities/data-management-api.md#exporttopackage) DMF REST API to schedule the export of your data package.</span></span>

    1. <span data-ttu-id="1d19d-146">A HTTP-ből válassza a **HTTP-kérelem hívása** műveletet az Azure AD-csatlakozó használatával.</span><span class="sxs-lookup"><span data-stu-id="1d19d-146">Use the **Invoke an HTTP request** action from the HTTP with Azure AD connector.</span></span>

        - <span data-ttu-id="1d19d-147">**Alaperőforrás URL**: a Human Resources környezetének URL-címe (Ne tartalmazza az elérési útra/névtérre vonatkozó adatokat.)</span><span class="sxs-lookup"><span data-stu-id="1d19d-147">**Base Resource URL:** The URL of your Human Resources environment (Don't include path/namespace information.)</span></span>
        - <span data-ttu-id="1d19d-148">**Azure AD Erőforrás URI-je:** `http://hr.talent.dynamics.com`</span><span class="sxs-lookup"><span data-stu-id="1d19d-148">**Azure AD Resource URI:** `http://hr.talent.dynamics.com`</span></span>

        > [!NOTE]
        > <span data-ttu-id="1d19d-149">A Human Resources-szolgáltatás még nem rendelkezik olyan csatlakozóval, amely megjeleníti a DMF-csomag REST összes API-ját (például **ExportToPackage**) alkotó API-kat.</span><span class="sxs-lookup"><span data-stu-id="1d19d-149">The Human Resources service doesn't yet provide a connector that exposes all the APIs that make up the DMF package REST API, such as **ExportToPackage**.</span></span> <span data-ttu-id="1d19d-150">Ehelyett az API-kat a nyers HTTPS-kérésekkel kell hívnia a HTTP-n keresztül és az Azure AD-csatlakozó segítségével.</span><span class="sxs-lookup"><span data-stu-id="1d19d-150">Instead, you must call the APIs by using raw HTTPS requests through the HTTP with Azure AD connector.</span></span> <span data-ttu-id="1d19d-151">Ez a csatlakozó az Azure Active Directory-t (Azure AD) használja a hitelesítésre és a Human Resources alkalmazáshoz való engedélyezéshez.</span><span class="sxs-lookup"><span data-stu-id="1d19d-151">This connector uses Azure Active Directory (Azure AD) for authentication and authorization to Human Resources.</span></span>

        ![HTTP Azure AD-csatlakozóval](media/integration-logic-app-http-aad-connector-step.png)

    2. <span data-ttu-id="1d19d-153">Jelentkezzen be a Human Resources környezetébe a HTTP-n keresztül az Azure AD-csatlakozó segítségével.</span><span class="sxs-lookup"><span data-stu-id="1d19d-153">Sign in to your Human Resources environment through the HTTP with Azure AD connector.</span></span>
    3. <span data-ttu-id="1d19d-154">Állítson be egy HTTP **POST**-kérelmet az **ExportToPackage** DMF REST API hívásához.</span><span class="sxs-lookup"><span data-stu-id="1d19d-154">Set up an HTTP **POST** request to call the **ExportToPackage** DMF REST API.</span></span>

        - <span data-ttu-id="1d19d-155">**Metódus**: POST</span><span class="sxs-lookup"><span data-stu-id="1d19d-155">**Method:** POST</span></span>
        - <span data-ttu-id="1d19d-156">**A kérelem URL-címe:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage</span><span class="sxs-lookup"><span data-stu-id="1d19d-156">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage</span></span>
        - <span data-ttu-id="1d19d-157">**A kérelem törzse:**</span><span class="sxs-lookup"><span data-stu-id="1d19d-157">**Body of the request:**</span></span>

            ```JSON
            {
                "definitionGroupId":"Export Workers",
                "packageName":"talent_package.zip",
                "executionId":"",
                "reExecute":false,
                "legalEntityId":"USMF"
            }
            ```

        ![HTTP-kérelem műveletének meghívása](media/integration-logic-app-export-to-package-step.png)

    > [!TIP]
    > <span data-ttu-id="1d19d-159">Előfordulhat, hogy az egyes lépéseket úgy szeretné átnevezni, hogy az az alapértelmezett nevénél érthetőbb legyen, **HTTP-kérelem meghívása**.</span><span class="sxs-lookup"><span data-stu-id="1d19d-159">You might want to rename each step so that it's more meaningful than the default name, **Invoke an HTTP request**.</span></span> <span data-ttu-id="1d19d-160">Ezt a lépést például átnevezheti a következőre: **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="1d19d-160">For example, you can rename this step **ExportToPackage**.</span></span>

5. <span data-ttu-id="1d19d-161">[Változó inicializálása](https://docs.microsoft.com/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable) az **ExportToPackage** kérelem végrehajtási állapotának tárolásához.</span><span class="sxs-lookup"><span data-stu-id="1d19d-161">[Initialize a variable](https://docs.microsoft.com/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable) to store the execution status of the **ExportToPackage** request.</span></span>

    ![Változó művelet inicializálása](media/integration-logic-app-initialize-variable-step.png)

6. <span data-ttu-id="1d19d-163">Várjon, amíg az adatexport végrehajtási állapota **Sikeres** nem lesz.</span><span class="sxs-lookup"><span data-stu-id="1d19d-163">Wait until the execution status of the data export is **Succeeded**.</span></span>

    1. <span data-ttu-id="1d19d-164">Adjon hozzá egy [Érvényesség vége-ciklus](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop) műveletet, amely addig ismétlődik, amíg az **ExecutionStatus**-változó értéke **Sikeres** nem lesz.</span><span class="sxs-lookup"><span data-stu-id="1d19d-164">Add an [Until loop](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop) that repeats until the value of the **ExecutionStatus** variable is **Succeeded**.</span></span>
    2. <span data-ttu-id="1d19d-165">Adjon hozzá egy **Késleltetési** műveletet, amely az exportálás aktuális végrehajtási állapotához kapcsolódó lekérdezések előtt öt másodpercig várakozik.</span><span class="sxs-lookup"><span data-stu-id="1d19d-165">Add a **Delay** action that waits five seconds before it polls for the current execution status of the export.</span></span>

        ![Érvényesség vége-ciklus tárolója](media/integration-logic-app-until-loop-step.png)

        > [!NOTE]
        > <span data-ttu-id="1d19d-167">Állítsa be limitszámot **15** -ös értékre, és az exportálás befejezéséhez várjon legfeljebb 75 másodpercig (15 ismétlés x 5 másodperc).</span><span class="sxs-lookup"><span data-stu-id="1d19d-167">Set the limit count to **15** to wait a maximum of 75 seconds (15 iterations × 5 seconds) for the export to be completed.</span></span> <span data-ttu-id="1d19d-168">Ha az exportálás több időt vesz igénybe, szükség szerint módosítsa a limiteket.</span><span class="sxs-lookup"><span data-stu-id="1d19d-168">If your export takes more time, adjust the limit count as appropriate.</span></span>        

    3. <span data-ttu-id="1d19d-169">Adjon hozzá egy **HTTP-kérelem meghívása** műveletet a [GetExecutionSummaryStatus](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) DMF REST API hívásához, majd állítsa át az **ExecutionStatus**-változót a **GetExecutionSummaryStatus** válaszának eredményére.</span><span class="sxs-lookup"><span data-stu-id="1d19d-169">Add an **Invoke HTTP request** action to call the [GetExecutionSummaryStatus](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) DMF REST API, and set the **ExecutionStatus** variable to the result of the **GetExecutionSummaryStatus** response.</span></span>

        > <span data-ttu-id="1d19d-170">Ez a minta nem végez hibaellenőrzést.</span><span class="sxs-lookup"><span data-stu-id="1d19d-170">This sample doesn't do error checking.</span></span> <span data-ttu-id="1d19d-171">A **GetExecutionSummaryStatus** API visszaküldheti a sikertelen terminálállapotokat (azaz a **Sikeres** állapoton kívüli más állapotokat).</span><span class="sxs-lookup"><span data-stu-id="1d19d-171">The **GetExecutionSummaryStatus** API can return non-successful terminal states (that is, states other than **Succeeded**).</span></span> <span data-ttu-id="1d19d-172">További részletek az [API-val kapcsolatos dokumentáció](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) részben találhatók.</span><span class="sxs-lookup"><span data-stu-id="1d19d-172">For more information, see the [API documentation](../dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus).</span></span>

        - <span data-ttu-id="1d19d-173">**Metódus**: POST</span><span class="sxs-lookup"><span data-stu-id="1d19d-173">**Method:** POST</span></span>
        - <span data-ttu-id="1d19d-174">**A kérelem URL-címe:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus</span><span class="sxs-lookup"><span data-stu-id="1d19d-174">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus</span></span>
        - <span data-ttu-id="1d19d-175">**A kérelem törzse:** body('Invoke\_\_HTTP\_request')?[value']</span><span class="sxs-lookup"><span data-stu-id="1d19d-175">**Body of the request:** body('Invoke\_an\_HTTP\_request')?['value']</span></span>

            > [!NOTE]
            > <span data-ttu-id="1d19d-176">Előfordulhat, hogy meg kell adnia **A kérelem törzse** értékét kódnézetben vagy a tervező funkciószerkesztőjében.</span><span class="sxs-lookup"><span data-stu-id="1d19d-176">You might have to enter the **Body of the request** value either in code view or in the function editor in the designer.</span></span>

        ![Egy HTTP-kérelem meghívása 2 művelet](media/integration-logic-app-get-execution-status-step.png)

        ![Változó művelet beállítása](media/integration-logic-app-set-variable-step.png)

        > [!IMPORTANT]
        > <span data-ttu-id="1d19d-179">A **Változó beállítása** művelet értéke (**body('Invoke\_an\_HTTP\_request\_2')?['value']**) nem fog megegyezni a **HTTP-kérelem 2 meghívása** törzsértékkel, habár a tervező ugyanolyan módon fogja mutatni az értékeket.</span><span class="sxs-lookup"><span data-stu-id="1d19d-179">The value for the **Set variable** action (**body('Invoke\_an\_HTTP\_request\_2')?['value']**) will differ from the value for the **Invoke an HTTP request 2** body value, even though the designer will show the values in the same way.</span></span>

7. <span data-ttu-id="1d19d-180">Az exportált csomag letöltési URL-jének beolvasása.</span><span class="sxs-lookup"><span data-stu-id="1d19d-180">Get the download URL of the exported package.</span></span>

    - <span data-ttu-id="1d19d-181">**HTTP-kérelem meghívása** művelet hozzáadása a [GetExportedPackageUrl](../dev-itpro/data-entities/data-management-api.md#getexportedpackageurl) DMF REST API hívásához.</span><span class="sxs-lookup"><span data-stu-id="1d19d-181">Add an **Invoke HTTP request** action to call the [GetExportedPackageUrl](../dev-itpro/data-entities/data-management-api.md#getexportedpackageurl) DMF REST API.</span></span>

        - <span data-ttu-id="1d19d-182">**Metódus**: POST</span><span class="sxs-lookup"><span data-stu-id="1d19d-182">**Method:** POST</span></span>
        - <span data-ttu-id="1d19d-183">**A kérelem URL-címe:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl</span><span class="sxs-lookup"><span data-stu-id="1d19d-183">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl</span></span>
        - <span data-ttu-id="1d19d-184">**A kérelem törzse:** {"executionId": Body ("GetExportedPackageURL")?["value"]}</span><span class="sxs-lookup"><span data-stu-id="1d19d-184">**Body of the request:** {"executionId": body('GetExportedPackageURL')?['value']}</span></span>

        ![GetExportedPackageURL-művelet](media/integration-logic-app-get-exported-package-step.png)

8. <span data-ttu-id="1d19d-186">Az exportált csomag letöltése.</span><span class="sxs-lookup"><span data-stu-id="1d19d-186">Download the exported package.</span></span>

    - <span data-ttu-id="1d19d-187">Adjon hozzá egy HTTP **GET**-kérelmet ( beépített [HTTP-csatlakozó művelet](https://docs.microsoft.com/azure/connectors/connectors-native-http)) az előző lépésben visszaküldött URL-címen szereplő csomag letöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="1d19d-187">Add an HTTP **GET** request (a built-in [HTTP connector action](https://docs.microsoft.com/azure/connectors/connectors-native-http)) to download the package from the URL that was returned in the previous step.</span></span>

        - <span data-ttu-id="1d19d-188">**Metódus**: GET</span><span class="sxs-lookup"><span data-stu-id="1d19d-188">**Method:** GET</span></span>
        - <span data-ttu-id="1d19d-189">**URI:** body('Invoke\_an\_HTTP\_request\_3').value</span><span class="sxs-lookup"><span data-stu-id="1d19d-189">**URI:** body('Invoke\_an\_HTTP\_request\_3').value</span></span>

            > [!NOTE]
            > <span data-ttu-id="1d19d-190">Előfordulhat, hogy meg kell adnia az **URI** értékét kódnézetben vagy a tervező funkciószerkesztőjében.</span><span class="sxs-lookup"><span data-stu-id="1d19d-190">You might have to enter the **URI** value either in code view or in the function editor in the designer.</span></span>

        ![HTTP GET-művelet](media/integration-logic-app-download-file-step.png)

        > [!NOTE]
        > <span data-ttu-id="1d19d-192">A kérelemhez nem szükséges további hitelesítés, mert a **GetExportedPackageUrl** API-t visszaküldő URL-cím tartalmaz egy megosztott hozzáférési aláírási tokent, amely hozzáférést biztosít a fájl letöltéséhez.</span><span class="sxs-lookup"><span data-stu-id="1d19d-192">This request doesn't require any additional authentication, because the URL that the **GetExportedPackageUrl** API returns includes a shared access signatures token that grants access to download the file.</span></span>

9. <span data-ttu-id="1d19d-193">Mentse a letöltött csomagot a [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness) csatlakozó segítségével.</span><span class="sxs-lookup"><span data-stu-id="1d19d-193">Save the downloaded package by using the [OneDrive for Business](https://docs.microsoft.com/azure/connectors/connectors-create-api-onedriveforbusiness) connector.</span></span>

    - <span data-ttu-id="1d19d-194">Adjon hozzá egy OneDrive for Business [Fájl létrehozása](https://docs.microsoft.com/connectors/onedriveforbusinessconnector/#create-file) műveletet.</span><span class="sxs-lookup"><span data-stu-id="1d19d-194">Add a OneDrive for Business [Create File](https://docs.microsoft.com/connectors/onedriveforbusinessconnector/#create-file) action.</span></span>
    - <span data-ttu-id="1d19d-195">Szükség szerint kapcsolódjon a OneDrive for Business fiókhoz.</span><span class="sxs-lookup"><span data-stu-id="1d19d-195">Connect to your OneDrive for Business account, as required.</span></span>

        - <span data-ttu-id="1d19d-196">**Mappa elérési útja:** egy Ön által kiválasztott mappa</span><span class="sxs-lookup"><span data-stu-id="1d19d-196">**Folder Path:** A folder of your choice</span></span>
        - <span data-ttu-id="1d19d-197">**Fájlnév:** dolgozó\_csomag.zip</span><span class="sxs-lookup"><span data-stu-id="1d19d-197">**File Name:** worker\_package.zip</span></span>
        - <span data-ttu-id="1d19d-198">**Fájl tartalma:** az előző lépés törzse (dinamikus tartalom)</span><span class="sxs-lookup"><span data-stu-id="1d19d-198">**File Content:** The body from the previous step (dynamic content)</span></span>

        ![Fájlművelet létrehozása](media/integration-logic-app-create-file-step.png)

### <a name="step-3-test-the-logic-app"></a><span data-ttu-id="1d19d-200">3. lépés: a logikai alkalmazás tesztelése</span><span class="sxs-lookup"><span data-stu-id="1d19d-200">Step 3: Test the logic app</span></span>

<span data-ttu-id="1d19d-201">A logikai alkalmazás teszteléséhez válassza a **Futtatás** gombot a tervezőben.</span><span class="sxs-lookup"><span data-stu-id="1d19d-201">To test your logic app, select the **Run** button in the designer.</span></span> <span data-ttu-id="1d19d-202">Látni fogja, hogy a logikai alkalmazás futtatásának lépései megkezdődnek.</span><span class="sxs-lookup"><span data-stu-id="1d19d-202">You will see that the steps of the logic app start to run.</span></span> <span data-ttu-id="1d19d-203">30-40 másodperccel később a logikai alkalmazásnak be kell fejeznie a futtatást, és a OneDrive for Business mappának tartalmaznia kell egy új, az exportált dolgozókat tartalmazó csomagot.</span><span class="sxs-lookup"><span data-stu-id="1d19d-203">After 30 to 40 seconds, the logic app should finish running, and your OneDrive for Business folder should include a new package file that contains the exported workers.</span></span>

<span data-ttu-id="1d19d-204">Ha bármilyen lépésnél hibát jelez, jelölje ki a sikertelen lépést a tervezőben, és vizsgálja meg a **Bemenetek** és **Kimenetek** mezőket.</span><span class="sxs-lookup"><span data-stu-id="1d19d-204">If a failure is reported for any step, select the failed step in the designer, and examine the **Inputs** and **Outputs** fields for it.</span></span> <span data-ttu-id="1d19d-205">Hibakereséshez és a hibák javítása érdekében módosítsa a lépést.</span><span class="sxs-lookup"><span data-stu-id="1d19d-205">Debug and adjust the step as required to correct the errors.</span></span>

<span data-ttu-id="1d19d-206">A következő ábra bemutatja, hogy néz ki a Logic Apps Designer, amikor a logikai alkalmazás minden lépését sikeresen futtatták.</span><span class="sxs-lookup"><span data-stu-id="1d19d-206">The following illustration shows what the Logic Apps Designer looks like when all the steps of the logic app run successfully.</span></span>

![Sikeres futtatott logikai alkalmazás](media/integration-logic-app-successful-run.png)

## <a name="summary"></a><span data-ttu-id="1d19d-208">Összegzés</span><span class="sxs-lookup"><span data-stu-id="1d19d-208">Summary</span></span>

<span data-ttu-id="1d19d-209">Ebben az oktatóanyagban megtanulta, hogyan kell használni a logikai alkalmazást a Human Resources adatainak exportálására, és hogyan kell menteni az exportált adatokat a OneDrive for Business mappába.</span><span class="sxs-lookup"><span data-stu-id="1d19d-209">In this tutorial, you learned how to use a logic app to export data from Human Resources and save the exported data to a OneDrive for Business folder.</span></span> <span data-ttu-id="1d19d-210">Az oktatóanyag lépései az üzleti igényeknek megfelelően módosíthatók.</span><span class="sxs-lookup"><span data-stu-id="1d19d-210">You can modify the steps of this tutorial as required to suit your business needs.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]