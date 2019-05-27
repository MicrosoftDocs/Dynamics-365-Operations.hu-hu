---
title: Rendelések szállítása egy másik üzletből költségküldési szolgáltatással
description: Ez a témakör leírja a költségküldési funkciót.
author: ashishmsft
manager: AnnBe
ms.date: 10/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-10-10
ms.dyn365.ops.version: Retail July 2017 update
ms.openlocfilehash: e5351086c56d13ef98937aec066be00cdf88fd37
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553635"
---
# <a name="ship-orders-from-another-store-by-using-the-charge-send-feature"></a><span data-ttu-id="c2bed-103">Rendelések szállítása egy másik üzletből költségküldési szolgáltatással</span><span class="sxs-lookup"><span data-stu-id="c2bed-103">Ship orders from another store by using the Charge send feature</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c2bed-104">A Dynamics 365 for Retail költségküldési funkciójával a vevői rendelések feladhatók egy üzletben, és kiszállíthatók egy másik üzletből.</span><span class="sxs-lookup"><span data-stu-id="c2bed-104">With the Charge send feature in Dynamics 365 for Retail, customer orders can be placed in one store and shipped from another store.</span></span>

<span data-ttu-id="c2bed-105">A pénztári (POS) ügyfélen feladott vevői rendelések több teljesítési lehetőséget támogatnak.</span><span class="sxs-lookup"><span data-stu-id="c2bed-105">Customer orders in the point of sale (POS) client support multiple fulfillment options.</span></span> <span data-ttu-id="c2bed-106">Néhány példa a teljesítési lehetőségekre:</span><span class="sxs-lookup"><span data-stu-id="c2bed-106">Some examples of fulfillment options include:</span></span>

- <span data-ttu-id="c2bed-107">Felvétel ugyanabban az üzletben egy másik napon.</span><span class="sxs-lookup"><span data-stu-id="c2bed-107">Pick up from the same store on a different date.</span></span>
- <span data-ttu-id="c2bed-108">Felvétel egy másik az üzletben ugyanazon a napon vagy egy másik napon.</span><span class="sxs-lookup"><span data-stu-id="c2bed-108">Pick up from a different store on the same date or a different date.</span></span>
- <span data-ttu-id="c2bed-109">Szállítás az üzlethez társított, alapértelmezett szállítási raktárból, és szállítás egy adott dátumon.</span><span class="sxs-lookup"><span data-stu-id="c2bed-109">Ship from the default shipping warehouse that is assigned to the store, and deliver on a specific date.</span></span>

<span data-ttu-id="c2bed-110">A költségküldési szolgáltatás a következő POS-műveleteket használj: az összes termék szállítás és a kijelölt termékek szállítása.</span><span class="sxs-lookup"><span data-stu-id="c2bed-110">The Charge send feature uses the following POS operations: Ship all products and Ship selected products.</span></span> <span data-ttu-id="c2bed-111">Ez lehetővé teszi a tárolóadminisztrátor számára a „szállítás kiindulási helye” kiválasztását, ahonnan a rendelés vagy a rendeléssor teljesíthető.</span><span class="sxs-lookup"><span data-stu-id="c2bed-111">This allows the store clerk to select the "ship from" location that the order or order line can be fulfilled from.</span></span> <span data-ttu-id="c2bed-112">Alapértelmezés szerint a „szállítás kiindulási helye” az üzlethez társított a szállítási raktár.</span><span class="sxs-lookup"><span data-stu-id="c2bed-112">By default, the "ship from" location is the shipping warehouse that is associated with the store.</span></span> <span data-ttu-id="c2bed-113">Az üzlet eladója azonban módosíthatja ezt a helyet, és minden üzletet kiválaszthat, amely az üzlethez társított lokátorcsoportban meg van adva.</span><span class="sxs-lookup"><span data-stu-id="c2bed-113">However, the store clerk can change this location and select any store that is defined in the store locator group that is assigned to the store.</span></span>

<span data-ttu-id="c2bed-114">A „szállítás célhelye” kiválasztásának képessége változatlan marad.</span><span class="sxs-lookup"><span data-stu-id="c2bed-114">The ability to select "ship to" addresses remains unchanged.</span></span>

<span data-ttu-id="c2bed-115">A rendelési sor teljesítéséhez használható szállítási módok a termékek és a címek érvényes szállítási módjainak konfigurációján alapulnak.</span><span class="sxs-lookup"><span data-stu-id="c2bed-115">The shipping methods that can be used to fulfill the order line are based on the configuration of valid modes of delivery for products and addresses.</span></span> <span data-ttu-id="c2bed-116">Mivel az érvényes szállítási módok szabályainak karbantartása csak a Kiskereskedelmi központban (HQ) történik, a POS-ügyfél a valós idejű hívással olvassa be a szállítási sor érvényes szállítási módjait.</span><span class="sxs-lookup"><span data-stu-id="c2bed-116">Because the rules about valid of modes of delivery are maintained only in the Retail headquarters (HQ), the POS client makes a real-time call to fetch the valid modes of delivery for a ship line.</span></span>
