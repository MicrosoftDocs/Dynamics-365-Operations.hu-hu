--- 
title: " Hitelkártya-feldolgozás konfigurálása"
description: "Ez az eljárás végigveszi a fizetési szolgáltatók listája megtekintésének lépéseit, és leírja, hogyan konfigurálhat egy fizetési számlát a kinnlevőségek részére."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 3b54cfdb22c0c9daa9564ae36ad2bb89edb81f11
ms.contentlocale: hu-hu
ms.lasthandoff: 01/19/2018

---
# <a name="configure-credit-card-processing"></a><span data-ttu-id="501d1-103"> Hitelkártya-feldolgozás konfigurálása</span><span class="sxs-lookup"><span data-stu-id="501d1-103">Configure credit card processing</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="501d1-104">Ez az eljárás végigveszi a fizetési szolgáltatók listája megtekintésének lépéseit, és leírja, hogyan konfigurálhat egy fizetési számlát a kinnlevőségek részére.</span><span class="sxs-lookup"><span data-stu-id="501d1-104">This procedure walks through how to view the list of payment providers and how to configure a payment account for accounts receivable.</span></span> <span data-ttu-id="501d1-105">Ez az eljárás az USRT cég adatait használja, mint bemutatóadatokat, és rendszergazdák, illetve informatikai szakemberek számára készült.</span><span class="sxs-lookup"><span data-stu-id="501d1-105">This procedure uses the USRT company in demo data and is intended for Administrators and IT Professionals.</span></span>


## <a name="view-a-list-of-payment-providers"></a><span data-ttu-id="501d1-106">A fizetési szolgáltatók listájának megtekintése</span><span class="sxs-lookup"><span data-stu-id="501d1-106">View a list of payment providers</span></span>
1. <span data-ttu-id="501d1-107">Ugorjon a következő oldalra: Kinnlevőségek >; Fizetési beállítások > Fizetési szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="501d1-107">Go to Accounts receivable > Payments setup > Payment services.</span></span>
2. <span data-ttu-id="501d1-108">Kattintson az Elérhető szolgáltatók megtekintése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="501d1-108">Click View available providers.</span></span>

## <a name="configure-payment-account"></a><span data-ttu-id="501d1-109">Fizetési számla konfigurálása</span><span class="sxs-lookup"><span data-stu-id="501d1-109">Configure payment account</span></span>
1. <span data-ttu-id="501d1-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="501d1-110">Click New.</span></span>
2. <span data-ttu-id="501d1-111">Írjon be egy értéket a Fizetési szolgáltatás mezőbe.</span><span class="sxs-lookup"><span data-stu-id="501d1-111">In the Payment service field, type a value.</span></span>
3. <span data-ttu-id="501d1-112">Válasszon ki egy lehetőséget a Fizetési csatlakoztató mezőben.</span><span class="sxs-lookup"><span data-stu-id="501d1-112">In the Payment connector field, select an option.</span></span>
4. <span data-ttu-id="501d1-113">Bontsa ki a Fizetési szolgáltatás fiókja részt.</span><span class="sxs-lookup"><span data-stu-id="501d1-113">Toggle the expansion of the Payment service account section.</span></span>
5. <span data-ttu-id="501d1-114">Írja be a Környezet: mezőbe a következőt: „PROD”.</span><span class="sxs-lookup"><span data-stu-id="501d1-114">In the Environment: field, type 'PROD'.</span></span>
6. <span data-ttu-id="501d1-115">Kattintson a Hitelkártyatípusok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="501d1-115">Click Credit card types.</span></span>
7. <span data-ttu-id="501d1-116">A Fizetési napló mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="501d1-116">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="501d1-117">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="501d1-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="501d1-118">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="501d1-118">Click Add.</span></span>
10. <span data-ttu-id="501d1-119">Érték beírása a Pénznem mezőbe.</span><span class="sxs-lookup"><span data-stu-id="501d1-119">In the Currency field, type a value.</span></span>
11. <span data-ttu-id="501d1-120">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="501d1-120">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="501d1-121">A Fizetési napló mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="501d1-121">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="501d1-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="501d1-122">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="501d1-123">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="501d1-123">Click Add.</span></span>
15. <span data-ttu-id="501d1-124">Érték beírása a Pénznem mezőbe.</span><span class="sxs-lookup"><span data-stu-id="501d1-124">In the Currency field, type a value.</span></span>
16. <span data-ttu-id="501d1-125">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="501d1-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="501d1-126">Ismételje meg ezeket a lépéseket annyi kártyatípus esetén, amennyire szüksége van.</span><span class="sxs-lookup"><span data-stu-id="501d1-126">You can repeat these steps for as many card types as you need.</span></span>  
17. <span data-ttu-id="501d1-127">A Fizetési napló mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="501d1-127">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="501d1-128">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="501d1-128">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="501d1-129">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="501d1-129">Click Add.</span></span>
20. <span data-ttu-id="501d1-130">Érték beírása a Pénznem mezőbe.</span><span class="sxs-lookup"><span data-stu-id="501d1-130">In the Currency field, type a value.</span></span>
21. <span data-ttu-id="501d1-131">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="501d1-131">Click Save.</span></span>
22. <span data-ttu-id="501d1-132">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="501d1-132">Close the page.</span></span>
23. <span data-ttu-id="501d1-133">Kattintson az Érvényesítés gombra.</span><span class="sxs-lookup"><span data-stu-id="501d1-133">Click Validate.</span></span>
24. <span data-ttu-id="501d1-134">Jelölje be az Új hitelkártyák alapértelmezett feldolgozója jelölőnégyezetet.</span><span class="sxs-lookup"><span data-stu-id="501d1-134">Click the Default processor for new credit cards checkbox.</span></span>
25. <span data-ttu-id="501d1-135">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="501d1-135">Click Save.</span></span>


