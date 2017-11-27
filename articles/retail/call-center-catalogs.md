---
title: "Hívásközponti katalógusok"
description: "A cikk a Microsoft Dynamics 365 for Retail-katalógusok hívásközpont-specifikus funkcióit ismerteti."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: e5a97ab749259fcc97b269b0134792820ebf13af
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="call-center-catalogs"></a><span data-ttu-id="31b25-103">Hívásközpont-katalógusok</span><span class="sxs-lookup"><span data-stu-id="31b25-103">Call center catalogs</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="31b25-104">A cikk a Microsoft Dynamics 365 for Retail-katalógusok hívásközpont-specifikus funkcióit ismerteti.</span><span class="sxs-lookup"><span data-stu-id="31b25-104">This article describes the call center–specific functionality for catalogs in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="31b25-105">Az ügyfélszolgálaton használhatja a termékkatalógusokat a termékek azonosításához, amelyet a vevőknek szeretne árusítani.</span><span class="sxs-lookup"><span data-stu-id="31b25-105">In a call center, you can use product catalogs to identify the products that you want to offer to customers.</span></span> <span data-ttu-id="31b25-106">Az ügyfélszolgálatok általában nyomtatott katalógusokat használnak.</span><span class="sxs-lookup"><span data-stu-id="31b25-106">Call centers typically use printed catalogs.</span></span> <span data-ttu-id="31b25-107">A nyomtatott katalógusok tervezése és gyártása a Dynamics 365 for Retail rendszeren kívül történik.</span><span class="sxs-lookup"><span data-stu-id="31b25-107">The design and production of a printed catalog is handled outside Dynamics 365 for Retail.</span></span> <span data-ttu-id="31b25-108">Azonban a katalógus digitális formáját létrehozhatja és tárolhatja ugyanazon oldalakkal, amelyeket az online kiskereskedelmi katalógusok beállítására használ.</span><span class="sxs-lookup"><span data-stu-id="31b25-108">However, you can create and store a digital form of a catalog by using the same pages that you use to set up online retail catalogs.</span></span> <span data-ttu-id="31b25-109">Katalógus létrehozása előtt állítsa be a termék szortimenteket a rendszerben, és a szortimenteket rendelje hozzá egy ügyfélszolgálathoz.</span><span class="sxs-lookup"><span data-stu-id="31b25-109">Before you can create a catalog, you must set up product assortments and assign the assortments to a call center.</span></span> <span data-ttu-id="31b25-110">Majd adja hozzá a termékeket a katalógushoz a termékek kijelölésével a szortimentekből.</span><span class="sxs-lookup"><span data-stu-id="31b25-110">You then add products to the catalog by selecting products from these assortments.</span></span> <span data-ttu-id="31b25-111">Miután a termékeket hozzáadta a katalógushoz, és a katalógus befejeződött, ellenőriznie kell a katalógust, az adatok igazolásához.</span><span class="sxs-lookup"><span data-stu-id="31b25-111">After products have been added to the catalog, and the catalog is complete, you must validate the catalog to verify the data.</span></span> <span data-ttu-id="31b25-112">Ezután küldje el a katalógust ellenőrzésre és jóváhagyásra.</span><span class="sxs-lookup"><span data-stu-id="31b25-112">You must then submit the catalog for review and approval.</span></span> <span data-ttu-id="31b25-113">Jóváhagyás után a katalógus közzétehető.</span><span class="sxs-lookup"><span data-stu-id="31b25-113">After the catalog is approved, it can be published.</span></span> <span data-ttu-id="31b25-114">Az ügyfélszolgálati katalógus létrehozásakor, megnézheti a katalógusadatok pillanatképét abban az időpontban, amikor a katalógus közzétele történik.</span><span class="sxs-lookup"><span data-stu-id="31b25-114">When a call center catalog is created, you can take a snapshot of the catalog data at the time that the catalog is published.</span></span> <span data-ttu-id="31b25-115">A pillanatkép-funkció segítségével elérheti a katalógus egy adott verzióját, még akkor is, ha a katalógus később módosul és frissül.</span><span class="sxs-lookup"><span data-stu-id="31b25-115">This snapshot functionality lets you access a particular version of the catalog even if the catalog is later changed and updated.</span></span> <span data-ttu-id="31b25-116">Az ügyfélszolgálati katalógusokat is be lehet állítani, hogy az alábbi választható szolgáltatásokat tartalmazzák:</span><span class="sxs-lookup"><span data-stu-id="31b25-116">Call center catalogs can also be set up to include the following optional features:</span></span>

-   <span data-ttu-id="31b25-117">**Forráskódok** – A forráskódokat az egyes katalógusokra kapott vevői válaszok nyomon követésére használatosak.</span><span class="sxs-lookup"><span data-stu-id="31b25-117">**Source codes** – Source codes are used to track the customer response to specific catalog mailings.</span></span>
-   <span data-ttu-id="31b25-118">**Szabadszöveges termékek** – Termékek, amelyek a vevői rendelésben extra díjak nélkül szerepelnek.</span><span class="sxs-lookup"><span data-stu-id="31b25-118">**Free products** – Products can be included in a customer's order at no additional charge.</span></span> <span data-ttu-id="31b25-119">Ezek a termékek automatikusan hozzáadódnak egy rendeléshez a katalógus forráskódjának a rendelésbe történő bevitelekor.</span><span class="sxs-lookup"><span data-stu-id="31b25-119">These products are automatically added to an order when the source code for the catalog is entered into the order.</span></span>
-   <span data-ttu-id="31b25-120">**Parancsfájlok** – A parancsfájlok szövegek, amelyeket az ügyfélszolgálat dolgozó olvas a vevőnek, egy értékesítési rendelés létrehozásakor.</span><span class="sxs-lookup"><span data-stu-id="31b25-120">**Scripts** – Scripts are texts that a call center worker reads to a customer when a sales order is being created.</span></span> <span data-ttu-id="31b25-121">Parancsfájlok tartalmazhatnak üdvözletet vagy beszerzési javaslatokat.</span><span class="sxs-lookup"><span data-stu-id="31b25-121">Scripts can include greetings or purchase suggestions.</span></span>
-   <span data-ttu-id="31b25-122">**Oldalelrendezés** – Az oldalelrendezés rögzíti a nyomtatott katalógusban szereplő termékek helyét az oldalon.</span><span class="sxs-lookup"><span data-stu-id="31b25-122">**Page layout** – A page layout captures the page position of products in the printed catalog.</span></span> <span data-ttu-id="31b25-123">Ezt az információt használja a katalógusterület-elemzési jelentés.</span><span class="sxs-lookup"><span data-stu-id="31b25-123">This information is used for the catalog area analysis report.</span></span>





