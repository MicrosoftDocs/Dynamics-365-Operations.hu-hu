--- 
title: "Adóhatóságok beállítása"
description: "Az adóhatóságok olyan entitások amelyek felé jelenteni és fizetni kell a begyűjtött áfát."
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 909433a04c1185039938f6233b30c235e7b8ed8b
ms.contentlocale: hu-hu
ms.lasthandoff: 09/14/2018

---
# <a name="set-up-sales-tax-authorities"></a><span data-ttu-id="63182-103">Adóhatóságok beállítása</span><span class="sxs-lookup"><span data-stu-id="63182-103">Set up sales tax authorities</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="63182-104">Az adóhatóságok olyan entitások amelyek felé jelenteni és fizetni kell a begyűjtött áfát.</span><span class="sxs-lookup"><span data-stu-id="63182-104">Sales tax authorities are entities to which collected sales tax needs to be reported and paid.</span></span> <span data-ttu-id="63182-105">Közvetlenül is fizetheti az áfát a hatóságnak, vagy egy, az adóhatóság számára létrehozott szállítóazonosítón keresztül.</span><span class="sxs-lookup"><span data-stu-id="63182-105">You can pay sales taxes to the authority directly or through a vendor account that you create for the sales tax authority.</span></span> <span data-ttu-id="63182-106">Végrehajtása esetén a vállalat a szokásos fizetési gyakorlata szerint, időben fizetheti be az áfát.</span><span class="sxs-lookup"><span data-stu-id="63182-106">If you do this, the company can use its usual payment routines to pay the sales tax authority on time.</span></span> <span data-ttu-id="63182-107">Ha nem állítja be szállítóként az adóhatóságot, valakinek az esedékesség napján manuálisan létre kell hoznia az adóhatóságnak szóló kifizetést.</span><span class="sxs-lookup"><span data-stu-id="63182-107">If you do not set up the tax authority as a vendor, someone must prepare a manual payment to the tax authority on the appropriate due date.</span></span> <span data-ttu-id="63182-108">Ez a feladat az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="63182-108">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="63182-109">Ugrás az Adó > Közvetett adók > Áfa > Adóhatóságok pontra.</span><span class="sxs-lookup"><span data-stu-id="63182-109">Go to Tax > Indirect taxes > Sales tax > Sales tax authorities.</span></span>
2. <span data-ttu-id="63182-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="63182-110">Click New.</span></span>
3. <span data-ttu-id="63182-111">Érték beírása a Hatóság mezőbe.</span><span class="sxs-lookup"><span data-stu-id="63182-111">In the Authority field, type a value.</span></span>
4. <span data-ttu-id="63182-112">Írjon be egy értéket a Név mezőbe.</span><span class="sxs-lookup"><span data-stu-id="63182-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="63182-113">A Szállítói számla mezőben kattintson a legördítő nyílra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="63182-113">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="63182-114">A kívánt rekord megkeresése és kijelölése a listán</span><span class="sxs-lookup"><span data-stu-id="63182-114">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="63182-115">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="63182-115">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="63182-116">Válassza ki az országának/területének megfelelő jelentéselrendezést, ha talál megfelelőt.</span><span class="sxs-lookup"><span data-stu-id="63182-116">Select the report layout for your country/region, if one is available.</span></span> <span data-ttu-id="63182-117">Ha a jelentéselrendezések nem felelnek meg az adóhatóság követelményeinek, akkor használja az alapértelmezett elrendezést.</span><span class="sxs-lookup"><span data-stu-id="63182-117">If the report layouts do not correspond to the requirements of the sales tax authority, use default layout.</span></span>
9. <span data-ttu-id="63182-118">Adjon meg értékeket a Kerekítés űrlapon és a Lekerekítés mezőkben a fizetendő áfa teljes összegének kerekítéséhez.</span><span class="sxs-lookup"><span data-stu-id="63182-118">Enter values in the Rounding form and the Round-off fields to specify how the tax total amount to be paid should be rounded.</span></span> <span data-ttu-id="63182-119">Bármilyen kerekítésből adódó különbség a Számlákhoz kerül feladásra, automatikus tranzakcióként a Főkönyvben.</span><span class="sxs-lookup"><span data-stu-id="63182-119">Any rounding differences will be posted to Accounts for automatic transactions set up in General ledger.</span></span>
10. <span data-ttu-id="63182-120">Adjon meg egy számot a Lekerekítés mezőben.</span><span class="sxs-lookup"><span data-stu-id="63182-120">In the Round-off field, enter a number.</span></span>
11. <span data-ttu-id="63182-121">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="63182-121">Click Save.</span></span>


