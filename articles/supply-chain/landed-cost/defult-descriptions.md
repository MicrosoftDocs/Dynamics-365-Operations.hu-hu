---
title: A főkönyv alapértelmezett leírásai
description: Az alapértelmezett leírásokkal lehet frissíteni a főkönyvbe való bizonylatfeladások Leírás mezőjét.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 25dd72c86b22b50eccef22a5d2cbcfcf04280684
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021612"
---
# <a name="default-descriptions-for-the-general-ledger"></a><span data-ttu-id="1971d-103">A főkönyv alapértelmezett leírásai</span><span class="sxs-lookup"><span data-stu-id="1971d-103">Default descriptions for the general ledger</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1971d-104">Az alapértelmezett leírásokkal lehet frissíteni a főkönyvbe való bizonylatfeladások **Leírás** mezőjét.</span><span class="sxs-lookup"><span data-stu-id="1971d-104">Default descriptions can be used to update the **Description** field in voucher postings to the general ledger.</span></span> <span data-ttu-id="1971d-105">Ez a funkció továbbfejlesztésre került, hogy működjön a Partraszállítási költséggel.</span><span class="sxs-lookup"><span data-stu-id="1971d-105">This functionality has been enhanced to work with Landed cost.</span></span>

<span data-ttu-id="1971d-106">A főkönyvi feladások alapértelmezett leírásainak beállításához használja a **Szervezeti adminisztráció \> Beállítás \> Alapértelmezett leírások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="1971d-106">To set up default descriptions for ledger postings, go to **Organizational administration \> Setup \> Default descriptions**.</span></span>

<span data-ttu-id="1971d-107">A következő táblázat felsorolja azokat az új értékeket, amelyek az **Alapértelmezett leírás** oldal **Leírás** mezőjéhez hozzáadva a Partraszállítási költséget támogatják.</span><span class="sxs-lookup"><span data-stu-id="1971d-107">The following table lists the new values that have been added for the **Description** field on the **Default descriptions** page to support Landed cost.</span></span>

| <span data-ttu-id="1971d-108">Leírás típusa</span><span class="sxs-lookup"><span data-stu-id="1971d-108">Description type</span></span> | <span data-ttu-id="1971d-109">Jegyzetek</span><span class="sxs-lookup"><span data-stu-id="1971d-109">Notes</span></span> |
|---|---|
| <span data-ttu-id="1971d-110">Importálás költségszámítása – Költség elhatárolása</span><span class="sxs-lookup"><span data-stu-id="1971d-110">Import costing – Cost accrual</span></span> | <span data-ttu-id="1971d-111">Beszerzési rendelés számlájának feladásakor egy költségelhatárolás kerül feldolgozásra a hajóút becsült költségeihez.</span><span class="sxs-lookup"><span data-stu-id="1971d-111">When a purchase order invoice is posted, a cost accrual is processed for estimate voyage costs.</span></span> <span data-ttu-id="1971d-112">Az hajóút számának a leíráshoz való hozzáadásához megadhatók alapértelmezett leírások.</span><span class="sxs-lookup"><span data-stu-id="1971d-112">Default descriptions can be specified to add the voyage number to the description.</span></span> <span data-ttu-id="1971d-113">*%4* használata a szállítmányszámhoz.</span><span class="sxs-lookup"><span data-stu-id="1971d-113">Use *%4* for the shipment number.</span></span> |
| <span data-ttu-id="1971d-114">Importálással kapcsolatos költségszámítás – Úton lévő árukkal kapcsolatos rendelés</span><span class="sxs-lookup"><span data-stu-id="1971d-114">Import costing – Goods in transit order</span></span> | <span data-ttu-id="1971d-115">Ha szállítás közbeni feldolgozást használ, feladásra kerül a beszerzési rendelés számlája, és az áruk feladása egy úton lévő áruk számlára lesznek feladva.</span><span class="sxs-lookup"><span data-stu-id="1971d-115">If you're using in-transit processing, the purchase order invoice is posted, and the goods are posted to a goods in transit account.</span></span> <span data-ttu-id="1971d-116">A szállítás alatt lévő rendelés számának a leíráshoz való hozzáadásához megadhatók alapértelmezett leírások.</span><span class="sxs-lookup"><span data-stu-id="1971d-116">Default descriptions can be specified to add the in-transit order number to the description.</span></span> <span data-ttu-id="1971d-117">*%4* használata a szállítás alatt lévő rendelés számához.</span><span class="sxs-lookup"><span data-stu-id="1971d-117">Use *%4* for the in-transit order number.</span></span> |
| <span data-ttu-id="1971d-118">Készlet – zárás – helyesbítés</span><span class="sxs-lookup"><span data-stu-id="1971d-118">Inventory – close – adjustment</span></span> | <span data-ttu-id="1971d-119">Ha a kötelezettségek (AP) számlája feldolgozásra kerül egy hajóútköltséghez, akkor a program készlethelyesbítést dolgoz fel a hajóút költségeinek becslésére.</span><span class="sxs-lookup"><span data-stu-id="1971d-119">When the accounts payable (AP) invoice is processed for a voyage cost, an inventory adjustment is processed to estimate voyage costs.</span></span> <span data-ttu-id="1971d-120">Az hajóút számának a leíráshoz való hozzáadásához megadhatók alapértelmezett leírások.</span><span class="sxs-lookup"><span data-stu-id="1971d-120">Default descriptions can be specified to add the voyage number to the description.</span></span> <span data-ttu-id="1971d-121">*%4* használata a szállítmányszámhoz.</span><span class="sxs-lookup"><span data-stu-id="1971d-121">Use *%4* for the shipment number.</span></span> |

<span data-ttu-id="1971d-122">Az **Alapértelmezett leírások** oldal beállításával kapcsolatos további tudnivalók: [Alapértelmezett leírások beállítása automatikus feladáshoz](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).</span><span class="sxs-lookup"><span data-stu-id="1971d-122">For more information about how to work with the **Default descriptions** page, see [Set up default descriptions for automatic posting](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).</span></span>
