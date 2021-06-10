---
title: Hozzáférés privát címekhez biztonsági szerepkörnek megfelelően
description: Ez a cikk bemutatja az olyan probléma megoldását, amikor a vevő nem fér hozzá a személyes címekhez.
author: andreabichsel
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2edcef338f0ff8fcf231d4314fc972284397d000
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053323"
---
# <a name="access-to-private-addresses-by-security-role"></a><span data-ttu-id="b90a5-103">Személyes címekhez való hozzáférés biztonsági szerepkörönként</span><span class="sxs-lookup"><span data-stu-id="b90a5-103">Access to private addresses by security role</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="b90a5-104">**Probléma**</span><span class="sxs-lookup"><span data-stu-id="b90a5-104">**Issue**</span></span>

<span data-ttu-id="b90a5-105">Miután a vevő duplikál egy biztonsági szerepkört, és az új szerepkörrel jelentkezik be, a vevő nem látja a személyesként megjelölt címeket.</span><span class="sxs-lookup"><span data-stu-id="b90a5-105">After a customer duplicates a security role and signs in as that new role, the customer can't see addresses that were marked as private.</span></span>

<span data-ttu-id="b90a5-106">**Felbontás**</span><span class="sxs-lookup"><span data-stu-id="b90a5-106">**Resolution**</span></span>

<span data-ttu-id="b90a5-107">A probléma megoldásához a vevőnek az alábbi lépéseket kell követnie a duplikált biztonsági szerepkör esetén.</span><span class="sxs-lookup"><span data-stu-id="b90a5-107">To resolve the issue, the customer must follow these steps for the duplicated security role.</span></span>

1. <span data-ttu-id="b90a5-108">Lépjen a **Szervezeti felügyelet \> Globális címjegyzék \> Globális címjegyzék paraméterei** elemre.</span><span class="sxs-lookup"><span data-stu-id="b90a5-108">Go to **Organization administration \> Global address book \> Global address book parameters**.</span></span>
2. <span data-ttu-id="b90a5-109">A **Saját hely biztonsága** lapon helyezze át az új biztonsági szerepkört az **Elérhető szerepkörök** listából a **Kijelölt szerepkörök** listájába.</span><span class="sxs-lookup"><span data-stu-id="b90a5-109">On the **Private location security** tab, move the new security role from the **Available roles** list to the **Selected roles** list.</span></span>
3. <span data-ttu-id="b90a5-110">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b90a5-110">Select **Save**.</span></span>

![Globális címjegyzék paraméterei oldal](media/GAD-parameters.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]