---
title: "Számlajóváhagyások mobil munkaterület"
description: "Ez a témakör a Számlajóváhagyások mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást. A munkaterület a szállítói számla fejléce munkafolyamattal Önhöz rendelt számlák listáját tartalmazza."
author: abruer
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 24818afbbdf328c8fd3eea691634db24e443b07b
ms.contentlocale: hu-hu
ms.lasthandoff: 07/18/2017

---

# <a name="invoice-approvals-mobile-workspace"></a><span data-ttu-id="cf752-104">Számlajóváhagyások mobil munkaterület</span><span class="sxs-lookup"><span data-stu-id="cf752-104">Invoice approvals mobile workspace</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="cf752-105">Ez a témakör a **Számlajóváhagyások** mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="cf752-105">This topic provides information about the **Invoice approvals** mobile workspace.</span></span> <span data-ttu-id="cf752-106">A munkaterület a szállítói számla fejléce munkafolyamattal Önhöz rendelt számlák listáját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="cf752-106">This workspace provides a list of invoices that have been assigned to you through the vendor invoice header workflow process.</span></span> 

<span data-ttu-id="cf752-107">A mobil munkaterületet a Microsoft Dynamics 365 for Unified Operations mobilalkalmazásban való használatra tervezték.</span><span class="sxs-lookup"><span data-stu-id="cf752-107">This mobile workspace is intended to be used with the Microsoft Dynamics 365 for Unified Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="cf752-108">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="cf752-108">Overview</span></span>

<span data-ttu-id="cf752-109">A **Számlajóváhagyások** mobil munkaterület lehetővé teszi, hogy a kötelezettségekkel foglalkozó ügyintézők és vezetők megtekintsék a szállítói számla fejléce munkafolyamat részeként hozzájuk rendelt számlákat.</span><span class="sxs-lookup"><span data-stu-id="cf752-109">The **Invoice approvals** mobile workspace lets Accounts payable clerks and managers view invoices that have been assigned to them as part of the vendor invoice header workflow process.</span></span> <span data-ttu-id="cf752-110">A jól informált jóváhagyási döntések meghozatala érdekében megtekintheti a számlaadatokat, és akár a sor és a terjesztési részleteket is.</span><span class="sxs-lookup"><span data-stu-id="cf752-110">You can view the invoice information, and even the line and distribution details, to help you make informed approval decisions.</span></span> <span data-ttu-id="cf752-111">A munkaterületről végrehajtott paranccsal végigviheti a számlát a munkafolyamaton.</span><span class="sxs-lookup"><span data-stu-id="cf752-111">From the workspace, you can take action to move the invoice through the workflow process.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="cf752-112">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="cf752-112">Prerequisites</span></span>

<span data-ttu-id="cf752-113">A mobil munkaterület csak a következő előfeltételek teljesülése esetén használható.</span><span class="sxs-lookup"><span data-stu-id="cf752-113">Before you can use this mobile workspace, the following prerequisites must be met.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="cf752-114">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="cf752-114">Prerequisite</span></span></th>
<th><span data-ttu-id="cf752-115">Szerep</span><span class="sxs-lookup"><span data-stu-id="cf752-115">Role</span></span></th>
<th><span data-ttu-id="cf752-116">Leírás</span><span class="sxs-lookup"><span data-stu-id="cf752-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cf752-117">A Microsoft Dynamics 365 for Finance and Operations, Enterprise kiadás 2017 júliusi frissítését telepíteni kell a szervezetben.</span><span class="sxs-lookup"><span data-stu-id="cf752-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition July 2017 update must be deployed in your organization.</span></span></td>
<td><span data-ttu-id="cf752-118">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="cf752-118">System administrator</span></span></td>
<td><span data-ttu-id="cf752-119">Lásd: <a href="../deployment/deploy-demo-environment.md">Bemutatókörnyezet telepítése</a>.</span><span class="sxs-lookup"><span data-stu-id="cf752-119">See <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="cf752-120">A <strong>Számlajóváhagyások</strong> munkaterületet közzé kell tenni.</span><span class="sxs-lookup"><span data-stu-id="cf752-120">The <strong>Invoice approvals</strong> mobile workspace must be published.</span></span></td>
<td><span data-ttu-id="cf752-121">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="cf752-121">System administrator</span></span></td>
<td><span data-ttu-id="cf752-122">Lásd: <a href="/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace">Mobil munkaterület közzététele</a>.</span><span class="sxs-lookup"><span data-stu-id="cf752-122">See <a href="/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="cf752-123">A mobilalkalmazás letöltése és telepítése</span><span class="sxs-lookup"><span data-stu-id="cf752-123">Download and install the mobile app</span></span>

<span data-ttu-id="cf752-124">Töltse le és telepítse a Dynamics 365 for Unified Operations mobilalkalmazást:</span><span class="sxs-lookup"><span data-stu-id="cf752-124">Download and install the Dynamics 365 for Unified Operations mobile app:</span></span>

-   [<span data-ttu-id="cf752-125">Android-telefonok esetében:</span><span class="sxs-lookup"><span data-stu-id="cf752-125">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="cf752-126">iPhone esetében:</span><span class="sxs-lookup"><span data-stu-id="cf752-126">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="cf752-127">Bejelentkezés a mobilalkalmazásba</span><span class="sxs-lookup"><span data-stu-id="cf752-127">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="cf752-128">Indítsa el az alkalmazást a mobileszközén.</span><span class="sxs-lookup"><span data-stu-id="cf752-128">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="cf752-129">Írja be a Microsoft Dynamics 365 URL-jét.</span><span class="sxs-lookup"><span data-stu-id="cf752-129">Enter your Microsoft Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="cf752-130">Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót.</span><span class="sxs-lookup"><span data-stu-id="cf752-130">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="cf752-131">Adja meg a hitelesítési adatait.</span><span class="sxs-lookup"><span data-stu-id="cf752-131">Enter your credentials.</span></span>
4.  <span data-ttu-id="cf752-132">A bejelentkezést követően megjelennek a vállalata rendelkezésre álló munkaterületek.</span><span class="sxs-lookup"><span data-stu-id="cf752-132">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="cf752-133">Vegye figyelembe, hogy ha a rendszergazda később teszi közzé az új munkaterületet, akkor Önnek frissítenie kell a mobil munkaterületek listáját.</span><span class="sxs-lookup"><span data-stu-id="cf752-133">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

    <span data-ttu-id="cf752-134">[![Lekérés frissítéshez](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="cf752-134">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a><span data-ttu-id="cf752-135">Számlák jóváhagyása a Számlajóváhagyások mobil munkaterület használatával</span><span class="sxs-lookup"><span data-stu-id="cf752-135">Approve invoices by using the Invoice approvals mobile workspace</span></span>
1.  <span data-ttu-id="cf752-136">A mobileszközön válassza a **Számlajóváhagyások** munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="cf752-136">On your mobile device, select the **Invoice approvals** workspace.</span></span>
2.  <span data-ttu-id="cf752-137">Válassza ki a számlát, amelyet a szállítói számla fejléce munkafolyamat által Önhöz hozzárendelték.</span><span class="sxs-lookup"><span data-stu-id="cf752-137">Select the invoice that has been assigned to you by the vendor invoice header workflow process.</span></span>
3.  <span data-ttu-id="cf752-138">A **Számlaadatok** oldalon tekintse át a számla fejlécadatait, többek között a dátum és a szállító adatait.</span><span class="sxs-lookup"><span data-stu-id="cf752-138">On the **Invoice details** page, review the invoice header information, such as the vendor and date information.</span></span>
4.  <span data-ttu-id="cf752-139">Válasszon ki egy sort a számlán a részletes információk megtekintéséhez a **Számlasor részletei** nézetben.</span><span class="sxs-lookup"><span data-stu-id="cf752-139">Select a line on the invoice to view more detailed information about it in the **Invoice line details** view.</span></span>
5.  <span data-ttu-id="cf752-140">A **Számlasor részletei** nézetben válassza a **Felosztások** lehetőséget a sorfelosztások megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="cf752-140">In the **Invoice line details** view, select **Distributions** to show the line distributions.</span></span> <span data-ttu-id="cf752-141">Itt megtekintheti a számlatétel könyvelési adatait.</span><span class="sxs-lookup"><span data-stu-id="cf752-141">Here, you can view the accounting for the invoice line.</span></span> <span data-ttu-id="cf752-142">A megjelenített információ tartalmazza a pénzügyi dimenziókat és a fő számlát.</span><span class="sxs-lookup"><span data-stu-id="cf752-142">The information that is shown includes the financial dimensions and the main account.</span></span>
6.  <span data-ttu-id="cf752-143">A **Számla részletei** oldalon válassza a **Felosztások** lehetőséget az összes felosztás megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="cf752-143">On the **Invoice details** page, select **Distributions** to show all distributions.</span></span> <span data-ttu-id="cf752-144">Itt megtekintheti a teljes számla könyvelési adatait.</span><span class="sxs-lookup"><span data-stu-id="cf752-144">Here, you can view the accounting for the whole invoice.</span></span> <span data-ttu-id="cf752-145">A megjelenített információ tartalmazza a pénzügyi dimenziókat és a fő számlákat.</span><span class="sxs-lookup"><span data-stu-id="cf752-145">The information that is shown includes the financial dimensions and the main accounts.</span></span> 
7.  <span data-ttu-id="cf752-146">Válassza ki a **Mellékletek** lehetőséget a számlához csatolt bármely megjegyzés vagy fájl megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="cf752-146">Select **Attachments** to view any notes or files that are attached to the invoice.</span></span>
8.  <span data-ttu-id="cf752-147">A **Számla részletei** lapon válassza ki a megfelelő munkafolyamat-műveletet az ellenőrzési folyamat befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="cf752-147">On the **Invoice details** page, select the appropriate workflow action to complete your review process.</span></span>
9.  <span data-ttu-id="cf752-148">Válassza a **Kész** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="cf752-148">Select **Done**.</span></span>

