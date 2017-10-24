---
title: "Szállítmány beállítása"
description: "Ez a témakör azt mutatja be, hogyan kell konfigurálni a bejövő bizományosi készlet műveleteit."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DirPartyTable, EcoResTrackingDimensionGroup, InventJournalName, InventJournalOwnershipChange, InventOwner, InventTableInventoryDimensionGroups, VendTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 220804
ms.assetid: 88822f78-4de5-462c-a55f-1f766c572719
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 41c1b8de0aae24efb30a670d3109b6d65e6abd9c
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-consignment"></a><span data-ttu-id="11f76-103">Szállítmány beállítása</span><span class="sxs-lookup"><span data-stu-id="11f76-103">Set up consignment</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="11f76-104">Ez a témakör azt mutatja be, hogyan kell konfigurálni a bejövő bizományosi készlet műveleteit.</span><span class="sxs-lookup"><span data-stu-id="11f76-104">This topic explains how to configure inbound consignment inventory operations.</span></span>

<span data-ttu-id="11f76-105">A bizományosi árukészlet olyan készlet, amely a szállító tulajdonában van, de a tárolása az Ön telephelyén történik.</span><span class="sxs-lookup"><span data-stu-id="11f76-105">Consignment inventory is inventory that’s owned by a vendor, but stored at your site.</span></span> <span data-ttu-id="11f76-106">Ha készen áll a felhasználására vagy a készlet használatára, átveszi a készlet tulajdonjogát.</span><span class="sxs-lookup"><span data-stu-id="11f76-106">When you’re ready to consume or use the inventory, you take over the ownership of the inventory.</span></span> <span data-ttu-id="11f76-107">Ez a témakör a bizományosi folyamatok engedélyezéséhez szükséges beállításokat ismerteti.</span><span class="sxs-lookup"><span data-stu-id="11f76-107">This topic describes the setup needed to enable consignment processes.</span></span> <span data-ttu-id="11f76-108">A bizományosi folyamatok beállításával kapcsolatos további tudnivalókért lásd: [Consignment](consignment.md).</span><span class="sxs-lookup"><span data-stu-id="11f76-108">For more information about consignment processes, see [Consignment](consignment.md).</span></span>

## <a name="inventory-owners"></a><span data-ttu-id="11f76-109">Készlettulajdonosok</span><span class="sxs-lookup"><span data-stu-id="11f76-109">Inventory owners</span></span>
<span data-ttu-id="11f76-110">Fizikai bejövő bizományosi készlet rögzítéséhez meg kell határozni a szállító-tulajdonost.</span><span class="sxs-lookup"><span data-stu-id="11f76-110">In order to record physical inbound consignment inventory, you need to define a vendor owner.</span></span> <span data-ttu-id="11f76-111">Ez a **készlettulajdonos** oldalon történik.</span><span class="sxs-lookup"><span data-stu-id="11f76-111">This is done on the **Inventory owner** page.</span></span> <span data-ttu-id="11f76-112">Ha bejelöli a **szállítói számlát**, ezzel létrehozza a **Név** és **Tulajdonos** mezők alapértelmezett értékeit.</span><span class="sxs-lookup"><span data-stu-id="11f76-112">When you select a **Vendor account** this generates default values for the **Name** and **Owner** fields.</span></span> <span data-ttu-id="11f76-113">Az a **tulajdonos** mezőben lévő érték látható a szállító számára, ezért érdemes úgy módosítani, hogy a szállítói számla nevei ne legyenek könnyen felismerhetők külső felhasználók számára.</span><span class="sxs-lookup"><span data-stu-id="11f76-113">The value in the **Owner** field will be visible to the vendor, so you might want to change it if your vendor account names aren’t easy for external people to recognize.</span></span> <span data-ttu-id="11f76-114">A **tulajdonos** mezőt lehet módosítani, de csak addig a pontig, amikor menti a **készlettulajdonos** rekordot.</span><span class="sxs-lookup"><span data-stu-id="11f76-114">It’s possible to edit the **Owner** field, but only up to the point when you save the **Inventory owner** record.</span></span> <span data-ttu-id="11f76-115">A **Név** mezőt a rendszer automatikusan beírja annak a félnek a neve alapján, akihez a szállítói számla hozzá van rendelve, és ez nem módosítható.</span><span class="sxs-lookup"><span data-stu-id="11f76-115">The **Name** field is populated with the name of the party that the vendor account is associated with, and this cannot be changed.</span></span>

<span data-ttu-id="11f76-116">[![készlettulajdonosok](./media/inventory-owners.png)](./media/inventory-owners.png)</span><span class="sxs-lookup"><span data-stu-id="11f76-116">[![inventory-owners](./media/inventory-owners.png)](./media/inventory-owners.png)</span></span>

## <a name="tracking-dimension-group"></a><span data-ttu-id="11f76-117">Nyomonkövetésidimenzió-csoport</span><span class="sxs-lookup"><span data-stu-id="11f76-117">Tracking dimension group</span></span>
<span data-ttu-id="11f76-118">A bizományosi folyamatokban használandó cikkeket társítani kell egy **nyomon követési dimenziócsoporttal**, ahol a **tulajdonos** dimenzió értéke **aktív**.</span><span class="sxs-lookup"><span data-stu-id="11f76-118">Items that are going to be used in consignment processes must be associated with a **Tracking dimension group** where the **Owner** dimension is set to **Active**.</span></span> <span data-ttu-id="11f76-119">A tulajdonos dimenzió esetében a **leltár** és a **pénzügyi készlet** opció mindig ki van választva.</span><span class="sxs-lookup"><span data-stu-id="11f76-119">The Owner dimension always has the **Physical inventory** and **Financial inventory** options selected.</span></span> <span data-ttu-id="11f76-120">A **fedezeti terv dimenziónként** soha nincs bejelölve.</span><span class="sxs-lookup"><span data-stu-id="11f76-120">The **Coverage plan by dimension** is never selected.</span></span>

<span data-ttu-id="11f76-121">[![nyomonkövetésidimenzió-csoport](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)</span><span class="sxs-lookup"><span data-stu-id="11f76-121">[![tracking-dimension-group](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)</span></span>

## <a name="inventory-ownership-change-journal"></a><span data-ttu-id="11f76-122">Készlet tulajdonosváltozási naplója</span><span class="sxs-lookup"><span data-stu-id="11f76-122">Inventory ownership change journal</span></span>
<span data-ttu-id="11f76-123">A **készlettulajdonos-változási**napló arra szolgál, hogy rögzítse, amikor a bizományosi készlet tulajdonosa a szállítóról a felhasználó jogi személyre változik.</span><span class="sxs-lookup"><span data-stu-id="11f76-123">The **Inventory ownership change** journal is used to record the transfer of ownership of consignment inventory from the vendor to the legal entity that’s consuming it.</span></span> <span data-ttu-id="11f76-124">Mint bármely készletnapló esetében ezt is azonosítani kell egy készletnapló-névvel.</span><span class="sxs-lookup"><span data-stu-id="11f76-124">Like any inventory journal, it must be identified with an Inventory journal name.</span></span> <span data-ttu-id="11f76-125">Ezeknek a neveknek a létrehozása a **készletnapló-nevek** lapon történik, és a **naplótípust** **tulajdonos módosítása** értékre kell állítani.</span><span class="sxs-lookup"><span data-stu-id="11f76-125">These names are created on the **Inventory journal names** page, and the **Journal type** must be set to **Ownership change**.</span></span>

<span data-ttu-id="11f76-126">[![készlet tulajdonosváltozási naplója](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)</span><span class="sxs-lookup"><span data-stu-id="11f76-126">[![inventory-ownership-change-journal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)</span></span>

## <a name="vendor-collaboration-in-consignment-processes"></a><span data-ttu-id="11f76-127">Szállítói együttműködés a bizományosi folyamatokban.</span><span class="sxs-lookup"><span data-stu-id="11f76-127">Vendor collaboration in consignment processes</span></span>
<span data-ttu-id="11f76-128">Ha az Ön szállítói a szállítói együttműködési felületet használják, ezt arra is felhasználhatják, hogy nyomon kövessék az Ön telephelyén lévő készlet felhasználását.</span><span class="sxs-lookup"><span data-stu-id="11f76-128">If your vendors are using the vendor collaboration interface, they can use this to monitor the consumption of inventory at your site.</span></span> <span data-ttu-id="11f76-129">A szállítóknak a szállítói együttműködésben való beállítására vonatkozó további tudnivalókat lásd: [- szállítói együttműködés felhasználóinak biztonsági konfigurációja](../procurement/configure-security-vendor-portal-users.md).</span><span class="sxs-lookup"><span data-stu-id="11f76-129">For more information about setting up vendors to use vendor collaboration, see [Configuration of security for vendor collaboration users](../procurement/configure-security-vendor-portal-users.md).</span></span>
