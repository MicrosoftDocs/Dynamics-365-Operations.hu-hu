--- 
title: "Formátum futtatása dokumentumkezelési fájlok használatára formátumkimenetekben elektronikus jelentéskészítéshez (ER)"
description: "A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben."
author: NickSelin
manager: AnnBe
ms.date: 10/31/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 419c3e305dfdd7d8612340b4a8e8e54e13c6362b
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---
# <a name="run-format-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a><span data-ttu-id="7cf42-103">Formátum futtatása dokumentumkezelési fájlok használatára formátumkimenetekben elektronikus jelentéskészítéshez (ER)</span><span class="sxs-lookup"><span data-stu-id="7cf42-103">Run format to use Document Management files in format outputs for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7cf42-104">A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben.</span><span class="sxs-lookup"><span data-stu-id="7cf42-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="7cf42-105">Ezeket a lépéseket a DEMF vállalatban hajthatja végre.</span><span class="sxs-lookup"><span data-stu-id="7cf42-105">These steps can be performed in the DEMF company.</span></span>

<span data-ttu-id="7cf42-106">A lépések végrehajtásához először végre kell hajtania az „ER Dokumentumkezelési fájlok használata formátumkimenetekben (3. rész: Formátum létrehozása)” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="7cf42-106">To complete these steps, you must first complete the steps in the “ER Use Document Management files in format outputs (Part 3: Create format)” procedure.</span></span>

<span data-ttu-id="7cf42-107">Ez az eljárás egy olyan funkcióra vonatkozik, amely a Dynamics 365 for Operations 1611-es verziójába került be.</span><span class="sxs-lookup"><span data-stu-id="7cf42-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="add-necessary-attachments-for-sales-order-of-a-single-invoice"></a><span data-ttu-id="7cf42-108">Egyetlen számla értékesítési rendeléshez szükséges mellékleteinek hozzáadása</span><span class="sxs-lookup"><span data-stu-id="7cf42-108">Add necessary attachments for sales order of a single invoice</span></span>
1. <span data-ttu-id="7cf42-109">Ugorjon a Kinnlévőségek > Számlák > Nyitott vevői számlák pontra.</span><span class="sxs-lookup"><span data-stu-id="7cf42-109">Go to Accounts receivable > Invoices > Open customer invoices.</span></span>
2. <span data-ttu-id="7cf42-110">Rekordok kereséséhez használja a gyorsszűrőt.</span><span class="sxs-lookup"><span data-stu-id="7cf42-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="7cf42-111">Például szűrje a Számla mezőt a „CIV-000148” értéket beírva.</span><span class="sxs-lookup"><span data-stu-id="7cf42-111">For example, filter on the Invoice field with a value of 'CIV-000148'.</span></span>
    * <span data-ttu-id="7cf42-112">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="7cf42-112">CIV-000148</span></span>  
3. <span data-ttu-id="7cf42-113">Ide kattintva nyithatja meg a kijelölt számla hivatkozását.</span><span class="sxs-lookup"><span data-stu-id="7cf42-113">Click to follow the selected invoice’s link.</span></span>
    * <span data-ttu-id="7cf42-114">CIV-000148</span><span class="sxs-lookup"><span data-stu-id="7cf42-114">CIV-000148</span></span>  
4. <span data-ttu-id="7cf42-115">Kattintson az Értékesítési rendelés mezőben található hivatkozás megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="7cf42-115">Click to follow the link in the Sales order field.</span></span>
    * <span data-ttu-id="7cf42-116">000148</span><span class="sxs-lookup"><span data-stu-id="7cf42-116">000148</span></span>  
5. <span data-ttu-id="7cf42-117">A Sorok vagy fejléc mezőben válassza a Fejléc lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7cf42-117">In the Lines or header field, select the option of Header.</span></span>
    * <span data-ttu-id="7cf42-118">Válassza ki a fejlécet annak a jelzésére, hogy ez lesz a cél a mellékletek hozzáadásához.</span><span class="sxs-lookup"><span data-stu-id="7cf42-118">Select Header to indicate that this will be the target for adding attachments.</span></span>  
6. <span data-ttu-id="7cf42-119">Kattintson a Csatolás elemre.</span><span class="sxs-lookup"><span data-stu-id="7cf42-119">Click Attach.</span></span>
    * <span data-ttu-id="7cf42-120">Adjon hozzá néhány fájlt az értékesítési rendeléshez mellékletként.</span><span class="sxs-lookup"><span data-stu-id="7cf42-120">Add a few files as attachments for this sales order.</span></span> <span data-ttu-id="7cf42-121">A Dokumentumkezelés által támogatott típusú dokumentumfájlokat használja (a fájlkiterjesztés DOCX, DPF, XML, JPG stb.).</span><span class="sxs-lookup"><span data-stu-id="7cf42-121">Use the files of the document types that are supported by the Document Management (with file extensions DOCX, DPF, XML, JPG, etc.).</span></span> <span data-ttu-id="7cf42-122">Keresse meg és válassza ki a fájlokat csatolásra és további feldolgozásra a kapcsolódó számlával az ER elektronikus üzenetben.</span><span class="sxs-lookup"><span data-stu-id="7cf42-122">Browse and select files to be attached and further processed with the related invoice in the ER electronic message.</span></span>  
7. <span data-ttu-id="7cf42-123">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7cf42-123">Click New.</span></span>
8. <span data-ttu-id="7cf42-124">Kattintson a Fájlra.</span><span class="sxs-lookup"><span data-stu-id="7cf42-124">Click File.</span></span>
9. <span data-ttu-id="7cf42-125">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="7cf42-125">Click New.</span></span>
10. <span data-ttu-id="7cf42-126">Kattintson a Fájlra.</span><span class="sxs-lookup"><span data-stu-id="7cf42-126">Click File.</span></span>
11. <span data-ttu-id="7cf42-127">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7cf42-127">Close the page.</span></span>
12. <span data-ttu-id="7cf42-128">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7cf42-128">Close the page.</span></span>
13. <span data-ttu-id="7cf42-129">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7cf42-129">Close the page.</span></span>
14. <span data-ttu-id="7cf42-130">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="7cf42-130">Close the page.</span></span>

## <a name="run-the-designed-report-for-the-selected-invoice"></a><span data-ttu-id="7cf42-131">A tervezett jelentés futtatása a kijelölt számlához</span><span class="sxs-lookup"><span data-stu-id="7cf42-131">Run the designed report for the selected invoice</span></span>
1. <span data-ttu-id="7cf42-132">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="7cf42-132">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="7cf42-133">A fastruktúrában bontsa ki a „Vevői számlamodell” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7cf42-133">In the tree, expand 'Customer invoice model'.</span></span>
3. <span data-ttu-id="7cf42-134">A fastruktúrában bontsa ki a következőt: Vevői számlamodell\Vevői számlamodell (egyéni).</span><span class="sxs-lookup"><span data-stu-id="7cf42-134">In the tree, expand 'Customer invoice model\Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="7cf42-135">A fastruktúrában válassza ki a következőt: Vevői számlamodell\Vevői számlamodell (egyéni)\Elektronikus számla mintaüzenet.</span><span class="sxs-lookup"><span data-stu-id="7cf42-135">In the tree, select 'Customer invoice model\Customer invoice model (custom)\Electronic invoice sample message'.</span></span>
5. <span data-ttu-id="7cf42-136">Kattintson a Futtatás elemre.</span><span class="sxs-lookup"><span data-stu-id="7cf42-136">Click Run.</span></span>
6. <span data-ttu-id="7cf42-137">Bontsa ki a Belefoglalandó rekordok () szakaszt.</span><span class="sxs-lookup"><span data-stu-id="7cf42-137">Expand the Records to include () section.</span></span>
7. <span data-ttu-id="7cf42-138">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="7cf42-138">Click Filter.</span></span>
8. <span data-ttu-id="7cf42-139">Válassza ki a Vevői számlanapló sorát és a Értékesítési rendelés mezőt.</span><span class="sxs-lookup"><span data-stu-id="7cf42-139">Select the row of the Customer invoice journal and the Sales order field.</span></span>
9. <span data-ttu-id="7cf42-140">A Feltétel mezőbe írja be a „000148” értéket.</span><span class="sxs-lookup"><span data-stu-id="7cf42-140">In the Criteria field, type '000148'.</span></span>
    * <span data-ttu-id="7cf42-141">Az „Értékesítési rendelés” mezőbe feltételként írja be a 000148-es rendelésszámot.</span><span class="sxs-lookup"><span data-stu-id="7cf42-141">In the criteria “Sales order” field, type the order number 000148.</span></span>  
10. <span data-ttu-id="7cf42-142">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7cf42-142">Click OK.</span></span>
11. <span data-ttu-id="7cf42-143">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="7cf42-143">Click OK.</span></span>
    * <span data-ttu-id="7cf42-144">Tekintse át a létrehozott kimenetet.</span><span class="sxs-lookup"><span data-stu-id="7cf42-144">Review the generated output.</span></span> <span data-ttu-id="7cf42-145">Fontos megjegyezni, hogy az összes melléklethez létrejött egy XML-csomópont.</span><span class="sxs-lookup"><span data-stu-id="7cf42-145">Note that for each attachment a single XML node has been created.</span></span> <span data-ttu-id="7cf42-146">A melléklet tartalma a MIME (base64) szövegformátumú XML-kimenethez van feltöltve.</span><span class="sxs-lookup"><span data-stu-id="7cf42-146">The attachment’s content is populated to the XML output in MIME (base64) text format.</span></span>  

