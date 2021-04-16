---
title: Alkalmazotti szabadság kezelése
description: Alkalmazotti szabadság kezelése a Dynamics 365 Human Resources alkalmazásban.
author: andreabichsel
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bf27f2a235ddb6c37601ce9d2dd7ceb356a511d9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794685"
---
# <a name="manage-employee-leave"></a><span data-ttu-id="cf942-103">Alkalmazotti szabadság kezelése</span><span class="sxs-lookup"><span data-stu-id="cf942-103">Manage employee leave</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="cf942-104">Az alkalmazottak szabadságát szabadságtípusonként kezelheti.</span><span class="sxs-lookup"><span data-stu-id="cf942-104">You can manage an employee's leave by leave type.</span></span> <span data-ttu-id="cf942-105">Ez magában foglalja a lejáró szabadság hozzárendelését és a szabadságtípus-egyenlegek helyesbítését.</span><span class="sxs-lookup"><span data-stu-id="cf942-105">This includes expiring leave enrollment and adjusting leave type balances.</span></span> 

## <a name="adjust-leave-balances"></a><span data-ttu-id="cf942-106">Szabadság-egyenlegek helyesbítése</span><span class="sxs-lookup"><span data-stu-id="cf942-106">Adjust leave balances</span></span>

1. <span data-ttu-id="cf942-107">Az alkalmazott rekordján válassza a **Szabadság** elemet.</span><span class="sxs-lookup"><span data-stu-id="cf942-107">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="cf942-108">Válassza a **Szabadság és távollét beállítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cf942-108">Select **Leave and absence setup**.</span></span>

3. <span data-ttu-id="cf942-109">Válassza az **Egyenleg helyesbítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cf942-109">Select **Adjust balance**.</span></span>

4. <span data-ttu-id="cf942-110">Válassza ki a **Szabadságtípust**.</span><span class="sxs-lookup"><span data-stu-id="cf942-110">Select the **Leave type**.</span></span>

5. <span data-ttu-id="cf942-111">Adjon meg egy **Kiigazítási összeget**.</span><span class="sxs-lookup"><span data-stu-id="cf942-111">Enter an **Adjustment amount**.</span></span> 

6. <span data-ttu-id="cf942-112">Opcionálisan kiválaszthat egy **Dátumot**.</span><span class="sxs-lookup"><span data-stu-id="cf942-112">Optionally, you can select a **Date**.</span></span> 

<span data-ttu-id="cf942-113">Az alkalmazott szabadságegyenlegének módosításakor az okkódok és a megjegyzések is megadhatók.</span><span class="sxs-lookup"><span data-stu-id="cf942-113">You can include a reason code and comment when adjusting an employee's leave balance.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="cf942-114">A szabadságegyenlegekkel kapcsolatos további információk megtekintése előzetes verzióban érhető el.</span><span class="sxs-lookup"><span data-stu-id="cf942-114">Viewing additional information about leave balances is in preview.</span></span> <span data-ttu-id="cf942-115">Engedélyeznie kell azt a **Tesztkörnyezetében**.</span><span class="sxs-lookup"><span data-stu-id="cf942-115">You'll need to enable it in your **Sandbox** environment.</span></span> <span data-ttu-id="cf942-116">Az előzetes funkciók engedélyezésével kapcsolatos további részletekért tekintse meg a [Kezelési funkciók](hr-admin-manage-features.md) cikket.</span><span class="sxs-lookup"><span data-stu-id="cf942-116">For more information about enabling preview features, see [Manage features](hr-admin-manage-features.md).</span></span><br>
><span data-ttu-id="cf942-117">Ha az egérmutatót a szabadság egyenlege fölé viszi, akkor a következőket fogja látni:</span><span class="sxs-lookup"><span data-stu-id="cf942-117">When hovering over any leave balance, you will now see:</span></span><br>
>- <span data-ttu-id="cf942-118">**Elérhető** : Összesen ebben az évben – Kivett ebben az évben</span><span class="sxs-lookup"><span data-stu-id="cf942-118">**Available**: Total this year - Take this year</span></span>
>- <span data-ttu-id="cf942-119">**Összesen ebben az évben**: Minden elhatárolás, kiigazítás és átvitel az évre</span><span class="sxs-lookup"><span data-stu-id="cf942-119">**Total this year**: All accruals, adjustments, and carry forward for the year</span></span>
>- <span data-ttu-id="cf942-120">**Kivett ebben az évben**: Minden jóváhagyott távollét</span><span class="sxs-lookup"><span data-stu-id="cf942-120">**Taken this year**: All approved time off</span></span>

## <a name="see-also"></a><span data-ttu-id="cf942-121">Lásd még</span><span class="sxs-lookup"><span data-stu-id="cf942-121">See also</span></span>

- [<span data-ttu-id="cf942-122">Szabadság és távollét áttekintése</span><span class="sxs-lookup"><span data-stu-id="cf942-122">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="cf942-123">Szabadság- és távollétkérelmek kezelése</span><span class="sxs-lookup"><span data-stu-id="cf942-123">Manage leave and absence requests</span></span>](hr-employee-self-service-manage-requests.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]