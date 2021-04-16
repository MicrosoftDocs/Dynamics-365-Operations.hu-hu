---
title: Globális adóelőleg beállítása
description: Ez a témakör az értékesítések és beszerzések globális adóelőleg-beállításának lépéseit sorolja fel.
author: roschlom
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 3270b3f75d719fef9a7eb991c49e9d6585cd44d8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815308"
---
# <a name="set-up-global-withholding-tax"></a><span data-ttu-id="2c264-103">Globális adóelőleg beállítása</span><span class="sxs-lookup"><span data-stu-id="2c264-103">Set up global withholding tax</span></span>

<span data-ttu-id="2c264-104">Ez a témakör az értékesítések és beszerzések globális adóelőleg-beállításának lépéseit sorolja fel.</span><span class="sxs-lookup"><span data-stu-id="2c264-104">This topic lists the steps for setting up global withholding tax for sales and purchases.</span></span> 

1. <span data-ttu-id="2c264-105">Állítsa be az adóelőlegekkel kapcsolatos hatóságokat az **Adóelőlegek hatóságai** oldalon.</span><span class="sxs-lookup"><span data-stu-id="2c264-105">Set up withholding tax authorities on the **Withholding tax authorities** page.</span></span>

2. <span data-ttu-id="2c264-106">Állítsa be az adóelőleg-kiegyenlítési időszakokat az **Adóelőleg-kiegyenlítési időszakok** oldalon.</span><span class="sxs-lookup"><span data-stu-id="2c264-106">Set up withholding settlement periods on the **Withholding tax settlement periods** page.</span></span>

3. <span data-ttu-id="2c264-107">Állítsa be az adóelőleg feladására vonatkozó főkönyvi csoportot az **Adóelőleg > Főkönyvi feladási csoport** oldalon.</span><span class="sxs-lookup"><span data-stu-id="2c264-107">Set up withholding ledger posting group on the **Withholding tax > ledger posting group** page.</span></span>

   > [!Note] 
   >
   > <span data-ttu-id="2c264-108">Az **Adóelőleg** számlát a rendszer az Adóelőleg **Feladás típusa** fő számlával rendeli hozzá.</span><span class="sxs-lookup"><span data-stu-id="2c264-108">**Withholding tax** account will be assigned with a main account with **Posting type** of Withholding tax.</span></span> <span data-ttu-id="2c264-109">Az **Adóelőleg ellenszámla** számlát a rendszer az Adóelőleg ellenszámlája **Feladás típusa** fő számlával rendeli hozzá.</span><span class="sxs-lookup"><span data-stu-id="2c264-109">**Withholding tax offset** account will also be assigned with a main account with **Posting type** "Withholding tax offset".</span></span> <span data-ttu-id="2c264-110">Lépjen a **Főkönyv > Számlatükör > Számlák > Fő számlák** pontra, állítsa be a **Feladás típusa** értékét a fő számlákhoz tartozó **Feladás-ellenőrzés** alárendelt űrlapon.</span><span class="sxs-lookup"><span data-stu-id="2c264-110">Go to **General ledger > Chart of accounts > Accounts > Main accounts**, set up the **Posting type** in the **Posting validation** sub-form for the main accounts.</span></span>

4. <span data-ttu-id="2c264-111">Állítsa be az adóelőlegekkel kapcsolatos kódokat az **Adóelőlegek kódjai** oldalon.</span><span class="sxs-lookup"><span data-stu-id="2c264-111">Set up withholding tax codes on the **Withholding tax codes** page.</span></span>

5. <span data-ttu-id="2c264-112">Állítsa be az adóelőlegekkel kapcsolatos csoportokat az **Adóelőlegek csoportjai** oldalon.</span><span class="sxs-lookup"><span data-stu-id="2c264-112">Set up withholding tax groups on the **Withholding tax groups** page.</span></span>

6. <span data-ttu-id="2c264-113">Állítsa be az adóelőleg bevételtípusát az **Adóelőleg bevételének** **típusai** oldalon.</span><span class="sxs-lookup"><span data-stu-id="2c264-113">Set up withholding tax revenue types on the **Withholding tax revenue** **types** page.</span></span>

7. <span data-ttu-id="2c264-114">Állítsa be az adóelőlegekkel kapcsolatos csoportokat a **Cikk-adóelőlegek csoportjai** oldalon egy cikk vagy szolgáltatás esetében.</span><span class="sxs-lookup"><span data-stu-id="2c264-114">Set up withholding tax groups on the **Item withholding tax groups** page for an item or service.</span></span>

8. <span data-ttu-id="2c264-115">Állítsa be a **Minimális számlaösszeg** értékét a **Főkönyvi paraméterek > Adóelőleg** oldalon.</span><span class="sxs-lookup"><span data-stu-id="2c264-115">Set up **Minimum invoice amount** on the **General ledger parameters > Withholding tax** page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]