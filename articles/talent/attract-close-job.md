---
title: Feladat lezárása az Attract szolgáltatásban
description: Ez a témakör bemutatja, hogyan lehet egy állást lezárni a Microsoft Dynamics 365 Talent - Attract megoldásban.
author: andreabichsel
manager: AnnBe
ms.date: 07/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2010-07-10
ms.dyn365.ops.version: Talent 2019 Wave 1 update
ms.openlocfilehash: 3705b5b1c6beab9e602ac7d16bf53da51602d61a
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/25/2019
ms.locfileid: "2833138"
---
# <a name="close-a-job-in-attract"></a><span data-ttu-id="1cab1-103">Feladat lezárása az Attract szolgáltatásban</span><span class="sxs-lookup"><span data-stu-id="1cab1-103">Close a job in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1cab1-104">A Microsoft Dynamics 365 Talent: Attract megoldásban **Állás érvénytelenítve** vagy **Beosztás betöltve** értékkel zárhat le egy állást.</span><span class="sxs-lookup"><span data-stu-id="1cab1-104">In Microsoft Dynamics 365 Talent: Attract, you can close a job as either **Job cancelled** or **Position filled**.</span></span> <span data-ttu-id="1cab1-105">Bármikor érvényteleníthet egy állást.</span><span class="sxs-lookup"><span data-stu-id="1cab1-105">You can cancel a job at any time.</span></span>

<span data-ttu-id="1cab1-106">Ha jelezni szeretné, hogy a beosztást betöltöttek, egy pályázónak el kell fogadnia az állásajánlatot.</span><span class="sxs-lookup"><span data-stu-id="1cab1-106">If you want to indicate that the position was filled, a candidate must have accepted an offer for the job.</span></span>

## <a name="cancel-a-job"></a><span data-ttu-id="1cab1-107">Állás érvénytelenítése</span><span class="sxs-lookup"><span data-stu-id="1cab1-107">Cancel a job</span></span>

<span data-ttu-id="1cab1-108">Bármikor érvényteleníthet egy állást az Attract megoldásban.</span><span class="sxs-lookup"><span data-stu-id="1cab1-108">You can cancel a job in Attract at any time.</span></span>

1. <span data-ttu-id="1cab1-109">Az Attract **Állások** lapján válassza ki azt az állást, amelyet vissza szeretne vonni.</span><span class="sxs-lookup"><span data-stu-id="1cab1-109">In the **Jobs** tab in Attract, select the job you want to cancel.</span></span>

2. <span data-ttu-id="1cab1-110">Válassza az **Állás lezárása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1cab1-110">Select **Close job**.</span></span>

   ![Állása lezárása az Attract megoldásban](./media/attract-close-job.png)

3. <span data-ttu-id="1cab1-112">Az **Állás lezárása** párbeszédpanelen válassza az **Állás érvénytelenítve** lehetőséget majd adja meg a megjegyzéseket, majd válassza az **Állás lezárása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1cab1-112">In the **Close this job** dialog box, select **Job cancelled**, add any comments, and then select **Close job**.</span></span>

   ![Állás lezárása Beosztás betöltve értékkel](./media/attract-close-job-as-cancelled.png)

## <a name="close-a-job-as-position-filled"></a><span data-ttu-id="1cab1-114">Egy állás lezárása Beosztás betöltve értékkel</span><span class="sxs-lookup"><span data-stu-id="1cab1-114">Close a job as Position filled</span></span>

<span data-ttu-id="1cab1-115">Az állást akkor zárhatja le **Beosztás betöltve** értékkel, ha legalább egy potenciális jelölt befejezte az ajánlati szakaszt.</span><span class="sxs-lookup"><span data-stu-id="1cab1-115">You can close a job as **Position filled** after at least one prospect has completed the Offer stage.</span></span>

1. <span data-ttu-id="1cab1-116">Az Attract **Állások** lapján válassza ki azt az állást, amelyet vissza szeretne vonni.</span><span class="sxs-lookup"><span data-stu-id="1cab1-116">In the **Jobs** tab in Attract, select the job you want to cancel.</span></span>

2. <span data-ttu-id="1cab1-117">Válassza az **Állás lezárása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1cab1-117">Select **Close job**.</span></span>

   ![Állása lezárása az Attract megoldásban](./media/attract-close-job.png)

3. <span data-ttu-id="1cab1-119">Az **Állás lezárása** párbeszédpanelen válassza ki a **Beosztás betöltve** értéket, válassza ki azt a pályázót, aki elfogadta az ajánlatot, vegyen fel megjegyzést, majd válassza a **Az állás lezárása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1cab1-119">In the **Close this job** dialog box, select **Position filled**, select the candidate who accepted the offer, add any comments, and then select **Close job**.</span></span>

   ![Állás lezárása Beosztás betöltve értékkel](./media/attract-close-job-as-position-filled.png)

   > [!NOTE]
   > <span data-ttu-id="1cab1-121">Az állást csak akkor zárhatja le **Beosztás betöltve** értékkel, ha legalább egy potenciális jelölt befejezte az ajánlati szakaszt.</span><span class="sxs-lookup"><span data-stu-id="1cab1-121">You can only close a job as **Position filled** when at least one prospect has completed the Offer stage.</span></span> <span data-ttu-id="1cab1-122">Ha az álláspályázathoz nincs kiválasztva az **Ajánlat elfogadva** lehetősége, vagy jelentkezésben nem az **Elfogadott** állapot az ajánlatban, a **Beosztás betöltve** lehetőség nem jelenik meg az **Ok** legördülő menüben.</span><span class="sxs-lookup"><span data-stu-id="1cab1-122">If the job application doesn't have **Offer accepted** selected, or if the application doesn't display a status of **Accepted** in Offer, the **Position filled** option won't display in the **Reason** dropdown.</span></span>


