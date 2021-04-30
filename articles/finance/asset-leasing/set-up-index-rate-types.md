---
title: Referencia-kamatláb beállítása
description: Ez a témakör ismerteti a referencia-kamatlábak beállítását. A referencia-kamatláb szükségesek, ha a szervezet referencia-kamatlábakkal társítja a lízingdíjakat.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseIndexRateType
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 40f230a9d69a142b18eb27a2d5e420dbadc600d2
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5880960"
---
# <a name="set-up-index-rates"></a><span data-ttu-id="a39f7-104">Referencia-kamatláb beállítása</span><span class="sxs-lookup"><span data-stu-id="a39f7-104">Set up index rates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a39f7-105">Ha a lízingfizetések indextől függenek, az referencia-kamatláb-típusok hozzáadhatók és karbantarthatók a rendszerben.</span><span class="sxs-lookup"><span data-stu-id="a39f7-105">If lease payments depend on an index, the index rate types can be added and maintained in the system.</span></span> <span data-ttu-id="a39f7-106">Ha át szeretné értékelni a lízingkifizetéseket a **Referencia-kamatláb típusa** oldalról, az referencia-kamatláb átértékelési folyamat az átértékelés dátumától számított legutóbbi referencia-kamatlábat használja.</span><span class="sxs-lookup"><span data-stu-id="a39f7-106">To revalue the lease payments from the **Index rate type** page, the index rate revaluation process uses the most recent index rate from the date of revaluation.</span></span>

<span data-ttu-id="a39f7-107">Referencia-kamatláb-típusok és referencia-kamatlábak hozzáadásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a39f7-107">To add index rate types and index rates, follow these steps.</span></span>

1. <span data-ttu-id="a39f7-108">Nyissa meg az **Eszközlízing \> Beállítás \> Referencia-kamatláb típusa** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a39f7-108">Go to **Asset leasing \> Setup \> Index rate type**.</span></span>
2. <span data-ttu-id="a39f7-109">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a39f7-109">Select **New**.</span></span>
3. <span data-ttu-id="a39f7-110">A megfelelő mezőkben adja meg a díj típusát és a referencia-kamatláb nevét.</span><span class="sxs-lookup"><span data-stu-id="a39f7-110">In the appropriate fields, enter the rate type and the name of the index rate.</span></span>
4. <span data-ttu-id="a39f7-111">Új referencia-kamatláb érték hozzáadásához jelölje ki a referencia-kamatláb típusát, majd a **Hozzáadás** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a39f7-111">To add a new index rate value, select the index rate type, and then select **Add**.</span></span>
5. <span data-ttu-id="a39f7-112">Válassza ki a díj kezdő dátumát, és válassza ki a díjértéket.</span><span class="sxs-lookup"><span data-stu-id="a39f7-112">Select the effective start date of the rate, and select the rate value.</span></span>

<span data-ttu-id="a39f7-113">**Referencia-kamatláb értékkülönbség** vagy **Referencia-kamatláb érték** lehetőséget kell választania referencia-kamatláb-módszerként.</span><span class="sxs-lookup"><span data-stu-id="a39f7-113">You must select either **Index rate value difference** or **Index rate value** as the index rate method.</span></span>

- <span data-ttu-id="a39f7-114">Válassza ki a **Referencia-kamatláb értékkülönbség** módszerét az új lízingkifizetés kiszámításához a kezdő dátum referencia-kamatlába és a legutóbbi referencia-kamatláb közötti különbség alapján.</span><span class="sxs-lookup"><span data-stu-id="a39f7-114">Select the **Index rate value difference** method to calculate a new lease payment, based on the difference between the index rate on the start date and the most recent index rate.</span></span> <span data-ttu-id="a39f7-115">A referencia-kamatláb az **Referencia-kamatláb (%)** mezőben van meghatározva.</span><span class="sxs-lookup"><span data-stu-id="a39f7-115">The index rate is defined in the **Index rate (%)** field.</span></span>
- <span data-ttu-id="a39f7-116">Válassza ki a **Referencia-kamatláb érték** módszerét a lízingkifizetés kiszámításához a **Referencia-kamatláb (%)** mezőben megadott százalék használatával.</span><span class="sxs-lookup"><span data-stu-id="a39f7-116">Select the **Index rate value** method to calculate the lease payment by using the percentage that is specified in the **Index rate (%)** field.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
