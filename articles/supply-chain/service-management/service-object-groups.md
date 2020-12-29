---
title: A szolgáltatás tárgyainak csoportjai
description: Az objektumcsoportok jól használhatók az objektumadatok rendezésére és szűrésére a jelentéseknél és a statisztikáknál.
author: ShylaThompson
manager: tfehr
ms.date: 05/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4438487fa234cf093b557bca9455717b2cd3ca0b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429206"
---
# <a name="service-object-groups"></a><span data-ttu-id="906ec-103">A szolgáltatás tárgyainak csoportjai</span><span class="sxs-lookup"><span data-stu-id="906ec-103">Service object groups</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="906ec-104">Az objektumcsoportok jól használhatók az objektumadatok rendezésére és szűrésére a jelentéseknél és a statisztikáknál.</span><span class="sxs-lookup"><span data-stu-id="906ec-104">Object groups are useful for sorting and filtering the data about objects for reports and statistics.</span></span> <span data-ttu-id="906ec-105">Csoportosíthatja például a tárgyakat földrajzi hely vagy típus szerint.</span><span class="sxs-lookup"><span data-stu-id="906ec-105">For example, you can group objects by geographical location or by type.</span></span>

## <a name="group-by-geographical-location"></a><span data-ttu-id="906ec-106">Csoportosítás földrajzi elhelyezkedés szerint</span><span class="sxs-lookup"><span data-stu-id="906ec-106">Group by geographical location</span></span>

<span data-ttu-id="906ec-107">Ezzel a csoportosítással megjelenítheti, hogy hol helyezkednek el a vállalat által szervizelt különböző tárgyak.</span><span class="sxs-lookup"><span data-stu-id="906ec-107">You can use this grouping method to show where the various different objects that your company services are located.</span></span> <span data-ttu-id="906ec-108">Az objektumok földrajzi elhelyezkedés szerinti csoportosítása hasznos lehet akkor is, ha például egy adott országban vagy területen kell meghatároznia, hogy milyen tárgyakat szervizeltek már.</span><span class="sxs-lookup"><span data-stu-id="906ec-108">Grouping objects by geographical location can also be useful if, for example, you must identify the objects that your company already provides services for in a particular country/region.</span></span>

## <a name="example"></a><span data-ttu-id="906ec-109">Példa</span><span class="sxs-lookup"><span data-stu-id="906ec-109">Example</span></span>

<span data-ttu-id="906ec-110">Egy Belgiumban lévő ügyfél felhívja szervizközpontját, és szolgáltatási szerződést szeretne kötni az ABC tárgyra.</span><span class="sxs-lookup"><span data-stu-id="906ec-110">A customer from Belgium calls your service center and wants to create a service agreement for an object, ABC.</span></span> <span data-ttu-id="906ec-111">Hozzárendelt egy tárgycsoportot a Belgium földrajzi helyhez minden olyan tárgy esetében, amelyeknek szervizelése Belgiumban történik.</span><span class="sxs-lookup"><span data-stu-id="906ec-111">You have attached an object group for geographical location, Belgium, to all objects that are serviced in Belgium.</span></span> <span data-ttu-id="906ec-112">Ha ezt a csoportot használja szűrőként, akkor gyorsan keresést végezhet, és megtekintheti, hogy rendelkezik-e már rekorddal az ABC tárgyhoz a programban, vagy új tárgyat kell beállítania.</span><span class="sxs-lookup"><span data-stu-id="906ec-112">By using this group as a filter, you can quickly search to see whether you already have a record for ABC in the program, or whether you must set up a new object.</span></span> 

## <a name="group-by-type"></a><span data-ttu-id="906ec-113">Csoportosítás típus szerint</span><span class="sxs-lookup"><span data-stu-id="906ec-113">Group by type</span></span>

<span data-ttu-id="906ec-114">Ezzel a csoportosítási móddal kimutathatja, hogy milyen tárgytípusokon végez szolgáltatást a vállalat.</span><span class="sxs-lookup"><span data-stu-id="906ec-114">You can use this grouping method to show the types of objects that your company services.</span></span> <span data-ttu-id="906ec-115">Az objektumok típus szerinti csoportosítása hasznos lehet például akkor is, ha a meglévő hasonló objektumok alapján egy új objektumot szeretne létrehozni a programban.</span><span class="sxs-lookup"><span data-stu-id="906ec-115">Grouping objects by type can also be useful if, for example, you want to create a new object based on similar objects that already exist in the program.</span></span>

## <a name="example"></a><span data-ttu-id="906ec-116">Példa</span><span class="sxs-lookup"><span data-stu-id="906ec-116">Example</span></span>

<span data-ttu-id="906ec-117">Egy ügyfél telefonál, és be szeretne állítani egy szervizszerződést a HIJ légkondícionálóról.</span><span class="sxs-lookup"><span data-stu-id="906ec-117">A customer calls and wants to set up a service agreement for an air conditioning machine, HIJ.</span></span> <span data-ttu-id="906ec-118">Nincs már rekordja ennél a készüléknél.</span><span class="sxs-lookup"><span data-stu-id="906ec-118">You do not already have a record for this machine.</span></span> <span data-ttu-id="906ec-119">Beállított azonban egy Légkondícionálók tárgycsoportot, és hozzárendelte ezt a csoportot az összes légkondícionálóhoz.</span><span class="sxs-lookup"><span data-stu-id="906ec-119">However, you have set up an object group titled Air Conditioners, and you have attached this group to all air conditioning objects.</span></span> <span data-ttu-id="906ec-120">Így gyorsan kikeresheti és azonosíthatja az összes többi légkondícionálót, és ezen tárgyak sablonadataiból szolgáltatásiszerződés-sorokat hozhat létre a HIJ számára.</span><span class="sxs-lookup"><span data-stu-id="906ec-120">Therefore, you can quickly search for and identify all other air conditioning machines and use the template information from these objects to create service agreement lines for HIJ.</span></span> <span data-ttu-id="906ec-121">Ha oly módon használja a tárgycsoportokat, akkor gyorsan beállíthatja az új tárgyakat, illetve meghatározhatja a szervizfeladatokat, amelyeket el kell végezni rajtuk.</span><span class="sxs-lookup"><span data-stu-id="906ec-121">By using object groups in this manner, you can quickly set up new objects and determine the service tasks that must be performed on them.</span></span> 

## <a name="create-service-object-groups"></a><span data-ttu-id="906ec-122">Szolgáltatás tárgyának csoportjai – Létrehozás</span><span class="sxs-lookup"><span data-stu-id="906ec-122">Create service object groups</span></span>

<span data-ttu-id="906ec-123">Hozzon létre csoportokat, amelyekhez szolgáltatási objektumokat rendelhet.</span><span class="sxs-lookup"><span data-stu-id="906ec-123">Create groups that you can assign service objects to.</span></span> <span data-ttu-id="906ec-124">A szolgáltatási objektumok olyan készletcikkek és egyéb termékek, amelyekhez szolgáltatást nyújtanak.</span><span class="sxs-lookup"><span data-stu-id="906ec-124">Service objects are inventory items and other products for which services are performed.</span></span> <span data-ttu-id="906ec-125">A szolgáltatási objektumok csoportosításával létrehozhat jelentéseket a hasonló és a kapcsolódó szolgáltatási objektumokhoz.</span><span class="sxs-lookup"><span data-stu-id="906ec-125">By grouping service objects, you can create reports for similar and related service objects.</span></span> <span data-ttu-id="906ec-126">Például egy szolgáltatási objektumcsoport állhat két szolgáltatásobjektumból: egy szolgáltatási objektum a csomag, a másik pedig a csomag telepítését magába foglaló szolgáltatás.</span><span class="sxs-lookup"><span data-stu-id="906ec-126">For example, a service object group might consist of two service objects: One service object is a kit, and the second service object is the service to install the kit.</span></span>

<span data-ttu-id="906ec-127">Szolgáltatási objektumcsoportok létrehozásához tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="906ec-127">To create service object groups, follow these steps:</span></span>

1. <span data-ttu-id="906ec-128">Kattintson a **Szolgáltatáskezelés > Beállítás > A szolgáltatás tárgyai > A szolgáltatás tárgyai lehetőségre**.</span><span class="sxs-lookup"><span data-stu-id="906ec-128">Click **Service management > Setup > Service objects > Service object groups**.</span></span>

2. <span data-ttu-id="906ec-129">Kattintson az **Új** lehetőségre egy új szolgáltatási objektumcsoport létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="906ec-129">Click **New** to create a new service object group.</span></span>

3. <span data-ttu-id="906ec-130">Írjon be egy egyedi nevet a szolgáltatási objektumcsoport számára, illetve igény szerint adjon meg hozzá leírást.</span><span class="sxs-lookup"><span data-stu-id="906ec-130">Enter a unique name for the service object group and, optionally, a description.</span></span>

<span data-ttu-id="906ec-131">A **Szolgáltatásobjektumok** képernyő használatával rendelhet szolgáltatási objektumokat a csoporthoz.</span><span class="sxs-lookup"><span data-stu-id="906ec-131">You can assign service objects to the group by using the **Service objects** form.</span></span> 

## <a name="see-also"></a><span data-ttu-id="906ec-132">Lásd még</span><span class="sxs-lookup"><span data-stu-id="906ec-132">See also</span></span>

[<span data-ttu-id="906ec-133">Szolgáltatási objektumok létrehozása</span><span class="sxs-lookup"><span data-stu-id="906ec-133">Create service objects</span></span>](create-service-objects.md)


