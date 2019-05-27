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
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 339cc1d3bcdc1dc93b796c385d2165f45f8f7ecf
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548089"
---
# <a name="import-users-in-bulk"></a><span data-ttu-id="46471-103">Felhasználók tömeges importálása</span><span class="sxs-lookup"><span data-stu-id="46471-103">Import users in bulk</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="46471-104">Ezzel az eljárással a rendszergazdák nagy számú felhasználót importálhatnak az Azure Active Directory rendszerből.</span><span class="sxs-lookup"><span data-stu-id="46471-104">This procedure can be used by system administrators to import a large number of users from Azure Active Directory.</span></span>


## <a name="run-as-a-batch-job"></a><span data-ttu-id="46471-105">Futtatás kötegelt feladatként</span><span class="sxs-lookup"><span data-stu-id="46471-105">Run as a batch job</span></span>
1. <span data-ttu-id="46471-106">Ugrás a Rendszerfelügyelet > Felhasználók > Felhasználók elemre.</span><span class="sxs-lookup"><span data-stu-id="46471-106">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="46471-107">Kattintson a Kötegelt importálás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46471-107">Click Batch import.</span></span>
3. <span data-ttu-id="46471-108">Bontsa ki a Futtatás a háttérben szakaszt.</span><span class="sxs-lookup"><span data-stu-id="46471-108">Expand the Run in the background section.</span></span>
4. <span data-ttu-id="46471-109">Válassza az Igen lehetőséget a Kötegelt feldolgozás mezőben.</span><span class="sxs-lookup"><span data-stu-id="46471-109">Select Yes in the Batch processing field.</span></span>
5. <span data-ttu-id="46471-110">A Feladat leírása mezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46471-110">In the Task description field, type a value.</span></span>
6. <span data-ttu-id="46471-111">A Kötegcsoport mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="46471-111">In the Batch group field, enter or select a value.</span></span>
    * <span data-ttu-id="46471-112">Ez a lépés nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="46471-112">This is an optional step.</span></span>  
7. <span data-ttu-id="46471-113">Válassza ki az Igen lehetőséget a Személyes mezőben.</span><span class="sxs-lookup"><span data-stu-id="46471-113">Select Yes in the Private field.</span></span>
    * <span data-ttu-id="46471-114">Ez a lépés nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="46471-114">This is an optional step.</span></span>  
8. <span data-ttu-id="46471-115">Válassza az Igen lehetőséget a Kritikus feladat mezőben.</span><span class="sxs-lookup"><span data-stu-id="46471-115">Select Yes in the Critical Job field.</span></span>
    * <span data-ttu-id="46471-116">Ez a lépés nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="46471-116">This is an optional step.</span></span>  
9. <span data-ttu-id="46471-117">Válasszon ki egy lehetőséget a Figyelési kategória mezőben.</span><span class="sxs-lookup"><span data-stu-id="46471-117">In the Monitoring category field, select an option.</span></span>
10. <span data-ttu-id="46471-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="46471-118">Click OK.</span></span>

## <a name="run-in-a-sandbox-environment"></a><span data-ttu-id="46471-119">Futtatás védőfalkörnyezetben</span><span class="sxs-lookup"><span data-stu-id="46471-119">Run in a sandbox environment</span></span>
1. <span data-ttu-id="46471-120">Kattintson a Kötegelt importálás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="46471-120">Click Batch import.</span></span>
2. <span data-ttu-id="46471-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="46471-121">Click OK.</span></span>

