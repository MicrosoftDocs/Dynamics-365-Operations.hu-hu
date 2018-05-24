---
title: "Szervizrendelési fokozatok beállítása"
description: "Szervizrendelési fokozatok beállítása."
author: YuyuScheller
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 6e2556dd8f3f32da16e53bfe46faec7489d84efa
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="set-up-service-order-stages"></a><span data-ttu-id="1d0c7-103">Szervizrendelési fokozatok beállítása</span><span class="sxs-lookup"><span data-stu-id="1d0c7-103">Set up service order stages</span></span> 

[!include [banner](../includes/banner.md)]


1.  <span data-ttu-id="1d0c7-104">Kattintson a **Szolgáltatáskezelés** \> **Beállítás** \> **Szervizrendelések** \> **Szerviz fokozatai** elemre.</span><span class="sxs-lookup"><span data-stu-id="1d0c7-104">Click **Service management** \> **Setup** \> **Service orders** \> **Service stages**.</span></span>

2.  <span data-ttu-id="1d0c7-105">Hozzon létre egy új rekordot a CTRL+N billentyűkombináció lenyomásával.</span><span class="sxs-lookup"><span data-stu-id="1d0c7-105">Press CTRL+N to create a new record.</span></span>

3.  <span data-ttu-id="1d0c7-106">A **Szolgáltatási fokozat** és a **Leírás** mezőkben adja meg a szolgáltatási fokozat azonosítóját és leírását.</span><span class="sxs-lookup"><span data-stu-id="1d0c7-106">In the **Service stage** and **Description** fields, specify a service stage ID and description.</span></span>

4.  <span data-ttu-id="1d0c7-107">Adja meg a fokozat megfelelő paramétereit.</span><span class="sxs-lookup"><span data-stu-id="1d0c7-107">Select the appropriate parameters for the stage.</span></span>

5.  <span data-ttu-id="1d0c7-108">Válassza ki a jelenlegi fokozat szülőfokozatát, vagy hagyja üresen a **Szülő** mezőt, amennyiben az a fokozatbeállítás kezdeti fokozata.</span><span class="sxs-lookup"><span data-stu-id="1d0c7-108">Select the parent stage for the current stage or leave the **Parent** field blank if the stage is the initial stage in the stage setup.</span></span>


> [!NOTE]
> <P><span data-ttu-id="1d0c7-109">A fokozat mentése után a <STRONG>Szülő</STRONG> mezőt nem lehet módosítani.</span><span class="sxs-lookup"><span data-stu-id="1d0c7-109">You cannot modify the <STRONG>Parent</STRONG> field after you save the stage.</span></span> <span data-ttu-id="1d0c7-110">Ehelyett ki kell törölni a rekordot, és újra létre kell hozni a <STRONG>Szülő</STRONG> mező más beállításával.</span><span class="sxs-lookup"><span data-stu-id="1d0c7-110">Instead, you can delete the record and create the record again with a different selection in the <STRONG>Parent</STRONG> field.</span></span></P>
> <P><span data-ttu-id="1d0c7-111">Ráadásul csak egyetlen fokozat hozható létre üres <STRONG>Szülő</STRONG> mezővel.</span><span class="sxs-lookup"><span data-stu-id="1d0c7-111">Also, you can only create one stage with a blank <STRONG>Parent</STRONG> field.</span></span> <span data-ttu-id="1d0c7-112">Vagyis egyetlen kezdeti fokozat van engedélyezve.</span><span class="sxs-lookup"><span data-stu-id="1d0c7-112">That is, only one initial stage is permitted.</span></span></P>


  



