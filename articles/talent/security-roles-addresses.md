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
ms.openlocfilehash: 58f3322ad64f7de07e17d193ff665bd6536a4070
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897097"
---
# <a name="access-to-private-addresses-by-security-role"></a><span data-ttu-id="8f183-103">Személyes címekhez való hozzáférés biztonsági szerepkörönként</span><span class="sxs-lookup"><span data-stu-id="8f183-103">Access to private addresses by security role</span></span>

<span data-ttu-id="8f183-104">**Probléma**</span><span class="sxs-lookup"><span data-stu-id="8f183-104">**Issue**</span></span>

<span data-ttu-id="8f183-105">Miután a vevő duplikál egy biztonsági szerepkört, és az új szerepkörrel jelentkezik be, a vevő nem látja a személyesként megjelölt címeket.</span><span class="sxs-lookup"><span data-stu-id="8f183-105">After a customer duplicates a security role and signs in as that new role, the customer can't see addresses that were marked as private.</span></span>

<span data-ttu-id="8f183-106">**Felbontás**</span><span class="sxs-lookup"><span data-stu-id="8f183-106">**Resolution**</span></span>

<span data-ttu-id="8f183-107">A probléma megoldásához a vevőnek az alábbi lépéseket kell követnie a duplikált biztonsági szerepkör esetén.</span><span class="sxs-lookup"><span data-stu-id="8f183-107">To resolve the issue, the customer must follow these steps for the duplicated security role.</span></span>

1. <span data-ttu-id="8f183-108">Lépjen a **Szervezeti felügyelet \> Globális címjegyzék \> Globális címjegyzék paraméterei** elemre.</span><span class="sxs-lookup"><span data-stu-id="8f183-108">Go to **Organization administration \> Global address book \> Global address book parameters**.</span></span>
2. <span data-ttu-id="8f183-109">A **Saját hely biztonsága** lapon helyezze át az új biztonsági szerepkört az **Elérhető szerepkörök** listából a **Kijelölt szerepkörök** listájába.</span><span class="sxs-lookup"><span data-stu-id="8f183-109">On the **Private location security** tab, move the new security role from the **Available roles** list to the **Selected roles** list.</span></span>
3. <span data-ttu-id="8f183-110">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="8f183-110">Select **Save**.</span></span>

![Globális címjegyzék paraméterei oldal](media/GAD-parameters.png)
