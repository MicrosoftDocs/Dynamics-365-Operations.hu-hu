---
title: " Konfigurációk tárolása kiskereskedelmi kimutatásokhoz"
description: Ez az eljárás a Commerce kimutatások létrehozásának és feladásának módját befolyásoló üzleti konfigurációkat mutatja be.
author: jashanno
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b73282abd2df92b3f466f7c1c6c210173001fd7
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3022757"
---
# <a name="store-configurations-for-retail-statements"></a><span data-ttu-id="76779-103"> Konfigurációk tárolása kiskereskedelmi kimutatásokhoz</span><span class="sxs-lookup"><span data-stu-id="76779-103">Store configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="76779-104">Ez az eljárás a Commerce kimutatások létrehozásának és feladásának módját befolyásoló üzleti konfigurációkat mutatja be.</span><span class="sxs-lookup"><span data-stu-id="76779-104">This procedure walks through configurations for the store that affect how Commerce statements get created and posted.</span></span> <span data-ttu-id="76779-105">Az üzletekkel kapcsolatos pénzügyi dimenziókat egy másik eljárás mutatja be.</span><span class="sxs-lookup"><span data-stu-id="76779-105">Financial dimensions on stores are covered in another procedure.</span></span> <span data-ttu-id="76779-106">Ez az eljárás az USRT bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="76779-106">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="76779-107">A **Navigációs ablaktáblán** lépjen a **Modulok > Retail és Commerce > Csatornák > Áruházak > Minden áruház** részhez.</span><span class="sxs-lookup"><span data-stu-id="76779-107">In the **Navgiation pane**, go to **Modules > Retail and Commerce > Channels > Stores > All stores**.</span></span>
2. <span data-ttu-id="76779-108">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="76779-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="76779-109">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="76779-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="76779-110">Kattintson a **Szerkesztés** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="76779-110">Click **Edit**.</span></span>
5. <span data-ttu-id="76779-111">A **Kimutatás/zárás** gyorslap beállításai hatással vannak a kimutatások létrehozására, ellenőrzésére és az üzlet részére történő feladására.</span><span class="sxs-lookup"><span data-stu-id="76779-111">The settings in the **Statement/closing** fastTab affect the statement creation, validation, and posting for the store.</span></span> <span data-ttu-id="76779-112">Bontsa ki a **Kimutatás/zárás**gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="76779-112">Expand the **Statement/closing** fastTab.</span></span>  
6. <span data-ttu-id="76779-113">A **Kimutatás módszere** mezőben válassza ki a kimutatássorok csoportosításához használni kívánt módszert.</span><span class="sxs-lookup"><span data-stu-id="76779-113">In the **Statement method** field, select the method you want to use to to group the statement lines by.</span></span>  
7. <span data-ttu-id="76779-114">Válassza az "Igen" lehetőséget a **Naponta egy kimutatás** pontban, ha csak napi egy kimutatást szeretne létrehozni, amikor a kimutatás létrehozása kötegelt feladat segítségével hoz létre kimutatásokat.</span><span class="sxs-lookup"><span data-stu-id="76779-114">Select "Yes" in **One statement per day** if there should only be one statement created per day when creating statements from the statement creation batch job.</span></span>  
8. <span data-ttu-id="76779-115">A **Fizetőeszköz-elszámolási számítás** mező határozza meg, hogy a rendszer összeadja-e a fizetőeszköz-elszámolásokat, vagy az utolsó elemet használja.</span><span class="sxs-lookup"><span data-stu-id="76779-115">The **Tender declaration calculation** field defines whether tender declarations should be added together or if the last one should be used.</span></span>  
9. <span data-ttu-id="76779-116">A **Kerekítés** mezőben válassza ki, hogy a kerekítési különbségek a főkönyvi számlába kerüljenek.</span><span class="sxs-lookup"><span data-stu-id="76779-116">In the **Rounding** field, select the ledger account to post rounding differences into.</span></span>  
10. <span data-ttu-id="76779-117">A **Kerekítés maximális összege** mezőben megadhatja a maximálisan megengedett kerekítési összeget.</span><span class="sxs-lookup"><span data-stu-id="76779-117">In the **Maximum rounding difference** field, enter the maximum rounding difference allowed.</span></span>
11. <span data-ttu-id="76779-118">A **Feladás** mezőben megadhatja az adott kimutatás esetén engedélyezett maximális teljes feladási eltérést.</span><span class="sxs-lookup"><span data-stu-id="76779-118">In the **Posting** field, enter the maximum total posting difference allowed for a statement.</span></span>
12. <span data-ttu-id="76779-119">A **Műszak** mezőben megadhatja egy adott műszak esetén engedélyezett maximális teljes eltérést.</span><span class="sxs-lookup"><span data-stu-id="76779-119">In the **Shift** field, enter the maximum total difference within a shift in a statement.</span></span>  
13. <span data-ttu-id="76779-120">A **Tranzakció** mezőben megadhatja az adott kimutatássorban engedélyezett maximális teljes eltérést.</span><span class="sxs-lookup"><span data-stu-id="76779-120">In the **Transaction** field, enter the maximum total difference in a statement line.</span></span>  
14. <span data-ttu-id="76779-121">A **Zárási mód** mezőben meghatározhatja, hogy a kimutatásban csak lezárt műszak részét képező tranzakciók szerepelhessenek-e, vagy bekerülhessen bármilyen, az adott dátumsávba/idősávba eső tranzakció.</span><span class="sxs-lookup"><span data-stu-id="76779-121">In the **Closing method** field, define whether transactions that will be included in a statement should be part of a closed shift or if they can be any transactions within the defined date/time range.</span></span>  
15. <span data-ttu-id="76779-122">A **Munkanap vége** mezőben tud megadni megfelelő időpontot, ha azt szeretné, hogy az éjfél utáni tranzakciókat az előző napra vonatkozóan adja fel a rendszer.</span><span class="sxs-lookup"><span data-stu-id="76779-122">In the **End of business day** field, enter a time if transactions that happen after midnight should be posted with the previous day.</span></span>  
16. <span data-ttu-id="76779-123">Válassza az „Igen” lehetőséget a **Feladás munkanapként** pontban, ha azt szeretné, hogy az éjfél utáni tranzakciókat az előző napra vonatkozóan adja fel a rendszer.</span><span class="sxs-lookup"><span data-stu-id="76779-123">Select "Yes" in **Post as business day** if transactions that happen after midnight should be posted as part of the previous day.</span></span>  
17. <span data-ttu-id="76779-124">Válassza az „Igen” lehetőséget a **Kimutatás szerinti bontás módszere** pontban, ha szeretné, hogy a rendszer hozzon létre kimutatást minden megjelölt kimutatásmódszer segítségével.</span><span class="sxs-lookup"><span data-stu-id="76779-124">Select "Yes" in **Split by Statement method** to get statements created for each statement method defined.</span></span> <span data-ttu-id="76779-125">Ez akkor lehet hasznos, ha a feladás teljesítményét javítani szükséges a magas tranzakciószámmal működő üzletek esetében, így ugyanis a rendszer több kisebb, párhuzamosan feldolgozható kimutatást hoz létre.</span><span class="sxs-lookup"><span data-stu-id="76779-125">This can be useful if the performance of the posting needs to be improved for stores with high transaction volumes since it will create many smaller statements that can be processed in parallel.</span></span>  
18. <span data-ttu-id="76779-126">Az **Általános** gyorslapon az **Alapértelmezett vevő** mezőben tudja kiválasztani az utcáról betérő vevőkhöz használni kívánt vevőszámlát.</span><span class="sxs-lookup"><span data-stu-id="76779-126">In the **General** fastTab, in the **Default customer** field, you can select the customer account to use for sales to walk-in customers.</span></span>  

