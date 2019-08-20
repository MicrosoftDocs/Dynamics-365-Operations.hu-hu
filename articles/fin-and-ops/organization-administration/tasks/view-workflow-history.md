---
title: Munkafolyamat-előzmények megtekintése
description: Ez a témakör azokat a lépéseket ismerteti, amelyekkel megtekintheti azoknak a dokumentumoknak az állapotát, amelyeket a munkafolyamat-rendszerbe küldtek feldolgozásra és jóváhagyásra.
author: jasongre
manager: AnnBe
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowStatus
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 16c6594161f1fecd36183a6b8f2c798f52d70a9c
ms.sourcegitcommit: 81e6eaa2178fda7f7d086ad978f4c891bc4ec10a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/10/2019
ms.locfileid: "1738788"
---
# <a name="view-workflow-history"></a><span data-ttu-id="9fbc7-103">Munkafolyamat-előzmények megtekintése</span><span class="sxs-lookup"><span data-stu-id="9fbc7-103">View workflow history</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9fbc7-104">Ez a témakör azokat a lépéseket ismerteti, amelyekkel megtekintheti azoknak a dokumentumoknak az állapotát, amelyeket a munkafolyamat-rendszerbe küldtek feldolgozásra és jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-104">This topic describes the steps to view the status of a document that was submitted to the workflow system for processing and approval.</span></span> <span data-ttu-id="9fbc7-105">Ez az eljárás az USMF bemutatócéget használja.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-105">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="9fbc7-106">Ugorjon a **Navigációs ablaktábla > Modulok > Gyakori > Lekérdezések > Munkafolyamat > Munkafolyamat-előzmények** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-106">Go to **Navigation pane > Modules > Common > Inquiries > Workflow > Workflow history**.</span></span>
    - <span data-ttu-id="9fbc7-107">Ezen a képernyő megtekintheti azoknak a dokumentumoknak az állapotát, amelyeket a munkafolyamat-rendszerbe küldtek feldolgozásra és jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-107">Use this form to view the status of a document that was submitted to the workflow system for processing and approval.</span></span>  
    - <span data-ttu-id="9fbc7-108">A **Példányazonosító** annak a munkafolyamat-példánynak az azonosító kódja, amely feldolgozza vagy feldolgozta a dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-108">The **Instance ID** is the identification code of the workflow instance that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="9fbc7-109">Az **Állapot** a dokumentum munkafolyamat-állapota.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-109">The **Status** is the workflow status of the document.</span></span>  
    - <span data-ttu-id="9fbc7-110">A **Munkafolyamat-azonosító** annak a munkafolyamatnak az azonosító kódja, amely feldolgozza vagy feldolgozta a dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-110">The **Workflow ID** is the identification code of the workflow that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="9fbc7-111">A **Dokumentum** a dokumentum azonosító kódja.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-111">The **Document** is the identification code of the document.</span></span>  
    - <span data-ttu-id="9fbc7-112">A **Dokumentum típusa** a feldolgozásra elküldött dokumentum típusa.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-112">The **Document type** is the type of document that was submitted for processing.</span></span>  
    - <span data-ttu-id="9fbc7-113">A **Munkafolyamat** annak a munkafolyamatnak a neve, amely feldolgozza vagy feldolgozta a dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-113">The **Workflow** is the name of the workflow that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="9fbc7-114">A **Verzió** annak a munkafolyamatnak a verziószáma, amely feldolgozza vagy feldolgozta a dokumentumot.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-114">The **Version** is the version number of the workflow that is processing, or has processed the document.</span></span>  
    - <span data-ttu-id="9fbc7-115">A **Létrehozás dátuma és időpontja** a dokumentum benyújtásnak dátuma és időpontja.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-115">The **Created date and time** is the date and time that the document was submitted.</span></span>  
    - <span data-ttu-id="9fbc7-116">Az **Eltelt idő** a dokumentum elküldése óta eltelt idő.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-116">The **Elapsed time** is the time that has passed since the document was submitted.</span></span>  
    - <span data-ttu-id="9fbc7-117">A **Folytatás** gomb lehetővé teszi a kijelölt dokumentum munkafolyamatának folytatását.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-117">The **Resume** button allows you to resume the workflow process for the selected document.</span></span>  
    - <span data-ttu-id="9fbc7-118">A **Visszahívás** gombra kattintva visszahívhatja a kiválasztott dokumentumot, így a rendszer nem dolgozza fel.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-118">The **Recall** button allows you to recall the selected document so that it is not processed.</span></span>   
2. <span data-ttu-id="9fbc7-119">A listában válassza ki a kívánt sorból a hivatkozást.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-119">In the list, select the link in the desired row.</span></span>
    - <span data-ttu-id="9fbc7-120">Győződjön meg arról, hogy a **Munkatételek** szakasz ki van bontva.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-120">Make sure the **Work items** section is expanded.</span></span> <span data-ttu-id="9fbc7-121">Ebben a szakaszban megtekintheti a kijelölt dokumentumhoz társított munkatételeket.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-121">In this section you can view the work items that are associated with the selected document.</span></span> <span data-ttu-id="9fbc7-122">Például lehet, hogy el kell végezni valamilyen feladatot, vagy a dokumentumot jóvá kell hagyni.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-122">For example, a task may have to be completed, or the document may have to be approved.</span></span>  
    - <span data-ttu-id="9fbc7-123">Az **Ismételt hozzárendelés** gomb egy párbeszédpanel megnyitását eredményezi, ahol a munkaelemet átadhatja egy másik felhasználónak.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-123">The **Reassign** button will open a dialog box where you can reassign a work item to another user.</span></span>  
    - <span data-ttu-id="9fbc7-124">Győződjön meg arról, hogy a **Nyomkövetési részletek** szakasz ki van bontva.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-124">Make sure the **Tracking details** section is expanded.</span></span> <span data-ttu-id="9fbc7-125">Ebben a szakaszban megtekintheti a kijelölt dokumentum munkafolyamat-előzményeit.</span><span class="sxs-lookup"><span data-stu-id="9fbc7-125">In this section you can view the workflow history of the selected document.</span></span>  

