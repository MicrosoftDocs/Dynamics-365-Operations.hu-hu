---
title: A(z) Finance and Operations alkalmazások frissítésével kapcsolatos problémák elhárítása
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segítségével javíthatók a Finance and Operations-alkalmazások frissítésével kapcsolatos problémák.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 59384d8e8d043eb14231a471c7218ced2dddf739
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172877"
---
# <a name="troubleshoot-issues-related-to-upgrades-of-finance-and-operations-apps"></a><span data-ttu-id="d5256-103">A(z) Finance and Operations alkalmazások frissítésével kapcsolatos problémák elhárítása</span><span class="sxs-lookup"><span data-stu-id="d5256-103">Troubleshoot issues related to upgrades of Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="d5256-104">Ez a cikk a Finance and Operations és a Common Data Service alkalmazások közötti kettős írású adatintegrációk során felmerülő hibák elhárításával kapcsolatos információkat tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="d5256-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="d5256-105">Pontosabban ez a témakör olyan információkat tartalmaz, amelyek segítségével javíthatók a Finance and Operations-alkalmazások frissítésével kapcsolatos problémák.</span><span class="sxs-lookup"><span data-stu-id="d5256-105">Specifically, it provides information that can help you fix issues that are related to upgrades of Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d5256-106">Előfordulhat, hogy az ebben a témakörben leírt problémák egy része a rendszergazda szerepkört vagy Microsoft Azure Active Directory (Azure AD) bérlői adminisztrátori hitelesítő adatait igénylik.</span><span class="sxs-lookup"><span data-stu-id="d5256-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="d5256-107">Az egyes problémákat tárgyaló szakaszok leírják, hogy szükség van-e konkrét szerepkörre vagy hitelesítő adatokra.</span><span class="sxs-lookup"><span data-stu-id="d5256-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="database-synchronization-errors"></a><span data-ttu-id="d5256-108">Adatbázis szinkronizálási hibái</span><span class="sxs-lookup"><span data-stu-id="d5256-108">Database synchronization errors</span></span>

<span data-ttu-id="d5256-109">**A hiba megtekintéséhez szükséges szerepkör:** Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="d5256-109">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="d5256-110">Előfordulhat, hogy egy hibaüzenet jelenik meg, amely a következő példához hasonlít, amikor megpróbálja használni a **DualWriteProjectConfiguration** entitást egy Finance and Operations-alkalmazás frissítésekor a Platform update 30 verzióra.</span><span class="sxs-lookup"><span data-stu-id="d5256-110">You might receive an error message that resembles the following example when you try to use the **DualWriteProjectConfiguration** entity to update a Finance and Operations app to Platform update 30.</span></span>

```console
Infolog diagnostic message: 'Cannot select a record in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

<span data-ttu-id="d5256-111">Egy hiba javításához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="d5256-111">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="d5256-112">Jelentkezzen be a Finance and Operations alkalmazáshoz tartozó virtuális gépre (VM).</span><span class="sxs-lookup"><span data-stu-id="d5256-112">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="d5256-113">Nyissa meg Visual Studio alkalmazást adminisztrátorként, és nyissa meg az alkalmazásobjektum-fát (AOT).</span><span class="sxs-lookup"><span data-stu-id="d5256-113">Open Visual Studio as an admin, and open the Application Object Tree (AOT).</span></span>
3. <span data-ttu-id="d5256-114">Keresse meg a **DualWriteProjectConfiguration** elemet.</span><span class="sxs-lookup"><span data-stu-id="d5256-114">Search for **DualWriteProjectConfiguration**.</span></span>
4. <span data-ttu-id="d5256-115">Az alkalmazásobjektum-fában kattintson a jobb gombbal a **DualWriteProjectConfiguration** elemre, majd válassza a **Hozzáadás új projekthez** parancsot.</span><span class="sxs-lookup"><span data-stu-id="d5256-115">In the AOT, right-click **DualWriteProjectConfiguration**, and select **Add to new project**.</span></span> <span data-ttu-id="d5256-116">Az **ok** gombra kattintva hozza létre az alapértelmezett beállításokat használó új projektet.</span><span class="sxs-lookup"><span data-stu-id="d5256-116">Select **OK** to create the new project that uses default options.</span></span>
5. <span data-ttu-id="d5256-117">A Solution Explorer alkalmazásban kattintson a jobb gombbal a **Projekt tulajdonságai** elemre, és állítsa az **Adatbázis szinkronizálása kialakításkor** beállítást **Igaz** értékre.</span><span class="sxs-lookup"><span data-stu-id="d5256-117">In Solution Explorer, right-click **Project properties**, and set **Synchronize Database on Build** to **True**.</span></span>
6. <span data-ttu-id="d5256-118">Hozza létre a projektet, és erősítse meg a létrehozás sikerességét.</span><span class="sxs-lookup"><span data-stu-id="d5256-118">Build the project, and confirm that the build is successful.</span></span>
7. <span data-ttu-id="d5256-119">Válassza a **Dynamics 365** menü **Adatbázis szinkronizálása** pontját.</span><span class="sxs-lookup"><span data-stu-id="d5256-119">On the **Dynamics 365** menu, select **Synchronize database**.</span></span>
8. <span data-ttu-id="d5256-120">A teljes adatbázis-szinkronizálás végrehajtásához válassza a **Szinkronizálás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="d5256-120">Select **Synchronize** to do a full database synchronization.</span></span>
9. <span data-ttu-id="d5256-121">A teljes adatbázis-szinkronizálás sikeres végrehajtása után futtassa újra az adatbázis-szinkronizálási lépést a Microsoft Dynamics Lifecycle Services (LCS) modulban, és szükség szerint használja a manuális frissítési parancsfájlokat, hogy folytathassa a frissítést.</span><span class="sxs-lookup"><span data-stu-id="d5256-121">After the full database synchronization is successful, rerun the database synchronization step in Microsoft Dynamics Lifecycle Services (LCS) and use the manual upgrade scripts as applicable, so that you can proceed with the update.</span></span>

## <a name="missing-entity-fields-issue-on-maps"></a><span data-ttu-id="d5256-122">Hiányzó entitásmezők problémája a leképezésekben</span><span class="sxs-lookup"><span data-stu-id="d5256-122">Missing entity fields issue on maps</span></span>

<span data-ttu-id="d5256-123">**A hiba megtekintéséhez szükséges szerepkör:** Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="d5256-123">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="d5256-124">A **Kettős írás** oldalon a következő példához hasonló hibaüzenet jelenhet meg:</span><span class="sxs-lookup"><span data-stu-id="d5256-124">On the **Dual-write** page, you might receive an error message that resembles the following example:</span></span>

<span data-ttu-id="d5256-125">*Hiányzó forrásmező \<mező neve\> a sémában.*</span><span class="sxs-lookup"><span data-stu-id="d5256-125">*Missing source field \<field name\> in the schema.*</span></span>

![Példa a hiányzó forrásmező hibaüzenetére](media/error_missing_field.png)

<span data-ttu-id="d5256-127">A hiba javításához kövesse az alábbi lépéseket, és győződjön meg arról, hogy a mezők szerepelnek az entitásban.</span><span class="sxs-lookup"><span data-stu-id="d5256-127">To fix the issue, first follow these steps to make sure that the fields are in the entity.</span></span>

1. <span data-ttu-id="d5256-128">Jelentkezzen be a Finance and Operations alkalmazáshoz tartozó virtuális gépre.</span><span class="sxs-lookup"><span data-stu-id="d5256-128">Sign in to the VM for the Finance and Operations app.</span></span>
2. <span data-ttu-id="d5256-129">Lépjen a **Munkaterületek \> Adatkezelés** pontra, válassza a **Keretrendszer paraméterei** csmepét, majd az **Entitásbeállítások** lapon válassza az **Entitáslista frissítése** parancsot az entitások frissítéséhez.</span><span class="sxs-lookup"><span data-stu-id="d5256-129">Go to **Workspaces \> Data management**, select the **Framework parameters** tile, and then, on the **Entity settings** tab, select **Refresh entity list** to refresh the entities.</span></span>
3. <span data-ttu-id="d5256-130">Lépjen a **Munkaterületek \> Adatkezelés** részre, válassza az **Adatentitások** lapot, és ellenőrizze, hogy az entitás szerepel a listában.</span><span class="sxs-lookup"><span data-stu-id="d5256-130">Go to **Workspaces \> Data management**, select the **Data entities** tab, and make sure that the entity is listed.</span></span> <span data-ttu-id="d5256-131">Ha az entitás nem szerepel a listában, jelentkezzen be a Finance and Operations alkalmazás virtuális gépére, és győződjön meg róla, hogy az entitás elérhető.</span><span class="sxs-lookup"><span data-stu-id="d5256-131">If the entity isn't listed, sign in to the VM for the Finance and Operations app, and make sure the entity is available.</span></span>
4. <span data-ttu-id="d5256-132">Nyissa meg az **Entitásleképezés** oldalt a Finance and Operations alkalmazás **Kettős írás** oldalán.</span><span class="sxs-lookup"><span data-stu-id="d5256-132">Open the **Entity mapping** page from the **Dual-write** page in the Finance and Operations app.</span></span>
5. <span data-ttu-id="d5256-133">Az entitásleképezések mezőinek automatikus kitöltéséhez válassza az **Entitáslista frissítése** elemet.</span><span class="sxs-lookup"><span data-stu-id="d5256-133">Select **Refresh entity list** to automatically fill the fields in the entity mappings.</span></span>

<span data-ttu-id="d5256-134">Ha a hiba továbbra sincs kijavítva, hajtsa végre az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="d5256-134">If the issue still isn't fixed, follow these steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d5256-135">Ezekkel a lépésekkel egy entitás törlési folyamatát hajthatja végre, majd hozzáadhatja újra.</span><span class="sxs-lookup"><span data-stu-id="d5256-135">These steps guide you through the process of deleting an entity and then adding it again.</span></span> <span data-ttu-id="d5256-136">A problémák elkerüléséhez ügyeljen arra, hogy a lépéseket pontosan kövesse.</span><span class="sxs-lookup"><span data-stu-id="d5256-136">To avoid issues, be sure to follow the steps exactly.</span></span>

1. <span data-ttu-id="d5256-137">A Finance and Operations alkalmazásban nyissa meg a **Munkaterületek \> Adatkezelés** pontot, és válassza az **Adatentitások** csempét.</span><span class="sxs-lookup"><span data-stu-id="d5256-137">In the Finance and Operations app, go to **Workspaces \> Data management**, and select the **Data entities** tile.</span></span>
2. <span data-ttu-id="d5256-138">Keresse meg azt az entitást, amelynek hiányzik a mezője.</span><span class="sxs-lookup"><span data-stu-id="d5256-138">Find the entity that is missing the field.</span></span> <span data-ttu-id="d5256-139">Jegyezze fel a cél entitást, az előkészítési táblát, az entitás nevét és a többi oszlop értékét.</span><span class="sxs-lookup"><span data-stu-id="d5256-139">Make a note of the target entity, staging table, entity name, and other column values.</span></span>
3. <span data-ttu-id="d5256-140">Ha bármelyik feldolgozási csoport ettől az entitástól függ, akkor az entitás törlése előtt hajtsa végre a megfelelő műveleteket a feldolgozási csoportoknak.</span><span class="sxs-lookup"><span data-stu-id="d5256-140">If any of your processing groups depend on this entity, take appropriate action for the processing groups before you delete the entity.</span></span>
4. <span data-ttu-id="d5256-141">Törölje azt az entitást, amelynek hiányzik a mezője.</span><span class="sxs-lookup"><span data-stu-id="d5256-141">Delete the entity that is missing the field.</span></span>
5. <span data-ttu-id="d5256-142">Válassza az **Új** lehetőséget, majd adja hozzá újra az entitást.</span><span class="sxs-lookup"><span data-stu-id="d5256-142">Select **New**, and add the entity back.</span></span> <span data-ttu-id="d5256-143">Adja meg a 2. lépésben jegyzetként elkészített értékeket.</span><span class="sxs-lookup"><span data-stu-id="d5256-143">Specify the values that you made a note of in step 2.</span></span>
6. <span data-ttu-id="d5256-144">Nyissa meg az **Entitásleképezés** oldalt a Finance and Operations alkalmazás **Kettős írás** oldalán.</span><span class="sxs-lookup"><span data-stu-id="d5256-144">Open the **Entity mapping** page from the **Dual-write** page in the Finance and Operations app.</span></span>
7. <span data-ttu-id="d5256-145">Az entitásleképezések mezőinek automatikus kitöltéséhez válassza az **Entitáslista frissítése** elemet.</span><span class="sxs-lookup"><span data-stu-id="d5256-145">Select **Refresh entity list** to automatically fill the fields in the entity mappings.</span></span>
