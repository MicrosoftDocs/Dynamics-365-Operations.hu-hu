---
title: Időablakok
description: Időablakok segítségével optimalizálhatja a szervizrendeléssorok ütemezését.
author: ShylaThompson
manager: tfehr
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATimeAgreement
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 63a166806c2c8ac84cc1d71d6ec84fcb28033feb
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206519"
---
# <a name="time-windows"></a><span data-ttu-id="b2562-103">Időablakok</span><span class="sxs-lookup"><span data-stu-id="b2562-103">Time windows</span></span>  

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b2562-104">Időablakok segítségével optimalizálhatja a szervizrendeléssorok ütemezését.</span><span class="sxs-lookup"><span data-stu-id="b2562-104">You can use time windows to optimize the scheduling of service order lines.</span></span> <span data-ttu-id="b2562-105">Beállíthatja, hogy a rendszer automatikusan létrehozza a szervizrendeléseket.</span><span class="sxs-lookup"><span data-stu-id="b2562-105">You can set up the system so that it automatically creates service orders.</span></span> <span data-ttu-id="b2562-106">Az időszak által meghatározott feltételek alapján a lehető legtöbb szervizrendeléssort csatlakoztathatja a lehető legkevesebb szervizrendeléshez.</span><span class="sxs-lookup"><span data-stu-id="b2562-106">Based on the criteria specified by a time window, you can connect as many service order lines as possible to as few service orders as possible.</span></span>

<span data-ttu-id="b2562-107">Az időszakok meghatározzák, hogy milyen távol kerülhetnek a szervizrendeléssorok a számított dátumukhoz képest.</span><span class="sxs-lookup"><span data-stu-id="b2562-107">Time windows specify how far a service order line can move from its calculated date.</span></span> <span data-ttu-id="b2562-108">A kiszámított dátum az a dátum, amikorra a szervizrendeléssor végrehajtását ütemezték.</span><span class="sxs-lookup"><span data-stu-id="b2562-108">The calculated date is the date when the service order line was scheduled to occur.</span></span> <span data-ttu-id="b2562-109">A dátum alapját az intervallum beállítása képezi, továbbá az a szervizidőszak, amelyet meghatározott a **Szervizrendelések létrehozása** lapon.</span><span class="sxs-lookup"><span data-stu-id="b2562-109">The date is based on its interval setting and the service period that you defined in the **Create service orders** page.</span></span> <span data-ttu-id="b2562-110">Az időszakok a következő táblázat értékeivel határozhatók meg.</span><span class="sxs-lookup"><span data-stu-id="b2562-110">You define a time window by using the values in the following table.</span></span>

| <span data-ttu-id="b2562-111">Metódus</span><span class="sxs-lookup"><span data-stu-id="b2562-111">Method</span></span> | <span data-ttu-id="b2562-112">Leírás</span><span class="sxs-lookup"><span data-stu-id="b2562-112">Description</span></span>                                                                                                                                                                                                                                                                                           |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="b2562-113">Hét</span><span class="sxs-lookup"><span data-stu-id="b2562-113">Week</span></span>   | <span data-ttu-id="b2562-114">A szervizrendeléssor dátuma a kiindulási számított dátum hetén belül bármelyik napra áthelyezhető.</span><span class="sxs-lookup"><span data-stu-id="b2562-114">The date that the service order line can be moved to any open day in the same week as the initial calculated date.</span></span>                                                                                                                                                                                    |
| <span data-ttu-id="b2562-115">Hónap</span><span class="sxs-lookup"><span data-stu-id="b2562-115">Month</span></span>  | <span data-ttu-id="b2562-116">A szervizrendeléssor dátuma a kiindulási számított dátum hónapján belül bármelyik napra áthelyezhető.</span><span class="sxs-lookup"><span data-stu-id="b2562-116">The date that the service order line can be moved to any open day in the same month as the initial calculated date.</span></span> <span data-ttu-id="b2562-117">Például egy szervizrendeléssor számított dátuma 2017. február 15.</span><span class="sxs-lookup"><span data-stu-id="b2562-117">For example, the calculated date for a service order line is February 15, 2017.</span></span> <span data-ttu-id="b2562-118">A szervizrendeléssor bármelyik hétköznapra ütemezhető 2017. február 1. és 2017. február 28. között.</span><span class="sxs-lookup"><span data-stu-id="b2562-118">The service order line can be scheduled for any weekday between February 1 and February 28, 2017.</span></span> |
| <span data-ttu-id="b2562-119">Manuális</span><span class="sxs-lookup"><span data-stu-id="b2562-119">Manual</span></span> | <span data-ttu-id="b2562-120">Azoknak a napoknak a maximális számát kell meghatároznia, amellyel a szervizrendeléssor a kiindulási számított dátumnál korábbra vagy későbbre ütemezhető.</span><span class="sxs-lookup"><span data-stu-id="b2562-120">You define the maximum number of days before or after the initial calculated date that the service order line can be moved.</span></span>                                                                                                                                                                           |

<span data-ttu-id="b2562-121">Ha a szolgáltatásiszerződés-sorra nem határoz meg időszakot, akkor a szerződéssorból származó szervizrendeléssort pontosan azon a napon kell végrehajtani, amelyre eredetileg ütemezték.</span><span class="sxs-lookup"><span data-stu-id="b2562-121">If you do not specify a time window for a service agreement line, the service order line that is derived from the service agreement must be on the exact date for which it was originally scheduled.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b2562-122">Kapcsolódó témakörök</span><span class="sxs-lookup"><span data-stu-id="b2562-122">Related topics</span></span>

[<span data-ttu-id="b2562-123">Időablakok létrehozása</span><span class="sxs-lookup"><span data-stu-id="b2562-123">Create time windows</span></span>](create-time-windows.md)

