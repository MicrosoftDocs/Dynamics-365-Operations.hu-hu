---
title: Lízingfelhasználói szerepkörök hozzárendelése
description: Ez a témakör az Eszközlízinghez használt biztonsági szerepeket ismerteti. Azt is bemutatja, hogyan rendelhet hozzá felhasználókat ezekhez a szerepkörökhöz.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 16719576dde73f096c0102a89c43cbc75594cc80
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819842"
---
# <a name="assign-lease-user-roles"></a><span data-ttu-id="cca32-104">Lízingfelhasználói szerepkörök hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="cca32-104">Assign lease user roles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cca32-105">Ez a témakör az Eszközlízinghez használt biztonsági szerepeket ismerteti.</span><span class="sxs-lookup"><span data-stu-id="cca32-105">This topic describes the security roles that are used in Asset leasing.</span></span> <span data-ttu-id="cca32-106">Azt is bemutatja, hogyan rendelhet hozzá felhasználókat ezekhez a szerepkörökhöz.</span><span class="sxs-lookup"><span data-stu-id="cca32-106">It also explains how to assign users to those roles.</span></span>

<span data-ttu-id="cca32-107">Három felhasználói szerepkör különbözteti meg a hozzáférést az Eszközlízingben.</span><span class="sxs-lookup"><span data-stu-id="cca32-107">Three user roles differentiate access in Asset leasing.</span></span> <span data-ttu-id="cca32-108">Az egyik szerepkör megfelelő a lízingek karbantartásához, a másik a lízingek megtekintéséhez, a harmadik pedig a lízingadminisztrátor feladatainak ellátásához.</span><span class="sxs-lookup"><span data-stu-id="cca32-108">One role is appropriate for maintaining leases, one is appropriate for viewing leases, and one is appropriate for performing a lease clerk's duties.</span></span> <span data-ttu-id="cca32-109">Minden szerepkör rendelkezik az összes lízinglapra vonatkozó speciális engedélyekkel, és mindegyik lehetővé teszi a felhasználók számára a lízingek megtekintését, létrehozását, szerkesztését vagy törlését a feladatköreiknek megfelelően.</span><span class="sxs-lookup"><span data-stu-id="cca32-109">Each role has specific permissions for all lease pages, and each lets users view, create, edit, or delete leases, according to their job duties.</span></span>

| <span data-ttu-id="cca32-110">Szerep</span><span class="sxs-lookup"><span data-stu-id="cca32-110">Role</span></span>           | <span data-ttu-id="cca32-111">Leírás</span><span class="sxs-lookup"><span data-stu-id="cca32-111">Description</span></span> |
|----------------|-------------|
| <span data-ttu-id="cca32-112">Lízing karbantartása</span><span class="sxs-lookup"><span data-stu-id="cca32-112">Maintain Lease</span></span> | <span data-ttu-id="cca32-113">A szerepkörben lévő felhasználók lízingeket adhatnak hozzá, szerkeszthetnek, törölhetnek és tekinthetnek meg.</span><span class="sxs-lookup"><span data-stu-id="cca32-113">Users in this role can add, edit, delete, and view leases.</span></span> <span data-ttu-id="cca32-114">Ez a szerepkör olyan napi felhasználók számára készült, akiknek feladatai közé tartozik a havi naplóbejegyzések létrehozása és feladása, valamint új lízingek hozzáadása.</span><span class="sxs-lookup"><span data-stu-id="cca32-114">This role is designed for daily users whose tasks include creating and posting monthly journal entries and adding new leases.</span></span> <span data-ttu-id="cca32-115">Ez a szerepkör hozzáférést biztosít az összes eszközlízing-funkcióhoz.</span><span class="sxs-lookup"><span data-stu-id="cca32-115">This role gives access to all Asset leasing functionality.</span></span> |
| <span data-ttu-id="cca32-116">Lízing megtekintése</span><span class="sxs-lookup"><span data-stu-id="cca32-116">View Lease</span></span>     | <span data-ttu-id="cca32-117">A szerepkörben lévő felhasználók csak lízingbejegyzéseket, -ütemezéseket tekinthetnek meg és jelentéseket futtathatnak.</span><span class="sxs-lookup"><span data-stu-id="cca32-117">Users in this role can only view lease records, schedules, and run reports.</span></span> <span data-ttu-id="cca32-118">Nem hozhatnak létre új lízingeket, nem szerkeszthetik a meglévő lízingeket, és nem hozhatnak létre naplóbejegyzéseket a lízingekkel szemben.</span><span class="sxs-lookup"><span data-stu-id="cca32-118">They can't create new leases, edit existing leases, or create journal entries against leases.</span></span> <span data-ttu-id="cca32-119">A szerepkör olyan felhasználók számára készült, akiknek csak meg kell tekinteniük a lízingeket, a lízingütemezéseket és a lízingekkel szemben előforduló tranzakciókat.</span><span class="sxs-lookup"><span data-stu-id="cca32-119">The role is designed for users who just have to view leases, lease schedules, and the transactions that occur against those leases.</span></span> |
| <span data-ttu-id="cca32-120">Lízingkönyvelő</span><span class="sxs-lookup"><span data-stu-id="cca32-120">Lease Clerk</span></span>    | <span data-ttu-id="cca32-121">Ebben a szerepkörben lévő felhasználók csak új lízingeket hozhatnak létre.</span><span class="sxs-lookup"><span data-stu-id="cca32-121">Users in this role can only create new leases.</span></span> <span data-ttu-id="cca32-122">Nem szerkeszthetik és nem törölhetik a meglévő lízingeket, nem tekinthetik meg a lízingütemezéseket, illetve nem adhatnak fel lízingnapló-bejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="cca32-122">They can't edit or delete existing leases, view lease schedules, or post leasing journal entries.</span></span> <span data-ttu-id="cca32-123">Ez a szerepkör adatbeviteli kapacitással dolgozó felhasználók számára készült.</span><span class="sxs-lookup"><span data-stu-id="cca32-123">This role is designed for users who work in a data entry capacity.</span></span> |

<span data-ttu-id="cca32-124">Az alábbi lépésekkel rendelje hozzá a felhasználókat az Eszközlízingben használt szerepkörökhöz.</span><span class="sxs-lookup"><span data-stu-id="cca32-124">Follow these steps to assign users to the roles that are used in Asset leasing.</span></span>

1. <span data-ttu-id="cca32-125">Menjen a **Rendszergazda \> Biztonság \> Felhasználók szerepkörökhöz való hozzárendelés**.</span><span class="sxs-lookup"><span data-stu-id="cca32-125">Go to **System administration \> Security \> Assign users to roles**.</span></span>
2. <span data-ttu-id="cca32-126">Válassza a **Lízing karbantartása**, **Lízingkönyvelő** vagy a **Lízing megtekintése** szerepkört, majd válassza a **Felhasználók manuális hozzárendelése/kizárása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cca32-126">Select the **Maintain lease**, **Lease clerk**, or **View lease** role, and then select **Manually assign/exclude users**.</span></span>
3. <span data-ttu-id="cca32-127">Válassza ki a szerepkörhöz hozzárendelni kívánt felhasználót, majd válassza a **Hozzárendelés a szerepkörhöz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cca32-127">Select the user to assign to the role, and then select **Assign to role**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]