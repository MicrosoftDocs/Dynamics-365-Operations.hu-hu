---
title: Több jogi entitásra kiterjedő személyzeti (HR) paraméterek beállítása
description: A több vállalatra kiterjedő rekordokhoz, mint például a Pozíció rekordok, megosztott paramétereket kell megadnia. A cikk ismerteti a jogi személyek közötti emberi erőforrás-paraméterek beállítását.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmSharedParameters
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: 5bd9684b8d5a5847ac212f2ff5214a6bcc3326fd
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897050"
---
# <a name="set-up-human-resources-hr-parameters-across-legal-entities"></a><span data-ttu-id="8b9ef-104">Több jogi entitásra kiterjedő személyzeti (HR) paraméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="8b9ef-104">Set up Human resources (HR) parameters across legal entities</span></span>

<span data-ttu-id="8b9ef-105">A több vállalatra kiterjedő rekordokhoz, mint például a Pozíció rekordok, megosztott paramétereket kell megadnia.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-105">You must set up shared parameters for records that are shared across companies, such as Position records.</span></span> <span data-ttu-id="8b9ef-106">A cikk ismerteti a jogi személyek közötti emberi erőforrás-paraméterek beállítását.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-106">This article explains how to set up Human resources parameters across legal entities.</span></span>

<span data-ttu-id="8b9ef-107">Bizonyos típusú bejegyzések, például a Beosztás bejegyzések több vállalatra is kiterjednek.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-107">Some types of records, such as Position records, are shared across companies.</span></span> <span data-ttu-id="8b9ef-108">Ezen bejegyzésekhez megosztott paramétereket kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-108">For these records, you must set up shared parameters.</span></span> <span data-ttu-id="8b9ef-109">Például a több jogi személyre kiterjedő emberi erőforrásokkal kapcsolatos paraméterek beállításához, használja az **Emberi erőforrások megosztott paraméterei** oldalt.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-109">For example, you use the **Human resources shared parameters** page to set up Human resources parameters across legal entities.</span></span> 

<span data-ttu-id="8b9ef-110">Az **Emberi erőforrások megosztott paraméterei** oldalon a paraméterek a funkcióik alapján vannak területileg elkülönítve.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-110">On the **Human resources shared parameters** page, parameters are grouped into areas, based on their functionality.</span></span> 

### <a name="previously-released-functionality"></a><span data-ttu-id="8b9ef-111">Korábban kiadott funkciók</span><span class="sxs-lookup"><span data-stu-id="8b9ef-111">Previously released functionality</span></span>
<span data-ttu-id="8b9ef-112">Az **Azonosító** ki kell választani az oldalon felsorolt azonosítószámokat képviselő azonosítótípusokat.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-112">On the **Identification** tab, you must select the identification types that represent the identification numbers that are listed on the page.</span></span> <span data-ttu-id="8b9ef-113">Dolgozók azonosító adatainak megadása előtt azonosítási típusokat kell beállítania.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-113">You must set up identification types before you can enter identification information for workers.</span></span> <span data-ttu-id="8b9ef-114">A TAJ-számmal, a nemzeti azonosítóval, a bevándorlási azonosítószámmal és a személyi azonosító kóddal kapcsolatos adatokat az **Azonosítótípus** oldalon lehet karbantartani.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-114">Information about the Social Security number, national ID number, alien ID number, and personal ID code is maintained on the **Identification type** page.</span></span> <span data-ttu-id="8b9ef-115">Egy új azonosítótípus létrehozásához vagy a már létezők felülvizsgálatához kattintson az **Személyzetkezelés** &gt; **Hivatkozások** &gt; **Beállítás** &gt; **Azonosítótípusok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-115">To define a new identification type or review the list of existing types, click **Personnel management** &gt; **Links tab** &gt; **Setup** &gt; **Identification types**.</span></span> <span data-ttu-id="8b9ef-116">Egy egyszerű kódot és leírást adhat meg.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-116">You can enter a simple code and description.</span></span> 

### <a name="if-youre-using-dynamics-365-talent"></a><span data-ttu-id="8b9ef-117">A Dynamics 365 Talent használata esetén</span><span class="sxs-lookup"><span data-stu-id="8b9ef-117">If you're using Dynamics 365 Talent</span></span>
<span data-ttu-id="8b9ef-118">Az **Azonosító** ki kell választani az oldalon felsorolt azonosítószámokat képviselő azonosítótípusokat.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-118">On the **Identification** tab, you must select the identification types that represent the identification numbers that are listed on the page.</span></span> <span data-ttu-id="8b9ef-119">Dolgozók azonosító adatainak megadása előtt azonosítási típusokat kell beállítania.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-119">You must set up identification types before you can enter identification information for workers.</span></span> <span data-ttu-id="8b9ef-120">A TAJ-számmal, a nemzeti azonosítóval, a bevándorlási azonosítószámmal és a személyi azonosító kóddal kapcsolatos adatokat az **Azonosítótípus** oldalon lehet karbantartani.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-120">Information about the Social Security number, national ID number, alien ID number, and personal ID code is maintained on the **Identification type** page.</span></span> <span data-ttu-id="8b9ef-121">Egy új azonosítótípus létrehozásához vagy a már létezők felülvizsgálatához kattintson az **Emberi erőforrások** &gt; **Beállítás** &gt; **Azonosítótípusok** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-121">To define a new identification type or review the list of existing types, click **Human resources** &gt; **Setup** &gt; **Identification types**.</span></span> <span data-ttu-id="8b9ef-122">Egy egyszerű kódot és leírást adhat meg.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-122">You can enter a simple code and description.</span></span> 

<span data-ttu-id="8b9ef-123">A **Számsorozatok** lapon kiválaszthatja a következő bejegyzésekhez használt számsorozatokat: személyzeti szám, beosztás, felhasználói kérelem azonosítója, I-9 dokumentum, pályázó, vitafórum, juttatásazonosító és személyzeti művelet (ha engedélyezve van ez a bejegyzéstípus).</span><span class="sxs-lookup"><span data-stu-id="8b9ef-123">On the **Number sequences** tab, you can select the number sequences that are used for the following records: Personnel number, Position, User request ID, I-9 document, Applicant, Discussion, Benefit ID, and Personnel action (if this record type is enabled).</span></span> <span data-ttu-id="8b9ef-124">A számsorozat-hivatkozások és a kódok fenntartásához használja a **Számsorozatok** listalapot.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-124">To maintain number sequence references and codes, use the **Number sequences** list page.</span></span> <span data-ttu-id="8b9ef-125">Az oldal megtalálásához használja az oldalkeresési funkciót.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-125">To find this page, use the page search feature.</span></span> 

<span data-ttu-id="8b9ef-126">A **Beosztások** lapon adhatja meg hogy alapértelmezés szeriont elérhetők-e új beosztásokhoz hozzárendeléshez:</span><span class="sxs-lookup"><span data-stu-id="8b9ef-126">On the **Positions** tab, indicate whether new positions are available for assignment by default:</span></span>

-   <span data-ttu-id="8b9ef-127">**Mindig** – Hozzárendelheti a dolgozókat az új beosztásokhoz, amikor beosztásokat hoz létre.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-127">**Always** – You can assign workers to new positions when positions are created.</span></span> <span data-ttu-id="8b9ef-128">Beosztások létrehozásakor az **Elérhető hozzárendeléshez** dátum és az idő az **Általános** lapon, a **Beosztás** oldalon automatikusan a létrehozási dátum és idő lesz.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-128">When positions are created, the **Available for assignment** date and time on the **General** tab of the **Position** page are automatically set to the creation date and time.</span></span>
-   <span data-ttu-id="8b9ef-129">**Soha** – Nem rendelheti hozzá a dolgozókat az új beosztásokhoz, amikor beosztásokat hoz létre.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-129">**Never** – You can't assign workers to new positions when positions are created.</span></span> <span data-ttu-id="8b9ef-130">Ha ezt a lehetőséget választja, akkor meg kell nyitnia a **Beosztás** oldalt minden új beosztásre vonatkozóan, ahogy elérhetővé válik, és adja meg az **Általános lapon** az **Elérhető hozzárendeléshez** dátumot a dolgozó-hozzárendelés engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="8b9ef-130">If you select this option, you must open the **Position** page for each new position as it becomes available, and then, on the **General** tab, enter the **Available for assignment** date to enable worker assignment.</span></span>


<a name="additional-resources"></a><span data-ttu-id="8b9ef-131">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8b9ef-131">Additional resources</span></span>
--------

[<span data-ttu-id="8b9ef-132">Vállalatfüggő személyzeti (HR) paraméterek beállítása</span><span class="sxs-lookup"><span data-stu-id="8b9ef-132">Set up company-specific Human resources (HR) parameters</span></span>](set-up-company-specific-hr-parameters.md)



