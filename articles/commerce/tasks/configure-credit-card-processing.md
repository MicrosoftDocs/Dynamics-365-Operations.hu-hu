---
title: " Hitelkártya-feldolgozás konfigurálása"
description: Ez az eljárás végigveszi a fizetési szolgáltatók listája megtekintésének lépéseit, és leírja, hogyan konfigurálhat egy fizetési számlát a kinnlevőségek részére.
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d365dfce8e8fbd332111d96eeb2a431151d7a342
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234221"
---
# <a name="configure-credit-card-processing"></a><span data-ttu-id="a8243-103"> Hitelkártya-feldolgozás konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a8243-103">Configure credit card processing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8243-104">Ez az eljárás végigveszi a fizetési szolgáltatók listája megtekintésének lépéseit, és leírja, hogyan konfigurálhat egy fizetési számlát a kinnlevőségek részére.</span><span class="sxs-lookup"><span data-stu-id="a8243-104">This procedure walks through how to view the list of payment providers and how to configure a payment account for accounts receivable.</span></span> <span data-ttu-id="a8243-105">Ez az eljárás az USRT cég adatait használja, mint bemutatóadatokat, és rendszergazdák, illetve informatikai szakemberek számára készült.</span><span class="sxs-lookup"><span data-stu-id="a8243-105">This procedure uses the USRT company in demo data and is intended for Administrators and IT Professionals.</span></span>


## <a name="view-a-list-of-payment-providers"></a><span data-ttu-id="a8243-106">A fizetési szolgáltatók listájának megtekintése</span><span class="sxs-lookup"><span data-stu-id="a8243-106">View a list of payment providers</span></span>
1. <span data-ttu-id="a8243-107">Ugorjon a következő oldalra: Kinnlevőségek >; Fizetési beállítások > Fizetési szolgáltatások.</span><span class="sxs-lookup"><span data-stu-id="a8243-107">Go to Accounts receivable > Payments setup > Payment services.</span></span>
2. <span data-ttu-id="a8243-108">Kattintson az Elérhető szolgáltatók megtekintése lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a8243-108">Click View available providers.</span></span>

## <a name="configure-payment-account"></a><span data-ttu-id="a8243-109">Fizetési számla konfigurálása</span><span class="sxs-lookup"><span data-stu-id="a8243-109">Configure payment account</span></span>
1. <span data-ttu-id="a8243-110">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a8243-110">Click New.</span></span>
2. <span data-ttu-id="a8243-111">Írjon be egy értéket a Fizetési szolgáltatás mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a8243-111">In the Payment service field, type a value.</span></span>
3. <span data-ttu-id="a8243-112">Válasszon ki egy lehetőséget a Fizetési csatlakoztató mezőben.</span><span class="sxs-lookup"><span data-stu-id="a8243-112">In the Payment connector field, select an option.</span></span>
4. <span data-ttu-id="a8243-113">Bontsa ki a Fizetési szolgáltatás fiókja részt.</span><span class="sxs-lookup"><span data-stu-id="a8243-113">Toggle the expansion of the Payment service account section.</span></span>
5. <span data-ttu-id="a8243-114">Írja be a Környezet: mezőbe a következőt: „PROD”.</span><span class="sxs-lookup"><span data-stu-id="a8243-114">In the Environment: field, type 'PROD'.</span></span>
6. <span data-ttu-id="a8243-115">Kattintson a Hitelkártyatípusok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a8243-115">Click Credit card types.</span></span>
7. <span data-ttu-id="a8243-116">A Fizetési napló mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="a8243-116">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="a8243-117">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a8243-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="a8243-118">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="a8243-118">Click Add.</span></span>
10. <span data-ttu-id="a8243-119">Érték beírása a Pénznem mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a8243-119">In the Currency field, type a value.</span></span>
11. <span data-ttu-id="a8243-120">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="a8243-120">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="a8243-121">A Fizetési napló mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="a8243-121">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="a8243-122">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a8243-122">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="a8243-123">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="a8243-123">Click Add.</span></span>
15. <span data-ttu-id="a8243-124">Érték beírása a Pénznem mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a8243-124">In the Currency field, type a value.</span></span>
16. <span data-ttu-id="a8243-125">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="a8243-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a8243-126">Ismételje meg ezeket a lépéseket annyi kártyatípus esetén, amennyire szüksége van.</span><span class="sxs-lookup"><span data-stu-id="a8243-126">You can repeat these steps for as many card types as you need.</span></span>  
17. <span data-ttu-id="a8243-127">A Fizetési napló mezőben kattintson a legördülő gombra a keresőlista megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="a8243-127">In the Payment journal field, click the drop-down button to open the lookup.</span></span>
18. <span data-ttu-id="a8243-128">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="a8243-128">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="a8243-129">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="a8243-129">Click Add.</span></span>
20. <span data-ttu-id="a8243-130">Érték beírása a Pénznem mezőbe.</span><span class="sxs-lookup"><span data-stu-id="a8243-130">In the Currency field, type a value.</span></span>
21. <span data-ttu-id="a8243-131">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a8243-131">Click Save.</span></span>
22. <span data-ttu-id="a8243-132">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a8243-132">Close the page.</span></span>
23. <span data-ttu-id="a8243-133">Kattintson az Érvényesítés gombra.</span><span class="sxs-lookup"><span data-stu-id="a8243-133">Click Validate.</span></span>
24. <span data-ttu-id="a8243-134">Jelölje be az Új hitelkártyák alapértelmezett feldolgozója jelölőnégyezetet.</span><span class="sxs-lookup"><span data-stu-id="a8243-134">Click the Default processor for new credit cards checkbox.</span></span>
25. <span data-ttu-id="a8243-135">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="a8243-135">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]