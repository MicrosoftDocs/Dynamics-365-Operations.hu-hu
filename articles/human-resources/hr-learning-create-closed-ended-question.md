---
title: Eldöntendő kérdés létrehozása
description: A zárt kérdések lehetővé teszik, hogy válaszlehetőségeket kínáljon fel a válaszadók számára.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMAnswerCollection, KMAnswer, KMQuestion, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 65d77806498c3a710c00865ad27716f50796cdf5
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/04/2021
ms.locfileid: "5114956"
---
# <a name="create-a-closed-ended-question"></a><span data-ttu-id="d731e-103">Eldöntendő kérdés létrehozása</span><span class="sxs-lookup"><span data-stu-id="d731e-103">Create a closed ended question</span></span>



<span data-ttu-id="d731e-104">A zárt kérdések lehetővé teszik, hogy válaszlehetőségeket kínáljon fel a válaszadók számára.</span><span class="sxs-lookup"><span data-stu-id="d731e-104">Closed-ended questions allow you to provide options for the respondent to choose from.</span></span> <span data-ttu-id="d731e-105">Először létre kell hoznia a Válaszcsoportot a válaszokkal, majd létre kell hoznia a válaszcsoportot használó kérdést.</span><span class="sxs-lookup"><span data-stu-id="d731e-105">First, you need to create the Answer group with the answers, then create the question that will use the answer group.</span></span> <span data-ttu-id="d731e-106">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="d731e-106">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-an-answer-group"></a><span data-ttu-id="d731e-107">Válaszcsoport létrehozása</span><span class="sxs-lookup"><span data-stu-id="d731e-107">Create an answer group</span></span>
1. <span data-ttu-id="d731e-108">Ugorjon a Kérdőív > Tervezés > Válaszcsoportok lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d731e-108">Go to Questionnaire > Design > Answer groups.</span></span>
2. <span data-ttu-id="d731e-109">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d731e-109">Click New.</span></span>
3. <span data-ttu-id="d731e-110">Írjon be egy értéket az Válaszcsoport mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d731e-110">In the Answer group field, type a value.</span></span>
4. <span data-ttu-id="d731e-111">A Leírás mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d731e-111">In the Description field, type a value.</span></span>
    * <span data-ttu-id="d731e-112">Használja a Véletlenszerűsítés funkciót, hogy minden alkalommal véletlenszerű sorrendben helyezze el a válaszokat, ha a válaszcsoportot felhasználják egy kérdéshez.</span><span class="sxs-lookup"><span data-stu-id="d731e-112">Use the Randomize functionality to randomly place the answers in a different order each time the answer group is used for a question.</span></span>  
5. <span data-ttu-id="d731e-113">Kattintson a Válasz lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d731e-113">Click Answer.</span></span>
6. <span data-ttu-id="d731e-114">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d731e-114">Click New.</span></span>
    * <span data-ttu-id="d731e-115">Ha a Véletlenszerűsítés nincs kiválasztva a Válaszcsoport számára a sorszám vezérli a válaszok megjelenítésének sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="d731e-115">Sequence number controls the order in which the answers are displayed, unless Randomize is selected for the Answer group.</span></span>  
    * <span data-ttu-id="d731e-116">A válaszokhoz pontok rendelhetőek a kérdőív értékeléséhez.</span><span class="sxs-lookup"><span data-stu-id="d731e-116">Points can be awarded to answers for use in scoring the questionnaire.</span></span>  
7. <span data-ttu-id="d731e-117">A Pontok mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="d731e-117">In the Points field, enter a number.</span></span>
    * <span data-ttu-id="d731e-118">A helyes válasz megjelölhető, hogy jelezze melyik az.</span><span class="sxs-lookup"><span data-stu-id="d731e-118">The correct answer can be marked to indicate that the selected answer is the correct one.</span></span> <span data-ttu-id="d731e-119">Ez használható a kérdőív pontozására.</span><span class="sxs-lookup"><span data-stu-id="d731e-119">This can be used for scoring the questionnaire.</span></span>  
8. <span data-ttu-id="d731e-120">A Válaszok mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d731e-120">In the Answer field, type a value.</span></span>
    * <span data-ttu-id="d731e-121">Folytassa a válaszkiválasztási opciók létrehozását a válaszcsoport számára.</span><span class="sxs-lookup"><span data-stu-id="d731e-121">Continue to create answer selection options for the answer group.</span></span>  
9. <span data-ttu-id="d731e-122">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d731e-122">Click New.</span></span>
10. <span data-ttu-id="d731e-123">A Pontok mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="d731e-123">In the Points field, enter a number.</span></span>
11. <span data-ttu-id="d731e-124">A Válaszok mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d731e-124">In the Answer field, type a value.</span></span>
12. <span data-ttu-id="d731e-125">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="d731e-125">Click New.</span></span>
13. <span data-ttu-id="d731e-126">A Pontok mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="d731e-126">In the Points field, enter a number.</span></span>
14. <span data-ttu-id="d731e-127">A Válaszok mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d731e-127">In the Answer field, type a value.</span></span>
15. <span data-ttu-id="d731e-128">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="d731e-128">Click New.</span></span>
16. <span data-ttu-id="d731e-129">A Pontok mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="d731e-129">In the Points field, enter a number.</span></span>
17. <span data-ttu-id="d731e-130">A Válaszok mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d731e-130">In the Answer field, type a value.</span></span>
18. <span data-ttu-id="d731e-131">Kattintson az Új elemre.</span><span class="sxs-lookup"><span data-stu-id="d731e-131">Click New.</span></span>
19. <span data-ttu-id="d731e-132">A Pontok mezőben adjon meg egy számot.</span><span class="sxs-lookup"><span data-stu-id="d731e-132">In the Points field, enter a number.</span></span>
20. <span data-ttu-id="d731e-133">A Válaszok mezőben adjon meg egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d731e-133">In the Answer field, type a value.</span></span>
21. <span data-ttu-id="d731e-134">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d731e-134">Close the page.</span></span>
22. <span data-ttu-id="d731e-135">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="d731e-135">Close the page.</span></span>

## <a name="create-the-question"></a><span data-ttu-id="d731e-136">Kérdés létrehozása</span><span class="sxs-lookup"><span data-stu-id="d731e-136">Create the question</span></span>
1. <span data-ttu-id="d731e-137">Ugorjon a Kérdőív > Tervezés > Kérdések lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d731e-137">Go to Questionnaire > Design > Questions.</span></span>
2. <span data-ttu-id="d731e-138">Kattintson az Új lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d731e-138">Click New.</span></span>
3. <span data-ttu-id="d731e-139">A Típus mező segítségével rendezze csoportba az összetartozó kérdéseket.</span><span class="sxs-lookup"><span data-stu-id="d731e-139">Use the Type field to group related questions together.</span></span>
    * <span data-ttu-id="d731e-140">Használhatja a Jelölőnégyzet, Alternatív gomb vagy Kombinált lista beviteli típusokat az eldöntendő kérdésekhez.</span><span class="sxs-lookup"><span data-stu-id="d731e-140">You can use input types of Check box, Alternative button, or Combo box for closed-ended questions.</span></span>  
4. <span data-ttu-id="d731e-141">Válasszon ki egy lehetőséget a Beviteli típus mezőben.</span><span class="sxs-lookup"><span data-stu-id="d731e-141">In the Input type field, select an option.</span></span>
5. <span data-ttu-id="d731e-142">A Válaszcsoportok mezőben adjon meg, vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="d731e-142">In the Answer group field, enter or select a value.</span></span>
6. <span data-ttu-id="d731e-143">Írjon be egy értéket a Szöveg mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d731e-143">In the Text field, type a value.</span></span>

