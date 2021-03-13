---
title: Eszközök számlálóinak automatikus frissítése
description: Ez a témakör az Eszközkezelésben használt eszközszámlálók automatikus frissítését ismerteti.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d3e8619439545cf3ea42f84a6dd7ee6ffdf1026e
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021930"
---
# <a name="automatic-update-of-asset-counters"></a><span data-ttu-id="61347-103">Eszközök számlálóinak automatikus frissítése</span><span class="sxs-lookup"><span data-stu-id="61347-103">Automatic update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="61347-104">Az eszközök számlálóinak manuális regisztrálásával kapcsolatos tudnivalókat lásd: [Eszközszámlálók manuális frissítése](../work-orders/manual-update-of-asset-counters.md).</span><span class="sxs-lookup"><span data-stu-id="61347-104">For information about manual registration of asset counters, see [Manual update of asset counters](../work-orders/manual-update-of-asset-counters.md).</span></span> <span data-ttu-id="61347-105">Az eszközszámlálók beállításával kapcsolatos további információkat lásd: [Számlálók](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="61347-105">For information on how to set up asset counters, see [Counters](../setup-for-objects/counters.md).</span></span>

<span data-ttu-id="61347-106">A számlálók értékei automatikusan is frissíthetők a termelési regisztrációk alapján, a termelési órák vagy termelési mennyiségek alapján (ez a gyártott mennyiség).</span><span class="sxs-lookup"><span data-stu-id="61347-106">Counter values can also be automatically updated from production registrations, based on the production hours or production quantity (that is, the quantity that is produced).</span></span> <span data-ttu-id="61347-107">Ez a frissítés az **Eszközök frissítése** lapon történik.</span><span class="sxs-lookup"><span data-stu-id="61347-107">This update is done on the **Update asset counters** page.</span></span> <span data-ttu-id="61347-108">Egy vagy több eszköz frissítéséhez egy paramétert, a **Kezdő dátumot** kell beállítani.</span><span class="sxs-lookup"><span data-stu-id="61347-108">You can update one or several assets by setting one parameter, **From date**.</span></span> <span data-ttu-id="61347-109">Ez a paraméter a termelési regisztrációk (termelési órák vagy termelési mennyiségek) kezdődátumát határozza meg.</span><span class="sxs-lookup"><span data-stu-id="61347-109">This parameter specifies the start date for production registrations (production hours or production quantities).</span></span> <span data-ttu-id="61347-110">Más szóval azt a dátumot határozza meg, amikortól a számlálók értékét frissíteni kell.</span><span class="sxs-lookup"><span data-stu-id="61347-110">In other words, it specifies the date that counter values should be updated from.</span></span>

<span data-ttu-id="61347-111">Minden olyan eszköz, amely egy erőforráshoz van rendelve *és* amelyekhez eszközszámláló van beállítva, amely a gyártott mennyiség vagy termelési óra alapján történő frissítésre van beállítva, az automatikus frissítés része lesz.</span><span class="sxs-lookup"><span data-stu-id="61347-111">All assets that are related to a resource, *and* that have asset counters that are set up to be updated based on the production hours or production quantity, will be included in an automatic update.</span></span> <span data-ttu-id="61347-112">Új számlálóértékek jönnek létre.</span><span class="sxs-lookup"><span data-stu-id="61347-112">New counter values will be created.</span></span>

<span data-ttu-id="61347-113">A termelési mennyiségen alapuló számlálók esetében a számlálás mind a jó mennyiséget, mind a regisztrált hibás mennyiséget tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="61347-113">For counters that are based on the production quantity, the count includes both the good quantity and the error quantity that are registered.</span></span> <span data-ttu-id="61347-114">Ha a termelési mennyiséghez használt egység eltér a számlálóban használt egységtől, akkor a program átváltja a mennyiséget a számláló egységének megfelelőre.</span><span class="sxs-lookup"><span data-stu-id="61347-114">If the unit that is used for production quantity registration differs from the unit that is used for the counter, the quantity is converted so that it corresponds to the counter unit.</span></span>

<span data-ttu-id="61347-115">A fent említettek szerint az automatikus számlálók a termelési regisztrációk alapján frissíthetők.</span><span class="sxs-lookup"><span data-stu-id="61347-115">As mentioned above, automatic counters can be updated from production registrations.</span></span> <span data-ttu-id="61347-116">Ennélfogva az eszköznek, amelynél automatikusan szeretné frissíteni a számlálókat, egy erőforráshoz (gép) kell tartoznia.</span><span class="sxs-lookup"><span data-stu-id="61347-116">Therefore, the asset for which you want to automatically update counters must be related to a resource (machine).</span></span> <span data-ttu-id="61347-117">Ha az erőforrásban a gyártott mennyiségek vagy a termelési órák regisztrálva vannak, akkor frissítheti a kapcsolódó eszköz számlálóit.</span><span class="sxs-lookup"><span data-stu-id="61347-117">When produced quantities or production hours have been registered on the resource, you can update the related asset counters.</span></span>

1. <span data-ttu-id="61347-118">Válassza az **Eszközkezelés** > **Időszakos** > **Eszközök** > **Eszköz számlálóinak frissítése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="61347-118">Select **Asset management** > **Periodic** > **Assets** > **Update asset counters**.</span></span>

2. <span data-ttu-id="61347-119">A **Kezdő dátum** mezőben válassza ki az automatikus frissítés kezdő dátumát.</span><span class="sxs-lookup"><span data-stu-id="61347-119">In the **From date** field, select the start date of the automatic update.</span></span>

    >[!NOTE]
    ><span data-ttu-id="61347-120">Az ebben a mezőben szereplő dátum a „folyamatban lévő munka” dátuma innen: **Útvonal-tranzakciók** (**Gyártásvezérlés** > **Lekérdezések és jelentések** > **Termelés** > **Útvonal-tranzakciók** > **Tényleges dátum** mező).</span><span class="sxs-lookup"><span data-stu-id="61347-120">The date in this field is the "work in progress" date from **Route transactions** (**Production control** > **Inquiries and reports** > **Production** > **Route transactions** > **Physical date** field).</span></span>

3. <span data-ttu-id="61347-121">A **Szerepeltetni kívánt rekordok** gyorslapon kiválaszthatja az automatikus frissítés konkrét eszközeit, eszköztípusait vagy erőforrásait.</span><span class="sxs-lookup"><span data-stu-id="61347-121">On the **Records to include** FastTab, you can select specific assets, asset types, or resources for the automatic update.</span></span> <span data-ttu-id="61347-122">Válassza a **Szűrő** elemet, és végezze el a kapcsolódó kiválasztásokat.</span><span class="sxs-lookup"><span data-stu-id="61347-122">Select **Filter**, and make the relevant selections.</span></span>

4. <span data-ttu-id="61347-123">A **Futtatás a háttérben** gyorslapon szükség szerint kötegelt feladatként is beállíthatja az automatikus frissítést.</span><span class="sxs-lookup"><span data-stu-id="61347-123">On the **Run in the background** FastTab, you can set up the automatic update as a batch job, as you require.</span></span>

    <span data-ttu-id="61347-124">Az alábbi ábra az **Eszköszámlálók frissítése** párbeszédablak egy példáját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="61347-124">The illustration below shows an example of the **Update asset counters** dialog.</span></span>

    ![1. ábra](media/12-work-orders.png)

5. <span data-ttu-id="61347-126">Válassza ki az **OK** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="61347-126">Select **OK**.</span></span> 

<span data-ttu-id="61347-127">Az automatikus eszközszámláló-frissítést követően megtekintheti a az eszközhöz kapcsolódó számlálóregisztrációkat az **Eszköz számlálók** oldalon.</span><span class="sxs-lookup"><span data-stu-id="61347-127">After the automatic asset counter update is done, you can view the counter registrations that are related to the asset on the **Asset counters** page.</span></span> <span data-ttu-id="61347-128">Válassza ki az **Eszközkezelés** > **Közös** > **Eszközök** > **Minden eszköz** lehetőséget, válassza ki a kívánt eszközt, majd a művelet ablaktábla **Eszköz** lapjának **Megelőzés** csoportjában válassza a **Számlálók** elemet.</span><span class="sxs-lookup"><span data-stu-id="61347-128">Select **Asset management** > **Common** > **Assets** > **All assets**, select the asset, and then, on the Action Pane, on the **Asset** tab, in the **Preventive** group, select **Counters**.</span></span>

<span data-ttu-id="61347-129">Az **Eszköz összesített értéke** oldalon áttekintést kaphat az összes eszközhöz készített összes számlálótípus legutóbbi regisztrálásairól.</span><span class="sxs-lookup"><span data-stu-id="61347-129">On the **Asset aggregated value** page, you can get an overview of the latest registration that have been made on all counter types on all assets.</span></span> <span data-ttu-id="61347-130">Válassza az **Eszközkezelés** > **Lekérdezések** > **Eszközök** > **Eszköz összesített érték** elemet.</span><span class="sxs-lookup"><span data-stu-id="61347-130">Select **Asset management** > **Inquiries** > **Assets** > **Asset aggregated value**.</span></span> <span data-ttu-id="61347-131">Ez a lap hasonlít az **Eszközök számlálók** lapjára, de regisztrációkat nem lehet regisztrációkat hozzáadni és szerkeszteni.</span><span class="sxs-lookup"><span data-stu-id="61347-131">This page resembles the **Asset counters** page, but you can't add or edit registrations.</span></span> <span data-ttu-id="61347-132">Csak áttekintésre szolgál.</span><span class="sxs-lookup"><span data-stu-id="61347-132">It's for overview only.</span></span>

<span data-ttu-id="61347-133">Az alábbi ábra az **Eszközök összesített értéke** oldal egy példáját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="61347-133">The illustration below shows an example of the **Asset aggregated value** page.</span></span>

![2. ábra](media/13-work-orders.png)

<span data-ttu-id="61347-135">Vegye figyelembe az alábbiakat:</span><span class="sxs-lookup"><span data-stu-id="61347-135">Note the following points:</span></span>

- <span data-ttu-id="61347-136">Továbbra is lehetősége van arra, hogy manuális számlálóregisztrációkat hozzon létre az automatikusan frissített számlálótípusokhoz.</span><span class="sxs-lookup"><span data-stu-id="61347-136">You can still create manual counter value registrations for counter types that are automatically updated.</span></span> <span data-ttu-id="61347-137">A további tudnivalókat lásd: [Eszközök számlálóinak manuális frissítése](../work-orders/manual-update-of-asset-counters.md).</span><span class="sxs-lookup"><span data-stu-id="61347-137">For more information, see [Manual update of asset counters](../work-orders/manual-update-of-asset-counters.md).</span></span>

- <span data-ttu-id="61347-138">Lehetőség van egy másik számlálóhoz kapcsolódó számlálók beállítására is.</span><span class="sxs-lookup"><span data-stu-id="61347-138">You can set up counters that are related to another counter.</span></span> <span data-ttu-id="61347-139">Ebben az esetben a számláló frissítését követően a kapcsolódó számlálók frissítése is egyidőben megtörténik.</span><span class="sxs-lookup"><span data-stu-id="61347-139">In this case, when a counter is updated, related counters are automatically updated at the same time.</span></span> <span data-ttu-id="61347-140">Az számlálók beállításával kapcsolatos további információkat lásd: [Számlálók](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="61347-140">For more information about how to set up related counters, see [Counters](../setup-for-objects/counters.md).</span></span>

