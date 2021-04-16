---
title: Eldöntendő kérdés létrehozása
description: A zárt kérdések lehetővé teszik, hogy válaszlehetőségeket kínáljon fel a válaszadók számára.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 41e12e6f35237ea125756b502d5cebed58c6bf55
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5790644"
---
# <a name="create-a-closed-ended-question"></a><span data-ttu-id="e3048-103">Eldöntendő kérdés létrehozása</span><span class="sxs-lookup"><span data-stu-id="e3048-103">Create a closed ended question</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



<span data-ttu-id="e3048-104">A zárt kérdések lehetővé teszik, hogy válaszlehetőségeket kínáljon fel a válaszadók számára.</span><span class="sxs-lookup"><span data-stu-id="e3048-104">Closed-ended questions allow you to provide options for the respondent to choose from.</span></span> <span data-ttu-id="e3048-105">Először létre kell hoznia a Válaszcsoportot a válaszokkal, majd létre kell hoznia a válaszcsoportot használó kérdést.</span><span class="sxs-lookup"><span data-stu-id="e3048-105">First, you need to create the Answer group with the answers, then create the question that will use the answer group.</span></span> <span data-ttu-id="e3048-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="e3048-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-an-answer-group"></a><span data-ttu-id="e3048-107">Válaszcsoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="e3048-107">Create an answer group</span></span>
1. <span data-ttu-id="e3048-108">Ugorjon a Kérdőív > Tervezés > Válaszcsoportok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e3048-108">Go to Questionnaire > Design > Answer groups.</span></span>
2. <span data-ttu-id="e3048-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e3048-109">Click New.</span></span>
3. <span data-ttu-id="e3048-110">Írjon be egy értéket az Válaszcsoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e3048-110">In the Answer group field, type a value.</span></span>
4. <span data-ttu-id="e3048-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e3048-111">In the Description field, type a value.</span></span>
    * <span data-ttu-id="e3048-112">Használja a Véletlenszerűsítés funkciót, hogy minden alkalommal véletlenszerű sorrendben helyezze el a válaszokat, ha a válaszcsoportot felhasználják egy kérdéshez.</span><span class="sxs-lookup"><span data-stu-id="e3048-112">Use the Randomize functionality to randomly place the answers in a different order each time the answer group is used for a question.</span></span>  
5. <span data-ttu-id="e3048-113">Kattintson a Válasz lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e3048-113">Click Answer.</span></span>
6. <span data-ttu-id="e3048-114">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e3048-114">Click New.</span></span>
    * <span data-ttu-id="e3048-115">Ha a Véletlenszerűsítés nincs kiválasztva a Válaszcsoport számára a sorszám vezérli a válaszok megjelenítésének sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="e3048-115">Sequence number controls the order in which the answers are displayed, unless Randomize is selected for the Answer group.</span></span>  
    * <span data-ttu-id="e3048-116">A válaszokhoz pontok rendelhetőek a kérdőív értékeléséhez.</span><span class="sxs-lookup"><span data-stu-id="e3048-116">Points can be awarded to answers for use in scoring the questionnaire.</span></span>  
7. <span data-ttu-id="e3048-117">A Pontok mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="e3048-117">In the Points field, enter a number.</span></span>
    * <span data-ttu-id="e3048-118">A helyes válasz megjelölhető, hogy jelezze melyik az.</span><span class="sxs-lookup"><span data-stu-id="e3048-118">The correct answer can be marked to indicate that the selected answer is the correct one.</span></span> <span data-ttu-id="e3048-119">Ez használható a kérdőív pontozására.</span><span class="sxs-lookup"><span data-stu-id="e3048-119">This can be used for scoring the questionnaire.</span></span>  
8. <span data-ttu-id="e3048-120">A Válaszok mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e3048-120">In the Answer field, type a value.</span></span>
    * <span data-ttu-id="e3048-121">Folytassa a válaszkiválasztási opciók létrehozását a válaszcsoport számára.</span><span class="sxs-lookup"><span data-stu-id="e3048-121">Continue to create answer selection options for the answer group.</span></span>  
9. <span data-ttu-id="e3048-122">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e3048-122">Click New.</span></span>
10. <span data-ttu-id="e3048-123">A Pontok mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="e3048-123">In the Points field, enter a number.</span></span>
11. <span data-ttu-id="e3048-124">A Válaszok mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e3048-124">In the Answer field, type a value.</span></span>
12. <span data-ttu-id="e3048-125">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="e3048-125">Click New.</span></span>
13. <span data-ttu-id="e3048-126">A Pontok mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="e3048-126">In the Points field, enter a number.</span></span>
14. <span data-ttu-id="e3048-127">A Válaszok mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e3048-127">In the Answer field, type a value.</span></span>
15. <span data-ttu-id="e3048-128">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="e3048-128">Click New.</span></span>
16. <span data-ttu-id="e3048-129">A Pontok mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="e3048-129">In the Points field, enter a number.</span></span>
17. <span data-ttu-id="e3048-130">A Válaszok mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e3048-130">In the Answer field, type a value.</span></span>
18. <span data-ttu-id="e3048-131">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="e3048-131">Click New.</span></span>
19. <span data-ttu-id="e3048-132">A Pontok mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="e3048-132">In the Points field, enter a number.</span></span>
20. <span data-ttu-id="e3048-133">A Válaszok mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e3048-133">In the Answer field, type a value.</span></span>
21. <span data-ttu-id="e3048-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e3048-134">Close the page.</span></span>
22. <span data-ttu-id="e3048-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="e3048-135">Close the page.</span></span>

## <a name="create-the-question"></a><span data-ttu-id="e3048-136">Kérdés létrehozása</span><span class="sxs-lookup"><span data-stu-id="e3048-136">Create the question</span></span>
1. <span data-ttu-id="e3048-137">Ugorjon a Kérdőív > Tervezés > Kérdések lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e3048-137">Go to Questionnaire > Design > Questions.</span></span>
2. <span data-ttu-id="e3048-138">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e3048-138">Click New.</span></span>
3. <span data-ttu-id="e3048-139">A Típus mező segítségével rendezze csoportba az összetartozó kérdéseket.</span><span class="sxs-lookup"><span data-stu-id="e3048-139">Use the Type field to group related questions together.</span></span>
    * <span data-ttu-id="e3048-140">Használhatja a Jelölőnégyzet, Alternatív gomb vagy Kombinált lista beviteli típusokat az eldöntendő kérdésekhez.</span><span class="sxs-lookup"><span data-stu-id="e3048-140">You can use input types of Check box, Alternative button, or Combo box for closed-ended questions.</span></span>  
4. <span data-ttu-id="e3048-141">Válasszon ki egy lehetőséget a Beviteli típus mezőben.</span><span class="sxs-lookup"><span data-stu-id="e3048-141">In the Input type field, select an option.</span></span>
5. <span data-ttu-id="e3048-142">A Válaszcsoportok mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="e3048-142">In the Answer group field, enter or select a value.</span></span>
6. <span data-ttu-id="e3048-143">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e3048-143">In the Text field, type a value.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]