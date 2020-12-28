---
title: Feladatlisták létrehozása és feladatok hozzáadása
description: Ez a témakör bemutatja, hogy hogyan lehet feladatlistákat létrehozni, és feladatokat adni azokhoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 1cab31784db9f3242dce20e98762088436a5a8f8
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4412925"
---
# <a name="create-task-lists-and-add-tasks"></a><span data-ttu-id="89e04-103">Feladatlisták létrehozása és feladatok hozzáadása</span><span class="sxs-lookup"><span data-stu-id="89e04-103">Create task lists and add tasks</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="89e04-104">Ez a témakör bemutatja, hogy hogyan lehet feladatlistákat létrehozni, és feladatokat adni azokhoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="89e04-104">This topic describes how to create task lists and add tasks to them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="89e04-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="89e04-105">Overview</span></span>

<span data-ttu-id="89e04-106">A *feladat* egy meghatározott munkát vagy egy műveletet határoz meg, amelyet valakinek el kell végeznie a megadott esedékességi dátumig vagy azt megelőzően.</span><span class="sxs-lookup"><span data-stu-id="89e04-106">A *task* defines a specific piece of work or an action that someone must complete on or before a specified due date.</span></span> <span data-ttu-id="89e04-107">A Dynamics 365 Commerce alkalmazásban egy feladathoz a kapcsolattartóval kapcsolatos részletes utasítások és információk is tartozhatnak.</span><span class="sxs-lookup"><span data-stu-id="89e04-107">In Dynamics 365 Commerce, a task can include detailed instructions and information about a contact person.</span></span> <span data-ttu-id="89e04-108">Tartalmazhat a háttérben történő irodai műveletekre, pénztári (POS) műveletekre vagy a webhelyoldalakra mutató hivatkozásokat is, amelyek segítségével javíthatja a termelékenységet, és egy kontextust adhat meg, hogy a feladat tulajdonosa hatékonyan végezhesse el a feladatot.</span><span class="sxs-lookup"><span data-stu-id="89e04-108">It can also include links to back-office operations, point of sale (POS) operations, or site pages, to help improve productivity and provide the context that the task owner requires to complete the task efficiently.</span></span>

<span data-ttu-id="89e04-109">A *feladatlista* olyan feladatok gyűjteménye, amelyeket egy üzleti folyamat részeként kell végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="89e04-109">A *task list* is a collection of tasks that must be completed as part of a business process.</span></span> <span data-ttu-id="89e04-110">Előfordulhat például, hogy az új dolgozónak be kell fejeznie egy feladatlistát a felvétel során, vagy van egy feladatlista a pénztárosoknak, akik az esti műszakban dolgoznak, vagy van egy olyan feladatlista, amivel felkészítik az üzletet a közelgő ünnepi szezonra.</span><span class="sxs-lookup"><span data-stu-id="89e04-110">For example, there might be a task list that a new worker must complete during onboarding, a task list for cashiers who work evening shifts, or a task list that must be completed to prepare the store for an upcoming holiday season.</span></span> <span data-ttu-id="89e04-111">A Commerce alkalmazásban minden olyan feladatlistát, amelynek van a megadott dátuma, tetszőleges számú üzlethez vagy alkalmazotthoz hozzá lehet rendelni, és be lehet állítani, hogy ismétlődjön.</span><span class="sxs-lookup"><span data-stu-id="89e04-111">In Commerce, every task list that has a target date can be assigned to any number of stores or employees, and it can be configured to recur.</span></span>

<span data-ttu-id="89e04-112">A vezetők és a dolgozók egyaránt létrehozhatnak feladatlistát a Commerce háttérirodájában, majd ezeket üzletek egy halmazához hozzárendelhetik.</span><span class="sxs-lookup"><span data-stu-id="89e04-112">Both managers and workers can create task lists in Commerce back office, and then assign them to a set of stores.</span></span>

## <a name="create-a-task-list"></a><span data-ttu-id="89e04-113">Feladatlista létrehozása</span><span class="sxs-lookup"><span data-stu-id="89e04-113">Create a task list</span></span>

<span data-ttu-id="89e04-114">Feladatlista létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="89e04-114">To create a task list, follow these steps.</span></span>

1. <span data-ttu-id="89e04-115">Válassza a **Retail és Commerce \> Feladatok kezelése \> Feladatkezelés adminisztrációja** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="89e04-115">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="89e04-116">Válassza az **Új** lehetőséget, majd írja be a kívánt értékeket a **Név**, a **Leírás** és a **Tulajdonos** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="89e04-116">Select **New**, and then enter values in the **Name**, **Description**, and **Owner** fields.</span></span>
1. <span data-ttu-id="89e04-117">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="89e04-117">Select **Save**.</span></span>

## <a name="add-tasks-to-a-task-list"></a><span data-ttu-id="89e04-118">Feladatok hozzáadása egy feladatlistához</span><span class="sxs-lookup"><span data-stu-id="89e04-118">Add tasks to a task list</span></span>

<span data-ttu-id="89e04-119">Feladatok hozzáadásához egy feladatlistához tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="89e04-119">To add tasks to a task list, follow these steps.</span></span>
 
1. <span data-ttu-id="89e04-120">Egy meglévő Feladatlista **Feladatok** gyorslapján válassza az **Új** lehetőséget, ha feladatot szeretne hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="89e04-120">On the **Tasks** FastTab of an existing task list, select **New** to add a task.</span></span>
1. <span data-ttu-id="89e04-121">Az **Új feladat létrehozása** párbeszédpanelen írjon be egy egyedi nevet a feladat számára a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="89e04-121">In the **Create a new task** dialog box, in the **Name** field, enter a name for the task.</span></span>
1. <span data-ttu-id="89e04-122">Írjon be egy pozitív vagy egy negatív egész értéket a **Határidő eltolása a céldátumhoz képest** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="89e04-122">In the **Due data offset from target date** field, enter a positive or negative integer value.</span></span> <span data-ttu-id="89e04-123">Írja be például a **-2** értéket, ha a feladatnak két nappal a feladatlista esedékességi dátuma előtt be kell fejeződnie.</span><span class="sxs-lookup"><span data-stu-id="89e04-123">For example, enter **-2** if the task should be completed two days before the task list's due date.</span></span>
1. <span data-ttu-id="89e04-124">A **Megjegyzések** mezőbe írja be a részletes utasításokat.</span><span class="sxs-lookup"><span data-stu-id="89e04-124">In the **Notes** field, enter detailed instructions.</span></span>
1. <span data-ttu-id="89e04-125">A **Kapcsolattartó személy** mezőjébe írja be annak a szakembernek a nevét, akivel a feladat tulajdonosa kapcsolatba tud lépni, ha segítségre van szüksége.</span><span class="sxs-lookup"><span data-stu-id="89e04-125">In the **Contact person** field, enter the name of a subject matter expert that the task owner can contact if he or she needs help.</span></span>
1. <span data-ttu-id="89e04-126">A **Feladat hivatkozása** mezőben adjon meg egy hivatkozást a feladat jellegétől függően.</span><span class="sxs-lookup"><span data-stu-id="89e04-126">In the **Task link** field, enter a link, based on the nature of the task.</span></span>

> [!TIP]
> <span data-ttu-id="89e04-127">Annak ellenére, hogy a **Hozzárendelve a következőhöz:** mezővel a feladatlista létrehozása során a feladatot hozzárendelheti valakihez, ajánlott elkerülni a feladatok hozzárendelését a Feladatlista létrehozása során.</span><span class="sxs-lookup"><span data-stu-id="89e04-127">Although you can use the **Assigned to** field to assign tasks to someone while you're creating a task list, we recommend that you avoid assigning tasks during task list creation.</span></span> <span data-ttu-id="89e04-128">Ehelyett a lista ez egyes üzletekhez való példányosítása után rendelje hozzá a feladatokat.</span><span class="sxs-lookup"><span data-stu-id="89e04-128">Instead, assign the tasks after the list is instantiated for individual stores.</span></span>

## <a name="use-task-links-to-help-improve-worker-productivity"></a><span data-ttu-id="89e04-129">A feladatra mutató hivatkozásokkal javíthatja a dolgozó termelékenységét</span><span class="sxs-lookup"><span data-stu-id="89e04-129">Use task links to help improve worker productivity</span></span>

<span data-ttu-id="89e04-130">A Commerce lehetővé teszi a feladatok meghatározott pénztári műveletekhez történő csatolását, például az értékesítési jelentések futtatását, az új alkalmazotti orientációhoz kapcsolódó online képzési videó megtekintését, illetve egy háttérművelet végrehajtását.</span><span class="sxs-lookup"><span data-stu-id="89e04-130">Commerce lets you link tasks to specific POS operations, such as running a sales report, viewing an online training video for new employee orientation, or performing a back-office operation.</span></span> <span data-ttu-id="89e04-131">Ez a funkció segít a feladattulajdonsoknak a feladatok hatékony teljesítéséhez szükséges információk beszerzésében.</span><span class="sxs-lookup"><span data-stu-id="89e04-131">This feature helps task owners get the information that they need to complete a task efficiently.</span></span>

<span data-ttu-id="89e04-132">A feladatok létrehozása közben feladathoz kapcsolódó hivatkozások hozzáadásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="89e04-132">To add task links while you create a task, follow these steps.</span></span>

1. <span data-ttu-id="89e04-133">Egy meglévő feladatlista **Feladatok** gyorslapján válassza az **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="89e04-133">On the **Tasks** FastTab of an existing task list, select **Edit**.</span></span>
1. <span data-ttu-id="89e04-134">A **Feladat szerkesztése** párbeszédpanel **Feladathivatkozás** mezőjében válasszon ki egyet vagy többet a következő lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="89e04-134">In the **Edit task** dialog box, in the **Task link** field, select one or more of the following options:</span></span>

    - <span data-ttu-id="89e04-135">Válassza ki a **Menüelemet** a háttérben történő működés konfigurálásához, például „Termékcsomagok.”</span><span class="sxs-lookup"><span data-stu-id="89e04-135">Select **Menu item** to configure a back-office operation, such as "Product kits."</span></span>
    - <span data-ttu-id="89e04-136">Válassza ki a **Pénztári művelet** elemet pénztári művelet konfigurálásához, például „Értékesítési jelentések.”</span><span class="sxs-lookup"><span data-stu-id="89e04-136">Select **POS Operation** to configure a POS operation, such as "Sales reports."</span></span>
    - <span data-ttu-id="89e04-137">Válasszon **URL-címet** egy abszolút URL-cím beállításához.</span><span class="sxs-lookup"><span data-stu-id="89e04-137">Select **URL** to configure an absolute URL.</span></span>

<span data-ttu-id="89e04-138">A következő ábra a **Feladatok szerkesztése** párbeszédpanel feladathivatkozások beállítását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="89e04-138">The following illustration shows the selection of task links in the **Edit task** dialog box.</span></span>

![A feladathivatkozások kiválasztása a feladat szerkesztése párbeszédpanelen](media/HQ-POS-Tasks-Linking.png)

### <a name="configure-a-pos-operation-so-that-it-can-be-linked-to-a-task"></a><span data-ttu-id="89e04-140">A pénztári művelet konfigurálása egy feladathoz való csatolás céljából</span><span class="sxs-lookup"><span data-stu-id="89e04-140">Configure a POS operation so that it can be linked to a task</span></span>

<span data-ttu-id="89e04-141">A pénztári művelet konfigurálásához egy feladathoz való csatolás céljából kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="89e04-141">To configure a POS operation so that it can be linked to a task, follow these steps.</span></span>

1. <span data-ttu-id="89e04-142">Lépjen a **Retail és Commerce \> Csatornabeállítás \> Pénztárbeállítás \> Pénztár \> Pénztárműveletek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="89e04-142">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS operations**.</span></span>
1. <span data-ttu-id="89e04-143">Válassz a **Szerkesztés** lehetőséget, keresse meg a pénztári műveletet és jelölje be hozzá a **Feladatkezelés engedélyezése** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="89e04-143">Select **Edit**, find the POS operation, and then select the **Enable Task Management** check box for it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="89e04-144">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="89e04-144">Additional resources</span></span>

[<span data-ttu-id="89e04-145">Feladatkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="89e04-145">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="89e04-146">Feladatkezelés konfigurálása</span><span class="sxs-lookup"><span data-stu-id="89e04-146">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="89e04-147">Feladatlisták hozzárendelése áruházakhoz vagy alkalmazottakhoz</span><span class="sxs-lookup"><span data-stu-id="89e04-147">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)

[<span data-ttu-id="89e04-148">Feladatkezelés a pénztárban</span><span class="sxs-lookup"><span data-stu-id="89e04-148">Task management in POS</span></span>](task-mgmt-POS.md)
