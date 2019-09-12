---
title: POS-engedélycsoportok létrehozása
description: Ez a témakör a pénztár engedélycsoport létrehozásának lépéseit mutatja be.
author: scott-tucker
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailPosPermissionGroup, HcmJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e6782c60aa659523775cc6c4eb1694430a4bf4f
ms.sourcegitcommit: e10491a2ff04f65d9f306ef6e068ee123213b23b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/21/2019
ms.locfileid: "1914801"
---
# <a name="create-pos-permission-groups"></a><span data-ttu-id="4ecbb-103">POS-engedélycsoportok létrehozása</span><span class="sxs-lookup"><span data-stu-id="4ecbb-103">Create POS permission groups</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="4ecbb-104">Ez a témakör a pénztár engedélycsoport létrehozásának lépéseit mutatja be.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-104">This topic explains how to create a POS permission group.</span></span> <span data-ttu-id="4ecbb-105">A feladat létrehozásához az USRT bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="4ecbb-106">A feladat a Kiskereskedelmi üzemeltetési vezető szerepkör számára készült.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-106">This task is intended for the Retail operations manager role.</span></span>

1. <span data-ttu-id="4ecbb-107">A navigációs ablakban nyissa meg a **Modulok > Kiskereskedelem > Alkalmazottak > Engedélycsoportok** elemet.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-107">In the navigation pane, go to **Modules > Retail > Employees > Permission groups**.</span></span>
2. <span data-ttu-id="4ecbb-108">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-108">Select **New**.</span></span>
3. <span data-ttu-id="4ecbb-109">Írjon be egy értéket a **POS-engedélycsoport azonosítója** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-109">In the **POS permission group ID** field, type a value.</span></span>
4. <span data-ttu-id="4ecbb-110">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-110">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="4ecbb-111">Válassza ki az **Igen** lehetőséget a **Blokkolóóra bejegyzéseinek megtekintése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-111">Select **Yes** in the **View time clock entries** field.</span></span> <span data-ttu-id="4ecbb-112">Most engedélyezheti vagy a letilthatja a POS-engedélycsoport különféle engedélyeit.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-112">You can now enable or disable various permissions for your POS Permission group.</span></span> <span data-ttu-id="4ecbb-113">Egyes engedélyekhez beállíthat egy értéket, amely meghatározza, hogy a pénztári felhasználó végrehajthatja-e az adott műveletet.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-113">For some permission you can set a value that will be used to evaluate if the POS user can perform the action.</span></span> <span data-ttu-id="4ecbb-114">Ez a feladat-útmutató beállít néhány, pénztárosoknak adható engedélyt.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-114">This task guide enables a few permission that might be given to a cashier.</span></span>  
6. <span data-ttu-id="4ecbb-115">Válassza ki az **Igen** lehetőséget a **Rendelés létrehozásának engedélyezése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-115">Select **Yes** in the **Allow create order** field.</span></span>
7. <span data-ttu-id="4ecbb-116">Válassza ki az **Igen** lehetőséget a **Rendelés szerkesztésének engedélyezése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-116">Select **Yes** in the **Allow edit order** field.</span></span>
8. <span data-ttu-id="4ecbb-117">Válassza ki az **Igen** lehetőséget a **Rendelés beolvasásának engedélyezése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-117">Select **Yes** in the **Allow retrieve order** field.</span></span>
9. <span data-ttu-id="4ecbb-118">Válassza ki az **Igen** lehetőséget a **Jelszómódosítás engedélyezése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-118">Select **Yes** in the **Allow password change** field.</span></span>
10. <span data-ttu-id="4ecbb-119">Válassza ki az **Igen** lehetőséget a **Számlálás nélküli zárás engedélyezése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-119">Select **Yes** in the **Allow blind close** field.</span></span>
11. <span data-ttu-id="4ecbb-120">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-120">Select **Save**.</span></span> <span data-ttu-id="4ecbb-121">A módosítások mentése után futtatnia kell a Személyzetelosztási ütemezést, hogy leküldje a változtatásokat a kiskereskedelmi csatornákba.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-121">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span> 
12. <span data-ttu-id="4ecbb-122">Ugorjon a Navigációs ablaktábla **Modulok > Emberi erőforrások > Állások > Állások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-122">In the navigation pane, go to **Modules > Human resources > Jobs > Jobs**.</span></span>
13. <span data-ttu-id="4ecbb-123">A következőkben hozzárendelünk egy POS-engedélycsoportot egy Feladathoz.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-123">Next we will assign the POS permission group to a Job.</span></span> <span data-ttu-id="4ecbb-124">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-124">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="4ecbb-125">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-125">Select **Edit**.</span></span>
15. <span data-ttu-id="4ecbb-126">Bontsa ki a **Munkaköri besorolás** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-126">Expand the **Job classification** section.</span></span>
16. <span data-ttu-id="4ecbb-127">A POS-engedélycsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-127">In the POS permission group field, enter or select a value.</span></span> <span data-ttu-id="4ecbb-128">Minden, ehhez a Feladathoz rendelt Pozícióban lévő Dolgozó ennek a POS-engedélycsoportnak a beállításait fogja használni, kivéve, ha a dolgozók POS-engedélyeit a Pozíció szintjén felülbírálták.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-128">All Workers in Positions for this Job will use this POS permission group’s settings unless the workers POS permissions have been overridden at their Position level.</span></span>  
17. <span data-ttu-id="4ecbb-129">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-129">Select **Save**.</span></span> <span data-ttu-id="4ecbb-130">A módosítások mentése után futtatnia kell a Személyzetelosztási ütemezést, hogy leküldje a változtatásokat a kiskereskedelmi csatornákba.</span><span class="sxs-lookup"><span data-stu-id="4ecbb-130">After your changes are saved you need to run the Staff distribution schedule to push the changes to retail channels.</span></span>  

