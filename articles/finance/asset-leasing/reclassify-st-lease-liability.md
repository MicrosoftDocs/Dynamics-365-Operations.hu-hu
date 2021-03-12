---
title: A lízingkötelezettség rövid távú részének átsorolása
description: Ez a témakör bemutatja, hogyan hozhat létre havi naplóbejegyzést a lízingkötelezettség egy részének rövid távúként történő átsorolásához.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 08ca824bb4c4a02a80f2187fb5f8fe4e8b7327c9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992914"
---
# <a name="reclassify-the-short-term-portion-of-lease-liability"></a><span data-ttu-id="24335-103">A lízingkötelezettség rövid távú részének átsorolása</span><span class="sxs-lookup"><span data-stu-id="24335-103">Reclassify the short-term portion of lease liability</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="24335-104">Ez a témakör bemutatja, hogyan hozhat létre havi naplóbejegyzést a lízingkötelezettség egy részének rövid távúként történő átsorolásához.</span><span class="sxs-lookup"><span data-stu-id="24335-104">This topic explains how to create a monthly journal entry to reclassify a portion of the lease liability as short-term.</span></span> <span data-ttu-id="24335-105">Ha a kötegfolyamatban kiválasztott ütemezés **Rövidtávú lízingkötelezettség átsorolásakor** egy naplóbejegyzés jön létre.</span><span class="sxs-lookup"><span data-stu-id="24335-105">When the schedule that is selected in the batch process is **Short-term lease liability reclass**, a journal entry is created.</span></span> <span data-ttu-id="24335-106">Ez a bejegyzés a lízingkötelezettség aktuális részének feladására szolgál a hónap utolsó napján.</span><span class="sxs-lookup"><span data-stu-id="24335-106">This entry is used to post the current portion of the lease liability on the last day of the month.</span></span> <span data-ttu-id="24335-107">Ezzel egy időben a következő hónap első napjától a függvény a következő hónap első napjától adja fel a sztornírozott bejegyzést.</span><span class="sxs-lookup"><span data-stu-id="24335-107">At the same time, a reversal entry is posted as of the first day of the next month.</span></span>

<span data-ttu-id="24335-108">A lízingkötelezettség rövid távú része a kötelezettség amortizációs ütemezésében jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="24335-108">The short-term portion of the lease liability is shown on the liability amortization schedule.</span></span> <span data-ttu-id="24335-109">A naplóbejegyzés feladásakor elérhetővé válik a **Létrehozott kötelezettség-átsorolási napló** oszlopa, és a naplóazonosító is ki lesz töltve az ütemezésben.</span><span class="sxs-lookup"><span data-stu-id="24335-109">When the journal entry is posted, the **Liability reclass journal created** column becomes available, and the journal ID is also filled in on the schedule.</span></span>

<span data-ttu-id="24335-110">A rövid távú kötelezettség újraosztályzási naplóbejegyzés létrehozásához és feladásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="24335-110">To create and post the short-term liability reclassification journal entry, follow these steps.</span></span>

1. <span data-ttu-id="24335-111">Nyissa meg az **Eszközlízing \> Időszakos \> Kötegelt napló létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24335-111">Go to **Asset leasing \> Periodic \> Batch journal creation**.</span></span>
2. <span data-ttu-id="24335-112">Válassza ki a **Kötegelt napló létrehozása** párbeszédpanel **Ütemezés kiválasztása** mezőjében a **Rövid távú lízingkötelezettség újraosztályozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24335-112">In the **Batch journal creation** dialog box, in the **Select schedule** field, select **Short-term lease liability reclass**.</span></span>
3. <span data-ttu-id="24335-113">Válassza ki a **Lízingcsoport** mezőben a lízingcsoportot.</span><span class="sxs-lookup"><span data-stu-id="24335-113">In the **Lease group** field, select a lease group.</span></span> <span data-ttu-id="24335-114">Másik lehetőségként a **Könyv azonosítója** mezőben válassza ki a könyv azonosítóját.</span><span class="sxs-lookup"><span data-stu-id="24335-114">Alternatively, in the **Book ID** field, select the book ID.</span></span>
4. <span data-ttu-id="24335-115">Kapcsolja be a **Feladás** paramétert.</span><span class="sxs-lookup"><span data-stu-id="24335-115">Turn on the **Post** parameter.</span></span> <span data-ttu-id="24335-116">Azt is megteheti, hogy ha a bejegyzést létre kell hozni, de nem szabad feladni, akkor kikapcsolva hagyja ezt a paramétert.</span><span class="sxs-lookup"><span data-stu-id="24335-116">Alternatively, if the entry should be created but not posted, leave this parameter turned off.</span></span>
5. <span data-ttu-id="24335-117">A feladás előtt kapcsolja be az **Előzetes verzió feladás előtt** paramétert, hogy a bejegyzést megtekinthesse feladás előtt.</span><span class="sxs-lookup"><span data-stu-id="24335-117">Turn on the **Preview before posting** parameter to view the entry before it's posted.</span></span>
6. <span data-ttu-id="24335-118">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="24335-118">Select **OK**.</span></span>
