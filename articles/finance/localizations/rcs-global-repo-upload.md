---
title: ER-konfigurációk létrehozása az RCS-ben, és feltöltésük a globális tárba
description: Ez a témakör azt mutatja be, hogyan hozhatók létre a Microsoft Regulatory Configuration Services (RCS) elektronikus jelentéskészítési (ER) konfigurációi, és tölthetők fel a globális tárba.
author: JaneA07
manager: AnnBe
ms.date: 09/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace, RCS
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 5b2b8f35b9931f8fd1824c20e9045da68af33ad5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444037"
---
# <a name="create-er-configurations-in-regulatory-configuration-services-rcs-and-upload-them-to-the-global-repository"></a><span data-ttu-id="a9e68-103">ER-konfigurációk létrehozása a Regulatory Configuration Services (RCS) rendszerben, és feltöltésük a globális tárba</span><span class="sxs-lookup"><span data-stu-id="a9e68-103">Create ER configurations in Regulatory Configuration Services (RCS) and upload them to the Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a9e68-104">A Microsoft Regulatory Configuration Services (RCS) segítségével elektronikus jelentéskészítési (ER) konfigurációk készíthetők, majd közzétehetők a szervezeten belüli felhasználásra.</span><span class="sxs-lookup"><span data-stu-id="a9e68-104">You can use Microsoft Regulatory Configuration Services (RCS) to design Electronic reporting (ER) configurations and publish them so that they can be used in your organization.</span></span>

<span data-ttu-id="a9e68-105">A következő lépések leírják, hogy a rendszergazda vagy az elektronikus jelentéskészítési fejlesztői szerepkörben lévő felhasználók hogyan hozhatják létre az RCS-példányban konfigurált ER-konfiguráció egy származtatott verzióját, majd hogyan tölthetik fel a származtatott konfigurációt a globális tárba.</span><span class="sxs-lookup"><span data-stu-id="a9e68-105">The following procedures explain how a user in the System Administrator or Electronic Reporting Developer role can create a derived version of an ER configuration that has been configured in an RCS instance, and then upload the derived configuration to the Global repository.</span></span> 

<span data-ttu-id="a9e68-106">Mielőtt teljesítené ezeket az eljárásokat, végre kell hajtania a következő előfeltételeket:</span><span class="sxs-lookup"><span data-stu-id="a9e68-106">Before you can complete those procedures, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="a9e68-107">Nyisson meg egy RCS-példányt.</span><span class="sxs-lookup"><span data-stu-id="a9e68-107">Access an RCS instance.</span></span>
- <span data-ttu-id="a9e68-108">Hozzon létre egy aktív konfigurációszolgáltatót.</span><span class="sxs-lookup"><span data-stu-id="a9e68-108">Create an active configuration provider.</span></span> <span data-ttu-id="a9e68-109">További információért tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.</span><span class="sxs-lookup"><span data-stu-id="a9e68-109">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

<span data-ttu-id="a9e68-110">Arról is meg kell győződnie, hogy a vállalatnál RCS-környezet van kiépítve.</span><span class="sxs-lookup"><span data-stu-id="a9e68-110">You must also make sure that an RCS environment is provisioned for your company.</span></span>

1. <span data-ttu-id="a9e68-111">A Finance and Operations alkalmazásban lépjen a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="a9e68-111">In a Finance and Operations app, go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="a9e68-112">Ha nincs RCS környezete a vállalathoz, kattintson a **Regulatory services – Külső konfiguráció** lehetőségre, és kövesse az RCS-környezet létrehozására vonatkozó instrukciókat.</span><span class="sxs-lookup"><span data-stu-id="a9e68-112">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration external**, and then follow the instructions to provision one.</span></span>

<span data-ttu-id="a9e68-113">Ha van már RCS-környezet létesítve a vállalat számára, akkor az oldal URL-címével érheti el a bejelentkezési beállítást.</span><span class="sxs-lookup"><span data-stu-id="a9e68-113">If an RCS environment has been already provisioned for your company, use the page URL to access it by selecting the sign-in option.</span></span>

## <a name="create-a-derived-version-of-a-configuration-in-rcs"></a><span data-ttu-id="a9e68-114">Konfiguráció származtatott verziójának létrehozása az RCS-ben</span><span class="sxs-lookup"><span data-stu-id="a9e68-114">Create a derived version of a configuration in RCS</span></span>

1. <span data-ttu-id="a9e68-115">Az **Elektronikus jelentéskészítés** munkaterületen ellenőrizze, hogy rendelkezik-e a szervezethez tartozó aktív konfigurációszolgáltatóval.</span><span class="sxs-lookup"><span data-stu-id="a9e68-115">In the **Electronic reporting** workspace, verify that you have an active configuration provider for your organization.</span></span> 
2. <span data-ttu-id="a9e68-116">Válassza a **Jelentéskészítési konfigurációk** elemet.</span><span class="sxs-lookup"><span data-stu-id="a9e68-116">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="a9e68-117">Válassza ki azt a konfigurációt, amelyből új verziót szeretne származtatni.</span><span class="sxs-lookup"><span data-stu-id="a9e68-117">Select the configuration that you want to derive a new version from.</span></span> <span data-ttu-id="a9e68-118">A fa feletti szűrő mező segítségével tovább szűkítheti a keresés eredményeit.</span><span class="sxs-lookup"><span data-stu-id="a9e68-118">You can use the filter field above the tree to narrow your search.</span></span>
4. <span data-ttu-id="a9e68-119">Válassza a **Konfiguráció létrehozása** \> **Származtatás névből** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a9e68-119">Select **Create configuration** \> **Derive from Name**.</span></span>
5. <span data-ttu-id="a9e68-120">Adjon meg egy nevet és egy leírást, majd válassza a **Konfiguráció létrehozása** lehetőséget egy új származtatott verzió létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="a9e68-120">Enter a name and description, and then select **Create configuration** to create a new derived version.</span></span>
6. <span data-ttu-id="a9e68-121">Válassza ki az újonnan származtatott konfigurációt, adja meg a verzió leírását, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="a9e68-121">Select the newly derived configuration, add a description of the version, and then select **OK**.</span></span> <span data-ttu-id="a9e68-122">A konfiguráció állapota **Kész** értékre módosul.</span><span class="sxs-lookup"><span data-stu-id="a9e68-122">The status of the configuration to is changed to **Completed**.</span></span>

![Új konfigurációverzió az RCS-ben](media/RCS_CompleteConfig.JPG)

> [!NOTE]
> <span data-ttu-id="a9e68-124">A konfiguráció állapotának módosításakor előfordulhat, hogy a csatlakoztatott alkalmazásokhoz kapcsolódó ellenőrzési hibaüzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="a9e68-124">When the configuration status is changed, you might receive a validation error message that is related to the connected applications.</span></span> <span data-ttu-id="a9e68-125">Ha ki szeretné kapcsolni a hitelesítést, válassza ki a Művelet panelen a **Konfigurációk** lapot, válassza a **Felhasználói paraméterek** lehetőséget, majd állítsa be a **Konfiguráció állapotváltozással és új alappal kapcsolatos érvényesítésének kihagyása** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="a9e68-125">To turn off the validation, on the Action Pane on the **Configurations** tab, select **User parameters**, and then set the **Skip validation at configuration's status change and rebase** option to **Yes**</span></span> 

## <a name="upload-a-configuration-to-the-global-repository"></a><span data-ttu-id="a9e68-126">Konfiguráció feltöltése a globális tárba</span><span class="sxs-lookup"><span data-stu-id="a9e68-126">Upload a configuration to the Global repository</span></span>

<span data-ttu-id="a9e68-127">Ha új vagy származtatott konfiguráció szeretne megosztani a szervezettel, akkor feltöltheti azt a globális tárba.</span><span class="sxs-lookup"><span data-stu-id="a9e68-127">To share a new or derived configuration with your organization, you can upload it to the Global repository.</span></span>

1. <span data-ttu-id="a9e68-128">Válassza ki a konfiguráció kész verzióját, majd válassza a **Feltöltés a tárba** parancsot.</span><span class="sxs-lookup"><span data-stu-id="a9e68-128">Select the completed version of the configuration, and then select **Upload into repository**.</span></span>
2. <span data-ttu-id="a9e68-129">Válassza ki a **Globális (Microsoft)** beállítást, majd válassza a **Feltöltés** elemet.</span><span class="sxs-lookup"><span data-stu-id="a9e68-129">Select the **Global (Microsoft)** option, and then select **Upload**.</span></span>

    ![Feltöltés a tárba beállításai](media/RCS_Upload_to_GlobalRepo_options.JPG)

3. <span data-ttu-id="a9e68-131">A megerősítő párbeszédpanelen válassza az **Igen** gombot.</span><span class="sxs-lookup"><span data-stu-id="a9e68-131">In the confirmation message box, select **Yes**.</span></span> 
4. <span data-ttu-id="a9e68-132">Szükség szerint frissítse a verzió leírását, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="a9e68-132">Update the description of the version as required, and then select **OK**.</span></span> 

<span data-ttu-id="a9e68-133">A konfiguráció állapota **Megosztás** értékre frissül, és a konfiguráció feltöltésre kerül a globális tárba.</span><span class="sxs-lookup"><span data-stu-id="a9e68-133">The status of the configuration is updated to **Share**, and the configuration is uploaded to the Global repository.</span></span> <span data-ttu-id="a9e68-134">Innen a következő módokon dolgozhat vele:</span><span class="sxs-lookup"><span data-stu-id="a9e68-134">From there, you can work with it in the following ways:</span></span>

- <span data-ttu-id="a9e68-135">Importálhatja a Dynamics 365-példányába.</span><span class="sxs-lookup"><span data-stu-id="a9e68-135">Import it into your Dynamics 365 instance.</span></span> <span data-ttu-id="a9e68-136">További információ: [(ER) Konfigurációk importálása RCS-ből](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).</span><span class="sxs-lookup"><span data-stu-id="a9e68-136">For more information, see [(ER) Import configurations from RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md).</span></span>
- <span data-ttu-id="a9e68-137">Megoszthatja egy harmadik féllel vagy külső szervezettel, lásd: [RCS elektronikus jelentéskészítési (ER) konfigurációk megosztása külső szervezetekkel](rcs-global-repo-share-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="a9e68-137">Share it with a third party or an external organization, see [RCS Share Electronic reporting (ER) configurations with external organizations](rcs-global-repo-share-configuration.md)</span></span>

    ![Származtatott Intrastat Contoso konfigurációverzió a globális tárban](media/RCS_Config_upload_GlobalRepo.JPG)

## <a name="delete-a-configuration-from-the-global-repository"></a><span data-ttu-id="a9e68-139">Konfiguráció törlése a Globális adattárból</span><span class="sxs-lookup"><span data-stu-id="a9e68-139">Delete a configuration from the Global repository</span></span>
<span data-ttu-id="a9e68-140">Hajtsa végre a következő lépéseket a szervezete által létrehozott konfiguráció törléséhez.</span><span class="sxs-lookup"><span data-stu-id="a9e68-140">Complete the following steps to delete a configuration that your organization has created.</span></span>

1. <span data-ttu-id="a9e68-141">Az **Elektronikus jelentés** munkaterületen ellenőrizze, hogy konfigurációszolgáltató állapota **Aktív**.</span><span class="sxs-lookup"><span data-stu-id="a9e68-141">In the **Electronic reporting** workspace, verify that your configuration provider is **Active**.</span></span> <span data-ttu-id="a9e68-142">További információért tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.</span><span class="sxs-lookup"><span data-stu-id="a9e68-142">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>
2. <span data-ttu-id="a9e68-143">Válassza az aktív konfiguráció szolgáltatójának **adattár** elemét.</span><span class="sxs-lookup"><span data-stu-id="a9e68-143">On your active configuration provider, select **repository**.</span></span>
3. <span data-ttu-id="a9e68-144">Válassza ki az adattár típusának a **Globális** értéket, majd válassza a **Megnyitás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a9e68-144">Select the repository type **Global**, and select **Open**.</span></span>
4. <span data-ttu-id="a9e68-145">A **Szűrő** gyorslapon keresse meg azt a konfigurációt, amelyet törölni szeretne a **Szűrő** funkció segítségével.</span><span class="sxs-lookup"><span data-stu-id="a9e68-145">On the **Filter** FastTab, find the configuration that you want to delete by using the **Filter** functionality.</span></span>
5. <span data-ttu-id="a9e68-146">A **Verzió** gyorslapon válassza ki a törölni kívánt konfiguráció verziószámát, majd válassza a **Törlés** lehetőséget:</span><span class="sxs-lookup"><span data-stu-id="a9e68-146">On the **Version** FastTab, select the version of the configuration that you want to delete, and then select **Delete**:</span></span>

    ![Konfiguráció törlése a globális adattárból](media/RCS_Delete_from_GlobalRepo.JPG)

6. <span data-ttu-id="a9e68-148">A megerősítő párbeszédpanelen válassza az **Igen** gombot.</span><span class="sxs-lookup"><span data-stu-id="a9e68-148">In the confirmation message box, select **Yes**.</span></span>

    ![Konfigurációverzió visszaigazolási üzenetének törlése](media/RCS_Delete_from_GlobalRepo_Msg.JPG)
 
<span data-ttu-id="a9e68-150">A konfigurációverziót törölve lesz, és egy megerősítő üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="a9e68-150">The configuration version is deleted, and confirmation message is shown.</span></span> 

> [!NOTE]
> <span data-ttu-id="a9e68-151">A konfigurációkat csak az azokat létrehozó Konfigurációs szolgáltató tudja törölni.</span><span class="sxs-lookup"><span data-stu-id="a9e68-151">Configurations can only be deleted by the Configuration provider that created them.</span></span> <span data-ttu-id="a9e68-152">Ha egy másik szervezettel meg lett osztva a konfiguráció, akkor a konfiguráció törlése előtt a megosztást meg kell szüntetni.</span><span class="sxs-lookup"><span data-stu-id="a9e68-152">If the configuration has been shared with another organization, the configuration will need to be unshared before you delete it.</span></span>
 
