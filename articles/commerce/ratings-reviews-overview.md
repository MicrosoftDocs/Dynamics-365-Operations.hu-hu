---
title: Minősítések és értékelések áttekintése
description: Ez a témakör a Microsoft Dynamics 365 Commerce minősítéseit és értékeléseit mutatja be.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ed31982dad8af4509d8dd0615ae53e3d3806640f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979778"
---
# <a name="ratings-and-reviews-overview"></a><span data-ttu-id="fa759-103">Minősítések és értékelések áttekintése</span><span class="sxs-lookup"><span data-stu-id="fa759-103">Ratings and reviews overview</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="fa759-104">Ez a témakör a Microsoft Dynamics 365 Commerce minősítéseit és értékeléseit mutatja be.</span><span class="sxs-lookup"><span data-stu-id="fa759-104">This topic covers ratings and reviews in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="fa759-105">Áttekintés</span><span class="sxs-lookup"><span data-stu-id="fa759-105">Overview</span></span>

<span data-ttu-id="fa759-106">A minősítések és az értékelések fontosak az e-kereskedelmi vevők számára, akik szeretnék megismerni, hogy a vevők milyen véleménnyel vannak a termékekről.</span><span class="sxs-lookup"><span data-stu-id="fa759-106">Ratings and reviews are crucial for e-Commerce customers who want to know how other customers perceive a product.</span></span> <span data-ttu-id="fa759-107">Emellett segítséget jelenthetnek a vásárlók számára a vásárlási döntések meghozatalában.</span><span class="sxs-lookup"><span data-stu-id="fa759-107">They can also help consumers make purchase decisions.</span></span> <span data-ttu-id="fa759-108">A Dynamics 365 Commerce alkalmazásban, a minősítések és a vélemények lehetővé teszik a kereskedők számára, hogy rögzítsék a vevőktől származó minősítéseket és értékeléseket.</span><span class="sxs-lookup"><span data-stu-id="fa759-108">In Dynamics 365 Commerce, the ratings and reviews solution lets retailers capture product reviews and ratings from customers.</span></span> <span data-ttu-id="fa759-109">A kiskereskedők ezután az átlagos minősítéseket és az értékeléseket megjeleníthetik e-Commerce-webhelyükön.</span><span class="sxs-lookup"><span data-stu-id="fa759-109">Retailers can then show average ratings and review information across their e-Commerce website.</span></span>

<span data-ttu-id="fa759-110">Az átlagos minősítési információ a pénztár (POS) és hívásközpont csatornákon jelenik meg.</span><span class="sxs-lookup"><span data-stu-id="fa759-110">Average rating information is shown in point of sale (POS) and call center channels.</span></span> <span data-ttu-id="fa759-111">Ennek megfelelően az értékesítési társítások segítenek a felhasználóknak a döntéshozatalban.</span><span class="sxs-lookup"><span data-stu-id="fa759-111">Therefore, sales associates can use it to help users make decisions.</span></span> <span data-ttu-id="fa759-112">A minősítések és a vélemények visszajelzési mechanizmusként is szolgálhatnak, amellyel a kiskereskedők egy termék minőségét javíthatják, így növelve az értékesítéseket.</span><span class="sxs-lookup"><span data-stu-id="fa759-112">Ratings and reviews can also serve as a feedback mechanism that retailers can use to improve the quality of a product and therefore increase sales.</span></span>

<span data-ttu-id="fa759-113">A Dynamics 365 Commerce minősítések és értékelések funkciója egy többcsatornás megoldás, amely natív módon érhető el a platform részeként.</span><span class="sxs-lookup"><span data-stu-id="fa759-113">Ratings and reviews functionality in Dynamics 365 Commerce is an omnichannel solution and is natively available as part of the platform.</span></span> <span data-ttu-id="fa759-114">A minősítések és a értékelések megoldás a Microsoft Azure felületre épül, amely magas színtű méretezhetőséget és megbízhatóságot biztosít.</span><span class="sxs-lookup"><span data-stu-id="fa759-114">The ratings and reviews solution is built on top of Microsoft Azure, which provides high scalability and reliability.</span></span>

<span data-ttu-id="fa759-115">A következő ábra bemutatja, hogyan működik a Dynamics 365 Commerce minősítések és a vélemények megoldása.</span><span class="sxs-lookup"><span data-stu-id="fa759-115">The following illustration shows how the ratings and reviews solution works in Dynamics 365 Commerce.</span></span>

![Értékelések és vélemények a Dynamics 365 for Commerce megoldásban](media/Dynamics-365-Commerce-Ratings-and-Reviews-Overview.jpg)

<span data-ttu-id="fa759-117">Az értékelések és vélemények a Dynamics 365 Commerce megoldásban az Azure Cognitive Services szolgáltatásokat kínálja, a sértő szavak automatikus szűrésére 40 nyelven.</span><span class="sxs-lookup"><span data-stu-id="fa759-117">The ratings and reviews solution in Dynamics 365 Commerce uses Azure Cognitive Services to offer automatic moderation of profane words in 40 languages.</span></span> <span data-ttu-id="fa759-118">Mivel az emberi jóváhagyás nem szükséges, a moderálási költségeket csökkenti a program.</span><span class="sxs-lookup"><span data-stu-id="fa759-118">Because human approval isn't required, moderation costs are reduced.</span></span> <span data-ttu-id="fa759-119">A rendszer olyan moderátori eszközöket is kínál, amelyek a vevői aggályok, visszajelzések és levételi kérelmek megválaszolására, valamint a felhasználóktól érkező adatkérések megválaszolására is használhatók.</span><span class="sxs-lookup"><span data-stu-id="fa759-119">The system also offers moderator tools that can be used to respond to customer concerns, feedback, and take-down requests, and to address data requests from users.</span></span>

<span data-ttu-id="fa759-120">Az értékelések és vélemények megoldás olyan minialkalmazásokat tartalmaz, amelyek a termékek listáiban, a keresési eredmények között, a termék részletei oldalon és más helyeken a minősítési összesítőket megjelenítik.</span><span class="sxs-lookup"><span data-stu-id="fa759-120">The ratings and reviews solution provides widgets that show rating summaries in product lists, in search results, on product details page, and in other places.</span></span> <span data-ttu-id="fa759-121">A minialkalmazások teljes ellenőrzési listákat jelenítenek meg, és rendezési és szűrési beállításokat is tartalmaznak.</span><span class="sxs-lookup"><span data-stu-id="fa759-121">The widgets show complete review lists, and they also provide sorting and filtering options.</span></span>

<span data-ttu-id="fa759-122">Az értékelések és vélemények megoldás egy üzleti intelligencia (BI) sablont is tartalmaz, amely olyan mérőszámokat tartalmaz, amelyek betekintést nyújtanak az értékelésekkel és véleményekkel kapcsolatosan.</span><span class="sxs-lookup"><span data-stu-id="fa759-122">The ratings and reviews solution also provides a business intelligence (BI) template that includes a set of metrics to provide insights into ratings and reviews.</span></span> <span data-ttu-id="fa759-123">Az értékelések és a vélemények adatait további elemzések céljából is exportálni lehet.</span><span class="sxs-lookup"><span data-stu-id="fa759-123">Ratings and reviews data can be exported for further analysis.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fa759-124">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="fa759-124">Additional resources</span></span>

[<span data-ttu-id="fa759-125">A minősítések és ellenőrzések használatának kiválasztása</span><span class="sxs-lookup"><span data-stu-id="fa759-125">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="fa759-126">Minősítések és értékelések kezelése</span><span class="sxs-lookup"><span data-stu-id="fa759-126">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="fa759-127">Minősítések és értékelések konfigurálása</span><span class="sxs-lookup"><span data-stu-id="fa759-127">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="fa759-128">A termék minősítések szinkronizálása a következőben: Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="fa759-128">Sync product ratings in Dynamics 365 Commerce</span></span>](sync-product-ratings.md)
