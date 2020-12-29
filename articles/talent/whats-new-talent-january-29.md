---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. január 31.)
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: andreabichsel
manager: AnnBe
ms.date: 01/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-01-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 8e8c11e460a4678efea81f8d3d1eec96b673d329
ms.sourcegitcommit: 53174ed4e7cc4e1ba07cdfc39207e7296ef87c1f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/07/2020
ms.locfileid: "4690052"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-31-2019"></a><span data-ttu-id="aa0a5-103">Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. január 31.)</span><span class="sxs-lookup"><span data-stu-id="aa0a5-103">What's new or changed in Dynamics 365 Talent (January 31, 2019)</span></span>

<span data-ttu-id="aa0a5-104">Ez a témakör a Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.</span><span class="sxs-lookup"><span data-stu-id="aa0a5-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

<span data-ttu-id="aa0a5-105">**Build 8.1.2128**</span><span class="sxs-lookup"><span data-stu-id="aa0a5-105">**Build 8.1.2128**</span></span>

## <a name="core-hr-changes"></a><span data-ttu-id="aa0a5-106">Core HR módosításai</span><span class="sxs-lookup"><span data-stu-id="aa0a5-106">Core HR Changes</span></span>

### <a name="time-off-taken-on-leave-people-card-doesnt-consider-leave-plan-dates"></a><span data-ttu-id="aa0a5-107">Az emberek szabadsága kártyán kivett szabadság nem veszi figyelembe a szabadságterv dátumait</span><span class="sxs-lookup"><span data-stu-id="aa0a5-107">Time off taken on leave people card doesn't consider leave plan dates</span></span>
<span data-ttu-id="aa0a5-108">A nem naptári év szerinti szabadságtervek esetében a **Kivett** kártya megjeleníti a szabadságot, amely a tervben definiált szabadságévben lett kivéve.</span><span class="sxs-lookup"><span data-stu-id="aa0a5-108">For leave plans that don’t run on a calendar year, the **Taken** card now displays time off that’s been taken in the plan-defined leave year.</span></span> <span data-ttu-id="aa0a5-109">Például ha egy szervezet szabadságéve június 1. és május 30. között van és egy alkalmazottnak kivett három napot decemberben, a **Kivett** kártya január 15-én, 3 napot jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="aa0a5-109">For example, if an organization’s leave year is June 1 through May 30 and an employee has taken three days off in December, the **Taken** card on January 15, will display 3 days.</span></span> 

### <a name="accrual-amounts-not-matching-tier-date-basis"></a><span data-ttu-id="aa0a5-110">A könyvelési összegek nem egyeznek szintdátum alapjával</span><span class="sxs-lookup"><span data-stu-id="aa0a5-110">Accrual amounts not matching tier date basis</span></span>
<span data-ttu-id="aa0a5-111">Új lehetőségek lettek hozzáadva szabadsághoz és távolléthez (**Emberierőforrás** paraméterek) , hogy az ügyfelek meghatározhassák, mikor legegyen érvényes a munkavállalók szolgálati hónap dátuma.</span><span class="sxs-lookup"><span data-stu-id="aa0a5-111">New options have been added to leave and absence (**Human resources** parameters) to enable customers to determine when employees’ months of service date are effective.</span></span> <span data-ttu-id="aa0a5-112">Egyes szervezeteknél ez a dátum a hónap vége, de másoknál lehet a következő hónap kezdete.</span><span class="sxs-lookup"><span data-stu-id="aa0a5-112">For some organizations, the date is the end of the month, but for others it may be the start of the next month.</span></span> <span data-ttu-id="aa0a5-113">Például egy szervezet szabadságot ad ki December 31-én, míg a másik január 1-jén.</span><span class="sxs-lookup"><span data-stu-id="aa0a5-113">For example, one organization may award time off on December 31, while another may award time off on January 1.</span></span> <span data-ttu-id="aa0a5-114">Ez a beállítás lehetővé teszi, hogy kiválassza mikor legyen kiadva.</span><span class="sxs-lookup"><span data-stu-id="aa0a5-114">This option will allow you to choose when the award should occur.</span></span> 

### <a name="worker-hire-actions-are-stuck-in-workflow-complete-state"></a><span data-ttu-id="aa0a5-115">Dolgozói felvételi műveletek elakadnak a "Munkafolyamat befejeződött" állapotban.</span><span class="sxs-lookup"><span data-stu-id="aa0a5-115">Worker hire actions are stuck in "Workflow complete" state</span></span>
<span data-ttu-id="aa0a5-116">Módosítások történtek azon hiba javítása érdekében, ahol néhány munkafolyamat a „Munkafolyamat befejeződött” állapottal fejeződött be.</span><span class="sxs-lookup"><span data-stu-id="aa0a5-116">Changes have been made to correct an issue where a small number of workflows finished with a "Workflow complete" status.</span></span> <span data-ttu-id="aa0a5-117">Az munkafolyamatok most átkerülnek a „Befejeződött” állapotba, amikor a munkafolyamat befejeződik.</span><span class="sxs-lookup"><span data-stu-id="aa0a5-117">New workflows should now move to a "Completed" state when the workflow finishes.</span></span> <span data-ttu-id="aa0a5-118">Az összes munkafolyamat befejezve állapotú munkafolyamat hibaállapotba kerül, hogy lehetséges legyen a frissítés vagy eltávolítás.</span><span class="sxs-lookup"><span data-stu-id="aa0a5-118">Any workflows in a workflow completed status will be transitioned to an error status to allow for updating or removal if required.</span></span> 
