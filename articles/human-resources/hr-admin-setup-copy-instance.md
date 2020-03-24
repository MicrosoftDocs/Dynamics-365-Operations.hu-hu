---
title: Példány másolása
description: A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatással átmásolhat egy Microsoft Dynamics 365 Human Resources-adatbázist egy védőfalkörnyezetbe.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bb363369994d99f358be0c23cdaf1dbc80b644e5
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092292"
---
# <a name="copy-an-instance"></a><span data-ttu-id="7419a-103">Példány másolása</span><span class="sxs-lookup"><span data-stu-id="7419a-103">Copy an instance</span></span>

<span data-ttu-id="7419a-104">A Microsoft Dynamics Lifecycle Services (LCS) szolgáltatással átmásolhat egy Microsoft Dynamics 365 Human Resources-adatbázist egy védőfalkörnyezetbe.</span><span class="sxs-lookup"><span data-stu-id="7419a-104">You can use Microsoft Dynamics Lifecycle Services (LCS) to copy a Microsoft Dynamics 365 Human Resources database to a sandbox environment.</span></span> <span data-ttu-id="7419a-105">Ha van másik tesztkörnyezete, akkor abból a környezetből is másolható az adatbázis a célként kiválasztott tesztkörnyezetbe.</span><span class="sxs-lookup"><span data-stu-id="7419a-105">If you have another sandbox environment, you can also copy the database from that environment to a targeted sandbox environment.</span></span>

<span data-ttu-id="7419a-106">Egy példány másolásához a következőket kell biztosítania:</span><span class="sxs-lookup"><span data-stu-id="7419a-106">To copy an instance, you need to ensure the following:</span></span>

- <span data-ttu-id="7419a-107">A felülírni kívánt Human Resources példánynak védőfalkörnyezetnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="7419a-107">The Human Resources instance you want to overwrite must be a sandbox environment.</span></span>

- <span data-ttu-id="7419a-108">A környezeteknek, ahonnan és ahová másolni kíván, ugyanabban a régióban kell lenniük.</span><span class="sxs-lookup"><span data-stu-id="7419a-108">The environments you are copying from and to must be in the same region.</span></span> <span data-ttu-id="7419a-109">Nem másolhat régiók között.</span><span class="sxs-lookup"><span data-stu-id="7419a-109">You can't copy across regions.</span></span>

- <span data-ttu-id="7419a-110">A célkörnyezetben rendszergazdának kell lennie ahhoz, hogy a példány másolása után bejelentkezhessen.</span><span class="sxs-lookup"><span data-stu-id="7419a-110">You must be an Administrator in the target environment so you can sign into it after copying the instance.</span></span>

- <span data-ttu-id="7419a-111">A Human Resources adatbázisának másolása során nem másolja át a Microsoft PowerApps környezetben található elemeket (alkalmazásokat vagy adatokat).</span><span class="sxs-lookup"><span data-stu-id="7419a-111">When you copy the Human Resources database, you don't copy the elements (apps or data) that are contained in a Microsoft PowerApps environment.</span></span> <span data-ttu-id="7419a-112">A PowerApps-környezet elemeinek másolásával kapcsolatos tudnivalókat lásd: [Környezet másolása](https://docs.microsoft.com/power-platform/admin/copy-environment).</span><span class="sxs-lookup"><span data-stu-id="7419a-112">For information about how to copy elements in a PowerApps environment, see [Copy an environment](https://docs.microsoft.com/power-platform/admin/copy-environment).</span></span> <span data-ttu-id="7419a-113">A felülírni kívánt PowerApps -könyezetnek védőfalkörnyezetnek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="7419a-113">The PowerApps environment you want to overwrite must be a sandbox environment.</span></span> <span data-ttu-id="7419a-114">A PowerApps éles környezet védőfalkörnyezetbe történő módosításához globális bérlői rendszergazdának kell lennie.</span><span class="sxs-lookup"><span data-stu-id="7419a-114">You must be a global tenant admin to change a PowerApps production environment to a sandbox environment.</span></span> <span data-ttu-id="7419a-115">A PowerApps-környezet módosításával kapcsolatos további tudnivalókat lásd: [Példány váltása](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span><span class="sxs-lookup"><span data-stu-id="7419a-115">For more information about changing a PowerApps environment, see [Switch an instance](https://docs.microsoft.com/dynamics365/admin/switch-instance).</span></span>

## <a name="effects-of-copying-a-human-resources-database"></a><span data-ttu-id="7419a-116">A Human Resources-adatbázis másolásának hatásai</span><span class="sxs-lookup"><span data-stu-id="7419a-116">Effects of copying a Human Resources database</span></span>

<span data-ttu-id="7419a-117">A Human Resources-adatbázis másolásakor a következő események történnek:</span><span class="sxs-lookup"><span data-stu-id="7419a-117">The following events occur when you copy a Human Resources database:</span></span>

- <span data-ttu-id="7419a-118">A másolási folyamat törli a meglévő adatbázist a célkörnyezetből.</span><span class="sxs-lookup"><span data-stu-id="7419a-118">The copy process erases the existing database in the target environment.</span></span> <span data-ttu-id="7419a-119">A másolási folyamat befejezése után nem lehet visszaállítani a meglévő adatbázist.</span><span class="sxs-lookup"><span data-stu-id="7419a-119">After the copy process is completed, you can't recover the existing database.</span></span>

- <span data-ttu-id="7419a-120">A célkörnyezet addig nem lesz elérhető, amíg a másolási folyamat be nem fejeződik.</span><span class="sxs-lookup"><span data-stu-id="7419a-120">The target environment will be unavailable until the copy process is completed.</span></span>

- <span data-ttu-id="7419a-121">A Microsoft Azure Blob-tárolóban lévő dokumentumok nem kerülnek át egyik környezetből a másikba.</span><span class="sxs-lookup"><span data-stu-id="7419a-121">Documents in Microsoft Azure Blob storage aren't copied from one environment to another.</span></span> <span data-ttu-id="7419a-122">Emiatt a rendszer nem másolja a csatolt dokumentumokat és sablonokat, és a forráskörnyezetben maradnak.</span><span class="sxs-lookup"><span data-stu-id="7419a-122">Therefore, any documents and templates that are attached won't be copied and will remain in the source environment.</span></span>

- <span data-ttu-id="7419a-123">Az összes felhasználó elérhetetlen lesz a rendszergazdai felhasználó és az egyéb belső szolgáltatási felhasználói fiókok kivételével.</span><span class="sxs-lookup"><span data-stu-id="7419a-123">All users except the Admin user and other internal service user accounts will be unavailable.</span></span> <span data-ttu-id="7419a-124">Emiatt a Rendszergazda felhasználó törölheti vagy álcázhatja az adatokat, mielőtt a többi felhasználó visszakerül a rendszerbe.</span><span class="sxs-lookup"><span data-stu-id="7419a-124">Therefore, the Admin user can delete or obfuscate data before other users are allowed back into the system.</span></span>

- <span data-ttu-id="7419a-125">A Rendszergazda felhasználónak végre kell hajtania a szükséges konfigurációs változtatásokat, például az integrációs végpontok újracsatlakoztatását meghatározott szolgáltatásokhoz vagy URL-címekhez.</span><span class="sxs-lookup"><span data-stu-id="7419a-125">The Admin user must make required configuration changes, such as reconnecting integration endpoints to specific services or URLs.</span></span>

## <a name="copy-the-human-resources-database"></a><span data-ttu-id="7419a-126">Human Resources-adatbázis másolása</span><span class="sxs-lookup"><span data-stu-id="7419a-126">Copy the Human Resources database</span></span>

<span data-ttu-id="7419a-127">A feladat végrehajtásához először másolja a példányt, majd jelentkezzen be a Microsoft Power Platform Admin Center programba a PowerApps-környezet másolásához.</span><span class="sxs-lookup"><span data-stu-id="7419a-127">To complete this task, you first copy an instance, and then sign in to the Microsoft Power Platform Admin Center to copy your PowerApps environment.</span></span>

> [!WARNING]
> <span data-ttu-id="7419a-128">Példány másolásakor a program törli az adatbázist a célpéldányban.</span><span class="sxs-lookup"><span data-stu-id="7419a-128">When you copy an instance, the database is erased in the target instance.</span></span> <span data-ttu-id="7419a-129">A célpéldány nem érhető el a folyamat során.</span><span class="sxs-lookup"><span data-stu-id="7419a-129">The target instance is unavailable during this process.</span></span>

1. <span data-ttu-id="7419a-130">Jelentkezzen be az LCS-rendszerbe, majd válassza ki a másolni kívánt példányt tartalmazó LCS-projektet.</span><span class="sxs-lookup"><span data-stu-id="7419a-130">Sign in to LCS, and select the LCS project that contains the instance that you want to copy.</span></span>

2. <span data-ttu-id="7419a-131">Az LCS-projektben válassza a **Human Resources alkalmazás kezelése** csempét.</span><span class="sxs-lookup"><span data-stu-id="7419a-131">In your LCS project, select the **Human Resources App Management** tile.</span></span>

3. <span data-ttu-id="7419a-132">Válassza ki a másolni kívánt példányt, majd válassza a **Másolás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="7419a-132">Select the instance to copy, and then select **Copy**.</span></span>

4. <span data-ttu-id="7419a-133">A **Példány másolása** munkaablakban válassza ki azt a példányt, amelyet felül szeretne írni, majd válassza a **Másolás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="7419a-133">In the **Copy an instance** task pane, select the instance to overwrite, and then select **Copy**.</span></span> <span data-ttu-id="7419a-134">Várjon, amíg a **Másolás állapota** mező értéke **Kész** értékre módosul.</span><span class="sxs-lookup"><span data-stu-id="7419a-134">Wait for the value of the **Copy status** field to be updated to **Completed**.</span></span>

   ![[<span data-ttu-id="7419a-135">Az felülírandó példány kiválasztása</span><span class="sxs-lookup"><span data-stu-id="7419a-135">Select instance to overwrite</span></span>](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. <span data-ttu-id="7419a-136">Válassza ki a **Power Platform** lehetőséget, majd jelentkezzen be a Microsoft Power Platform Admin Centerbe.</span><span class="sxs-lookup"><span data-stu-id="7419a-136">Select **Power Platform**, and sign in to the Microsoft Power Platform Admin Center.</span></span>

   ![[<span data-ttu-id="7419a-137">Power Platform kiválasztása</span><span class="sxs-lookup"><span data-stu-id="7419a-137">Select Power Platform</span></span>](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. <span data-ttu-id="7419a-138">Válassza ki a másolni kívánt PowerApps-környezetet, majd válassza a **Másolás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="7419a-138">Select the PowerApps environment to copy, and then select **Copy**.</span></span>

7. <span data-ttu-id="7419a-139">A másolási folyamat befejezése után jelentkezzen be a célpéldányba, és engedélyezze a Common Data Service-integrációt.</span><span class="sxs-lookup"><span data-stu-id="7419a-139">When the copy process is completed, sign in to the target instance, and enable Common Data Service integration.</span></span> <span data-ttu-id="7419a-140">További tudnivalókért és utasításokért lásd: [A Common Data Service-integráció konfigurálása](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span><span class="sxs-lookup"><span data-stu-id="7419a-140">For more information and instructions, see [Configure Common Data Service integration](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).</span></span>

## <a name="data-elements-and-statuses"></a><span data-ttu-id="7419a-141">Adatelemek és állapotok</span><span class="sxs-lookup"><span data-stu-id="7419a-141">Data elements and statuses</span></span>

<span data-ttu-id="7419a-142">A rendszer nem másolja át a következő adatelemeket a Human Resources példányának másolásakor:</span><span class="sxs-lookup"><span data-stu-id="7419a-142">The following data elements aren't copied when you copy a Human Resources instance:</span></span>

- <span data-ttu-id="7419a-143">E-mail-címek a **LogisticsElectronicAddress** táblában</span><span class="sxs-lookup"><span data-stu-id="7419a-143">Email addresses in the **LogisticsElectronicAddress** table</span></span>

- <span data-ttu-id="7419a-144">A kötegelt feladat előzményei a **BatchJobHistory**, a **BatchHistory**és a **BatchConstraintHistory** táblákban</span><span class="sxs-lookup"><span data-stu-id="7419a-144">The batch job history in the **BatchJobHistory**, **BatchHistory**, and **BatchConstraintHistory** tables</span></span>

- <span data-ttu-id="7419a-145">A Simple Mail Transfer Protocol (SMTP)-jelszó a **SysEmailSMTPPassword** táblában</span><span class="sxs-lookup"><span data-stu-id="7419a-145">The Simple Mail Transfer Protocol (SMTP) password in the **SysEmailSMTPPassword** table</span></span>

- <span data-ttu-id="7419a-146">Az SMTP-közvetítőkiszolgáló a **SysEmailParameters** táblában</span><span class="sxs-lookup"><span data-stu-id="7419a-146">The SMTP Relay server in the **SysEmailParameters** table</span></span>

- <span data-ttu-id="7419a-147">A **PrintMgmtSettings** és a **PrintMgmtDocInstance** táblákban lévő nyomtatáskezelési beállítások</span><span class="sxs-lookup"><span data-stu-id="7419a-147">Print Management settings in the **PrintMgmtSettings** and **PrintMgmtDocInstance** tables</span></span>

- <span data-ttu-id="7419a-148">Környezetspecifikus rekordok a **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** és **BatchServerGroup** táblákban</span><span class="sxs-lookup"><span data-stu-id="7419a-148">Environment-specific records in the **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig**, and **BatchServerGroup** tables</span></span>

- <span data-ttu-id="7419a-149">Dokumentumok mellékletei a DocuValue táblában.</span><span class="sxs-lookup"><span data-stu-id="7419a-149">Document attachments in the DocuValue table.</span></span> <span data-ttu-id="7419a-150">Ezek a mellékletek a Microsoft Office forráskörnyezetben felülírt sablonokat tartalmazzák</span><span class="sxs-lookup"><span data-stu-id="7419a-150">These attachments include any Microsoft Office templates that were overwritten in the source environment</span></span>

- <span data-ttu-id="7419a-151">Kapcsolati karakterlánc a **PersonnelIntegrationConfiguration** táblában</span><span class="sxs-lookup"><span data-stu-id="7419a-151">The connection string in the **PersonnelIntegrationConfiguration** table</span></span>

<span data-ttu-id="7419a-152">Néhány elemet nem másolt át a program, mert környezetspecifikusak.</span><span class="sxs-lookup"><span data-stu-id="7419a-152">Some of these elements aren't copied because they are environment-specific.</span></span> <span data-ttu-id="7419a-153">Ilyenek például a **BatchServerConfig** és a **SysCorpNetPrinters** rekordok.</span><span class="sxs-lookup"><span data-stu-id="7419a-153">Examples include **BatchServerConfig** and **SysCorpNetPrinters** records.</span></span> <span data-ttu-id="7419a-154">A rendszer más elemeket nem másol a támogatási jegyek mennyisége miatt.</span><span class="sxs-lookup"><span data-stu-id="7419a-154">Other elements aren't copied because of the volume of support tickets.</span></span> <span data-ttu-id="7419a-155">Előfordulhat például, hogy a rendszer ismétlődő e-maileket küld el, mivel az SMTP továbbra is engedélyezve van a felhasználó jóváhagyásának tesztelésére szolgáló (védőfal-) környezetben, a rendszer érvénytelen integrációs üzeneteket küld, mert a kötegelt feladatok továbbra is engedélyezve vannak, és a felhasználók engedélyezésére csak a rendszergazdák által végrehajtott frissítés utáni törlési műveletek elvégzése után kerül sor.</span><span class="sxs-lookup"><span data-stu-id="7419a-155">For example, duplicate emails might be sent because SMTP is still enabled in the user acceptance testing (sandbox) environment, invalid integration messages might be sent because batch jobs are still enabled, and users might be enabled before admins can perform post-refresh cleanup actions.</span></span>

<span data-ttu-id="7419a-156">Ezenkívül a következő állapotok módosulnak egy példány másolásakor:</span><span class="sxs-lookup"><span data-stu-id="7419a-156">In addition, the following statuses change when you copy an instance:</span></span>

- <span data-ttu-id="7419a-157">A rendszergazda kivételével minden felhasználó **Letiltva** állapotban van.</span><span class="sxs-lookup"><span data-stu-id="7419a-157">All users except Admin are set to **Disabled**.</span></span>

- <span data-ttu-id="7419a-158">Minden kötegelt feladat – kivéve néhány rendszerfeladatot – **Visszatartás** értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="7419a-158">All batch jobs, except for some system jobs, are set to **Withhold**.</span></span>

## <a name="environment-admin"></a><span data-ttu-id="7419a-159">Környezeti adminisztrátor</span><span class="sxs-lookup"><span data-stu-id="7419a-159">Environment admin</span></span>

<span data-ttu-id="7419a-160">A cél védőfalkörnyezetében található összes felhasználót, többek között a rendszergazdákat is, felváltották a forráskörnyezet felhasználói.</span><span class="sxs-lookup"><span data-stu-id="7419a-160">All users in the target sandbox environment, including Administrators, are replaced by the users of the source environment.</span></span> <span data-ttu-id="7419a-161">Egy példány másolása előtt győződjön meg arról, hogy Ön a célkörnyezet rendszergazdája.</span><span class="sxs-lookup"><span data-stu-id="7419a-161">Before you copy an instance, be sure that you're an Administrator in the target environment.</span></span> <span data-ttu-id="7419a-162">Ha nem, akkor nem tud bejelentkezni a cél védőfalkörnyezetébe a másolás befejezése után.</span><span class="sxs-lookup"><span data-stu-id="7419a-162">If you aren't, you won't be able to sign in to the target sandbox environment after the copy has completed.</span></span>

<span data-ttu-id="7419a-163">A cél-védőfalkörnyezet minden nem rendszergazdai felhasználója le van tiltva, megakadályozva a nem kívánt bejelentkezéseket a védőfalkörnyezetben.</span><span class="sxs-lookup"><span data-stu-id="7419a-163">All non-Administrator users in the target sandbox environment are disabled to prevent unwanted sign-ins in the sandbox environment.</span></span> <span data-ttu-id="7419a-164">Ha szükséges, a rendszergazdák újra engedélyezhetik a felhasználókat.</span><span class="sxs-lookup"><span data-stu-id="7419a-164">Administrators can reenable users if needed.</span></span>
