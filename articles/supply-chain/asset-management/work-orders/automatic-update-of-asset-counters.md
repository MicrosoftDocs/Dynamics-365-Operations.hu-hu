---
title: Eszközök számlálóinak automatikus frissítése
description: Ez a témakör az Eszközkezelésben használt eszközszámlálók automatikus frissítését ismerteti.
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
ms.openlocfilehash: 97e6912cd37d6f82d8bf022141f04645a3364ee1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875700"
---
# <a name="automatic-update-of-asset-counters"></a><span data-ttu-id="d44c0-103">Eszközök számlálóinak automatikus frissítése</span><span class="sxs-lookup"><span data-stu-id="d44c0-103">Automatic update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="d44c0-104">Az előző részben le van írva az eszközök számlálóinak manuális regisztrálása.</span><span class="sxs-lookup"><span data-stu-id="d44c0-104">In the previous section, manual registration of asset counters is described.</span></span> <span data-ttu-id="d44c0-105">Az eszközök számlálóinak beállítását a [Számlálók](../setup-for-objects/counters.md) írják le.</span><span class="sxs-lookup"><span data-stu-id="d44c0-105">Setup of asset counters is described in [Counters](../setup-for-objects/counters.md).</span></span>

<span data-ttu-id="d44c0-106">A számlálók értékei automatikusan is frissíthetők a termelési regisztrációk alapján, a termelési órák vagy termelési mennyiségek alapján.</span><span class="sxs-lookup"><span data-stu-id="d44c0-106">Counter values can also be automatically updated from production registrations, based on production hours or production quantity.</span></span> <span data-ttu-id="d44c0-107">Ez az **Eszköz számlálóinak frissítése** során történik.</span><span class="sxs-lookup"><span data-stu-id="d44c0-107">This is done in **Update asset counters**.</span></span> <span data-ttu-id="d44c0-108">Egy vagy több eszköz frissítéséhez egy paramétert, a **Kezdő dátumot**kell beszúrni.</span><span class="sxs-lookup"><span data-stu-id="d44c0-108">You can update one or several assets by inserting one parameter, **From date**.</span></span> <span data-ttu-id="d44c0-109">Ez a paraméter határozza meg a termelési regisztrációk kezdő dátumát (az órákat vagy a termelt mennyiséget), vagyis azt a kezdő dátumot, amikor a számlálók értékét frissíteni kell.</span><span class="sxs-lookup"><span data-stu-id="d44c0-109">This parameter specifies the start date for production registrations (hours or quantity produced), meaning the start date from which counter values should be updated.</span></span>

<span data-ttu-id="d44c0-110">Minden olyan eszköz, amely egy erőforráshoz van rendelve *és* amelyekhez eszközszámláló van beállítva, amely a gyártott mennyiség vagy termelési óra alapján történő frissítésre van beállítva, az automatikus frissítés része lesz, és létrejönnek az új számlálók értékei.</span><span class="sxs-lookup"><span data-stu-id="d44c0-110">All assets that are related to a resource *and* have asset counters, which are set up to be updated based on produced quantity or production hours, will be included in an automatic update, and new counter values will be created.</span></span>

<span data-ttu-id="d44c0-111">A termelési mennyiségen alapuló számlálók, a megfelelő mennyiség és a regisztrált hibás mennyiség a számlálásban szerepel.</span><span class="sxs-lookup"><span data-stu-id="d44c0-111">Regarding counters based on production quantity, good quantity as well as error quantity registered are included in the count.</span></span> <span data-ttu-id="d44c0-112">Ha a termelt mennyiséghez használt egység eltér a számlálóban használt egységtől, akkor a program átváltja a mennyiséget a számláló egységével.</span><span class="sxs-lookup"><span data-stu-id="d44c0-112">If the unit used for produced quantity registration is different from the unit used on the counter, quantity is converted to correspond with the counter unit.</span></span>

<span data-ttu-id="d44c0-113">A fent említettek szerint az automatikus számlálók a termelési regisztrációk alapján frissíthetők.</span><span class="sxs-lookup"><span data-stu-id="d44c0-113">As mentioned above, automatic counters can be updated from production registrations.</span></span> <span data-ttu-id="d44c0-114">Ennélfogva az eszköznek, amelynél automatikusan szeretné frissíteni a számlálókat, egy erőforráshoz (gép) kell tartoznia.</span><span class="sxs-lookup"><span data-stu-id="d44c0-114">Therefore, the asset for which you want to automatically update counters must be related to a resource (machine).</span></span> <span data-ttu-id="d44c0-115">A következő leírások áttekintést nyújtanak a termelési rendelések beállításáról és feldolgozásáról (a **Gyártásvezérlés** modulban), amelyek az eszköz számlálóinak automatikus frissítéséhez használatosak az **Eszközkezelés** modulban.</span><span class="sxs-lookup"><span data-stu-id="d44c0-115">The following descriptions provide an overview of the setup and processing of production orders (in the **Production control** module), which is used as a basis for automatic update of counters on an asset in the **Asset management** module.</span></span>

<span data-ttu-id="d44c0-116">Ha az erőforrásban a gyártott mennyiségek vagy a termelési órák regisztrálva vannak, akkor frissítheti a kapcsolódó eszköz számlálóit.</span><span class="sxs-lookup"><span data-stu-id="d44c0-116">When produced quantities or production hours have been registered on the resource, you can update the related asset counters.</span></span>

1. <span data-ttu-id="d44c0-117">Kattintson az **Eszközkezelés** > **Időszakos** > **Eszközök** > **Eszköz számlálóinak frissítése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="d44c0-117">Click **Asset management** > **Periodic** > **Assets** > **Update asset counters**.</span></span>

2. <span data-ttu-id="d44c0-118">A **Kezdő dátum** mezőben válassza ki az automatikus frissítés kezdő dátumát.</span><span class="sxs-lookup"><span data-stu-id="d44c0-118">Select the start date of the automatic update in the **From date** field.</span></span>

>[!NOTE]
><span data-ttu-id="d44c0-119">Az ebben a mezőben szereplő dátum a „folyamatban lévő munka” dátuma innen: **Útvonal-tranzakciók** (**Gyártásvezérlés** > **Lekérdezések és jelentések** > **Termelés** > **Útvonal-tranzakciók** > **Tényleges dátum** mező).</span><span class="sxs-lookup"><span data-stu-id="d44c0-119">The date in this field is the "work in progress" date from **Route transactions** (**Production control** > **Inquiries and reports** > **Production** > **Route transactions** > **Physical date** field).</span></span>

3. <span data-ttu-id="d44c0-120">Ha ki szeretne választani adott eszközt, eszköztípust vagy erőforrást az automatikus frissítéshez, kattintson a **Belefoglalandó rekordok** gyorslap **Szűrő** elemére, és végezz el a megfelelő kiválasztásokat.</span><span class="sxs-lookup"><span data-stu-id="d44c0-120">If you want to select specific assets, asset types, or resources for the automatic update, click **Filter** on the **Records to include** FastTab, and make the relevant selections.</span></span>

4. <span data-ttu-id="d44c0-121">Ha szükséges, a **Futtatás a háttérben** gyorslapon szükség szerint kötegelt feladatként is beállíthatja az automatikus frissítést.</span><span class="sxs-lookup"><span data-stu-id="d44c0-121">If required, you can set up the automatic update as a batch job on the **Run in the background** FastTab.</span></span>

![1. ábra](media/12-work-orders.png)

5. <span data-ttu-id="d44c0-123">Kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="d44c0-123">Click **OK**.</span></span> <span data-ttu-id="d44c0-124">Amikor az automatikus eszközszámláló-frissítés megtörtént, az eszközhöz kapcsolódó számláló-regisztrációk láthatók itt: **Eszközökszámlálók** (**Eszközkezelés** > **Közös** > **Eszközök** > **Minden eszköz** > eszköz kiválasztása > **Számlálók** gomb).</span><span class="sxs-lookup"><span data-stu-id="d44c0-124">When the automatic asset counter update is done, you can see the counter registrations related to the asset in **Asset counters** (**Asset management** > **Common** > **Assets** > **All assets** > select asset > **Counters** button).</span></span>

<span data-ttu-id="d44c0-125">Az **Eszköz számlálóinak összegei** részben áttekintést kaphat az összes eszközhöz tartozó összes számlálótípus legutóbbi regisztrálásairól.</span><span class="sxs-lookup"><span data-stu-id="d44c0-125">In **Asset counter totals**, you can get an overview of the latest registration made on all counter types on all assets.</span></span> <span data-ttu-id="d44c0-126">Kattintson az **Eszközkezelés** > **Lekérdezések** > **Eszközök** > **Eszköz összesített érték** elemre.</span><span class="sxs-lookup"><span data-stu-id="d44c0-126">Click **Asset management** > **Inquiries** > **Assets** > **Asset aggregated value**.</span></span> <span data-ttu-id="d44c0-127">A nézet nagyon hasonló az **Eszközszámlálók** elemhez, de nem lehet hozzáadni és szerkeszteni a regisztrációkat itt: **Eszköz összesített érték**.</span><span class="sxs-lookup"><span data-stu-id="d44c0-127">The view is very similar to **Asset counters**, but you cannot add or edit registrations in **Asset aggregated value**.</span></span> <span data-ttu-id="d44c0-128">Csak áttekintésre szolgál.</span><span class="sxs-lookup"><span data-stu-id="d44c0-128">It is for overview only.</span></span>

![2. ábra](media/13-work-orders.png)


- <span data-ttu-id="d44c0-130">Továbbra is lehetőség van arra, hogy manuális számlálóregisztrációkat hozzon létre az automatikusan frissített számlálótípusokhoz.</span><span class="sxs-lookup"><span data-stu-id="d44c0-130">It is still possible to create manual counter value registrations for counter types that are automatically updated.</span></span> <span data-ttu-id="d44c0-131">A további tudnivalókat lásd: „Eszközök számlálóinak manuális frissítése”.</span><span class="sxs-lookup"><span data-stu-id="d44c0-131">Refer to the "Manual update of asset counters" section for more information.</span></span>
- <span data-ttu-id="d44c0-132">Egy másik számlálóhoz kapcsolódó számlálókat is beállíthat, ami azt jelenti, hogy a számláló frissítésekor a program automatikusan frissíti a kapcsolódó számlálókat is.</span><span class="sxs-lookup"><span data-stu-id="d44c0-132">You can set up counters related to another counter, which means that when a counter is updated, related counters are automatically updated at the same time.</span></span> <span data-ttu-id="d44c0-133">A kapcsolódó számlálók beállításáról itt talál további információt: [Számlálók](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="d44c0-133">Refer to [Counters](../setup-for-objects/counters.md) regarding setup of related counters.</span></span>
