---
title: Hozzáférés privát címekhez biztonsági szerepkörnek megfelelően
description: Ez a cikk bemutatja az olyan probléma megoldását, amikor a vevő nem fér hozzá a személyes címekhez.
author: andreabichsel
manager: tfehr
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
ms.openlocfilehash: 6598094e7877a30c35e1b03794f82c8a4ec001a7
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2021
ms.locfileid: "5112789"
---
# <a name="access-to-private-addresses-by-security-role"></a><span data-ttu-id="73f52-103">Személyes címekhez való hozzáférés biztonsági szerepkörönként</span><span class="sxs-lookup"><span data-stu-id="73f52-103">Access to private addresses by security role</span></span>

<span data-ttu-id="73f52-104">**Probléma**</span><span class="sxs-lookup"><span data-stu-id="73f52-104">**Issue**</span></span>

<span data-ttu-id="73f52-105">Miután a vevő duplikál egy biztonsági szerepkört, és az új szerepkörrel jelentkezik be, a vevő nem látja a személyesként megjelölt címeket.</span><span class="sxs-lookup"><span data-stu-id="73f52-105">After a customer duplicates a security role and signs in as that new role, the customer can't see addresses that were marked as private.</span></span>

<span data-ttu-id="73f52-106">**Felbontás**</span><span class="sxs-lookup"><span data-stu-id="73f52-106">**Resolution**</span></span>

<span data-ttu-id="73f52-107">A probléma megoldásához a vevőnek az alábbi lépéseket kell követnie a duplikált biztonsági szerepkör esetén.</span><span class="sxs-lookup"><span data-stu-id="73f52-107">To resolve the issue, the customer must follow these steps for the duplicated security role.</span></span>

1. <span data-ttu-id="73f52-108">Lépjen a **Szervezeti felügyelet \> Globális címjegyzék \> Globális címjegyzék paraméterei** elemre.</span><span class="sxs-lookup"><span data-stu-id="73f52-108">Go to **Organization administration \> Global address book \> Global address book parameters**.</span></span>
2. <span data-ttu-id="73f52-109">A **Saját hely biztonsága** lapon helyezze át az új biztonsági szerepkört az **Elérhető szerepkörök** listából a **Kijelölt szerepkörök** listájába.</span><span class="sxs-lookup"><span data-stu-id="73f52-109">On the **Private location security** tab, move the new security role from the **Available roles** list to the **Selected roles** list.</span></span>
3. <span data-ttu-id="73f52-110">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="73f52-110">Select **Save**.</span></span>

![Globális címjegyzék paraméterei oldal](media/GAD-parameters.png)
