---
title: "Előfizetési munkafolyamat áttekintése"
description: "Ez a témakör az előfizetési munkafolyamatról nyújt áttekintést."
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionGroup, SMASubscriptionCreateDialog
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9747ba144d56c9410846769e5465372c89ea111
ms.openlocfilehash: b5cff6910dcb273fc081443546676426387f6625
ms.contentlocale: hu-hu
ms.lasthandoff: 08/07/2018

---


# <a name="subscription-workflow-overview"></a><span data-ttu-id="73c87-103">Előfizetési munkafolyamat áttekintése</span><span class="sxs-lookup"><span data-stu-id="73c87-103">Subscription workflow overview</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="73c87-104">Ön egy világítási cég előfizetési felelőse, a vállalat pedig világosítóberendezések előfizetéses karbantartását kínálja.</span><span class="sxs-lookup"><span data-stu-id="73c87-104">You are the subscriptions administrator for a light company that offers subscriptions for lighting rig maintenance.</span></span> <span data-ttu-id="73c87-105">Egy ügyfél a vállalatához fordul, hogy éves előfizetést vásároljon világosítóberendezés karbantartására.</span><span class="sxs-lookup"><span data-stu-id="73c87-105">A customer contacts your company to purchase a yearly subscription for lighting rig maintenance.</span></span>

## <a name="setting-up-subscriptions"></a><span data-ttu-id="73c87-106">Előfizetések beállítása</span><span class="sxs-lookup"><span data-stu-id="73c87-106">Setting up subscriptions</span></span>

<span data-ttu-id="73c87-107">Előfizetés beállításához először hozzon létre egy előfizetési csoportot az új szolgáltatási szerződéshez vagy ellenőrzze egy előfizetési csoport meglétét.</span><span class="sxs-lookup"><span data-stu-id="73c87-107">To set up a subscription, you must first create a subscription group for the new service agreement or verify that a subscription group exists.</span></span> <span data-ttu-id="73c87-108">Ha létezik egy előfizetési csoport, be kell állítani, hogy évente számlázzon a vevőnek, és elhatárolja az értékesítési bevétel minden hónapban az év során.</span><span class="sxs-lookup"><span data-stu-id="73c87-108">If a subscription group exists, you must set it up to invoice the customer yearly and to accrue sales revenue every month of the year.</span></span> <span data-ttu-id="73c87-109">Az előfizetések beállításának módjáról bővebben lásd: [Előfizetési csoportok beállítása](set-up-subscription-groups.md).</span><span class="sxs-lookup"><span data-stu-id="73c87-109">For more information about how to set up subscriptions, see [Set up subscription groups](set-up-subscription-groups.md).</span></span>

<span data-ttu-id="73c87-110">Az előfizetési csoport létrehozása után létrehozhatja az előfizetést.</span><span class="sxs-lookup"><span data-stu-id="73c87-110">After the subscription group is created, you can create the subscription.</span></span> <span data-ttu-id="73c87-111">Szolgáltatási előfizetések létrehozásával kapcsolatos további tudnivalókat lásd: [Szolgáltatási előfizetés létrehozása előfizetési csoportból](create-service-subscriptions-from-subscription-group.md).</span><span class="sxs-lookup"><span data-stu-id="73c87-111">For more information about how to create service subscriptions, see [Create service subscriptions from a subscription group](create-service-subscriptions-from-subscription-group.md).</span></span>

## <a name="create-and-modify-subscription-transactions"></a><span data-ttu-id="73c87-112">Előfizetési tranzakciók létrehozása és módosítása</span><span class="sxs-lookup"><span data-stu-id="73c87-112">Create and modify subscription transactions</span></span>

<span data-ttu-id="73c87-113">Miután beállította az előfizetést, létrehozza az első számlázási időszak előfizetési díjtranzakcióját, ami egy év.</span><span class="sxs-lookup"><span data-stu-id="73c87-113">After you set up the subscription, you create the subscription fee transaction for the first invoicing period, which is one year.</span></span> <span data-ttu-id="73c87-114">A tranzakció típusa **Normál**.</span><span class="sxs-lookup"><span data-stu-id="73c87-114">The transactions are of the **Regular** type.</span></span> <span data-ttu-id="73c87-115">Ezért csak ott hozhat létre előfizetési tranzakciókat, ahol a kezdő dátum és a záró dátum megfelel a korábban létrehozott időszakoknak az **Időszaktípusok** képernyőn.</span><span class="sxs-lookup"><span data-stu-id="73c87-115">Therefore, you can only create subscription transactions where the from date and the to date correspond to periods that were previously created in the **Period types** form.</span></span> <span data-ttu-id="73c87-116">Díjtranzakciókkal kapcsolatos további tudnivalókat lásd: [Előfizetési díj tranzakcióinak létrehozása](create-subscription-fee-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="73c87-116">For more information about fee transactions, see [Create subscription fee transactions](create-subscription-fee-transactions.md).</span></span>

<span data-ttu-id="73c87-117">Miután beállította az előfizetést a vevőhöz, eszébe jut, hogy a tárgyalások során a szolgáltatás ajánlatokból 10 százalékos engedményt adott.</span><span class="sxs-lookup"><span data-stu-id="73c87-117">After you set up the subscription for your customer, you remember that they have negotiated a 10 percent discount on all list prices for service offerings.</span></span> <span data-ttu-id="73c87-118">Emiatt az Ön által létrehozott tranzakciós díj árát csökkentenie kell.</span><span class="sxs-lookup"><span data-stu-id="73c87-118">Therefore, you must reduce the price of the transaction fee that you created.</span></span>

<span data-ttu-id="73c87-119">Aznap később a vevő kapcsolattartója felhívja azzal, hogy bár továbbra is akarja a világosítóberendezésekre a szolgáltatási szerződést, azt tervezi, hogy egy új világosítóberendezést vezet be az adott évben később.</span><span class="sxs-lookup"><span data-stu-id="73c87-119">Later in the day, your customer contact calls to say that, although they still want the service agreement for the lighting rig, they plan to introduce a new lighting rig later in the year.</span></span> <span data-ttu-id="73c87-120">Ezért csak 2013 októberéig kér karbantartást.</span><span class="sxs-lookup"><span data-stu-id="73c87-120">Therefore, they only need maintenance coverage until October 2013.</span></span> <span data-ttu-id="73c87-121">A vevő előfizetési hónapok számának csökkentéséhez az új előfizetési díj tranzakciót hoz létre a **Csökkentési napok** típussal.</span><span class="sxs-lookup"><span data-stu-id="73c87-121">To reduce the number of months for the customer’s subscription, you create a new subscription fee transaction of the **Reduction days** type.</span></span> <span data-ttu-id="73c87-122">A napok csökkentéséről a további tudnivalókat lásd: [Előfizetési díjak napjainak csökkentése](reduce-the-days-on-subscription-fees.md).</span><span class="sxs-lookup"><span data-stu-id="73c87-122">For more information about how to reduce days, see [Reduce the days on subscription fees](reduce-the-days-on-subscription-fees.md).</span></span>

## <a name="invoice-and-accrue-subscription-transactions"></a><span data-ttu-id="73c87-123">Előfizetési tranzakciók számlázása és könyvelése</span><span class="sxs-lookup"><span data-stu-id="73c87-123">Invoice and accrue subscription transactions</span></span>

<span data-ttu-id="73c87-124">Ezzel befejezte az előfizetés beállítását, és készen áll a számlázásra a vevő számára.</span><span class="sxs-lookup"><span data-stu-id="73c87-124">You have now finished setting up the subscription, and you are ready to invoice your customer for it.</span></span> <span data-ttu-id="73c87-125">Az előfizetések számlázásának módjáról bővebben lásd: [Előfizetési tranzakciók számlázása](invoice-subscription-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="73c87-125">For more information about how to invoice subscriptions, see [Invoice subscription transactions](invoice-subscription-transactions.md).</span></span>

<span data-ttu-id="73c87-126">Két nappal később a vevő telefonál, hogy az előfizetés számlázandó USAb dollárban, nem euróban.</span><span class="sxs-lookup"><span data-stu-id="73c87-126">Two days later, your customer calls to say that the subscription should be invoiced in U.S. dollars, not Euros.</span></span> <span data-ttu-id="73c87-127">Emiatt ön jóváírást hoz létre, és a megfelelő pénznemben is létrehoz egy új előfizetési tranzakciót.</span><span class="sxs-lookup"><span data-stu-id="73c87-127">Therefore, you create a credit note, and you also create a new subscription transaction in the correct currency.</span></span> <span data-ttu-id="73c87-128">Az előfizetési tranzakciók jóváírásának módjáról bővebben lásd: [Előfizetési tranzakciók jóváírása](credit-subscription-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="73c87-128">For more information about how to credit subscription transactions, see [Credit subscription transactions](credit-subscription-transactions.md).</span></span>

<span data-ttu-id="73c87-129">A vevő előfizetéseiből minden hónap végén egy havi bevétel lekönyvelhető az eredményszámlára és a folyamatban lévő munka számlájára.</span><span class="sxs-lookup"><span data-stu-id="73c87-129">At the end of each month, one month's revenue can be accrued from the customer's subscription to the profit and loss account and the WIP accounts.</span></span> <span data-ttu-id="73c87-130">Az előfizetési bevételek könyvelésével kapcsolatos további tudnivalók: [Előfizetési bevétel könyvelése](accrue-subscription-revenue.md).</span><span class="sxs-lookup"><span data-stu-id="73c87-130">For more information about how to accrue revenue for subscriptions, see [Accrue subscription revenue](accrue-subscription-revenue.md).</span></span>

  



