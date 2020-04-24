---
title: Eszköz szolgáltatásszintjei
description: Ez a témakör bemutatja az Eszközkezelés eszközökhöz tartozó szolgáltatási szintjeit.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35e7a55b1ba230be6bb72b20fcd805ea061b648e
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216574"
---
# <a name="asset-service-levels"></a><span data-ttu-id="7b1cc-103">Eszköz szolgáltatásszintjei</span><span class="sxs-lookup"><span data-stu-id="7b1cc-103">Asset service levels</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="7b1cc-104">Ez a témakör bemutatja az Eszközkezelés eszközökhöz tartozó szolgáltatási szintjeit.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-104">This topic explains asset service levels in Asset Management.</span></span> <span data-ttu-id="7b1cc-105">Az eszköz szolgáltatási szintje az eszközökhöz kapcsolódnak, és átkerülnek a karbantartási kérésekre és munkarendelésekre.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-105">Asset service levels are related to assets, and are transferred to maintenance requests and work orders.</span></span> <span data-ttu-id="7b1cc-106">A Munkarendelés ütemezése során a munkarendelések prioritásának kiszámításához használatosak.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-106">They are used to calculate the priority of work orders during work order scheduling.</span></span> <span data-ttu-id="7b1cc-107">Az eszköz szolgáltatási szintjei módosíthatók, ha szükségesek a változtatások.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-107">Asset service levels can be changed, if changes are required.</span></span>

<span data-ttu-id="7b1cc-108">A munkarendelés ütemezéséhez szükséges értékelési pontszámok kiszámításával kapcsolatos beállításra vonatkozó további információkat az [Eszközkezelés paraméterei](../setup-for-objects/enterprise-asset-management-parameters.md) részben találhat.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-108">For more information about the setup that is related to the calculation of rating scores for work order scheduling, see [Asset Management parameters](../setup-for-objects/enterprise-asset-management-parameters.md).</span></span> <span data-ttu-id="7b1cc-109">Az eszköz szolgáltatási szintjéhez legalább egy alapértelmezett rekordot be kell állítania.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-109">You must set up at least one default record for the asset service level.</span></span> <span data-ttu-id="7b1cc-110">Ez az alapértelmezett rekord akkor használatos, ha a Munkarendelés ütemezése során nem találhatók egyéb egyezések.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-110">This default record is used if no other match is found during work order scheduling.</span></span>

<span data-ttu-id="7b1cc-111">**1. példa** : Az alapértelmezett szolgáltatási szint, amely akkor használatos, ha a rendszer nem talál más egyezést.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-111">**Example 1:** The default service level that is used if no other match is found.</span></span> <span data-ttu-id="7b1cc-112">Ebben a rekordban csak szolgáltatási szintet lehet kiválasztani.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-112">In this record, you select only a service level.</span></span>

<span data-ttu-id="7b1cc-113">**2. példa** : Egy magas szolgáltatási szint, amely a Volvo teherautó-motor feladatainak ütemezéséhez használatos.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-113">**Example 2:** A high service level that is used to schedule jobs for a Volvo truck engine.</span></span> <span data-ttu-id="7b1cc-114">Ebben a rekordban kiválaszthatja a megfelelő eszköztípust ( Például **Teherautó-motor**), a gyártót (**Volvo**) és szolgáltatási szintet.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-114">In this record, you select a relevant asset type (such as **Truck Engine**), a manufacturer (**Volvo**), and a service level.</span></span>

## <a name="set-up-asset-service-levels"></a><span data-ttu-id="7b1cc-115">Eszköz szolgáltatásszintjeinek beállítása</span><span class="sxs-lookup"><span data-stu-id="7b1cc-115">Set up asset service levels</span></span>

1. <span data-ttu-id="7b1cc-116">Válassza ki az **Eszközkezelés** \> **Beállítás** \> **Eszköz szolgáltatási szintjei** elemet.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-116">Select **Asset management** \> **Setup** \> **Asset service levels**.</span></span>
2. <span data-ttu-id="7b1cc-117">Válassza az **Új** lehetőséget egy rekord létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-117">Select **New** to create a record.</span></span>
3. <span data-ttu-id="7b1cc-118">Az eszköz szolgáltatási szintjéhez szüksége részletességi szinttől függően végezze el a releváns kiválasztásokat a következő mezőkben: **munkavégzési helyszín**, **Eszköztípus**, **Gyártó**, **Modell**, **Eszköz**, **Munkarendelés típusa** és **Szolgáltatási szint**.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-118">Depending on the detail level that is required for the asset service level, make relevant selections in the **Functional location**, **Asset type**, **Manufacturer**, **Model**, **Asset**, **Work order type**, and **Service level** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7b1cc-119">Amikor az eszköz szolgáltatási szintjét karbantartási kérésekhez és munkarendelésekhez használják, az Eszközkezelés végigmegy az összes eszközszolgáltatási szinthez kapcsolódó rekordon lehetséges egyezést keresve.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-119">When the asset service level is used for maintenance requests and work orders, Asset Management goes through all asset service level records to check for a possible match.</span></span> <span data-ttu-id="7b1cc-120">Mindig a leginkább meghatározott kombinációt ellenőrzi először.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-120">It always checks the most specific combination first.</span></span> <span data-ttu-id="7b1cc-121">Más szóval az Eszközkezelés modul először a **Munkarendelés típusa** mezővel való egyezést ellenőrzi.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-121">In other words, Asset Management first checks for a match for the **Work order type** field.</span></span> <span data-ttu-id="7b1cc-122">Ha nem talál egyezést, akkor az **Eszköz** mezővel való egyezést ellenőrzi, és így tovább.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-122">If no match is found, it checks for a match for the **Asset** field, and so on.</span></span> <span data-ttu-id="7b1cc-123">Ahogy az az **Eszköz szolgáltatási szintje** oldal elrendezésében is látható, ez a viselkedésmód azt jelenti, hogy a legspecifikusabb kombináció megkereséséhez az Eszközkezelés minden egyes rekordot jobbról balra ellenőriz egyezést keresve.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-123">As you can see in the layout of the **Asset service levels** page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="7b1cc-124">Ha nem talál egyezést, akkor a rendszer azt az alapértelmezett rekordot használja, amely azon mezők egyikében sem tartalmaz választási lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-124">If no match is found, the default record that has no selections in those fields is used.</span></span>

4. <span data-ttu-id="7b1cc-125">A **Szolgáltatási szint** mezőben válassza ki azt a számot, amely a szolgáltatási szintet (prioritást) jelzi.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-125">In the **Service level** field, select a number that indicates the service level (priority).</span></span>


> [!NOTE]
> <span data-ttu-id="7b1cc-126">Ha módosítja az eszköz szolgáltatási szintjéhez tartozó rekordot az **Eszköz szolgáltatási szintje** oldalon , miután már használta egy munkarendelésen, a karbantartási kérések és munkarendelések szolgáltatási szintje nem frissül ennek megfelelően.</span><span class="sxs-lookup"><span data-stu-id="7b1cc-126">If you change an asset service level record on the **Asset service levels** page after you've already used it on a work order, the service level on maintenance requests and work orders isn't updated accordingly.</span></span>
