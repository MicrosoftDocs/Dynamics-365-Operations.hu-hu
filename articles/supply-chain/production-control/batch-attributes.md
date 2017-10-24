---
title: "Kötegattribútumok"
description: "Ez a cikk a kötegattribútumokkal kapcsolatban tartalmaz információkat. A kötegattribútumok a nyersanyagok és a késztermékek jellemzői, amelyek készletkötegeket alkotnak. A cikk bemutatja továbbá a kötegattribútumok társítását, és hogy a kötegek lefoglalásánál hogyan kereshet rájuk."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PdsBatchAttrib, PdsBatchAttribAssociate, PdsBatchAttribByAttribGroup, PdsBatchAttribByItem, PdsBatchAttribByitemCustomer, PdsBatchAttribGroup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19271
ms.assetid: 41de0250-4a96-412e-a412-aa06615b6b1d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0c3f5115377178941984e53749c18cc1c9179812
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="batch-attributes"></a><span data-ttu-id="bb22a-105">Kötegattribútumok</span><span class="sxs-lookup"><span data-stu-id="bb22a-105">Batch attributes</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="bb22a-106">Ez a cikk a kötegattribútumokkal kapcsolatban tartalmaz információkat.</span><span class="sxs-lookup"><span data-stu-id="bb22a-106">This article provides information about batch attributes.</span></span> <span data-ttu-id="bb22a-107">A kötegattribútumok a nyersanyagok és a késztermékek jellemzői, amelyek készletkötegeket alkotnak.</span><span class="sxs-lookup"><span data-stu-id="bb22a-107">Batch attributes are characteristics of raw materials and finished products that make up inventory batches.</span></span> <span data-ttu-id="bb22a-108">A cikk bemutatja továbbá a kötegattribútumok társítását, és hogy a kötegek lefoglalásánál hogyan kereshet rájuk.</span><span class="sxs-lookup"><span data-stu-id="bb22a-108">The article also explains how to assign batch attributes, and how you can search on them when you reserve batches.</span></span>

<span data-ttu-id="bb22a-109">A kötegattribútumok a nyersanyagok és a késztermékek jellemzői, amelyek készletkötegeket alkotnak.</span><span class="sxs-lookup"><span data-stu-id="bb22a-109">Batch attributes are characteristics of raw materials and finished products that make up inventory batches.</span></span> <span data-ttu-id="bb22a-110">A kötegattribútumok különbözhetnek olyan tényezők tekintetében, mint a környezeti tényezők, a köteg előállításához használt nyersanyagok minősége, vagy a késztermék eredménye.</span><span class="sxs-lookup"><span data-stu-id="bb22a-110">Batch attributes can vary, depending on factors such as environmental conditions, the quality of the raw materials that are used to produce the batch, or the outcome of the finished product.</span></span> <span data-ttu-id="bb22a-111">A használt szám és kötegattribútumok-típusok is jelentősen eltérhetnek iparáganként.</span><span class="sxs-lookup"><span data-stu-id="bb22a-111">The number and types of batch attributes that are used can vary widely from one industry to another.</span></span> <span data-ttu-id="bb22a-112">Az alábbiakban két példák, illusztrálja, hogy hogyan kell használni a kötegattribútumokat:</span><span class="sxs-lookup"><span data-stu-id="bb22a-112">Here are two examples that show how to use batch attributes:</span></span>

-   <span data-ttu-id="bb22a-113">A sajt iparágban a tej, amely a sajt előállításához használt nyersanyagok közé tartozik, különböző jellemzőkkel bír, mint pl. zsírtartalom és százalékos súly.</span><span class="sxs-lookup"><span data-stu-id="bb22a-113">In the cheese industry, milk, which is one of the raw materials that are used to produce the cheese, can have attributes such as fat content and percentage weight.</span></span> <span data-ttu-id="bb22a-114">A tejből előállított sajt más attribútumokkal rendelkezhet, például a nedvesség és a kor.</span><span class="sxs-lookup"><span data-stu-id="bb22a-114">The cheese that is produced from the milk can have other attributes, such as moisture and age.</span></span>
-   <span data-ttu-id="bb22a-115">Az acéliparban a létrehozott vas olyan attribútumokkal rendelkezhet, mint a magnéziumtartalom, ezüsttartalom, és cinktartalom százalékos aránya.</span><span class="sxs-lookup"><span data-stu-id="bb22a-115">In the steel industry, the iron that is produced might have attributes such as the percentages of magnesium content, silver content, and zinc content.</span></span>

<span data-ttu-id="bb22a-116">Az attribútumok számának és típusainak jobb kezelése érdekében használhatja a kötegattribútum-csoportokat.</span><span class="sxs-lookup"><span data-stu-id="bb22a-116">To better manage the number and types of attributes, you can use batch attribute groups.</span></span> <span data-ttu-id="bb22a-117">Ezzel a módszerrel nem kell külön-külön hozzáadnia az egyes attribútumokat.</span><span class="sxs-lookup"><span data-stu-id="bb22a-117">In this way, you don't have to add each attribute individually.</span></span>

## <a name="assign-batch-attributes"></a><span data-ttu-id="bb22a-118">Kötegattribútumok hozzárendelése</span><span class="sxs-lookup"><span data-stu-id="bb22a-118">Assign batch attributes</span></span>
<span data-ttu-id="bb22a-119">Kötegattribútumokat hozzárendelhet az egyes termékekhez, amelyeket készletkötegekben tartanak, vagy hozzárendelheti őket meghatározott vevőkhöz kapcsolódó termékekhez.</span><span class="sxs-lookup"><span data-stu-id="bb22a-119">You can assign batch attributes to individual products that are held in inventory batches, or you can assign them to products that are associated with specific customers.</span></span> <span data-ttu-id="bb22a-120">Mielőtt hozzárendel egy kötegattribútumot a vevő szintjén, a termék szintjén kell hozzárendelnie.</span><span class="sxs-lookup"><span data-stu-id="bb22a-120">Before you can assign a batch attribute at the customer level, you must assign it at the product level.</span></span> <span data-ttu-id="bb22a-121">A terméknek kell rendelkeznie egy kötegdimenzió-készlettel, amely az **Aktív** lehetőségre van állítva a nyomonkövetési dimenziócsoportban.</span><span class="sxs-lookup"><span data-stu-id="bb22a-121">The product must have the batch dimension set to **Active** in the tracking dimension group.</span></span> <span data-ttu-id="bb22a-122">Használja a termékspecifikus lapot, ha kötegattribútum-csoportot akar hozzárendelni az egyes termékekhez.</span><span class="sxs-lookup"><span data-stu-id="bb22a-122">To assign a batch attribute to an individual product, use the product-specific page.</span></span> <span data-ttu-id="bb22a-123">Ha az attribútum meghatározott vevőhöz tartozó termékre jellemző, akkor a vevőre jellemző lapot kell használni.</span><span class="sxs-lookup"><span data-stu-id="bb22a-123">If the attribute is specific to a product for a customer, use the customer-specific page.</span></span> <span data-ttu-id="bb22a-124">Attribútum hozzáadásakor egy termékhez megadhat egyéb paramétereket is.</span><span class="sxs-lookup"><span data-stu-id="bb22a-124">When you add an attribute to a product, you also define other parameters.</span></span> <span data-ttu-id="bb22a-125">Íme néhány példa:</span><span class="sxs-lookup"><span data-stu-id="bb22a-125">Here are some examples:</span></span>

-   <span data-ttu-id="bb22a-126">Egy attribútum maximális és minimális értékei az **Egész** vagy **Rész** típusban.</span><span class="sxs-lookup"><span data-stu-id="bb22a-126">The minimum and maximum ranges for an attribute of the **Integer** or **Fraction** type.</span></span>
-   <span data-ttu-id="bb22a-127">Az attribútum tűréshatárának műveletei az **Egész** vagy **Tört** típusban.</span><span class="sxs-lookup"><span data-stu-id="bb22a-127">The tolerance actions for an attribute of the **Integer** or **Fraction** type.</span></span> <span data-ttu-id="bb22a-128">Ha az attribútum értéke a minimális és maximális tartományon kívül esik, a művelet lehet figyelmeztetés vagy hibaüzenet.</span><span class="sxs-lookup"><span data-stu-id="bb22a-128">If the value of the attribute falls outside the minimum and maximum range, the action can be either a warning message or an error message.</span></span>
-   <span data-ttu-id="bb22a-129">Az attribútum célértéke.</span><span class="sxs-lookup"><span data-stu-id="bb22a-129">The target value for the attribute.</span></span> <span data-ttu-id="bb22a-130">Ez az érték az attribútum optimális értéke, és minden attribútumtípusra vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="bb22a-130">This value is the optimal value of the attribute, and it applies to all attribute types.</span></span>

<span data-ttu-id="bb22a-131">Hozzáférhet a kiválasztott termékek lapjaihoz, ha a **Felszabadított termékek** oldalon kiválasztja a Termékinformációk kezelése lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bb22a-131">You can access the pages for products that you select on the **Released products** page in Product information management.</span></span> <span data-ttu-id="bb22a-132">Miután hozzárendelte kötegattribútumokat egy termékhez, akkor hozzáadhat adott értékeket az attribútumokhoz a **Készletköteg-attribútumok** oldalon.</span><span class="sxs-lookup"><span data-stu-id="bb22a-132">After you assign batch attributes to a product, you can add specific values to the attributes on the **Inventory batch attributes** page.</span></span>

## <a name="reserve-batches"></a><span data-ttu-id="bb22a-133">Kötegek foglalása</span><span class="sxs-lookup"><span data-stu-id="bb22a-133">Reserve batches</span></span>
<span data-ttu-id="bb22a-134">Rákereshet kötegattribútumokra amikor egy vásárlói rendelés kielégítéséhez kötegfoglalásokat végez egy értékesítési rendeléshez, de egy termelési rendeléshez való kötegkitárolás és -foglalás esetén is megteheti ezt.</span><span class="sxs-lookup"><span data-stu-id="bb22a-134">You can search on batch attributes when you do batch reservations for a sales order to fullfill a customer's order, or when you pick and reserve batches for a production order.</span></span> <span data-ttu-id="bb22a-135">A keresés segítségével keresse meg a készletköteget, amely tartalmazza a terméket, amely rendelkezik a kívánt kötegattribútummal.</span><span class="sxs-lookup"><span data-stu-id="bb22a-135">The search helps locate an inventory batch that contains the product that has the batch attribute that you want.</span></span> <span data-ttu-id="bb22a-136">A köteg- vagy kötegek megtalálása után lefoglalhatja a terméket a származó készlet-tranzakciósorba.</span><span class="sxs-lookup"><span data-stu-id="bb22a-136">After you locate the batch or batches, you can reserve the product to the originating inventory transaction line.</span></span>




