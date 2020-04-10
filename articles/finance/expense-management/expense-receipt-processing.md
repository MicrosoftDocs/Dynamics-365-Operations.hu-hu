---
title: Költség-visszaigazolások feldolgozása
description: Ez a témakör a nyugták optikai karakterfelismerésre (OCR) alapuló feldolgozásával kapcsolatban tartalmaz tájékoztatást. Ez a funkció azt a célt szolgálja, hogy javítsa a felhasználói élményt, amikor költségjelentéseket hoz létre a Microsoft Dynamics 365 Finance szolgáltatásban.
author: stsporen
manager: AnnBe
ms.date: 11/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: stsporen
ms.search.validFrom: 2019-11-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 49cdfeac8cda9f1ddd3aca61f902f00f30f3485b
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154040"
---
# <a name="expense-receipt-processing"></a><span data-ttu-id="5cc80-104">Költség a bevételezés feldolgozásakor</span><span class="sxs-lookup"><span data-stu-id="5cc80-104">Expense receipt processing</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


<span data-ttu-id="5cc80-105">A kiadások bevitelét a nyugták optikai karakterfelismerés (OCR) segítségével történő feldolgozása jobbá tette.</span><span class="sxs-lookup"><span data-stu-id="5cc80-105">Expense entry has been enhanced through the introduction of optical character recognition (OCR) processing for receipts.</span></span> <span data-ttu-id="5cc80-106">Ez a funkció azt a célt szolgálja, hogy javítsa a felhasználói élményt, amikor költségjelentéseket hoz létre.</span><span class="sxs-lookup"><span data-stu-id="5cc80-106">This feature is designed to improve the user experience when expense reports are created.</span></span>

## <a name="key-features"></a><span data-ttu-id="5cc80-107">Fő funkciók</span><span class="sxs-lookup"><span data-stu-id="5cc80-107">Key features</span></span>

- <span data-ttu-id="5cc80-108">A kereskedő neve, a dátum és a teljes összeg a nyugtából megállapítható.</span><span class="sxs-lookup"><span data-stu-id="5cc80-108">The merchant name, date, and total amount are extracted from receipts.</span></span>
- <span data-ttu-id="5cc80-109">A funkció megpróbálja egyeztetni a nem csatolt bevételeket a nem csatolt kiadási tranzakciókkal.</span><span class="sxs-lookup"><span data-stu-id="5cc80-109">The feature tries to match unattached receipts to unattached expense transactions.</span></span>
- <span data-ttu-id="5cc80-110">A felhasználók manuálisan megadott kiadási tranzakciókat hozhatnak létre a nyugtákból.</span><span class="sxs-lookup"><span data-stu-id="5cc80-110">Users can create manually entered expense transactions from receipts.</span></span>

## <a name="usage-examples"></a><span data-ttu-id="5cc80-111">Felhasználási példák</span><span class="sxs-lookup"><span data-stu-id="5cc80-111">Usage examples</span></span>

- <span data-ttu-id="5cc80-112">**Hitelkártya-adatokat tartalmazó nyugták automatikus csatolása költségjelentés létrehozásakor.**</span><span class="sxs-lookup"><span data-stu-id="5cc80-112">**Automatically attach receipts that include credit card transactions when an expense report is created.**</span></span>

    1. <span data-ttu-id="5cc80-113">Nyissa meg a **Költséggazdálkodás** munkaterületet.</span><span class="sxs-lookup"><span data-stu-id="5cc80-113">Open the **Expense management** workspace.</span></span>
    2. <span data-ttu-id="5cc80-114">A **Nyugták** lapon ellenőrizze, hogy vannak-e nem csatolt nyugták.</span><span class="sxs-lookup"><span data-stu-id="5cc80-114">On the **Receipts** tab, verify that unattached receipts exist.</span></span> <span data-ttu-id="5cc80-115">A nyugtákat a **Nyugták** lapon is fel lehet tölteni.</span><span class="sxs-lookup"><span data-stu-id="5cc80-115">You can also upload receipts on the **Receipts** tab.</span></span>
    3. <span data-ttu-id="5cc80-116">A **Költségek** lapon ellenőrizze, hogy vannak-e nem csatolt költségek.</span><span class="sxs-lookup"><span data-stu-id="5cc80-116">On the **Expenses** tab, verify that unattached expenses exist.</span></span> <span data-ttu-id="5cc80-117">A költség felügyelője általában a hitelkártya kiadójától importálja ezeket a költségeket.</span><span class="sxs-lookup"><span data-stu-id="5cc80-117">Typically, the expense administrator imports these expenses from the credit card provider.</span></span>
    4. <span data-ttu-id="5cc80-118">Jelölje ki az **Új költégjelentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5cc80-118">Select **New expense report**.</span></span> <span data-ttu-id="5cc80-119">Vegye észre, hogy a költségek és a most már a nyugták is a költségjelentés létrehozásakor is megadhatók.</span><span class="sxs-lookup"><span data-stu-id="5cc80-119">Notice that you can include expenses, and receipts, now as well, when you create an expense report.</span></span> <span data-ttu-id="5cc80-120">Ha a költséget és a nyugtákat is hozzáadja, akkor a program automatikusan egyezteti a kiadásokat a bevételekhez.</span><span class="sxs-lookup"><span data-stu-id="5cc80-120">If you add both expenses and receipts, automatic matching of the receipts against the expenses is triggered.</span></span>

- <span data-ttu-id="5cc80-121">**Költség létrehozása vagy költség egyeztetése nyugta alapján.**</span><span class="sxs-lookup"><span data-stu-id="5cc80-121">**Create an expense, or match an expense from a receipt.**</span></span>

    1. <span data-ttu-id="5cc80-122">Egy költségjelentés **Nyugták** lapján a **Nyugták hozzáadása** lehetőség kiválasztásával csatoljon nyugtát.</span><span class="sxs-lookup"><span data-stu-id="5cc80-122">On an expense report, on the **Receipts** tab, attach a receipt by selecting **Add receipts**.</span></span>
    2. <span data-ttu-id="5cc80-123">A nyugta feltöltött képe alatt vegye észre a **Létrehozás** és az **Egyeztetés** beállításokat.</span><span class="sxs-lookup"><span data-stu-id="5cc80-123">Under the uploaded image of the receipt, notice the **Create** and **Match** options.</span></span>

        - <span data-ttu-id="5cc80-124">Válassza a **Létrehozás** lehetőséget, ha manuálisan megadott kiadási tranzakciót szeretne létrehozni, és töltse ki a nyugtából megszerzett értékeket.</span><span class="sxs-lookup"><span data-stu-id="5cc80-124">Select **Create** to create a manually entered expense transaction and fill in the values that are extracted from the receipt.</span></span>
        - <span data-ttu-id="5cc80-125">Ha az **Egyeztetés** lehetőséget választja, a rendszer megpróbál egy meglévő költséget egyeztetni a nyugta értékéhez.</span><span class="sxs-lookup"><span data-stu-id="5cc80-125">If you select **Match**, the system tries to match an existing expense to the receipt.</span></span>

## <a name="installation"></a><span data-ttu-id="5cc80-126">Telepítés</span><span class="sxs-lookup"><span data-stu-id="5cc80-126">Installation</span></span>

<span data-ttu-id="5cc80-127">Ez a funkció együtt dolgozik a **Költségjelentések újragondolva** szolgáltatással, amely egyszerűsíti a költségek élményét.</span><span class="sxs-lookup"><span data-stu-id="5cc80-127">This feature works in combination with the **Expense reports re-imagined** feature to help simplify the expense experience.</span></span>

<span data-ttu-id="5cc80-128">Ha ezeket a speciális képességetek szeretné használni, telepítse a Microsoft Dynamics 365 Finance Expense Management Service beépülő modulját, és kapcsolja be a saját példányának funkcióit.</span><span class="sxs-lookup"><span data-stu-id="5cc80-128">To use these advanced expense capabilities, install the Expense Management Service add-in for Microsoft Dynamics 365 Finance, and turn on the features in your instance.</span></span> <span data-ttu-id="5cc80-129">A bővítményt a projektje Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásából éri el.</span><span class="sxs-lookup"><span data-stu-id="5cc80-129">You can access the add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

1. <span data-ttu-id="5cc80-130">Jelentkezzen be a LCS-ba, majd nyissa meg a kívánt környezetet.</span><span class="sxs-lookup"><span data-stu-id="5cc80-130">Sign in to LCS, and open the desired environment.</span></span>
2. <span data-ttu-id="5cc80-131">Lépjen a **Teljes részletek** elemre.</span><span class="sxs-lookup"><span data-stu-id="5cc80-131">Go to **Full details**.</span></span>
3. <span data-ttu-id="5cc80-132">Válassza a **karbantartás** lehetőséget, vagy görgessen a **környezeti bővítmények** gyorslapra.</span><span class="sxs-lookup"><span data-stu-id="5cc80-132">Select **Maintain**, or scroll down to the **Environment add-ins** FastTab.</span></span>
4. <span data-ttu-id="5cc80-133">Válassza az **Új bővítmény telepítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5cc80-133">Select **Install a new add-in**.</span></span>
5. <span data-ttu-id="5cc80-134">Válassza az **Expense Management Service** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="5cc80-134">Select **Expense Management Service**.</span></span>
6. <span data-ttu-id="5cc80-135">Kövesse a telepítési útmutatót, és fogadja el a feltételeit és kikötéseit.</span><span class="sxs-lookup"><span data-stu-id="5cc80-135">Follow the installation guide, and agree to the terms and conditions.</span></span>
7. <span data-ttu-id="5cc80-136">Válassza a **Telepítés** parancsot.</span><span class="sxs-lookup"><span data-stu-id="5cc80-136">Select **Install**.</span></span>

<span data-ttu-id="5cc80-137">Kapcsolja be a következő funkciókat a **Funkció kezelése** munkaterületen:</span><span class="sxs-lookup"><span data-stu-id="5cc80-137">In the **Feature management** workspace, turn on the following features:</span></span>

- <span data-ttu-id="5cc80-138">Költségjelentések újragondolva</span><span class="sxs-lookup"><span data-stu-id="5cc80-138">Expense reports re-imagined</span></span>
- <span data-ttu-id="5cc80-139">Automatikus egyeztetés és költség létrehozása nyugtából</span><span class="sxs-lookup"><span data-stu-id="5cc80-139">Auto-match and create expense from receipt</span></span>

<span data-ttu-id="5cc80-140">A funkciók bekapcsolásakor a következő műveletek történnek:</span><span class="sxs-lookup"><span data-stu-id="5cc80-140">When you turn on these features the following actions occur:</span></span>

- <span data-ttu-id="5cc80-141">A meglévő **Költséggazdálkodás** munkaterületet az új munkaterülettel helyettesíti a program.</span><span class="sxs-lookup"><span data-stu-id="5cc80-141">The existing **Expense management** workspace is replaced with the new workspace.</span></span>
- <span data-ttu-id="5cc80-142">A program hozzáad egy új menüelemet a költségmező láthatóságához.</span><span class="sxs-lookup"><span data-stu-id="5cc80-142">A new menu item for expense field visibility is added.</span></span>
- <span data-ttu-id="5cc80-143">A korábbi **Költségjelentések** lapot továbbra is megnyithatja, ha a **Költségkezelés > Költségeim >Költségjelentések** elemre lép.</span><span class="sxs-lookup"><span data-stu-id="5cc80-143">You can still open the former **Expense reports** page by going to **Expense management > My expenses > Expense reports**.</span></span>
- <span data-ttu-id="5cc80-144">A munkafolyamatok és az esetleges jóváhagyások továbbra is elviszik a meglévő költségjelentések lapra.</span><span class="sxs-lookup"><span data-stu-id="5cc80-144">Workflows and any approvals still take you to the existing expense reports page.</span></span>
- <span data-ttu-id="5cc80-145">A program a nyugtákat a Microsoft Azure Cognitive Services segítségével dolgozza fel, és a metaadatokat kinyeri, majd hozzáadja.</span><span class="sxs-lookup"><span data-stu-id="5cc80-145">Receipts will be processed through Microsoft Azure Cognitive Services, and metadata will be extracted and added.</span></span>
- <span data-ttu-id="5cc80-146">Olyan beállítás van kiválasztva, amely lehetővé teszi az egyeztetett, nem csatolt nyugtákat tartalmazó költségjelentés létrehozását.</span><span class="sxs-lookup"><span data-stu-id="5cc80-146">An option is added that lets you create an expense report that includes matched unattached receipts.</span></span>
- <span data-ttu-id="5cc80-147">Egy, a költségjelentésekhez kapcsolódó opció lehetővé teszi a költségsor létrehozását a nyugtából, vagy egy meglévő bevétel egyeztetésének megkísérlését egy meglévő költségsorral.</span><span class="sxs-lookup"><span data-stu-id="5cc80-147">An option that is added to expense reports lets you create an expense line from a receipt, or attempts to match an existing receipt to an existing expense line.</span></span>

<span data-ttu-id="5cc80-148">A Költségjelentések újragondolva szolgáltatással kapcsolatos további tudnivalókat lásd: [Költségjelentések újragondolva](ExpenseWorkspaceNew.md).</span><span class="sxs-lookup"><span data-stu-id="5cc80-148">For more information about the Expense reports re-imagined feature, see [Expense reports reimagined](ExpenseWorkspaceNew.md).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="5cc80-149">Gyakori kérdések</span><span class="sxs-lookup"><span data-stu-id="5cc80-149">Frequently asked questions</span></span>

<span data-ttu-id="5cc80-150">**Felhasználja-e a Microsoft az adataimat a modelljeiben?**</span><span class="sxs-lookup"><span data-stu-id="5cc80-150">**Does Microsoft use my data for its models?**</span></span>

<span data-ttu-id="5cc80-151">Nem, a Microsoft egy általános gépi tanulási modellt épített ki a nyugtafeldolgozási szolgáltatáshoz.</span><span class="sxs-lookup"><span data-stu-id="5cc80-151">No, Microsoft has built a general machine learning model for its receipt processing service.</span></span> <span data-ttu-id="5cc80-152">Ez a modell nem a feltöltött nyugtákon alapul.</span><span class="sxs-lookup"><span data-stu-id="5cc80-152">This model isn't based on the receipts that you upload.</span></span>

<span data-ttu-id="5cc80-153">**Hol érhető el a funkció, és hogyan dolgozzák fel?**</span><span class="sxs-lookup"><span data-stu-id="5cc80-153">**Where is this feature available and processed?**</span></span>

<span data-ttu-id="5cc80-154">Jelenleg az Egyesült Államok támogatott.</span><span class="sxs-lookup"><span data-stu-id="5cc80-154">Currently, the United States is supported.</span></span>

<span data-ttu-id="5cc80-155">**Hová kerülnek a nyugtáim?**</span><span class="sxs-lookup"><span data-stu-id="5cc80-155">**Where do my receipts go?**</span></span>

<span data-ttu-id="5cc80-156">A Finance kapcsolatba lép a Cognitive Services szolgáltatással a mezőadatok kinyeréséhez.</span><span class="sxs-lookup"><span data-stu-id="5cc80-156">Finance will contact Cognitive Services to extract the field data.</span></span> <span data-ttu-id="5cc80-157">A Cognitive Services legfeljebb 24 óráig őrzi meg a nyugta egy példányát.</span><span class="sxs-lookup"><span data-stu-id="5cc80-157">Cognitive Services will retain a copy of your receipt for up to 24 hours while processing occurs.</span></span> <span data-ttu-id="5cc80-158">A feldolgozás befejezése után a Cognitive Services eltávolítja a nyugtát.</span><span class="sxs-lookup"><span data-stu-id="5cc80-158">After processing is completed, Cognitive Services will remove the receipt.</span></span> <span data-ttu-id="5cc80-159">A Finance továbbra is tárolja a nyugtát.</span><span class="sxs-lookup"><span data-stu-id="5cc80-159">Receipts are still stored in Finance.</span></span>

<span data-ttu-id="5cc80-160">További tudnivalókért lásd: [A nyugta megértésének engedélyezése a Form Recognizer új képességével](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).</span><span class="sxs-lookup"><span data-stu-id="5cc80-160">For more information, see [Enable receipt understanding with Form Recognizer's new capability](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).</span></span>
