---
title: Személyes címekhez való hozzáférés biztonsági szerepkörönként
description: Ez a témakör bemutatja a probléma megoldását, amikor a vevő nem fér hozzá a személyes címeket.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f8aaa33e5fda404b48548f9a57977dd0ccd53dc1
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518174"
---
# <a name="access-to-private-addresses-by-security-role"></a><span data-ttu-id="a0c2a-103">Személyes címekhez való hozzáférés biztonsági szerepkörönként</span><span class="sxs-lookup"><span data-stu-id="a0c2a-103">Access to private addresses by security role</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a0c2a-104">**Probléma**</span><span class="sxs-lookup"><span data-stu-id="a0c2a-104">**Issue**</span></span>

<span data-ttu-id="a0c2a-105">Miután a vevő duplikál egy biztonsági szerepkört, és az új szerepkörrel jelentkezik be, a vevő nem látja a személyesként megjelölt címeket.</span><span class="sxs-lookup"><span data-stu-id="a0c2a-105">After a customer duplicates a security role and signs in as that new role, the customer can't see addresses that were marked as private.</span></span>

<span data-ttu-id="a0c2a-106">**Felbontás**</span><span class="sxs-lookup"><span data-stu-id="a0c2a-106">**Resolution**</span></span>

<span data-ttu-id="a0c2a-107">A probléma megoldásához a vevőnek az alábbi lépéseket kell követnie a duplikált biztonsági szerepkör esetén.</span><span class="sxs-lookup"><span data-stu-id="a0c2a-107">To resolve the issue, the customer must follow these steps for the duplicated security role.</span></span>

1. <span data-ttu-id="a0c2a-108">Lépjen a **Szervezeti felügyelet \> Globális címjegyzék \> Globális címjegyzék paraméterei** elemre.</span><span class="sxs-lookup"><span data-stu-id="a0c2a-108">Go to **Organization administration \> Global address book \> Global address book parameters**.</span></span>
2. <span data-ttu-id="a0c2a-109">A **Saját hely biztonsága** lapon helyezze át az új biztonsági szerepkört az **Elérhető szerepkörök** listából a **Kijelölt szerepkörök** listájába.</span><span class="sxs-lookup"><span data-stu-id="a0c2a-109">On the **Private location security** tab, move the new security role from the **Available roles** list to the **Selected roles** list.</span></span>
3. <span data-ttu-id="a0c2a-110">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a0c2a-110">Select **Save**.</span></span>

![Globális címjegyzék paraméterei oldal](media/GAD-parameters.png)
