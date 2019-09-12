---
title: Karbantartás miatti üzemkimaradás
description: Ez a cikk a karbantartás miatti üzemkimaradás Eszközkezelésben való használatát írja le.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cc79dc1b5911679586fa560142ada5add1a881d2
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918244"
---
# <a name="maintenance-downtime"></a><span data-ttu-id="e1ea2-103">Karbantartás miatti üzemkimaradás</span><span class="sxs-lookup"><span data-stu-id="e1ea2-103">Maintenance downtime</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="e1ea2-104">A karbantartás miatti üzemkimaradás regisztrációkat a munkarendelésen kiválasztott eszközre vonatkozóan lehet létrehozni.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-104">You can create maintenance downtime registrations on the asset selected on a work order.</span></span> <span data-ttu-id="e1ea2-105">Ez akkor lehet hasznos, ha a termelési területen egy vagy több gépen szeretné rögzíteni a karbantartás miatti üzemkimaradást.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-105">This is useful if you want to register maintenance downtime on one or more machines in the production area.</span></span> <span data-ttu-id="e1ea2-106">Először létre kell hoznia azokat a karbantartás miatti üzemkimaradásokat, amelyeket használni szeretne, például a meghibásodást és a tervezett leállítást.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-106">First, you create the maintenance downtime reason codes that you want to use, for example, breakdown and planned stop.</span></span> <span data-ttu-id="e1ea2-107">Ezt a **Karbantartás miatti üzemkimaradás okkódjai** helyen teheti meg.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-107">This is done in **Maintenance downtime reason codes**.</span></span> <span data-ttu-id="e1ea2-108">Ezután létrehozhatja a karbantartás miatti üzemkimaradás regisztrációkat a **Karbantartás miatti üzemkimaradás** helyen, és hozzáadhatja a megfelelő okkódokat.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-108">Next, you can create maintenance downtime registrations in **Maintenance downtime** and add the relevant reason codes.</span></span>

## <a name="create-maintenance-downtime-reason-codes"></a><span data-ttu-id="e1ea2-109">karbantartás miatti üzemkimaradás okkódjainak létrehozása</span><span class="sxs-lookup"><span data-stu-id="e1ea2-109">Create maintenance downtime reason codes</span></span>

1. <span data-ttu-id="e1ea2-110">Kattintson az **Eszközkezelés** > **Beállítás** > **Munkarendelések** > **Karbantartás miatti üzemkimaradás okkódjai** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-110">Click **Asset management** > **Setup** > **Work orders** > **Maintenance downtime reason codes**.</span></span>

2. <span data-ttu-id="e1ea2-111">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-111">Click **New**.</span></span>

3. <span data-ttu-id="e1ea2-112">Írja be az azonosítót a **Karbantartás miatti üzemkimaradás okkódja** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-112">Insert an ID in the **Maintenance downtime reason code** field.</span></span>

4. <span data-ttu-id="e1ea2-113">Adjon meg egy nevet az okkódnak a **Név** mezőben.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-113">Insert a name for the reason code in the **Name** field.</span></span>

5. <span data-ttu-id="e1ea2-114">Jelölje be a **KPI befoglalása** jelölőnégyzetet, ha azt szeretné, hogy az okkód szerepeljen az eszköz KPI-számításaiban.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-114">Select the **KPI include** check box if the reason code should be included in asset KPI calculations.</span></span> <span data-ttu-id="e1ea2-115">A tervezett termelési leállások általában nem szerepelnek a KPI-számításokban, mivel nem befolyásolják a várt teljesítményt.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-115">Generally, planned production stops should not be included in KPI calculations as they do not impact expected performance.</span></span>

6. <span data-ttu-id="e1ea2-116">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-116">Click **Save**.</span></span>

![1. ábra](media/15-work-orders.png)


<span data-ttu-id="e1ea2-118">Miután létrehozta a használni kívánt karbantartás miatti üzemkimaradás okkódokat, létrehozhatja a munkarendelésekhez és a eszközökhöz tartozó karbantartás miatti üzemkimaradás regisztrációkat.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-118">When you have created the maintenance downtime reason codes you want to use, you can create maintenance downtime registrations for work orders and assets.</span></span>


## <a name="create-maintenance-downtime-registrations"></a><span data-ttu-id="e1ea2-119">karbantartás miatti üzemkimaradás regisztrációinak létrehozása</span><span class="sxs-lookup"><span data-stu-id="e1ea2-119">Create maintenance downtime registrations</span></span>

1. <span data-ttu-id="e1ea2-120">Kattintson az **Eszközkezelés** > **Közös** > **Munkarendelések** > **Összes munkarendelés** vagy **Aktív munkarendelések** elemre.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-120">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="e1ea2-121">Válassza ki a munkarendelést, majd kattintson a **Karbantartás miatti üzemkimaradás** elemre.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-121">Select the work order and click **Maintenance downtime**.</span></span>

3. <span data-ttu-id="e1ea2-122">Kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-122">Click **New**.</span></span>

4. <span data-ttu-id="e1ea2-123">Dátum-és időintervallum beszúrása a karbantartási leállás regisztrálásához a **Kezdés** és **Befejezés** mezőkbe.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-123">Insert date and time interval for the maintenance downtime registration in the **From** and **To** fields.</span></span>

5. <span data-ttu-id="e1ea2-124">A **Befejezés** mező kihagyásakor a program automatikusan beszúrja az időtartamot órában az **Időtartam** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-124">When you leave the **To** field, the duration in hours is automatically inserted in the **Duration** field.</span></span>

6. <span data-ttu-id="e1ea2-125">Válasszon egy okkódot a **karbantartás miatti üzemkimaradás okkódja** mezőben.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-125">Select a reason code in the **maintenance downtime reason code** field.</span></span>

7. <span data-ttu-id="e1ea2-126">Ha további regisztrációkat szeretne hozzáadni, ismételje meg a 3-6. lépést.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-126">Repeat steps 3-6 if you want to add more registrations.</span></span>

8. <span data-ttu-id="e1ea2-127">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-127">Click **Save**.</span></span>


![2. ábra](media/16-work-orders.png)


<span data-ttu-id="e1ea2-129">A karbantartás miatti üzemkimaradások kiszámításához használt naptár a tárgyi eszközök és paraméterek beállításában megadott beállítástól függ.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-129">The calendar used to calculate a maintenance downtime registration depends on your selection in the setup of assets and parameters.</span></span> <span data-ttu-id="e1ea2-130">Ha ki van választva egy erőforrás egy eszközön az **Összes eszköz** > **tárgyi eszköz** gyorslap > **erőforrás** mezőjében, akkor a program a társított erőforráscsoport naptárát használja, ahogy az a következő ábrán látható.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-130">If a resource is selected on an asset in **All assets** > **Fixed asset** FastTab > **Resource** field, the calendar set up for the associated resource group is used, as shown in the following figure.</span></span>

![3. ábra](media/17-work-orders.png)


<span data-ttu-id="e1ea2-132">Ha az eszközhöz nincs kiválasztva erőforrás, akkor a program az **Eszközkezelés paraméterei** alatt kiválasztott naptárat használja a következő ábrának megfelelően.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-132">If no resource is selected on the asset, the standard calendar selected in **Asset management parameters** is used, as shown in the following figure.</span></span>

![4. ábra](media/18-work-orders.png)


<span data-ttu-id="e1ea2-134">Kattintson a **Vállalati eszközkezelés** > **Lekérdezések** > **Karbantartás miatti üzemkimaradás** lehetőségre az összes karbantartás miatti üzemkimaradás regisztráció megtekintéséhez.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-134">Click **Enterprise asset management** > **Inquiries** > **Maintenance downtime** to see an overview of all maintenance downtime registrations.</span></span>

>[!NOTE]
><span data-ttu-id="e1ea2-135">Az **Eszközkezelés** modulban használt összes naptár a szervezeti felügyelet **Szervezeti adminisztráció** > **Beállítás** > **Naptárak** > **Naptárak** helyen van beállítva.</span><span class="sxs-lookup"><span data-stu-id="e1ea2-135">All calendars used in the **Asset Management** module are set up in **Organization administration** > **Setup** > **Calendars** > **Calendars**.</span></span>

