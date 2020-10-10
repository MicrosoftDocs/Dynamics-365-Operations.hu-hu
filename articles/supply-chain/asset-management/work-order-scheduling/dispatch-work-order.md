---
title: Munkarendelés elküldése
description: Ez a témakör azt mutatja be, hogyan lehet munkarendeléseket elküldeni az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetScheduledExecution
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d46beb04923d06aa8ccec05355731aa1b3f27c5b
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889289"
---
# <a name="dispatch-work-order"></a><span data-ttu-id="0b33f-103">Munkarendelés elküldése</span><span class="sxs-lookup"><span data-stu-id="0b33f-103">Dispatch work order</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="0b33f-104">Az **Elküldés** funkciót használva egy munkarendelést vagy munkarendelési feladatot ütemezhet egy dolgozóra.</span><span class="sxs-lookup"><span data-stu-id="0b33f-104">You can schedule one work order or work order jobs to one worker using the **Dispatch** functionality.</span></span>

1. <span data-ttu-id="0b33f-105">Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.</span><span class="sxs-lookup"><span data-stu-id="0b33f-105">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="0b33f-106">A listában válassza ki a munkarendelést.</span><span class="sxs-lookup"><span data-stu-id="0b33f-106">Select the work order in the list.</span></span>

3. <span data-ttu-id="0b33f-107">Az **Általános** lapon kattintson az **Kiszállás** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="0b33f-107">On the **General** tab, click **Dispatch**.</span></span>

4. <span data-ttu-id="0b33f-108">A **Munkarendelés ütemezése** párbeszédablakban válassza ki a dolgozót a **Dolgozó** mezőben.</span><span class="sxs-lookup"><span data-stu-id="0b33f-108">In the **Schedule work order** dialog, select the worker in the **Worker** field.</span></span>

5. <span data-ttu-id="0b33f-109">Az **Ütemezési órák** mezőben be lehet szúrni a várható munkaórákat, ha a várhatót munkaórák eltérnek az előrejelzett óráktól.</span><span class="sxs-lookup"><span data-stu-id="0b33f-109">In the **Schedule hours** field, you can insert expected work hours in case expected work hours differ from forecast hours.</span></span>

6. <span data-ttu-id="0b33f-110">Az **Ütemezett kezdés** mezőben szükség esetén módosíthatja a kezdő dátumot és időpontot.</span><span class="sxs-lookup"><span data-stu-id="0b33f-110">In the **Scheduled start** field, you can edit start date and time, if required.</span></span>

7. <span data-ttu-id="0b33f-111">Ha az ütemezési folyamat figyelembe veszi a más feladatokra már ütemezett erőforrásokra vonatkozó kapacitási korlátozásokat, akkor győződjön meg róla, hogy az **Eszköz**, **Segédeszköz** és **Dolgozó** váltógomb **Igen** értékű.</span><span class="sxs-lookup"><span data-stu-id="0b33f-111">If the scheduling process should observe capacity limitations regarding resources already scheduled on other jobs, make sure that the **Asset**, **Tool**, and **Worker** toggle buttons are set to **Yes**.</span></span> <span data-ttu-id="0b33f-112">Ha meg szeretné tekinteni az ütemezési folyamat részletes adatait megtekintéséhez válassza az **Igen** beállítást a **Részletes** váltógombnál.</span><span class="sxs-lookup"><span data-stu-id="0b33f-112">If you want to see detailed information about the scheduling process, select **Yes** on the **Verbose** toggle button.</span></span> <span data-ttu-id="0b33f-113">Ez azt jelenti, hogy az információs naplóban megjelennek a munkarendelésekhez és a karbantartási dolgozókhoz tartozó számított pontszámokkal kapcsolatos részletes információk.</span><span class="sxs-lookup"><span data-stu-id="0b33f-113">This means detailed information about the calculated scores on the work order is shown in the Infolog.</span></span>

8. <span data-ttu-id="0b33f-114">Válassza az **igen** beállítást az **Ütemezés kihagyása** választógombnál, ha a naptárban a lezárt napokat figyelmen kívül szeretné hagyni (a következőkre vonatkozik eszköz, dolgozó és szerszámok).</span><span class="sxs-lookup"><span data-stu-id="0b33f-114">Select **Yes** on the **Ignore schedule** toggle button to ignore closed days in the calendar (applies to asset, worker, and tools).</span></span> <span data-ttu-id="0b33f-115">Válassza az **igen** beállítást az **Ütemezett végrehajtás figyelmen kívül hagyása** választógombon, ha figyelmen kívül hagyja azokat a korlátozásokat, amelyek ki lettek választva az ütemezéssel kapcsolatos munkarendelésen.</span><span class="sxs-lookup"><span data-stu-id="0b33f-115">Select **Yes** on the **Ignore scheduled execution** toggle button to ignore limitations that may have been selected on the work order regarding scheduling.</span></span> 

    <span data-ttu-id="0b33f-116">Az ütemezett végrehajtás beállításával kapcsolatos tudnivalókat lásd az [Ütemezett végrehajtás](../setup-for-work-orders/scheduled-execution.md) szakaszban.</span><span class="sxs-lookup"><span data-stu-id="0b33f-116">For information on the setup of scheduled execution, see the [Scheduled execution](../setup-for-work-orders/scheduled-execution.md) section.</span></span>

9. <span data-ttu-id="0b33f-117">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="0b33f-117">Click **OK**.</span></span> <span data-ttu-id="0b33f-118">A Munkarendelés életciklusállapotát automatikusan frissíti a program, hogy az **Ütemezett** életciklus állapotra, amely az **Eszközkezelés** > **Beállítás** > **Munkarendelések** > **Életciklus-modellek** helyen van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="0b33f-118">The work order lifecycle state is automatically updated to the **Scheduled** lifecycle state specified **Asset management** > **Setup** > **Work orders** > **Lifecycle models**.</span></span>

<span data-ttu-id="0b33f-119">Az alábbi ábra egy példát mutat be a kiszállási beállításokra az **Ütemezett munkarendelés** párbeszédpanelen.</span><span class="sxs-lookup"><span data-stu-id="0b33f-119">The figure below shows an example of dispatch selections in the **Schedule work order** dialog.</span></span>

![1. ábra](media/04-work-order-scheduling.png)

[!NOTE]
<span data-ttu-id="0b33f-121">Ha törölni szeretné az ütemezést egy munkarendelésen, akkor ezt úgy teheti meg, hogy a **Minden munkarendelés** alatt kijelöli a munkarendelést, majd az **Általános** lapon az **Ütemezés törlése** elemre kattint. Ne felejtse el manuálisan frissíteni a munkarendelés életciklus-állapotát, ha törli az ütemezést.</span><span class="sxs-lookup"><span data-stu-id="0b33f-121">If you want to delete the schedule on a work order, select the work order in **All work orders**, and then click **Delete schedule** on the **General** tab. Remember to manually update the work order lifecycle state if you delete the schedule.</span></span>

