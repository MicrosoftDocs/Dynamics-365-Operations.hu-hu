---
title: A kérdőívek eredményeinek megtekintése és kiértékelése
description: Ez a cikk ismerteti, hogyan tudja megtekinteni és elemezni a kitöltött kérdőívek válaszait.
author: andreabichsel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMCollection, KMKnowledgeCollectorCollection, KMKnowledgeCollectorUserResults, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 17444
ms.assetid: 6570206a-b2c4-4025-8715-432fe6652b78
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 54530a8735cb8ce4b21688eae86fda83035133ed
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464958"
---
# <a name="view-and-evaluate-the-results-of-questionnaires"></a><span data-ttu-id="b9541-103">A kérdőívek eredményeinek megtekintése és kiértékelése</span><span class="sxs-lookup"><span data-stu-id="b9541-103">View and evaluate the results of questionnaires</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="b9541-104">Ez a cikk ismerteti, hogyan tudja megtekinteni és elemezni a kitöltött kérdőívek válaszait.</span><span class="sxs-lookup"><span data-stu-id="b9541-104">This article explains how you can view and evaluate the results of questionnaires that respondents complete.</span></span> 

<span data-ttu-id="b9541-105">Ha a válaszadók kitöltötték a kérdőívet, megtekintheti, valamint kiértékelheti a kérdőív eredményét az alábbi módokon:</span><span class="sxs-lookup"><span data-stu-id="b9541-105">After respondents complete a questionnaire, you can view and evaluate the questionnaire results in the following ways:</span></span>

-   <span data-ttu-id="b9541-106">**Befejezett válaszmunkamenetek** – A válaszadók által kitöltött kérdőívek részleteinek megtekintése, valamint a válaszok és elért pontok összesítésére szolgáló jelentés létrehozása.</span><span class="sxs-lookup"><span data-stu-id="b9541-106">**Completed answer sessions** – View details about the questionnaires that respondents have completed, and generate reports to summarize answers and any points that were earned.</span></span>
-   <span data-ttu-id="b9541-107">**Eredmény csoportok** – A kérdőív eredménycsoportjainak és statisztikájának megtekintése.</span><span class="sxs-lookup"><span data-stu-id="b9541-107">**Result groups** – View result group details and statistics for questionnaires.</span></span> <span data-ttu-id="b9541-108">Az eredménycsoport statisztikája létrehozható a kérdőív egyetlen válaszmunkamenetéhez, illetve az összes válaszmunkamenethez.</span><span class="sxs-lookup"><span data-stu-id="b9541-108">Result group statistics can be generated for either a single answer session  of a questionnaire or all answer sessions.</span></span>
-   <span data-ttu-id="b9541-109">**Kérdőív-statisztika** – A válaszadók bizonyos csoportjához tartozó statisztika kiszámítási feltételeinek megadása.</span><span class="sxs-lookup"><span data-stu-id="b9541-109">**Questionnaire statistics** – Specify criteria to calculate statistics for a specific group of respondents.</span></span>

<span data-ttu-id="b9541-110">Létrehozhat az eredmények megtekintéséhez személy, válaszmunkamenet vagy eredménycsoport alapján rendezett jelentéseket.</span><span class="sxs-lookup"><span data-stu-id="b9541-110">You can also generate various reports to view results that are sorted by person, answer session, or result group.</span></span> <span data-ttu-id="b9541-111">Az alábbi jelentések érhetőek el a kitöltött kérdőívekhez:</span><span class="sxs-lookup"><span data-stu-id="b9541-111">The following reports that are related to completed questionnaires are available:</span></span>

-   <span data-ttu-id="b9541-112">Válaszok</span><span class="sxs-lookup"><span data-stu-id="b9541-112">Answers</span></span>
-   <span data-ttu-id="b9541-113">Válaszok kérdőívenként</span><span class="sxs-lookup"><span data-stu-id="b9541-113">Answers per questionnaire</span></span>
-   <span data-ttu-id="b9541-114">Válaszok személyenként</span><span class="sxs-lookup"><span data-stu-id="b9541-114">Answers per person</span></span>
-   <span data-ttu-id="b9541-115">Visszajelzés elemzése</span><span class="sxs-lookup"><span data-stu-id="b9541-115">Feedback analysis</span></span>

## <a name="answer-session-results"></a><span data-ttu-id="b9541-116">Válaszmunkamenet eredményei</span><span class="sxs-lookup"><span data-stu-id="b9541-116">Answer session results</span></span>

<span data-ttu-id="b9541-117">Miután a válaszadók kitöltötték a kérdőívet, megtekintheti a befejezett válaszmunkamenetek eredményeit.</span><span class="sxs-lookup"><span data-stu-id="b9541-117">After respondents complete a questionnaire, you can view the results of the completed answer sessions.</span></span> <span data-ttu-id="b9541-118">A válaszmunkamenet egy adott felhasználó válasza a kérdőívre.</span><span class="sxs-lookup"><span data-stu-id="b9541-118">An answer session is one user’s response to a questionnaire.</span></span> <span data-ttu-id="b9541-119">A **Válaszok** oldalon megtekintheti a befejezett válaszmunkamenetekhez kapcsolódó részleteket.</span><span class="sxs-lookup"><span data-stu-id="b9541-119">You can view details about completed answer sessions on the **Answers** page.</span></span> <span data-ttu-id="b9541-120">Az a válaszmunkamenet, ami a **Válaszok** oldalon megjelenik, különböző szűrőkkel van ellátva, attól függően, hogy miként nyitja meg az oldalt.</span><span class="sxs-lookup"><span data-stu-id="b9541-120">The answer sessions that are included on the **Answers** page are filtered in various ways, depending on how you open the page:</span></span>

-   <span data-ttu-id="b9541-121">Összes kérdőív</span><span class="sxs-lookup"><span data-stu-id="b9541-121">All questionnaires</span></span>
-   <span data-ttu-id="b9541-122">Adott kérdőív</span><span class="sxs-lookup"><span data-stu-id="b9541-122">A specific questionnaire</span></span>
-   <span data-ttu-id="b9541-123">Adott személy</span><span class="sxs-lookup"><span data-stu-id="b9541-123">A specific person</span></span>

<span data-ttu-id="b9541-124">A **Válaszok** oldalon megtekinthet részleteket a válaszokról, az elért pontokról, a válaszadó minden eredménycsoportban adott válaszairól, valamint a kérdőívben használt kérdéshierarchiáról, ha volt használva kérdéshierarchia.</span><span class="sxs-lookup"><span data-stu-id="b9541-124">From the **Answers** page, you can view details about answers, points that were earned, a respondent’s responses in each result group, and the question hierarchy that was used on the selected questionnaire, if a question hierarchy was used.</span></span> <span data-ttu-id="b9541-125">Létrehozhatja és kinyomtathatja az alábbi jelentéseket:</span><span class="sxs-lookup"><span data-stu-id="b9541-125">You can also generate and print the following reports:</span></span>

-   <span data-ttu-id="b9541-126">**Eredmény jelentés** – Ez a jelentés grafikusan ábrázolja az eredménycsoportonként elért pontjait a kiválasztott válaszmunkamenetnek.</span><span class="sxs-lookup"><span data-stu-id="b9541-126">**Results report** – This report shows a graphical representation of the points that were earned per result group for the selected answer session.</span></span>
-   <span data-ttu-id="b9541-127">**Válasz jelentés** – Ez a jelentés a válaszadó kérdésenkénti válaszait mutatja.</span><span class="sxs-lookup"><span data-stu-id="b9541-127">**Answer report** – This report shows the answers that the respondent selected for each question on the questionnaire.</span></span>
-   <span data-ttu-id="b9541-128">**Helytelen válaszok** – Ez a jelentés a válaszadó által adott helytelen válaszokhoz kapcsolódó információkat mutatja.</span><span class="sxs-lookup"><span data-stu-id="b9541-128">**Incorrect answers** – This report shows information that is related to the incorrect answers that the respondent selected.</span></span>

> [!NOTE]
> <span data-ttu-id="b9541-129">Az **Eredmények** jelentés csak akkor érhető el, ha válaszcsoportokat használt a kérdőívben, valamint ha kiválasztotta az **Eredményeket bemutató oldal** lehetőséget a **Kérdőívek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="b9541-129">The **Results** report is available only if you use results groups on the questionnaire, and if you selected **Results page** on the **Questionnaires** page.</span></span> <span data-ttu-id="b9541-130">A **Válasz** jelentés és a **Helytelen válaszok** jelentés csak akkor érhető el, ha kiválasztotta a **Válaszjelentés** lehetőséget a **Kérdőívek** oldalon.</span><span class="sxs-lookup"><span data-stu-id="b9541-130">The **Answer** report and the **Incorrect answers** report are available only if you selected **Answer report** on the **Questionnaires** page.</span></span>

## <a name="questionnaire-statistics"></a><span data-ttu-id="b9541-131">Kérdőív-statisztika</span><span class="sxs-lookup"><span data-stu-id="b9541-131">Questionnaire statistics</span></span>

<span data-ttu-id="b9541-132">Használhat kérdőív statisztikákat a kitöltött kérdőívek eredményének kiértékeléséhez, az Ön által megszabott számítások alapján.</span><span class="sxs-lookup"><span data-stu-id="b9541-132">You can use questionnaire statistics to analyze the results of a completed questionnaire, based on calculations that you define.</span></span> <span data-ttu-id="b9541-133">A számítások megadásához az alábbi feladatokat kell elvégeznie:</span><span class="sxs-lookup"><span data-stu-id="b9541-133">To define calculations, you must complete the following tasks:</span></span>

-   <span data-ttu-id="b9541-134">Válassza ki a statisztikák megjelenítésének és kiszámításának feltételeit.</span><span class="sxs-lookup"><span data-stu-id="b9541-134">Select criteria to calculate and display the statistics.</span></span>
    -   <span data-ttu-id="b9541-135">Megjelenítheti a kérdőív, a kérdések, a kérdés sorok, illetve az eredménycsoportok statisztikáit.</span><span class="sxs-lookup"><span data-stu-id="b9541-135">You can show statistics by questionnaire, questions, question rows, or results groups.</span></span>
    -   <span data-ttu-id="b9541-136">Válassza ki az eredmények megtekintéséhez használatos diagram típusát.</span><span class="sxs-lookup"><span data-stu-id="b9541-136">Select the type of chart that will be used when you view results.</span></span>
    -   <span data-ttu-id="b9541-137">Válassza ki a személyek típusát, akik válaszát bele szeretné foglalni a statisztikába, mint például alkalmazottak, kapcsolattartók vagy pályázók.</span><span class="sxs-lookup"><span data-stu-id="b9541-137">Select the types of people from the network, such as employees, contact persons, or applicants, to include answers for.</span></span> <span data-ttu-id="b9541-138">Olyan kérdőívek válaszait is belefoglalhat a statisztikába, amiket névtelenül töltöttek ki.</span><span class="sxs-lookup"><span data-stu-id="b9541-138">You can also include answers from questionnaires that were completed anonymously.</span></span>
    -   <span data-ttu-id="b9541-139">Az eredmények kiértékeléséhez állítsa be kor vagy szolgálati idő alapján az intervallumokat.</span><span class="sxs-lookup"><span data-stu-id="b9541-139">Set up intervals that are based on age or seniority to analyze results.</span></span>
-   <span data-ttu-id="b9541-140">Válassza ki, vagy ellenőrizze meg a statisztikák tárgyának finomítására szolgáló beállításokat.</span><span class="sxs-lookup"><span data-stu-id="b9541-140">Select or verify settings that refine the subject of the statistics.</span></span> <span data-ttu-id="b9541-141">Például irányítószám megadásával az adott földrajzi terület válaszadóinak eredményeit elemezheti.</span><span class="sxs-lookup"><span data-stu-id="b9541-141">For example, by selecting a ZIP Code or postal code, you can analyze results for all respondents within a specific geographic area.</span></span>
-   <span data-ttu-id="b9541-142">Válassza ki, vagy ellenőrizze az eredmények kiértékelésének feltételeit, válaszadó vagy a kérdői jellemzője alapján.</span><span class="sxs-lookup"><span data-stu-id="b9541-142">Select or verify criteria to analyze results by respondent or questionnaire characteristics.</span></span> <span data-ttu-id="b9541-143">Például az **Irányítószám** kiválasztásával kiértékelheti a válaszadó helye és helyes válaszai közti korrelációt.</span><span class="sxs-lookup"><span data-stu-id="b9541-143">For example, by selecting **ZIP/postal code**, you can analyze the correlation between a respondent’s location and correct answers.</span></span>

<span data-ttu-id="b9541-144">A program menti a megadott beállításokat, így ezek az eredmények ismételt újraszámításakor felhasználhatók.</span><span class="sxs-lookup"><span data-stu-id="b9541-144">The settings that you define are saved and can be used to periodically recalculate results.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]