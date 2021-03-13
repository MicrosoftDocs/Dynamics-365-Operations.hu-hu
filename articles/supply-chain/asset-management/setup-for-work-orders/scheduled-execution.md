---
title: Ütemezett végrehajtás
description: Ez a témakör azt ismerteti, hogyan lehet ütemezett végrehajtást beállítani az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a6d1761202697f62421bbf288c7e22efe559a986
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5022407"
---
# <a name="scheduled-execution"></a><span data-ttu-id="91940-103">Ütemezett végrehajtás</span><span class="sxs-lookup"><span data-stu-id="91940-103">Scheduled execution</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="91940-104">Az ütemezett végrehajtás beállításához a munkarendelés szolgáltatási szintjét is használhatja.</span><span class="sxs-lookup"><span data-stu-id="91940-104">You can use work order service levels to set up scheduled execution.</span></span> <span data-ttu-id="91940-105">(A munkarendelés szolgáltatási szintjeivel kapcsolatos további tudnivalókat lásd itt: [Szolgáltatási szint és leírás](service-level-and-description.md).) Az ütemezett végrehajtás kellő rugalmasságot ad a karbantartási dolgozók munkájának megtervezéséhez, mivel részletesebb vagy kevésbé részletes követelményeket is beállíthat ahhoz az időszakhoz, amely alatt a munkarendelést végre kell hajtani.</span><span class="sxs-lookup"><span data-stu-id="91940-105">(For more information about work order service levels, see [Service level and description](service-level-and-description.md).) Scheduled execution provides flexibility in work planning for maintenance workers, because you can set up more detailed or less detailed requirements for the interval that a work order should be completed during.</span></span> <span data-ttu-id="91940-106">Előfordulhat például, hogy az a karbantartási dolgozó, aki a vártnál gyorsabban végez munkájával az egyik gyártólétesítményben, elkezdhet egy másik, az aktuális hétre tervezett, de nem feltétlenül az aktuális napra ütemezett feladatot.</span><span class="sxs-lookup"><span data-stu-id="91940-106">For example, a maintenance worker who completes a job faster than expected in a production facility might be able to move on to another nearby job that was planned for the current week but not necessarily for the current day.</span></span> <span data-ttu-id="91940-107">Ez a megközelítés lehetővé teszi a dolgozók munkatervének és a feladatok befejezésének optimalizálását.</span><span class="sxs-lookup"><span data-stu-id="91940-107">This approach allows for optimization of worker planning and job completion.</span></span>

<span data-ttu-id="91940-108">A munkarendelésekhez kapcsolódó ütemezett végrehajtás beállítása lehet általános vagy specifikus.</span><span class="sxs-lookup"><span data-stu-id="91940-108">Scheduled execution setup, which is related to work orders, can be generic or specific.</span></span> <span data-ttu-id="91940-109">Beállíthat olyan általános sorokat, amelyek nem korlátozódnak meghatározott munkarendelés-típusokra, eszköztípusokra stb.</span><span class="sxs-lookup"><span data-stu-id="91940-109">You can set up generic lines that aren't limited to specific work order types, asset types, and so on.</span></span> <span data-ttu-id="91940-110">Azt is megteheti, hogy olyan ütemezett végrehajtási sorokat hoz létre, amelyek egy adott munkarendelés-típusra, eszköztípusra stb. vonatkoznak.</span><span class="sxs-lookup"><span data-stu-id="91940-110">Alternatively, you can create scheduled execution lines that apply to a specific work order type, asset type, maintenance job type, and so on.</span></span>

1. <span data-ttu-id="91940-111">Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Munkarendelések** \> **Ütemezett végrehajtás** elemet.</span><span class="sxs-lookup"><span data-stu-id="91940-111">Select **Asset management** \> **Setup** \> **Work orders** \> **Scheduled execution**.</span></span>
2. <span data-ttu-id="91940-112">Ha új ütemezett végrehajtást szeretne létrehozni, kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="91940-112">Select **New** to create a scheduled execution line.</span></span>
3. <span data-ttu-id="91940-113">A **Munkavégzési helyszín**, a **Munkarendelés típusa**, az **Eszköztípus**, a **Gyártó**, a **Modell**, a **Karbantartási feladat típuskategóriája**, a **Karbantartásifeladat-típusok**, a **Karbantartási feladat típusának változata**, valamint a **Kereskedelem** mezőben válassza ki a szükséges értékeket.</span><span class="sxs-lookup"><span data-stu-id="91940-113">In the **Functional location**, **Work order type**, **Asset type**, **Manufacturer**, **Model**, **Maintenance job type category**, **Maintenance job type**, **Maintenance job type variant**, and **Trade** fields, select values as you require.</span></span>
4. <span data-ttu-id="91940-114">Válassza ki a munkarendelés szolgáltatási szintjét a **Szolgáltatási szint** mezőben.</span><span class="sxs-lookup"><span data-stu-id="91940-114">In the **Service level** field, select a work order service level.</span></span> <span data-ttu-id="91940-115">Ha üresen hagyja ezt a mezőt, akkor a legáltalánosabb típusú ütemezési végrehajtási sort alkalmazhatja.</span><span class="sxs-lookup"><span data-stu-id="91940-115">If you leave this field blank, you make the most generic type of scheduled execution line.</span></span> <span data-ttu-id="91940-116">Ha szeretne példát látni az általános sorhoz, tekintse meg a következő illusztráció első rekordját.</span><span class="sxs-lookup"><span data-stu-id="91940-116">For an example of a generic line, see the first record in the illustration that follows.</span></span> <span data-ttu-id="91940-117">Ez a sor minden olyan munkarendelést aktivál, amelyekhez nem tartozik egy adott dátumra és időpontra ütemezendő munkarendelési szolgáltatási szint.</span><span class="sxs-lookup"><span data-stu-id="91940-117">That line enables all work orders that have no work order service level to be scheduled for a specific date and time.</span></span>
5. <span data-ttu-id="91940-118">Válassza ki az időintervallumot az **Ütemezett végrehajtás** mezőben.</span><span class="sxs-lookup"><span data-stu-id="91940-118">In the **Scheduled execution** field, select the time interval.</span></span>
6. <span data-ttu-id="91940-119">Válassza a **Mentés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="91940-119">Select **Save**.</span></span>

![Ütemezett végrehajtás](media/20-setup-for-work-orders.png)
