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
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: e091aab70a98e0f4b96c41c1ee48926947539105
ms.contentlocale: hu-hu
ms.lasthandoff: 08/31/2018

---

# <a name="manage-international-bank-account-number-iban-account-validation"></a><span data-ttu-id="6a985-103">Nemzetközi bankszámlaszám (IBAN) számlák ellenőrzésének kezelése</span><span class="sxs-lookup"><span data-stu-id="6a985-103">Manage International Bank Account Number (IBAN) account validation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6a985-104">A Nemzetközi bankszámlaszám (IBAN) számla ellenőrzése növeli az ellenőrzések mennyiségét, amikor IBAN-t ad hozzá egy bankszámlához.</span><span class="sxs-lookup"><span data-stu-id="6a985-104">International Bank Account Number (IBAN) account validation increases the amount of validation that is done when you add an IBAN to a bank account.</span></span>

<span data-ttu-id="6a985-105">Az IBAN szám szerkezete tárolva van a Microsoft Dynamics 365 for Finance and Operations alkalmazásban, és az IBAN szám első használatakor a bankszámlák esetén automatikusan betöltődik.</span><span class="sxs-lookup"><span data-stu-id="6a985-105">The structure of the IBAN is stored in Microsoft Dynamics 365 for Finance and Operation, and is automatically loaded when you first use the IBAN on bank accounts.</span></span> <span data-ttu-id="6a985-106">A bankszámlaszám az IBAN-számhoz definiált szerkezet része.</span><span class="sxs-lookup"><span data-stu-id="6a985-106">The bank account number is part of the structure defined for an IBAN number.</span></span> <span data-ttu-id="6a985-107">A szerkezet alapján ha számlaszám helye és hossza az IBAN számban nem egyezik meg az egyes országokhoz vagy területekhez meghatározott szerkezetnek, figyelmeztető üzenet fog kapni.</span><span class="sxs-lookup"><span data-stu-id="6a985-107">Based on that structure, if the position and length of the account number in the IBAN don't match the position that is defined in the structure for each country or region, you will receive warning messages.</span></span>

## <a name="set-up-iban-structures"></a><span data-ttu-id="6a985-108">IBAN-szerkezetek beállítása</span><span class="sxs-lookup"><span data-stu-id="6a985-108">Set up IBAN structures</span></span>

1. <span data-ttu-id="6a985-109">Nyissa meg a következőt: **Készpénz- és bankkezelés \> Beállítás \> IBAN-struktúrák**.</span><span class="sxs-lookup"><span data-stu-id="6a985-109">Go to **Cash and bank management \> Setup \> IBAN structures**.</span></span>
2. <span data-ttu-id="6a985-110">Láthatja, hogy minden egyes ország vagy régió IBAN-struktúrája automatikusan be van állítva.</span><span class="sxs-lookup"><span data-stu-id="6a985-110">Notice that the IBAN structures for each country or region have been set up automatically.</span></span>
3. <span data-ttu-id="6a985-111">Ha testre szabja egy adott ország vagy régió struktúráit, szerkesztheti azokat.</span><span class="sxs-lookup"><span data-stu-id="6a985-111">If you must customize the structures for a specific country or region, you can edit them.</span></span>
4. <span data-ttu-id="6a985-112">A struktúradefiníciók az egyes új kiadások részei lesznek.</span><span class="sxs-lookup"><span data-stu-id="6a985-112">The structure definitions will be a part of each new release.</span></span> <span data-ttu-id="6a985-113">Használhatja a **Struktúrák alaphelyzetbe állítása** menüt, hogy az egyes frissítések után betöltse a legfrissebb definíciókat.</span><span class="sxs-lookup"><span data-stu-id="6a985-113">You can use the **Reset structures** menu to load the latest definitions after each update.</span></span>

## <a name="validate-the-iban-structure-in-a-bank-account"></a><span data-ttu-id="6a985-114">A bankszámla IBAN-struktúrájának ellenőrzése</span><span class="sxs-lookup"><span data-stu-id="6a985-114">Validate the IBAN structure in a bank account</span></span>

1. <span data-ttu-id="6a985-115">Menjen a **Készpénz és bankkezelés \> Bankszámlák \> Bankszámlák menüpontra**.</span><span class="sxs-lookup"><span data-stu-id="6a985-115">Go to **Cash and bank management \> Bank accounts \> Bank accounts**.</span></span>
2. <span data-ttu-id="6a985-116">Hozzon létre bankszámlát</span><span class="sxs-lookup"><span data-stu-id="6a985-116">Create a bank account.</span></span>
3. <span data-ttu-id="6a985-117">A **További információk** gyorslapon adjon meg egy IBAN-t.</span><span class="sxs-lookup"><span data-stu-id="6a985-117">On the **Additional information** FastTab, enter an IBAN.</span></span>

    <span data-ttu-id="6a985-118">Ha számlaszám helye és hossza az IBAN számban nem egyezik meg az egyes országokhoz vagy területekhez meghatározott szerkezetnek, egy üzenetet fog kapni.</span><span class="sxs-lookup"><span data-stu-id="6a985-118">If the position and length of the account number in the IBAN don't match the position that is defined in the structure for each country or region, you receive a message.</span></span> <span data-ttu-id="6a985-119">Nem folytathatja, ha az IBAN-szám hossza nem egyezik meg az IBAN-struktúrában megadottal.</span><span class="sxs-lookup"><span data-stu-id="6a985-119">You can't continue if the length of the IBAN doesn't match the length in the IBAN structure.</span></span>

    <span data-ttu-id="6a985-120">Az ellenőrzés azt is ellenőrzi, hogy a bankszámla száma megegyezik-e az IBAN szám a bankszámlaszámot jelölő részével.</span><span class="sxs-lookup"><span data-stu-id="6a985-120">The validation also verifies that the bank account number matches the part of the IBAN that represents the bank account number.</span></span> <span data-ttu-id="6a985-121">Ha a bankszámlaszám nem egyezik meg, egy figyelmeztető üzenetet kap.</span><span class="sxs-lookup"><span data-stu-id="6a985-121">If the bank account number doesn't match, you receive a warning message.</span></span> <span data-ttu-id="6a985-122">Ez az üzenet csak egy figyelmeztetés.</span><span class="sxs-lookup"><span data-stu-id="6a985-122">This message is only a warning.</span></span> <span data-ttu-id="6a985-123">Folytathatja, még akkor is, ha a bankszámlaszám nem egyezik meg.</span><span class="sxs-lookup"><span data-stu-id="6a985-123">You can continue even if the bank account number doesn't match.</span></span>

