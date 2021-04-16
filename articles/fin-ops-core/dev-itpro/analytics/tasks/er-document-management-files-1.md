---
title: ER Dokumentumkezelési fájlok használata formátumkimenetekben (1. rész – Adatmodell előkészítése)
description: Ez a témakör azt ismerteti, hogyan kell konfigurálni egy Elektronikus jelentéskészítési (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatára az ER-kimenetben. (1. rész)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6b265c9af0635e6c9fb6295f7e8e4e353b2a5ba5
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754938"
---
# <a name="er-use-document-management-files-in-format-outputs-part-1---prepare-data-model"></a><span data-ttu-id="c100c-104">ER Dokumentumkezelési fájlok használata formátumkimenetekben (1. rész – Adatmodell előkészítése)</span><span class="sxs-lookup"><span data-stu-id="c100c-104">ER Use Document Management files in format outputs (Part 1 - Prepare data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c100c-105">A következő lépések leírják, hogy egy rendszergazda vagy elektronikus jelentések fejlesztője szerepkörrel rendelkező felhasználó miként konfigurálhat egy új Elektronikus jelentés (ER) formátumot a dokumentumkezelési fájlok (mellékletek) használatához az ER-kimenetben.</span><span class="sxs-lookup"><span data-stu-id="c100c-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="c100c-106">Ezeket a lépéseket bármely vállalatban végrehajthatja.</span><span class="sxs-lookup"><span data-stu-id="c100c-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="c100c-107">Hajtsa végre az alábbi lépéseket: először hajtsa végre a „Konfigurációszolgáltató létrehozása és aktívként történő megjelölése” eljárás lépéseit.</span><span class="sxs-lookup"><span data-stu-id="c100c-107">To complete these steps, you must first complete the steps in the "Create a configuration provider and mark it as active" procedure.</span></span>

<span data-ttu-id="c100c-108">Az eljárás egy olyan szolgáltatáshoz tartozik, amely a Dynamics 365 for Operations 1611-es verziójában jelent meg.</span><span class="sxs-lookup"><span data-stu-id="c100c-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="c100c-109">Hozzáférés a Microsoft által biztosított konfigurációk listájához</span><span class="sxs-lookup"><span data-stu-id="c100c-109">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="c100c-110">Ugorjon a Szervezeti adminisztráció > Munkaterületek > Elektronikus jelentés pontra.</span><span class="sxs-lookup"><span data-stu-id="c100c-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>

    <span data-ttu-id="c100c-111">Győződjön meg róla, hogy a Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="c100c-111">Make sure that the 'Litware, Inc.'</span></span> <span data-ttu-id="c100c-112">szolgáltató elérhető és aktívként megjelölt legyen.</span><span class="sxs-lookup"><span data-stu-id="c100c-112">provider is available and marked as active.</span></span>  

2. <span data-ttu-id="c100c-113">Válassza ki a Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="c100c-113">Select the 'Litware, Inc.'</span></span> <span data-ttu-id="c100c-114">szolgáltatót.</span><span class="sxs-lookup"><span data-stu-id="c100c-114">provider.</span></span>
3. <span data-ttu-id="c100c-115">Kattintson a Tárházak gombra.</span><span class="sxs-lookup"><span data-stu-id="c100c-115">Click Repositories.</span></span>

    <span data-ttu-id="c100c-116">Ha már létezik egy „Üzemi erőforrások” típusú tár, hagyja ki az aktuális altevékenység többi lépését.</span><span class="sxs-lookup"><span data-stu-id="c100c-116">If a repository of the 'Operations resources' type already exists, skip the remaining steps of the current sub-task.</span></span>  

4. <span data-ttu-id="c100c-117">A Hozzáadása gombra kattintva nyissa meg a legördülő párbeszédpanelt.</span><span class="sxs-lookup"><span data-stu-id="c100c-117">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="c100c-118">A Konfiguráció tárházának típusa mezőbe írja be az „Üzemi erőforrások” szöveget.</span><span class="sxs-lookup"><span data-stu-id="c100c-118">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="c100c-119">Kattintson a Tárház létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c100c-119">Click Create repository.</span></span>
7. <span data-ttu-id="c100c-120">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="c100c-120">Click OK.</span></span>

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a><span data-ttu-id="c100c-121">A Microsoft által biztosított vevői számlamodell konfigurációk beszerzése</span><span class="sxs-lookup"><span data-stu-id="c100c-121">Get the Customer invoice model configurations provided by Microsoft</span></span>
1. <span data-ttu-id="c100c-122">Kattintson a Szűrők megjelenítése pontra.</span><span class="sxs-lookup"><span data-stu-id="c100c-122">Click Show filters.</span></span>
2. <span data-ttu-id="c100c-123">Alkalmazza az alábbi szűrőket: Adja meg az „Üzemi erőforrások” szűrőértéket a „Név” mezőben a „kezdete” szűrőoperátor használatával; Adja meg az "" szűrőértéket a „Leírás” mezőben a „kezdete” szűrőoperátor használatával</span><span class="sxs-lookup"><span data-stu-id="c100c-123">Apply the following filters: Enter a filter value of "Operations resources" on the "Name" field using the "begins with" filter operator; Enter a filter value of "" on the "Description" field using the "begins with" filter operator</span></span>
3. <span data-ttu-id="c100c-124">Kattintson a Szűrők megjelenítése pontra.</span><span class="sxs-lookup"><span data-stu-id="c100c-124">Click Show filters.</span></span>
4. <span data-ttu-id="c100c-125">Kattintson a Megnyitás gombra.</span><span class="sxs-lookup"><span data-stu-id="c100c-125">Click Open.</span></span>
5. <span data-ttu-id="c100c-126">A fastruktúrában válassza ki a „Vevői számlamodell” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c100c-126">In the tree, select 'Customer invoice model'.</span></span>

    <span data-ttu-id="c100c-127">Válassza ki a „Vevői számlamodell modellkonfigurációt” az importáláshoz.</span><span class="sxs-lookup"><span data-stu-id="c100c-127">Select the model configuration 'Customer invoice model' to import it.</span></span>  

6. <span data-ttu-id="c100c-128">Kattintson az Importálás gombra.</span><span class="sxs-lookup"><span data-stu-id="c100c-128">Click Import.</span></span>

    <span data-ttu-id="c100c-129">Kattintson az Importálás gombra a kijelölt konfiguráció 1-es verziójának esetében.</span><span class="sxs-lookup"><span data-stu-id="c100c-129">Click Import for version 1 of the selected configuration.</span></span>  

7. <span data-ttu-id="c100c-130">Kattintson az Igen gombra.</span><span class="sxs-lookup"><span data-stu-id="c100c-130">Click Yes.</span></span>
8. <span data-ttu-id="c100c-131">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c100c-131">Close the page.</span></span>
9. <span data-ttu-id="c100c-132">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="c100c-132">Close the page.</span></span>
10. <span data-ttu-id="c100c-133">Kattintson a Jelentéskészítés konfigurációi lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c100c-133">Click Reporting configurations.</span></span>
11. <span data-ttu-id="c100c-134">A fastruktúrában válassza ki a „Vevői számlamodell” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="c100c-134">In the tree, select 'Customer invoice model'.</span></span>

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a><span data-ttu-id="c100c-135">Hozza létre a származtatott modellt a Dokumentumkezelés fájlok elérésének támogatásához.</span><span class="sxs-lookup"><span data-stu-id="c100c-135">Create the derived model to support access to the Document Management files.</span></span>
<span data-ttu-id="c100c-136">A vevői számlamodellhez saját konfigurációt fog létrehozni, a Microsoft által biztosított konfiguráció alapján.</span><span class="sxs-lookup"><span data-stu-id="c100c-136">You will create our own configuration of the Customer invoice model deriving it from the configuration provided by Microsoft.</span></span> <span data-ttu-id="c100c-137">A konfiguráció használatával fogja megvalósítani a hozzáférést a dokumentumkezelési fájlokhoz, illetve elérhetővé tenni őket az elektronikus dokumentumok számára, amelyeket a modell alapján hoz létre.</span><span class="sxs-lookup"><span data-stu-id="c100c-137">You will use this configuration to implement access to the Document Management files and make them available for electronic documents that you will create based on this model.</span></span>  
1. <span data-ttu-id="c100c-138">A Konfiguráció létrehozása gombra kattintva megnyithatja a legördülő párbeszédablakot.</span><span class="sxs-lookup"><span data-stu-id="c100c-138">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="c100c-139">Az Új mezőbe írja be a következőt: „Származtatás innen: Vevői számlamodell, Microsoft”.</span><span class="sxs-lookup"><span data-stu-id="c100c-139">In the New field, enter 'Derive from Name: Customer invoice model, Microsoft'.</span></span>
3. <span data-ttu-id="c100c-140">A Név mezőbe írja be a „Vevői számlamodell (egyéni)” szöveget.</span><span class="sxs-lookup"><span data-stu-id="c100c-140">In the Name field, type 'Customer invoice model (custom)'.</span></span>
4. <span data-ttu-id="c100c-141">Kattintson a Konfiguráció létrehozása lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="c100c-141">Click Create configuration.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]