---
title: E-kereskedelmi fejlesztői környezet beállítása 1. szintű Retail Server virtuális géppel való hibakereséshez
description: Ez a témakör bemutatja, hogyan állíthat be e-kereskedelmi fejlesztői környezetet 1. szintű Retail Server virtuális géppel (VM) való hibakereséshez.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 35380a559a4f1b22bdf04ff25cb2bbfc51aff45b
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585348"
---
# <a name="set-up-an-e-commerce-development-environment-to-debug-against-a-tier-1-retail-server-virtual-machine"></a><span data-ttu-id="fa919-103">E-kereskedelmi fejlesztői környezet beállítása 1. szintű Retail Server virtuális géppel való hibakereséshez</span><span class="sxs-lookup"><span data-stu-id="fa919-103">Set up an e-commerce development environment to debug against a Tier 1 Retail Server virtual machine</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fa919-104">Ez a témakör bemutatja, hogyan állíthat be e-kereskedelmi fejlesztői környezetet 1. szintű Retail Server virtuális géppel (VM) való hibakereséshez.</span><span class="sxs-lookup"><span data-stu-id="fa919-104">This topic explains how to set up an e-commerce development environment to debug against a Tier 1 Retail Server virtual machine (VM).</span></span>

## <a name="description"></a><span data-ttu-id="fa919-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="fa919-105">Description</span></span>

<span data-ttu-id="fa919-106">A Microsoft Dynamics 365 Commerce 1. szintű környezeteket általában Commerce Runtime (CRT) és pénztári (POS) bővítmény fejlesztéséhez kell telepíteni.</span><span class="sxs-lookup"><span data-stu-id="fa919-106">Microsoft Dynamics 365 Commerce Tier 1 environments are typically deployed for Commerce runtime (CRT) and point of sale (POS) extension development.</span></span> <span data-ttu-id="fa919-107">Ezek különálló környezetek.</span><span class="sxs-lookup"><span data-stu-id="fa919-107">They are standalone environments.</span></span> <span data-ttu-id="fa919-108">A szoftver szolgáltatásként (SaaS) architektúra jellege miatt nem tartalmaznak e-kereskedelmi összetevőket.</span><span class="sxs-lookup"><span data-stu-id="fa919-108">Because of the software as a service (SaaS) nature of the architecture, they don't include e-commerce components.</span></span>

<span data-ttu-id="fa919-109">Bizonyos helyzetekben az 1. szintű környezetben érdemes tesztelni a bővítmények hívásait, hogy az e-kereskedelmi összetevőkből elvégezhesse a bővítmények hibakeresését.</span><span class="sxs-lookup"><span data-stu-id="fa919-109">In some scenarios, you might want to test calls to extensions in a Tier 1 environment, so that you can debug extensions from e-commerce components.</span></span> <span data-ttu-id="fa919-110">Általános tudnivalók: [Hibakeresés az 1. szintű Commerce fejlesztői környezetben](../e-commerce-extensibility/debug-tier-1.md).</span><span class="sxs-lookup"><span data-stu-id="fa919-110">For general instructions, see [Debug against a Tier 1 Commerce development environment](../e-commerce-extensibility/debug-tier-1.md).</span></span>

<span data-ttu-id="fa919-111">Ha az 1. szintű környezetben hibakeresést végez, mivel a webhely egy másik Retail Server kiszolgálót hív, a több kiszolgálóra vonatkozó hívások a tartalombiztonsági házirendhez kapcsolódó, különféle hibákat okozhatnak.</span><span class="sxs-lookup"><span data-stu-id="fa919-111">When you debug against a Tier 1 environment, because the site is now calling a different Retail Server, cross-server calls might cause various errors that are related to the content security policy.</span></span>

<span data-ttu-id="fa919-112">A következő ábra egy olyan hibát mutat be, amely akkor fordulhat elő, ha a termék részleteit tartalmazó oldalon egy változatot választanak ki.</span><span class="sxs-lookup"><span data-stu-id="fa919-112">The following illustration shows an example of an error that might occur when a variant is selected on a product details page.</span></span>

![Hiba történt, amikor egy változatot választottak ki a termék részleteit tartalmazó oldalon](media/unhandled-rejection-error.jpg)

<span data-ttu-id="fa919-114">Az alábbi ábra a böngésző hibakereső eszközeiben (F12 Fejlesztői eszközök) található hasonló hibára mutat be példát.</span><span class="sxs-lookup"><span data-stu-id="fa919-114">The following illustration shows an example of a similar error in a browser's debugger tools (F12 Developer Tools).</span></span> <span data-ttu-id="fa919-115">A hibaüzenet a tartalombiztonsági házirendjének megsértését említi.</span><span class="sxs-lookup"><span data-stu-id="fa919-115">The error message mentions violation of the content security policy directive.</span></span>

![Hiba a hibakereső eszközökben](media/debugger-tools-error.JPG)

## <a name="resolution"></a><span data-ttu-id="fa919-117">Felbontás</span><span class="sxs-lookup"><span data-stu-id="fa919-117">Resolution</span></span>

### <a name="disable-the-content-security-policy-for-the-site-in-commerce-site-builder"></a><span data-ttu-id="fa919-118">A webhely tartalombiztonsági házirendjének letiltása a Commerce webhelyszerkesztőben</span><span class="sxs-lookup"><span data-stu-id="fa919-118">Disable the content security policy for the site in Commerce site builder</span></span>

1. <span data-ttu-id="fa919-119">Válassza ki azt a webhelyet, amelyen dolgozik.</span><span class="sxs-lookup"><span data-stu-id="fa919-119">Select the site that you're working on.</span></span>
1. <span data-ttu-id="fa919-120">Válassza a **Beállítások** lehetőséget, majd válassza ki a **Bővítmények** pontot.</span><span class="sxs-lookup"><span data-stu-id="fa919-120">Select **Settings**, and then select **Extensions**.</span></span>
1. <span data-ttu-id="fa919-121">Válassza a **Tartalombiztonsági házirend** lapon a **Tartalombiztonsági házirend letiltása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fa919-121">On the **Content security policy** tab, select **Disable content security policy**.</span></span>
1. <span data-ttu-id="fa919-122">Válassza a **Mentés és közzététel** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="fa919-122">Select **Save and publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="fa919-123">A cég és ügyfél (B2C) bejelentkezés helyi fejlesztőkörnyezetben nem működik.</span><span class="sxs-lookup"><span data-stu-id="fa919-123">Business-to-consumer (B2C) sign-in won't work in a local development environment.</span></span> <span data-ttu-id="fa919-124">Vendégfizetésekkel és a buildoldalak próbaverzióival azonban szükség esetén szimulálhatja a felhasználók bejelentkezését.</span><span class="sxs-lookup"><span data-stu-id="fa919-124">However, you can use guest checkouts or build page mocks to simulate a user sign-in as required.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fa919-125">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="fa919-125">Additional resources</span></span>

[<span data-ttu-id="fa919-126">Első lépések az e-kereskedelem online bővíthetőségének fejlesztésében</span><span class="sxs-lookup"><span data-stu-id="fa919-126">Get started with e-commerce online extensibility development</span></span>](../e-commerce-extensibility/sdk-getting-started.md)

[<span data-ttu-id="fa919-127">Tartalombiztonsági házirend (CSP) kezelése az e-kereskedelmi webhelyen</span><span class="sxs-lookup"><span data-stu-id="fa919-127">Manage content security policy (CSP) on e-commerce site</span></span>](../manage-csp.md)
