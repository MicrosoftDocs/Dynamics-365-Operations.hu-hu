---
title: Felhasználók tömeges importálása
description: Ezzel az eljárással a rendszergazdák nagy számú felhasználót importálhatnak az Azure Active Directory rendszerből.
author: maertenm
manager: AnnBe
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fa86d408727ecf2127308070fda592ff6a1fccf4
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982454"
---
# <a name="import-users-in-bulk"></a><span data-ttu-id="e50c9-103">Felhasználók tömeges importálása</span><span class="sxs-lookup"><span data-stu-id="e50c9-103">Import users in bulk</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e50c9-104">Ezzel az eljárással a rendszergazdák nagy számú felhasználót importálhatnak az Azure Active Directory rendszerből.</span><span class="sxs-lookup"><span data-stu-id="e50c9-104">This procedure can be used by system administrators to import a large number of users from Azure Active Directory.</span></span>


## <a name="run-as-a-batch-job"></a><span data-ttu-id="e50c9-105">Futtatás kötegelt feladatként</span><span class="sxs-lookup"><span data-stu-id="e50c9-105">Run as a batch job</span></span>
1. <span data-ttu-id="e50c9-106">Ugrás a Rendszerfelügyelet > Felhasználók > Felhasználók elemre.</span><span class="sxs-lookup"><span data-stu-id="e50c9-106">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="e50c9-107">Kattintson a Kötegelt importálás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e50c9-107">Click Batch import.</span></span>
3. <span data-ttu-id="e50c9-108">Bontsa ki a Futtatás a háttérben szakaszt.</span><span class="sxs-lookup"><span data-stu-id="e50c9-108">Expand the Run in the background section.</span></span>
4. <span data-ttu-id="e50c9-109">Válassza az Igen lehetőséget a Kötegelt feldolgozás mezőben.</span><span class="sxs-lookup"><span data-stu-id="e50c9-109">Select Yes in the Batch processing field.</span></span>
5. <span data-ttu-id="e50c9-110">A Feladat leírása mezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e50c9-110">In the Task description field, type a value.</span></span>
6. <span data-ttu-id="e50c9-111">A Kötegcsoport mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e50c9-111">In the Batch group field, enter or select a value.</span></span>
    * <span data-ttu-id="e50c9-112">Ez a lépés nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="e50c9-112">This is an optional step.</span></span>  
7. <span data-ttu-id="e50c9-113">Válassza ki az Igen lehetőséget a Személyes mezőben.</span><span class="sxs-lookup"><span data-stu-id="e50c9-113">Select Yes in the Private field.</span></span>
    * <span data-ttu-id="e50c9-114">Ez a lépés nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="e50c9-114">This is an optional step.</span></span>  
8. <span data-ttu-id="e50c9-115">Válassza az Igen lehetőséget a Kritikus feladat mezőben.</span><span class="sxs-lookup"><span data-stu-id="e50c9-115">Select Yes in the Critical Job field.</span></span>
    * <span data-ttu-id="e50c9-116">Ez a lépés nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="e50c9-116">This is an optional step.</span></span>  
9. <span data-ttu-id="e50c9-117">Válasszon ki egy lehetőséget a Figyelési kategória mezőben.</span><span class="sxs-lookup"><span data-stu-id="e50c9-117">In the Monitoring category field, select an option.</span></span>
10. <span data-ttu-id="e50c9-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e50c9-118">Click OK.</span></span>

## <a name="run-in-a-sandbox-environment"></a><span data-ttu-id="e50c9-119">Futtatás védőfalkörnyezetben</span><span class="sxs-lookup"><span data-stu-id="e50c9-119">Run in a sandbox environment</span></span>
1. <span data-ttu-id="e50c9-120">Kattintson a Kötegelt importálás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e50c9-120">Click Batch import.</span></span>
2. <span data-ttu-id="e50c9-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="e50c9-121">Click OK.</span></span>

