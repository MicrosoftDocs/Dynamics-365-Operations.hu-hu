--- 
title: "Bankhitelek beállítása és az akkreditívhez tartozó profilok feladása"
description: "Ez az eljárás bemutatja a banki hitel létrehozásán és az akkreditív feladásához szükséges profil közzétételén."
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 3419d975c087350c01c6854dbbae07b6bb20bc03
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a><span data-ttu-id="526f4-103">Bankhitelek beállítása és az akkreditívhez tartozó profilok feladása</span><span class="sxs-lookup"><span data-stu-id="526f4-103">Set up bank facilities and posting profiles for letter of credit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="526f4-104">Ez az eljárás bemutatja a banki hitel létrehozásán és az akkreditív feladásához szükséges profil közzétételén.</span><span class="sxs-lookup"><span data-stu-id="526f4-104">This procedure walks through creating a Bank facility and posting profile required to process Letters of credit.</span></span> 

<span data-ttu-id="526f4-105">Ezek az eljárások az „USMF” bemutatócéget használják.</span><span class="sxs-lookup"><span data-stu-id="526f4-105">This tasks uses the demo company 'USMF'.</span></span>






## <a name="general-ledger-parameter"></a><span data-ttu-id="526f4-106">Főkönyvi paraméter</span><span class="sxs-lookup"><span data-stu-id="526f4-106">General ledger parameter</span></span>
1. <span data-ttu-id="526f4-107">Ugorjon a Készpénz- és bankkezelés > Beállítás > Készpénz- és bankkezelési paraméterek pontra.</span><span class="sxs-lookup"><span data-stu-id="526f4-107">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="526f4-108">Bontsa ki a A banki bizonylat szakaszt.</span><span class="sxs-lookup"><span data-stu-id="526f4-108">Expand the Bank document section.</span></span>
3. <span data-ttu-id="526f4-109">Jelölje be az Importakkreditív engedélyezése lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="526f4-109">Select the Enable import letter of credit option.</span></span>
4. <span data-ttu-id="526f4-110">Jelölje be az Exportakkreditív engedélyezése lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="526f4-110">Select the Enable export letter of credit option.</span></span>
5. <span data-ttu-id="526f4-111">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="526f4-111">Click Save.</span></span>
6. <span data-ttu-id="526f4-112">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="526f4-112">Close the page.</span></span>

## <a name="create-bank-facility"></a><span data-ttu-id="526f4-113">Banki hitel létrehozása</span><span class="sxs-lookup"><span data-stu-id="526f4-113">Create Bank facility</span></span>
1. <span data-ttu-id="526f4-114">Ugorjon a Készpénz- és bankkezelés > Beállítás > Banki hitelek pontra.</span><span class="sxs-lookup"><span data-stu-id="526f4-114">Go to Cash and bank management > Setup > Bank facilities.</span></span>
2. <span data-ttu-id="526f4-115">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="526f4-115">Click New.</span></span>
3. <span data-ttu-id="526f4-116">A Hitelcsoport mezőben adja meg a banki hitelcsoportot.</span><span class="sxs-lookup"><span data-stu-id="526f4-116">In the Facility group field, enter the bank facility group name.</span></span>
4. <span data-ttu-id="526f4-117">A Leírás mezőbe írja be a banki hitelcsoport leírását.</span><span class="sxs-lookup"><span data-stu-id="526f4-117">In the Description field, enter the bank facility group description.</span></span>
5. <span data-ttu-id="526f4-118">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="526f4-118">Click Save.</span></span>
6. <span data-ttu-id="526f4-119">Kattintson a Hitelek lapra.</span><span class="sxs-lookup"><span data-stu-id="526f4-119">Click the Facility types tab.</span></span>
7. <span data-ttu-id="526f4-120">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="526f4-120">Click New.</span></span>
8. <span data-ttu-id="526f4-121">Írja be a cikk egyedi nevét a Hiteltípus mezőbe.</span><span class="sxs-lookup"><span data-stu-id="526f4-121">In the Facility type field, enter a unique code.</span></span>
9. <span data-ttu-id="526f4-122">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="526f4-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="526f4-123">A Hitelcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="526f4-123">In the Facility group field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="526f4-124">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="526f4-124">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="526f4-125">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="526f4-125">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="526f4-126">A Hitel természete mezőben válassza ki a hiteltípushoz tartozó természetet.</span><span class="sxs-lookup"><span data-stu-id="526f4-126">In the Facility nature field, select the nature of the bank facility.</span></span>
14. <span data-ttu-id="526f4-127">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="526f4-127">Click Save.</span></span>
15. <span data-ttu-id="526f4-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="526f4-128">Close the page.</span></span>

## <a name="bank-posting-profile"></a><span data-ttu-id="526f4-129">Banki feladási profil</span><span class="sxs-lookup"><span data-stu-id="526f4-129">Bank posting profile</span></span>
1. <span data-ttu-id="526f4-130">Ugorjon a Készpénz- és bankkezelés > Beállítás > Banki dokumentumok közzétele profil pontra.</span><span class="sxs-lookup"><span data-stu-id="526f4-130">Go to Cash and bank management > Setup > Bank documents posting profile.</span></span>
2. <span data-ttu-id="526f4-131">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="526f4-131">Click New.</span></span>
3. <span data-ttu-id="526f4-132">A Fiók/Csoport száma mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="526f4-132">In the Account/Group number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="526f4-133">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="526f4-133">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="526f4-134">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="526f4-134">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="526f4-135">Válassza ki a rendezéshez a fő számlát.</span><span class="sxs-lookup"><span data-stu-id="526f4-135">Select the main account for settlement.</span></span>
    * <span data-ttu-id="526f4-136">Ezt a számlát kell használni a pénzforgalmi előrejelzés kiszámításakor.</span><span class="sxs-lookup"><span data-stu-id="526f4-136">This account is used when calculating cash flow forecast.</span></span>  
7. <span data-ttu-id="526f4-137">A Díjfiók mezőben válassza ki a számlát a költségtranzakciókhoz.</span><span class="sxs-lookup"><span data-stu-id="526f4-137">In the Charges account field, select the account for expense transactions.</span></span>
8. <span data-ttu-id="526f4-138">Az Értékpapír-hitelszámla mezőben válassza ki a számlát az értékpapír-tranzakciókhoz.</span><span class="sxs-lookup"><span data-stu-id="526f4-138">In the Margin account field, select the account for margin transactions.</span></span>
    * <span data-ttu-id="526f4-139">Ez a számla lesz megterhelve a nyitó különbözet feladásakor, és ezen a számlán jelenik meg a jóváírás a kifizetés feladásakor.</span><span class="sxs-lookup"><span data-stu-id="526f4-139">This account is debited when the opening margin is posted and credited when the payment is posted.</span></span>  
9. <span data-ttu-id="526f4-140">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="526f4-140">Click Save.</span></span>


