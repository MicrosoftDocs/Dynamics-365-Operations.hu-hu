---
title: Szolgáltatás intervallumainak beállítása
description: A szerviz intervalluma azt a gyakoriságot jelzi, amellyel a szervizrendeléssorok létrejönnek a szervizrendelések automatikus létrehozása esetén.
author: ShylaThompson
manager: tfehr
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementinterval
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 815da6b24de401ad11febb0b0564738ce6967a9c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991665"
---
# <a name="set-up-service-intervals"></a><span data-ttu-id="69c47-103">Szolgáltatás intervallumainak beállítása</span><span class="sxs-lookup"><span data-stu-id="69c47-103">Set up service intervals</span></span>  

[!include [banner](../includes/banner.md)]

<span data-ttu-id="69c47-104">A szerviz intervalluma azt a gyakoriságot jelzi, amellyel a szervizrendeléssorok létrejönnek a szervizrendelések automatikus létrehozása esetén.</span><span class="sxs-lookup"><span data-stu-id="69c47-104">Service interval indicates the frequency with which service order lines are created for service agreement lines when you create service orders.</span></span>

1. <span data-ttu-id="69c47-105">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **Szolgáltatási szerződések** \> **Szolgáltatás intervallumai** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="69c47-105">Click **Service management** \> **Setup** \> **Service agreements** \> **Service intervals**.</span></span>
2. <span data-ttu-id="69c47-106">Hozzon létre egy új szolgáltatás-intervallumot.</span><span class="sxs-lookup"><span data-stu-id="69c47-106">Create a new service interval.</span></span>
3. <span data-ttu-id="69c47-107">Adja meg a szolgáltatás intervallumának azonosítóját és leírását.</span><span class="sxs-lookup"><span data-stu-id="69c47-107">Enter the ID and description of the service interval.</span></span>
4. <span data-ttu-id="69c47-108">Válassza ki a tartományt a **Tartomány** mezőben.</span><span class="sxs-lookup"><span data-stu-id="69c47-108">In the **Range** field, select the range.</span></span>
5. <span data-ttu-id="69c47-109">A **Gyakoriság** mezőben adja meg a gyakoriságot.</span><span class="sxs-lookup"><span data-stu-id="69c47-109">In the **Frequency** field, type the frequency.</span></span> <span data-ttu-id="69c47-110">A gyakoriság az a tényező, amellyel meg kell szorozni a tartományt a szolgáltatási szerződés intervallumának megállapítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="69c47-110">The frequency is the factor by which you must multiply the range to obtain the interval for a service agreement.</span></span>
6. <span data-ttu-id="69c47-111">Az **Alt+S** billentyűkombinációval mentse a szolgáltatás intervallumát.</span><span class="sxs-lookup"><span data-stu-id="69c47-111">Press **Alt+S** to save the service interval.</span></span>

## <a name="example"></a><span data-ttu-id="69c47-112">Példa</span><span class="sxs-lookup"><span data-stu-id="69c47-112">Example</span></span>

<span data-ttu-id="69c47-113">10 napos szolgáltatási intervallumot szeretne létrehozni.</span><span class="sxs-lookup"><span data-stu-id="69c47-113">You want to create a service interval of 10 days.</span></span>

<span data-ttu-id="69c47-114">**10 napos szolgáltatási intervallum létrehozása**</span><span class="sxs-lookup"><span data-stu-id="69c47-114">**Create a 10-day service interval**</span></span>

1. <span data-ttu-id="69c47-115">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **Szolgáltatási szerződések** \> **Szolgáltatás intervallumai** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="69c47-115">Click **Service management** \> **Setup** \> **Service agreements** \> **Service intervals**.</span></span>
2. <span data-ttu-id="69c47-116">Hozzon létre egy új szolgáltatás-intervallumot.</span><span class="sxs-lookup"><span data-stu-id="69c47-116">Create a new service interval.</span></span>
3. <span data-ttu-id="69c47-117">Adja meg a szolgáltatás intervallumának azonosítóját és leírását.</span><span class="sxs-lookup"><span data-stu-id="69c47-117">Enter the ID and description of the service interval.</span></span>
4. <span data-ttu-id="69c47-118">A **Tartomány** mezőben válassza ki a **Napi** értéket.</span><span class="sxs-lookup"><span data-stu-id="69c47-118">In the **Range** field, select **Daily**.</span></span>
5. <span data-ttu-id="69c47-119">A **Gyakoriság** mezőben adja meg a 10 értéket.</span><span class="sxs-lookup"><span data-stu-id="69c47-119">In the **Frequency** field, type 10.</span></span>
6. <span data-ttu-id="69c47-120">Az **Alt+S** billentyűkombinációval mentse a szolgáltatás intervallumát.</span><span class="sxs-lookup"><span data-stu-id="69c47-120">Press **Alt+S** to save the service interval.</span></span>

## <a name="related-topics"></a><span data-ttu-id="69c47-121">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="69c47-121">Related topics</span></span>

[<span data-ttu-id="69c47-122">Szolgáltatás intervallumai</span><span class="sxs-lookup"><span data-stu-id="69c47-122">Service intervals</span></span>](service-intervals.md)  
