--- 
title: "Feladott naplóbejegyzések naplózása"
description: "Az eljárás bemutatja, hogyan naplózhatók a feladott naplóbejegyzések."
author: aprilolson
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 253794b4eb44cb5fa6f946caa96ec39a477c061e
ms.contentlocale: hu-hu
ms.lasthandoff: 04/13/2018

---
# <a name="journalize-posted-journal-entries"></a><span data-ttu-id="b1ba7-103">Feladott naplóbejegyzések naplózása</span><span class="sxs-lookup"><span data-stu-id="b1ba7-103">Journalize posted journal entries</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b1ba7-104">Az eljárás bemutatja, hogyan naplózhatók a feladott naplóbejegyzések.</span><span class="sxs-lookup"><span data-stu-id="b1ba7-104">This procedure shows how to journalize posted journal entries.</span></span> <span data-ttu-id="b1ba7-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="b1ba7-105">This procedure uses the USMF demo data company.</span></span>

1. <span data-ttu-id="b1ba7-106">Ellenőrizze a naplózási beállításokat a Főkönyv > Főkönyv beállításai > Főkönyvi paraméterek menüpontban.</span><span class="sxs-lookup"><span data-stu-id="b1ba7-106">Validate the settings for journalizing under General ledger > Ledger setup > General ledger parameters.</span></span>
2. <span data-ttu-id="b1ba7-107">A Bővített főkönyvnapló mező értéke lehet Igen vagy Nem.</span><span class="sxs-lookup"><span data-stu-id="b1ba7-107">The Extended ledger journal field can be set to Yes or No.</span></span> <span data-ttu-id="b1ba7-108">Ha Igen, akkor a kapott jelentés eltérő lesz.</span><span class="sxs-lookup"><span data-stu-id="b1ba7-108">If Yes, the report output will be different.</span></span>
3. <span data-ttu-id="b1ba7-109">Válassza ki, hogy az időszak lezárható-e, ha a naplózási folyamatot még nem futtatták le.</span><span class="sxs-lookup"><span data-stu-id="b1ba7-109">Select whether the period can be closed if the journalizing process hasn't been run.</span></span>
    * <span data-ttu-id="b1ba7-110">Ha a megadott érték Igen, az időszakot nem lehet lezárni mindaddig, amíg az adott időszakra a naplózási folyamat be nem fejeződött.</span><span class="sxs-lookup"><span data-stu-id="b1ba7-110">If this option is set to Yes, the period cannot be closed until the journalizing process has been completed for that period.</span></span>  
4. <span data-ttu-id="b1ba7-111">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="b1ba7-111">Close the page.</span></span>
5. <span data-ttu-id="b1ba7-112">Ugorjon a Főkönyv > Időszaki feladatok > Naplózás pontra.</span><span class="sxs-lookup"><span data-stu-id="b1ba7-112">Go to General ledger > Periodic tasks > Journalizing.</span></span>
6. <span data-ttu-id="b1ba7-113">Kattintson a Szűrő parancsra.</span><span class="sxs-lookup"><span data-stu-id="b1ba7-113">Click Filter.</span></span>
7. <span data-ttu-id="b1ba7-114">Jelölje ki a sort a megadni kívánt szűrőfeltételekkel.</span><span class="sxs-lookup"><span data-stu-id="b1ba7-114">Highlight the row with the filter criteria that you want to define.</span></span>
8. <span data-ttu-id="b1ba7-115">A Feltételek mezőben adja meg vagy válassza ki a szűrőfeltételeket.</span><span class="sxs-lookup"><span data-stu-id="b1ba7-115">In the Criteria field, enter or select the filter criteria..</span></span>
9. <span data-ttu-id="b1ba7-116">Kattintson az OK gombra a szűrőoldal bezárásához.</span><span class="sxs-lookup"><span data-stu-id="b1ba7-116">Click OK to close the filter page.</span></span>
10. <span data-ttu-id="b1ba7-117">Kattintson az OK gombra a naplózási folyamat elindításához.</span><span class="sxs-lookup"><span data-stu-id="b1ba7-117">Click OK to start the journalizing process.</span></span>
    * <span data-ttu-id="b1ba7-118">A folyamat befejezése után jelentés készül.</span><span class="sxs-lookup"><span data-stu-id="b1ba7-118">A report will be generated after the process is complete.</span></span>  


