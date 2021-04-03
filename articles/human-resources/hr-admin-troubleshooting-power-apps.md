---
title: Nem lehet környezetet létrehozni a Power Apps felügyeleti központjában
description: Ez a cikk bemutatja, hogy mi a teendő olyankor, ha a rendszergazda nem tud környezetet létrehozni a Microsoft Power Apps felügyeleti központban.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ec63148364022fe5b8c40d855856eec232af3e48
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463960"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a><span data-ttu-id="f3180-103">Nem lehet környezetet létrehozni a Power Apps felügyeleti központjában</span><span class="sxs-lookup"><span data-stu-id="f3180-103">Can't create an environment in the Power Apps Admin center</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f3180-104">**Kibocsátás**</span><span class="sxs-lookup"><span data-stu-id="f3180-104">**Issue**</span></span>

- <span data-ttu-id="f3180-105">A bérlő/környezet-rendszergazda nem tud környezetet létrehozni a Microsoft Power Apps felügyeleti központban.</span><span class="sxs-lookup"><span data-stu-id="f3180-105">The tenant/environment admin can't create an environment in the Microsoft Power Apps Admin center.</span></span>
- <span data-ttu-id="f3180-106">A felhasználónak nincs olyan licence, amely lehetővé teszi környezetek létrehozását.</span><span class="sxs-lookup"><span data-stu-id="f3180-106">The user doesn't have a license that gives the right to create environments.</span></span>

<span data-ttu-id="f3180-107">**Megoldás**</span><span class="sxs-lookup"><span data-stu-id="f3180-107">**Solution**</span></span>

<span data-ttu-id="f3180-108">Győződjön meg arról, hogy a bérlői rendszergazda érvényes Power Apps P2-licencet rendelt a környezetet létrehozó felhasználóhoz.</span><span class="sxs-lookup"><span data-stu-id="f3180-108">Make sure the tenant admin has assigned a valid Power Apps P2 license to the user creating the environment.</span></span> <span data-ttu-id="f3180-109">A következő Microsoft Dynamics szolgáltatási tervek nyújtanak engedélyeket környezetek létrehozásához:</span><span class="sxs-lookup"><span data-stu-id="f3180-109">The following Microsoft Dynamics service plans provide permissions to create environments:</span></span>

| <span data-ttu-id="f3180-110">Teljes termékraktározási egység (SKU)</span><span class="sxs-lookup"><span data-stu-id="f3180-110">Overall product stockkeeping unit (SKU)</span></span>       | <span data-ttu-id="f3180-111">Power Apps P2-szolgáltatási terv</span><span class="sxs-lookup"><span data-stu-id="f3180-111">Power Apps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="f3180-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="f3180-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="f3180-113">Power Apps for Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="f3180-113">Power Apps for Dynamics 365</span></span> |
| <span data-ttu-id="f3180-114">Microsoft Dynamics 365 csomag Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f3180-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="f3180-115">Power Apps for Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="f3180-115">Power Apps for Dynamics 365</span></span> |

<span data-ttu-id="f3180-116">Felhívjuk figyelmét, hogy a különböző Microsoft Office-raktározási egységek (SKU-k) szintén biztosítják a jogot az önálló Power Apps Plan 2 raktározási egységekkel.</span><span class="sxs-lookup"><span data-stu-id="f3180-116">Note that various Microsoft Office SKUs also provide the right, together with standalone Power Apps Plan 2 SKUs.</span></span> <span data-ttu-id="f3180-117">Az a fontos, hogy ezek közül a raktározási egységek közül egy legyen jelen.</span><span class="sxs-lookup"><span data-stu-id="f3180-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="f3180-118">Ugorjon ide: [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="f3180-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="f3180-119">Hozzon létre környezeteket az alábbi utasítások követésével: [Human Resources környezet létesítése](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="f3180-119">Create the environments by following the instructions in [Provision Human Resources](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]