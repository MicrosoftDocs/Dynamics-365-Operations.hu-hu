---
title: ER Dokumentumkezelési fájlok használata formátumkimenetekben (2. rész – Adatmodell kibővítése)
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni egy Elektronikus jelentéskészítési (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatára az ER-kimenetben. (2. rész)
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
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9cd06cdfd9bae57577c2e3ec97848e319b197f41
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092591"
---
# <a name="er-use-document-management-files-in-format-outputs-part-2---extend-data-model"></a><span data-ttu-id="f6bc1-104">ER Dokumentumkezelési fájlok használata formátumkimenetekben (2. rész – Adatmodell kibővítése)</span><span class="sxs-lookup"><span data-stu-id="f6bc1-104">ER Use Document Management files in format outputs (Part 2 - Extend data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f6bc1-105">A következő lépések leírják, hogy egy Rendszergazda vagy Elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-105">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="f6bc1-106">Ezeket a lépéseket bármely vállalatban végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="f6bc1-107">A lépések végrehajtásához először végre kell hajtania az „ER Dokumentumkezelési fájlok használata formátumkimenetekben (1. rész: Adatmodell előkészítése)” feladat-útmutató lépéseit.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 1: Prepare data model)" task guide.</span></span>

<span data-ttu-id="f6bc1-108">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a><span data-ttu-id="f6bc1-109">Az adatmodell kibővítése a benne található Dokumentumkezelés fájlok megjelenítéséhez</span><span class="sxs-lookup"><span data-stu-id="f6bc1-109">Extend data model to present the Document Management files in it</span></span>
1. <span data-ttu-id="f6bc1-110">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="f6bc1-111">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="f6bc1-112">A fastruktúrában bontsa ki a „Vevői számlamodell” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-112">In the tree, expand 'Customer invoice model'.</span></span>
4. <span data-ttu-id="f6bc1-113">A fastruktúrában válassza ki a következőt: Vevői számlamodell\Vevői számlamodell (egyéni).</span><span class="sxs-lookup"><span data-stu-id="f6bc1-113">In the tree, select 'Customer invoice model\Customer invoice model (custom)'.</span></span>
5. <span data-ttu-id="f6bc1-114">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-114">Click Designer.</span></span>
6. <span data-ttu-id="f6bc1-115">A fastruktúrában válassza ki a „Vevői számla (InvoiceCustomer)” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-115">In the tree, select 'Customer invoice(InvoiceCustomer)'.</span></span>
    * <span data-ttu-id="f6bc1-116">Ki fogjuk terjeszteni ezt az adatmodellt, hogy az összes olyan fájlt megjelenítsük benne, amelyet olyan értékesítési rendeléshez mellékeltek, amely egy elektronikusan feldolgozott számlához kapcsolódik.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-116">We will extend this data model to expose in it any files that have been attached to a sales order that is related to an electronically processing invoice.</span></span>  
7. <span data-ttu-id="f6bc1-117">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-117">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="f6bc1-118">A Név mezőbe írja be a következőt: „Számlamellékletek”.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-118">In the Name field, type 'Invoice attachments'.</span></span>
    * <span data-ttu-id="f6bc1-119">Számlamellékletek</span><span class="sxs-lookup"><span data-stu-id="f6bc1-119">Invoice attachments</span></span>  
9. <span data-ttu-id="f6bc1-120">A Cikktípus mezőben válassza ki a „Rekordlista” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-120">In the Item type field, select 'Record list'.</span></span>
10. <span data-ttu-id="f6bc1-121">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-121">Click Add.</span></span>
11. <span data-ttu-id="f6bc1-122">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-122">Click New to open the drop dialog.</span></span>
12. <span data-ttu-id="f6bc1-123">A Név mezőbe írja be a következőt: „Fájltartalom”.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-123">In the Name field, type 'File content'.</span></span>
    * <span data-ttu-id="f6bc1-124">Fájl tartalma</span><span class="sxs-lookup"><span data-stu-id="f6bc1-124">File content</span></span>  
13. <span data-ttu-id="f6bc1-125">A Cikktípus mezőben válassza ki a „Tároló” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-125">In the Item type field, select 'Container'.</span></span>
14. <span data-ttu-id="f6bc1-126">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-126">Click Add.</span></span>
15. <span data-ttu-id="f6bc1-127">Az Új gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-127">Click New to open the drop dialog.</span></span>
16. <span data-ttu-id="f6bc1-128">A Név mezőbe írja be a következőt: „Fájlnév”.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-128">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="f6bc1-129">Fájlnév</span><span class="sxs-lookup"><span data-stu-id="f6bc1-129">File name</span></span>  
17. <span data-ttu-id="f6bc1-130">A Cikktípus mezőben válassza ki a „Karakterlánc” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-130">In the Item type field, select 'String'.</span></span>
18. <span data-ttu-id="f6bc1-131">Kattintson a Hozzáadás gombra.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-131">Click Add.</span></span>

## <a name="map-new-data-model-elements-to-data-sources"></a><span data-ttu-id="f6bc1-132">Az új adatmodellelemek leképezése adatforrásokra</span><span class="sxs-lookup"><span data-stu-id="f6bc1-132">Map new data model elements to data sources</span></span>
1. <span data-ttu-id="f6bc1-133">Kattintson a Modell hozzárendelése adatforráshoz gombra.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-133">Click Map model to datasource.</span></span>
2. <span data-ttu-id="f6bc1-134">A gyorsszűrő használatával keresse meg azokat a rekordokat, ahol a Definíció mezőben az „InvoiceCustomer” érték szerepel.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-134">Use the Quick Filter to filter on the Definition field with a value of 'InvoiceCustomer'.</span></span>
    * <span data-ttu-id="f6bc1-135">InvoiceCustomer</span><span class="sxs-lookup"><span data-stu-id="f6bc1-135">InvoiceCustomer</span></span>  
    * <span data-ttu-id="f6bc1-136">Az új modellelemeket hozzá fogjuk rendelni a megfelelő adatforrásokhoz.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-136">We will map new model elements to appropriate data sources.</span></span>  
3. <span data-ttu-id="f6bc1-137">Kattintson a Tervező pontra.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-137">Click Designer.</span></span>
4. <span data-ttu-id="f6bc1-138">A fastruktúrában válassza ki a „Számlamellékletek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-138">In the tree, select 'Invoice attachments'.</span></span>
5. <span data-ttu-id="f6bc1-139">A fastruktúrában bontsa ki a „Számlamellékletek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-139">In the tree, expand 'Invoice attachments'.</span></span>
6. <span data-ttu-id="f6bc1-140">A fastruktúrában válassza ki a „Számlamellékletek\Fájlnév” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-140">In the tree, select 'Invoice attachments\File name'.</span></span>
7. <span data-ttu-id="f6bc1-141">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-141">Click Edit.</span></span>
8. <span data-ttu-id="f6bc1-142">A Képlet mezőbe írja be következőt: 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-142">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.</span></span>
    * <span data-ttu-id="f6bc1-143">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span><span class="sxs-lookup"><span data-stu-id="f6bc1-143">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'</span></span>  
9. <span data-ttu-id="f6bc1-144">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-144">Click Save.</span></span>
10. <span data-ttu-id="f6bc1-145">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-145">Close the page.</span></span>
11. <span data-ttu-id="f6bc1-146">A fastruktúrában válassza ki a „Számlamellékletek\Fájltartalom” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-146">In the tree, select 'Invoice attachments\File content'.</span></span>
12. <span data-ttu-id="f6bc1-147">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-147">Click Edit.</span></span>
13. <span data-ttu-id="f6bc1-148">A Képlet mezőbe írja be következőt: 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-148">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.</span></span>
    * <span data-ttu-id="f6bc1-149">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span><span class="sxs-lookup"><span data-stu-id="f6bc1-149">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'</span></span>  
14. <span data-ttu-id="f6bc1-150">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-150">Click Save.</span></span>
15. <span data-ttu-id="f6bc1-151">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-151">Close the page.</span></span>
16. <span data-ttu-id="f6bc1-152">A fastruktúrában válassza ki a „Számlamellékletek” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-152">In the tree, select 'Invoice attachments'.</span></span>
17. <span data-ttu-id="f6bc1-153">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-153">Click Edit.</span></span>
18. <span data-ttu-id="f6bc1-154">A Képlet mezőbe írja be következőt: 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-154">In the Formula field, enter 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.</span></span>
    * <span data-ttu-id="f6bc1-155">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span><span class="sxs-lookup"><span data-stu-id="f6bc1-155">CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'</span></span>  
19. <span data-ttu-id="f6bc1-156">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-156">Click Save.</span></span>
20. <span data-ttu-id="f6bc1-157">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-157">Close the page.</span></span>
21. <span data-ttu-id="f6bc1-158">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-158">Click Save.</span></span>
22. <span data-ttu-id="f6bc1-159">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-159">Close the page.</span></span>
23. <span data-ttu-id="f6bc1-160">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-160">Close the page.</span></span>
24. <span data-ttu-id="f6bc1-161">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-161">Close the page.</span></span>
25. <span data-ttu-id="f6bc1-162">Kattintson az Állapot módosítása elemre.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-162">Click Change status.</span></span>
26. <span data-ttu-id="f6bc1-163">Kattintson a Befejezés gombra.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-163">Click Complete.</span></span>
27. <span data-ttu-id="f6bc1-164">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="f6bc1-164">Click OK.</span></span>

