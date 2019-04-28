---
title: Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. január 31.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
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
ms.author: dkrame
ms.search.validFrom: 2019-01-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d4504cebb7702c7163c94badeeb06d9af0e5467e
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/19/2019
ms.locfileid: "857638"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-january-31-2019"></a><span data-ttu-id="32684-103">Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban (2019. január 31.)</span><span class="sxs-lookup"><span data-stu-id="32684-103">What's new or changed in Dynamics 365 for Talent (January 31, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="32684-104">Ez a témakör a Dynamics 365 for Talent új vagy módosított szolgáltatásait írja le.</span><span class="sxs-lookup"><span data-stu-id="32684-104">This topic describes features that are either new or changed in Dynamics 365 for Talent</span></span>

<span data-ttu-id="32684-105">**Build 8.1.2128**</span><span class="sxs-lookup"><span data-stu-id="32684-105">**Build 8.1.2128**</span></span>

## <a name="core-hr-changes"></a><span data-ttu-id="32684-106">Core HR módosításai</span><span class="sxs-lookup"><span data-stu-id="32684-106">Core HR Changes</span></span>

### <a name="time-off-taken-on-leave-people-card-doesnt-consider-leave-plan-dates"></a><span data-ttu-id="32684-107">Az emberek szabadsága kártyán kivett szabadság nem veszi figyelembe a szabadságterv dátumait</span><span class="sxs-lookup"><span data-stu-id="32684-107">Time off taken on leave people card doesn't consider leave plan dates</span></span>
<span data-ttu-id="32684-108">Azoknál akiknek szabadságterve nem naptári év szerinti a **Kivett** kártya megjeleníti a szabadságot, amely a tervben definiált szabadságévben lett kivéve.</span><span class="sxs-lookup"><span data-stu-id="32684-108">For those that have leave plans that don’t run on a calendar year, the **Taken** card now displays time off that’s been taken in the plan-defined leave year.</span></span> <span data-ttu-id="32684-109">Például ha egy szervezet szabadságéve június 1. és május 30. között van és egy alkalmazottnak kivett 3 napot decemberben, a **Kivett** kártya január 15-én, 3 napot jelenít meg.</span><span class="sxs-lookup"><span data-stu-id="32684-109">For example, if an organization’s leave year is June 1 through May 30 and an employee has taken 3 days off in December, the **Taken** card on January 15, will display 3 days.</span></span> 

### <a name="accrual-amounts-not-matching-tier-date-basis"></a><span data-ttu-id="32684-110">A könyvelési összegek nem egyeznek szintdátum alapjával</span><span class="sxs-lookup"><span data-stu-id="32684-110">Accrual amounts not matching tier date basis</span></span>
<span data-ttu-id="32684-111">Új lehetőségek lettek hozzáadva szabadsághoz és távolléthez (**Emberierőforrás** paraméterek) , hogy az ügyfelek meghatározhassák, mikor legegyen érvényes a munkavállalók szolgálati hónap dátuma.</span><span class="sxs-lookup"><span data-stu-id="32684-111">New options have been added to leave and absence (**Human resources** parameters) to enable customers to determine when employees’ months of service date are effective.</span></span> <span data-ttu-id="32684-112">Egyes szervezeteknél ez a dátum a hónap vége, de másoknál lehet a következő hónap kezdete.</span><span class="sxs-lookup"><span data-stu-id="32684-112">For some organizations, the date is the end of the month, but for others it may be the start of the next month.</span></span> <span data-ttu-id="32684-113">Például egy szervezet szabadságot ad ki December 31-én, míg a másik január 1-jén.</span><span class="sxs-lookup"><span data-stu-id="32684-113">For example, one organization may award time off on December 31, while another may award time off on January 1.</span></span> <span data-ttu-id="32684-114">Ez a beállítás lehetővé teszi, hogy kiválassza mikor legyen kiadva.</span><span class="sxs-lookup"><span data-stu-id="32684-114">This option will allow you to choose when the award should occur.</span></span> 

### <a name="worker-hire-actions-are-stuck-in-workflow-complete-state"></a><span data-ttu-id="32684-115">Dolgozói felvételi műveletek elakadnak a "Munkafolyamat befejeződött" állapotban.</span><span class="sxs-lookup"><span data-stu-id="32684-115">Worker hire actions are stuck in "Workflow complete" state</span></span>
<span data-ttu-id="32684-116">Módosítások történtek azon hiba javítása érdekében, ahol néhány munkafolyamat a „Munkafolyamat befejeződött” állapottal fejeződött be.</span><span class="sxs-lookup"><span data-stu-id="32684-116">Changes have been made to correct an issue where a small number of workflows finished with a "Workflow complete" status.</span></span> <span data-ttu-id="32684-117">Az munkafolyamatok most átkerülnek a „Befejeződött” állapotba, amikor a munkafolyamat befejeződik.</span><span class="sxs-lookup"><span data-stu-id="32684-117">New workflows should now move to a "Completed" state when the workflow finishes.</span></span> <span data-ttu-id="32684-118">Az összes munkafolyamat befejezve állapotú munkafolyamat hibaállapotba kerül, hogy lehetséges legyen a frissítés vagy eltávolítás.</span><span class="sxs-lookup"><span data-stu-id="32684-118">Any workflows in a workflow completed status will be transitioned to an error status to allow for updating or removal if required.</span></span> 
