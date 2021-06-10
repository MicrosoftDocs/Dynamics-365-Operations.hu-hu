---
title: Példány másolása
description: A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatással átmásolhat egy Microsoft Dynamics 365 Human Resources-adatbázist egy védőfalkörnyezetbe.
author: andreabichsel
ms.date: 07/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8961b7156f52e48dbfcf7efb14e50316e81fcfff
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053683"
---
# <a name="copy-an-instance"></a><span data-ttu-id="afa58-103">Példány másolása</span><span class="sxs-lookup"><span data-stu-id="afa58-103">Copy an instance</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="afa58-104">A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatással átmásolhat egy Microsoft Dynamics 365 Human Resources-adatbázist egy védőfalkörnyezetbe.</span><span class="sxs-lookup"><span data-stu-id="afa58-104">You can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Human Resources database to a sandbox environment.</span></span> <span data-ttu-id="afa58-105">Ha van másik tesztkörnyezete, akkor abból a környezetből is másolható az adatbázis a célként kiválasztott tesztkörnyezetbe.</span><span class="sxs-lookup"><span data-stu-id="afa58-105">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span>

<span data-ttu-id="afa58-106">Egy példány másolásához tartsa szem előtt a következő tanácsokat:</span><span class="sxs-lookup"><span data-stu-id="afa58-106">To copy an instance, keep the following tips in mind:</span></span>

- <span data-ttu-id="afa58-107">A felülírni kívánt Human Resources példánynak védőfalkörnyezetnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="afa58-107">The Human Resources instance you want to overwrite must be a sandbox environment.</span></span>

- <span data-ttu-id="afa58-108">A környezeteknek, ahonnan és ahová másolni kíván, ugyanabban a régióban kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="afa58-108">The environments you're copying from and to must be in the same region.</span></span> <span data-ttu-id="afa58-109">Nem másolhat régiók között.</span><span class="sxs-lookup"><span data-stu-id="afa58-109">You can't copy across regions.</span></span>

- <span data-ttu-id="afa58-110">A célkörnyezetben rendszergazdának kell lennie ahhoz, hogy a példány másolása után bejelentkezhessen.</span><span class="sxs-lookup"><span data-stu-id="afa58-110">You must be an Administrator in the target environment so you can sign into it after copying the instance.</span></span>

- <span data-ttu-id="afa58-111">A Human Resources adatbázisának másolása során nem másolja át a Microsoft Power Apps környezetben található elemeket (alkalmazásokat vagy adatokat).</span><span class="sxs-lookup"><span data-stu-id="afa58-111">When you copy the Human Resources database, you don't copy the elements (apps or data) that are contained in a Microsoft Power Apps environment.</span></span> <span data-ttu-id="afa58-112">A Power Apps-környezet elemeinek másolásával kapcsolatos tudnivalókat lásd: [Környezet másolása](/power-platform/admin/copy-environment).</span><span class="sxs-lookup"><span data-stu-id="afa58-112">For information about how to copy elements in a Power Apps environment, see [Copy an environment](/power-platform/admin/copy-environment).</span></span> <span data-ttu-id="afa58-113">A felülírni kívánt Power Apps -könyezetnek védőfalkörnyezetnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="afa58-113">The Power Apps environment you want to overwrite must be a sandbox environment.</span></span> <span data-ttu-id="afa58-114">A Power Apps éles környezet védőfalkörnyezetbe történő módosításához globális bérlői rendszergazdának kell lennie.</span><span class="sxs-lookup"><span data-stu-id="afa58-114">You must be a global tenant admin to change a Power Apps production environment to a sandbox environment.</span></span> <span data-ttu-id="afa58-115">A Power Apps-környezet módosításával kapcsolatos további tudnivalókat lásd: [Példány váltása](/dynamics365/admin/switch-instance).</span><span class="sxs-lookup"><span data-stu-id="afa58-115">For more information about changing a Power Apps environment, see [Switch an instance](/dynamics365/admin/switch-instance).</span></span>

- <span data-ttu-id="afa58-116">Ha példányát egy tesztkörnyezetbe másolja , és szeretné integrálni a tesztkörnyezetét a Dataverse szolgáltatással, akkor újra kell alkalmaznia az egyéni mezőket a Dataverse-táblákra.</span><span class="sxs-lookup"><span data-stu-id="afa58-116">If you copy an instance into your sandbox environment and want to integrate your sandbox environment with Dataverse, you must reapply custom fields to Dataverse tables.</span></span> <span data-ttu-id="afa58-117">Lásd: [Egyéni mezők alkalmazása a Dataverse-szolgáltatásra](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).</span><span class="sxs-lookup"><span data-stu-id="afa58-117">See [Apply custom fields to Dataverse](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).</span></span>

## <a name="effects-of-copying-a-human-resources-database"></a><span data-ttu-id="afa58-118">A Human Resources-adatbázis másolásának hatásai</span><span class="sxs-lookup"><span data-stu-id="afa58-118">Effects of copying a Human Resources database</span></span>

<span data-ttu-id="afa58-119">A Human Resources-adatbázis másolásakor a következő események történnek:</span><span class="sxs-lookup"><span data-stu-id="afa58-119">The following events occur when you copy a Human Resources database:</span></span>

- <span data-ttu-id="afa58-120">A másolási folyamat törli a meglévő adatbázist a célkörnyezetből.</span><span class="sxs-lookup"><span data-stu-id="afa58-120">The copy process erases the existing database in the target environment.</span></span> <span data-ttu-id="afa58-121">A másolási folyamat befejezése után nem lehet visszaállítani a meglévő adatbázist.</span><span class="sxs-lookup"><span data-stu-id="afa58-121">After the copy process is completed, you can't recover the existing database.</span></span>

- <span data-ttu-id="afa58-122">A célkörnyezet addig nem lesz elérhető, amíg a másolási folyamat be nem fejeződik.</span><span class="sxs-lookup"><span data-stu-id="afa58-122">The target environment will be unavailable until the copy process is completed.</span></span>

- <span data-ttu-id="afa58-123">A Microsoft Azure Blob-tárolóban lévő dokumentumok nem kerülnek át egyik környezetből a másikba.</span><span class="sxs-lookup"><span data-stu-id="afa58-123">Documents in Microsoft Azure Blob storage aren't copied from one environment to another.</span></span> <span data-ttu-id="afa58-124">Ennek megfelelően a rendszer nem másolja a csatolt dokumentumokat és sablonokat, és a forráskörnyezetben maradnak.</span><span class="sxs-lookup"><span data-stu-id="afa58-124">As a result, any documents and templates that are attached won't be copied and will remain in the source environment.</span></span>

- <span data-ttu-id="afa58-125">Az összes felhasználó elérhetetlen lesz a rendszergazdai felhasználó és az egyéb belső szolgáltatási felhasználói fiókok kivételével.</span><span class="sxs-lookup"><span data-stu-id="afa58-125">All users except the Admin user and other internal service user accounts will be unavailable.</span></span> <span data-ttu-id="afa58-126">A Rendszergazda felhasználó törölheti vagy álcázhatja az adatokat, mielőtt a többi felhasználó visszakerül a rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="afa58-126">The Admin user can delete or obfuscate data before other users are allowed back into the system.</span></span>

- <span data-ttu-id="afa58-127">A Rendszergazda felhasználónak végre kell hajtania a szükséges konfigurációs változtatásokat, például az integrációs végpontok újracsatlakoztatását meghatározott szolgáltatásokhoz vagy URL-címekhez.</span><span class="sxs-lookup"><span data-stu-id="afa58-127">The Admin user must make required configuration changes, such as reconnecting integration endpoints to specific services or URLs.</span></span>

## <a name="copy-the-human-resources-database"></a><span data-ttu-id="afa58-128">Human Resources-adatbázis másolása</span><span class="sxs-lookup"><span data-stu-id="afa58-128">Copy the Human Resources database</span></span>

<span data-ttu-id="afa58-129">A feladat végrehajtásához először másolja a példányt, majd jelentkezzen be a Microsoft Power Platform Admin Center programba a Power Apps-környezet másolásához.</span><span class="sxs-lookup"><span data-stu-id="afa58-129">To complete this task, you first copy an instance, and then sign in to the Microsoft Power Platform Admin Center to copy your Power Apps environment.</span></span>

> [!WARNING]
> <span data-ttu-id="afa58-130">Példány másolásakor a program törli az adatbázist a célpéldányban.</span><span class="sxs-lookup"><span data-stu-id="afa58-130">When you copy an instance, the database is erased in the target instance.</span></span> <span data-ttu-id="afa58-131">A célpéldány nem érhető el a folyamat során.</span><span class="sxs-lookup"><span data-stu-id="afa58-131">The target instance is unavailable during this process.</span></span>

1. <span data-ttu-id="afa58-132">Jelentkezzen be az LCS-rendszerbe, majd válassza ki a másolni kívánt példányt tartalmazó LCS-projektet.</span><span class="sxs-lookup"><span data-stu-id="afa58-132">Sign in to LCS, and select the LCS project that contains the instance that you want to copy.</span></span>

2. <span data-ttu-id="afa58-133">Az LCS-projektben válassza a **Human Resources alkalmazás kezelése** csempét.</span><span class="sxs-lookup"><span data-stu-id="afa58-133">In your LCS project, select the **Human Resources App Management** tile.</span></span>

3. <span data-ttu-id="afa58-134">Válassza ki a másolni kívánt példányt, majd válassza a **Másolás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="afa58-134">Select the instance to copy, and then select **Copy**.</span></span>

4. <span data-ttu-id="afa58-135">A **Példány másolása** munkaablakban válassza ki azt a példányt, amelyet felül szeretne írni, majd válassza a **Másolás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="afa58-135">In the **Copy an instance** task pane, select the instance to overwrite, and then select **Copy**.</span></span> <span data-ttu-id="afa58-136">Várjon, amíg a **Másolás állapota** mező értéke **Kész** értékre módosul.</span><span class="sxs-lookup"><span data-stu-id="afa58-136">Wait for the value of the **Copy status** field to be updated to **Completed**.</span></span>

   ![[<span data-ttu-id="afa58-137">Felülírandó példány kiválasztása</span><span class="sxs-lookup"><span data-stu-id="afa58-137">Select instance to overwrite</span></span>](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. <span data-ttu-id="afa58-138">Válassza ki a **Power Platform** lehetőséget, majd jelentkezzen be a Microsoft Power Platform Admin Centerbe.</span><span class="sxs-lookup"><span data-stu-id="afa58-138">Select **Power Platform**, and sign in to the Microsoft Power Platform Admin Center.</span></span>

   ![[<span data-ttu-id="afa58-139">Válassza a Power Platform lehetőséget</span><span class="sxs-lookup"><span data-stu-id="afa58-139">Select Power Platform</span></span>](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. <span data-ttu-id="afa58-140">Válassza ki a másolni kívánt Power Apps-környezetet, majd válassza a **Másolás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="afa58-140">Select the Power Apps environment to copy, and then select **Copy**.</span></span>

7. <span data-ttu-id="afa58-141">A másolási folyamat befejezése után jelentkezzen be a célpéldányba, és engedélyezze a Dataverse-integrációt.</span><span class="sxs-lookup"><span data-stu-id="afa58-141">When the copy process is completed, sign in to the target instance, and enable Dataverse integration.</span></span> <span data-ttu-id="afa58-142">További tudnivalókért és utasításokért lásd: [A Dataverse-integráció konfigurálása](./hr-admin-integration-common-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="afa58-142">For more information and instructions, see [Configure Dataverse integration](./hr-admin-integration-common-data-service.md).</span></span>

## <a name="data-elements-and-statuses"></a><span data-ttu-id="afa58-143">Adatelemek és állapotok</span><span class="sxs-lookup"><span data-stu-id="afa58-143">Data elements and statuses</span></span>

<span data-ttu-id="afa58-144">A rendszer nem másolja át a következő adatelemeket a Human Resources példányának másolásakor:</span><span class="sxs-lookup"><span data-stu-id="afa58-144">The following data elements aren't copied when you copy a Human Resources instance:</span></span>

- <span data-ttu-id="afa58-145">E-mail-címek a **LogisticsElectronicAddress** táblában</span><span class="sxs-lookup"><span data-stu-id="afa58-145">Email addresses in the **LogisticsElectronicAddress** table</span></span>

- <span data-ttu-id="afa58-146">A kötegelt feladat előzményei a **BatchJobHistory**, a **BatchHistory** és a **BatchConstraintHistory** táblákban</span><span class="sxs-lookup"><span data-stu-id="afa58-146">The batch job history in the **BatchJobHistory**, **BatchHistory**, and **BatchConstraintHistory** tables</span></span>

- <span data-ttu-id="afa58-147">A Simple Mail Transfer Protocol (SMTP)-jelszó a **SysEmailSMTPPassword** táblában</span><span class="sxs-lookup"><span data-stu-id="afa58-147">The Simple Mail Transfer Protocol (SMTP) password in the **SysEmailSMTPPassword** table</span></span>

- <span data-ttu-id="afa58-148">Az SMTP-közvetítőkiszolgáló a **SysEmailParameters** táblában</span><span class="sxs-lookup"><span data-stu-id="afa58-148">The SMTP Relay server in the **SysEmailParameters** table</span></span>

- <span data-ttu-id="afa58-149">A **PrintMgmtSettings** és a **PrintMgmtDocInstance** táblákban lévő nyomtatáskezelési beállítások</span><span class="sxs-lookup"><span data-stu-id="afa58-149">Print Management settings in the **PrintMgmtSettings** and **PrintMgmtDocInstance** tables</span></span>

- <span data-ttu-id="afa58-150">Környezetspecifikus rekordok a **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** és **BatchServerGroup** táblákban</span><span class="sxs-lookup"><span data-stu-id="afa58-150">Environment-specific records in the **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, and **BatchServerGroup** tables</span></span>

- <span data-ttu-id="afa58-151">Dokumentumok mellékletei a DocuValue táblában.</span><span class="sxs-lookup"><span data-stu-id="afa58-151">Document attachments in the DocuValue table.</span></span> <span data-ttu-id="afa58-152">Ezek a mellékletek a Microsoft Office forráskörnyezetben felülírt sablonokat tartalmazzák</span><span class="sxs-lookup"><span data-stu-id="afa58-152">These attachments include any Microsoft Office templates that were overwritten in the source environment</span></span>

- <span data-ttu-id="afa58-153">Kapcsolati karakterlánc a **PersonnelIntegrationConfiguration** táblában</span><span class="sxs-lookup"><span data-stu-id="afa58-153">The connection string in the **PersonnelIntegrationConfiguration** table</span></span>

<span data-ttu-id="afa58-154">Néhány elemet nem másolt át a program, mert környezetspecifikusak.</span><span class="sxs-lookup"><span data-stu-id="afa58-154">Some of these elements aren't copied because they're environment-specific.</span></span> <span data-ttu-id="afa58-155">Ilyenek például a **BatchServerConfig** és a **SysCorpNetPrinters** rekordok.</span><span class="sxs-lookup"><span data-stu-id="afa58-155">Examples include **BatchServerConfig** and **SysCorpNetPrinters** records.</span></span> <span data-ttu-id="afa58-156">A rendszer más elemeket nem másol a támogatási jegyek mennyisége miatt.</span><span class="sxs-lookup"><span data-stu-id="afa58-156">Other elements aren't copied because of the volume of support tickets.</span></span> <span data-ttu-id="afa58-157">Példa:</span><span class="sxs-lookup"><span data-stu-id="afa58-157">For example:</span></span>

- <span data-ttu-id="afa58-158">Ismétlődő e-mailek küldése történhet, mert az SMTP továbbra is engedélyezve van a felhasználói elfogadás (teszt) környezetében.</span><span class="sxs-lookup"><span data-stu-id="afa58-158">Duplicate emails might be sent because SMTP is still enabled in the user acceptance testing (sandbox) environment.</span></span>

- <span data-ttu-id="afa58-159">A program érvénytelen integrációs üzeneteket küld, mert a kötegelt feladatok továbbra is engedélyezve vannak.</span><span class="sxs-lookup"><span data-stu-id="afa58-159">Invalid integration messages might be sent because batch jobs are still enabled.</span></span>

- <span data-ttu-id="afa58-160">A felhasználók engedélyezhetők, mielőtt a rendszergazdák elvégezhetnék a frissítés utáni karbantartási műveleteket.</span><span class="sxs-lookup"><span data-stu-id="afa58-160">Users might be enabled before admins can perform post-refresh cleanup actions.</span></span>

<span data-ttu-id="afa58-161">Ezenkívül a következő állapotok módosulnak egy példány másolásakor:</span><span class="sxs-lookup"><span data-stu-id="afa58-161">Also, the following statuses change when you copy an instance:</span></span>

- <span data-ttu-id="afa58-162">A rendszergazda kivételével minden felhasználó **Letiltva** állapotban van.</span><span class="sxs-lookup"><span data-stu-id="afa58-162">All users except Admin are set to **Disabled**.</span></span>

- <span data-ttu-id="afa58-163">Minden kötegelt feladat – kivéve néhány rendszerfeladatot – **Visszatartás** értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="afa58-163">All batch jobs, except for some system jobs, are set to **Withhold**.</span></span>

## <a name="environment-admin"></a><span data-ttu-id="afa58-164">Környezeti adminisztrátor</span><span class="sxs-lookup"><span data-stu-id="afa58-164">Environment admin</span></span>

<span data-ttu-id="afa58-165">A cél védőfalkörnyezetében található összes felhasználót, többek között a rendszergazdákat is, felváltották a forráskörnyezet felhasználói.</span><span class="sxs-lookup"><span data-stu-id="afa58-165">All users in the target sandbox environment, including Administrators, are replaced by the users of the source environment.</span></span> <span data-ttu-id="afa58-166">Egy példány másolása előtt győződjön meg arról, hogy Ön a forráskörnyezet rendszergazdája.</span><span class="sxs-lookup"><span data-stu-id="afa58-166">Before you copy an instance, be sure that you're an Administrator in the source environment.</span></span> <span data-ttu-id="afa58-167">Ha nem, akkor nem tud bejelentkezni a cél védőfalkörnyezetébe a másolás befejezése után.</span><span class="sxs-lookup"><span data-stu-id="afa58-167">If you aren't, you can't sign in to the target sandbox environment after the copy has completed.</span></span>

<span data-ttu-id="afa58-168">A cél-védőfalkörnyezet minden nem rendszergazdai felhasználója le van tiltva, megakadályozva a nem kívánt bejelentkezéseket a védőfalkörnyezetben.</span><span class="sxs-lookup"><span data-stu-id="afa58-168">All non-Administrator users in the target sandbox environment are disabled to prevent unwanted sign-ins in the sandbox environment.</span></span> <span data-ttu-id="afa58-169">Ha szükséges, a rendszergazdák újra engedélyezhetik a felhasználókat.</span><span class="sxs-lookup"><span data-stu-id="afa58-169">Administrators can reenable users if needed.</span></span>

## <a name="apply-custom-fields-to-dataverse"></a><span data-ttu-id="afa58-170">Egyéni mezők alkalmazása a Dataverse-szolgáltatásra</span><span class="sxs-lookup"><span data-stu-id="afa58-170">Apply custom fields to Dataverse</span></span>

<span data-ttu-id="afa58-171">Ha példányát egy tesztkörnyezetbe másolja , és szeretné integrálni a tesztkörnyezetét a Dataverse szolgáltatással, akkor újra kell alkalmaznia az egyéni mezőket a Dataverse-táblákra.</span><span class="sxs-lookup"><span data-stu-id="afa58-171">If you copy an instance into your sandbox environment and want to integrate your sandbox environment with Dataverse, you must reapply custom fields to Dataverse tables.</span></span>

<span data-ttu-id="afa58-172">A Dataverse-táblákon közzétett egyéni mezők esetében hajtsa végre a következő lépéseket:</span><span class="sxs-lookup"><span data-stu-id="afa58-172">For each custom field that's exposed on Dataverse tables, do the following steps:</span></span>

1. <span data-ttu-id="afa58-173">Nyissa meg az egyéni mezőt, és válassza a **Szerkesztés** elemet.</span><span class="sxs-lookup"><span data-stu-id="afa58-173">Go to the custom field and select **Edit**.</span></span>

2. <span data-ttu-id="afa58-174">Törölje az **Engedélyezve** jelölőnégyzet jelölését minden olyan cdm_\* entitás esetében, amelynél engedélyezve van az egyéni mező.</span><span class="sxs-lookup"><span data-stu-id="afa58-174">Unselect the **Enabled** field for each cdm_\* entity that the custom field is enabled on.</span></span>

3. <span data-ttu-id="afa58-175">Válassza a **Módosítások alkalmazása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="afa58-175">Select **Apply Changes**.</span></span>

4. <span data-ttu-id="afa58-176">Válassza ismét a **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="afa58-176">Select **Edit** again.</span></span>

5. <span data-ttu-id="afa58-177">Jelölj be az **Engedélyezve** jelölőnégyzetet minden olyan cdm_\* entitás esetében, amelynél engedélyezve van az egyéni mező.</span><span class="sxs-lookup"><span data-stu-id="afa58-177">Select the **Enabled** field for each cdm_\* entity that the custom field is enabled on.</span></span>

6. <span data-ttu-id="afa58-178">Válassza ismét a **Módosítások alkalmazása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="afa58-178">Select **Apply Changes** again.</span></span>

<span data-ttu-id="afa58-179">A kijelölés törlése, változtatások alkalmazása, kijelölés újra, és változtatások ismételt alkalmazása arra utasítja a sémát, hogy frissítsen a Dataverse-szolgáltatásban, hogy tartalmazza az egyéni mezőket.</span><span class="sxs-lookup"><span data-stu-id="afa58-179">The process of unselecting, applying changes, reselecting, and reapplying changes prompts the schema to update in Dataverse to include the custom fields.</span></span>

<span data-ttu-id="afa58-180">További információkért az egyéni mezőkről lásd: [Egyéni mezők létrehozása és felhasználása](../fin-ops-core/fin-ops/get-started/user-defined-fields.md).</span><span class="sxs-lookup"><span data-stu-id="afa58-180">For more information about custom fields, see [Create and work with custom fields](../fin-ops-core/fin-ops/get-started/user-defined-fields.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="afa58-181">Lásd még</span><span class="sxs-lookup"><span data-stu-id="afa58-181">See also</span></span>

[<span data-ttu-id="afa58-182">Emberi erőforrások létesítése</span><span class="sxs-lookup"><span data-stu-id="afa58-182">Provision Human Resources</span></span>](hr-admin-setup-provision.md)</br>
[<span data-ttu-id="afa58-183">Példány eltávolítása</span><span class="sxs-lookup"><span data-stu-id="afa58-183">Remove an instance</span></span>](hr-admin-setup-remove-instance.md)</br>
[<span data-ttu-id="afa58-184">Rendelés frissítése</span><span class="sxs-lookup"><span data-stu-id="afa58-184">Update process</span></span>](hr-admin-setup-update-process.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]