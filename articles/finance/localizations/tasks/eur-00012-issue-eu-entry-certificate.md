---
title: EUR-00012 Európai beérkezési igazolás kibocsátása
description: Ez az eljárás bemutatja az EU beérkezési igazolás engedélyezésén és a vevői számla beállításán a beérkezési igazolások használata és az igazolás kiállítása érdekében.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, CustTable, SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CustEntryCertificateJour_W, SrsReportViewerForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 735331fd399ba9501031084e236b88c0e11bb179
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183681"
---
# <a name="eur-00012-issue-an-eu-entry-certificate"></a><span data-ttu-id="09ca3-103">EUR-00012 Európai beérkezési igazolás kibocsátása</span><span class="sxs-lookup"><span data-stu-id="09ca3-103">EUR-00012 Issue an EU entry certificate</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="09ca3-104">Ez az eljárás bemutatja az EU beérkezési igazolás engedélyezésén és a vevői számla beállításán a beérkezési igazolások használata és az igazolás kiállítása érdekében.</span><span class="sxs-lookup"><span data-stu-id="09ca3-104">This procedure walks you through enabling an EU entry certificate, configuring a customer account to use entry certificates and issue a certificate.</span></span> <span data-ttu-id="09ca3-105">Ez az eljárás a DEMF bemutatócég segítségével lett létrehozva.</span><span class="sxs-lookup"><span data-stu-id="09ca3-105">This procedure was created using the demo data company DEMF.</span></span>


## <a name="enable-entry-certificate-management"></a><span data-ttu-id="09ca3-106">Beérkezési igazolások kezelésének engedélyezése</span><span class="sxs-lookup"><span data-stu-id="09ca3-106">Enable entry certificate management</span></span>
1. <span data-ttu-id="09ca3-107">Ugorjon a Kintlévőségek > Beállítás > Kinnlevőségek paraméterei pontra.</span><span class="sxs-lookup"><span data-stu-id="09ca3-107">Go to Accounts receivable > Setup > Accounts receivable parameters.</span></span>
2. <span data-ttu-id="09ca3-108">Kattintson a Szállítások fülre.</span><span class="sxs-lookup"><span data-stu-id="09ca3-108">Click the Shipments tab.</span></span>
3. <span data-ttu-id="09ca3-109">Bontsa ki a Beérkezési igazolás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="09ca3-109">Expand the Entry certificate section.</span></span>
4. <span data-ttu-id="09ca3-110">Jelölje be az Igent a Beérkezési igazolások kezelésének engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="09ca3-110">Select Yes in the Enable entry certificate management field.</span></span>
5. <span data-ttu-id="09ca3-111">Jelölje be az Igent a Beérkezési igazolások kiadásának engedélyezése mezőben.</span><span class="sxs-lookup"><span data-stu-id="09ca3-111">Select Yes in the Enable entry certificate issuing field.</span></span>
6. <span data-ttu-id="09ca3-112">Kattintson a Számsorozatok lapra.</span><span class="sxs-lookup"><span data-stu-id="09ca3-112">Click the Number sequences tab.</span></span>
7. <span data-ttu-id="09ca3-113">A listában keresse meg és jelölje be a Beérkezési igazolás sort.</span><span class="sxs-lookup"><span data-stu-id="09ca3-113">In the list, find and select Entry certificate row.</span></span>
8. <span data-ttu-id="09ca3-114">A Számsorrend kódja mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="09ca3-114">In the Number sequence code field, enter or select a value.</span></span>

## <a name="set-up-a-customer"></a><span data-ttu-id="09ca3-115">Ügyfél beállítása</span><span class="sxs-lookup"><span data-stu-id="09ca3-115">Set up a customer</span></span>
1. <span data-ttu-id="09ca3-116">Ugorjon a Kinnlevőségek > Vevők > Minden vevő pontra.</span><span class="sxs-lookup"><span data-stu-id="09ca3-116">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="09ca3-117">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="09ca3-117">Use the Quick Filter to find records.</span></span> <span data-ttu-id="09ca3-118">Például szűkítsen a „Számla” mezővel a „DE-015” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="09ca3-118">For example, filter on the Account field with a value of 'DE-015'.</span></span>
3. <span data-ttu-id="09ca3-119">Nyissa meg a Vevői számla részletes adatait.</span><span class="sxs-lookup"><span data-stu-id="09ca3-119">Open customer account details.</span></span>
4. <span data-ttu-id="09ca3-120">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="09ca3-120">Click Edit.</span></span>
5. <span data-ttu-id="09ca3-121">Nyissa meg A számlázás és szállítás szakaszt.</span><span class="sxs-lookup"><span data-stu-id="09ca3-121">Expand the Invoice and delivery section.</span></span>
6. <span data-ttu-id="09ca3-122">Jelölje be az Igent a Beérkezési igazolás szükséges hozzá mezőben.</span><span class="sxs-lookup"><span data-stu-id="09ca3-122">Select Yes in the Entry certificate required field.</span></span>
7. <span data-ttu-id="09ca3-123">Jelölje be az Igent a Beérkezési igazolás kiadása mezőben.</span><span class="sxs-lookup"><span data-stu-id="09ca3-123">Select Yes in the Issue entry certificate field.</span></span>
8. <span data-ttu-id="09ca3-124">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="09ca3-124">Click Save.</span></span>

## <a name="create-an-eu-entry-certificate-automatically"></a><span data-ttu-id="09ca3-125">EU-s beérkezési igazolás automatikus létrehozása</span><span class="sxs-lookup"><span data-stu-id="09ca3-125">Create an EU entry certificate automatically</span></span>
1. <span data-ttu-id="09ca3-126">Ugorjon a Kinnlevőségek > Rendelések > Minden értékesítési rendelés elemre.</span><span class="sxs-lookup"><span data-stu-id="09ca3-126">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="09ca3-127">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="09ca3-127">Click New.</span></span>
3. <span data-ttu-id="09ca3-128">A Vevőszámla mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="09ca3-128">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="09ca3-129">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="09ca3-129">Click OK.</span></span>
5. <span data-ttu-id="09ca3-130">Az Elemszám mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="09ca3-130">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="09ca3-131">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="09ca3-131">Click Save.</span></span>
7. <span data-ttu-id="09ca3-132">A Művelet panelen kattintson a Kitárolás és csomagolás elemre.</span><span class="sxs-lookup"><span data-stu-id="09ca3-132">On the Action Pane, click Pick and pack.</span></span>
8. <span data-ttu-id="09ca3-133">Kattintson A szállítólevél feladása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="09ca3-133">Click Post packing slip.</span></span>
9. <span data-ttu-id="09ca3-134">Bontsa ki a Paraméterek szakaszt.</span><span class="sxs-lookup"><span data-stu-id="09ca3-134">Expand the Parameters section.</span></span>
10. <span data-ttu-id="09ca3-135">A Mennyiség mezőben válassza a „Mind” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="09ca3-135">In the Quantity field, select 'All'.</span></span>
11. <span data-ttu-id="09ca3-136">Törölje a jelet a jelölőnégyzetből a Beérkezési igazolások kiállítása mellett.</span><span class="sxs-lookup"><span data-stu-id="09ca3-136">Clear the Issue entry certificate check box.</span></span>
    * <span data-ttu-id="09ca3-137">A beérkezési igazolást a szállítólevél feladásakor, vagy a rendelés számlázása során állíthatja ki.</span><span class="sxs-lookup"><span data-stu-id="09ca3-137">An entry certificate can be issued during packing slip posting or during order invoicing.</span></span> <span data-ttu-id="09ca3-138">Hagyja üresen a Beérkezési igazolás kiállítása jelölőnégyzetet, ha később szeretné azt kiállítani.</span><span class="sxs-lookup"><span data-stu-id="09ca3-138">Leave the Issue entry certificate checkbox unchecked to issue it later.</span></span>  
12. <span data-ttu-id="09ca3-139">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="09ca3-139">Click OK.</span></span>
13. <span data-ttu-id="09ca3-140">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="09ca3-140">Click OK.</span></span>
14. <span data-ttu-id="09ca3-141">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="09ca3-141">On the Action Pane, click Invoice.</span></span>
15. <span data-ttu-id="09ca3-142">Kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="09ca3-142">Click Invoice.</span></span>
    * <span data-ttu-id="09ca3-143">Győződjön meg róla, hogy a Beérkezési igazolás szükséges, és a Bejegyzési tanúsítvány kiadása, illetve az Áttekintés jelölőnégyzetek be vannak jelölve.</span><span class="sxs-lookup"><span data-stu-id="09ca3-143">Verify that the Entry certificate required and Issue entry certificate checkboxes in the Overview section are marked.</span></span>  <span data-ttu-id="09ca3-144">Kiválaszthatja a Beérkezési igazolás nyomtatása jelölőnégyzetet is az igazolás kinyomtatásához.</span><span class="sxs-lookup"><span data-stu-id="09ca3-144">You can also select the Print entry certificate check box to allow printing of the certificate.</span></span>  
16. <span data-ttu-id="09ca3-145">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="09ca3-145">Click OK.</span></span>
17. <span data-ttu-id="09ca3-146">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="09ca3-146">Click OK.</span></span>
18. <span data-ttu-id="09ca3-147">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="09ca3-147">On the Action Pane, click Invoice.</span></span>
19. <span data-ttu-id="09ca3-148">Kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="09ca3-148">Click Invoice.</span></span>
20. <span data-ttu-id="09ca3-149">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="09ca3-149">On the Action Pane, click Invoice.</span></span>
21. <span data-ttu-id="09ca3-150">Kattintson a Kiállított beérkezési igazolások megtekintése elemre.</span><span class="sxs-lookup"><span data-stu-id="09ca3-150">Click View issued entry certificates.</span></span>
22. <span data-ttu-id="09ca3-151">Kattintson a Nyomtatás parancsra.</span><span class="sxs-lookup"><span data-stu-id="09ca3-151">Click Print.</span></span>
23. <span data-ttu-id="09ca3-152">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="09ca3-152">Close the page.</span></span>
24. <span data-ttu-id="09ca3-153">Kattintson az Állapot módosítása elemre.</span><span class="sxs-lookup"><span data-stu-id="09ca3-153">Click Change status.</span></span>
25. <span data-ttu-id="09ca3-154">Az Új állapot mezőben válasszon ki egy opciót.</span><span class="sxs-lookup"><span data-stu-id="09ca3-154">In the New status field, select an option.</span></span>
26. <span data-ttu-id="09ca3-155">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="09ca3-155">Click OK.</span></span>
27. <span data-ttu-id="09ca3-156">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="09ca3-156">Close the page.</span></span>

## <a name="create-an-eu-entry-certificate-manually"></a><span data-ttu-id="09ca3-157">EU-s beérkezési igazolás manuális létrehozása</span><span class="sxs-lookup"><span data-stu-id="09ca3-157">Create an EU entry certificate manually</span></span>
1. <span data-ttu-id="09ca3-158">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="09ca3-158">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="09ca3-159">Kattintson a Beérkezési igazolás létrehozása elemre.</span><span class="sxs-lookup"><span data-stu-id="09ca3-159">Click Create entry certificate.</span></span>
3. <span data-ttu-id="09ca3-160">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="09ca3-160">Click OK.</span></span>
4. <span data-ttu-id="09ca3-161">A Művelet panelen kattintson a Számla lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="09ca3-161">On the Action Pane, click Invoice.</span></span>
5. <span data-ttu-id="09ca3-162">Kattintson a Kiállított beérkezési igazolások megtekintése elemre.</span><span class="sxs-lookup"><span data-stu-id="09ca3-162">Click View issued entry certificates.</span></span>

