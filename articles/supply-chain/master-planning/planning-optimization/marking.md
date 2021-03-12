---
title: Készletjelölés tervezési optimalizálással
description: Ez a témakör a megerősített rendelések készletének megjelölésére használható beállításokról nyújt tájékoztatást a tervezésoptimalizálás során.
author: ChristianRytt
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 236e1955dd80564e748aab1c595b017cb78e9418
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983491"
---
# <a name="inventory-marking-with-planning-optimization"></a><span data-ttu-id="5b481-103">Készletjelölés tervezési optimalizálással</span><span class="sxs-lookup"><span data-stu-id="5b481-103">Inventory marking with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5b481-104">Ez a témakör a megerősített rendelések készletének megjelölésére használható beállításokról nyújt tájékoztatást a tervezésoptimalizálás során.</span><span class="sxs-lookup"><span data-stu-id="5b481-104">This topic provides information about the options that are available for marking inventory in firmed orders when you use Planning Optimization.</span></span>

<span data-ttu-id="5b481-105">A *Jelölés* a kínálat és kereslet összekapcsolására szolgál.</span><span class="sxs-lookup"><span data-stu-id="5b481-105">*Marking* is used to link supply and demand.</span></span> <span data-ttu-id="5b481-106">Ez hasonlít az *igénykövetés* műveletre, amely azt jelzi, hogy az alaptervezés hogyan tervezi a szükségletek lefedését.</span><span class="sxs-lookup"><span data-stu-id="5b481-106">It resembles *pegging*, which indicates how master planning expects to cover demand.</span></span> <span data-ttu-id="5b481-107">Tervezési szempontból a fő különbség az, hogy a jelölés állandóbb, mint az igénykövetés.</span><span class="sxs-lookup"><span data-stu-id="5b481-107">From a planning point of view, the main difference is that marking is more permanent than pegging.</span></span>

<span data-ttu-id="5b481-108">A jelölést a speciális költségszámítási esetek támogatására vezették be a elsőként be, elsőként ki (FIFO) és utolsóként be, elsőként ki (LIFO) esetekhez.</span><span class="sxs-lookup"><span data-stu-id="5b481-108">Marking was introduced to support special costing scenarios for first in, first out (FIFO) and last in, first out (LIFO).</span></span> <span data-ttu-id="5b481-109">Azonban most már néhány nem költségszámítási esethez is használatos.</span><span class="sxs-lookup"><span data-stu-id="5b481-109">However, it's now also used for some non-costing scenarios.</span></span> <span data-ttu-id="5b481-110">A kínálat és a szükséglet közötti jelölés nem kötelező, és csaknem állandó.</span><span class="sxs-lookup"><span data-stu-id="5b481-110">Marking between supply and demand is optional and almost permanent.</span></span> <span data-ttu-id="5b481-111">A jelölést a felhasználó manuálisan is eltávolíthatja, vagy az értékesítésirendelés-sor alábontásával eltávolíthatja, ha be van jelölve a **Jelölés törlése** beállítás.</span><span class="sxs-lookup"><span data-stu-id="5b481-111">Marking can be removed manually by a user, or it can be removed by running a sales order line explosion where the **Remove marking** option is selected.</span></span>

<span data-ttu-id="5b481-112">Az igénykövetést az Alaptervezés vezérli, hogy a szükségletet a szükséges kínálattal kapcsolja.</span><span class="sxs-lookup"><span data-stu-id="5b481-112">Pegging is controlled by master planning during coverage to link demand with the required supply.</span></span> <span data-ttu-id="5b481-113">Az igénykövetés a szükségletek fedezéséhez szükséges kínálat optimalizálása céljából minden tervezési futtatásnál módosítható.</span><span class="sxs-lookup"><span data-stu-id="5b481-113">Pegging can be updated for each planning run to optimize the supply that is required to cover demand.</span></span> <span data-ttu-id="5b481-114">Amikor az alaptervezési frissíti az igénykövetési információkat, minden meglévő jelölést figyelembe vesz.</span><span class="sxs-lookup"><span data-stu-id="5b481-114">When master planning updates pegging information, it respects any existing marking.</span></span>

<span data-ttu-id="5b481-115">Az igénykövetés a megfelelő jelöléssel, az aktuális készletfoglalásokkal és a rendelésen szereplő foglalásokkal együtt kezdődik, a következő sorrendben:</span><span class="sxs-lookup"><span data-stu-id="5b481-115">Pegging starts by including relevant marking, on-hand reservations, and on-order reservations, in the following sequence:</span></span>

1. <span data-ttu-id="5b481-116">Szükséglet és kínálat közötti jelölés</span><span class="sxs-lookup"><span data-stu-id="5b481-116">Marking between demand and supply</span></span>
1. <span data-ttu-id="5b481-117">Aktuális készletfoglalások</span><span class="sxs-lookup"><span data-stu-id="5b481-117">On-hand reservations</span></span>
1. <span data-ttu-id="5b481-118">Rendelésen szereplő foglalások</span><span class="sxs-lookup"><span data-stu-id="5b481-118">On-order reservations</span></span>

<span data-ttu-id="5b481-119">Ha egy tervezett rendelést erősít meg, akkor a **Megerősítés** párbeszédpanelen szerepel egy **Jelölés frissítése** mező, amellyel beállíthatók a megerősítés során létrehozott rendelésekre vonatkozó jelölési beállítások.</span><span class="sxs-lookup"><span data-stu-id="5b481-119">When you firm a planned order, the **Firming** dialog box provides an **Update marking** field that you use to set marking options for the orders that are created during firming.</span></span> <span data-ttu-id="5b481-120">Válasszon a következő értékek közül:</span><span class="sxs-lookup"><span data-stu-id="5b481-120">Select one of the following values:</span></span>

- <span data-ttu-id="5b481-121">**Nem** – Nem alkalmaztak készletjelölést.</span><span class="sxs-lookup"><span data-stu-id="5b481-121">**No** – No inventory marking is applied.</span></span>
- <span data-ttu-id="5b481-122">**Standard** – a készletjelölés frissítése az igénykövetés alapján történik.</span><span class="sxs-lookup"><span data-stu-id="5b481-122">**Standard** – Inventory marking is updated according to the pegging.</span></span> <span data-ttu-id="5b481-123">Egy szükségleti rendelést (igény) és egy teljesítési rendelést (kínálat) állít jelöléssel párba a program.</span><span class="sxs-lookup"><span data-stu-id="5b481-123">A requirement order (demand) is marked against a fulfillment order (supply).</span></span> <span data-ttu-id="5b481-124">Ha a teljesítési rendelésen bizonyos mennyiség megmarad, a rendszer nem jelöli meg, és a hivatkozási adatok üresen maradnak.</span><span class="sxs-lookup"><span data-stu-id="5b481-124">If some quantity remains on the fulfillment order, it isn't marked, and the reference information is left blank.</span></span> <span data-ttu-id="5b481-125">Ha például egy 100 ea-ra vonatkozó értékesítési rendelést igénykövetéssel egy 150 ea-s beszerzési rendeléssel állítják szembe, akkor a hivatkozási adatokat a rendszer csak az értékesítési rendeléshez rendeli hozzá.</span><span class="sxs-lookup"><span data-stu-id="5b481-125">For example, if a sales order for 100 ea is pegged against a purchase order for 150 ea, reference information will be assigned only to the sales order.</span></span>
- <span data-ttu-id="5b481-126">**Bővített** – mind a szükségleti rendelést (szükséglet), mind a teljesítési rendelést (ellátás) megjelöli a program, függetlenül attól, hogy marad-e mennyiség a teljesítési rendelésen.</span><span class="sxs-lookup"><span data-stu-id="5b481-126">**Extended** – Both the requirement order (demand) and the fulfillment order (supply) are marked, regardless of any quantity that remains on the fulfillment order.</span></span> <span data-ttu-id="5b481-127">Ha például egy 100 ea-ra vonatkozó értékesítési rendelést igénykövetéssel egy 150 ea-s beszerzési rendeléssel állítják szembe, akkor a hivatkozási adatokat a rendszer mint az értékesítési rendeléshez, mind a beszerzési rendeléshez hozzárendeli.</span><span class="sxs-lookup"><span data-stu-id="5b481-127">For example, if a sales order for 100 ea is pegged against a purchase order for 150 ea, reference information will be assigned to both the sales order and the purchase order.</span></span>
