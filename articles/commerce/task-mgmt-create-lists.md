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
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 28bea16c3266115cf09aa80a364344789d60af7a
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477829"
---
# <a name="create-task-lists-and-add-tasks"></a><span data-ttu-id="9fbf3-103">Feladatlisták létrehozása és feladatok hozzáadása</span><span class="sxs-lookup"><span data-stu-id="9fbf3-103">Create task lists and add tasks</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9fbf3-104">Ez a témakör bemutatja, hogy hogyan lehet feladatlistákat létrehozni, és feladatokat adni azokhoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-104">This topic describes how to create task lists and add tasks to them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="9fbf3-105">A *feladat* egy meghatározott munkát vagy egy műveletet határoz meg, amelyet valakinek el kell végeznie a megadott esedékességi dátumig vagy azt megelőzően.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-105">A *task* defines a specific piece of work or an action that someone must complete on or before a specified due date.</span></span> <span data-ttu-id="9fbf3-106">A Dynamics 365 Commerce alkalmazásban egy feladathoz a kapcsolattartóval kapcsolatos részletes utasítások és információk is tartozhatnak.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-106">In Dynamics 365 Commerce, a task can include detailed instructions and information about a contact person.</span></span> <span data-ttu-id="9fbf3-107">Tartalmazhat a háttérben történő irodai műveletekre, pénztári (POS) műveletekre vagy a webhelyoldalakra mutató hivatkozásokat is, amelyek segítségével javíthatja a termelékenységet, és egy kontextust adhat meg, hogy a feladat tulajdonosa hatékonyan végezhesse el a feladatot.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-107">It can also include links to back-office operations, point of sale (POS) operations, or site pages, to help improve productivity and provide the context that the task owner requires to complete the task efficiently.</span></span>

<span data-ttu-id="9fbf3-108">A *feladatlista* olyan feladatok gyűjteménye, amelyeket egy üzleti folyamat részeként kell végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-108">A *task list* is a collection of tasks that must be completed as part of a business process.</span></span> <span data-ttu-id="9fbf3-109">Előfordulhat például, hogy az új dolgozónak be kell fejeznie egy feladatlistát a felvétel során, vagy van egy feladatlista a pénztárosoknak, akik az esti műszakban dolgoznak, vagy van egy olyan feladatlista, amivel felkészítik az üzletet a közelgő ünnepi szezonra.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-109">For example, there might be a task list that a new worker must complete during onboarding, a task list for cashiers who work evening shifts, or a task list that must be completed to prepare the store for an upcoming holiday season.</span></span> <span data-ttu-id="9fbf3-110">A Commerce alkalmazásban minden olyan feladatlistát, amelynek van a megadott dátuma, tetszőleges számú üzlethez vagy alkalmazotthoz hozzá lehet rendelni, és be lehet állítani, hogy ismétlődjön.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-110">In Commerce, every task list that has a target date can be assigned to any number of stores or employees, and it can be configured to recur.</span></span>

<span data-ttu-id="9fbf3-111">A vezetők és a dolgozók egyaránt létrehozhatnak feladatlistát a Commerce háttérirodájában, majd ezeket üzletek egy halmazához hozzárendelhetik.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-111">Both managers and workers can create task lists in Commerce back office, and then assign them to a set of stores.</span></span>

## <a name="create-a-task-list"></a><span data-ttu-id="9fbf3-112">Feladatlista létrehozása</span><span class="sxs-lookup"><span data-stu-id="9fbf3-112">Create a task list</span></span>

<span data-ttu-id="9fbf3-113">Feladatlista létrehozásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-113">To create a task list, follow these steps.</span></span>

1. <span data-ttu-id="9fbf3-114">Válassza a **Retail és Commerce \> Feladatok kezelése \> Feladatkezelés adminisztrációja** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-114">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="9fbf3-115">Válassza az **Új** lehetőséget, majd írja be a kívánt értékeket a **Név**, a **Leírás** és a **Tulajdonos** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-115">Select **New**, and then enter values in the **Name**, **Description**, and **Owner** fields.</span></span>
1. <span data-ttu-id="9fbf3-116">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-116">Select **Save**.</span></span>

## <a name="add-tasks-to-a-task-list"></a><span data-ttu-id="9fbf3-117">Feladatok hozzáadása egy feladatlistához</span><span class="sxs-lookup"><span data-stu-id="9fbf3-117">Add tasks to a task list</span></span>

<span data-ttu-id="9fbf3-118">Feladatok hozzáadásához egy feladatlistához tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="9fbf3-118">To add tasks to a task list, follow these steps.</span></span>
 
1. <span data-ttu-id="9fbf3-119">Egy meglévő Feladatlista **Feladatok** gyorslapján válassza az **Új** lehetőséget, ha feladatot szeretne hozzáadni.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-119">On the **Tasks** FastTab of an existing task list, select **New** to add a task.</span></span>
1. <span data-ttu-id="9fbf3-120">Az **Új feladat létrehozása** párbeszédpanelen írjon be egy egyedi nevet a feladat számára a **Név** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-120">In the **Create a new task** dialog box, in the **Name** field, enter a name for the task.</span></span>
1. <span data-ttu-id="9fbf3-121">Írjon be egy pozitív vagy egy negatív egész értéket a **Határidő eltolása a céldátumhoz képest** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-121">In the **Due data offset from target date** field, enter a positive or negative integer value.</span></span> <span data-ttu-id="9fbf3-122">Írja be például a **-2** értéket, ha a feladatnak két nappal a feladatlista esedékességi dátuma előtt be kell fejeződnie.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-122">For example, enter **-2** if the task should be completed two days before the task list's due date.</span></span>
1. <span data-ttu-id="9fbf3-123">A **Megjegyzések** mezőbe írja be a részletes utasításokat.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-123">In the **Notes** field, enter detailed instructions.</span></span>
1. <span data-ttu-id="9fbf3-124">A **Kapcsolattartó személy** mezőjébe írja be annak a szakembernek a nevét, akivel a feladat tulajdonosa kapcsolatba tud lépni, ha segítségre van szüksége.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-124">In the **Contact person** field, enter the name of a subject matter expert that the task owner can contact if he or she needs help.</span></span>
1. <span data-ttu-id="9fbf3-125">A **Feladat hivatkozása** mezőben adjon meg egy hivatkozást a feladat jellegétől függően.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-125">In the **Task link** field, enter a link, based on the nature of the task.</span></span>

> [!TIP]
> <span data-ttu-id="9fbf3-126">Annak ellenére, hogy a **Hozzárendelve a következőhöz:** mezővel a feladatlista létrehozása során a feladatot hozzárendelheti valakihez, ajánlott elkerülni a feladatok hozzárendelését a Feladatlista létrehozása során.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-126">Although you can use the **Assigned to** field to assign tasks to someone while you're creating a task list, we recommend that you avoid assigning tasks during task list creation.</span></span> <span data-ttu-id="9fbf3-127">Ehelyett a lista ez egyes üzletekhez való példányosítása után rendelje hozzá a feladatokat.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-127">Instead, assign the tasks after the list is instantiated for individual stores.</span></span>

## <a name="use-task-links-to-help-improve-worker-productivity"></a><span data-ttu-id="9fbf3-128">A feladatra mutató hivatkozásokkal javíthatja a dolgozó termelékenységét</span><span class="sxs-lookup"><span data-stu-id="9fbf3-128">Use task links to help improve worker productivity</span></span>

<span data-ttu-id="9fbf3-129">A Commerce lehetővé teszi a feladatok meghatározott pénztári műveletekhez történő csatolását, például az értékesítési jelentések futtatását, az új alkalmazotti orientációhoz kapcsolódó online képzési videó megtekintését, illetve egy háttérművelet végrehajtását.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-129">Commerce lets you link tasks to specific POS operations, such as running a sales report, viewing an online training video for new employee orientation, or performing a back-office operation.</span></span> <span data-ttu-id="9fbf3-130">Ez a funkció segít a feladattulajdonsoknak a feladatok hatékony teljesítéséhez szükséges információk beszerzésében.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-130">This feature helps task owners get the information that they need to complete a task efficiently.</span></span>

<span data-ttu-id="9fbf3-131">A feladatok létrehozása közben feladathoz kapcsolódó hivatkozások hozzáadásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-131">To add task links while you create a task, follow these steps.</span></span>

1. <span data-ttu-id="9fbf3-132">Egy meglévő feladatlista **Feladatok** gyorslapján válassza az **Szerkesztés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-132">On the **Tasks** FastTab of an existing task list, select **Edit**.</span></span>
1. <span data-ttu-id="9fbf3-133">A **Feladat szerkesztése** párbeszédpanel **Feladathivatkozás** mezőjében válasszon ki egyet vagy többet a következő lehetőségek közül:</span><span class="sxs-lookup"><span data-stu-id="9fbf3-133">In the **Edit task** dialog box, in the **Task link** field, select one or more of the following options:</span></span>

    - <span data-ttu-id="9fbf3-134">Válassza ki a **Menüelemet** a háttérben történő működés konfigurálásához, például „Termékcsomagok.”</span><span class="sxs-lookup"><span data-stu-id="9fbf3-134">Select **Menu item** to configure a back-office operation, such as "Product kits."</span></span>
    - <span data-ttu-id="9fbf3-135">Válassza ki a **Pénztári művelet** elemet pénztári művelet konfigurálásához, például „Értékesítési jelentések.”</span><span class="sxs-lookup"><span data-stu-id="9fbf3-135">Select **POS Operation** to configure a POS operation, such as "Sales reports."</span></span>
    - <span data-ttu-id="9fbf3-136">Válasszon **URL-címet** egy abszolút URL-cím beállításához.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-136">Select **URL** to configure an absolute URL.</span></span>

<span data-ttu-id="9fbf3-137">A következő ábra a **Feladatok szerkesztése** párbeszédpanel feladathivatkozások beállítását mutatja be.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-137">The following illustration shows the selection of task links in the **Edit task** dialog box.</span></span>

![A feladathivatkozások kiválasztása a feladat szerkesztése párbeszédpanelen](media/HQ-POS-Tasks-Linking.png)

### <a name="configure-a-pos-operation-so-that-it-can-be-linked-to-a-task"></a><span data-ttu-id="9fbf3-139">A pénztári művelet konfigurálása egy feladathoz való csatolás céljából</span><span class="sxs-lookup"><span data-stu-id="9fbf3-139">Configure a POS operation so that it can be linked to a task</span></span>

<span data-ttu-id="9fbf3-140">A pénztári művelet konfigurálásához egy feladathoz való csatolás céljából kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-140">To configure a POS operation so that it can be linked to a task, follow these steps.</span></span>

1. <span data-ttu-id="9fbf3-141">Lépjen a **Retail és Commerce \> Csatornabeállítás \> Pénztárbeállítás \> Pénztár \> Pénztárműveletek** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-141">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS operations**.</span></span>
1. <span data-ttu-id="9fbf3-142">Válassz a **Szerkesztés** lehetőséget, keresse meg a pénztári műveletet és jelölje be hozzá a **Feladatkezelés engedélyezése** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="9fbf3-142">Select **Edit**, find the POS operation, and then select the **Enable Task Management** check box for it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9fbf3-143">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="9fbf3-143">Additional resources</span></span>

[<span data-ttu-id="9fbf3-144">Feladatkezelés – áttekintés</span><span class="sxs-lookup"><span data-stu-id="9fbf3-144">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="9fbf3-145">Feladatkezelés konfigurálása</span><span class="sxs-lookup"><span data-stu-id="9fbf3-145">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="9fbf3-146">Feladatlisták hozzárendelése áruházakhoz vagy alkalmazottakhoz</span><span class="sxs-lookup"><span data-stu-id="9fbf3-146">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)

[<span data-ttu-id="9fbf3-147">Feladatkezelés a pénztárban</span><span class="sxs-lookup"><span data-stu-id="9fbf3-147">Task management in POS</span></span>](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
