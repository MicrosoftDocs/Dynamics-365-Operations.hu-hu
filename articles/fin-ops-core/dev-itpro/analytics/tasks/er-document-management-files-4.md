---
title: ER Dokumentumkezelési fájlok használata formátumkimenetekben (4. rész – Formátum futtatása)
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni egy Elektronikus jelentéskészítési formátumot a dokumentumkezelési fájlok használatára az ER-kimenetben. (4. rész)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenInvoicesListPage, CustInvoiceJournal, SalesTable, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ede71118f64eec27b150a4c575aead97d3174509
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559725"
---
# <a name="er-use-document-management-files-in-format-outputs-part-4---run-format"></a><span data-ttu-id="a7264-104">ER Dokumentumkezelési fájlok használata formátumkimenetekben (4. rész – Formátum futtatása)</span><span class="sxs-lookup"><span data-stu-id="a7264-104">ER Use Document Management files in format outputs (Part 4 - Run format)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a7264-105">A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben.</span><span class="sxs-lookup"><span data-stu-id="a7264-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="a7264-106">Ezeket a lépéseket a DEMF vállalatban hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="a7264-106">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="a7264-107">A lépések végrehajtásához először végre kell hajtania az „ER Dokumentumkezelési fájlok használata formátumkimenetekben (3. rész: Formátum létrehozása)” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="a7264-107">To complete these steps, you must first complete the steps in the "ER Use Document Management files in format outputs (Part 3: Create format)" procedure.</span></span>

<span data-ttu-id="a7264-108">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="a7264-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a><span data-ttu-id="a7264-109">Egyetlen számla értékesítési rendeléshez szükséges mellékleteinek hozzáadása</span><span class="sxs-lookup"><span data-stu-id="a7264-109">Add necessary attachments for sales order of a single invoice</span></span>
1. <span data-ttu-id="a7264-110">Ugorjon a Kinnlévőségek > Számlák > Nyitott vevői számlák pontra.</span><span class="sxs-lookup"><span data-stu-id="a7264-110">Go to Accounts receivable > Invoices > Open customer invoices.</span></span>
2. <span data-ttu-id="a7264-111">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="a7264-111">Use the Quick Filter to find records.</span></span> <span data-ttu-id="a7264-112">Például szűrje a Számla mezőt a „CIV-000148” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="a7264-112">For example, filter on the Invoice field with a value of 'CIV-000148'.</span></span>
    * <span data-ttu-id="a7264-113">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="a7264-113">CIV-000148</span></span>  
3. <span data-ttu-id="a7264-114">Ide kattintva nyithatja meg a kijelölt számla hivatkozását.</span><span class="sxs-lookup"><span data-stu-id="a7264-114">Click to follow the selected invoice's link.</span></span>
    * <span data-ttu-id="a7264-115">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="a7264-115">CIV-000148</span></span>  
4. <span data-ttu-id="a7264-116">Kattintson az Értékesítési rendelés mezőben található hivatkozás megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="a7264-116">Click to follow the link in the Sales order field.</span></span>
    * <span data-ttu-id="a7264-117">000148</span><span class="sxs-lookup"><span data-stu-id="a7264-117">000148</span></span>  
5. <span data-ttu-id="a7264-118">A Sorok vagy fejléc mezőben válassza a Fejléc lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7264-118">In the Lines or header field, select the option of Header.</span></span>
    * <span data-ttu-id="a7264-119">Válassza ki a fejlécet annak a jelzésére, hogy ez lesz a cél a mellékletek hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="a7264-119">Select Header to indicate that this will be the target for adding attachments.</span></span>  
6. <span data-ttu-id="a7264-120">Kattintson a Csatolás elemre.</span><span class="sxs-lookup"><span data-stu-id="a7264-120">Click Attach.</span></span>
    * <span data-ttu-id="a7264-121">Adjon hozzá néhány fájlt az értékesítési rendeléshez mellékletként.</span><span class="sxs-lookup"><span data-stu-id="a7264-121">Add a few files as attachments for this sales order.</span></span> <span data-ttu-id="a7264-122">A Dokumentumkezelés által támogatott típusú dokumentumfájlokat használja (a fájlkiterjesztés DOCX, DPF, XML, JPG stb.).</span><span class="sxs-lookup"><span data-stu-id="a7264-122">Use the files of the document types that are supported by the Document Management (with file extensions DOCX, DPF, XML, JPG, etc.).</span></span> <span data-ttu-id="a7264-123">Keresse meg és válassza ki a fájlokat csatolásra és további feldolgozásra a kapcsolódó számlával az ER elektronikus üzenetben.</span><span class="sxs-lookup"><span data-stu-id="a7264-123">Browse and select files to be attached and further processed with the related invoice in the ER electronic message.</span></span>  
7. <span data-ttu-id="a7264-124">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a7264-124">Click New.</span></span>
8. <span data-ttu-id="a7264-125">Kattintson a Fájlra.</span><span class="sxs-lookup"><span data-stu-id="a7264-125">Click File.</span></span>
9. <span data-ttu-id="a7264-126">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="a7264-126">Click New.</span></span>
10. <span data-ttu-id="a7264-127">Kattintson a Fájlra.</span><span class="sxs-lookup"><span data-stu-id="a7264-127">Click File.</span></span>
11. <span data-ttu-id="a7264-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a7264-128">Close the page.</span></span>
12. <span data-ttu-id="a7264-129">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a7264-129">Close the page.</span></span>
13. <span data-ttu-id="a7264-130">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a7264-130">Close the page.</span></span>
14. <span data-ttu-id="a7264-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="a7264-131">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="a7264-132">A tervezett jelentés futtatása a kijelölt számlához</span><span class="sxs-lookup"><span data-stu-id="a7264-132">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="a7264-133">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="a7264-133">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="a7264-134">A fastruktúrában bontsa ki a „Vevői számlamodell” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a7264-134">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="a7264-135">A fastruktúrában bontsa ki a következőt: Vevői számlamodell\Vevői számlamodell (egyéni).</span><span class="sxs-lookup"><span data-stu-id="a7264-135">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="a7264-136">A fastruktúrában válassza ki a következőt: Vevői számlamodell\Vevői számlamodell (egyéni)\Elektronikus számla mintaüzenet.</span><span class="sxs-lookup"><span data-stu-id="a7264-136">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="a7264-137">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="a7264-137">Click Run.</span></span>
6. <span data-ttu-id="a7264-138">Bontsa ki a Belefoglalandó rekordok () szakaszt.</span><span class="sxs-lookup"><span data-stu-id="a7264-138">Expand the Records to include () section.</span></span>
7. <span data-ttu-id="a7264-139">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="a7264-139">Click Filter.</span></span>
8. <span data-ttu-id="a7264-140">Válassza ki a Vevői számlanapló sorát és a Értékesítési rendelés mezőt.</span><span class="sxs-lookup"><span data-stu-id="a7264-140">Select the row of the Customer invoice journal and the Sales order field.</span></span>
9. <span data-ttu-id="a7264-141">A Feltétel mezőbe írja be a „000148” értéket.</span><span class="sxs-lookup"><span data-stu-id="a7264-141">In the Criteria field, type '000148'.</span></span>
    * <span data-ttu-id="a7264-142">Az „Értékesítési rendelés” mezőbe feltételként írja be a 000148-es rendelésszámot.</span><span class="sxs-lookup"><span data-stu-id="a7264-142">In the criteria "Sales order" field, type the order number 000148.</span></span>  
10. <span data-ttu-id="a7264-143">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a7264-143">Click OK.</span></span>
11. <span data-ttu-id="a7264-144">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="a7264-144">Click OK.</span></span>
    * <span data-ttu-id="a7264-145">Tekintse át a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="a7264-145">Review the generated output.</span></span> <span data-ttu-id="a7264-146">Fontos megjegyezni, hogy az összes melléklethez létrejött egy XML-csomópont.</span><span class="sxs-lookup"><span data-stu-id="a7264-146">Note that for each attachment a single XML node has been created.</span></span> <span data-ttu-id="a7264-147">A melléklet tartalma a MIME (base64) szövegformátumú XML-kimenethez van feltöltve.</span><span class="sxs-lookup"><span data-stu-id="a7264-147">The attachment's content is populated to the XML output in MIME (base64) text format.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]