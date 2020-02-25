---
title: Nem lehet környezetet létrehozni a Power Apps felügyeleti központjában
description: Ez a cikk bemutatja, hogy mi a teendő olyankor, ha a rendszergazda nem tud környezetet létrehozni a Microsoft Power Apps felügyeleti központban.
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: f4c75706183a3d6c961852395e464d46ba3ec1f2
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009246"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a><span data-ttu-id="e0dc7-103">Nem lehet környezetet létrehozni a Power Apps felügyeleti központjában</span><span class="sxs-lookup"><span data-stu-id="e0dc7-103">Can't create an environment in the Power Apps Admin center</span></span>

<span data-ttu-id="e0dc7-104">**Kibocsátás**</span><span class="sxs-lookup"><span data-stu-id="e0dc7-104">**Issue**</span></span>

- <span data-ttu-id="e0dc7-105">A bérlő/környezet-rendszergazda nem tud környezetet létrehozni a Microsoft Power Apps felügyeleti központban.</span><span class="sxs-lookup"><span data-stu-id="e0dc7-105">The tenant/environment admin can't create an environment in the Microsoft Power Apps Admin center.</span></span>
- <span data-ttu-id="e0dc7-106">Az engedélyt, amely jogot biztosít a felhasználóknak, hogy végrehajtsák a környezet-létrehozás lépését, még nem rendelték közvetlenül a felhasználóhoz, aki az adott lépést végrehajtja.</span><span class="sxs-lookup"><span data-stu-id="e0dc7-106">A licence that gives users the right to perform the environment creation step hasn't been assigned directly to the user who is performing that step.</span></span>

<span data-ttu-id="e0dc7-107">**Megoldás**</span><span class="sxs-lookup"><span data-stu-id="e0dc7-107">**Solution**</span></span>

<span data-ttu-id="e0dc7-108">Győződjön meg arról, hogy a bérlő adminisztrátor hozzárendelt érvényes Power Apps P2-licencet közvetlenül ahhoz a felhasználóhoz, aki végrehajtja a környezet létrehozási lépését.</span><span class="sxs-lookup"><span data-stu-id="e0dc7-108">Make sure that the tenant admin has assigned a valid Power Apps P2 license directly to the user who will perform the environment creation step.</span></span> <span data-ttu-id="e0dc7-109">A következő Microsoft Dynamics szolgáltatási tervek biztosítják ezt a jogot.</span><span class="sxs-lookup"><span data-stu-id="e0dc7-109">Here are the Microsoft Dynamics service plans that provide that right.</span></span>

| <span data-ttu-id="e0dc7-110">Teljes termékraktározási egység (SKU)</span><span class="sxs-lookup"><span data-stu-id="e0dc7-110">Overall product stock keeping unit (SKU)</span></span>       | <span data-ttu-id="e0dc7-111">Power Apps P2-szolgáltatási terv</span><span class="sxs-lookup"><span data-stu-id="e0dc7-111">Power Apps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="e0dc7-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="e0dc7-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="e0dc7-113">Power Apps for Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e0dc7-113">Power Apps for Dynamics 365</span></span> |
| <span data-ttu-id="e0dc7-114">Microsoft Dynamics 365 csomag Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e0dc7-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="e0dc7-115">Power Apps for Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e0dc7-115">Power Apps for Dynamics 365</span></span> |

<span data-ttu-id="e0dc7-116">Felhívjuk figyelmét, hogy a különböző Microsoft Office-raktározási egységek (SKU-k) szintén biztosítják a jogot az önálló Power Apps Plan 2 raktározási egységekkel.</span><span class="sxs-lookup"><span data-stu-id="e0dc7-116">Note that various Microsoft Office SKUs also provide the right, together with standalone Power Apps Plan 2 SKUs.</span></span> <span data-ttu-id="e0dc7-117">Az a fontos, hogy ezek közül a raktározási egységek közül egy legyen jelen.</span><span class="sxs-lookup"><span data-stu-id="e0dc7-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="e0dc7-118">Ugorjon ide: [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="e0dc7-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="e0dc7-119">Hozzon létre környezeteket az alábbi utasítások követésével: [Human Resources környezet létesítése](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="e0dc7-119">Create the environments by following the instructions in [Provision Human Resources](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>
