---
title: Regulatory Configuration Services (RCS) – Globalizációs funkció
description: Ez a témakör azt mutatja be, hogyan használható a Microsoft Regulatory Configuration Services (RCS) és a Globális tár a globalizációs funkciók létrehozásához és használatához.
author: JaneA07
manager: AnnBe
ms.date: 06/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RCS, RCSWorkspace, e-Invoicing service
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: ae46dab5250fbe8096f43e420cb7ef33a5862af0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443886"
---
# <a name="regulatory-configuration-services-rcs---globalization-features"></a><span data-ttu-id="61528-103">Regulatory Configuration Services (RCS) – Globalizációs funkció</span><span class="sxs-lookup"><span data-stu-id="61528-103">Regulatory Configuration Services (RCS) - Globalization features</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="61528-104">A Microsoft Regulatory Configuration Services (RCS) segítségével létrehozhat egy globalizációs szolgáltatást, amely a globalizációs szolgáltatásokban, például az elektronikus számlázásban is használható.</span><span class="sxs-lookup"><span data-stu-id="61528-104">You can use Microsoft Regulatory Configuration Services (RCS) to create a Globalization feature that can be used in Globalization services, such as an e-invoicing service.</span></span> <span data-ttu-id="61528-105">Az RCS segítségével a következő feladatokat hajthatja végre:</span><span class="sxs-lookup"><span data-stu-id="61528-105">RCS lets you perform these tasks:</span></span>

- <span data-ttu-id="61528-106">A szolgáltatáshoz kapcsolódó összetevők definiálása.</span><span class="sxs-lookup"><span data-stu-id="61528-106">Define related components of a feature.</span></span>
- <span data-ttu-id="61528-107">A funkció életciklusának kezelése a funkció állapotán keresztül.</span><span class="sxs-lookup"><span data-stu-id="61528-107">Manage the feature lifecycle through a feature's status.</span></span>
- <span data-ttu-id="61528-108">Szolgáltatás elérhetővé tétele meghatározott környezetekben.</span><span class="sxs-lookup"><span data-stu-id="61528-108">Make a feature available for defined environments.</span></span>
- <span data-ttu-id="61528-109">Szolgáltatások megosztása más szervezetekkel.</span><span class="sxs-lookup"><span data-stu-id="61528-109">Share a feature with other organizations.</span></span>

<span data-ttu-id="61528-110">A következő lépések leírják, hogy egy RCS-felhasználó hogyan adhatja hozzá a globalizációs szolgáltatásokat és a kapcsolódó összetevőket, frissítheti a szolgáltatás állapotát, és teheti elérhetővé a szolgáltatást, hogy a globalizációs szolgáltatásokban is használható legyen.</span><span class="sxs-lookup"><span data-stu-id="61528-110">The following procedures explain how a user in RCS can add a Globalization feature and related components, update the feature's status, and make the feature available so that it can be used in Globalization services.</span></span>

<span data-ttu-id="61528-111">Az eljárások elvégzése előtt be kell fejeznie a következő feladatokhoz kapcsolódó lépéseket:</span><span class="sxs-lookup"><span data-stu-id="61528-111">Before you complete the procedures, you must complete the steps that are related to the following tasks:</span></span>

- <span data-ttu-id="61528-112">Hozzáférés egy RCS-példányhoz.</span><span class="sxs-lookup"><span data-stu-id="61528-112">Accessing an RCS instance.</span></span>
- <span data-ttu-id="61528-113">Konfigurációs szolgáltató létrehozása és aktiválása.</span><span class="sxs-lookup"><span data-stu-id="61528-113">Creating and activating a configuration provider.</span></span> <span data-ttu-id="61528-114">További információért tekintse át a [Konfigurációszolgáltatók létrehozása és megjelölése aktívként](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md) eljárást.</span><span class="sxs-lookup"><span data-stu-id="61528-114">For more information, see [Create configuration providers and mark them as active](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).</span></span>

<span data-ttu-id="61528-115">Hajtsa végre az alábbi lépéseket a Finance and Operations alkalmazáspéldányban.</span><span class="sxs-lookup"><span data-stu-id="61528-115">In your Finance and Operations apps instance, follow these steps.</span></span>

1. <span data-ttu-id="61528-116">Ugorjon a **Szervezeti adminisztráció** \> **Munkaterületek** \> **Elektronikus jelentés** pontra.</span><span class="sxs-lookup"><span data-stu-id="61528-116">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
2. <span data-ttu-id="61528-117">Ha nincs RCS környezete a vállalathoz, kattintson a **Regulatory services – konfiguráció** lehetőségre, és kövesse a létrehozására vonatkozó instrukciókat.</span><span class="sxs-lookup"><span data-stu-id="61528-117">If no RCS environment is provisioned for your company, select **Regulatory services – Configuration**, and follow the instructions to provision one.</span></span>

> [!NOTE]
> <span data-ttu-id="61528-118">Ha van már RCS-környezet létesítve a vállalat számára, akkor az oldal URL-címével érheti el a környezetet, a bejelentkezési beállítás kiválasztásával.</span><span class="sxs-lookup"><span data-stu-id="61528-118">If an RCS environment has already been provisioned for your company, use the page URL to access the environment by selecting the sign-in option.</span></span>

## <a name="turn-on-the-globalization-features"></a><span data-ttu-id="61528-119">A globalizációs szolgáltatások bekapcsolása</span><span class="sxs-lookup"><span data-stu-id="61528-119">Turn on the Globalization features</span></span>

1. <span data-ttu-id="61528-120">A RCS-példányban válassza ki a **Funkció kezelése** mozaikját.</span><span class="sxs-lookup"><span data-stu-id="61528-120">In your RCS instance, select the **Feature management** tile.</span></span>
2. <span data-ttu-id="61528-121">A **Funkció kezelése** munkaterületen válassza ki a **Globalizációs funkciókat** a listán, majd válassza az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="61528-121">In the **Feature management** workspace, select **Globalization features** in the list, and then select **Enable now**.</span></span>

    ![Globalizációs szolgáltatások a szolgáltatások kezelésében](./media/RCS_GlobalF_1%20Feature%20mgmt.JPG)

## <a name="globalization-features"></a><span data-ttu-id="61528-123">Globalizációs funkciók</span><span class="sxs-lookup"><span data-stu-id="61528-123">Globalization features</span></span>

<span data-ttu-id="61528-124">A globalizációs funkciók használatához először importálnia kell azt a globális tárházból, és létre kell hoznia saját verzióját.</span><span class="sxs-lookup"><span data-stu-id="61528-124">To use a Globalization feature, you must first import it from the the Global repository and create your own version of it.</span></span> <span data-ttu-id="61528-125">A globalizációs funkciókat kétféleképpen lehet hozzáadni:</span><span class="sxs-lookup"><span data-stu-id="61528-125">There are two ways to add Globalization features:</span></span>

- <span data-ttu-id="61528-126">Olyan származtatott funkció hozzáadása, amely egy már közzétett vagy megosztott meglévő szolgáltatáson alapul.</span><span class="sxs-lookup"><span data-stu-id="61528-126">Add a derived feature that is based on an existing feature that has been published or shared.</span></span>
- <span data-ttu-id="61528-127">Új, a nulláról létrehozott funkció hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="61528-127">Add a new feature that you've created from scratch.</span></span>

## <a name="access-globalization-features"></a><span data-ttu-id="61528-128">Globalizációs funkciók elérése</span><span class="sxs-lookup"><span data-stu-id="61528-128">Access Globalization features</span></span>

1. <span data-ttu-id="61528-129">Győződjön meg róla, hogy a **globalizációs szolgáltatások** funkció be van kapcsolva a szolgáltatások kezelése modulban, az ebben a témakörben korábban ismertetett módon.</span><span class="sxs-lookup"><span data-stu-id="61528-129">Make sure that the **Globalization features** feature is turned on in Feature management, as described earlier in this topic.</span></span>
2. <span data-ttu-id="61528-130">Nyissa meg az új **Globalizációs szolgáltatások** munkaterületet, majd a **Szolgáltatások** területen válassza az **E-számlázás** mozaikot.</span><span class="sxs-lookup"><span data-stu-id="61528-130">Open the new **Globalization Features** workspace, and then, under **Features**, select the **e-Invoicing** tile.</span></span>

    ![Globális szolgáltatások munkaterülete](./media/RCS_GlobalF_2%20Feature%20wrkspace.JPG)

    <span data-ttu-id="61528-132">Megnyílik az **E-számlázási szolgáltatások** lap.</span><span class="sxs-lookup"><span data-stu-id="61528-132">The **e-Invoicing Features** page is opened.</span></span>

    ![E-számlázási szolgáltatások lap](./media/RCS_GlobalF_3%20Feature%20form.JPG)

## <a name="add-a-derived-globalization-feature"></a><span data-ttu-id="61528-134">Származtatott globalizációs funkció hozzáadása</span><span class="sxs-lookup"><span data-stu-id="61528-134">Add a derived Globalization feature</span></span>

<span data-ttu-id="61528-135">Új globalizációs funkciókat úgy adhat hozzá, hogy egy már közzétett vagy megosztott meglévő szolgáltatásból ered.</span><span class="sxs-lookup"><span data-stu-id="61528-135">You can add a new Globalization feature by deriving it from an existing feature that has been published or shared.</span></span>

1. <span data-ttu-id="61528-136">Válassza az **Importálás** lehetőséget, ha meg szeretné nyitni az **Importálási funkció a globális tárházból** lapról.</span><span class="sxs-lookup"><span data-stu-id="61528-136">Select **Import** to open the **Import feature from Global repository** page.</span></span>

    ![Szolgáltatás importálása a globális tárház lapjáról](./media/RCS_GlobalF_4%20Feature%20import%20form%20GR.JPG)

2. <span data-ttu-id="61528-138">A legújabb szolgáltatások beszerzéséhez válassza a **Szinkronizálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="61528-138">Select **Synchronize** to get the latest features.</span></span>

    <span data-ttu-id="61528-139">A szinkronizált lista olyan funkciókat tartalmaz, amelyek elérhetők az Ön számára, akár azért, mert a Microsoft közzétette, akár azért, mert egy másik konfigurációs szolgáltató megosztotta Önnel.</span><span class="sxs-lookup"><span data-stu-id="61528-139">The synced list includes features that are available to you either because they were published by Microsoft or because they were shared with you by another configuration provider.</span></span>

    ![A szolgáltatások szinkronizált listája](./media/RCS_GlobalF_5%20Feature%20GR%20sync.JPG)

3. <span data-ttu-id="61528-141">Válassza ki az importálni kívánt funkciókat a listán, majd válassza az **Importálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="61528-141">In the list, select the features to import, and then select **Import**.</span></span> <span data-ttu-id="61528-142">A kiválasztott szolgáltatások sikeres importálásakor egy üzenet jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="61528-142">You receive a message when the selected features have been successfully imported.</span></span>

    ![Sikeres importálás üzenet](./media/RCS_GlobalF_6%20Feature%20GR%20import%20success.JPG)

4. <span data-ttu-id="61528-144">Válassza a **Hozzáadás** lehetőséget, majd a legördülő párbeszédpanelen válassza ki a **Meglévő verzió alapján** beállítást.</span><span class="sxs-lookup"><span data-stu-id="61528-144">Select **Add**, and then, in the drop-down dialog box, select the **Based on existing version** option.</span></span>
5. <span data-ttu-id="61528-145">Írja be a funkció nevét és a leírását.</span><span class="sxs-lookup"><span data-stu-id="61528-145">Enter a name and description for the feature.</span></span>
6. <span data-ttu-id="61528-146">A választható szolgáltatások listáján válassza ki a funkció alapverzióját, majd válassza a **Funkció létrehozása** elemet.</span><span class="sxs-lookup"><span data-stu-id="61528-146">In the list of available features, select the base version of the feature, and then select **Create feature**.</span></span>

    ![Származtatott funkció hozzáadása](./media/RCS_GlobalF_7%20Feature%20create%20derived.JPG)

    <span data-ttu-id="61528-148">A hozzáadott funkció létrejön, és **Vázlat** lesz az állapota.</span><span class="sxs-lookup"><span data-stu-id="61528-148">The feature that you added is created and has a status of **Draft**.</span></span>

    ![Vázlat állapotú származtatott funkció](./media/RCS_GlobalF_8%20Feature%20draft%20create.JPG)

7. <span data-ttu-id="61528-150">Tekintse át a szolgáltatások összetevőit annak a megállapításához, hogy szükségesek-e frissítések:</span><span class="sxs-lookup"><span data-stu-id="61528-150">Review the feature components to determine whether updates are required:</span></span>

    - <span data-ttu-id="61528-151">Tekintse át a konfigurációkat, ha testre szeretné szabni az elektronikus jelentések (ER) formátumát, valamint a szolgáltatás verziójának formátum-hozzárendelésével történő kötését.</span><span class="sxs-lookup"><span data-stu-id="61528-151">Review the configurations, in case you need to customize the Electronic reporting (ER) formats and their binding with format mappings for the feature version.</span></span>
    - <span data-ttu-id="61528-152">Ellenőrizze a beállítást, ha testre szeretné szabni a funkció verziójának **Műveletek** lapját, **Alkalmazhatósági szabályok** lapját és **Változók** lapját.</span><span class="sxs-lookup"><span data-stu-id="61528-152">Review the setup, in case you need to customize the **Actions** tab, **Applicability rules** tab, or **Variables** tab for the feature version.</span></span>

8. <span data-ttu-id="61528-153">A **Változatok** lapon válassza ki az **Érvényesség kezdő** dátumát, és adjon meg egy leírást, ha a **Leírás** mező üres.</span><span class="sxs-lookup"><span data-stu-id="61528-153">On the **Versions** tab, select an **Effective from** date, and enter a description if the **Description** field is blank.</span></span>
9. <span data-ttu-id="61528-154">A funkció befejezéséhez válassza az **Állapot módosítása** parancsot.</span><span class="sxs-lookup"><span data-stu-id="61528-154">Select **Change status** to complete the feature.</span></span> <span data-ttu-id="61528-155">A teljesített funkciókat egy adott környezet számára elérhetővé teheti, hogy a globalizációs szolgáltatásokban használható legyen, vagy közzétehető legyen a globális tárházban.</span><span class="sxs-lookup"><span data-stu-id="61528-155">Completed features can be made available for a specific environment so that they can be used in Globalization services, or they can be published to the Global repository.</span></span>

> [!NOTE]
> <span data-ttu-id="61528-156">A funkciók, amelyeknél a **Szolgáltatási verzió állapota** értéke **Közzétett**, megoszthatók külső szervezetekkel.</span><span class="sxs-lookup"><span data-stu-id="61528-156">Features that have a **Feature version status** value of **Published** can be shared with external organizations.</span></span>

## <a name="add-a-new-globalization-feature"></a><span data-ttu-id="61528-157">Új globalizációs funkció hozzáadása</span><span class="sxs-lookup"><span data-stu-id="61528-157">Add a new Globalization feature</span></span>

<span data-ttu-id="61528-158">Új globalizációs funkciót úgy is hozzáadhat, hogy a semmiből hozza létre.</span><span class="sxs-lookup"><span data-stu-id="61528-158">You can add a new Globalization feature by creating it from scratch.</span></span>

1. <span data-ttu-id="61528-159">Az **Szolgáltatás importálása a globális tárházból** lapon válassza ki a **Hozzáadás** elemet, majd a legördülő listából válassza az **Új szolgáltatás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="61528-159">On the **Import feature from Global repository** page, select **Add**, and then, in the drop-down dialog box, select the **New feature** option.</span></span>
2. <span data-ttu-id="61528-160">Írja be a funkció nevét és a leírását.</span><span class="sxs-lookup"><span data-stu-id="61528-160">Enter a name and description for the feature.</span></span>
3. <span data-ttu-id="61528-161">Válassza a **Létrehozás lehetőséget**.</span><span class="sxs-lookup"><span data-stu-id="61528-161">Select **Create feature**.</span></span>

    ![Új funkció hozzáadása](./media/RCS_GlobalF_9%20Feature%20create%20new.JPG)

4. <span data-ttu-id="61528-163">A **Változatok** lapon válasszon egy **Érvényesség kezdő** dátumát, majd a funkció befejezéséhez válassza az **Állapot módosítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="61528-163">On the **Versions** tab, select an **Effective from** date, and then select **Change status** to complete the feature.</span></span> <span data-ttu-id="61528-164">A teljesített funkciókat egy adott környezet számára elérhetővé teheti, hogy a globalizációs szolgáltatásokban használható legyen, vagy közzétehető legyen a globális tárházban.</span><span class="sxs-lookup"><span data-stu-id="61528-164">Completed features can be made available for a specific environment so that they can be used in Globalization services, or they can be published to the Global repository.</span></span>

> [!NOTE]
> <span data-ttu-id="61528-165">A funkciók, amelyeknél a **Szolgáltatási verzió állapota** értéke **Közzétett**, megoszthatók külső szervezetekkel.</span><span class="sxs-lookup"><span data-stu-id="61528-165">Features that have a **Feature version status** value of **Published** can be shared with external organizations.</span></span>

## <a name="feature-component-overview"></a><span data-ttu-id="61528-166">Funkcióösszetevő áttekintése</span><span class="sxs-lookup"><span data-stu-id="61528-166">Feature component overview</span></span>

<span data-ttu-id="61528-167">A globalizációs szolgáltatások számos összetevővel rendelkeznek:</span><span class="sxs-lookup"><span data-stu-id="61528-167">Globalization features have several components:</span></span>

- <span data-ttu-id="61528-168">**Verzió** – Ez az összetevő támogatja a szolgáltatások életciklusának kezelését, és lehetővé teszi a felhasználók számára a funkció különböző verzióihoz tartozó állapot kezelését.</span><span class="sxs-lookup"><span data-stu-id="61528-168">**Version** – This component supports feature lifecycle management and lets users manage the status for different versions of the feature.</span></span>
- <span data-ttu-id="61528-169">**Konfigurációk** – Ez az összetevő lehetővé teszi a felhasználók számára a kapcsolódó ER-formátumok és formátum-hozzárendelések kezelését, megtekintését és szerkesztését.</span><span class="sxs-lookup"><span data-stu-id="61528-169">**Configurations** – This component lets users manage, view, and edit related ER formats and format mappings.</span></span>
- <span data-ttu-id="61528-170">**Beállítások** – Ez az összetevő lehetővé teszi a globalizációs szolgáltatások – például az e-számlázási szolgáltatások – felhasználóinak a kapcsolódó szolgáltatás verziójának beállításának kezelését.</span><span class="sxs-lookup"><span data-stu-id="61528-170">**Setups** – This component lets users of Globalization services, such as an e-invoicing service, manage the setup of the related feature version.</span></span> <span data-ttu-id="61528-171">Ezért támogatja a kommunikációs és a válaszadási szabályok rugalmas felépítését.</span><span class="sxs-lookup"><span data-stu-id="61528-171">Therefore, it supports the flexible construction of communication and responses rules.</span></span>
- <span data-ttu-id="61528-172">**Környezet** – Ez az összetevő lehetővé teszi a globalizációs szolgáltatások – például az e-számlázási szolgáltatások – felhasználóinak annak a környezetnek a kezelését, ahol a szolgáltatásverzió beállítását használják, és engedélyt adni azoknak a felhasználóknak, akik hozzáférhetnek a rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="61528-172">**Environment** – This component lets users of Globalization services, such as an e-invoicing service, manage the environment where the feature version setup is used and grant authorization to the users who will have access to it.</span></span>
- <span data-ttu-id="61528-173">**Szervezetek** – Ez az összetevő lehetővé teszi a felhasználók számára a funkció külső szervezetekkel való megosztását.</span><span class="sxs-lookup"><span data-stu-id="61528-173">**Organizations** – This component lets users to share the feature with external organizations.</span></span>

## <a name="configuring-feature-components"></a><span data-ttu-id="61528-174">Szolgáltatásösszetevők konfigurálása</span><span class="sxs-lookup"><span data-stu-id="61528-174">Configuring feature components</span></span>

### <a name="version-and-status"></a><span data-ttu-id="61528-175">Állapot és verzió</span><span class="sxs-lookup"><span data-stu-id="61528-175">Version and status</span></span>

<span data-ttu-id="61528-176">A verzió a globalizációs szolgáltatások életciklusának kezelésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="61528-176">The version is used to manage the Globalization feature lifecycle.</span></span>

<span data-ttu-id="61528-177">Az állapot módosítható az **Állapot** mezőjében a **Verzió** lapnak. A következő állapotok érhetők el:</span><span class="sxs-lookup"><span data-stu-id="61528-177">The status can be changed in the **Status** field on the **Version** tab. The following statuses are available:</span></span>

- <span data-ttu-id="61528-178">**Vázlat** – a funkció csak akkor szerkeszthető, ha ebben az állapotban van.</span><span class="sxs-lookup"><span data-stu-id="61528-178">**Draft** – The feature can be edited only when it's in this status.</span></span>
- <span data-ttu-id="61528-179">**Kész** – a funkció és az összes kapcsolódó összetevő véglegesítésre került (kész), és nem szerkeszthető.</span><span class="sxs-lookup"><span data-stu-id="61528-179">**Complete** – The feature and all related components have been finalized (completed) and can't be edited.</span></span>
- <span data-ttu-id="61528-180">**Közzétéve** – a funkció és az összes kapcsolódó összetevő közzé lett téve a globális tárházban.</span><span class="sxs-lookup"><span data-stu-id="61528-180">**Published** – The feature and all related components have been published to the Global repository.</span></span>
- <span data-ttu-id="61528-181">**Megosztott** – a funkció és a kapcsolódó összetevők megosztása megtörtént a külső szervezetekkel.</span><span class="sxs-lookup"><span data-stu-id="61528-181">**Shared** – The feature and all related components have been shared with external organizations.</span></span>
- <span data-ttu-id="61528-182">**Engedélyezve** – a funkció és az összes kapcsolódó összetevő engedélyezve van egy globalizációs szolgáltatásban való használatra, mint például az e-számlázási szolgáltatás.</span><span class="sxs-lookup"><span data-stu-id="61528-182">**Enabled** – The feature and all related components have been enabled for use in a Globalization service, such as an e-invoicing service.</span></span>

> [!NOTE]
> <span data-ttu-id="61528-183">A szolgáltatásoknak egymás után kell mozogni az egyes állapotok között.</span><span class="sxs-lookup"><span data-stu-id="61528-183">Features must move sequentially through some of these statuses.</span></span> <span data-ttu-id="61528-184">Ennélfogva nem minden állapot érhető el minden életciklus-szakaszban.</span><span class="sxs-lookup"><span data-stu-id="61528-184">Therefore, not every status might be available at every lifecycle stage.</span></span>

### <a name="configurations"></a><span data-ttu-id="61528-185">Konfigurációk</span><span class="sxs-lookup"><span data-stu-id="61528-185">Configurations</span></span>

<span data-ttu-id="61528-186">A konfigurációkhoz az alábbi műveletek érhetők el:</span><span class="sxs-lookup"><span data-stu-id="61528-186">The following actions are available for configurations:</span></span>

- <span data-ttu-id="61528-187">**Nézet** – a frissítést nem igénylő alapfunkció-konfigurációk megtekintése.</span><span class="sxs-lookup"><span data-stu-id="61528-187">**View** – View the underlying feature configurations that don't require any update.</span></span>
- <span data-ttu-id="61528-188">**Szerkesztés** – a kiválasztott konfiguráció vázlat verziójának létrehozása, amellyel szerkeszthető a formátum vagy a formátum-hozzárendelés a formátumtervezőben.</span><span class="sxs-lookup"><span data-stu-id="61528-188">**Edit** – Create a draft version of a selected configuration so that you can edit the format or format mapping in the Format designer.</span></span>
- <span data-ttu-id="61528-189">**Törlés** – a funkcióból kiválasztott konfiguráció törlése.</span><span class="sxs-lookup"><span data-stu-id="61528-189">**Delete** – Delete a selected configuration from the feature.</span></span>
- <span data-ttu-id="61528-190">**Új alap** – a funkció új alapra helyezése.</span><span class="sxs-lookup"><span data-stu-id="61528-190">**Rebase** – Rebase the feature.</span></span> <span data-ttu-id="61528-191">További információt a témakör későbbi részében található [Származtatott globalizációs funkciók új alapra helyezése](#rebase) című szakaszban talál.</span><span class="sxs-lookup"><span data-stu-id="61528-191">For more information, see the [Rebase derived Globalization features](#rebase) section later in this topic.</span></span>

### <a name="setups"></a><span data-ttu-id="61528-192">Beállítások</span><span class="sxs-lookup"><span data-stu-id="61528-192">Setups</span></span>

<span data-ttu-id="61528-193">A funkcióbeállításhoz az alábbi műveletek érhetők el:</span><span class="sxs-lookup"><span data-stu-id="61528-193">The following actions are available for feature setups:</span></span>

- <span data-ttu-id="61528-194">**Hozzáadás** – új funkcióbeállítás létrehozása.</span><span class="sxs-lookup"><span data-stu-id="61528-194">**Add** – Create a new feature setup.</span></span> <span data-ttu-id="61528-195">Ez a funkcióbeállítás származtatható egy létező funkcióbeállításból, vagy a nulláról létrehozva.</span><span class="sxs-lookup"><span data-stu-id="61528-195">This feature setup can be derived from an existing feature setup or created from scratch.</span></span>
- <span data-ttu-id="61528-196">**Törlés** – a kiválasztott funkcióbeállítás törlése.</span><span class="sxs-lookup"><span data-stu-id="61528-196">**Delete** – Delete a selected feature setup.</span></span>
- <span data-ttu-id="61528-197">**Nézet** – egy alap funkcióbeállítás megtekintése, amelyekhez nem szükséges változtatás.</span><span class="sxs-lookup"><span data-stu-id="61528-197">**View** – View an underlying feature setup that doesn't require any changes.</span></span>
- <span data-ttu-id="61528-198">**Szerkesztés** – a funkcióbeállítás három fő összetevőjéhez tartozó attribútumok létrehozása, törlése vagy módosítása:</span><span class="sxs-lookup"><span data-stu-id="61528-198">**Edit** – Create, delete, or modify the attributes of the three main components of a feature setup:</span></span>

    - <span data-ttu-id="61528-199">Műveletek és paramétereik</span><span class="sxs-lookup"><span data-stu-id="61528-199">Actions and their parameters</span></span>
    - <span data-ttu-id="61528-200">Alkalmazhatósági szabályok</span><span class="sxs-lookup"><span data-stu-id="61528-200">Applicability rules</span></span>
    - <span data-ttu-id="61528-201">Változók</span><span class="sxs-lookup"><span data-stu-id="61528-201">Variables</span></span>

![Szolgáltatásverzió beállítási lapja](./media/RCS_GlobalF_10%20Feature%20set%20up.JPG)

### <a name="environments"></a><span data-ttu-id="61528-203">Környezetek</span><span class="sxs-lookup"><span data-stu-id="61528-203">Environments</span></span>

<span data-ttu-id="61528-204">A környezetekhez az alábbi műveletek érhetők el:</span><span class="sxs-lookup"><span data-stu-id="61528-204">The following actions are available for environments:</span></span>

- <span data-ttu-id="61528-205">**Engedélyezés** – a kiválasztott szolgáltatási verzió esetében válasszon ki egy közzétett környezetet, és válassza ki a **tényleges kezdő** dátumot, amikor elérhetővé kell tenni.</span><span class="sxs-lookup"><span data-stu-id="61528-205">**Enable** – For a selected feature version, select a published environment, and select an **Effective from** date when it should be available.</span></span> <span data-ttu-id="61528-206">További információt a témakör későbbi részében találhat: [Környezet konfigurálása engedélyezéshez](#configureenvironment) című szakaszban talál.</span><span class="sxs-lookup"><span data-stu-id="61528-206">For more information, see the [Configure environments for enablement](#configureenvironment) section later in this topic.</span></span>
- <span data-ttu-id="61528-207">**Mégse** – környezet eltávolítása a funkció beállításához.</span><span class="sxs-lookup"><span data-stu-id="61528-207">**Cancel** – Remove an environment for a feature setup.</span></span>

### <a name="organizations"></a><span data-ttu-id="61528-208">Szervezetek</span><span class="sxs-lookup"><span data-stu-id="61528-208">Organizations</span></span>

<span data-ttu-id="61528-209">Kövesse az alábbi lépéseket egy globalizációs funkció külső szervezettel történő megosztásához.</span><span class="sxs-lookup"><span data-stu-id="61528-209">Follow these steps to share a Globalization feature with an external organization.</span></span>

1. <span data-ttu-id="61528-210">Az **E-számlázási szolgáltatások** lapon válassza ki a megosztani kívánt funkciót és a funkció-verziószámot.</span><span class="sxs-lookup"><span data-stu-id="61528-210">On the **e-Invoicing features** page, select the feature and the feature version to share.</span></span>
2. <span data-ttu-id="61528-211">Válassza a **Szervezetek** lapon a **Megosztás a következővel** elemet, majd a legördülő párbeszédpanelen írja be a szervezet tartománynevét.</span><span class="sxs-lookup"><span data-stu-id="61528-211">On the **Organizations** tab, select **Share with**, and then, in the drop-down dialog box, enter the organization's domain name.</span></span>
3. <span data-ttu-id="61528-212">Válassza ki a **Megosztás** elemet.</span><span class="sxs-lookup"><span data-stu-id="61528-212">Select **Share**.</span></span>

    ![Szolgáltatás megosztása egy szervezettel](./media/RCS_GlobalF_20%20Feature%20orgn_share%20with.JPG)

<span data-ttu-id="61528-214">A funkció megosztásra kerül a kiválasztott szervezettel, és a szervezet számára elérhető a globális tárban.</span><span class="sxs-lookup"><span data-stu-id="61528-214">The feature is shared with the selected organization and is available for that organization in the Global repository.</span></span> <span data-ttu-id="61528-215">Innen a funkció a szervezet RCS- vagy Dynamics 365 Finance-példányába importálható, hogy használható legyen.</span><span class="sxs-lookup"><span data-stu-id="61528-215">From there, the feature can be imported into the organization's instance of RCS or Dynamics 365 Finance so that it can be used.</span></span>

## <a name="rebase-derived-globalization-features"></a><a name="rebase"></a><span data-ttu-id="61528-216">Származtatott globalizációs funkciók új alapra helyezése</span><span class="sxs-lookup"><span data-stu-id="61528-216">Rebase derived Globalization features</span></span>

<span data-ttu-id="61528-217">A származtatott globalizáció funkció az új vagy a frissített alapszolgáltatási verzióra vezethető át új alapra helyezéssel.</span><span class="sxs-lookup"><span data-stu-id="61528-217">You can rebase a derived Globalization feature to the new or updated base feature version.</span></span> <span data-ttu-id="61528-218">Ily módon az alapverzióban történt módosítások automatikusan frissíthetők.</span><span class="sxs-lookup"><span data-stu-id="61528-218">In this way, changes that have occurred in the base version can be automatically updated.</span></span> <span data-ttu-id="61528-219">A frissített alapverziót a származó konfigurációs szolgáltató hozza létre, és ezt követően közzéteszi vagy megosztja.</span><span class="sxs-lookup"><span data-stu-id="61528-219">The updated base feature version is created by the originating configuration provider, and it's then published or shared.</span></span>

![Frissített alapfunkció-verzió](./media/RCS_GlobalF_12%20Feature%20new%20version.JPG)

<span data-ttu-id="61528-221">Ha például a létrehozott funkció származtatott verzióját szeretné új alapra helyezni, először a szolgáltatás legújabb verzióját kell beolvasnia a globális tárházból.</span><span class="sxs-lookup"><span data-stu-id="61528-221">For example, if you want to rebase the derived version of a feature that you created, you first get the latest version of the feature by importing it from the Global repository.</span></span>

1. <span data-ttu-id="61528-222">Az **E-számlázási szolgáltatások** lapon válassza az **Importálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="61528-222">On the **e-Invoicing features** page, select **Import**.</span></span>
2. <span data-ttu-id="61528-223">A legújabb szolgáltatások beszerzéséhez válassza a **Szinkronizálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="61528-223">Select **Synchronize** to get the latest features.</span></span>
3. <span data-ttu-id="61528-224">Válassza ki az importálni kívánt funkciókat a funkciólistán, majd válassza az **Importálás** elemet.</span><span class="sxs-lookup"><span data-stu-id="61528-224">In the list of features, select the features to import, and then select **Import**.</span></span>

    ![A szolgáltatás legújabb verziójának importálása](./media/RCS_GlobalF_13%20Feature%20new%20version%20import.JPG)

4. <span data-ttu-id="61528-226">A szolgáltatások listájában válassza ki az új alapra helyezendő funkciót.</span><span class="sxs-lookup"><span data-stu-id="61528-226">In the list of features, select the feature to rebase.</span></span>
5. <span data-ttu-id="61528-227">A **Verzió** lapon válassza az **Új** parancsot a vázlat verzió létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="61528-227">On the **Version** tab, select **New** to create a draft version.</span></span>

    ![Új vázlat verzió létrehozva](./media/RCS_GlobalF_14%20Feature%20new%20base%20version.JPG)

6. <span data-ttu-id="61528-229">Válassza az **Új alap** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="61528-229">Select **Rebase**.</span></span>
7. <span data-ttu-id="61528-230">Az **Új alap** párbeszédpanelen válassza ki annak a funkciónak a legfrissebb verzióját, amelybe át szeretné alapozni.</span><span class="sxs-lookup"><span data-stu-id="61528-230">In the **Rebase** dialog box, select the latest version of the feature to rebase to.</span></span>

    ![Új alap párbeszédpanel](./media/RCS_GlobalF_15%20Feature%20rebase%20version.JPG)

8. <span data-ttu-id="61528-232">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="61528-232">Select **OK**.</span></span>
9. <span data-ttu-id="61528-233">Tekintse át a funkció összetevőit, és végezze el a szükséges módosításokat.</span><span class="sxs-lookup"><span data-stu-id="61528-233">Review the feature components, and make any changes that are required.</span></span>
10. <span data-ttu-id="61528-234">Az új alapra helyezett funkció befejezéséhez válassza az **Állapot módosítása** parancsot.</span><span class="sxs-lookup"><span data-stu-id="61528-234">Select **Change status** to complete the rebased feature.</span></span> <span data-ttu-id="61528-235">Az új alapra helyezetés befejezése után további műveleteket is végre lehet hajtani.</span><span class="sxs-lookup"><span data-stu-id="61528-235">When the rebase is completed, you can perform additional actions.</span></span> <span data-ttu-id="61528-236">Közzéteheti például a funkciót, és elérhetővé teheti a globalizációs szolgáltatásokban való használatra.</span><span class="sxs-lookup"><span data-stu-id="61528-236">For example, you can publish the feature and make it available for use in Globalization services.</span></span>

    ![A funkció állapota készre módosult](./media/RCS_GlobalF_16%20Feature%20rebase%20version%20complete.JPG)

## <a name="configure-environments-for-globalization-features"></a><a name="configureenvironment"></a><span data-ttu-id="61528-238">A globalizációs szolgáltatások környezetének konfigurálása</span><span class="sxs-lookup"><span data-stu-id="61528-238">Configure environments for Globalization features</span></span>

<span data-ttu-id="61528-239">A globalizációs szolgáltatásokat használó felhasználók kezelhetik a környezetet a globalizációs funkció beállításához, és engedélyt adhatnak más felhasználóknak, akik hozzáférhetnek a rendszerhez.</span><span class="sxs-lookup"><span data-stu-id="61528-239">Users of Globalization services can manage the environment to set up a Globalization feature and grant authorization to other users who will have access to it.</span></span>

1. <span data-ttu-id="61528-240">Nyissa meg a **Globalizációs szolgáltatások** munkaterületet, majd a **Környezetek** területen válassza az **E-számlázás** mozaikot.</span><span class="sxs-lookup"><span data-stu-id="61528-240">In the **Globalization Features** workspace, under **Environments**, select the **e-Invoicing** tile.</span></span>

    ![Globalizációs szolgáltatások munkaterülete](./media/RCS_GlobalF_17%20Feature%20environment.JPG)

2. <span data-ttu-id="61528-242">Válassza ki a **Kulcstároló paramétereit**, majd az **Új** parancsot választva hozzon létre egy Azure Key Vault-titkot.</span><span class="sxs-lookup"><span data-stu-id="61528-242">Select **Key Vault parameters**, and then select **New** to create an Azure Key Vault secret.</span></span>
3. <span data-ttu-id="61528-243">Írjon be egy nevet és egy leírást a kulcstárolóhoz, majd a **Kulcstároló-URI** mezőbe írja be azt az URL-címet, amely azonosítja a kulcstároló erőforrást az Azure megoldásban.</span><span class="sxs-lookup"><span data-stu-id="61528-243">Enter a name and description for the key vault, and then, in the **Key Vault URI** field, enter the URL that identifies the Key Vault resource in Azure.</span></span>
4. <span data-ttu-id="61528-244">A **Tanúsítványok** gyorslapon válassza a **Hozzáadás** lehetőséget a tanúsítvány hozzáadásához, majd adja meg az egyes tanúsítványok nevét és leírását.</span><span class="sxs-lookup"><span data-stu-id="61528-244">On the **Certificates** FastTab, select **Add** to add the certificate, and enter a name and description for each certificate.</span></span>

    ![Tanúsítvány hozzáadva](./media/RCS_GlobalF_18%20Feature%20envn%20key%20vault%20parameter.JPG)

5. <span data-ttu-id="61528-246">Válassza ki az **Új** lehetőséget egy új környezet létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="61528-246">Select **New** to create a new environment.</span></span>
6. <span data-ttu-id="61528-247">Írjon be egy nevet, egy leírást, valamint a tároláshoz szükséges megosztott hozzáférési aláírás token titkát.</span><span class="sxs-lookup"><span data-stu-id="61528-247">Enter a name, a description, and the shared access signature token secret required for the storage.</span></span>
7. <span data-ttu-id="61528-248">A **Felhasználók** gyorslapon válassza az **Új** lehetőséget, ha a környezethez hozzáférési jogosultsággal rendelkező felhasználó szeretne hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="61528-248">On the **Users** FastTab, select **New** to add a user who will have permission to access this environment.</span></span>
8. <span data-ttu-id="61528-249">Adja meg a felhasználó felhasználói azonosítóját és e-mail-címét.</span><span class="sxs-lookup"><span data-stu-id="61528-249">Enter the user's user ID and email address.</span></span>
9. <span data-ttu-id="61528-250">További felhasználók hozzáadásához ismételje meg a 7. és 8. lépést.</span><span class="sxs-lookup"><span data-stu-id="61528-250">Repeat steps 7 and 8 to add more users.</span></span>
10. <span data-ttu-id="61528-251">A környezet közzétételéhez válassza a **Közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="61528-251">Select **Publish** to publish the environment.</span></span>

    ![Közzétett környezet](./media/RCS_GlobalF_19%20Feature%20envn%20publishing.JPG)
