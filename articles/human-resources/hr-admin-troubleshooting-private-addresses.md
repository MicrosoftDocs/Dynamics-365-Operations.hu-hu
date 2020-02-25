---
title: Hozzáférés privát címekhez biztonsági szerepkörnek megfelelően
description: Ez a cikk bemutatja az olyan probléma megoldását, amikor a vevő nem fér hozzá a személyes címekhez.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: facfd17f007b2c9e6f068d0ec4c5ce45b85a1b78
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009302"
---
# <a name="access-to-private-addresses-by-security-role"></a><span data-ttu-id="5f0e9-103">Személyes címekhez való hozzáférés biztonsági szerepkörönként</span><span class="sxs-lookup"><span data-stu-id="5f0e9-103">Access to private addresses by security role</span></span>

<span data-ttu-id="5f0e9-104">**Probléma**</span><span class="sxs-lookup"><span data-stu-id="5f0e9-104">**Issue**</span></span>

<span data-ttu-id="5f0e9-105">Miután a vevő duplikál egy biztonsági szerepkört, és az új szerepkörrel jelentkezik be, a vevő nem látja a személyesként megjelölt címeket.</span><span class="sxs-lookup"><span data-stu-id="5f0e9-105">After a customer duplicates a security role and signs in as that new role, the customer can't see addresses that were marked as private.</span></span>

<span data-ttu-id="5f0e9-106">**Felbontás**</span><span class="sxs-lookup"><span data-stu-id="5f0e9-106">**Resolution**</span></span>

<span data-ttu-id="5f0e9-107">A probléma megoldásához a vevőnek az alábbi lépéseket kell követnie a duplikált biztonsági szerepkör esetén.</span><span class="sxs-lookup"><span data-stu-id="5f0e9-107">To resolve the issue, the customer must follow these steps for the duplicated security role.</span></span>

1. <span data-ttu-id="5f0e9-108">Lépjen a **Szervezeti felügyelet \> Globális címjegyzék \> Globális címjegyzék paraméterei** elemre.</span><span class="sxs-lookup"><span data-stu-id="5f0e9-108">Go to **Organization administration \> Global address book \> Global address book parameters**.</span></span>
2. <span data-ttu-id="5f0e9-109">A **Saját hely biztonsága** lapon helyezze át az új biztonsági szerepkört az **Elérhető szerepkörök** listából a **Kijelölt szerepkörök** listájába.</span><span class="sxs-lookup"><span data-stu-id="5f0e9-109">On the **Private location security** tab, move the new security role from the **Available roles** list to the **Selected roles** list.</span></span>
3. <span data-ttu-id="5f0e9-110">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5f0e9-110">Select **Save**.</span></span>

![Globális címjegyzék paraméterei oldal](media/GAD-parameters.png)
