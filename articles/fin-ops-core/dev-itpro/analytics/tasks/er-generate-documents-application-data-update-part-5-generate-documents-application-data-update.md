---
title: Alkalmazásadatokkal rendelkező dokumentumok létrehozása
description: 'Az eljárás lépéseinek elvégzéséhez először hajtsa végre az „ER – Dokumentumok létrehozása alkalmazásadat-frissítéssel (4. rész: Formátum módosítása)” eljárást.'
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dcc00bba4aa92ad089bcab83ee22f79c21ccc252
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141856"
---
# <a name="generate-documents-that-have-application-data"></a><span data-ttu-id="40ceb-103">Alkalmazásadatokkal rendelkező dokumentumok létrehozása</span><span class="sxs-lookup"><span data-stu-id="40ceb-103">Generate documents that have application data</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="40ceb-104">Az eljárás lépéseinek elvégzéséhez először hajtsa végre az „ER – Dokumentumok létrehozása alkalmazásadat-frissítéssel (4. rész: Formátum módosítása)” eljárást.</span><span class="sxs-lookup"><span data-stu-id="40ceb-104">To complete the steps in this procedure, you must first complete the procedure, "ER Generate documents with application data update (Part 4: Modify format)".</span></span>



<span data-ttu-id="40ceb-105">Az eljárás lépései az elektronikus dokumentumot létrehozó elektronikus jelentési (ER) konfigurációk megtervezését és az alkalmazásadatok frissítését mutatják be.</span><span class="sxs-lookup"><span data-stu-id="40ceb-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="40ceb-106">Ebben az eljárásban végrehajtja az ER-formátumkonfigurációt az Intrastat-jelentés létrehozása, illetve az alkalmazásadatoknak a jelentési folyamat részleteinek archiválásához szükséges frissítése céljából.</span><span class="sxs-lookup"><span data-stu-id="40ceb-106">In this procedure, you execute the ER format configuration to generate the Intrastat report and update application data for archiving details of the reporting process.</span></span>



<span data-ttu-id="40ceb-107">Ez az eljárás a rendszergazda vagy az elektronikus jelentések fejlesztője szerepkör rendelkező felhasználók számára készült.</span><span class="sxs-lookup"><span data-stu-id="40ceb-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="40ceb-108">A lépések a DEMF-adathalmazzal hajthatók végre.</span><span class="sxs-lookup"><span data-stu-id="40ceb-108">These steps can be completed using the DEMF dataset.</span></span> <span data-ttu-id="40ceb-109">Mielőtt hozzálátna, győződjön meg arról, hogy a DEMF vállalat országfüggő környezete BEL (Belgium).</span><span class="sxs-lookup"><span data-stu-id="40ceb-109">Before you begin, make sure that the country context for the DEMF company is BEL (Belgium).</span></span>


## <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="40ceb-110">Külkereskedelmi paraméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="40ceb-110">Set up foreign trade parameters</span></span>
1. <span data-ttu-id="40ceb-111">Ugorjon az Adó > Beállítás > Külkereskedelmi > Külkereskedelmi paraméterek pontra.</span><span class="sxs-lookup"><span data-stu-id="40ceb-111">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
2. <span data-ttu-id="40ceb-112">Kattintson a Számsorozatok lapra.</span><span class="sxs-lookup"><span data-stu-id="40ceb-112">Click the Number sequences tab.</span></span>

    <span data-ttu-id="40ceb-113">Az Intrastat jelentési folyamat részleteinek archiválása során azonosítani kell a létrehozott archívumokat.</span><span class="sxs-lookup"><span data-stu-id="40ceb-113">Archiving details of Intrastat reporting process, we need to identify records of each archive we created.</span></span> <span data-ttu-id="40ceb-114">Ehhez egy speciális számsorozatot kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="40ceb-114">A special number sequence must be configured for that.</span></span>  

3. <span data-ttu-id="40ceb-115">Válassza ki az „Intrastat-archívum azonosítója” hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="40ceb-115">Select the 'Intrastat archive ID' reference.</span></span>
4. <span data-ttu-id="40ceb-116">Adjon meg egy értéket a Számsorozat kódja mezőben.</span><span class="sxs-lookup"><span data-stu-id="40ceb-116">In the Number sequence code field, type a value.</span></span>

    <span data-ttu-id="40ceb-117">A Számsorrend kódja mezőben adja meg vagy válassza ki a „Fore_2” értéket.</span><span class="sxs-lookup"><span data-stu-id="40ceb-117">In the 'Number sequence code' field, enter or select the value 'Fore_2'.</span></span>  

5. <span data-ttu-id="40ceb-118">ResolveChanges a számsorozat kódja.</span><span class="sxs-lookup"><span data-stu-id="40ceb-118">ResolveChanges the Number sequence code.</span></span>
6. <span data-ttu-id="40ceb-119">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="40ceb-119">Click Save.</span></span>
7. <span data-ttu-id="40ceb-120">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="40ceb-120">Close the page.</span></span>

## <a name="run-modified-er-format"></a><span data-ttu-id="40ceb-121">Módosított ER-formátum futtatása</span><span class="sxs-lookup"><span data-stu-id="40ceb-121">Run modified ER format</span></span>
1. <span data-ttu-id="40ceb-122">Nyissa meg a következőt: Szervezeti adminisztráció > Elektronikus jelentés > Konfigurációk.</span><span class="sxs-lookup"><span data-stu-id="40ceb-122">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="40ceb-123">A fastruktúrában bontsa ki az „Instrastat (model)” elemet.</span><span class="sxs-lookup"><span data-stu-id="40ceb-123">In the tree, expand 'Intrastat (model)'.</span></span>
3. <span data-ttu-id="40ceb-124">A fastruktúrában jelölje ki a következőt: „Intrastat (model)\Intrastat (format)”.</span><span class="sxs-lookup"><span data-stu-id="40ceb-124">In the tree, select 'Intrastat (model)\Intrastat (format)'.</span></span>
4. <span data-ttu-id="40ceb-125">Kattintson a Futtatásra.</span><span class="sxs-lookup"><span data-stu-id="40ceb-125">Click Run.</span></span>
5. <span data-ttu-id="40ceb-126">Az Enter fájlnévmezőbe írja be a következőt: intrastat2.xml.</span><span class="sxs-lookup"><span data-stu-id="40ceb-126">In the Enter file name field, type 'intrastat2.xml'.</span></span>
6. <span data-ttu-id="40ceb-127">Kattintson az OK gombra.</span><span class="sxs-lookup"><span data-stu-id="40ceb-127">Click OK.</span></span>

## <a name="review-er-format-executions-results"></a><span data-ttu-id="40ceb-128">ER-formátum végrehajtási eredményeinek áttekintése</span><span class="sxs-lookup"><span data-stu-id="40ceb-128">Review ER format execution's results</span></span>
<span data-ttu-id="40ceb-129">Tekintse át a létrehozott XML-fájlt.</span><span class="sxs-lookup"><span data-stu-id="40ceb-129">Review the generated XML file.</span></span>  
1. <span data-ttu-id="40ceb-130">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="40ceb-130">Close the page.</span></span>
2. <span data-ttu-id="40ceb-131">Ugorjon az Adó > Nyilatkozatok > Külkereskedelem > Intrastat pontra.</span><span class="sxs-lookup"><span data-stu-id="40ceb-131">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>

    <span data-ttu-id="40ceb-132">Nyissa meg azon Intrastat-tranzakciókat tartalmazó képernyőt, amelyek szerepelnek a létrehozott elektronikus dokumentumban.</span><span class="sxs-lookup"><span data-stu-id="40ceb-132">Open this form containing Intrastat transactions that have been included to the generated electronic document.</span></span>  

3. <span data-ttu-id="40ceb-133">Kattintson az Intrastat archívum elemre.</span><span class="sxs-lookup"><span data-stu-id="40ceb-133">Click Intrastat archive.</span></span>

    <span data-ttu-id="40ceb-134">Mivel a végrehajtott ER-formátum most az alkalmazásadatok módosításának beállításait tartalmazza, a rendszer archiválta a kitöltött Intrastat-jelentés részleteit.</span><span class="sxs-lookup"><span data-stu-id="40ceb-134">Since the executed ER format contains now settings for application data update, the details of the completed Intrastat reporting have been archived.</span></span> <span data-ttu-id="40ceb-135">Ezen a képernyőn megtekintheti a létrehozott archívum fejlécrekordját.</span><span class="sxs-lookup"><span data-stu-id="40ceb-135">In this form, you can see the header record of the created archive.</span></span>  

4. <span data-ttu-id="40ceb-136">Kattintson a Részletek gombra.</span><span class="sxs-lookup"><span data-stu-id="40ceb-136">Click Details.</span></span>

    <span data-ttu-id="40ceb-137">Ezen a képernyőn megtekintheti a létrehozott archívum részleteit.</span><span class="sxs-lookup"><span data-stu-id="40ceb-137">In this form, you can see the details for the created archive.</span></span>  

5. <span data-ttu-id="40ceb-138">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="40ceb-138">Close the page.</span></span>
6. <span data-ttu-id="40ceb-139">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="40ceb-139">Close the page.</span></span>
7. <span data-ttu-id="40ceb-140">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="40ceb-140">Close the page.</span></span>

