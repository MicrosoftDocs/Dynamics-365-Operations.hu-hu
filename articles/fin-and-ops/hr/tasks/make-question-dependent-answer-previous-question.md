--- 
title: "A kérdések függővé tétele az előző kérdésre adott választól"
description: "A feltételes kérdések segítségével meghatározhatja, hogy ilyen további kérdések jelennek meg a válaszadónak az előző kérdésekre adott válaszai alapján."
author: ShylaThompson
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Talent
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: 3e0a6d63a266bf49764c8cdcfd407ff0733ea27c
ms.contentlocale: hu-hu
ms.lasthandoff: 08/09/2018

---
# <a name="make-questions-dependent-on-the-answer-of-the-previous-question"></a><span data-ttu-id="ab08b-103">A kérdések függővé tétele az előző kérdésre adott választól</span><span class="sxs-lookup"><span data-stu-id="ab08b-103">Make questions dependent on the answer of the previous question</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ab08b-104">A feltételes kérdések segítségével meghatározhatja, hogy ilyen további kérdések jelennek meg a válaszadónak az előző kérdésekre adott válaszai alapján.</span><span class="sxs-lookup"><span data-stu-id="ab08b-104">Conditional questions allow you to specify what follow-up question will be presented to a respondent, based on the answer to the preceding question.</span></span> <span data-ttu-id="ab08b-105">Például, ha megkérdezni hogy a „Kávét vagy a teát szereti-e” meghatározható egy logikus további kérdés az alapján, hogy a válaszadó a kávét vagy a teát választja-e.</span><span class="sxs-lookup"><span data-stu-id="ab08b-105">For example, if you ask "Do you prefer coffee or tea," a logical follow-up question can be determined depending on whether the respondent selects coffee or tea as their answer.</span></span> <span data-ttu-id="ab08b-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="ab08b-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="find-the-existing-questionnaire"></a><span data-ttu-id="ab08b-107">Meglévő kérdőív megkeresése</span><span class="sxs-lookup"><span data-stu-id="ab08b-107">Find the existing questionnaire</span></span>
1. <span data-ttu-id="ab08b-108">Ugorjon a Kérdőív > Tervezés > Kérdőívek lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab08b-108">Go to Questionnaire > Design > Questionnaires.</span></span>
2. <span data-ttu-id="ab08b-109">A listában válassza ki a WorkFH kérdőívet.</span><span class="sxs-lookup"><span data-stu-id="ab08b-109">In the list, select the WorkFH questionnaire.</span></span>

## <a name="add-all-questions-and-sub-questions-to-the-questionnaire"></a><span data-ttu-id="ab08b-110">Összes kérdés és alkérdés hozzáadása a Kérdőívhez</span><span class="sxs-lookup"><span data-stu-id="ab08b-110">Add all questions and sub-questions to the Questionnaire</span></span>
1. <span data-ttu-id="ab08b-111">Kattintson a Kérdések lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab08b-111">Click Questions.</span></span>
2. <span data-ttu-id="ab08b-112">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab08b-112">Click New.</span></span>
3. <span data-ttu-id="ab08b-113">A Kérdések mezőben válassza ki a 00016 számú kérdést.</span><span class="sxs-lookup"><span data-stu-id="ab08b-113">In the Question field, select question number 00016.</span></span>
4. <span data-ttu-id="ab08b-114">Keresse meg és jelölje ki a kívánt rekordot a listán.</span><span class="sxs-lookup"><span data-stu-id="ab08b-114">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="ab08b-115">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="ab08b-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="ab08b-116">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ab08b-116">Click Save.</span></span>
7. <span data-ttu-id="ab08b-117">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="ab08b-117">Close the page.</span></span>

## <a name="set-the-questionnaire-sequence-to-conditional-and-make-the-question-dependent-on-the-appropriate-question"></a><span data-ttu-id="ab08b-118">Kérdőív sorrendjének Feltételesre állítása, és a kérdés függővé tétele a megfelelő kérdéstől</span><span class="sxs-lookup"><span data-stu-id="ab08b-118">Set the Questionnaire Sequence to Conditional and make the question dependent on the appropriate question</span></span>
1. <span data-ttu-id="ab08b-119">Kattintson a Szerkesztés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab08b-119">Click Edit.</span></span>
2. <span data-ttu-id="ab08b-120">Bontsa ki a Beállítások szakaszt.</span><span class="sxs-lookup"><span data-stu-id="ab08b-120">Expand the Setup section.</span></span>
3. <span data-ttu-id="ab08b-121">A Kérdések sorrendje mezőben válassza ki a „Feltételes” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab08b-121">In the Question order field, select 'Conditional'.</span></span>
4. <span data-ttu-id="ab08b-122">Kattintson a Feltételes kérdés lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="ab08b-122">Click Conditional question.</span></span>
5. <span data-ttu-id="ab08b-123">A fanézetben jelölje ki a „Kérdések\Magyarázza el, hogy miért válaszolt így az előző kérdésre?” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab08b-123">In the tree, select 'Questions\Explain why you answered the previous question the way you did?'.</span></span>
6. <span data-ttu-id="ab08b-124">Az Elsődleges kérdések mezőben válassza ki a 00009 számú kérdést.</span><span class="sxs-lookup"><span data-stu-id="ab08b-124">In the Primary question field, select question 00009</span></span>
7. <span data-ttu-id="ab08b-125">A listában kattintson a kijelölt sorban lévő hivatkozásra.</span><span class="sxs-lookup"><span data-stu-id="ab08b-125">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="ab08b-126">A Válasz mezőben adja meg azon válaszlehetőség válaszsorrend-azonosítóját, amelytől függő szeretné tenni a kérdést.</span><span class="sxs-lookup"><span data-stu-id="ab08b-126">In the Answer field, enter the answer sequence ID of the answer option you want to make the question dependent on.</span></span> <span data-ttu-id="ab08b-127">Például adja meg az 1 értéket az első válaszlehetőséghez.</span><span class="sxs-lookup"><span data-stu-id="ab08b-127">For example, enter 1 for the first answer option.</span></span>
9. <span data-ttu-id="ab08b-128">Kattintson a Mentés gombra.</span><span class="sxs-lookup"><span data-stu-id="ab08b-128">Click Save.</span></span>
10. <span data-ttu-id="ab08b-129">A fanézetben válassza ki a „Kérdések\Rendesen megfizetik a munkámat” lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="ab08b-129">In the tree, select 'Questions\I am paid fairly for the work I do.'.</span></span>
    * <span data-ttu-id="ab08b-130">Vegye figyelembe, hogy a kérdésfa frissül a függőségek jelzése érdekében.</span><span class="sxs-lookup"><span data-stu-id="ab08b-130">Note that the question tree updated to show the dependency.</span></span>  


