---
title: Bankhitelek beállítása és az akkreditívhez tartozó profilok feladása
description: Ez az eljárás bemutatja a banki hitel létrehozásán és az akkreditív feladásához szükséges profil közzétételén.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bc94100461bc82e9e7cd243f198711ab61a79b0c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5225273"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a><span data-ttu-id="3e940-103">Bankhitelek beállítása és az akkreditívhez tartozó profilok feladása</span><span class="sxs-lookup"><span data-stu-id="3e940-103">Set up bank facilities and posting profiles for letter of credit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3e940-104">Ez az eljárás bemutatja a banki hitel létrehozásán és az akkreditív feladásához szükséges profil közzétételén.</span><span class="sxs-lookup"><span data-stu-id="3e940-104">This procedure walks through creating a Bank facility and posting profile required to process Letters of credit.</span></span> 

<span data-ttu-id="3e940-105">Ezek az eljárások az „USMF” bemutatócéget használják.</span><span class="sxs-lookup"><span data-stu-id="3e940-105">This tasks uses the demo company 'USMF'.</span></span>






## <a name="general-ledger-parameter"></a><span data-ttu-id="3e940-106">Főkönyvi paraméter</span><span class="sxs-lookup"><span data-stu-id="3e940-106">General ledger parameter</span></span>
1. <span data-ttu-id="3e940-107">Ugorjon a Készpénz- és bankkezelés > Beállítás > Készpénz- és bankkezelési paraméterek pontra.</span><span class="sxs-lookup"><span data-stu-id="3e940-107">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="3e940-108">Bontsa ki a A banki bizonylat szakaszt.</span><span class="sxs-lookup"><span data-stu-id="3e940-108">Expand the Bank document section.</span></span>
3. <span data-ttu-id="3e940-109">Jelölje be az Importakkreditív engedélyezése lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3e940-109">Select the Enable import letter of credit option.</span></span>
4. <span data-ttu-id="3e940-110">Jelölje be az Exportakkreditív engedélyezése lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="3e940-110">Select the Enable export letter of credit option.</span></span>
5. <span data-ttu-id="3e940-111">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3e940-111">Click Save.</span></span>
6. <span data-ttu-id="3e940-112">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3e940-112">Close the page.</span></span>

## <a name="create-bank-facility"></a><span data-ttu-id="3e940-113">Banki hitel létrehozása</span><span class="sxs-lookup"><span data-stu-id="3e940-113">Create Bank facility</span></span>
1. <span data-ttu-id="3e940-114">Ugorjon a Készpénz- és bankkezelés > Beállítás > Banki hitelek pontra.</span><span class="sxs-lookup"><span data-stu-id="3e940-114">Go to Cash and bank management > Setup > Bank facilities.</span></span>
2. <span data-ttu-id="3e940-115">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3e940-115">Click New.</span></span>
3. <span data-ttu-id="3e940-116">A Hitelcsoport mezőben adja meg a banki hitelcsoportot.</span><span class="sxs-lookup"><span data-stu-id="3e940-116">In the Facility group field, enter the bank facility group name.</span></span>
4. <span data-ttu-id="3e940-117">A Leírás mezőbe írja be a banki hitelcsoport leírását.</span><span class="sxs-lookup"><span data-stu-id="3e940-117">In the Description field, enter the bank facility group description.</span></span>
5. <span data-ttu-id="3e940-118">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3e940-118">Click Save.</span></span>
6. <span data-ttu-id="3e940-119">Kattintson a Hitelek lapra.</span><span class="sxs-lookup"><span data-stu-id="3e940-119">Click the Facility types tab.</span></span>
7. <span data-ttu-id="3e940-120">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3e940-120">Click New.</span></span>
8. <span data-ttu-id="3e940-121">Írja be a cikk egyedi nevét a Hiteltípus mezőbe.</span><span class="sxs-lookup"><span data-stu-id="3e940-121">In the Facility type field, enter a unique code.</span></span>
9. <span data-ttu-id="3e940-122">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="3e940-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="3e940-123">A Hitelcsoport mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3e940-123">In the Facility group field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="3e940-124">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="3e940-124">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="3e940-125">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3e940-125">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="3e940-126">A Hitel természete mezőben válassza ki a hiteltípushoz tartozó természetet.</span><span class="sxs-lookup"><span data-stu-id="3e940-126">In the Facility nature field, select the nature of the bank facility.</span></span>
14. <span data-ttu-id="3e940-127">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3e940-127">Click Save.</span></span>
15. <span data-ttu-id="3e940-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="3e940-128">Close the page.</span></span>

## <a name="bank-posting-profile"></a><span data-ttu-id="3e940-129">Banki feladási profil</span><span class="sxs-lookup"><span data-stu-id="3e940-129">Bank posting profile</span></span>
1. <span data-ttu-id="3e940-130">Ugorjon a Készpénz- és bankkezelés > Beállítás > Banki dokumentumok közzétele profil pontra.</span><span class="sxs-lookup"><span data-stu-id="3e940-130">Go to Cash and bank management > Setup > Bank documents posting profile.</span></span>
2. <span data-ttu-id="3e940-131">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="3e940-131">Click New.</span></span>
3. <span data-ttu-id="3e940-132">A Fiók/Csoport száma mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="3e940-132">In the Account/Group number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="3e940-133">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="3e940-133">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="3e940-134">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="3e940-134">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="3e940-135">Válassza ki a rendezéshez a fő számlát.</span><span class="sxs-lookup"><span data-stu-id="3e940-135">Select the main account for settlement.</span></span>
    * <span data-ttu-id="3e940-136">Ezt a számlát kell használni a pénzforgalmi előrejelzés kiszámításakor.</span><span class="sxs-lookup"><span data-stu-id="3e940-136">This account is used when calculating cash flow forecast.</span></span>  
7. <span data-ttu-id="3e940-137">A Díjfiók mezőben válassza ki a számlát a költségtranzakciókhoz.</span><span class="sxs-lookup"><span data-stu-id="3e940-137">In the Charges account field, select the account for expense transactions.</span></span>
8. <span data-ttu-id="3e940-138">Az Értékpapír-hitelszámla mezőben válassza ki a számlát az értékpapír-tranzakciókhoz.</span><span class="sxs-lookup"><span data-stu-id="3e940-138">In the Margin account field, select the account for margin transactions.</span></span>
    * <span data-ttu-id="3e940-139">Ez a számla lesz megterhelve a nyitó különbözet feladásakor, és ezen a számlán jelenik meg a jóváírás a kifizetés feladásakor.</span><span class="sxs-lookup"><span data-stu-id="3e940-139">This account is debited when the opening margin is posted and credited when the payment is posted.</span></span>  
9. <span data-ttu-id="3e940-140">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="3e940-140">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]