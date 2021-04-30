---
title: Hozzáférési jogok költségobjektum-ellenőrök számára
description: Ez a témakör a költségobjektum-ellenőrök hozzáférési jogairól nyújt tájékoztatást.
author: AndersGirke
ms.date: 06/24/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: fa8faf0f0f45f901151b3b20a1792b3d8f264fa6
ms.sourcegitcommit: 7d0cfb359a4abc7392ddb3f0b3e9539c40b7204d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/14/2021
ms.locfileid: "5897624"
---
# <a name="access-rights-for-cost-object-controllers"></a><span data-ttu-id="1b958-103">Hozzáférési jogok költségobjektum-ellenőrök számára</span><span class="sxs-lookup"><span data-stu-id="1b958-103">Access rights for cost object controllers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1b958-104">A **Költségkontroll** munkaterület az a központ, ahol a vezetők megtekinthetik a költségobjektumaik teljesítményét.</span><span class="sxs-lookup"><span data-stu-id="1b958-104">The **Cost control** workspace is a central point where managers can view the performance of their cost objects.</span></span> <span data-ttu-id="1b958-105">Ez a munkaterület lehetővé teszi, hogy a vezetők költségkönyvelési adatokat fogyaszthassanak annak ellenére, hogy nem költségkönyvelők.</span><span class="sxs-lookup"><span data-stu-id="1b958-105">This workspace lets managers consume Cost accounting data even though they aren't cost accountants.</span></span> <span data-ttu-id="1b958-106">A vezetőknek biztonsági okokból csak azoknak a Költségkönyvelési adatoknak a megtekintése engedélyezett, amelyek kapcsolódnak azokhoz a költségobjektumokhoz, amelyekért felelősek.</span><span class="sxs-lookup"><span data-stu-id="1b958-106">For security reasons, managers should be allowed to see only the Cost accounting data that is related to the specific cost objects that they are responsible for.</span></span>

<span data-ttu-id="1b958-107">Négy egyedi szerepkör található a Költségkönyvelésben.</span><span class="sxs-lookup"><span data-stu-id="1b958-107">There are four unique roles in Cost accounting.</span></span>

| <span data-ttu-id="1b958-108">Szerepkör neve</span><span class="sxs-lookup"><span data-stu-id="1b958-108">Role name</span></span>               | <span data-ttu-id="1b958-109">Licenc</span><span class="sxs-lookup"><span data-stu-id="1b958-109">License</span></span>      |
|-------------------------|--------------|
| <span data-ttu-id="1b958-110">Költségkönyvelés-kezelő</span><span class="sxs-lookup"><span data-stu-id="1b958-110">Cost accounting manager</span></span> | <span data-ttu-id="1b958-111">Tevékenység</span><span class="sxs-lookup"><span data-stu-id="1b958-111">Activity</span></span>     |
| <span data-ttu-id="1b958-112">Költségkönyvelő munkatárs</span><span class="sxs-lookup"><span data-stu-id="1b958-112">Cost accountant</span></span>         | <span data-ttu-id="1b958-113">Operations</span><span class="sxs-lookup"><span data-stu-id="1b958-113">Operations</span></span>   |
| <span data-ttu-id="1b958-114">Költségkönyvelő adminisztrátor</span><span class="sxs-lookup"><span data-stu-id="1b958-114">Cost accountant clerk</span></span>   | <span data-ttu-id="1b958-115">Operations</span><span class="sxs-lookup"><span data-stu-id="1b958-115">Operations</span></span>   |
| <span data-ttu-id="1b958-116">Költségobjektum-ellenőr</span><span class="sxs-lookup"><span data-stu-id="1b958-116">Cost object controller</span></span>  | <span data-ttu-id="1b958-117">Csapattagok</span><span class="sxs-lookup"><span data-stu-id="1b958-117">Team members</span></span> |

<span data-ttu-id="1b958-118">Ez a témakör megmagyarázza, hogy miként rendelheti hozzá a **Költségobjektum-ellenőr** szerepkört egy vezetőhöz.</span><span class="sxs-lookup"><span data-stu-id="1b958-118">This topic explains how to assign the **Cost object controller** role to a manager.</span></span>

<span data-ttu-id="1b958-119">Ha hozzá van rendelve a **Költségobjektum-ellenőr** szerepkör a vezetőhöz, akkor a következő feladatokat hajthatja végre:</span><span class="sxs-lookup"><span data-stu-id="1b958-119">When the **Cost object controller** role is assigned to a manager, the manager can perform the following tasks:</span></span>

- <span data-ttu-id="1b958-120">A **Költségkontroll** munkaterület elérése (a kliensben).</span><span class="sxs-lookup"><span data-stu-id="1b958-120">Access the **Cost control** workspace (in the client).</span></span>

    - <span data-ttu-id="1b958-121">Részletezés és megtekintési hozzáférés azoknál az oldalaknál, amelyek támogatják a részletezést.</span><span class="sxs-lookup"><span data-stu-id="1b958-121">Drill through and have view access to the pages that support the drill-through experience.</span></span>

- <span data-ttu-id="1b958-122">A **Költségkontroll** munkaterület elérése (a mobilalkalmazásban).</span><span class="sxs-lookup"><span data-stu-id="1b958-122">Access the **Cost control** workspace (in the mobile application).</span></span>

> [!NOTE]
> <span data-ttu-id="1b958-123">A **Költségobjektum-ellenőr** szerepkör nem szabályozza, hogy melyik költségobjektumhoz férhet hozzá a felhasználó, illetve melyiknek nézheti meg az adatait.</span><span class="sxs-lookup"><span data-stu-id="1b958-123">The **Cost object controller** role doesn't control which cost objects the user can access and view data for.</span></span> <span data-ttu-id="1b958-124">A sorszintű biztonság dimenzióhierarchiákon és a hozzáférési lista hierarchiáján keresztül valósul meg.</span><span class="sxs-lookup"><span data-stu-id="1b958-124">Row-level security is provided via dimension hierarchies and the Access list hierarchy.</span></span>

## <a name="grant-access-rights"></a><span data-ttu-id="1b958-125">Hozzáférési jogosultságok megadása</span><span class="sxs-lookup"><span data-stu-id="1b958-125">Grant access rights</span></span>
<span data-ttu-id="1b958-126">A következő példában bemutatjuk, hogyan nézhet ki egy dimenzióhierarchia.</span><span class="sxs-lookup"><span data-stu-id="1b958-126">The following example shows what a dimension hierarchy can look like.</span></span>

<span data-ttu-id="1b958-127">**Dimenzióhierarchia részletei**</span><span class="sxs-lookup"><span data-stu-id="1b958-127">**Dimension hierarchy details**</span></span>

| <span data-ttu-id="1b958-128">Dimenzióhierarchia neve</span><span class="sxs-lookup"><span data-stu-id="1b958-128">Dimension hierarchy name</span></span> | <span data-ttu-id="1b958-129">Dimenzió</span><span class="sxs-lookup"><span data-stu-id="1b958-129">Dimension</span></span>    | <span data-ttu-id="1b958-130">Dimenzióhierarchia típus neve</span><span class="sxs-lookup"><span data-stu-id="1b958-130">Dimension hierarchy type name</span></span>      | <span data-ttu-id="1b958-131">Hozzáférési lista hierarchia</span><span class="sxs-lookup"><span data-stu-id="1b958-131">Access list hierarchy</span></span> |
|--------------------------|--------------|------------------------------------|-----------------------|
| <span data-ttu-id="1b958-132">Szervezet</span><span class="sxs-lookup"><span data-stu-id="1b958-132">Organization</span></span>             | <span data-ttu-id="1b958-133">Költséghelyek</span><span class="sxs-lookup"><span data-stu-id="1b958-133">Cost centers</span></span> | <span data-ttu-id="1b958-134">Dimenzió-osztályozáshierarchia</span><span class="sxs-lookup"><span data-stu-id="1b958-134">Dimension classification hierarchy</span></span> | <span data-ttu-id="1b958-135">**Igen**</span><span class="sxs-lookup"><span data-stu-id="1b958-135">**Yes**</span></span>               |

<span data-ttu-id="1b958-136">A hierarchiatervező **Felhasználók** gyorslapja segítségével egy vagy több felhasználói azonosítót illeszthet minden egyes csomóponthoz.</span><span class="sxs-lookup"><span data-stu-id="1b958-136">You can use the **Users** FastTab in the hierarchy designer to insert one or more user IDs on each node.</span></span>

|             <span data-ttu-id="1b958-137">Csomópontok</span><span class="sxs-lookup"><span data-stu-id="1b958-137">Nodes</span></span>                 | <span data-ttu-id="1b958-138">Felhasználók</span><span class="sxs-lookup"><span data-stu-id="1b958-138">Users</span></span>            | <span data-ttu-id="1b958-139">Forrásdimenzió-tag</span><span class="sxs-lookup"><span data-stu-id="1b958-139">From dimension member</span></span>     |   <span data-ttu-id="1b958-140">Céldimenziótag</span><span class="sxs-lookup"><span data-stu-id="1b958-140">To dimension member</span></span>   |
|-----------------------------------|------------------|---------------------------|-------------------------|
| <span data-ttu-id="1b958-141">Szervezet</span><span class="sxs-lookup"><span data-stu-id="1b958-141">Organization</span></span>                      | <span data-ttu-id="1b958-142">Benjamin, Claire</span><span class="sxs-lookup"><span data-stu-id="1b958-142">Benjamin, Claire</span></span> |                           |                         |
| <span data-ttu-id="1b958-143">&nbsp;&nbsp;Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="1b958-143">&nbsp;&nbsp;Admin</span></span>                 | <span data-ttu-id="1b958-144">Április</span><span class="sxs-lookup"><span data-stu-id="1b958-144">April</span></span>            |                           |                         |
| <span data-ttu-id="1b958-145">&nbsp;&nbsp;&nbsp;&nbsp;Pénzügy</span><span class="sxs-lookup"><span data-stu-id="1b958-145">&nbsp;&nbsp;&nbsp;&nbsp;Finance</span></span>   | <span data-ttu-id="1b958-146">Alicia</span><span class="sxs-lookup"><span data-stu-id="1b958-146">Alicia</span></span>           | <span data-ttu-id="1b958-147">CC002</span><span class="sxs-lookup"><span data-stu-id="1b958-147">CC002</span></span>                     | <span data-ttu-id="1b958-148">CC003</span><span class="sxs-lookup"><span data-stu-id="1b958-148">CC003</span></span>                   |
|                                   |                  | <span data-ttu-id="1b958-149">CC007</span><span class="sxs-lookup"><span data-stu-id="1b958-149">CC007</span></span>                     | <span data-ttu-id="1b958-150">CC007</span><span class="sxs-lookup"><span data-stu-id="1b958-150">CC007</span></span>                   |
| <span data-ttu-id="1b958-151">&nbsp;&nbsp;&nbsp;&nbsp;HR</span><span class="sxs-lookup"><span data-stu-id="1b958-151">&nbsp;&nbsp;&nbsp;&nbsp;HR</span></span>        | <span data-ttu-id="1b958-152">Anna</span><span class="sxs-lookup"><span data-stu-id="1b958-152">Arnie</span></span>            | <span data-ttu-id="1b958-153">CC001</span><span class="sxs-lookup"><span data-stu-id="1b958-153">CC001</span></span>                     | <span data-ttu-id="1b958-154">CC001</span><span class="sxs-lookup"><span data-stu-id="1b958-154">CC001</span></span>                   |
| <span data-ttu-id="1b958-155">&nbsp;&nbsp;Termelés</span><span class="sxs-lookup"><span data-stu-id="1b958-155">&nbsp;&nbsp;Production</span></span>            | <span data-ttu-id="1b958-156">Dávid</span><span class="sxs-lookup"><span data-stu-id="1b958-156">David</span></span>            |                           |                         |
| <span data-ttu-id="1b958-157">&nbsp;&nbsp;&nbsp;&nbsp;Csomagolás</span><span class="sxs-lookup"><span data-stu-id="1b958-157">&nbsp;&nbsp;&nbsp;&nbsp;Packaging</span></span> | <span data-ttu-id="1b958-158">Verebélyi</span><span class="sxs-lookup"><span data-stu-id="1b958-158">Ellen</span></span>            | <span data-ttu-id="1b958-159">CC005</span><span class="sxs-lookup"><span data-stu-id="1b958-159">CC005</span></span>                     | <span data-ttu-id="1b958-160">CC005</span><span class="sxs-lookup"><span data-stu-id="1b958-160">CC005</span></span>                   |
| <span data-ttu-id="1b958-161">&nbsp;&nbsp;&nbsp;&nbsp;Szerelvény</span><span class="sxs-lookup"><span data-stu-id="1b958-161">&nbsp;&nbsp;&nbsp;&nbsp;Assembly</span></span>  | <span data-ttu-id="1b958-162">Chris</span><span class="sxs-lookup"><span data-stu-id="1b958-162">Chris</span></span>            | <span data-ttu-id="1b958-163">CC006</span><span class="sxs-lookup"><span data-stu-id="1b958-163">CC006</span></span>                     | <span data-ttu-id="1b958-164">CC006</span><span class="sxs-lookup"><span data-stu-id="1b958-164">CC006</span></span>                   |

> [!NOTE]
> <span data-ttu-id="1b958-165">A költségkönyvelőket a hierarchia felső szintjéhez kell rendelni, hogy láthassák az összes költségkönyvelési tételt.</span><span class="sxs-lookup"><span data-stu-id="1b958-165">Cost accountants should be assigned to the top level of the hierarchy, so that they can see all entries in Cost accounting.</span></span>

<span data-ttu-id="1b958-166">Ahhoz, hogy a Hozzáférési lista hierarchia és annak biztonsági beállításai alkalmazhatók legyenek, a **Költségobjektumdimenzió-tagok megtekintési hozzáférésének engedélyezése** lehetőséget **Igen** értékre kell állítani az **Általános** lapon, a **Költségkönyvelés paraméterei** oldalon (**Költségkönyvelés** > **Beállítás** > **Paraméterek**).</span><span class="sxs-lookup"><span data-stu-id="1b958-166">Before the Access list hierarchy and its security settings can be applied, the **Enable view access for cost object dimension members** option must be set to **Yes** on the **General** tab of the **Cost accounting parameters** page (**Cost accounting** > **Setup** > **Parameters**).</span></span>

<span data-ttu-id="1b958-167">A Hozzáférési lista hierarchiájának beállításait használja a rendszer azoknak az adatoknak az irányítására, amelyek a következő területeken jelennek meg:</span><span class="sxs-lookup"><span data-stu-id="1b958-167">The settings for the Access list hierarchy are used to control the data that is shown in following areas:</span></span>

- <span data-ttu-id="1b958-168">**Költségkontroll** munkaterület (a kliensben):</span><span class="sxs-lookup"><span data-stu-id="1b958-168">**Cost control** workspace (in the client):</span></span>

    - <span data-ttu-id="1b958-169">Adatok azokról az oldalakról, amelyeket a részletezésnél használ a rendszer</span><span class="sxs-lookup"><span data-stu-id="1b958-169">Data on the pages that are used for drill-through</span></span>

- <span data-ttu-id="1b958-170">**Költségkontroll** munkaterület (a mobilalkalmazásban):</span><span class="sxs-lookup"><span data-stu-id="1b958-170">**Cost control** workspace (in the mobile application):</span></span>

    - <span data-ttu-id="1b958-171">Egyenlegek a kártyákon</span><span class="sxs-lookup"><span data-stu-id="1b958-171">Balances in cards</span></span>

- <span data-ttu-id="1b958-172">Microsoft Power BI:</span><span class="sxs-lookup"><span data-stu-id="1b958-172">Microsoft Power BI:</span></span>

    - <span data-ttu-id="1b958-173">Adatok, amelyek megjelennek a Power BI ábrázolásaiban</span><span class="sxs-lookup"><span data-stu-id="1b958-173">Data that is shown in Power BI visualizations</span></span>
    - <span data-ttu-id="1b958-174">Az adatok Power BI-megjelenítései, amelyek a Dynamics 365 Finance kliensbe vannak ágyazva</span><span class="sxs-lookup"><span data-stu-id="1b958-174">Data Power BI visualizations that are embedded in the Dynamics 365 Finance client</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="1b958-175">Ahhoz, hogy a Hozzáférési lista hierarchia befolyásolhassa a Power BI adatait, párosítani kell a Hozzáférési lista hierarchiát és a sorszintű biztonságot a Power BI-ben.</span><span class="sxs-lookup"><span data-stu-id="1b958-175">Before the Access list hierarchy can affect data in Power BI, the Access list hierarchy and row-level security in Power BI must be paired.</span></span> <span data-ttu-id="1b958-176">További információ: [Biztonság beállítása a Költségkönyvelés tartalmi csomagban](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)</span><span class="sxs-lookup"><span data-stu-id="1b958-176">For more information, see [Set up security for Cost accounting content pack](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).</span></span>
> - <span data-ttu-id="1b958-177">Ez a témakör azokat az előfeltételeket mutatja be, amelyeknek teljesülniük kell a **Költségkontroll** munkaterület használatához.</span><span class="sxs-lookup"><span data-stu-id="1b958-177">This topic shows the prerequisites that must be in place before you can use the **Cost control** workspace.</span></span>

<span data-ttu-id="1b958-178">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="1b958-178">Additional resources</span></span>

- [<span data-ttu-id="1b958-179">Költségellenőrzési munkaterület</span><span class="sxs-lookup"><span data-stu-id="1b958-179">Cost control workspace</span></span>](cost-control-workspace.md)
- [<span data-ttu-id="1b958-180">Dimenzióhierarchia</span><span class="sxs-lookup"><span data-stu-id="1b958-180">Dimension hierarchy</span></span>](dimension-hierarchy.md)
- [<span data-ttu-id="1b958-181">Biztonság beállítása a Költségkönyvelés tartalmi csomagban</span><span class="sxs-lookup"><span data-stu-id="1b958-181">Set up security for Cost accounting content pack</span></span>](../../fin-ops-core/dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
