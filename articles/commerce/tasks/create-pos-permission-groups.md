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
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ac03e1bfb7a2463b31feca0a4303c182a00ad259
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4964820"
---
# <a name="create-pos-permission-groups"></a><span data-ttu-id="f4575-103">POS-engedélycsoportok létrehozása</span><span class="sxs-lookup"><span data-stu-id="f4575-103">Create POS permission groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f4575-104">Ez a témakör a pénztár engedélycsoport létrehozásának lépéseit mutatja be.</span><span class="sxs-lookup"><span data-stu-id="f4575-104">This topic explains how to create a POS permission group.</span></span> <span data-ttu-id="f4575-105">A feladat létrehozásához az USRT bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="f4575-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="f4575-106">Ez a feladat Kereskedelmi üzemeltetési vezető szerepkörhöz tartozik.</span><span class="sxs-lookup"><span data-stu-id="f4575-106">This task is intended for the Commerce operations manager role.</span></span>

1. <span data-ttu-id="f4575-107">A navigációs ablakban nyissa meg a **Modulok > Kiskereskedelem és kereskedelem > Alkalmazottak > Engedélycsoportok** elemet.</span><span class="sxs-lookup"><span data-stu-id="f4575-107">In the navigation pane, go to **Modules > Retail and Commerce > Employees > Permission groups**.</span></span>
2. <span data-ttu-id="f4575-108">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f4575-108">Select **New**.</span></span>
3. <span data-ttu-id="f4575-109">Írjon be egy értéket a **POS-engedélycsoport azonosítója** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f4575-109">In the **POS permission group ID** field, type a value.</span></span>
4. <span data-ttu-id="f4575-110">Írjon egy értéket a **Leírás** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="f4575-110">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="f4575-111">Válassza ki az **Igen** lehetőséget a **Blokkolóóra bejegyzéseinek megtekintése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f4575-111">Select **Yes** in the **View time clock entries** field.</span></span> <span data-ttu-id="f4575-112">Most engedélyezheti vagy a letilthatja a POS-engedélycsoport különféle engedélyeit.</span><span class="sxs-lookup"><span data-stu-id="f4575-112">You can now enable or disable various permissions for your POS Permission group.</span></span> <span data-ttu-id="f4575-113">Egyes engedélyekhez beállíthat egy értéket, amely meghatározza, hogy a pénztári felhasználó végrehajthatja-e az adott műveletet.</span><span class="sxs-lookup"><span data-stu-id="f4575-113">For some permission you can set a value that will be used to evaluate if the POS user can perform the action.</span></span> <span data-ttu-id="f4575-114">Ez a feladat-útmutató beállít néhány, pénztárosoknak adható engedélyt.</span><span class="sxs-lookup"><span data-stu-id="f4575-114">This task guide enables a few permission that might be given to a cashier.</span></span>  
6. <span data-ttu-id="f4575-115">Válassza ki az **Igen** lehetőséget a **Rendelés létrehozásának engedélyezése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f4575-115">Select **Yes** in the **Allow create order** field.</span></span>
7. <span data-ttu-id="f4575-116">Válassza ki az **Igen** lehetőséget a **Rendelés szerkesztésének engedélyezése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f4575-116">Select **Yes** in the **Allow edit order** field.</span></span>
8. <span data-ttu-id="f4575-117">Válassza ki az **Igen** lehetőséget a **Rendelés beolvasásának engedélyezése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f4575-117">Select **Yes** in the **Allow retrieve order** field.</span></span>
9. <span data-ttu-id="f4575-118">Válassza ki az **Igen** lehetőséget a **Jelszómódosítás engedélyezése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f4575-118">Select **Yes** in the **Allow password change** field.</span></span>
10. <span data-ttu-id="f4575-119">Válassza ki az **Igen** lehetőséget a **Számlálás nélküli zárás engedélyezése** mezőben.</span><span class="sxs-lookup"><span data-stu-id="f4575-119">Select **Yes** in the **Allow blind close** field.</span></span>
11. <span data-ttu-id="f4575-120">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f4575-120">Select **Save**.</span></span> <span data-ttu-id="f4575-121">A módosítások mentése után futtatnia kell a Személyzetelosztási ütemezést, hogy leküldje a változtatásokat a kereskedelmi csatornákba.</span><span class="sxs-lookup"><span data-stu-id="f4575-121">After your changes are saved you need to run the Staff distribution schedule to push the changes to commerce channels.</span></span> 
12. <span data-ttu-id="f4575-122">Ugorjon a Navigációs ablaktábla **Modulok > Emberi erőforrások > Állások > Állások** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f4575-122">In the navigation pane, go to **Modules > Human resources > Jobs > Jobs**.</span></span>
13. <span data-ttu-id="f4575-123">A következőkben hozzárendelünk egy POS-engedélycsoportot egy Feladathoz.</span><span class="sxs-lookup"><span data-stu-id="f4575-123">Next we will assign the POS permission group to a Job.</span></span> <span data-ttu-id="f4575-124">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="f4575-124">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="f4575-125">Válassza ki a **Szerkesztés** opciót.</span><span class="sxs-lookup"><span data-stu-id="f4575-125">Select **Edit**.</span></span>
15. <span data-ttu-id="f4575-126">Bontsa ki a **Munkaköri besorolás** szakaszt.</span><span class="sxs-lookup"><span data-stu-id="f4575-126">Expand the **Job classification** section.</span></span>
16. <span data-ttu-id="f4575-127">A POS-engedélycsoport mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="f4575-127">In the POS permission group field, enter or select a value.</span></span> <span data-ttu-id="f4575-128">Minden, ehhez a Feladathoz rendelt Pozícióban lévő Dolgozó ennek a pénztár-engedélycsoportnak a beállításait fogja használni, kivéve, ha a dolgozók pénztár-engedélyeit a Pozíció szintjén felülbírálták.</span><span class="sxs-lookup"><span data-stu-id="f4575-128">All Workers in Positions for this Job will use this POS permission group's settings unless the workers POS permissions have been overridden at their Position level.</span></span>  
17. <span data-ttu-id="f4575-129">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f4575-129">Select **Save**.</span></span> <span data-ttu-id="f4575-130">A módosítások mentése után futtatnia kell a Személyzetelosztási ütemezést, hogy leküldje a változtatásokat a csatornákba.</span><span class="sxs-lookup"><span data-stu-id="f4575-130">After your changes are saved you need to run the Staff distribution schedule to push the changes to channels.</span></span>  

