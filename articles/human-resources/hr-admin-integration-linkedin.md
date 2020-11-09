---
title: Integráció a LinkedIn Talent Hub szolgáltatással
description: Ez a témakör bemutatja, hogyan lehet beállítani a Microsoft Dynamics 365 Human Resources és a LinkedIn Talent Hub közötti integrációt.
author: jaredha
manager: tfehr
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e82b79858060f31a6310cc5abdb2faf87db2d6c2
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2020
ms.locfileid: "4056097"
---
# <a name="integrate-with-linkedin-talent-hub"></a><span data-ttu-id="97c36-103">Integráció a LinkedIn Talent Hub szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="97c36-103">Integrate with LinkedIn Talent Hub</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="97c36-104">A [LinkedIn Talent hub](https://business.linkedin.com/talent-solutions/talent-hub) egy pályázókövetési rendszer (applicant tracking system, ATS) platform.</span><span class="sxs-lookup"><span data-stu-id="97c36-104">[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) is an applicant tracking system (ATS) platform.</span></span> <span data-ttu-id="97c36-105">Ez lehetővé teszi a munkaerő sourcingját, kezelését és alkalmazását egyetlen helyen.</span><span class="sxs-lookup"><span data-stu-id="97c36-105">It lets you source, manage, and hire employees all in one place.</span></span> <span data-ttu-id="97c36-106">A Microsoft Dynamics 365 Human Resources és a LinkedIn Talent hub integrálásával könnyedén létrehozhat alkalmazotti rekordokat a Human Resources alkalmazásban azok számára, akiket felvettek valamilyen beosztásra.</span><span class="sxs-lookup"><span data-stu-id="97c36-106">By integrating Microsoft Dynamics 365 Human Resources with LinkedIn Talent Hub, you can easily create employee records in Human Resources for applicants who have been hired for a position.</span></span>

## <a name="setup"></a><span data-ttu-id="97c36-107">Beállítás</span><span class="sxs-lookup"><span data-stu-id="97c36-107">Setup</span></span>

<span data-ttu-id="97c36-108">A rendszergazdának be kell fejeznie a beállítási feladatokat, hogy engedélyezze a LinkedIn Talent hub integrációját.</span><span class="sxs-lookup"><span data-stu-id="97c36-108">A system administrator must complete setup tasks to enable integration with LinkedIn Talent Hub.</span></span> <span data-ttu-id="97c36-109">Először a Power Apps környezetben be kell állítania egy felhasználót és egy biztonsági szerepkört, amely megadja a LinkedIn Talent Hub számára a szükséges engedélyeket az adatok Human Resources alklamazásba történő írására.</span><span class="sxs-lookup"><span data-stu-id="97c36-109">First, in the Power Apps environment, you must set up a user and security role to grant LinkedIn Talent Hub the appropriate permissions to write data into Human Resources.</span></span>

### <a name="link-your-environment-to-linkedin-talent-hub"></a><span data-ttu-id="97c36-110">A környezete csatolása a LinkedIn Talent Hub alkalmazáshoz</span><span class="sxs-lookup"><span data-stu-id="97c36-110">Link your environment to LinkedIn Talent Hub</span></span>

1. <span data-ttu-id="97c36-111">Nyissa meg a [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="97c36-111">Open [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub).</span></span>

2. <span data-ttu-id="97c36-112">A felhasználói legördülő menüben válassza a **Termék beállításai** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c36-112">On the user drop-down menu, select **Product Settings**.</span></span>

3. <span data-ttu-id="97c36-113">A bal oldali navigációs ablak **Speciális** szakaszában válassza az **Integrációk** elemet.</span><span class="sxs-lookup"><span data-stu-id="97c36-113">In the left navigation pane, in the **Advanced** section, select **Integrations**.</span></span>

4. <span data-ttu-id="97c36-114">Jelölje be az **Engedélyezés** jelölőnégyzetet a Microsoft Dynamics 365 Human Resources integrációjához.</span><span class="sxs-lookup"><span data-stu-id="97c36-114">Select **Authorize** for the Microsoft Dynamics 365 Human Resources integration.</span></span>

5. <span data-ttu-id="97c36-115">A **Dynamics 365 Human Resources** lapon válassza ki a LinkedIn Talent Hub elemhez kapcsolandó környezetet, majd válassza a **Csatolás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c36-115">On the **Dynamics 365 Human Resources** page, select the environment to link LinkedIn Talent Hub to, and then select **Link**.</span></span>

    ![LinkedIn Talent Hub előkészítés](./media/hr-admin-integration-talent-hub-onboarding.jpg)

    > [!NOTE]
    > <span data-ttu-id="97c36-117">Csak olyan környezetekhez kapcsolódhat, amelyeknél a felhasználói fiók rendszergazdája hozzáférhet mind a Human Resources környezethez, mind a társított Power Apps-környezethez.</span><span class="sxs-lookup"><span data-stu-id="97c36-117">You can link only to environments where your user account has administrator access to both the Human Resources environment and the associated Power Apps environment.</span></span> <span data-ttu-id="97c36-118">Ha a Human Resources hivatkozáslapján nem szerepelnek környezetek, győződjön meg arról, hogy a bérlőn engedélyezve legyen a Human Resources környezet, valamint azt, hogy a hivatkozás lapra bejelentkezett felhasználó rendelkezzen rendszergazdai jogosultsággal mind a Human Resources környezethez, mind a Power Apps-környezethez.</span><span class="sxs-lookup"><span data-stu-id="97c36-118">If no environments are listed on the Human Resources link page, make sure that you have licensed Human Resources environments on the tenant, and that the user that you signed in to the link page as has administrator permissions to both the Human Resources environment and the Power Apps environment.</span></span>

### <a name="create-a-power-apps-security-role"></a><span data-ttu-id="97c36-119">Power Apps biztonsági szerepkör létrehozása</span><span class="sxs-lookup"><span data-stu-id="97c36-119">Create a Power Apps security role</span></span>

1. <span data-ttu-id="97c36-120">Nyissa meg a [Power Platform felügyeleti központot](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="97c36-120">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="97c36-121">A **Környezetek** listából válassza ki a LinkedIn Talent Hub példányához csatolni kívánt, a Human Resources környezettel társított környezetet.</span><span class="sxs-lookup"><span data-stu-id="97c36-121">In the **Environments** list, select the environment that is associated with the Human Resources environment that you want to link your instance of LinkedIn Talent Hub to.</span></span>

3. <span data-ttu-id="97c36-122">Válassza a **Beállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c36-122">Select **Settings**.</span></span>

4. <span data-ttu-id="97c36-123">Bontsa ki a **Felhasználók + engedélyek** csomópontot, és válassza a **Biztonsági szerepkörök** elemet.</span><span class="sxs-lookup"><span data-stu-id="97c36-123">Expand the **Users + Permissions** node, and select **Security Roles**.</span></span>

5. <span data-ttu-id="97c36-124">A **Biztonsági szerepkörök** lap eszköztárán válassza az **Új szerepkör** elemet.</span><span class="sxs-lookup"><span data-stu-id="97c36-124">On the **Security Roles** page, on the toolbar, select **New role**.</span></span>

6. <span data-ttu-id="97c36-125">A **Részletek** lapon adja meg a szerepkör nevét, például **LinkedIn Talent Hub HRIS Integráció**.</span><span class="sxs-lookup"><span data-stu-id="97c36-125">On the **Details** tab, enter a name for the role, such as **LinkedIn Talent Hub HRIS Integration**.</span></span>

7. <span data-ttu-id="97c36-126">A **Testreszabás** lapon válassza ki a szervezetszintű **Olvasási** engedélyt az alábbi entitásokhoz:</span><span class="sxs-lookup"><span data-stu-id="97c36-126">On the **Customization** tab, select organization-level **Read** permission for the following entities:</span></span>

    - <span data-ttu-id="97c36-127">Entitás</span><span class="sxs-lookup"><span data-stu-id="97c36-127">Entity</span></span>
    - <span data-ttu-id="97c36-128">Mező</span><span class="sxs-lookup"><span data-stu-id="97c36-128">Field</span></span>
    - <span data-ttu-id="97c36-129">Kapcsolat</span><span class="sxs-lookup"><span data-stu-id="97c36-129">Relationship</span></span>

8. <span data-ttu-id="97c36-130">Mentse el és zárja be a biztonsági szerepkört.</span><span class="sxs-lookup"><span data-stu-id="97c36-130">Save and close the security role.</span></span>

### <a name="create-a-power-apps-application-user"></a><span data-ttu-id="97c36-131">Power Apps-alkalmazásfelhasználó létrehozása</span><span class="sxs-lookup"><span data-stu-id="97c36-131">Create a Power Apps application user</span></span>

<span data-ttu-id="97c36-132">Létre kell hozni egy alkalmazásfelhasználót a LinkedIn Talent Hub adapterhez, aki jogosultságokat biztosít annak, hogy az adapter beírhassa a jelöltrekordokat a Power Apps-környezetbe.</span><span class="sxs-lookup"><span data-stu-id="97c36-132">An application user must be created for the LinkedIn Talent Hub adapter to grant permissions to the adapter to write candidate records into the Power Apps environment.</span></span>

1. <span data-ttu-id="97c36-133">Nyissa meg a [Power Platform felügyeleti központot](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="97c36-133">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="97c36-134">A **Környezetek** listából válassza ki a LinkedIn Talent Hub példányához csatolni kívánt, a Human Resources környezettel társított környezetet.</span><span class="sxs-lookup"><span data-stu-id="97c36-134">In the **Environments** list, select the environment that is associated with the Human Resources environment that you want to link your instance of LinkedIn Talent Hub to.</span></span>

3. <span data-ttu-id="97c36-135">Válassza a **Beállítások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c36-135">Select **Settings**.</span></span>

4. <span data-ttu-id="97c36-136">Bontsa ki a **Felhasználók + engedélyek** csomópontot, és válassza a **Felhasználók** elemet.</span><span class="sxs-lookup"><span data-stu-id="97c36-136">Expand the **Users + Permissions** node, and select **Users**.</span></span>

5. <span data-ttu-id="97c36-137">Jelölje ki a **Felhasználók kezelése a Dynamics 365 rendszerben** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c36-137">Select **Manage users in Dynamics 365**.</span></span>

6. <span data-ttu-id="97c36-138">A lista fölötti legördülő menü segítségével módosítsa az alapértelmezett **Engedélyezett felhasználók** nézetet erre: **Alkalmazásfelhasználók**.</span><span class="sxs-lookup"><span data-stu-id="97c36-138">Use the drop-down menu above the list to change the view from the default **Enabled Users** view to **Application Users**.</span></span>

    ![Alkalmazásfelhasználók nézet](./media/hr-admin-integration-power-apps-application-users.jpg)

7. <span data-ttu-id="97c36-140">Válassza ki az eszköztár **Új** gombját.</span><span class="sxs-lookup"><span data-stu-id="97c36-140">On the toolbar, select **New**.</span></span>

8. <span data-ttu-id="97c36-141">Az **Új felhasználó** oldalon kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="97c36-141">On the **New user** page, follow these steps:</span></span>

    1. <span data-ttu-id="97c36-142">Módosítsa a **Felhasználótípus** mező értékét erre: **Alkalmazásfelhasználó**.</span><span class="sxs-lookup"><span data-stu-id="97c36-142">Change the value of the **User type** field to **Application User**.</span></span>
    2. <span data-ttu-id="97c36-143">A **Felhasználónév** mező értékét erre: **Dynamics365 HR LinkedIn HRIS-integráció**.</span><span class="sxs-lookup"><span data-stu-id="97c36-143">Set the **User Name** field to **Dynamics365 HR LinkedIn HRIS Integration**.</span></span>
    3. <span data-ttu-id="97c36-144">Állítsa az **Alkalmazásazonosító** mező értékét erre: **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span><span class="sxs-lookup"><span data-stu-id="97c36-144">Set the **Application ID** field to **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span></span>
    4. <span data-ttu-id="97c36-145">Írjon be bármilyen értéket az **Utónév** , **Családnév** és **Elsődleges e-mail-cím** mezőkbe.</span><span class="sxs-lookup"><span data-stu-id="97c36-145">Enter any value in the **First Name** , **Last Name** , and **Primary Email** fields.</span></span>
    5. <span data-ttu-id="97c36-146">Kattintson az eszköztár **Mentés \& Bezárás** gombjára.</span><span class="sxs-lookup"><span data-stu-id="97c36-146">On the toolbar, select **Save \& Close**.</span></span>

### <a name="assign-a-security-role-to-the-new-user"></a><span data-ttu-id="97c36-147">Biztonsági szerepkör hozzárendelése az új felhasználóhoz</span><span class="sxs-lookup"><span data-stu-id="97c36-147">Assign a security role to the new user</span></span>

<span data-ttu-id="97c36-148">Miután elmentette és bezárta az új alkalmazásfelhasználót az előző szakaszban, a program visszaviszi a **Felhasználólista** lapra.</span><span class="sxs-lookup"><span data-stu-id="97c36-148">After you save and close the new application user in the previous section, you're returned to the **Users list** page.</span></span>

1. <span data-ttu-id="97c36-149">A **Felhasználólista** lapon módosítsa a nézetet erre: **Alkalmazásfelhasználók**.</span><span class="sxs-lookup"><span data-stu-id="97c36-149">On the **Users list** page, change the view to **Application Users**.</span></span>

2. <span data-ttu-id="97c36-150">Válassza ki az előző szakaszban létrehozott alkalmazásfelhasználót.</span><span class="sxs-lookup"><span data-stu-id="97c36-150">Select the application user that you created in the previous section.</span></span>

3. <span data-ttu-id="97c36-151">Válassza ki az eszköztár **Szerepkörök kezelése** elemét.</span><span class="sxs-lookup"><span data-stu-id="97c36-151">On the toolbar, select **Manage Roles**.</span></span>

4. <span data-ttu-id="97c36-152">Válassza ki az integráció céljára korábban létrehozott biztonsági szerepkört.</span><span class="sxs-lookup"><span data-stu-id="97c36-152">Select the security role that you created earlier for the integration.</span></span>

5. <span data-ttu-id="97c36-153">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c36-153">Select **OK**.</span></span>

### <a name="add-an-azure-active-directory-app-in-human-resources"></a><span data-ttu-id="97c36-154">Adjon hozzá egy Azure Active Directory-alkalmazást a Human Resources alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="97c36-154">Add an Azure Active Directory app in Human Resources</span></span>

1. <span data-ttu-id="97c36-155">A Dynamics 365 Human Resources alkalmazásban nyissa meg az **Azure Active Directory-alkalmazások** oldalt.</span><span class="sxs-lookup"><span data-stu-id="97c36-155">In Dynamics 365 Human Resources, open the **Azure Active Directory applications** page.</span></span>
2. <span data-ttu-id="97c36-156">Adjon hozzá egy új rekordot a listához és állítsa be a következő mezőket:</span><span class="sxs-lookup"><span data-stu-id="97c36-156">Add a new record to the list, and set the following fields:</span></span>

    - <span data-ttu-id="97c36-157">**Ügyfélazonosító** : adja meg az alábbit: **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span><span class="sxs-lookup"><span data-stu-id="97c36-157">**Client ID** : Enter **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span></span>
    - <span data-ttu-id="97c36-158">**Név** : adja meg a korábban létrehozott Power Apps biztonsági szerepkör nevét, például **LinkedIn Talent Hub HRIS Integráció**.</span><span class="sxs-lookup"><span data-stu-id="97c36-158">**Name** : Enter the name of the Power Apps security role that you created earlier, such as **LinkedIn Talent Hub HRIS Integration**.</span></span>
    - <span data-ttu-id="97c36-159">**Felhasználói azonosító** : válassza ki azt a felhasználót, akinek van engedélye a Személyzet kezelése szakasz adatainak írására.</span><span class="sxs-lookup"><span data-stu-id="97c36-159">**User ID** : Select a user who has permissions to write data in Personnel Management.</span></span>

### <a name="create-the-entity-in-common-data-service"></a><span data-ttu-id="97c36-160">Entitás létrehozása a Common Data Service szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="97c36-160">Create the entity in Common Data Service</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97c36-161">A LinkedIn Talent Hub integrációja a Common Data Service Human Resources számára létrehozott virtuális entitásaitól függ.</span><span class="sxs-lookup"><span data-stu-id="97c36-161">The integration with LinkedIn Talent Hub depends on virtual entities in Common Data Service for Human Resources.</span></span> <span data-ttu-id="97c36-162">A beállítás előfeltétele, a virtuális entitásokat beállítása.</span><span class="sxs-lookup"><span data-stu-id="97c36-162">As a prerequisite for this step in the setup, you must configure virtual entities.</span></span> <span data-ttu-id="97c36-163">A virtuális entitások konfigurálásával kapcsolatos tudnivalókért lásd: [Common Data Service virtuális entitások](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span><span class="sxs-lookup"><span data-stu-id="97c36-163">For information about how to configure virtual entities, see [Configure Common Data Service virtual entities](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span></span>

1. <span data-ttu-id="97c36-164">A HR-modulban nyissa meg a **Common Data Service (CDS) integrációja** oldalt.</span><span class="sxs-lookup"><span data-stu-id="97c36-164">In Human Resources, open the **Common Data Service (CDS) integration** page.</span></span>

2. <span data-ttu-id="97c36-165">Válassza ki a **Virtuális entitások** lapot.</span><span class="sxs-lookup"><span data-stu-id="97c36-165">Select the **Virtual entities** tab.</span></span>

3. <span data-ttu-id="97c36-166">Az entitáslistájár zűrje az entitások címkéi szerint, hogy megtalálja a **LinkedIn exportált pályázóit**.</span><span class="sxs-lookup"><span data-stu-id="97c36-166">Filter the entity list by entity label to find **LinkedIn exported candidate**.</span></span>

4. <span data-ttu-id="97c36-167">Válassza ki a jogi személyt, majd kattintson a **Létrehozás/frissítés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="97c36-167">Select the entity, and then select **Generate/refresh**.</span></span>

## <a name="exporting-candidate-records"></a><span data-ttu-id="97c36-168">Jelöltrekordok exportálása</span><span class="sxs-lookup"><span data-stu-id="97c36-168">Exporting candidate records</span></span>

<span data-ttu-id="97c36-169">A telepítés befejezése után a toborzók és az Emberi erőforrások (HR) szakemberei a LinkedIn Talent hub **Exportálás a HRIS-be** funkcióját használhatják a LinkedIn Talent Hub programból a Human Resources felé átadott jelöltrekordok exportálására.</span><span class="sxs-lookup"><span data-stu-id="97c36-169">After the setup is completed, recruiters and Human resources (HR) professionals can use the **Export to HRIS** function in LinkedIn Talent Hub to export hired candidate records from LinkedIn Talent Hub to Human Resources.</span></span>

### <a name="export-records-from-linkedin-talent-hub"></a><span data-ttu-id="97c36-170">Rekordok exportálása a LinkedIn Talent Hub alkalmazásból</span><span class="sxs-lookup"><span data-stu-id="97c36-170">Export records from LinkedIn Talent Hub</span></span>

<span data-ttu-id="97c36-171">Miután a pályázó végigment a toborzási folyamaton, és már felvették, exportálhatja a LinkedIn Talent Hub alkalmazásból a Human Resources rendszerbe a pályázó rekordját.</span><span class="sxs-lookup"><span data-stu-id="97c36-171">After a candidate has moved through the recruiting process and has been hired, you can export the candidate record from LinkedIn Talent Hub to Human Resources.</span></span>

1. <span data-ttu-id="97c36-172">A LinkedIn Talent Hub alkalmazásban nyissa meg azt a projektet, amelyhez az új alkalmazottat felvette.</span><span class="sxs-lookup"><span data-stu-id="97c36-172">In LinkedIn Talent Hub, open the project that you hired the new employee for.</span></span>

2. <span data-ttu-id="97c36-173">Válasszon ki egy jelöltrekordot.</span><span class="sxs-lookup"><span data-stu-id="97c36-173">Select a candidate record.</span></span>

3. <span data-ttu-id="97c36-174">Válassza ki a **Szakasz módosítása** elemet, majd kattintson a **Felvéve** gombra.</span><span class="sxs-lookup"><span data-stu-id="97c36-174">Select **Change stage** , and then select **Hired**.</span></span>

4. <span data-ttu-id="97c36-175">A pályázó három ponttal ( **...** ) jelölt menüpontjában válassza az **Exportálás a HRIS-be** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c36-175">On the ellipsis menu ( **...** ) for the candidate, select **Export to HRIS**.</span></span>

5. <span data-ttu-id="97c36-176">Az **Exportálás a HRIS-be** ablaktáblában adja meg a exportálandó adatokat:</span><span class="sxs-lookup"><span data-stu-id="97c36-176">In the **Export to HRIS** pane, enter the information that must be exported:</span></span>

    - <span data-ttu-id="97c36-177">A **HRIS-szolgáltató** mezőben válassza a **Microsoft Dynamics 365 Human Resources** elemet.</span><span class="sxs-lookup"><span data-stu-id="97c36-177">In the **HRIS provider** field, select **Microsoft Dynamics 365 Human Resources**.</span></span>
    - <span data-ttu-id="97c36-178">A **Kezdő dátum** mezőben válasszon egy értéket az új alkalmazott számára.</span><span class="sxs-lookup"><span data-stu-id="97c36-178">In the **Start date** field, select a value for the new employee.</span></span>
    - <span data-ttu-id="97c36-179">A **Beosztás** mezőbe írja be az új alkalmazott feladatköréhez tartozó beosztást.</span><span class="sxs-lookup"><span data-stu-id="97c36-179">In the **Job title** field, enter a job title for the new employee's job.</span></span>
    - <span data-ttu-id="97c36-180">A **Telephely** mezőbe írja be azt a telephelyet, ahol az alkalmazott alapvetően dolgozni fog.</span><span class="sxs-lookup"><span data-stu-id="97c36-180">In the **Location** field, enter the location where the employee will be based.</span></span>
    - <span data-ttu-id="97c36-181">Adja meg vagy ellenőrizze az alkalmazott e-mail-címét.</span><span class="sxs-lookup"><span data-stu-id="97c36-181">Enter or verify the employee's email address.</span></span>

![Exportálás a HRIS-be ablaktábla a LinkedIn Talent hub alkalmazásban](./media/hr-admin-integration-linkedin-talent-hub-export.jpg)

## <a name="complete-onboarding-in-human-resources"></a><span data-ttu-id="97c36-183">Előkészítés befejezése a Human Resources alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="97c36-183">Complete onboarding in Human Resources</span></span>

<span data-ttu-id="97c36-184">A LinkedIn Talent Hub alkalmazásból a Human Resources felé exportálandó jelöltrekordok a **Személyzet kezelése** oldal **Foglalkoztatható jelöltek** szakaszában találhatók.</span><span class="sxs-lookup"><span data-stu-id="97c36-184">Candidate records that are exported from LinkedIn Talent Hub to Human Resources appear in the **Candidates to hire** section of the **Personnel management** page.</span></span>

1. <span data-ttu-id="97c36-185">A Human Resources alkalmazásban nyissa meg **Személyzet kezelése** lapot.</span><span class="sxs-lookup"><span data-stu-id="97c36-185">In Human Resources, open the **Personnel management** page.</span></span>

2. <span data-ttu-id="97c36-186">A **Foglalkoztatható jelöltek** szakaszban a kiválasztott pályázó esetén válassza a **Felvétel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="97c36-186">In the **Candidates to hire** section, select **Hire** for the selected candidate.</span></span>

3. <span data-ttu-id="97c36-187">Az **Új dolgozó felvétele** párbeszédpanelen ellenőrizze a rekordot, és adja meg a szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="97c36-187">In the **Hire new worker** dialog box, review the record, and add any required information.</span></span> <span data-ttu-id="97c36-188">Kiválaszthatja azt a beosztást is, amelyre a pályázót már felvette.</span><span class="sxs-lookup"><span data-stu-id="97c36-188">You can also select the position number that the candidate has been hired for.</span></span>

<span data-ttu-id="97c36-189">Miután megtörtént a szükséges információk megadása, folytathatja az alkalmazottak rekordjainak és szokásos folyamatainak létrehozását, illetve az alkalmazottak előkészítését.</span><span class="sxs-lookup"><span data-stu-id="97c36-189">After the required information has been entered, you can continue with your standard processes for creating employee records and onboarding employees.</span></span>

<span data-ttu-id="97c36-190">A program az alábbi adatokat importálja és viszi fel az új alkalmazotti rekordba:</span><span class="sxs-lookup"><span data-stu-id="97c36-190">The following details are imported and included on the new employee record:</span></span>

- <span data-ttu-id="97c36-191">Keresztnév</span><span class="sxs-lookup"><span data-stu-id="97c36-191">First name</span></span>
- <span data-ttu-id="97c36-192">Vezetéknév</span><span class="sxs-lookup"><span data-stu-id="97c36-192">Last name</span></span>
- <span data-ttu-id="97c36-193">Foglalkoztatás kezdő dátuma</span><span class="sxs-lookup"><span data-stu-id="97c36-193">Employment start date</span></span>
- <span data-ttu-id="97c36-194">E-mail cím</span><span class="sxs-lookup"><span data-stu-id="97c36-194">Email address</span></span>
- <span data-ttu-id="97c36-195">Telefonszám</span><span class="sxs-lookup"><span data-stu-id="97c36-195">Phone number</span></span>

## <a name="see-also"></a><span data-ttu-id="97c36-196">Lásd még</span><span class="sxs-lookup"><span data-stu-id="97c36-196">See also</span></span>

[<span data-ttu-id="97c36-197">Common Data Service-virtuális entitások konfigurálása</span><span class="sxs-lookup"><span data-stu-id="97c36-197">Configure Common Data Service virtual entities</span></span>](./hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="97c36-198">Mi az a Common Data Service?</span><span class="sxs-lookup"><span data-stu-id="97c36-198">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)