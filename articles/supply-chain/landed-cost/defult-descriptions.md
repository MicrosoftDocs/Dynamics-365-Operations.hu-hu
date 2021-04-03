---
title: A főkönyv alapértelmezett leírásai
description: Az alapértelmezett leírásokkal lehet frissíteni a főkönyvbe való bizonylatfeladások Leírás mezőjét.
author: sherry-zheng
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 47c5c9e71dba7a0cb7c798c167208faebeb5af6c
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500380"
---
# <a name="default-descriptions-for-the-general-ledger"></a><span data-ttu-id="bf122-103">A főkönyv alapértelmezett leírásai</span><span class="sxs-lookup"><span data-stu-id="bf122-103">Default descriptions for the general ledger</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="bf122-104">Az alapértelmezett leírásokkal lehet frissíteni a főkönyvbe való bizonylatfeladások **Leírás** mezőjét.</span><span class="sxs-lookup"><span data-stu-id="bf122-104">Default descriptions can be used to update the **Description** field in voucher postings to the general ledger.</span></span> <span data-ttu-id="bf122-105">Ez a funkció továbbfejlesztésre került, hogy működjön a Partraszállítási költséggel.</span><span class="sxs-lookup"><span data-stu-id="bf122-105">This functionality has been enhanced to work with Landed cost.</span></span>

<span data-ttu-id="bf122-106">A főkönyvi feladások alapértelmezett leírásainak beállításához használja a **Szervezeti adminisztráció \> Beállítás \> Alapértelmezett leírások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="bf122-106">To set up default descriptions for ledger postings, go to **Organizational administration \> Setup \> Default descriptions**.</span></span>

<span data-ttu-id="bf122-107">A következő táblázat felsorolja azokat az új értékeket, amelyek az **Alapértelmezett leírás** oldal **Leírás** mezőjéhez hozzáadva a Partraszállítási költséget támogatják.</span><span class="sxs-lookup"><span data-stu-id="bf122-107">The following table lists the new values that have been added for the **Description** field on the **Default descriptions** page to support Landed cost.</span></span>

| <span data-ttu-id="bf122-108">Leírás típusa</span><span class="sxs-lookup"><span data-stu-id="bf122-108">Description type</span></span> | <span data-ttu-id="bf122-109">Jegyzetek</span><span class="sxs-lookup"><span data-stu-id="bf122-109">Notes</span></span> |
|---|---|
| <span data-ttu-id="bf122-110">Importálás költségszámítása – Költség elhatárolása</span><span class="sxs-lookup"><span data-stu-id="bf122-110">Import costing – Cost accrual</span></span> | <span data-ttu-id="bf122-111">Beszerzési rendelés számlájának feladásakor egy költségelhatárolás kerül feldolgozásra a hajóút becsült költségeihez.</span><span class="sxs-lookup"><span data-stu-id="bf122-111">When a purchase order invoice is posted, a cost accrual is processed for estimate voyage costs.</span></span> <span data-ttu-id="bf122-112">Az hajóút számának a leíráshoz való hozzáadásához megadhatók alapértelmezett leírások.</span><span class="sxs-lookup"><span data-stu-id="bf122-112">Default descriptions can be specified to add the voyage number to the description.</span></span> <span data-ttu-id="bf122-113">*%4* használata a szállítmányszámhoz.</span><span class="sxs-lookup"><span data-stu-id="bf122-113">Use *%4* for the shipment number.</span></span> |
| <span data-ttu-id="bf122-114">Importálással kapcsolatos költségszámítás – Úton lévő árukkal kapcsolatos rendelés</span><span class="sxs-lookup"><span data-stu-id="bf122-114">Import costing – Goods in transit order</span></span> | <span data-ttu-id="bf122-115">Ha szállítás közbeni feldolgozást használ, feladásra kerül a beszerzési rendelés számlája, és az áruk feladása egy úton lévő áruk számlára lesznek feladva.</span><span class="sxs-lookup"><span data-stu-id="bf122-115">If you're using in-transit processing, the purchase order invoice is posted, and the goods are posted to a goods in transit account.</span></span> <span data-ttu-id="bf122-116">A szállítás alatt lévő rendelés számának a leíráshoz való hozzáadásához megadhatók alapértelmezett leírások.</span><span class="sxs-lookup"><span data-stu-id="bf122-116">Default descriptions can be specified to add the in-transit order number to the description.</span></span> <span data-ttu-id="bf122-117">*%4* használata a szállítás alatt lévő rendelés számához.</span><span class="sxs-lookup"><span data-stu-id="bf122-117">Use *%4* for the in-transit order number.</span></span> |
| <span data-ttu-id="bf122-118">Készlet – zárás – helyesbítés</span><span class="sxs-lookup"><span data-stu-id="bf122-118">Inventory – close – adjustment</span></span> | <span data-ttu-id="bf122-119">Ha a kötelezettségek (AP) számlája feldolgozásra kerül egy hajóútköltséghez, akkor a program készlethelyesbítést dolgoz fel a hajóút költségeinek becslésére.</span><span class="sxs-lookup"><span data-stu-id="bf122-119">When the accounts payable (AP) invoice is processed for a voyage cost, an inventory adjustment is processed to estimate voyage costs.</span></span> <span data-ttu-id="bf122-120">Az hajóút számának a leíráshoz való hozzáadásához megadhatók alapértelmezett leírások.</span><span class="sxs-lookup"><span data-stu-id="bf122-120">Default descriptions can be specified to add the voyage number to the description.</span></span> <span data-ttu-id="bf122-121">*%4* használata a szállítmányszámhoz.</span><span class="sxs-lookup"><span data-stu-id="bf122-121">Use *%4* for the shipment number.</span></span> |

<span data-ttu-id="bf122-122">Az **Alapértelmezett leírások** oldal beállításával kapcsolatos további tudnivalók: [Alapértelmezett leírások beállítása automatikus feladáshoz](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).</span><span class="sxs-lookup"><span data-stu-id="bf122-122">For more information about how to work with the **Default descriptions** page, see [Set up default descriptions for automatic posting](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).</span></span>
