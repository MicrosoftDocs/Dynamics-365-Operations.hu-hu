---
title: Projektbecslés figyelmen kívül hagyása
description: Ez a témakör a projektbecslésének a befejezése után történő figyelmen kívül hagyással kapcsolatban tartalmaz tájékoztatást.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: eb323bdeb2a4701cdc9383b8da29e05a4cab107c
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410226"
---
# <a name="eliminate-a-project-estimate"></a><span data-ttu-id="7deb8-103">Projektbecslés figyelmen kívül hagyása</span><span class="sxs-lookup"><span data-stu-id="7deb8-103">Eliminate a project estimate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7deb8-104">A projektbecslés nyújtja a projekthez becsült és ütemezett munka pénzügyi nézőpontját.</span><span class="sxs-lookup"><span data-stu-id="7deb8-104">Project estimates provide the financial view for work that is estimated and scheduled for a project.</span></span> <span data-ttu-id="7deb8-105">Egy projekt becsléseivel akkor lehet dolgozni, ha társította azt egy becsült projekthez.</span><span class="sxs-lookup"><span data-stu-id="7deb8-105">To work with estimates for a project, you must attach the project to an estimate project.</span></span> <span data-ttu-id="7deb8-106">Egy becsült projekt mindig egy létező projekten alapul, ugyanakkor több projekt is tartozhat egyetlen becsült projekthez.</span><span class="sxs-lookup"><span data-stu-id="7deb8-106">An estimate project is always based on an existing project, however multiple projects can refer to a single estimate project.</span></span> <span data-ttu-id="7deb8-107">Csak rögzített árú és beruházási projektek csatolhatók becsült projektekhez, és ezeknek a projekteknek ugyanahhoz a projektcsoporthoz kell tartozniuk, mint a becsült projektnek.</span><span class="sxs-lookup"><span data-stu-id="7deb8-107">Only fixed-price and investment projects can be attached to estimate projects, and those projects must belong to the same project group as the estimate project.</span></span>

<span data-ttu-id="7deb8-108">Becsült projekt figyelmen kívül hagyásához annak késznek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="7deb8-108">To eliminate an estimate project, it must be complete.</span></span> <span data-ttu-id="7deb8-109">A következő lépések azt mutatják be, hogyan lehet egy becslést figyelmen kívül hagyni.</span><span class="sxs-lookup"><span data-stu-id="7deb8-109">The following steps explain how to eliminate an estimate.</span></span>

1. <span data-ttu-id="7deb8-110">Ugorjon a **Projektvezetés és könyvelés** > **Minden projekt** pontra, és nyissa meg a projektet.</span><span class="sxs-lookup"><span data-stu-id="7deb8-110">Go to **Project management and accounting** > **All Projects** and open the project.</span></span> 
2. <span data-ttu-id="7deb8-111">A **Kezelés** lapon válassza ki a **Becsléseket**, és a **Becslés** lapon válassza a **Figyelmen kívül hagyás** elemet.</span><span class="sxs-lookup"><span data-stu-id="7deb8-111">On the **Manage** tab, select **Estimates**, and on the **Estimate** page select **Eliminate**.</span></span>
3. <span data-ttu-id="7deb8-112">Az **Általános** lap **Becslés figyelmen kívül hagyása** lapján adja meg a következő beállításokat:</span><span class="sxs-lookup"><span data-stu-id="7deb8-112">On the **Eliminate estimate** page on the **General** tab, set the following options:</span></span>

   - <span data-ttu-id="7deb8-113">**Időszakkód**: Válassza ki a kiválasztani kívánt becsült projekteknek megfelelő időszakkódot.</span><span class="sxs-lookup"><span data-stu-id="7deb8-113">**Period code**: Select the period code to choose the appropriate estimate projects.</span></span> 
   - <span data-ttu-id="7deb8-114">**Becslés dátuma**: Válassza ki az eltávolítás megfelelő becsült dátumát.</span><span class="sxs-lookup"><span data-stu-id="7deb8-114">**Estimate date**: Select the appropriate estimate date for elimination.</span></span>
   - <span data-ttu-id="7deb8-115">**Eltávolítás befejezetlen termelés figyelmeztetésekkel**: Engedélyezze ezt a beállítást, ha folyamatban lévő munkához társított becslést szeretne figyelmen kívül hagyni.</span><span class="sxs-lookup"><span data-stu-id="7deb8-115">**Eliminate with WIP warnings**: Enable this option to provide notification when an estimate that is associated with a work in progress (WIP) will be eliminated.</span></span> <span data-ttu-id="7deb8-116">Ha ez a beállítás nincs engedélyezve, akkor az eltávolítás nem folytatódhat, ha nem becsült tranzakció létezik.</span><span class="sxs-lookup"><span data-stu-id="7deb8-116">When this option is not enabled, elimination can’t continue if any non-estimated transactions exist.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="7deb8-117">Ez a beállítás csak akkor érhető el, ha az eltávolítást egy becsült projektre alkalmazza a program.</span><span class="sxs-lookup"><span data-stu-id="7deb8-117">This option is available only when elimination is applied to an estimate project.</span></span> <span data-ttu-id="7deb8-118">Nem érhető el, ha ismétlődő feladásokat használ.</span><span class="sxs-lookup"><span data-stu-id="7deb8-118">It is not available if you are using periodic postings.</span></span> <span data-ttu-id="7deb8-119">Ez a beállítás a **Projekt paraméterei** oldal **Becslés** lapjának beállításaival működik, az **Eltávolítás engedélyezése, amikor nem becsült tranzakciók léteznek** mezőcsoportban.</span><span class="sxs-lookup"><span data-stu-id="7deb8-119">This setting works with the settings on the **Estimate** tab on the **Project parameters** page, in the **Allow elimination when non-estimated transactions exist** field group.</span></span>
   - <span data-ttu-id="7deb8-120">**Állapot befejezettre állítása**: Engedélyezze ezt a lehetőséget, ha a becslési projektnek az eltávolítás futtatása után **Befejezett** értékre szeretné állítani az állapotát.</span><span class="sxs-lookup"><span data-stu-id="7deb8-120">**Set stage to Finished**: Enable this option to set the estimate project’s stage to **Finished** after you run the elimination.</span></span>
   - <span data-ttu-id="7deb8-121">**Becsléslista nyomtatása**: Válassza ki, hogy mely adatokat nyomtassa ki a program a becsléslista nyomtatásakor.</span><span class="sxs-lookup"><span data-stu-id="7deb8-121">**Print estimate list**: Select the information to be included when the estimate list is printed.</span></span>
   - <span data-ttu-id="7deb8-122">**Információs napló megjelenítése** : Engedélyezze ezt a beállítást az információs napló megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="7deb8-122">**Show Infolog**: Enable this option to display the Infolog.</span></span>
   - <span data-ttu-id="7deb8-123">**Feladás dátuma** : Válassza ki a becslés főkönyvi feladási dátumát.</span><span class="sxs-lookup"><span data-stu-id="7deb8-123">**Posting date**: Choose the ledger posting date of the estimate.</span></span>

4.  <span data-ttu-id="7deb8-124">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7deb8-124">Select **OK**.</span></span>
5. <span data-ttu-id="7deb8-125">Az eltávolítási folyamat befejezése után az eltávolított becsült projekt negatív értékkel jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="7deb8-125">After the elimination process is complete, the eliminated estimate project is displayed with a negative value.</span></span> 

<span data-ttu-id="7deb8-126">Ha nem szándékosan szűntetett meg egy becslést, akkor kiválaszthatja a megszűntetett becslést, majd az **Eltávolítás sztornírozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7deb8-126">If you did not intend to eliminate an estimate, you can select the eliminated estimate and select **Reverse elimination**.</span></span>   
