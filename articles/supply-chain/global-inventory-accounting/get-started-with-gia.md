---
title: Első lépések a Global Inventory Accounting szolgáltatással
description: Ez a témakör azt ismerteti, hogyan lehet elkezdeni a Global Inventory Accounting szolgáltatást.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 59f9db309312bbbc88b4fa47c12c4c02f09e7c6d
ms.sourcegitcommit: cbbb35c71ab4ff1ae08fa4f7cc97019b207246be
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301698"
---
# <a name="get-started-with-global-inventory-accounting"></a><span data-ttu-id="8808e-103">Első lépések a Global Inventory Accounting szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="8808e-103">Get started with Global Inventory Accounting</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="8808e-104">A Global Inventory Accounting szolgáltatás segítségével több készlet könyveléseit végezheti el a beállított Global Inventory Accounting főkönyvben.</span><span class="sxs-lookup"><span data-stu-id="8808e-104">Global Inventory Accounting lets you do multiple inventory accountings in the Global Inventory Accounting ledgers that you've set up.</span></span> <span data-ttu-id="8808e-105">Minden Global Inventory Accounting főkönyvhöz egy *szabályt* társít.</span><span class="sxs-lookup"><span data-stu-id="8808e-105">You must associate each Global Inventory Accounting ledger with a *convention*.</span></span> <span data-ttu-id="8808e-106">Egy szabály a következő típusú könyvelési irányelvek gyűjteményét jelenti:</span><span class="sxs-lookup"><span data-stu-id="8808e-106">A convention is a collection of the following types of accounting policies:</span></span>

- <span data-ttu-id="8808e-107">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="8808e-107">Cost object</span></span>
- <span data-ttu-id="8808e-108">Bemeneti mérték alapja</span><span class="sxs-lookup"><span data-stu-id="8808e-108">Input measurement basis</span></span>
- <span data-ttu-id="8808e-109">Költségforgalom-feltételezés</span><span class="sxs-lookup"><span data-stu-id="8808e-109">Cost flow assumption</span></span>
- <span data-ttu-id="8808e-110">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="8808e-110">Cost element</span></span>

> [!NOTE]
> <span data-ttu-id="8808e-111">Még a Global Inventory Accounting bekapcsolása után is elvégezheti szokás szerint a készletkönyvelést a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="8808e-111">Even after you turn on Global Inventory Accounting, you can still do inventory accounting in Microsoft Dynamics 365 Supply Chain Management in the usual way.</span></span>

<span data-ttu-id="8808e-112">A Global Inventory Accounting szolgáltatás egy bővítmény.</span><span class="sxs-lookup"><span data-stu-id="8808e-112">Global Inventory Accounting is an add-in.</span></span> <span data-ttu-id="8808e-113">Ahhoz, hogy hozzáférhetővé váljanak a funkciók, telepítenie kell a Microsoft Dynamics Lifecycle Services (LCS) felületéről.</span><span class="sxs-lookup"><span data-stu-id="8808e-113">To make its features available, you must install it from Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="8808e-114">Kiválaszthatja, hogy a termelési környezetekben való bekapcsolás előtt szeretné-e értékelni tesztkörnyezetben.</span><span class="sxs-lookup"><span data-stu-id="8808e-114">You can choose to evaluate it in a test environment before you turn it on for production environments.</span></span>

<span data-ttu-id="8808e-115">A Global Inventory Accounting jelenleg nem támogatja a Supply Chain Management eszközbe beépített költségkezelési funkciókat.</span><span class="sxs-lookup"><span data-stu-id="8808e-115">Global Inventory Accounting doesn't currently support all the cost management features that are built into Supply Chain Management.</span></span> <span data-ttu-id="8808e-116">Ezért fontos, hogy meggyőződjön, hogy a jelenleg elérhető funkciókészlet kielégíti-e a követelményeket.</span><span class="sxs-lookup"><span data-stu-id="8808e-116">Therefore, it's important that you evaluate whether the set of features that is currently available will meet your requirements.</span></span>

## <a name="how-to-get-the-global-inventory-accounting-public-preview"></a><a name="sign-up"></a><span data-ttu-id="8808e-117">A Global Inventory Accounting nyilvános előzetes verzió beszerzése</span><span class="sxs-lookup"><span data-stu-id="8808e-117">How to get the Global Inventory Accounting public preview</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8808e-118">A Global Inventory Accounting csak akkor használható, ha engedélyezve van az LCS-szolgáltatásban engedélyezett, nagy rendelkezésre állású környezet (nem OneBox környezet).</span><span class="sxs-lookup"><span data-stu-id="8808e-118">To use Global Inventory Accounting, you must have an LCS-enabled high-availability environment (not a OneBox environment).</span></span> <span data-ttu-id="8808e-119">Ezenkívül a Supply Chain Management 10.0.19-es vagy újabb verziójának is futnia kell.</span><span class="sxs-lookup"><span data-stu-id="8808e-119">Additionally, you must be running Supply Chain Management version 10.0.19 or later.</span></span>

<span data-ttu-id="8808e-120">A Global Inventory Accounting nyilvános előnézetére való regisztrációhoz küldje el e-mailben az LCS-környezetazonosítót a [Global Inventory Accounting csoportnak](mailto:GlobalInventoryAccounting@service.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="8808e-120">To sign up for the Global Inventory Accounting public preview, send your LCS environment ID by email to the [Global Inventory Accounting team](mailto:GlobalInventoryAccounting@service.microsoft.com).</span></span> <span data-ttu-id="8808e-121">Ha jóváhagyta a programot, a csoport egy követő e-mailt küld, amely tartalmaz egy Global Inventory Accounting bétakulcsot és a szolgáltatási végpontokat.</span><span class="sxs-lookup"><span data-stu-id="8808e-121">After you're approved for the program, the team will send you a follow-up email that contains a Global Inventory Accounting beta key and your service endpoints.</span></span> <span data-ttu-id="8808e-122">Miután megkapja a béta kulcsot, [telepítheti a bővítményt](#install).</span><span class="sxs-lookup"><span data-stu-id="8808e-122">After you receive the beta key, you can [install the add-in](#install).</span></span>

## <a name="licensing"></a><span data-ttu-id="8808e-123">Licenckezelés</span><span class="sxs-lookup"><span data-stu-id="8808e-123">Licensing</span></span>

<span data-ttu-id="8808e-124">A Global Inventory Accounting szolgáltatás egy licencben szerepel az Supply Chain Management szolgáltatásban elérhető készletkönyvelési standard funkciókkal.</span><span class="sxs-lookup"><span data-stu-id="8808e-124">Global Inventory Accounting is licensed together with the standard features of inventory accounting that are available for Supply Chain Management.</span></span> <span data-ttu-id="8808e-125">Nem kell további licencet vásárolnia a Global Inventory Accounting szolgáltatás használatához.</span><span class="sxs-lookup"><span data-stu-id="8808e-125">You don't have to purchase an additional license to use Global Inventory Accounting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8808e-126">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="8808e-126">Prerequisites</span></span>

### <a name="set-up-microsoft-power-platform-integration"></a><span data-ttu-id="8808e-127">Microsoft Power Platform-integráció beállítása</span><span class="sxs-lookup"><span data-stu-id="8808e-127">Set up Microsoft Power Platform integration</span></span>

<span data-ttu-id="8808e-128">A bővítmények funkcióit a következő lépések segítségével kell Microsoft Power Platform platformmal integrálni.</span><span class="sxs-lookup"><span data-stu-id="8808e-128">Before you can enable add-in functionality, you must integrate with Microsoft Power Platform by following these steps.</span></span>

1. <span data-ttu-id="8808e-129">Nyissa meg azt a LCS-környezetet, amelyhez hozzá szeretné adni a szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="8808e-129">Open the LCS environment where you want to add the service.</span></span>
1. <span data-ttu-id="8808e-130">Lépjen a **Teljes részletek** elemre.</span><span class="sxs-lookup"><span data-stu-id="8808e-130">Go to **Full details**.</span></span>
1. <span data-ttu-id="8808e-131">Válassza a **Beállítás**  lehetőséget a **Power Platform-integráció** szakaszban.</span><span class="sxs-lookup"><span data-stu-id="8808e-131">In the **Power Platform Integration** section, select **Setup**.</span></span>
1. <span data-ttu-id="8808e-132">A **Power Platform környezetének** beállítása párbeszédpanelen jelölje be a jelölőnégyzetet, majd válassza a **Beállítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8808e-132">In the **Power platform environment setup** dialog box, select the checkbox, and then select **Setup**.</span></span> <span data-ttu-id="8808e-133">A beállítás általában 60 és 90 perc közötti időt vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="8808e-133">Typically, setup takes between 60 and 90 minutes.</span></span>
1. <span data-ttu-id="8808e-134">A Microsoft Power Platform környezet beállítása után az oldal megjeleníti a környezet nevét.</span><span class="sxs-lookup"><span data-stu-id="8808e-134">After setup of the Microsoft Power Platform environment is completed, the page shows the name of your environment.</span></span> <span data-ttu-id="8808e-135">Ezenkívül az **Power Platform Integráció** szakasz a "Power Platform környezet beállítása kész" utasítást is megjeleníti.</span><span class="sxs-lookup"><span data-stu-id="8808e-135">Additionally, the **Power Platform Integration** section shows the statement, "Power Platform environment setup is complete."</span></span> <span data-ttu-id="8808e-136">A Global Inventory Accountinghoz nem szükséges kétírásos alkalmazás.</span><span class="sxs-lookup"><span data-stu-id="8808e-136">Global Inventory Accounting doesn't require a dual-write application.</span></span>

<span data-ttu-id="8808e-137">További információkért lásd: [Beállítás a környezet üzemelő példánya után](../../fin-ops-core/dev-itpro/power-platform/overview.md#set-up-after-environment-deployment).</span><span class="sxs-lookup"><span data-stu-id="8808e-137">For more information, see [Set up after environment deployment](../../fin-ops-core/dev-itpro/power-platform/overview.md#set-up-after-environment-deployment).</span></span>

### <a name="set-up-dataverse"></a><span data-ttu-id="8808e-138">Dataverse Beállítása</span><span class="sxs-lookup"><span data-stu-id="8808e-138">Set up Dataverse</span></span>

<span data-ttu-id="8808e-139">A következő lépések szerint adja hozzá a Global Inventory Accounting szolgáltatási elveket a Dataverse beállítása előtt.</span><span class="sxs-lookup"><span data-stu-id="8808e-139">Before you set up Dataverse, add the Global Inventory Accounting service principles to your tenant by following these steps.</span></span>

1. <span data-ttu-id="8808e-140">Telepítse az Azure AD Windows PowerShell modul v2 verzióját az [Azure Active Directory PowerShell for Graph telepítése](/powershell/azure/active-directory/install-adv2) részben leírtak szerint.</span><span class="sxs-lookup"><span data-stu-id="8808e-140">Install Azure AD Module for Windows PowerShell v2 as described in [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
1. <span data-ttu-id="8808e-141">Futtassa a következő PowerShell-parancsot.</span><span class="sxs-lookup"><span data-stu-id="8808e-141">Run the following PowerShell command.</span></span>

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)

    New-AzureADServicePrincipal -AppId "7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9" -DisplayName "d365-scm-costaccountingservice"

    New-AzureADServicePrincipal -AppId "5f58fc56-0202-49a8-ac9e-0946b049718b" -DisplayName "d365-scm-operationdataservice"
    ```

<span data-ttu-id="8808e-142">Ezután hozza létre az alkalmazásfelhasználókat a Global Inventory Accounting szoláltatáshoz a Dataverse szolgáltatásban a következő lépések segítségével.</span><span class="sxs-lookup"><span data-stu-id="8808e-142">Next, create application users for Global Inventory Accounting in Dataverse by following these steps.</span></span>

1. <span data-ttu-id="8808e-143">Nyissa meg a Dataverse környezete URL-címét.</span><span class="sxs-lookup"><span data-stu-id="8808e-143">Open the URL of your Dataverse environment.</span></span>
1. <span data-ttu-id="8808e-144">Lépjen a **Speciális beállítások \> Rendszer \> Biztonság \> Felhasználók** lehetőségre, és hozzon létre egy alkalmazásfelhasználót.</span><span class="sxs-lookup"><span data-stu-id="8808e-144">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="8808e-145">A **Nézet** mező használatával módosítsa az oldal nézetét az *Alkalmazásfelhasználók* lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8808e-145">Use the **View** field to change the page view to *Application users*.</span></span>
1. <span data-ttu-id="8808e-146">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8808e-146">Select **New**.</span></span>
1. <span data-ttu-id="8808e-147">Állítsa az **Alkalmazásazonosító** mező értékét erre: *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.</span><span class="sxs-lookup"><span data-stu-id="8808e-147">Set the **Application ID** field to *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.</span></span>
1. <span data-ttu-id="8808e-148">Válassza a **Szerepkör hozzárendelése**, majd a *Rendszergazda* lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8808e-148">Select **Assign Role**, and then select *System Administrator*.</span></span> <span data-ttu-id="8808e-149">Ha van *Common Data Service-felhasználó* nevű szerepkör, válassza ki azt is.</span><span class="sxs-lookup"><span data-stu-id="8808e-149">If there is a role that is named *Common Data Service User*, select it too.</span></span>
1. <span data-ttu-id="8808e-150">Ismételje meg az előző lépéseket, de állítsa az **Alkalmazásazonosító** mezőt a következőre: *5f58fc56-0202-49a8-ac9e-0946b049718b*.</span><span class="sxs-lookup"><span data-stu-id="8808e-150">Repeat the preceding steps, but set the **Application ID** field to *5f58fc56-0202-49a8-ac9e-0946b049718b*.</span></span>

<span data-ttu-id="8808e-151">További tudnivalókért lásd: [Alkalmazásfelhasználó létrehozása](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="8808e-151">For more information, see [Create an application user](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

<span data-ttu-id="8808e-152">Ha a Dataverse telepítés alapértelmezett nyelve nem angol, kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="8808e-152">If the default language of your Dataverse installation isn't English, follow these steps.</span></span>

1. <span data-ttu-id="8808e-153">Ugrás ide: **Speciális beállítások \> Adminisztráció \> Nyelvek**.</span><span class="sxs-lookup"><span data-stu-id="8808e-153">Go to **Advanced Setting \> Administration \> Languages**.</span></span>
1. <span data-ttu-id="8808e-154">Válassza az *Angol* (*LanguageCode=1033*), és majd az **Alkalmaz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8808e-154">Select *English* (*LanguageCode=1033*), and then select **Apply**.</span></span>

## <a name="install-the-add-in"></a><a name="install"></a><span data-ttu-id="8808e-155">Telepítse a bővítményt</span><span class="sxs-lookup"><span data-stu-id="8808e-155">Install the add-in</span></span>

<span data-ttu-id="8808e-156">A következő lépések szerint telepítheti a bővítményt a Global Inventory Accounting használata érdekében.</span><span class="sxs-lookup"><span data-stu-id="8808e-156">Follow these steps to install the add-in so that you can use Global Inventory Accounting.</span></span>

1. <span data-ttu-id="8808e-157">[Regisztrálás](#sign-up) a Global Inventory Accounting nyilvános előzetes verziójára.</span><span class="sxs-lookup"><span data-stu-id="8808e-157">[Sign up](#sign-up) for the Global Inventory Accounting public preview.</span></span>
1. <span data-ttu-id="8808e-158">Bejelentkezés az [LCS](https://lcs.dynamics.com/Logon/Index) alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="8808e-158">Sign in to [LCS](https://lcs.dynamics.com/Logon/Index).</span></span>
1. <span data-ttu-id="8808e-159">Lépjen a **Előzetes funkció kezelése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8808e-159">Go to **Preview feature management**.</span></span>
1. <span data-ttu-id="8808e-160">Válassza ki a plusz jelet (**+**).</span><span class="sxs-lookup"><span data-stu-id="8808e-160">Select the plus sign (**+**).</span></span>
1. <span data-ttu-id="8808e-161">A **Kód** mezőbe írja be a Global Inventory Accounting szolgáltatáshoz tartozó bővítmény bétakulcsát.</span><span class="sxs-lookup"><span data-stu-id="8808e-161">In the **Code** field, enter your add-in beta key for Global Inventory Accounting.</span></span> <span data-ttu-id="8808e-162">(A bétakulcsot e-mailben kellett volna megkapni a kijelentkezett verzióban.)</span><span class="sxs-lookup"><span data-stu-id="8808e-162">(You should have received your beta key by email when you signed up.)</span></span>
1. <span data-ttu-id="8808e-163">Válassza a **Blokkolás feloldása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8808e-163">Select **Unblock**.</span></span>
1. <span data-ttu-id="8808e-164">Nyissa meg azt a LCS-környezetet, amelyhez hozzá szeretné adni a szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="8808e-164">Open the LCS environment where you want to add the service.</span></span>
1. <span data-ttu-id="8808e-165">Lépjen a **Teljes részletek** elemre.</span><span class="sxs-lookup"><span data-stu-id="8808e-165">Go to **Full details**.</span></span>
1. <span data-ttu-id="8808e-166">Menjen a **Power Platform Integráció** gombra, és válassza a **Telepítőt**.</span><span class="sxs-lookup"><span data-stu-id="8808e-166">Go to **Power Platform Integration**, and select **Setup**.</span></span>
1. <span data-ttu-id="8808e-167">A **Power Platform környezetének** beállítása párbeszédpanelen jelölje be a jelölőnégyzetet, majd válassza a **Beállítás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8808e-167">In the **Power platform environment setup** dialog box, select the checkbox, and then select **Setup**.</span></span> <span data-ttu-id="8808e-168">A beállítás általában 60 és 90 perc közötti időt vesz igénybe.</span><span class="sxs-lookup"><span data-stu-id="8808e-168">Typically, setup takes between 60 and 90 minutes.</span></span>
1. <span data-ttu-id="8808e-169">A Microsoft Power Platform környezet beállítása után a **Környezet bővítmény** gyorslapját választva válassza az **Új bővítmény telepítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8808e-169">After setup of the Microsoft Power Platform environment is completed, on the **Environment add-ins** FastTab, select **Install a new add-in**.</span></span>
1. <span data-ttu-id="8808e-170">Válassza a **Globális Inventory Accounting** eseményt.</span><span class="sxs-lookup"><span data-stu-id="8808e-170">Select **Global inventory accounting**.</span></span>
1. <span data-ttu-id="8808e-171">Kövesse a telepítési útmutatót, és fogadja el a feltételeit és kikötéseit.</span><span class="sxs-lookup"><span data-stu-id="8808e-171">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="8808e-172">Válassza a **Telepítés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="8808e-172">Select **Install**.</span></span>
1. <span data-ttu-id="8808e-173">A **Környezeti bővítmények** gyorslapon látható, hogy a Global Inventory Accounting szolgáltatás telepítése folyamatban van.</span><span class="sxs-lookup"><span data-stu-id="8808e-173">On the **Environment add-ins** FastTab, you should see that Global Inventory Accounting is being installed.</span></span> <span data-ttu-id="8808e-174">Néhány perc múlva az állapotot változik *Telepítés folyamatban* állapotról *Telepítve* értékre.</span><span class="sxs-lookup"><span data-stu-id="8808e-174">After a few minutes, the status should change from *Installing* to *Installed*.</span></span> <span data-ttu-id="8808e-175">(Elképzelhető, hogy frissíteni kell a lapot a változás megtekintéséhez.) Ezen a ponton a Global Inventory Accounting szolgáltatás készen áll a használatra.</span><span class="sxs-lookup"><span data-stu-id="8808e-175">(You might have to refresh the page to see this change.) At that point, Global Inventory Accounting is ready to use.</span></span>

## <a name="set-up-the-integration"></a><span data-ttu-id="8808e-176">Integráció beállítása</span><span class="sxs-lookup"><span data-stu-id="8808e-176">Set up the integration</span></span>

<span data-ttu-id="8808e-177">A következő lépések szerint állíthatja be a Global Inventory Accounting és a Supply Chain Management közötti integrációt.</span><span class="sxs-lookup"><span data-stu-id="8808e-177">Follow these steps to set up the integration between Global Inventory Accounting and Supply Chain Management.</span></span>

1. <span data-ttu-id="8808e-178">Jelentkezzen be a Supply Chain Management alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="8808e-178">Sign in to Supply Chain Management.</span></span>
1. <span data-ttu-id="8808e-179">Lépjen a **Rendszerfelügyelet \> Funkciókezelés** elemre.</span><span class="sxs-lookup"><span data-stu-id="8808e-179">Go to **System administration \> Feature Management**.</span></span>
1. <span data-ttu-id="8808e-180">Válassza a **Frissítések keresése** elemet.</span><span class="sxs-lookup"><span data-stu-id="8808e-180">Select **Check for updates**.</span></span>
1. <span data-ttu-id="8808e-181">A **Mind** lapon keresse meg a *Global Inventory Accounting* nevű szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="8808e-181">On the **All** tab, search for the feature that is named *Global inventory accounting*.</span></span>
1. <span data-ttu-id="8808e-182">Válassza az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8808e-182">Select **Enable now**.</span></span>
1. <span data-ttu-id="8808e-183">Ugrás a **Globális készletkönyvelés \> Beállítása \> Global Inventory Accounting paraméterei \> Integrációs paraméterek**.</span><span class="sxs-lookup"><span data-stu-id="8808e-183">Go to **Global inventory accounting \> Setup \> Global inventory accounting parameters \> Integrations parameters**.</span></span>
1. <span data-ttu-id="8808e-184">Az **Adatszolgáltatás végpontja** és a **Global Inventory Accounting végpont** mezőiben adja meg az URL-címeket abból az e-mailből, amit a globális készletkönyvelési csoport küldött, amikor előképként jelentkezett.</span><span class="sxs-lookup"><span data-stu-id="8808e-184">In the **Data service endpoint** and **Global inventory accounting endpoint** fields, enter the URLs from the email that the Global Inventory Accounting team sent when you signed up for the preview.</span></span>

<span data-ttu-id="8808e-185">A Global Inventory Accounting készen áll a használatra.</span><span class="sxs-lookup"><span data-stu-id="8808e-185">Global Inventory Accounting is now ready to use.</span></span>
