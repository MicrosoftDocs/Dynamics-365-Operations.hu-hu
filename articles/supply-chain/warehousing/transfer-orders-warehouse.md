---
title: Raktárak beállítása átmozgatási rendelésekhez
description: Ez a témakör leírja, hogyan állíthat be raktárakat átmozgatási rendelésekhez.
author: Mirzaab
manager: AnnBe
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 8111601cb2948c66097b0f5b2f261b7462b279f9
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1567078"
---
# <a name="set-up-warehouses-for-transfer-orders"></a><span data-ttu-id="4c32e-103">Raktárak beállítása átmozgatási rendelésekhez</span><span class="sxs-lookup"><span data-stu-id="4c32e-103">Set up warehouses for transfer orders</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4c32e-104">A raktári szintek segítségével lehet létrehozni olyan hierarchiát, amely támogatja a raktárok közötti átmozgatási rendeléseket.</span><span class="sxs-lookup"><span data-stu-id="4c32e-104">You can use warehouse levels to create a hierarchy that supports transfer orders between warehouses.</span></span> <span data-ttu-id="4c32e-105">Ezen beállítás alapján számítja ki az alapütemezés az egyedi raktári szinteken szükséges cikkeket, és létrehozza a tervezett átmozgatási rendeléseket a feltöltéshez társított forrásraktárból.</span><span class="sxs-lookup"><span data-stu-id="4c32e-105">Based on this setup, master scheduling calculates item requirements at the individual warehouse level and generates planned transfer orders from an assigned source warehouse to fulfill them.</span></span>

1.  <span data-ttu-id="4c32e-106">Kattintson a **Készletgazdálkodás > Beállítás > Készlet részletezése > Raktárak** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="4c32e-106">Click **Inventory management > Setup > Inventory breakdown > Warehouses**.</span></span>

2.  <span data-ttu-id="4c32e-107">Az  lapon válassza ki a újratöltendő raktárat.</span><span class="sxs-lookup"><span data-stu-id="4c32e-107">Select the warehouse that you want to refill.</span></span>

3.  <span data-ttu-id="4c32e-108">Az **Alaptervezés** gyorslapon jelölje be a **Feltöltés** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="4c32e-108">On the **Master planning** FastTab, select the **Refilling** check box.</span></span>

4.  <span data-ttu-id="4c32e-109">A **Főraktár** mezőben válassza ki az újratöltési raktárként társítandó raktárt.</span><span class="sxs-lookup"><span data-stu-id="4c32e-109">In the **Main warehouse** field, select the warehouse that you want to assign as the refilling warehouse.</span></span> <span data-ttu-id="4c32e-110">Az alapütemezés kiszámítja a kiválasztott raktár esetében szükséges átmozgatást, és létrehoz egy tervezett átmozgatási rendelést a társított **Főraktár** forrásból.</span><span class="sxs-lookup"><span data-stu-id="4c32e-110">Master scheduling calculates a transfer requirement for the selected warehouse and generates a planned transfer order from the assigned **Main warehouse**.</span></span>
   
    > [!NOTE]
    > <P><span data-ttu-id="4c32e-111">Ha üresen hagyja a <STRONG>Feltöltés</STRONG> jelölőnégyzetet a kiválasztott raktárhoz a rendszer a <STRONG>Főraktár</STRONG> alapján viszonyított raktárszintet társít, a <STRONG>Főraktár</STRONG> azonban nincs beállítva feltöltő raktárként.</span><span class="sxs-lookup"><span data-stu-id="4c32e-111">If you clear the <STRONG>Refilling</STRONG> check box, the selected warehouse is assigned a warehouse level in regard to the <STRONG>Main warehouse</STRONG>, but the <STRONG>Main warehouse</STRONG> is not set up as a refilling warehouse.</span></span></P>

5.  <span data-ttu-id="4c32e-112">Az új beállítások alkalmazásához zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="4c32e-112">Close the page to apply the new setup.</span></span>


> [!TIP]
> <P><span data-ttu-id="4c32e-113">Ha szeretne feltöltési raktárt társítani, először tárolási dimenzióként kell beállítani a raktárt a <STRONG>Tárolásidimenzió-csoportok</STRONG> lapon.</span><span class="sxs-lookup"><span data-stu-id="4c32e-113">If you want to assign a warehouse for refilling, you must first set up the warehouse as a storage dimension on the <STRONG>Storage dimension groups</STRONG> page.</span></span> <span data-ttu-id="4c32e-114">Ezen a lapon válassza ki a <STRONG>Aktív</STRONG> mezőt és a <STRONG>Fedezeti terv dimenziónként</STRONG> mezőt a raktárhoz.</span><span class="sxs-lookup"><span data-stu-id="4c32e-114">On this page, select the <STRONG>Active</STRONG> field and the <STRONG>Coverage plan by dimension</STRONG> field for the warehouse.</span></span></P>

## <a name="set-up-transport-lead-time"></a><span data-ttu-id="4c32e-115">Szállítás átfutási idejének beállítása</span><span class="sxs-lookup"><span data-stu-id="4c32e-115">Set up transport lead time</span></span>

<span data-ttu-id="4c32e-116">Be kell állítania a raktárak között a szállítás átfutási idejét is a **Szállítási napok** oldalon.</span><span class="sxs-lookup"><span data-stu-id="4c32e-116">You must also set up the transport lead time between the warehouses on the **Transport days** page.</span></span> 
1. <span data-ttu-id="4c32e-117">Menjen a **Készletkezelés > Beállítások > Elosztás > Szállítási napok** menübe.</span><span class="sxs-lookup"><span data-stu-id="4c32e-117">Go to **Inventory management > Setup > Distribution > Transport days**.</span></span>
2. <span data-ttu-id="4c32e-118">Válasszon egy **raktárat** a **Bevételezési pont** mezőben.</span><span class="sxs-lookup"><span data-stu-id="4c32e-118">In the **Receiving point** field, select **warehouse**.</span></span>
3. <span data-ttu-id="4c32e-119">Válassza ki a **Szállítási raktár**, **Fogadó raktár**, és **Szállítási napok** értékeket.</span><span class="sxs-lookup"><span data-stu-id="4c32e-119">Select the **Shipping warehouse**, **Receiving warehouse**, and **Transport days**.</span></span> 
4. <span data-ttu-id="4c32e-120">(Nem kötelező) Beállíthatja a szállítási időt, a szállítási módtól függően a **Szállítási napok a szállítás módja szerint** lapon.</span><span class="sxs-lookup"><span data-stu-id="4c32e-120">(Optional) You can also set transport time, depending on the mode of delivery, under the **Transport days per mode of delivery** tab.</span></span>
