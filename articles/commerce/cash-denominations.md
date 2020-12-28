---
title: Készpénzcímletek konfigurálása a pénztár (POS) számára
description: A háttérirodában meghatározható a pénztárosok, értékesítési munkatársak és a vezetők által az üzletben levő POS modulban használandó bankjegyek és érmék készpénzcímlete.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreCashDeclarationTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: a34ae8084c0ad55221f4ab93eb8c6481fa8c4771
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412830"
---
# <a name="configure-cash-denominations-for-the-point-of-sale-pos"></a><span data-ttu-id="c62a8-103">Készpénzcímletek konfigurálása a pénztár (POS) számára</span><span class="sxs-lookup"><span data-stu-id="c62a8-103">Configure cash denominations for the point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c62a8-104">A háttérirodában meghatározható a pénztárosok, értékesítési munkatársak és a vezetők által az üzletben levő POS modulban használandó bankjegyek és érmék készpénzcímlete.</span><span class="sxs-lookup"><span data-stu-id="c62a8-104">Cash denominations for notes and coins can be defined in the back office to be used by cashiers, sales associates, and managers at the store from within the POS.</span></span> <span data-ttu-id="c62a8-105">Az ilyen címletek felhasználhatók a napvégi készpénzszámlálási fizetőeszköz-elszámolások vagy egy gyors értékesítés fizetése során.</span><span class="sxs-lookup"><span data-stu-id="c62a8-105">These denominations can be used to aid in counting cash for end of day tender declarations or for quickly tendering a sale.</span></span>

## <a name="define-denominations"></a><span data-ttu-id="c62a8-106">Címletek meghatározása</span><span class="sxs-lookup"><span data-stu-id="c62a8-106">Define denominations</span></span>

<span data-ttu-id="c62a8-107">A címletek üzletenként állíthatók be a **Beállítás** \> **Készpénzelszámolás** lehetőségnél az üzlet tulajdonságainak oldalán.</span><span class="sxs-lookup"><span data-stu-id="c62a8-107">The denominations are set up per store on the **Set up** \> **Cash declaration** option from the store property page.</span></span>

![Készpénzelszámolás beállítás](./media/image1-denomination.png)

<span data-ttu-id="c62a8-109">Címlet meghatározása:</span><span class="sxs-lookup"><span data-stu-id="c62a8-109">To define a denomination:</span></span>

1. <span data-ttu-id="c62a8-110">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="c62a8-110">Click **New**.</span></span>
1. <span data-ttu-id="c62a8-111">Adja meg a típust (érme vagy bankjegy).</span><span class="sxs-lookup"><span data-stu-id="c62a8-111">Specify the type (coin or note).</span></span>
1. <span data-ttu-id="c62a8-112">Adja meg az összeget (érték).</span><span class="sxs-lookup"><span data-stu-id="c62a8-112">Specify the amount (value).</span></span>

![Készpénzelszámolás címletek szerint oldal](./media/image2-denomination.png)

## <a name="configure-the-functionality-profile"></a><span data-ttu-id="c62a8-114">A funkcióprofil konfigurálása</span><span class="sxs-lookup"><span data-stu-id="c62a8-114">Configure the functionality profile</span></span>

<span data-ttu-id="c62a8-115">A POS-ben készpénzzel történő fizetés esetén a felhasználó a bankjegycímletek segítségével gyorsan beírhatja a vevő által fizetett összeget.</span><span class="sxs-lookup"><span data-stu-id="c62a8-115">When paying by cash in POS, the user can use the note denominations to quickly enter the amount paid by the customer.</span></span> <span data-ttu-id="c62a8-116">A funkcióprofilban beállíthatja a címlet kétféle megjelenítését a POS rendszerben.</span><span class="sxs-lookup"><span data-stu-id="c62a8-116">In the functionality profile, you can configure the two options for showing the denomination in POS.</span></span>

- <span data-ttu-id="c62a8-117">**Nagyobb vagy egyenlő az esedékes összeggel** – alapértelmezés szerint a POS csak azokat az esedékes összegnél nagyobb címleteket jeleníti meg, amelyek lehetővé teszik az egyetlen mozdulattal elvégezhető fizetést.</span><span class="sxs-lookup"><span data-stu-id="c62a8-117">**Greater or equal to amount due** – By default, POS will only show the note denominations that are greater than the amount due, which allows for one-touch tendering.</span></span> <span data-ttu-id="c62a8-118">Például, ha az esedékes összeg 7,50 dollár, a POS a következő címleteket jelenítené meg: $10, $20, $50 és $100.</span><span class="sxs-lookup"><span data-stu-id="c62a8-118">For example, if the amount due is $7.50, POS would show the following denominations: $10, $20, $50, and $100.</span></span> <span data-ttu-id="c62a8-119">A fenti összegek bármelyikének megérintése automatikusan kifizeti az értékesítést ehhez az összeghez.</span><span class="sxs-lookup"><span data-stu-id="c62a8-119">Touching any of these amounts will automatically tender the sale for that amount.</span></span> <span data-ttu-id="c62a8-120">A $1 és $5 címletek nem jelennek meg, mivel ezek az összegek kisebbek az esedékes összegnél.</span><span class="sxs-lookup"><span data-stu-id="c62a8-120">The $1 and $5 notes are not shown since these amounts are less than the amount due.</span></span>
- <span data-ttu-id="c62a8-121">**Minden címlet** – Jelölje be ezt a lehetőséget, hogy minden címletet megjelenítsen a POS rendszerben, függetlenül az esedékes összeg mértékétől.</span><span class="sxs-lookup"><span data-stu-id="c62a8-121">**All denominations** – Select this option to always show all note denominations in POS, regardless of the amount due.</span></span> <span data-ttu-id="c62a8-122">Ez azt jelenti, hogy a felhasználó az esedékes összeget eléréséhez címletkombinációkat használhat.</span><span class="sxs-lookup"><span data-stu-id="c62a8-122">This means that the user can use a combination of notes to reach the amount due.</span></span> <span data-ttu-id="c62a8-123">Például ha az esedékes összeg 25,00 dollár, a felhasználó választhatja a $20 és $5 címletet az értékesítés befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="c62a8-123">For example, if the amount due is $25.00, the user can choose $20 and $5 to complete the sale.</span></span>
