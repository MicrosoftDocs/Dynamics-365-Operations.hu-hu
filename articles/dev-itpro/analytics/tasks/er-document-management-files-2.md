---
title: ER Dokumentumkezelési fájlok használata formátumkimenetekben (2. rész – Adatmodell kibővítése)
description: A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cb4c58dc86a159a70634c05408a8db471ebcae4c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544805"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2-extend-data-model"></a><span data-ttu-id="556f4-103">ER Dokumentumkezelési fájlok használata formátumkimenetekben (2. rész: Adatmodell kibővítése)</span><span class="sxs-lookup"><span data-stu-id="556f4-103">ER Use Document Management files in format outputs (Part 2: Extend data model)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="556f4-104">A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben.</span><span class="sxs-lookup"><span data-stu-id="556f4-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="556f4-105">Ezeket a lépéseket bármely vállalatban végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="556f4-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="556f4-106">A lépések végrehajtásához először végre kell hajtania az „ER Dokumentumkezelési fájlok használata formátumkimenetekben (1. rész: Adatmodell előkészítése)” feladat-útmutató lépéseit.</span><span class="sxs-lookup"><span data-stu-id="556f4-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 1: Prepare data model)” task guide.</span></span>

<span data-ttu-id="556f4-107">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="556f4-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="556f4-108">Az adatmodell kibővítése a benne található Dokumentumkezelés fájlok megjelenítéséhez</span><span class="sxs-lookup"><span data-stu-id="556f4-108">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="556f4-109">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="556f4-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="556f4-110">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="556f4-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="556f4-111">A fastruktúrában bontsa ki a „Vevői számlamodell” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="556f4-111">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="556f4-112">A fastruktúrában válassza ki a következőt: Vevői számlamodell\Vevői számlamodell (egyéni).</span><span class="sxs-lookup"><span data-stu-id="556f4-112">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="556f4-113">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="556f4-113">Click Designer.</span></span>
6. <span data-ttu-id="556f4-114">A fastruktúrában válassza ki a „Vevői számla (InvoiceCustomer)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="556f4-114">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="556f4-115">Ki fogjuk terjeszteni ezt az adatmodellt, hogy az összes olyan fájlt megjelenítsük benne, amelyet olyan értékesítési rendeléshez mellékeltek, amely egy elektronikusan feldolgozott számlához kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="556f4-115">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="556f4-116">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="556f4-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="556f4-117">A Név mezőbe írja be a következőt: „Számlamellékletek”.</span><span class="sxs-lookup"><span data-stu-id="556f4-117">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="556f4-118">Számlamellékletek</span><span class="sxs-lookup"><span data-stu-id="556f4-118">Invoice attachments</span></span>  
9. <span data-ttu-id="556f4-119">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="556f4-119">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="556f4-120">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="556f4-120">Click Add.</span></span>
11. <span data-ttu-id="556f4-121">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="556f4-121">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="556f4-122">A Név mezőbe írja be a következőt: „Fájltartalom”.</span><span class="sxs-lookup"><span data-stu-id="556f4-122">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="556f4-123">Fájl tartalma</span><span class="sxs-lookup"><span data-stu-id="556f4-123">File content</span></span>  
13. <span data-ttu-id="556f4-124">A Cikktípus mezőben válassza ki a „Tároló” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="556f4-124">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="556f4-125">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="556f4-125">Click Add.</span></span>
15. <span data-ttu-id="556f4-126">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="556f4-126">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="556f4-127">A Név mezőbe írja be a következőt: „Fájlnév”.</span><span class="sxs-lookup"><span data-stu-id="556f4-127">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="556f4-128">Fájlnév</span><span class="sxs-lookup"><span data-stu-id="556f4-128">File name</span></span>  
17. <span data-ttu-id="556f4-129">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="556f4-129">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="556f4-130">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="556f4-130">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-dynamics-365-for-finance-and-operations-enterprise-edition-data-sources"></a><span data-ttu-id="556f4-131">Az új adatmodellelemek leképezése a Dynamics 365 for Finance and Operations, Enterprise kiadás adatforrásokra</span><span class="sxs-lookup"><span data-stu-id="556f4-131">Map new data model elements to Dynamics 365 for Finance and Operations, Enterprise edition data sources</span></span>
1. <span data-ttu-id="556f4-132">Kattintson a Modell hozzárendelése adatforráshoz gombra.</span><span class="sxs-lookup"><span data-stu-id="556f4-132">Click Map model to datasource.</span></span>
2. <span data-ttu-id="556f4-133">A gyorsszűrő használatával keresse meg azokat a rekordokat, ahol a Definíció mezőben az „InvoiceCustomer” érték szerepel.</span><span class="sxs-lookup"><span data-stu-id="556f4-133">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="556f4-134">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="556f4-134">InvoiceCustomer</span></span>  
    * <span data-ttu-id="556f4-135">Az új modellelemeket hozzá fogjuk rendelni a megfelelő adatforrásokhoz.</span><span class="sxs-lookup"><span data-stu-id="556f4-135">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="556f4-136">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="556f4-136">Click Designer.</span></span>
4. <span data-ttu-id="556f4-137">A fastruktúrában válassza ki a „Számlamellékletek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="556f4-137">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="556f4-138">A fastruktúrában bontsa ki a „Számlamellékletek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="556f4-138">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="556f4-139">A fastruktúrában válassza ki a „Számlamellékletek\Fájlnév” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="556f4-139">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="556f4-140">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="556f4-140">Click Edit.</span></span>
8. <span data-ttu-id="556f4-141">A Képlet mezőbe írja be következőt: 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span><span class="sxs-lookup"><span data-stu-id="556f4-141">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="556f4-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span><span class="sxs-lookup"><span data-stu-id="556f4-142">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="556f4-143">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="556f4-143">Click Save.</span></span>
10. <span data-ttu-id="556f4-144">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="556f4-144">Close the page.</span></span>
11. <span data-ttu-id="556f4-145">A fastruktúrában válassza ki a „Számlamellékletek\Fájltartalom” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="556f4-145">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="556f4-146">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="556f4-146">Click Edit.</span></span>
13. <span data-ttu-id="556f4-147">A Képlet mezőbe írja be következőt: 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span><span class="sxs-lookup"><span data-stu-id="556f4-147">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="556f4-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span><span class="sxs-lookup"><span data-stu-id="556f4-148">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="556f4-149">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="556f4-149">Click Save.</span></span>
15. <span data-ttu-id="556f4-150">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="556f4-150">Close the page.</span></span>
16. <span data-ttu-id="556f4-151">A fastruktúrában válassza ki a „Számlamellékletek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="556f4-151">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="556f4-152">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="556f4-152">Click Edit.</span></span>
18. <span data-ttu-id="556f4-153">A Képlet mezőbe írja be következőt: 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span><span class="sxs-lookup"><span data-stu-id="556f4-153">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="556f4-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span><span class="sxs-lookup"><span data-stu-id="556f4-154">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="556f4-155">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="556f4-155">Click Save.</span></span>
20. <span data-ttu-id="556f4-156">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="556f4-156">Close the page.</span></span>
21. <span data-ttu-id="556f4-157">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="556f4-157">Click Save.</span></span>
22. <span data-ttu-id="556f4-158">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="556f4-158">Close the page.</span></span>
23. <span data-ttu-id="556f4-159">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="556f4-159">Close the page.</span></span>
24. <span data-ttu-id="556f4-160">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="556f4-160">Close the page.</span></span>
25. <span data-ttu-id="556f4-161">Kattintson az Állapot módosítása elemre.</span><span class="sxs-lookup"><span data-stu-id="556f4-161">Click Change status.</span></span>
26. <span data-ttu-id="556f4-162">Kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="556f4-162">Click Complete.</span></span>
27. <span data-ttu-id="556f4-163">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="556f4-163">Click OK.</span></span>

