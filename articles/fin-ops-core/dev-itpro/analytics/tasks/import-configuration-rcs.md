---
title: (ER) Konfigurációk importálása RCS-ből
description: Ez a témakör azt mutatja be, hogyan képes a felhasználó az RCS-ből egy ER-konfiguráció új verzióját importálni.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 32c9c17d8b63e4c0806559c2dcc2e11ae9825a53
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184623"
---
# <a name="er-import-configurations-from-rcs"></a><span data-ttu-id="f0d2a-103">(ER) Konfigurációk importálása RCS-ből</span><span class="sxs-lookup"><span data-stu-id="f0d2a-103">(ER) Import configurations from RCS</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f0d2a-104">A következő lépések leírják, hogy a Rendszergazda vagy az Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként importálhat új Elektronikus jelentés (ER) konfigurációt a Microsoft Regulatory Configuration Services (RCS) rendszerből.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can import a new version of an Electronic reporting (ER) configuration from Microsoft Regulatory Configuration Services (RCS).</span></span> <span data-ttu-id="f0d2a-105">Ebben a példában kiválasztja majd az ER-konfiguráció adott verzióját, amelyet egy RCS-példányban konfigurált, és importálja a mintavállalat, a Litware Inc. aktuális példányába. Ezeket a lépéseket bármilyen vállalatban végre lehet hajtani, mivel az ER-konfigurációk megoszthatók vállalatok között.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-105">In this example, you will select the version of the ER configuration that has been configured in an RCS instance and import it into the current instance for sample company, Litware, Inc. These steps can be performed in any company because ER configurations are shared among companies.</span></span> <span data-ttu-id="f0d2a-106">Az alábbi lépések végrehajtásához először hajtsa végre a [Konfigurációszolgáltató létrehozása és aktívként történő megjelölése](er-configuration-provider-mark-it-active-2016-11.md) témakör lépéseit.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-106">To complete these steps, you must first complete the steps in the topic, [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="f0d2a-107">Ezeknek a lépéseknek a végrehajtásához hozzáféréssel kell rendelkeznie egy olyan RCS-példányhoz is, amely legalább egy ER-konfigurációt tartalmaz vagy **Befejezett** vagy **Megosztott** állapotban.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-107">To complete these steps, you must also have access to an RCS instance containing at least one ER configuration in either **Completed** or **Shared** status.</span></span>

1. <span data-ttu-id="f0d2a-108">Lépjen a **Szervezeti adminisztráció** > **Munkaterületek** > **Elektronikus jelentés** részre.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-108">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="f0d2a-109">Ellenőrizze, hogy a Litware, Inc. mintavállalat esetében rendelkezésre áll és **aktívként** van megjelölve a konfigurációszolgáltató.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-109">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="f0d2a-110">Ha nem látja a konfigurációszolgáltatót, végezze el a [Konfigurációszolgáltató létrehozása, és megjelölés aktívként](er-configuration-provider-mark-it-active-2016-11.md) témakörben szereplő lépéseket.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-110">If you don’t see this configuration provider, complete the steps in the topic, [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 
3. <span data-ttu-id="f0d2a-111">Ha nincs RCS környezete a vállalathoz, kattintson a **Regulatory services – Konfiguráció** külső hivatkozásra, és kövesse az RCS-környezet létrehozására vonatkozó instrukciókat.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-111">If you have no RCS environment provisioned to your company, click **Regulatory services – Configuration** external link and follow the instructions to provision an RCS environment.</span></span> 
4. <span data-ttu-id="f0d2a-112">Kattintson az **Elektronikus jelentéskészítés paraméterei** elemre.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-112">Click **Electronic reporting parameters**.</span></span> 
5. <span data-ttu-id="f0d2a-113">Kattintson az **RCS** lapra.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-113">Click the **RCS** tab.</span></span> 
6. <span data-ttu-id="f0d2a-114">Ha a RCS környezet már ki lett építve a vállalatnál, akkor a lapon megjelenő URL-címen érheti el.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-114">If RCS environment has been already provisioned to your company, use presented on the page URLs to access it.</span></span> 
7. <span data-ttu-id="f0d2a-115">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-115">Close the page.</span></span> 

## <a name="register-a-new-er-repository"></a><span data-ttu-id="f0d2a-116">Új ER-tárház regisztrálása.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-116">Register a new ER repository.</span></span> 
1. <span data-ttu-id="f0d2a-117">A listában jelölje meg a kiválasztott sort.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-117">In the list, mark the selected row.</span></span> 
2. <span data-ttu-id="f0d2a-118">Válassza ki a Litware, Inc. szolgáltatót.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-118">Select Litware, Inc. provider.</span></span> 
3. <span data-ttu-id="f0d2a-119">Kattintson a Tárházak gombra.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-119">Click Repositories.</span></span> 
4. <span data-ttu-id="f0d2a-120">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-120">Click Add to open the drop dialog.</span></span> 
5. <span data-ttu-id="f0d2a-121">A Konfiguráció tárházának típusa mezőbe írja be az „RCS” értéket.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-121">In the Configuration repository type field, enter 'RCS'.</span></span> 
6. <span data-ttu-id="f0d2a-122">Kattintson a Tárház létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-122">Click Create repository.</span></span> 
7. <span data-ttu-id="f0d2a-123">Az RCS környezet megjelenítése mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-123">In the RCS environment display name field, enter or select a value.</span></span> 
8. <span data-ttu-id="f0d2a-124">Válassza ki a kívánt RCS-példányt.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-124">Select the desired RCS instance.</span></span> <span data-ttu-id="f0d2a-125">Ne feledje, hogy több is lehet.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-125">Note that you can have several of them.</span></span> 
9. <span data-ttu-id="f0d2a-126">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-126">Click OK.</span></span> 

## <a name="import-er-configurations-from-rcs-based-repository"></a><span data-ttu-id="f0d2a-127">ER-konfigurációk importálása az RCS-alapú tárházból</span><span class="sxs-lookup"><span data-stu-id="f0d2a-127">Import ER configurations from RCS based repository</span></span>
1. <span data-ttu-id="f0d2a-128">Kattintson a **Szűrők megjelenítése** pontra.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-128">Click **Show filters**.</span></span> 
2. <span data-ttu-id="f0d2a-129">Adja meg az „RCS” szűrőértéket a **Név** mezőben az **ezzel kezdődik** szűrési operátor használatával.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-129">Enter a filter value of "RCS" on the **Name** field using the **begins with** filter operator.</span></span> 
3. <span data-ttu-id="f0d2a-130">Amikor megnyitja a kiválasztott tárházat a **Csatlakozás a Regulatory Configuration Services szolgáltatáshoz** oldalon, kattintson az **Ide kattintva csatlakozhat a Regulatory Configuration Services szolgáltatáshoz** hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-130">When you open the selected repository, on the **Connect to Regulatory Configuration Services** page, click **Click here to connect to Regulatory Configuration Services** link.</span></span> 
4. <span data-ttu-id="f0d2a-131">Kattintson a **Megnyitás** gombra.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-131">Click **Open**.</span></span> 
5. <span data-ttu-id="f0d2a-132">Kattintson a **Bezárás** gombra.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-132">Click **Close**.</span></span> 
6. <span data-ttu-id="f0d2a-133">Válassza ki az ER-konfiguráció kívánt verzióját, és kattintson az **Importálás** lehetőségre az aktuális példányba való behúzáshoz.</span><span class="sxs-lookup"><span data-stu-id="f0d2a-133">Select the desired version of ER configuration and click **Import** to bring it in the current instance.</span></span>

