---
title: Számlajóváhagyások mobil munkaterület
description: Ez a témakör a Számlajóváhagyások mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást.
author: abruer
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 3d90b89900b35bce648841aa9e49737a25309ce2
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570073"
---
# <a name="invoice-approvals-mobile-workspace"></a><span data-ttu-id="640ed-103">Számlajóváhagyások mobil munkaterület</span><span class="sxs-lookup"><span data-stu-id="640ed-103">Invoice approvals mobile workspace</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="640ed-104">Ez a témakör a **Számlajóváhagyások** mobil munkaterülettel kapcsolatban tartalmaz tájékoztatást.</span><span class="sxs-lookup"><span data-stu-id="640ed-104">This topic provides information about the **Invoice approvals** mobile workspace.</span></span> <span data-ttu-id="640ed-105">A munkaterület a szállítói számla fejléce munkafolyamattal Önhöz rendelt számlák listáját tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="640ed-105">This workspace provides a list of invoices that have been assigned to you through the vendor invoice header workflow process.</span></span> 

<span data-ttu-id="640ed-106">A mobil munkaterületet a Finance and Operations mobilalkalmazásban való használatra tervezték.</span><span class="sxs-lookup"><span data-stu-id="640ed-106">This mobile workspace is intended to be used with the Finance and Operations mobile app.</span></span>

## <a name="overview"></a><span data-ttu-id="640ed-107">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="640ed-107">Overview</span></span>

<span data-ttu-id="640ed-108">A **Számlajóváhagyások** mobil munkaterület lehetővé teszi, hogy a kötelezettségekkel foglalkozó ügyintézők és vezetők megtekintsék a szállítói számla fejléce munkafolyamat részeként hozzájuk rendelt számlákat.</span><span class="sxs-lookup"><span data-stu-id="640ed-108">The **Invoice approvals** mobile workspace lets Accounts payable clerks and managers view invoices that have been assigned to them as part of the vendor invoice header workflow process.</span></span> <span data-ttu-id="640ed-109">A jól informált jóváhagyási döntések meghozatala érdekében megtekintheti a számlaadatokat, és akár a sor és a terjesztési részleteket is.</span><span class="sxs-lookup"><span data-stu-id="640ed-109">You can view the invoice information, and even the line and distribution details, to help you make informed approval decisions.</span></span> <span data-ttu-id="640ed-110">A munkaterületről végrehajtott paranccsal végigviheti a számlát a munkafolyamaton.</span><span class="sxs-lookup"><span data-stu-id="640ed-110">From the workspace, you can take action to move the invoice through the workflow process.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="640ed-111">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="640ed-111">Prerequisites</span></span>

<span data-ttu-id="640ed-112">A mobil munkaterület csak a következő előfeltételek teljesülése esetén használható.</span><span class="sxs-lookup"><span data-stu-id="640ed-112">Before you can use this mobile workspace, the following prerequisites must be met.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="640ed-113">Előfeltételek</span><span class="sxs-lookup"><span data-stu-id="640ed-113">Prerequisite</span></span></th>
<th><span data-ttu-id="640ed-114">Szerep</span><span class="sxs-lookup"><span data-stu-id="640ed-114">Role</span></span></th>
<th><span data-ttu-id="640ed-115">Leírás</span><span class="sxs-lookup"><span data-stu-id="640ed-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="640ed-116">A Microsoft Dynamics 365 Finance szolgáltatást telepíteni kell a szervezetében.</span><span class="sxs-lookup"><span data-stu-id="640ed-116">Microsoft Dynamics 365 Finance must be deployed in your organization.</span></span></td>
<td><span data-ttu-id="640ed-117">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="640ed-117">System administrator</span></span></td>
<td><span data-ttu-id="640ed-118">Lásd: <a href="../deployment/deploy-demo-environment.md">Bemutatókörnyezet telepítése</a>.</span><span class="sxs-lookup"><span data-stu-id="640ed-118">See <a href="../deployment/deploy-demo-environment.md">Deploy a demo environment</a>.</span></span>
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="640ed-119">A <strong>Számlajóváhagyások</strong> munkaterületet közzé kell tenni.</span><span class="sxs-lookup"><span data-stu-id="640ed-119">The <strong>Invoice approvals</strong> mobile workspace must be published.</span></span></td>
<td><span data-ttu-id="640ed-120">Rendszergazda</span><span class="sxs-lookup"><span data-stu-id="640ed-120">System administrator</span></span></td>
<td><span data-ttu-id="640ed-121">Lásd: <a href="publish-mobile-workspace.md">Mobil munkaterület közzététele</a>.</span><span class="sxs-lookup"><span data-stu-id="640ed-121">See <a href="publish-mobile-workspace.md">Publish a mobile workspace</a>.</span></span></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a><span data-ttu-id="640ed-122">A mobilalkalmazás letöltése és telepítése</span><span class="sxs-lookup"><span data-stu-id="640ed-122">Download and install the mobile app</span></span>

<span data-ttu-id="640ed-123">A Finance and Operations mobilalkalmazás letöltése és telepítése:</span><span class="sxs-lookup"><span data-stu-id="640ed-123">Download and install the Finance and Operations mobile app:</span></span>

-   [<span data-ttu-id="640ed-124">Android telefonok esetében:</span><span class="sxs-lookup"><span data-stu-id="640ed-124">For Android phones</span></span>](https://go.microsoft.com/fwlink/?linkid=850662)
-   [<span data-ttu-id="640ed-125">iPhone esetében:</span><span class="sxs-lookup"><span data-stu-id="640ed-125">For iPhones</span></span>](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a><span data-ttu-id="640ed-126">Bejelentkezés a mobilalkalmazásba</span><span class="sxs-lookup"><span data-stu-id="640ed-126">Sign in to the mobile app</span></span>

1.  <span data-ttu-id="640ed-127">Indítsa el az alkalmazást a mobileszközén.</span><span class="sxs-lookup"><span data-stu-id="640ed-127">Start the app on your mobile device.</span></span>
2.  <span data-ttu-id="640ed-128">Adja meg a Microsoft Dynamics 365 URL-címét.</span><span class="sxs-lookup"><span data-stu-id="640ed-128">Enter your Microsoft Dynamics 365 URL.</span></span>
3.  <span data-ttu-id="640ed-129">Az első bejelentkezéskor a rendszer kéri a felhasználónevet és jelszót.</span><span class="sxs-lookup"><span data-stu-id="640ed-129">The first time that you sign in, you're prompted for your user name and password.</span></span> <span data-ttu-id="640ed-130">Adja meg a hitelesítési adatait.</span><span class="sxs-lookup"><span data-stu-id="640ed-130">Enter your credentials.</span></span>
4.  <span data-ttu-id="640ed-131">A bejelentkezést követően megjelennek a vállalata rendelkezésre álló munkaterületek.</span><span class="sxs-lookup"><span data-stu-id="640ed-131">After you sign in, the available workspaces for your company are shown.</span></span> <span data-ttu-id="640ed-132">Vegye figyelembe, hogy ha a rendszergazda később teszi közzé az új munkaterületet, akkor Önnek frissítenie kell a mobil munkaterületek listáját.</span><span class="sxs-lookup"><span data-stu-id="640ed-132">Note that if your system administrator publishes a new workspace later, you will have to refresh the list of mobile workspaces.</span></span>

    <span data-ttu-id="640ed-133">[![Lekérés frissítéshez](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span><span class="sxs-lookup"><span data-stu-id="640ed-133">[![Pull to refresh](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)</span></span>

## <a name="approve-invoices-by-using-the-invoice-approvals-mobile-workspace"></a><span data-ttu-id="640ed-134">Számlák jóváhagyása a Számlajóváhagyások mobil munkaterület használatával</span><span class="sxs-lookup"><span data-stu-id="640ed-134">Approve invoices by using the Invoice approvals mobile workspace</span></span>
1.  <span data-ttu-id="640ed-135">A mobileszközön válassza a **Számlajóváhagyások** munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="640ed-135">On your mobile device, select the **Invoice approvals** workspace.</span></span>
2.  <span data-ttu-id="640ed-136">Válassza ki a számlát, amelyet a szállítói számla fejléce munkafolyamat által Önhöz hozzárendelték.</span><span class="sxs-lookup"><span data-stu-id="640ed-136">Select the invoice that has been assigned to you by the vendor invoice header workflow process.</span></span>
3.  <span data-ttu-id="640ed-137">A **Számlaadatok** oldalon tekintse át a számla fejlécadatait, többek között a dátum és a szállító adatait.</span><span class="sxs-lookup"><span data-stu-id="640ed-137">On the **Invoice details** page, review the invoice header information, such as the vendor and date information.</span></span>
4.  <span data-ttu-id="640ed-138">Válasszon ki egy sort a számlán a részletes információk megtekintéséhez a **Számlasor részletei** nézetben.</span><span class="sxs-lookup"><span data-stu-id="640ed-138">Select a line on the invoice to view more detailed information about it in the **Invoice line details** view.</span></span>
5.  <span data-ttu-id="640ed-139">A **Számlasor részletei** nézetben válassza a **Felosztások** lehetőséget a sorfelosztások megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="640ed-139">In the **Invoice line details** view, select **Distributions** to show the line distributions.</span></span> <span data-ttu-id="640ed-140">Itt megtekintheti a számlatétel könyvelési adatait.</span><span class="sxs-lookup"><span data-stu-id="640ed-140">Here, you can view the accounting for the invoice line.</span></span> <span data-ttu-id="640ed-141">A megjelenített információ tartalmazza a pénzügyi dimenziókat és a fő számlát.</span><span class="sxs-lookup"><span data-stu-id="640ed-141">The information that is shown includes the financial dimensions and the main account.</span></span>
6.  <span data-ttu-id="640ed-142">A **Számla részletei** oldalon válassza a **Felosztások** lehetőséget az összes felosztás megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="640ed-142">On the **Invoice details** page, select **Distributions** to show all distributions.</span></span> <span data-ttu-id="640ed-143">Itt megtekintheti a teljes számla könyvelési adatait.</span><span class="sxs-lookup"><span data-stu-id="640ed-143">Here, you can view the accounting for the whole invoice.</span></span> <span data-ttu-id="640ed-144">A megjelenített információ tartalmazza a pénzügyi dimenziókat és a fő számlákat.</span><span class="sxs-lookup"><span data-stu-id="640ed-144">The information that is shown includes the financial dimensions and the main accounts.</span></span> 
7.  <span data-ttu-id="640ed-145">Válassza ki a **Mellékletek** lehetőséget a számlához csatolt bármely megjegyzés vagy fájl megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="640ed-145">Select **Attachments** to view any notes or files that are attached to the invoice.</span></span>
8.  <span data-ttu-id="640ed-146">A **Számla részletei** lapon válassza ki a megfelelő munkafolyamat-műveletet az ellenőrzési folyamat befejezéséhez.</span><span class="sxs-lookup"><span data-stu-id="640ed-146">On the **Invoice details** page, select the appropriate workflow action to complete your review process.</span></span>
9.  <span data-ttu-id="640ed-147">Válassza a **Kész** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="640ed-147">Select **Done**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]