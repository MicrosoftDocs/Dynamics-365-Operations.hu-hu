---
title: Első lépések a költségkönyvelési szolgáltatásban (privát előnézet)
description: Ez a témakör bemutatja a költségkönyvelési szolgáltatás licencelési adatait és telepítési útmutatását.
author: AndersGirke
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: b6756e3745aa4596bd5d63ad15aaf4385cfc4813
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813195"
---
# <a name="get-started-with-the-cost-accounting-service-private-preview"></a><span data-ttu-id="04056-103">Első lépések a költségkönyvelési szolgáltatásban (privát előnézet)</span><span class="sxs-lookup"><span data-stu-id="04056-103">Get started with the cost accounting service (private preview)</span></span>

[!INCLUDE [banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="04056-104">A témakörben leírt funkciók privát előzetes kiadás részeként állnak rendelkezésre.</span><span class="sxs-lookup"><span data-stu-id="04056-104">The functionality that is described in this topic is available as part of a private preview release.</span></span> <span data-ttu-id="04056-105">Ennek a témakörnek a tartalma és az ebben ismertetett funkciók változhatnak.</span><span class="sxs-lookup"><span data-stu-id="04056-105">The content of this topic and the functionality that it describes are subject to change.</span></span> <span data-ttu-id="04056-106">Az előzetes kiadásokkal kapcsolatban további információkat az [Egyverziós szolgáltatásfrissítések GYIK](../../fin-ops-core/fin-ops/get-started/one-version.md) oldalon találhat.</span><span class="sxs-lookup"><span data-stu-id="04056-106">For more information about preview releases, see [One version service updates FAQ](../../fin-ops-core/fin-ops/get-started/one-version.md).</span></span>

<span data-ttu-id="04056-107">A Költségkönyvelés szolgáltatás segítségével több készlet könyvelését végezheti el a beállított költségkönyvelési főkönyvben.</span><span class="sxs-lookup"><span data-stu-id="04056-107">The cost accounting service lets you do multiple inventory accounting in the cost accounting ledgers that you've set up.</span></span> <span data-ttu-id="04056-108">Minden költségkönyvelési főkönyvhöz egy *szabályt* társít.</span><span class="sxs-lookup"><span data-stu-id="04056-108">You associate each cost accounting ledger with a *convention*.</span></span> <span data-ttu-id="04056-109">Egy szabály a következő típusú könyvelési irányelvek gyűjteményét jelenti:</span><span class="sxs-lookup"><span data-stu-id="04056-109">A convention is a collection of the following types of accounting policies:</span></span>

- <span data-ttu-id="04056-110">Költségobjektum</span><span class="sxs-lookup"><span data-stu-id="04056-110">Cost object</span></span>
- <span data-ttu-id="04056-111">Bemeneti mérték alapja</span><span class="sxs-lookup"><span data-stu-id="04056-111">Input measurement basis</span></span>
- <span data-ttu-id="04056-112">Költségforgalom-feltételezés</span><span class="sxs-lookup"><span data-stu-id="04056-112">Cost flow assumption</span></span>
- <span data-ttu-id="04056-113">Költségösszetevő</span><span class="sxs-lookup"><span data-stu-id="04056-113">Cost element</span></span>

> [!NOTE]
> <span data-ttu-id="04056-114">Még a költségkönyvelési szolgáltatás bekapcsolása után is elvégezheti szokás szerint a készletkönyvelést a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="04056-114">Even after you've turned on the cost accounting service, you can still do  inventory accounting in Microsoft Dynamics 365 Supply Chain Management, as usual.</span></span>

<span data-ttu-id="04056-115">A Költségkönyvelés szolgáltatás egy bővítmény.</span><span class="sxs-lookup"><span data-stu-id="04056-115">The cost accounting service is an add-in.</span></span> <span data-ttu-id="04056-116">Ahhoz, hogy hozzáférhetővé váljanak a funkciók, telepítenie kell a Microsoft Dynamics Lifecycle Services (LCS) felületéről.</span><span class="sxs-lookup"><span data-stu-id="04056-116">To makes its features available, you must install it from Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="04056-117">Ennek megfelelően kiválaszthatja, hogy a termelési környezetekben való bekapcsolás előtt szeretné-e értékelni tesztkörnyezetben.</span><span class="sxs-lookup"><span data-stu-id="04056-117">Therefore, you can choose to evaluate it in a test environment before you turn it on for production environments.</span></span>

<span data-ttu-id="04056-118">A Költségkönyvelés szolgáltatás jelenleg nem támogatja a Dynamics 365 Supply Chain Management szolgáltatásba beépített összes költségkönyvelési funkciót.</span><span class="sxs-lookup"><span data-stu-id="04056-118">The cost accounting service doesn't currently support all the cost management features that are built into Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="04056-119">Ezért fontos, hogy meggyőződjön, hogy a jelenleg elérhető funkciókészlet kielégíti-e a követelményeket.</span><span class="sxs-lookup"><span data-stu-id="04056-119">Therefore, it's important that you evaluate whether the set of features that is currently available will meet your requirements.</span></span>

## <a name="how-to-get-the-cost-accounting-service-private-preview"></a><a name="sign-up"></a><span data-ttu-id="04056-120">Hogyan érjük el a költségkönyvelési szolgáltatást (privát előnézet)</span><span class="sxs-lookup"><span data-stu-id="04056-120">How to get the cost accounting service (private preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04056-121">A költségkönyvelési szolgáltatás használatához rendelkeznie kell LCS-kompatibilis magas elérhetőségű környezettel (nem OneBox.környezettel), és a Dynamics 365 Supply Chain Management 10.0.11-es vagy újabb verzióját kell futtatnia.</span><span class="sxs-lookup"><span data-stu-id="04056-121">To use the cost accounting service, you must have an LCS-enabled high-availability environment (not a OneBox environment), and you must be running Dynamics 365 Supply Chain Management version 10.0.11 or later.</span></span>

<span data-ttu-id="04056-122">A költségkönyvelési szolgáltatás privát előnézetére történő feliratkozáshoz küldje el a LCS környezeti azonosítót e-mailben a [Költségkönyvelési szolgáltatáshoz (privát előnézet)](mailto:aevengir@microsoft.com?subject=Cost%20accounting%20service%20%28private%20preview%29).</span><span class="sxs-lookup"><span data-stu-id="04056-122">To sign up for the cost accounting service private preview, please send your LCS environment ID by email to [Cost accounting service (private preview)](mailto:aevengir@microsoft.com?subject=Cost%20accounting%20service%20%28private%20preview%29).</span></span> <span data-ttu-id="04056-123">Ha felvételt nyert a programba, elküldjük Önnek a költségszámítási szolgáltatás bétakulcsát tartalmazó nyomon követési e-mail üzenetet.</span><span class="sxs-lookup"><span data-stu-id="04056-123">On approving you for the program, we will send you a follow up email that contains a cost accounting service beta key.</span></span> <span data-ttu-id="04056-124">Ha megkapta a bétakulcsot, folytathatja [a bővítmény telepítését](#install).</span><span class="sxs-lookup"><span data-stu-id="04056-124">On receiving the beta key, you can proceed by [installing the add-in](#install).</span></span>

## <a name="licensing"></a><span data-ttu-id="04056-125">Licenckezelés</span><span class="sxs-lookup"><span data-stu-id="04056-125">Licensing</span></span>

<span data-ttu-id="04056-126">A Költségkönyvelés szolgáltatás egy licencben szerepel az Supply Chain Management szolgáltatásban elérhető készletkönyvelési standard funkciókkal.</span><span class="sxs-lookup"><span data-stu-id="04056-126">The cost accounting service is licensed together with the standard features of inventory accounting that are available for Supply Chain Management.</span></span> <span data-ttu-id="04056-127">Nem kell további licencet vásárolnia a Költségkönyvelés szolgáltatás használatához.</span><span class="sxs-lookup"><span data-stu-id="04056-127">You don't have to purchase an additional license to use the cost accounting service.</span></span>

## <a name="install-the-add-in"></a><a name="install"></a><span data-ttu-id="04056-128">Telepítse a bővítményt</span><span class="sxs-lookup"><span data-stu-id="04056-128">Install the add-in</span></span>

<span data-ttu-id="04056-129">A Költségkönyvelés szolgáltatás használatához a következő eljárás szerint telepítse a Supply Chain Management költségszámítási szolgáltatásának beépülő modulját.</span><span class="sxs-lookup"><span data-stu-id="04056-129">To use the cost accounting service, install the cost accounting service add-in for Supply Chain Management as described in the following procedure.</span></span>

1. <span data-ttu-id="04056-130">[Regisztráljon](#sign-up) a költségkönyvelési szolgáltatásba (privát előnézet).</span><span class="sxs-lookup"><span data-stu-id="04056-130">[Sign up](#sign-up) for the cost accounting service (private preview).</span></span>

1. <span data-ttu-id="04056-131">Bejelentkezés az LCS alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="04056-131">Sign in to LCS.</span></span>

1. <span data-ttu-id="04056-132">Lépjen a **Előzetes funkció kezelése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="04056-132">Go to **Preview feature management**.</span></span>

1. <span data-ttu-id="04056-133">Válassza ki a plusz jelet (**+**).</span><span class="sxs-lookup"><span data-stu-id="04056-133">Select the plus sign (**+**).</span></span>

1. <span data-ttu-id="04056-134">A **kód** mezőbe írja be a költségkönyvelési szolgáltatáshoz tartozó bővítmény bétakulcsát.</span><span class="sxs-lookup"><span data-stu-id="04056-134">In the **Code** field, enter your add-in beta key for the cost accounting service.</span></span> <span data-ttu-id="04056-135">(E-mailben meg kellett volna kapnia a kulcsot.)</span><span class="sxs-lookup"><span data-stu-id="04056-135">(You should have received your key by email.)</span></span>

1. <span data-ttu-id="04056-136">Válassza a **Blokkolás feloldása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="04056-136">Select **Unblock**.</span></span>

1. <span data-ttu-id="04056-137">Nyissa meg azt a LCS-környezetet, amelyhez hozzá szeretné adni a szolgáltatást.</span><span class="sxs-lookup"><span data-stu-id="04056-137">Open the LCS environment where you want to add the service.</span></span>

1. <span data-ttu-id="04056-138">Lépjen a **Teljes részletek** elemre.</span><span class="sxs-lookup"><span data-stu-id="04056-138">Go to **Full details**.</span></span>

1. <span data-ttu-id="04056-139">Görgessen le a **Környezeti bővítmények** gyorslapra.</span><span class="sxs-lookup"><span data-stu-id="04056-139">Scroll down to the **Environment add-ins** FastTab.</span></span>

1. <span data-ttu-id="04056-140">Válassza az **Új bővítmény telepítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="04056-140">Select **Install a new add-in**.</span></span>

1. <span data-ttu-id="04056-141">Válassza a **Költségkönyvelési szolgáltatás** elemet.</span><span class="sxs-lookup"><span data-stu-id="04056-141">Select **Cost accounting service**.</span></span>

1. <span data-ttu-id="04056-142">Kövesse a telepítési útmutatót, és fogadja el a feltételeit és kikötéseit.</span><span class="sxs-lookup"><span data-stu-id="04056-142">Follow the installation guide, and agree to the terms and conditions.</span></span>

1. <span data-ttu-id="04056-143">Válassza a **Telepítés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="04056-143">Select **Install**.</span></span>

1. <span data-ttu-id="04056-144">A **környezeti bővítmények** gyorslapon látható, hogy a Költségkönyvelés szolgáltatás telepítése folyamatban van.</span><span class="sxs-lookup"><span data-stu-id="04056-144">On the **Environment add-ins** FastTab, you should see that the cost accounting service is being installed.</span></span> <span data-ttu-id="04056-145">Néhány perc múlva az állapotot változik **Telepítés folyamatban** állapotról **Telepítve** értékre.</span><span class="sxs-lookup"><span data-stu-id="04056-145">After a few minutes, the status should change from **Installing** to **Installed**.</span></span> <span data-ttu-id="04056-146">(Elképzelhető, hogy frissíteni kell a lapot a változás megtekintéséhez.) Ezen a ponton a Költségkönyvelés szolgáltatás készen áll a használatra.</span><span class="sxs-lookup"><span data-stu-id="04056-146">(You might have to refresh the page to see this change.) At that point, the cost accounting service is ready for use.</span></span>

## <a name="set-up-the-integration"></a><span data-ttu-id="04056-147">Integráció beállítása</span><span class="sxs-lookup"><span data-stu-id="04056-147">Set up the integration</span></span>

<span data-ttu-id="04056-148">A Költségkönyvelés szolgáltatás és Dynamics 365 Supply Chain Management közötti integráció beállításához:</span><span class="sxs-lookup"><span data-stu-id="04056-148">To set up the integration between the cost accounting service and Dynamics 365 Supply Chain Management:</span></span>

1. <span data-ttu-id="04056-149">Lépjen a **Rendszerfelügyelet > Funkciókezelés** elemre.</span><span class="sxs-lookup"><span data-stu-id="04056-149">Go to **System administration > Feature Management**.</span></span>

1. <span data-ttu-id="04056-150">Válassza a **Frissítések keresése** elemet.</span><span class="sxs-lookup"><span data-stu-id="04056-150">Select **Check for updates**.</span></span>

1. <span data-ttu-id="04056-151">Nyissa meg az **összes** fület, és keresse meg a *Költségkönyvelési szolgáltatás* nevű funkciót.</span><span class="sxs-lookup"><span data-stu-id="04056-151">Open the **All** tab and search for the feature named *Cost accounting service*.</span></span>

1. <span data-ttu-id="04056-152">Válassza az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="04056-152">Select **Enable now**.</span></span>

1. <span data-ttu-id="04056-153">Lépjen a **Költségkezelés > Költségkönyvelési szolgáltatás > Beállítás > Költségkönyvelési szolgáltatás paraméterei > Integráció paraméterei** elemre.</span><span class="sxs-lookup"><span data-stu-id="04056-153">Go to **Cost management > Cost accounting service > Setup > Cost accounting service parameters > Integrations parameters**.</span></span>

1. <span data-ttu-id="04056-154">Írja be a következő kódot az **Alkalmazás azonosítója** mezőbe:</span><span class="sxs-lookup"><span data-stu-id="04056-154">In the **Application ID** field, enter the following code:</span></span><br> <span data-ttu-id="04056-155">08231eb2-a501-4edb-b3c5-aede5e5e0c3f</span><span class="sxs-lookup"><span data-stu-id="04056-155">08231eb2-a501-4edb-b3c5-aede5e5e0c3f</span></span>

1. <span data-ttu-id="04056-156">Az **Adatszolgáltatási végpont** mezőbe írja be a következő URL-címet:</span><span class="sxs-lookup"><span data-stu-id="04056-156">In the **Data service endpoint** field, enter the following URL:</span></span><br>https://operationsdataservice.operations365.dynamics.com/

1. <span data-ttu-id="04056-157">Az **Költségkönyvelési szolgáltatási végpont** mezőbe írja be a következő URL-címet:</span><span class="sxs-lookup"><span data-stu-id="04056-157">In the **Cost accounting service endpoint** field, enter the following URL:</span></span><br>https://costaccountingservice.operations365.dynamics.com/

1. <span data-ttu-id="04056-158">A Költségkönyvelés szolgáltatás készen áll a használatra.</span><span class="sxs-lookup"><span data-stu-id="04056-158">The cost accounting service is now ready for use.</span></span>

## <a name="related-resources"></a><span data-ttu-id="04056-159">Kapcsolódó erőforrások</span><span class="sxs-lookup"><span data-stu-id="04056-159">Related resources</span></span>

[<span data-ttu-id="04056-160">Költségkönyvelési szolgáltatás kezdőlap</span><span class="sxs-lookup"><span data-stu-id="04056-160">Cost accounting service home page</span></span>](cost-accounting-service-home.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]