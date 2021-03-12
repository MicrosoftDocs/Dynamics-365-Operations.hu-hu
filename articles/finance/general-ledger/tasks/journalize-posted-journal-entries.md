---
title: Feladott naplóbejegyzések naplózása
description: Az eljárás bemutatja, hogyan naplózhatók a feladott naplóbejegyzések.
author: aprilolson
manager: AnnBe
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ad18063e0a66a4aac0ebef7f0ce45c73137abcc7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968529"
---
# <a name="journalize-posted-journal-entries"></a><span data-ttu-id="92133-103">Feladott naplóbejegyzések naplózása</span><span class="sxs-lookup"><span data-stu-id="92133-103">Journalize posted journal entries</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="92133-104">Az eljárás bemutatja, hogyan naplózhatók a feladott naplóbejegyzések.</span><span class="sxs-lookup"><span data-stu-id="92133-104">This procedure shows how to journalize posted journal entries.</span></span> <span data-ttu-id="92133-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="92133-105">This procedure uses the USMF demo data company.</span></span>

1. <span data-ttu-id="92133-106">A **Navigációs panelen** válassza a **Modulok > Főkönyv > Főkönyv beállítás > Főkönyv paraméterei** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="92133-106">In the **Navigation pane**, go to **Modules > General ledger > Ledger setup > General ledger parameters**.</span></span>
2. <span data-ttu-id="92133-107">A **Bővített főkönyvnapló** mező értéke lehet Igen vagy Nem.</span><span class="sxs-lookup"><span data-stu-id="92133-107">The **Extended ledger journal** field can be set to Yes or No.</span></span> <span data-ttu-id="92133-108">Ha Igen, akkor a kapott jelentés eltérő lesz.</span><span class="sxs-lookup"><span data-stu-id="92133-108">If Yes, the report output will be different.</span></span>
3. <span data-ttu-id="92133-109">Válassza ki, hogy az időszak lezárható-e, ha a naplózási folyamatot még nem futtatták le.</span><span class="sxs-lookup"><span data-stu-id="92133-109">Select whether the period can be closed if the journalizing process hasn't been run.</span></span> <span data-ttu-id="92133-110">Ha a megadott érték Igen, az időszakot nem lehet lezárni mindaddig, amíg az adott időszakra a naplózási folyamat be nem fejeződött.</span><span class="sxs-lookup"><span data-stu-id="92133-110">If this option is set to Yes, the period cannot be closed until the journalizing process has been completed for that period.</span></span>  
4. <span data-ttu-id="92133-111">Zárja be a lapot.</span><span class="sxs-lookup"><span data-stu-id="92133-111">Close the page.</span></span>
5. <span data-ttu-id="92133-112">Nyissa meg a **Navigációs ablakban** a **Modulok > Főkönyv > Időszakos feladatok >Naplózás** elemet.</span><span class="sxs-lookup"><span data-stu-id="92133-112">In the **Navigation pane**, go to **Modules > General ledger > Periodic tasks > Journalizing**.</span></span>
6. <span data-ttu-id="92133-113">Kattintson a **Szűrő** parancsra.</span><span class="sxs-lookup"><span data-stu-id="92133-113">Click **Filter**.</span></span>
7. <span data-ttu-id="92133-114">Jelölje ki a sort a megadni kívánt szűrőfeltételekkel.</span><span class="sxs-lookup"><span data-stu-id="92133-114">Highlight the row with the filter criteria that you want to define.</span></span>
8. <span data-ttu-id="92133-115">A **Feltételek** mezőben adja meg vagy válassza ki a szűrőfeltételeket.</span><span class="sxs-lookup"><span data-stu-id="92133-115">In the **Criteria** field, enter or select the filter criteria..</span></span>
9. <span data-ttu-id="92133-116">Kattintson az **OK** gombra a szűrőoldal bezárásához.</span><span class="sxs-lookup"><span data-stu-id="92133-116">Click **OK** to close the filter page.</span></span>
10. <span data-ttu-id="92133-117">Kattintson az **OK** gombra a naplózási folyamat elindításához.</span><span class="sxs-lookup"><span data-stu-id="92133-117">Click **OK** to start the journalizing process.</span></span> <span data-ttu-id="92133-118">A folyamat befejezése után jelentés készül.</span><span class="sxs-lookup"><span data-stu-id="92133-118">A report will be generated after the process is complete.</span></span>  

