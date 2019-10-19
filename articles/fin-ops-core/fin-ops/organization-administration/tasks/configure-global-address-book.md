---
title: A globális címjegyzék konfigurálása
description: Ezekkel a lépésekkel beállíthatja az alapértelmezett értékeket és a globális címjegyzék biztonsági irányelveit.
author: kfend
manager: AnnBe
ms.date: 07/23/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirParameters
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3994c7bb77e9821a880dc009681e113013129850
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189913"
---
# <a name="configure-the-global-address-book"></a><span data-ttu-id="16f6a-103">A globális címjegyzék konfigurálása</span><span class="sxs-lookup"><span data-stu-id="16f6a-103">Configure the global address book</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="16f6a-104">Ezekkel a lépésekkel beállíthatja az alapértelmezett értékeket és a globális címjegyzék biztonsági irányelveit.</span><span class="sxs-lookup"><span data-stu-id="16f6a-104">Use this procedure to set the default values and security policies for the global address book.</span></span> 

<span data-ttu-id="16f6a-105">A feladat létrehozásához az USMF bemutató vállalatot használtuk példaként.</span><span class="sxs-lookup"><span data-stu-id="16f6a-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="16f6a-106">Ez a feladat a Tervezési és a konfigurációs csoport számára készült.</span><span class="sxs-lookup"><span data-stu-id="16f6a-106">This task is intended for the Planning and configuration team.</span></span>

1. <span data-ttu-id="16f6a-107">A Navigációs ablaktáblán válassza a **Moduok > Szervezeti felügyelet > Globális címjegyzék > Globális címjegyzék paraméterei** elemet.</span><span class="sxs-lookup"><span data-stu-id="16f6a-107">In the Navigation pane, go to **Modules > Organization administration > Global address book > Global address book parameters**.</span></span>
2. <span data-ttu-id="16f6a-108">A **Névsorozat** mezőben válassza ki a nevek megjelenítési módját.</span><span class="sxs-lookup"><span data-stu-id="16f6a-108">In the **Name sequence** field, select how names should be shown.</span></span>
3. <span data-ttu-id="16f6a-109">A **Szerepkörrel nem rendelkező felek törlése** helyen válassza ki, hogy törölni szeretné-e a szerepkörrel nem rendelkező feleket.</span><span class="sxs-lookup"><span data-stu-id="16f6a-109">In **Delete parties with no roles**, select whether to delete parties with that have not been assigned a role.</span></span>
4. <span data-ttu-id="16f6a-110">A **Duplikált csekk használata** területen válassza ki, hogy az ismétlődő rekordokat szeretné-e ellenőrizni.</span><span class="sxs-lookup"><span data-stu-id="16f6a-110">In **Use duplicate check**, select whether to check for duplicate records.</span></span>
5. <span data-ttu-id="16f6a-111">A **A DUNS szám megjelenítése a címeken** részben, válassza ki, hogy megjeleníti-e DUNS-számokat a címeken.</span><span class="sxs-lookup"><span data-stu-id="16f6a-111">In **Display DUNS number on addresses**, select whether to display the DUNS number on addresses.</span></span>
6. <span data-ttu-id="16f6a-112">Az **Egyedi DUNS számokellenőrzése** helyen válassza ki, hogy ellenőrizze-e az egyedi DUNS számokat.</span><span class="sxs-lookup"><span data-stu-id="16f6a-112">In **Check for unique DUNS number**, select whether to check for unique DUNS numbers.</span></span>
7. <span data-ttu-id="16f6a-113">Egy lehetőség kiválasztása a **Fél** mezőben.</span><span class="sxs-lookup"><span data-stu-id="16f6a-113">In the **Party** field, select an option.</span></span>
8. <span data-ttu-id="16f6a-114">Egy lehetőség kiválasztása az **Ügyfél** mezőben.</span><span class="sxs-lookup"><span data-stu-id="16f6a-114">In the **Customer** field, select an option.</span></span>
9. <span data-ttu-id="16f6a-115">Egy lehetőség kiválasztása a **Szállító** mezőben.</span><span class="sxs-lookup"><span data-stu-id="16f6a-115">In the **Vendor** field, select an option.</span></span>
10. <span data-ttu-id="16f6a-116">Egy lehetőség kiválasztása a **Potenciális vevő** mezőben.</span><span class="sxs-lookup"><span data-stu-id="16f6a-116">In the **Prospect** field, select an option.</span></span>
11. <span data-ttu-id="16f6a-117">Egy lehetőség kiválasztása a **Versenytárs** mezőben.</span><span class="sxs-lookup"><span data-stu-id="16f6a-117">In the **Competitor** field, select an option.</span></span>
12. <span data-ttu-id="16f6a-118">Kattintson a **Privát hely biztonsága** lapra.</span><span class="sxs-lookup"><span data-stu-id="16f6a-118">Click the **Private location security** tab.</span></span>
13. <span data-ttu-id="16f6a-119">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="16f6a-119">In the list, find and select the desired record.</span></span> <span data-ttu-id="16f6a-120">Nyomja le a Shift billentyűt, jelöljön be több szerepkört a **Kijelölt szerepkörök** ablakban való hozzáadáshoz, és kattintson a nyílra a kijelölt szerepkörök hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="16f6a-120">Press the Shift key to select multiple roles to add to the **Selected roles** pane and then click the arrow to add the selected roles.</span></span>  
14. <span data-ttu-id="16f6a-121">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="16f6a-121">Click **Save**.</span></span>

