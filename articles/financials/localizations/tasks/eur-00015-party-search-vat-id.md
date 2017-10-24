--- 
title: "Fél keresése adószám használatával"
description: "Ez az eljárás bemutatja, hogyan kell elvégezni egy fél keresését a regisztrációs azonosító használatával."
author: v-oloski
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f47dfd99a99995bff3a5c443631fa724d36165bf
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="party-search-using-vat-id"></a><span data-ttu-id="1efbe-103">Fél keresése adószám használatával</span><span class="sxs-lookup"><span data-stu-id="1efbe-103">Party search using VAT ID</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1efbe-104">Ez az eljárás bemutatja, hogyan kell elvégezni egy fél keresését a regisztrációs azonosító használatával.</span><span class="sxs-lookup"><span data-stu-id="1efbe-104">This procedure shows how to complete a party search using a registration ID.</span></span> <span data-ttu-id="1efbe-105">Mielőtt ezt a műveletet végrehajthatná, be kell állítani az áfaazonosítót, és áfaazonosítót kell megadnia a szállítókhoz, vevőkhöz vagy jogi személyekhez.</span><span class="sxs-lookup"><span data-stu-id="1efbe-105">Before you can complete this procedure, you must set up VAT IDs and enter any VAT IDs for vendors, customers, or legal entities.</span></span>

<span data-ttu-id="1efbe-106">Ez az eljárás minden európai országra/régióra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="1efbe-106">This procedure applies to all European countries/regions.</span></span> <span data-ttu-id="1efbe-107">Ezt az eljárást a németországi elsődleges címmel rendelkező DEMF bemutatócég segítségével hozták létre.</span><span class="sxs-lookup"><span data-stu-id="1efbe-107">The procedure was created using the demo data company DEMF with a primary address in Germany.</span></span> <span data-ttu-id="1efbe-108">Ez az eljárás a kötelezettségeket kezelő vezető és a kinnlevőség-kezelő számára szól.</span><span class="sxs-lookup"><span data-stu-id="1efbe-108">This procedure is intended for an accounts payable manager or accounts receivable manager.</span></span> <span data-ttu-id="1efbe-109">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="1efbe-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="1efbe-110">Ugrás a Szervezeti adminisztráció > Globális címjegyzék > Globális címjegyzék elemre.</span><span class="sxs-lookup"><span data-stu-id="1efbe-110">Go to Organization administration > Global address book > Global address book.</span></span>
2. <span data-ttu-id="1efbe-111">Kattintson a Regisztrációs azonosító keresése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="1efbe-111">Click Registration ID search.</span></span>
3. <span data-ttu-id="1efbe-112">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="1efbe-112">Click Add.</span></span>
4. <span data-ttu-id="1efbe-113">A Regisztráció típusa mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1efbe-113">In the Registration type field, enter or select a value.</span></span>
    * <span data-ttu-id="1efbe-114">Ha például áfaazonosító típusú regisztrációs azonosítóval rendelkező feleket szeretne megkeresni, válassza az áfaazonosítót.</span><span class="sxs-lookup"><span data-stu-id="1efbe-114">For example, if you wanted to find parties with a registration ID of type VAT ID, select VAT ID.</span></span>  
5. <span data-ttu-id="1efbe-115">Az Ország/régió mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="1efbe-115">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="1efbe-116">Például írja be, hogy DEU.</span><span class="sxs-lookup"><span data-stu-id="1efbe-116">For example, enter DEU.</span></span>  
6. <span data-ttu-id="1efbe-117">Írjon be egy értéket a Regisztrációs szám mezőbe.</span><span class="sxs-lookup"><span data-stu-id="1efbe-117">In the Registration number field, type a value.</span></span>
7. <span data-ttu-id="1efbe-118">Kattintson a Keresés gombra.</span><span class="sxs-lookup"><span data-stu-id="1efbe-118">Click Find.</span></span>
    * <span data-ttu-id="1efbe-119">Minden, az adott regisztrációs azonosítóval rendelkező fél megjelenik.</span><span class="sxs-lookup"><span data-stu-id="1efbe-119">All parties with that registration ID will be displayed.</span></span>  

