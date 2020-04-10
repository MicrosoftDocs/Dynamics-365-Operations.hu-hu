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
ms.openlocfilehash: 7d8b55895c9dfaf1c69cd319697f1e0da5990daf
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144087"
---
# <a name="import-users-in-bulk"></a><span data-ttu-id="0ad49-103">Felhasználók tömeges importálása</span><span class="sxs-lookup"><span data-stu-id="0ad49-103">Import users in bulk</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0ad49-104">Ezzel az eljárással a rendszergazdák nagy számú felhasználót importálhatnak az Azure Active Directory rendszerből.</span><span class="sxs-lookup"><span data-stu-id="0ad49-104">This procedure can be used by system administrators to import a large number of users from Azure Active Directory.</span></span>


## <a name="run-as-a-batch-job"></a><span data-ttu-id="0ad49-105">Futtatás kötegelt feladatként</span><span class="sxs-lookup"><span data-stu-id="0ad49-105">Run as a batch job</span></span>
1. <span data-ttu-id="0ad49-106">Ugrás a Rendszerfelügyelet > Felhasználók > Felhasználók elemre.</span><span class="sxs-lookup"><span data-stu-id="0ad49-106">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="0ad49-107">Kattintson a Kötegelt importálás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0ad49-107">Click Batch import.</span></span>
3. <span data-ttu-id="0ad49-108">Bontsa ki a Futtatás a háttérben szakaszt.</span><span class="sxs-lookup"><span data-stu-id="0ad49-108">Expand the Run in the background section.</span></span>
4. <span data-ttu-id="0ad49-109">Válassza az Igen lehetőséget a Kötegelt feldolgozás mezőben.</span><span class="sxs-lookup"><span data-stu-id="0ad49-109">Select Yes in the Batch processing field.</span></span>
5. <span data-ttu-id="0ad49-110">A Feladat leírása mezőbe írjon egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0ad49-110">In the Task description field, type a value.</span></span>
6. <span data-ttu-id="0ad49-111">A Kötegcsoport mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="0ad49-111">In the Batch group field, enter or select a value.</span></span>
    * <span data-ttu-id="0ad49-112">Ez a lépés nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="0ad49-112">This is an optional step.</span></span>  
7. <span data-ttu-id="0ad49-113">Válassza ki az Igen lehetőséget a Személyes mezőben.</span><span class="sxs-lookup"><span data-stu-id="0ad49-113">Select Yes in the Private field.</span></span>
    * <span data-ttu-id="0ad49-114">Ez a lépés nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="0ad49-114">This is an optional step.</span></span>  
8. <span data-ttu-id="0ad49-115">Válassza az Igen lehetőséget a Kritikus feladat mezőben.</span><span class="sxs-lookup"><span data-stu-id="0ad49-115">Select Yes in the Critical Job field.</span></span>
    * <span data-ttu-id="0ad49-116">Ez a lépés nem kötelező.</span><span class="sxs-lookup"><span data-stu-id="0ad49-116">This is an optional step.</span></span>  
9. <span data-ttu-id="0ad49-117">Válasszon ki egy lehetőséget a Figyelési kategória mezőben.</span><span class="sxs-lookup"><span data-stu-id="0ad49-117">In the Monitoring category field, select an option.</span></span>
10. <span data-ttu-id="0ad49-118">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0ad49-118">Click OK.</span></span>

## <a name="run-in-a-sandbox-environment"></a><span data-ttu-id="0ad49-119">Futtatás védőfalkörnyezetben</span><span class="sxs-lookup"><span data-stu-id="0ad49-119">Run in a sandbox environment</span></span>
1. <span data-ttu-id="0ad49-120">Kattintson a Kötegelt importálás lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0ad49-120">Click Batch import.</span></span>
2. <span data-ttu-id="0ad49-121">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="0ad49-121">Click OK.</span></span>

