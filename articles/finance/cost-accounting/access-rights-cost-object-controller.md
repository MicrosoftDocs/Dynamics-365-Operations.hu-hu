---
title: Hozzáférési jogok meghatározása költségobjektum-ellenőrök számára
description: Ez a témakör a költségobjektum-ellenőrök hozzáférési jogairól nyújt tájékoztatást.
author: AndersGirke
manager: AnnBe
ms.date: 06/24/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a1e9ead5a10b3f4e8bb989dd35936945afaf3f29
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178108"
---
# <a name="access-rights-of-a-cost-object-controller"></a><span data-ttu-id="0600d-103">Egy költségobjektum-ellenőr hozzáférési jogai</span><span class="sxs-lookup"><span data-stu-id="0600d-103">Access rights of a cost object controller</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0600d-104">A **Költségkontroll** munkaterület az a központ, ahol a vezetők megtekinthetik a költségobjektumaik teljesítményét.</span><span class="sxs-lookup"><span data-stu-id="0600d-104">The **Cost control** workspace is a central point where managers can view the performance of their cost objects.</span></span> <span data-ttu-id="0600d-105">Ez a munkaterület lehetővé teszi, hogy a vezetők költségkönyvelési adatokat fogyaszthassanak annak ellenére, hogy nem költségkönyvelők.</span><span class="sxs-lookup"><span data-stu-id="0600d-105">This workspace lets managers consume Cost accounting data even though they aren't cost accountants.</span></span> <span data-ttu-id="0600d-106">A vezetőknek biztonsági okokból csak azoknak a Költségkönyvelési adatoknak a megtekintése engedélyezett, amelyek kapcsolódnak azokhoz a költségobjektumokhoz, amelyekért felelősek.</span><span class="sxs-lookup"><span data-stu-id="0600d-106">For security reasons, managers should be allowed to see only the Cost accounting data that is related to the specific cost objects that they are responsible for.</span></span>

<span data-ttu-id="0600d-107">Négy egyedi szerepkör található a Költségkönyvelésben.</span><span class="sxs-lookup"><span data-stu-id="0600d-107">There are four unique roles in Cost accounting.</span></span>

| <span data-ttu-id="0600d-108">Szerepkör neve</span><span class="sxs-lookup"><span data-stu-id="0600d-108">Role name</span></span>               | <span data-ttu-id="0600d-109">Licenc</span><span class="sxs-lookup"><span data-stu-id="0600d-109">License</span></span>      |
|-------------------------|--------------|
| <span data-ttu-id="0600d-110">Költségkönyvelés-kezelő</span><span class="sxs-lookup"><span data-stu-id="0600d-110">Cost accounting manager</span></span> | <span data-ttu-id="0600d-111">Tevékenység</span><span class="sxs-lookup"><span data-stu-id="0600d-111">Activity</span></span>     |
| <span data-ttu-id="0600d-112">Költségkönyvelő munkatárs</span><span class="sxs-lookup"><span data-stu-id="0600d-112">Cost accountant</span></span>         | <span data-ttu-id="0600d-113">Operations</span><span class="sxs-lookup"><span data-stu-id="0600d-113">Operations</span></span>   |
| <span data-ttu-id="0600d-114">Költségkönyvelő adminisztrátor</span><span class="sxs-lookup"><span data-stu-id="0600d-114">Cost accountant clerk</span></span>   | <span data-ttu-id="0600d-115">Operations</span><span class="sxs-lookup"><span data-stu-id="0600d-115">Operations</span></span>   |
| <span data-ttu-id="0600d-116">Költségobjektum-ellenőr</span><span class="sxs-lookup"><span data-stu-id="0600d-116">Cost object controller</span></span>  | <span data-ttu-id="0600d-117">Csapattagok</span><span class="sxs-lookup"><span data-stu-id="0600d-117">Team members</span></span> |

<span data-ttu-id="0600d-118">Ez a témakör megmagyarázza, hogy miként rendelheti hozzá a **Költségobjektum-ellenőr** szerepkört egy vezetőhöz.</span><span class="sxs-lookup"><span data-stu-id="0600d-118">This topic explains how to assign the **Cost object controller** role to a manager.</span></span>

<span data-ttu-id="0600d-119">Ha hozzá van rendelve a **Költségobjektum-ellenőr** szerepkör a vezetőhöz, akkor a következő feladatokat hajthatja végre:</span><span class="sxs-lookup"><span data-stu-id="0600d-119">When the **Cost object controller** role is assigned to a manager, the manager can perform the following tasks:</span></span>

- <span data-ttu-id="0600d-120">A **Költségkontroll** munkaterület elérése (a kliensben).</span><span class="sxs-lookup"><span data-stu-id="0600d-120">Access the **Cost control** workspace (in the client).</span></span>

    - <span data-ttu-id="0600d-121">Részletezés és megtekintési hozzáférés azoknál az oldalaknál, amelyek támogatják a részletezést.</span><span class="sxs-lookup"><span data-stu-id="0600d-121">Drill through and have view access to the pages that support the drill-through experience.</span></span>

- <span data-ttu-id="0600d-122">A **Költségkontroll** munkaterület elérése (a mobilalkalmazásban).</span><span class="sxs-lookup"><span data-stu-id="0600d-122">Access the **Cost control** workspace (in the mobile application).</span></span>

> [!NOTE]
> <span data-ttu-id="0600d-123">A **Költségobjektum-ellenőr** szerepkör nem szabályozza, hogy melyik költségobjektumhoz férhet hozzá a felhasználó, illetve melyiknek nézheti meg az adatait.</span><span class="sxs-lookup"><span data-stu-id="0600d-123">The **Cost object controller** role doesn't control which cost objects the user can access and view data for.</span></span> <span data-ttu-id="0600d-124">A sorszintű biztonság dimenzióhierarchiákon és a hozzáférési lista hierarchiáján keresztül valósul meg.</span><span class="sxs-lookup"><span data-stu-id="0600d-124">Row-level security is provided via dimension hierarchies and the Access list hierarchy.</span></span>

## <a name="grant-access-rights"></a><span data-ttu-id="0600d-125">Hozzáférési jogosultságok megadása</span><span class="sxs-lookup"><span data-stu-id="0600d-125">Grant access rights</span></span>
<span data-ttu-id="0600d-126">A következő példában bemutatjuk, hogyan nézhet ki egy dimenzióhierarchia.</span><span class="sxs-lookup"><span data-stu-id="0600d-126">The following example shows what a dimension hierarchy can look like.</span></span>

<span data-ttu-id="0600d-127">**Dimenzióhierarchia részletei**</span><span class="sxs-lookup"><span data-stu-id="0600d-127">**Dimension hierarchy details**</span></span>

| <span data-ttu-id="0600d-128">Dimenzióhierarchia neve</span><span class="sxs-lookup"><span data-stu-id="0600d-128">Dimension hierarchy name</span></span> | <span data-ttu-id="0600d-129">Dimenzió</span><span class="sxs-lookup"><span data-stu-id="0600d-129">Dimension</span></span>    | <span data-ttu-id="0600d-130">Dimenzióhierarchia típus neve</span><span class="sxs-lookup"><span data-stu-id="0600d-130">Dimension hierarchy type name</span></span>      | <span data-ttu-id="0600d-131">Hozzáférési lista hierarchia</span><span class="sxs-lookup"><span data-stu-id="0600d-131">Access list hierarchy</span></span> |
|--------------------------|--------------|------------------------------------|-----------------------|
| <span data-ttu-id="0600d-132">Szervezet</span><span class="sxs-lookup"><span data-stu-id="0600d-132">Organization</span></span>             | <span data-ttu-id="0600d-133">Költséghelyek</span><span class="sxs-lookup"><span data-stu-id="0600d-133">Cost centers</span></span> | <span data-ttu-id="0600d-134">Dimenzió-osztályozáshierarchia</span><span class="sxs-lookup"><span data-stu-id="0600d-134">Dimension classification hierarchy</span></span> | <span data-ttu-id="0600d-135">**Igen**</span><span class="sxs-lookup"><span data-stu-id="0600d-135">**Yes**</span></span>               |

<span data-ttu-id="0600d-136">A hierarchiatervező **Felhasználók** gyorslapja segítségével egy vagy több felhasználói azonosítót illeszthet minden egyes csomóponthoz.</span><span class="sxs-lookup"><span data-stu-id="0600d-136">You can use the **Users** FastTab in the hierarchy designer to insert one or more user IDs on each node.</span></span>

|                                   | <span data-ttu-id="0600d-137">Felhasználók</span><span class="sxs-lookup"><span data-stu-id="0600d-137">Users</span></span>            | <span data-ttu-id="0600d-138">Dimenziótag tartományok</span><span class="sxs-lookup"><span data-stu-id="0600d-138">Dimension member ranges</span></span>   |                         |
|-----------------------------------|------------------|---------------------------|-------------------------|
| <span data-ttu-id="0600d-139">**Csomópontok**</span><span class="sxs-lookup"><span data-stu-id="0600d-139">**Nodes**</span></span>                         | <span data-ttu-id="0600d-140">**Felhasználói azonosító**</span><span class="sxs-lookup"><span data-stu-id="0600d-140">**User ID**</span></span>      | <span data-ttu-id="0600d-141">**Forrásdimenzió-tag**</span><span class="sxs-lookup"><span data-stu-id="0600d-141">**From dimension member**</span></span> | <span data-ttu-id="0600d-142">**Céldimenziótag**</span><span class="sxs-lookup"><span data-stu-id="0600d-142">**To dimension member**</span></span> |
| <span data-ttu-id="0600d-143">Szervezet</span><span class="sxs-lookup"><span data-stu-id="0600d-143">Organization</span></span>                      | <span data-ttu-id="0600d-144">Benjamin, Claire</span><span class="sxs-lookup"><span data-stu-id="0600d-144">Benjamin, Claire</span></span> |                           |                         |
| <span data-ttu-id="0600d-145">&nbsp;&nbsp;Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="0600d-145">&nbsp;&nbsp;Admin</span></span>                 | <span data-ttu-id="0600d-146">Április</span><span class="sxs-lookup"><span data-stu-id="0600d-146">April</span></span>            |                           |                         |
| <span data-ttu-id="0600d-147">&nbsp;&nbsp;&nbsp;&nbsp;Pénzügy</span><span class="sxs-lookup"><span data-stu-id="0600d-147">&nbsp;&nbsp;&nbsp;&nbsp;Finance</span></span>   | <span data-ttu-id="0600d-148">Alicia</span><span class="sxs-lookup"><span data-stu-id="0600d-148">Alicia</span></span>           | <span data-ttu-id="0600d-149">CC002</span><span class="sxs-lookup"><span data-stu-id="0600d-149">CC002</span></span>                     | <span data-ttu-id="0600d-150">CC003</span><span class="sxs-lookup"><span data-stu-id="0600d-150">CC003</span></span>                   |
|                                   |                  | <span data-ttu-id="0600d-151">CC007</span><span class="sxs-lookup"><span data-stu-id="0600d-151">CC007</span></span>                     | <span data-ttu-id="0600d-152">CC007</span><span class="sxs-lookup"><span data-stu-id="0600d-152">CC007</span></span>                   |
| <span data-ttu-id="0600d-153">&nbsp;&nbsp;&nbsp;&nbsp;HR</span><span class="sxs-lookup"><span data-stu-id="0600d-153">&nbsp;&nbsp;&nbsp;&nbsp;HR</span></span>        | <span data-ttu-id="0600d-154">Anna</span><span class="sxs-lookup"><span data-stu-id="0600d-154">Arnie</span></span>            | <span data-ttu-id="0600d-155">CC001</span><span class="sxs-lookup"><span data-stu-id="0600d-155">CC001</span></span>                     | <span data-ttu-id="0600d-156">CC001</span><span class="sxs-lookup"><span data-stu-id="0600d-156">CC001</span></span>                   |
| <span data-ttu-id="0600d-157">&nbsp;&nbsp;Termelés</span><span class="sxs-lookup"><span data-stu-id="0600d-157">&nbsp;&nbsp;Production</span></span>            | <span data-ttu-id="0600d-158">Dávid</span><span class="sxs-lookup"><span data-stu-id="0600d-158">David</span></span>            |                           |                         |
| <span data-ttu-id="0600d-159">&nbsp;&nbsp;&nbsp;&nbsp;Csomagolás</span><span class="sxs-lookup"><span data-stu-id="0600d-159">&nbsp;&nbsp;&nbsp;&nbsp;Packaging</span></span> | <span data-ttu-id="0600d-160">Verebélyi</span><span class="sxs-lookup"><span data-stu-id="0600d-160">Ellen</span></span>            | <span data-ttu-id="0600d-161">CC005</span><span class="sxs-lookup"><span data-stu-id="0600d-161">CC005</span></span>                     | <span data-ttu-id="0600d-162">CC005</span><span class="sxs-lookup"><span data-stu-id="0600d-162">CC005</span></span>                   |
| <span data-ttu-id="0600d-163">&nbsp;&nbsp;&nbsp;&nbsp;Szerelvény</span><span class="sxs-lookup"><span data-stu-id="0600d-163">&nbsp;&nbsp;&nbsp;&nbsp;Assembly</span></span>  | <span data-ttu-id="0600d-164">Chris</span><span class="sxs-lookup"><span data-stu-id="0600d-164">Chris</span></span>            | <span data-ttu-id="0600d-165">CC006</span><span class="sxs-lookup"><span data-stu-id="0600d-165">CC006</span></span>                     | <span data-ttu-id="0600d-166">CC006</span><span class="sxs-lookup"><span data-stu-id="0600d-166">CC006</span></span>                   |

> [!NOTE]
> <span data-ttu-id="0600d-167">A költségkönyvelőket a hierarchia felső szintjéhez kell rendelni, hogy láthassák az összes költségkönyvelési tételt.</span><span class="sxs-lookup"><span data-stu-id="0600d-167">Cost accountants should be assigned to the top level of the hierarchy, so that they can see all entries in Cost accounting.</span></span>

<span data-ttu-id="0600d-168">Ahhoz, hogy a Hozzáférési lista hierarchia és annak biztonsági beállításai alkalmazhatók legyenek, a **Költségobjektumdimenzió-tagok megtekintési hozzáférésének engedélyezése** lehetőséget **Igen** értékre kell állítani az **Általános** lapon, a **Költségkönyvelés paraméterei** oldalon (**Költségkönyvelés** > **Beállítás** > **Paraméterek**).</span><span class="sxs-lookup"><span data-stu-id="0600d-168">Before the Access list hierarchy and its security settings can be applied, the **Enable view access for cost object dimension members** option must be set to **Yes** on the **General** tab of the **Cost accounting parameters** page (**Cost accounting** > **Setup** > **Parameters**).</span></span>

<span data-ttu-id="0600d-169">A Hozzáférési lista hierarchiájának beállításait használja a rendszer azoknak az adatoknak az irányítására, amelyek a következő területeken jelennek meg:</span><span class="sxs-lookup"><span data-stu-id="0600d-169">The settings for the Access list hierarchy are used to control the data that is shown in following areas:</span></span>

- <span data-ttu-id="0600d-170">**Költségkontroll** munkaterület (a kliensben):</span><span class="sxs-lookup"><span data-stu-id="0600d-170">**Cost control** workspace (in the client):</span></span>

    - <span data-ttu-id="0600d-171">Adatok azokról az oldalakról, amelyeket a részletezésnél használ a rendszer</span><span class="sxs-lookup"><span data-stu-id="0600d-171">Data on the pages that are used for drill-through</span></span>

- <span data-ttu-id="0600d-172">**Költségkontroll** munkaterület (a mobilalkalmazásban):</span><span class="sxs-lookup"><span data-stu-id="0600d-172">**Cost control** workspace (in the mobile application):</span></span>

    - <span data-ttu-id="0600d-173">Egyenlegek a kártyákon</span><span class="sxs-lookup"><span data-stu-id="0600d-173">Balances in cards</span></span>

- <span data-ttu-id="0600d-174">Microsoft Power BI:</span><span class="sxs-lookup"><span data-stu-id="0600d-174">Microsoft Power BI:</span></span>

    - <span data-ttu-id="0600d-175">Adatok, amelyek megjelennek a Power BI ábrázolásaiban</span><span class="sxs-lookup"><span data-stu-id="0600d-175">Data that is shown in Power BI visualizations</span></span>
    - <span data-ttu-id="0600d-176">Az adatok Power BI-megjelenítései, amelyek a Dynamics 365 Finance kliensbe vannak ágyazva</span><span class="sxs-lookup"><span data-stu-id="0600d-176">Data Power BI visualizations that are embedded in the Dynamics 365 Finance client</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="0600d-177">Ahhoz, hogy a Hozzáférési lista hierarchia befolyásolhassa a Power BI adatait, párosítani kell a Hozzáférési lista hierarchiát és a sorszintű biztonságot a Power BI-ben.</span><span class="sxs-lookup"><span data-stu-id="0600d-177">Before the Access list hierarchy can affect data in Power BI, the Access list hierarchy and row-level security in Power BI must be paired.</span></span> <span data-ttu-id="0600d-178">További információ: [Biztonság beállítása a Költségkönyvelés tartalmi csomagban](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)</span><span class="sxs-lookup"><span data-stu-id="0600d-178">For more information, see [Set up security for Cost accounting content pack](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).</span></span>
> - <span data-ttu-id="0600d-179">Ez a témakör azokat az előfeltételeket mutatja be, amelyeknek teljesülniük kell a **Költségkontroll** munkaterület használatához.</span><span class="sxs-lookup"><span data-stu-id="0600d-179">This topic shows the prerequisites that must be in place before you can use the **Cost control** workspace.</span></span>

<span data-ttu-id="0600d-180">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="0600d-180">Additional resources</span></span>

- [<span data-ttu-id="0600d-181">Költségellenőrzési munkaterület</span><span class="sxs-lookup"><span data-stu-id="0600d-181">Cost control workspace</span></span>](cost-control-workspace.md)
- [<span data-ttu-id="0600d-182">Dimenzióhierarchia</span><span class="sxs-lookup"><span data-stu-id="0600d-182">Dimension hierarchy</span></span>](dimension-hierarchy.md)
- [<span data-ttu-id="0600d-183">Biztonság beállítása a Költségkönyvelés tartalmi csomagban</span><span class="sxs-lookup"><span data-stu-id="0600d-183">Set up security for Cost accounting content pack</span></span>](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)
