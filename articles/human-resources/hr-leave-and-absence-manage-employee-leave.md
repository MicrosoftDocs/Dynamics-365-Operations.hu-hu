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
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 33080fc5ca43f3d83ee9d17565f4c229ced7b94f
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055628"
---
# <a name="manage-employee-leave"></a><span data-ttu-id="1c980-103">Alkalmazotti szabadság kezelése</span><span class="sxs-lookup"><span data-stu-id="1c980-103">Manage employee leave</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="1c980-104">Az alkalmazottak szabadságát szabadságtípusonként kezelheti.</span><span class="sxs-lookup"><span data-stu-id="1c980-104">You can manage an employee's leave by leave type.</span></span> <span data-ttu-id="1c980-105">Ez magában foglalja a lejáró szabadság hozzárendelését és a szabadságtípus-egyenlegek helyesbítését.</span><span class="sxs-lookup"><span data-stu-id="1c980-105">This includes expiring leave enrollment and adjusting leave type balances.</span></span> 

## <a name="adjust-leave-balances"></a><span data-ttu-id="1c980-106">Szabadság-egyenlegek helyesbítése</span><span class="sxs-lookup"><span data-stu-id="1c980-106">Adjust leave balances</span></span>

1. <span data-ttu-id="1c980-107">Az alkalmazott rekordján válassza a **Szabadság** elemet.</span><span class="sxs-lookup"><span data-stu-id="1c980-107">On the employee's record, select **Leave**.</span></span>

2. <span data-ttu-id="1c980-108">Válassza a **Szabadság és távollét beállítása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1c980-108">Select **Leave and absence setup**.</span></span>

3. <span data-ttu-id="1c980-109">Válassza az **Egyenleg helyesbítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1c980-109">Select **Adjust balance**.</span></span>

4. <span data-ttu-id="1c980-110">Válassza ki a **Szabadságtípust**.</span><span class="sxs-lookup"><span data-stu-id="1c980-110">Select the **Leave type**.</span></span>

5. <span data-ttu-id="1c980-111">Adjon meg egy **Kiigazítási összeget**.</span><span class="sxs-lookup"><span data-stu-id="1c980-111">Enter an **Adjustment amount**.</span></span> 

6. <span data-ttu-id="1c980-112">Opcionálisan kiválaszthat egy **Dátumot**.</span><span class="sxs-lookup"><span data-stu-id="1c980-112">Optionally, you can select a **Date**.</span></span> 

<span data-ttu-id="1c980-113">Az alkalmazott szabadságegyenlegének módosításakor az okkódok és a megjegyzések is megadhatók.</span><span class="sxs-lookup"><span data-stu-id="1c980-113">You can include a reason code and comment when adjusting an employee's leave balance.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="1c980-114">A szabadságegyenlegekkel kapcsolatos további információk megtekintése előzetes verzióban érhető el.</span><span class="sxs-lookup"><span data-stu-id="1c980-114">Viewing additional information about leave balances is in preview.</span></span> <span data-ttu-id="1c980-115">Engedélyeznie kell azt a **Tesztkörnyezetében**.</span><span class="sxs-lookup"><span data-stu-id="1c980-115">You'll need to enable it in your **Sandbox** environment.</span></span> <span data-ttu-id="1c980-116">Az előzetes funkciók engedélyezésével kapcsolatos további részletekért tekintse meg a [Kezelési funkciók](hr-admin-manage-features.md) cikket.</span><span class="sxs-lookup"><span data-stu-id="1c980-116">For more information about enabling preview features, see [Manage features](hr-admin-manage-features.md).</span></span><br>
><span data-ttu-id="1c980-117">Ha az egérmutatót a szabadság egyenlege fölé viszi, akkor a következőket fogja látni:</span><span class="sxs-lookup"><span data-stu-id="1c980-117">When hovering over any leave balance, you will now see:</span></span><br>
>- <span data-ttu-id="1c980-118">**Elérhető** : Összesen ebben az évben – Kivett ebben az évben</span><span class="sxs-lookup"><span data-stu-id="1c980-118">**Available**: Total this year - Take this year</span></span>
>- <span data-ttu-id="1c980-119">**Összesen ebben az évben**: Minden elhatárolás, kiigazítás és átvitel az évre</span><span class="sxs-lookup"><span data-stu-id="1c980-119">**Total this year**: All accruals, adjustments, and carry forward for the year</span></span>
>- <span data-ttu-id="1c980-120">**Kivett ebben az évben**: Minden jóváhagyott távollét</span><span class="sxs-lookup"><span data-stu-id="1c980-120">**Taken this year**: All approved time off</span></span>

## <a name="see-also"></a><span data-ttu-id="1c980-121">Lásd még</span><span class="sxs-lookup"><span data-stu-id="1c980-121">See also</span></span>

- [<span data-ttu-id="1c980-122">Szabadság és távollét áttekintése</span><span class="sxs-lookup"><span data-stu-id="1c980-122">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="1c980-123">Szabadság- és távollétkérelmek kezelése</span><span class="sxs-lookup"><span data-stu-id="1c980-123">Manage leave and absence requests</span></span>](hr-employee-self-service-manage-requests.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]