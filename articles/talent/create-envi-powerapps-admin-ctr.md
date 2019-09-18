---
title: Nem lehet környezetet létrehozni a PowerApps felügyeleti központban
description: Ez a témakör bemutatja, mi a teendő, ha a rendszergazda nem tud környezetet létrehozni a Microsoft PowerApps felügyeleti központban.
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
ms.openlocfilehash: 96119ca869cbbb15ed8d8d5d0fe3b0f94b5f36cc
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742842"
---
# <a name="cant-create-an-environment-in-the-powerapps-admin-center"></a><span data-ttu-id="ebbea-103">Nem lehet környezetet létrehozni a PowerApps felügyeleti központjában</span><span class="sxs-lookup"><span data-stu-id="ebbea-103">Can't create an environment in the PowerApps Admin center</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ebbea-104">**Probléma**</span><span class="sxs-lookup"><span data-stu-id="ebbea-104">**Issue**</span></span>

- <span data-ttu-id="ebbea-105">A bérlő/környezet-rendszergazda nem tud környezetet létrehozni a Microsoft PowerApps felügyeleti központban.</span><span class="sxs-lookup"><span data-stu-id="ebbea-105">The tenant/environment admin can't create an environment in the Microsoft PowerApps Admin center.</span></span>
- <span data-ttu-id="ebbea-106">Az engedélyt, amely jogot biztosít a felhasználóknak, hogy végrehajtsák a környezet-létrehozás lépését, még nem rendelték közvetlenül a felhasználóhoz, aki az adott lépést végrehajtja.</span><span class="sxs-lookup"><span data-stu-id="ebbea-106">A licence that gives users the right to perform the environment creation step hasn't been assigned directly to the user who is performing that step.</span></span>

<span data-ttu-id="ebbea-107">**Megoldás**</span><span class="sxs-lookup"><span data-stu-id="ebbea-107">**Solution**</span></span>

<span data-ttu-id="ebbea-108">Győződjön meg arról, hogy a helyi rendszergazdához hozzárendelt egy érvényes PowerApps P2-licencet közvetlenül a felhasználóhoz, aki végrehajtja a környezet-létrehozás lépését.</span><span class="sxs-lookup"><span data-stu-id="ebbea-108">Make sure that the tenant admin has assigned a valid PowerApps P2 license directly to the user who will perform the environment creation step.</span></span> <span data-ttu-id="ebbea-109">A következő Microsoft Dynamics szolgáltatási tervek biztosítják ezt a jogot.</span><span class="sxs-lookup"><span data-stu-id="ebbea-109">Here are the Microsoft Dynamics service plans that provide that right.</span></span>

| <span data-ttu-id="ebbea-110">Teljes termékraktározási egység (SKU)</span><span class="sxs-lookup"><span data-stu-id="ebbea-110">Overall product stock keeping unit (SKU)</span></span>       | <span data-ttu-id="ebbea-111">PowerApps P2 szolgáltatásterv</span><span class="sxs-lookup"><span data-stu-id="ebbea-111">PowerApps P2 service plan</span></span>  |
|------------------------------------------------|----------------------------|
| <span data-ttu-id="ebbea-112">Microsoft Dynamics 365 for Operations</span><span class="sxs-lookup"><span data-stu-id="ebbea-112">Microsoft Dynamics 365 for Operations</span></span>          | <span data-ttu-id="ebbea-113">PowerApps for Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ebbea-113">PowerApps for Dynamics 365</span></span> |
| <span data-ttu-id="ebbea-114">Microsoft Dynamics 365 csomag Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="ebbea-114">Microsoft Dynamics 365 Plan Enterprise Edition</span></span> | <span data-ttu-id="ebbea-115">PowerApps for Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ebbea-115">PowerApps for Dynamics 365</span></span> |

<span data-ttu-id="ebbea-116">Felhívjuk figyelmét, hogy a különböző Microsoft Office raktározási egységek (SKU-k) szintén biztosítják a jogot, az egyedülálló PowerApps csomag 2 raktározási egységekkel együtt.</span><span class="sxs-lookup"><span data-stu-id="ebbea-116">Note that various Microsoft Office SKUs also provide the right, together with standalone PowerApps Plan 2 SKUs.</span></span> <span data-ttu-id="ebbea-117">Az a fontos, hogy ezek közül a raktározási egységek közül egy legyen jelen.</span><span class="sxs-lookup"><span data-stu-id="ebbea-117">The important point is that one of these SKUs must be present.</span></span>

1. <span data-ttu-id="ebbea-118">Ugorjon ide: [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span><span class="sxs-lookup"><span data-stu-id="ebbea-118">Go to [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).</span></span>
2. <span data-ttu-id="ebbea-119">Hozzon létre környezeteket a következő helyen található utasítások követésével: [A Talent létesítése](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="ebbea-119">Create the environments by following the instructions in [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>
