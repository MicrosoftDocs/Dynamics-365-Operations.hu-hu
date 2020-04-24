---
title: Munkarendelések és tárgyi eszközök
description: Ez a témakör a munkarendeléseket és tárgyi eszközöket mutatja be az Eszközkezelésben.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ca7a5d88de4308d7be9c1bc749b9dbf1da027c2c
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208823"
---
# <a name="work-orders-and-fixed-assets"></a><span data-ttu-id="50261-103">Munkarendelések és tárgyi eszközök</span><span class="sxs-lookup"><span data-stu-id="50261-103">Work orders and fixed assets</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="50261-104">Az Eszközkezelésben az eszközök kapcsolódhatnak tárgyi eszközökhöz, és ezekhez az eszközökhöz munkarendeléseket is létrehozhat.</span><span class="sxs-lookup"><span data-stu-id="50261-104">In Asset Management, assets can be related to fixed assets, and you can create work orders for those assets.</span></span> <span data-ttu-id="50261-105">A funkció használatával teljeskörű áttekintést kaphat a tárgyi eszközökről, kapcsolódó befektetési projektekről és a befektetési projekteken rögzített költségekről a **Projektvezetés és könyvelés** modulokban és a **Tárgyi eszközök** modulokban a Microsoft Dynamics 365 for Finance and Operations szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="50261-105">If you use this functionality, you can get a complete overview of fixed assets, related investment projects, and the costs that are registered on the investment projects in the **Project management and accounting** and **Fixed assets** modules in Microsoft Dynamics 365 for Finance and Operations.</span></span>

>[!NOTE]
><span data-ttu-id="50261-106">A **Tárgyi eszköz száma** mező csak akkor van beállítva munkarendelési feladat projektjén, ha a munkarendelési feladat projektjén a kiválasztott projekttípus **Befektetés**.</span><span class="sxs-lookup"><span data-stu-id="50261-106">The **Fixed asset number** field on the work order job project is set only if **Investment** is selected as the project type on the work order job project.</span></span>

<span data-ttu-id="50261-107">Az alábbi ábra a **Projekt menedzsment és a könyvelés** modul egy beruházási projektje, valamint egy munkarendelési feladatprojekt közötti kapcsolatot mutatja.</span><span class="sxs-lookup"><span data-stu-id="50261-107">The illustration below shows the relation between an investment project in the **Project management and accounting** module and a work order job project.</span></span>

![1. ábra](media/24-work-orders.png)

<span data-ttu-id="50261-109">A következő eljárás az eszközök, munkarendelések, munkarendelés-feladatok projektjei és tárgyi eszközök közötti kapcsolatot írja le.</span><span class="sxs-lookup"><span data-stu-id="50261-109">The following procedure describes the relation between assets, work orders, work order job projects, and fixed assets.</span></span>

1. <span data-ttu-id="50261-110">Egy tárgyi eszközhöz kapcsolódó eszközt hoz létre.</span><span class="sxs-lookup"><span data-stu-id="50261-110">You create an asset that you relate to a fixed asset.</span></span>

![2. ábra](media/25-work-orders.png)

2. <span data-ttu-id="50261-112">A munkarendelési típusok beállítása során a **Munkarendelés-típusok** oldalon (**Eszközkezelés** > **Beállítás** > **Munkarendelések** > **Munkarendelés-típusok**) létrehoz egy munkarendelési típust a befektetések kezelése céljából.</span><span class="sxs-lookup"><span data-stu-id="50261-112">When you set up work order types on the **Work order types** page (**Asset management** > **Setup** > **Work orders** > **Work order types**), you create a work order type for handling investments.</span></span> <span data-ttu-id="50261-113">Lásd még: [Munkarendelés-típusok ](../setup-for-work-orders/work-order-types.md).</span><span class="sxs-lookup"><span data-stu-id="50261-113">See also [Work order types](../setup-for-work-orders/work-order-types.md).</span></span>

![3. ábra](media/26-work-orders.png)

3. <span data-ttu-id="50261-115">A munkarendelési projektcsoportok beállítása során a **Projektcsoport** lapon a **Munkarendelés projektbeállítása** oldalon (**Eszközkezelés** > **Beállítás** > **Munkarendelések** > **Projektbeállítás** hivatkozáson) kapcsolatot hoz létre a befektetésekhez használt munkarendelés-típus és a befejtetésekhez létrehozott projektcsoport között a Projektvezetés és könyvelés modulban a **Projektcsoportok** oldalon a **Projektmenedzsment és könyvelés** modulban (**Projektvezetés és könyvelés** > **Beállítás** > **Feladás** > **Projektcsoportok**).</span><span class="sxs-lookup"><span data-stu-id="50261-115">When you set up work order project groups on the **Project group** tab of the **Work order project setup** page (**Asset management** > **Setup** > **Work orders** > **Project setup**), you create a relation between the work order type that is used for investments and the project group that was created for investments on the **Project groups** page in the **Project management and accounting** module (**Project management and accounting** > **Setup** > **Posting** > **Project groups**).</span></span>

![4. ábra](media/27-work-orders.png)

4. <span data-ttu-id="50261-117">Amikor egy tárgyieszköz-objektumhoz kapcsolódó munkarendelést hoz létre, kiválasztja a befektetések kezeléséhez használt munkarendelés-típust, például **Befektetés**.</span><span class="sxs-lookup"><span data-stu-id="50261-117">When you create a work order that is related to a fixed asset, you select the work order type that is used to handle investments, such as **Investment**.</span></span>

5. <span data-ttu-id="50261-118">A munkarendelés létrehozása után a létrejött munkarendelés-típus megjelenik az **Összes munkarendelés** oldalon.</span><span class="sxs-lookup"><span data-stu-id="50261-118">When the work order is created, the related work order type is shown on the **All work orders** page.</span></span>

![5. ábra](media/28-work-orders.png)

6. <span data-ttu-id="50261-120">A Munkarendelés létrehozásakor a munkarendeléshez kapcsolódó projekt létrejön az **Összes projekt** oldalon a **Projektmenedzsment és könyvelés** modul modulban (**Projektmenedzsment és könyvelés** > **Projektek** > **Minden projekt**).</span><span class="sxs-lookup"><span data-stu-id="50261-120">When the work order is created, the project that is related to the work order is created on the **All projects** page in the **Project management and accounting** module (**Project management and accounting** > **Projects** > **All projects**).</span></span> <span data-ttu-id="50261-121">Ha meg szeretné tekinteni a projekttel kapcsolatos adatokat, válassza ki a hivatkozást a **Projekt azonosítója** mezőben, az **Általános** lapon a **Sor részletei** gyorslapon a részletek nézetben az **Összes munkarendelés lapon** az **Eszközkezelés** modulban (**Eszközkezelés** > **Közös** > **Munkarendelések** > **Minden munkarendelés**).</span><span class="sxs-lookup"><span data-stu-id="50261-121">To view project-related information, select the link in the **Project ID** field on the **General** tab on the **Line details** FastTab in the details view of the **All work orders** page in the **Asset management** module (**Asset management** > **Commom** > **Work orders** > **All work orders**).</span></span>

![6. ábra](media/29-work-orders.png)

7. <span data-ttu-id="50261-123">A tárgyi eszközhöz társított projektek áttekintésének megtekintéséhez válassza a **Tárgyi eszközök** > **Tárgyi eszközök** > **Tárgyi eszközök** elemet, majd a **Tárgyi eszköz száma** mezőben válassza ki a tárgyi eszköz hivatkozását a megnyitásához a részletek nézetben.</span><span class="sxs-lookup"><span data-stu-id="50261-123">To see an overview of the projects associated with a fixed asset, select **Fixed assets** > **Fixed assets** > **Fixed assets**, and then, in the **Fixed asset number** field, select the link for the fixed asset to open the details view.</span></span> <span data-ttu-id="50261-124">Bontsa ki a lap jobb oldalán a **Kapcsolódó információk** ablaktáblát, és válassza ki a **Társított projektek** gyorslapot.</span><span class="sxs-lookup"><span data-stu-id="50261-124">Expand the **Related information** pane on the right side of the page, and select the **Associated projects** FastTab.</span></span>

