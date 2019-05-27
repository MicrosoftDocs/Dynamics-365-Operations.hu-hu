---
title: Az SQL Server Reporting Services konfigurálása on-premises telepítésekhez
description: Ez a témakör információkat nyújt az SQL Server Reporting Services (SSRS) szolgáltatásról on-premises telepítés esetén.
author: sarvanisathish
manager: AnnBe
ms.date: 06/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Operations
ms.custom: 55651
ms.assetid: ''
ms.search.region: Global
ms.author: sarvanis
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.openlocfilehash: 166d419f16866f699b96013222ce8da147a5ec21
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548719"
---
# <a name="configure-sql-server-reporting-services-for-on-premises-deployments"></a><span data-ttu-id="2ad8e-103">Az SQL Server Reporting Services konfigurálása on-premises telepítésekhez</span><span class="sxs-lookup"><span data-stu-id="2ad8e-103">Configure SQL Server Reporting Services for on-premises deployments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2ad8e-104">Kövesse a témakörben található a lépéseket az SQL Server Reporting Services (SRRS) konfigurálásához a Microsoft Dynamics 365 for Finance and Operations (on premises) telepítéséhez.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-104">Use the steps in this topic to configure SQL Server Reporting Services (SSRS) for your Microsoft Dynamics 365 for Finance and Operations (on-premises) deployment.</span></span>

1. <span data-ttu-id="2ad8e-105">Nyissa meg a Reporting Services konfigurációkezelő alkalmazást.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-105">Open the Reporting Services Configuration Manager application.</span></span>
2. <span data-ttu-id="2ad8e-106">Hagyja meg az alapértelmezett **Kiszolgálónév** értéket, amelynek a jelenlegi gép nevének kell lennie, valamint a **Jelentéskészítő kiszolgáló példánya** is legyen az alapértelmezett **MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-106">Leave the default **Server name**, which should be the name of the current machine, and the **Report Server Instance**, **MSSQLSERVER**.</span></span>
3. <span data-ttu-id="2ad8e-107">Kattintson a **Kapcsolódás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-107">Click **Connect**.</span></span>

    <span data-ttu-id="2ad8e-108">[![Jelentéskészítő szolgáltatások konfigurációs kapcsolata](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)</span><span class="sxs-lookup"><span data-stu-id="2ad8e-108">[![Reporting services configuration connection](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)</span></span>

4. <span data-ttu-id="2ad8e-109">Kattintson a **Szolgáltatásfiók** lapfülre, és ellenőrizze, hogy a beállítások megegyeznek-e a következő ábrán láthatókkal.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-109">Click the **Service Account** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="2ad8e-110">[![Szolgáltatásfiók lap](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)</span><span class="sxs-lookup"><span data-stu-id="2ad8e-110">[![Service account tab](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)</span></span>

5. <span data-ttu-id="2ad8e-111">Kattintson a **Webszolgáltatás URL-címe** lapfülre, és ellenőrizze, hogy a beállítások megegyeznek-e a következő ábrán láthatókkal.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-111">Click the **Web Service URL** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="2ad8e-112">[![Webszolgáltatás URL-címe lap](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)</span><span class="sxs-lookup"><span data-stu-id="2ad8e-112">[![Web service URL tab](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)</span></span>

6. <span data-ttu-id="2ad8e-113">Kattintson az **Adatbázis** fülre, és ellenőrizze, hogy az **Adatbázisnév** és a **Hitelesítő beállítások** megfelelnek az alábbi ábrán láthatóaknak.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-113">Click the **Database** tab and verify that the **Database Name** and **Credential settings** match the following graphic.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2ad8e-114">Szüksége lesz új adatbázis létrehozására.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-114">You will need to create a new database.</span></span> <span data-ttu-id="2ad8e-115">Ehhez kattintson az **Adatbázis módosítása** lehetőségre, majd győződjön meg róla, hogy az új adatbázis neve a **DynamicsAxReportServer**.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-115">To do this, click **Change Database**, and then verify that the new database name is: **DynamicsAxReportServer**.</span></span>

    <span data-ttu-id="2ad8e-116">[![adatbázis lap](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)</span><span class="sxs-lookup"><span data-stu-id="2ad8e-116">[![database tab](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)</span></span>

7. <span data-ttu-id="2ad8e-117">Kattintson a **Webportál URL-címe** lapfülre, és ellenőrizze, hogy a beállítások megegyeznek-e a következő ábrán láthatókkal.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-117">Click the **Web Portal URL** tab and verify that the settings match the following graphic.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2ad8e-118">Rá kell kattintania az **Alkalmaz** lehetőségre a portál létrehozásához és megfelelő konfigurálásához.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-118">You must click **Apply** to create and properly configure the Portal.</span></span>

    <span data-ttu-id="2ad8e-119">[![webportál url-címe lap](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)</span><span class="sxs-lookup"><span data-stu-id="2ad8e-119">[![web portal url tab](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)</span></span>

    <span data-ttu-id="2ad8e-120">A portál beállítása után a **Webes portál** lap az alábbi ábrával fog megegyezni.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-120">After the Portal is configured, the **Web Portal** tab will match the following graphic.</span></span>

    <span data-ttu-id="2ad8e-121">[![webportál lap](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)</span><span class="sxs-lookup"><span data-stu-id="2ad8e-121">[![web portal tab](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)</span></span>

8. <span data-ttu-id="2ad8e-122">Kattintson a jelentések URL-jére az SQL Server Reporting Services webportál megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-122">Click the reports URL to view the SQL Server Reporting Services web portal.</span></span>
9. <span data-ttu-id="2ad8e-123">A portálon hozzon létre egy új, **Dynamics** nevű mappát.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-123">When you are in the portal, create a new folder named **Dynamics**.</span></span>

    <span data-ttu-id="2ad8e-124">[![dynamics mappa](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)</span><span class="sxs-lookup"><span data-stu-id="2ad8e-124">[![dynamics folder](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)</span></span>

10. <span data-ttu-id="2ad8e-125">A **Reporting Services konfigurációkezelőben** kattintson az **E-mail beállítások** lapfülre, és ellenőrizze, hogy a beállítások megfelelnek-e az alábbi ábrán láthatóaknak.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-125">In the **Reporting Services Configuration Manager**, click the **E-mail Settings** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="2ad8e-126">[![e-mail beállítások lap](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)</span><span class="sxs-lookup"><span data-stu-id="2ad8e-126">[![email settings tab](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)</span></span>

11. <span data-ttu-id="2ad8e-127">Kattintson a **Végrehajtó fiók** lapfülre, és ellenőrizze, hogy a beállítások megegyeznek-e a következő ábrán láthatókkal.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-127">Click the **Execution Account** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="2ad8e-128">[![végrehajtó fiók lap](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)</span><span class="sxs-lookup"><span data-stu-id="2ad8e-128">[![execution account tab](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)</span></span>

    <span data-ttu-id="2ad8e-129">Ne módosítsa az alapértelmezett beállításokat a **Titkosítási kulcsok** lapon.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-129">Don't change the default settings on the **Encryption Keys** tab.</span></span>

    <span data-ttu-id="2ad8e-130">[![titkosítási kulcsok lap](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)</span><span class="sxs-lookup"><span data-stu-id="2ad8e-130">[![encryption keys tab](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)</span></span>

12. <span data-ttu-id="2ad8e-131">Kattintson az **Előfizetési beállítások** lapfülre, és ellenőrizze, hogy a beállítások megegyeznek-e a következő ábrán láthatókkal.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-131">Click the **Subscription Settings** tab, and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="2ad8e-132">[![előfizetési beállítások lap](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)</span><span class="sxs-lookup"><span data-stu-id="2ad8e-132">[![subscription settings tab](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)</span></span>

    <span data-ttu-id="2ad8e-133">Ne módosítsa az alapértelmezett beállításokat a **Skálázott telepítés** lapon.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-133">Don't change the default settings on the **Scale-out Deployment** tab.</span></span>

    <span data-ttu-id="2ad8e-134">[![skálázott telepítés lap](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)</span><span class="sxs-lookup"><span data-stu-id="2ad8e-134">[![scale-out deployment tab](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)</span></span>

    <span data-ttu-id="2ad8e-135">Ne módosítsa az alapértelmezett beállításokat a **Power BI-integráció** lapon.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-135">Don't change the default settings on the **Power BI Integration** tab.</span></span>

    <span data-ttu-id="2ad8e-136">[![power BI-integráció lap](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)</span><span class="sxs-lookup"><span data-stu-id="2ad8e-136">[![power bi integration tab](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)</span></span>

13. <span data-ttu-id="2ad8e-137">Kattintson a **Kilépés** ikonra a **Reporting Services konfigurációkezelő** bezárásához.</span><span class="sxs-lookup"><span data-stu-id="2ad8e-137">Click **Exit** to close the **Reporting Services Configuration Manager**.</span></span>

    <span data-ttu-id="2ad8e-138">[![a reporting services konfigurációkezelőjének bezárása](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)</span><span class="sxs-lookup"><span data-stu-id="2ad8e-138">[![close reporting services configuration manager](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)</span></span>
