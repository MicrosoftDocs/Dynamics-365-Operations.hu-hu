---
title: "Nemzetközi bankszámlaszám (IBAN) számlák ellenőrzésének kezelése"
description: "Ez a témakör bemutatja a Nemzetközi bankszámlaszám (IBAN) számlák ellenőrzésének kezelését"
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: c6502a6fb0ceaed75fd5bb6ec5b2f13db1879eea
ms.openlocfilehash: 19e0528b95952de8e5503c361efcfeca4c529caf
ms.contentlocale: hu-hu
ms.lasthandoff: 10/12/2018

---

# <a name="manage-international-bank-account-number-iban-validation"></a><span data-ttu-id="c66c5-103">Nemzetközi bankszámlaszám (IBAN) ellenőrzésének kezelése</span><span class="sxs-lookup"><span data-stu-id="c66c5-103">Manage International Bank Account Number (IBAN) validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c66c5-104">A Nemzetközi bankszámlaszám (IBAN) ellenőrzése növeli az ellenőrzések mennyiségét, amikor IBAN-t ad hozzá egy bankszámlához.</span><span class="sxs-lookup"><span data-stu-id="c66c5-104">International Bank Account Number (IBAN) validation increases the amount of validation that is done when you add an IBAN to a bank account.</span></span>

<span data-ttu-id="c66c5-105">Az IBAN-szám szerkezetével kapcsolatos információkat a Microsoft Dynamics 365 for Finance and Operations tárolja.</span><span class="sxs-lookup"><span data-stu-id="c66c5-105">Information about the structure of the IBAN is stored in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="c66c5-106">Az IBAN szám első használatakor bankszámlákkal az adatokat automatikusan betöltődnek.</span><span class="sxs-lookup"><span data-stu-id="c66c5-106">That information is automatically loaded when you first use the IBAN on bank accounts.</span></span> <span data-ttu-id="c66c5-107">Az IBAN-szám hosszát, a bankszámlaszám és a bank regisztrációs azonosítójának kezdő pozícióit, és a bankszámlaszám és a bank regisztrációs azonosítójának hosszát tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="c66c5-107">It contains the length of the IBAN, the starting positions of the bank account number and the routing number, and the length of the bank account number and routing number.</span></span>

## <a name="set-up-iban-structures"></a><span data-ttu-id="c66c5-108">IBAN-szerkezetek beállítása</span><span class="sxs-lookup"><span data-stu-id="c66c5-108">Set up IBAN structures</span></span>

1. <span data-ttu-id="c66c5-109">Nyissa meg a következőt: **Készpénz- és bankkezelés \> Beállítás \> IBAN-struktúrák**.</span><span class="sxs-lookup"><span data-stu-id="c66c5-109">Go to **Cash and bank management \> Setup \> IBAN structures**.</span></span>
2. <span data-ttu-id="c66c5-110">Láthatja, hogy minden egyes ország vagy régió IBAN-struktúrája automatikusan be van állítva.</span><span class="sxs-lookup"><span data-stu-id="c66c5-110">Notice that the IBAN structures for each country or region have been set up automatically.</span></span>
3. <span data-ttu-id="c66c5-111">Ha testre akarja szabni egy adott ország vagy régió struktúráit, szerkesztheti azokat.</span><span class="sxs-lookup"><span data-stu-id="c66c5-111">If you want to customize the structures for a specific country or region, you can edit them.</span></span>
4. <span data-ttu-id="c66c5-112">A struktúradefiníciók az egyes új kiadások részei lesznek.</span><span class="sxs-lookup"><span data-stu-id="c66c5-112">The structure definitions will be a part of each new release.</span></span> <span data-ttu-id="c66c5-113">Használhatja a **Struktúrák alaphelyzetbe állítása** menüt, hogy az egyes frissítések után betöltse a legfrissebb definíciókat.</span><span class="sxs-lookup"><span data-stu-id="c66c5-113">You can use the **Reset structures** menu to load the latest definitions after each update.</span></span>

## <a name="validate-the-iban-structure-in-a-bank-account"></a><span data-ttu-id="c66c5-114">A bankszámla IBAN-struktúrájának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="c66c5-114">Validate the IBAN structure in a bank account</span></span>

1. <span data-ttu-id="c66c5-115">Menjen a **Készpénz és bankkezelés \> Bankszámlák \> Bankszámlák menüpontra**.</span><span class="sxs-lookup"><span data-stu-id="c66c5-115">Go to **Cash and bank management \> Bank accounts \> Bank accounts**.</span></span>
2. <span data-ttu-id="c66c5-116">Hozzon létre bankszámlát</span><span class="sxs-lookup"><span data-stu-id="c66c5-116">Create a bank account.</span></span>
3. <span data-ttu-id="c66c5-117">A **További információk** gyorslapon adjon meg egy IBAN-t.</span><span class="sxs-lookup"><span data-stu-id="c66c5-117">On the **Additional information** FastTab, enter an IBAN.</span></span>

    <span data-ttu-id="c66c5-118">Ha az IBAN-szám hossza nem egyezik meg minden egyes ország vagy terület meghatározott hosszával, egy figyelmeztető üzenetet kap.</span><span class="sxs-lookup"><span data-stu-id="c66c5-118">If the length of the IBAN doesn't match the length that is defined for each country or region, you will receive a warning message.</span></span> <span data-ttu-id="c66c5-119">Nem folytathatja, ha az IBAN-szám hossza nem egyezik meg az IBAN-struktúrában megadottal.</span><span class="sxs-lookup"><span data-stu-id="c66c5-119">You can't continue if the length of the IBAN doesn't match the length specified in the IBAN structure.</span></span>

    <span data-ttu-id="c66c5-120">Az ellenőrzés azt is ellenőrzi, hogy a bankszámla száma megegyezik-e az IBAN szám a bankszámlaszámot jelölő részével.</span><span class="sxs-lookup"><span data-stu-id="c66c5-120">The validation also verifies that the bank account number matches the part of the IBAN that represents the bank account number.</span></span> <span data-ttu-id="c66c5-121">Ha a bankszámlaszám nem egyezik meg, egy figyelmeztető üzenetet kap.</span><span class="sxs-lookup"><span data-stu-id="c66c5-121">If the bank account number doesn't match, you will receive a warning message.</span></span> <span data-ttu-id="c66c5-122">Ez az üzenet csak egy figyelmeztetés.</span><span class="sxs-lookup"><span data-stu-id="c66c5-122">This message is only a warning.</span></span> <span data-ttu-id="c66c5-123">Folytathatja, még akkor is, ha a bankszámlaszám nem egyezik meg.</span><span class="sxs-lookup"><span data-stu-id="c66c5-123">You can continue even if the bank account number doesn't match.</span></span>

    <span data-ttu-id="c66c5-124">Az ellenőrzés azt is ellenőrzi, hogy a bank regisztrációs azonosítója megegyezik-e az IBAN-szám a bank regisztrációs azonosítóját jelölő részével.</span><span class="sxs-lookup"><span data-stu-id="c66c5-124">The validation also verifies that the bank routing number matches the part of the IBAN that represents the bank routing number.</span></span> <span data-ttu-id="c66c5-125">A bank regisztrációs azonosítója tartalmazza a banki számot, és gyakran egy további bankfiókot is.</span><span class="sxs-lookup"><span data-stu-id="c66c5-125">The routing number includes a bank number and often an additional bank branch.</span></span> <span data-ttu-id="c66c5-126">Ha a bank regisztrációs azonosítója nem egyezik meg, egy figyelmeztető üzenetet kap.</span><span class="sxs-lookup"><span data-stu-id="c66c5-126">If the bank routing number doesn't match, you will receive a warning message.</span></span> <span data-ttu-id="c66c5-127">Ez az üzenet csak egy figyelmeztetés.</span><span class="sxs-lookup"><span data-stu-id="c66c5-127">This message is only a warning.</span></span> <span data-ttu-id="c66c5-128">Folytathatja, még akkor is, ha a bank regisztrációs azonosítója nem egyezik meg.</span><span class="sxs-lookup"><span data-stu-id="c66c5-128">You can continue even if the bank routing number doesn't match.</span></span>

