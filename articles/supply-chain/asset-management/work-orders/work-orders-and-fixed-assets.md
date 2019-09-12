---
title: Munkarendelések és tárgyi eszközök
description: Ez a témakör a munkarendeléseket és tárgyi eszközöket mutatja be az Eszközkezelésben.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f03b7fa073c4e5338b7b5681ba7b8c9fe00a657b
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875687"
---
# <a name="work-orders-and-fixed-assets"></a><span data-ttu-id="050ff-103">Munkarendelések és tárgyi eszközök</span><span class="sxs-lookup"><span data-stu-id="050ff-103">Work orders and fixed assets</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="050ff-104">Az Eszközkezelésben az eszközök kapcsolódhatnak tárgyi eszközökhöz, és ezekhez az eszközökhöz munkarendeléseket is létrehozhat.</span><span class="sxs-lookup"><span data-stu-id="050ff-104">In Asset Management, assets can be related to fixed assets, and you can create work orders for those assets.</span></span> <span data-ttu-id="050ff-105">A funkció használatával teljeskörű áttekintést kaphat a tárgyi eszközökről, kapcsolódó befektetési projektekről és a befektetési projekteken rügzített költségekről a **Projektvezetés és könyvelés** modulban és a **Tárgyi eszközök** modulban a Dynamics 365 for Finance and Operations szolgáltatásban.</span><span class="sxs-lookup"><span data-stu-id="050ff-105">If you use this functionality, you can get a complete overview of fixed assets, related investment projects, and the costs registered on the investment projects in the **Project management and accounting** module and the **Fixed assets** module in Dynamics 365 for Finance and Operations.</span></span>

>[!NOTE]
><span data-ttu-id="050ff-106">A **Tárgyi eszköz száma** mező csak akkor tölthető ki a munkarendelési feladat projektjén, ha a munkarendelési feladat projektjén a kiválasztott projekttípus „Befektetés”.</span><span class="sxs-lookup"><span data-stu-id="050ff-106">The **Fixed asset number** field is only filled out on the work order job project if type "Investment" is selected as the project type on the work order job project.</span></span>

![1. ábra](media/24-work-orders.png)

<span data-ttu-id="050ff-108">A következő eljárás az eszközök, munkarendelések, munkarendelés-feladatok projektjei és tárgyi eszközök közötti kapcsolatot írja le.</span><span class="sxs-lookup"><span data-stu-id="050ff-108">The following procedure describes the relation between assets, work orders, work order job projects, and fixed assets.</span></span>

1. <span data-ttu-id="050ff-109">A tárgyi eszközhöz kapcsolódó eszköz létrehozása az alábbi ábrán látható módon történik.</span><span class="sxs-lookup"><span data-stu-id="050ff-109">You create an asset that you relate to a fixed asset, as shown in the figure below.</span></span>

![2. ábra](media/25-work-orders.png)

2. <span data-ttu-id="050ff-111">A munkarendelési típusok beállítása során (**Eszközkezelés** > **Beállítás** > **Munkarendelések** > **Munkarendelés-típusok**) létrehoz egy munkarendelési típust a befektetések kezelése céljából.</span><span class="sxs-lookup"><span data-stu-id="050ff-111">When you set up work order types (**Asset management** > **Setup** > **Work orders** > **Work order types**), you create a work order type for handling investments.</span></span> <span data-ttu-id="050ff-112">Lásd még: [Munkarendelés-típusok ](../setup-for-work-orders/work-order-types.md).</span><span class="sxs-lookup"><span data-stu-id="050ff-112">See also [Work order types](../setup-for-work-orders/work-order-types.md).</span></span>

![3. ábra](media/26-work-orders.png)

3. <span data-ttu-id="050ff-114">A munkarendelési projektcsoportok beállítása során (**Eszközkezelés** > **Beállítás** > **Munkarendelések** > **Projektbeállítás** > **Projektcsoport** hivatkozáson) kapcsolatot hoz létre a befektetésekhez használt munkarendelés-típus és a befejtetésekhez létrehozott projektcsoport között a **Projektvezetés és könyvelés** modulban (**Projektvezetés és könyvelés** > **Beállítás** > **Feladás** > **Projektcsoportok**).</span><span class="sxs-lookup"><span data-stu-id="050ff-114">When you set up work order project groups (**Asset management** > **Setup** > **Work orders** > **Project setup** > **Project group** link), you create a relation between the work order type used for investments and the project group created for investments in the **Project management and accounting** module (**Project management and accounting** > **Setup** > **Posting** > **Project groups**).</span></span>

![4. ábra](media/27-work-orders.png)

4. <span data-ttu-id="050ff-116">Amikor egy tárgyieszköz-objektumhoz kapcsolódó munkarendelést hoz létre, kiválasztja a befektetések kezeléséhez használt munkarendelés-típust, például „Befektetés”.</span><span class="sxs-lookup"><span data-stu-id="050ff-116">When you create a work order that relates to a fixed asset object, you select the work order type used for handling investments, for example, "Investment".</span></span>

5. <span data-ttu-id="050ff-117">A munkarendelés létrehozása után a létrejött munkarendelés-típus megjelenik az **Összes munkarendelés** pontban.</span><span class="sxs-lookup"><span data-stu-id="050ff-117">When the work order is created, the related work order type is shown in **All work orders**.</span></span>

![5. ábra](media/28-work-orders.png)

6. <span data-ttu-id="050ff-119">A munkarendelés létrehozása után a munkarendeléshez kapcsolódó projekt létrejön a **Projektvezetés és könyvelés** > **Összes projekt** pontban.</span><span class="sxs-lookup"><span data-stu-id="050ff-119">When the work order is created, the project related to the work order is created in **Project management and accounting** > **All projects**.</span></span> <span data-ttu-id="050ff-120">A projekttel kapcsolatos információkat a munkarendelésen található **Projektazonosító** hivatkozásra kattintva tekintheti meg (az **Eszközkezelés** pontban nyissa meg a munkarendelést részletes nézetben > **Sor részletei** gyorslap > **Általános** lap > **Projektazonosító** mező).</span><span class="sxs-lookup"><span data-stu-id="050ff-120">You can see project-related information by clicking the **Project ID** link on the work order (in **Asset management**, open the work order in Details view > **Line details** FastTab > **General** tab > **Project ID** field).</span></span>

![6. ábra](media/29-work-orders.png)

7. <span data-ttu-id="050ff-122">A **Tárgyi eszközök** pontban láthatja az adott tárgyi eszközhöz társított projektek áttekintését (**Tárgyi eszközök** > **Tárgyi eszközök** > **Tárgyi eszközök** > kattintson a tárgyi eszközre a **Tárgyi eszköz száma** mezőben > tekintse meg a **Kapcsolódó információk** ablaktábla tartalmát > **Társított projektek** szakasz).</span><span class="sxs-lookup"><span data-stu-id="050ff-122">In **Fixed assets**, you are able to see an overview of the projects associated with a fixed asset (**Fixed assets** > **Fixed assets** > **Fixed assets** > click on the fixed asset in the **Fixed asset number** field > view the contents in the **Related information** pane > **Associated projects** section).</span></span>

