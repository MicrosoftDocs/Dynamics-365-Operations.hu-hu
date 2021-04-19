---
title: Összesített kötegrendelések
description: Ez a cikk az összesített kötegrendelések koncepcióját mutatja be.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PmfAddToConsOrder, PmfBulkItemConv, PmfBulkPackOnHand, PmfConsOrderListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19291
ms.assetid: e97f1d3d-1306-4c42-b2bc-d1755fe574d5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e8d7656889b69cfd1dcffb45b52eb649bce59629
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809230"
---
# <a name="consolidated-batch-orders"></a><span data-ttu-id="c9e2e-103">Összesített kötegrendelések</span><span class="sxs-lookup"><span data-stu-id="c9e2e-103">Consolidated batch orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c9e2e-104">Ez a cikk az összesített kötegrendelések koncepcióját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="c9e2e-104">This article describes the concept of consolidated batch orders.</span></span>

<span data-ttu-id="c9e2e-105">Az ömlesztett cikket tekintjük szülőcikknek, a csomagolt cikket pedig gyermekcikknek.</span><span class="sxs-lookup"><span data-stu-id="c9e2e-105">A bulk item that is produced is considered a parent item, whereas a packed item is considered a child item.</span></span> <span data-ttu-id="c9e2e-106">Az ömlesztett cikk és a csomagolt cikk közötti összefüggés az ömlesztett cikk konverziója.</span><span class="sxs-lookup"><span data-stu-id="c9e2e-106">The relation between the bulk item and the packed item is expressed in a bulk item conversion.</span></span> <span data-ttu-id="c9e2e-107">Az ömlesztett cikk konverzióját magában az ömlesztett cikkben kell meghatározni.</span><span class="sxs-lookup"><span data-stu-id="c9e2e-107">This bulk item conversion is defined on the bulk item itself.</span></span>  

<span data-ttu-id="c9e2e-108">A csomagolt cikkek egy vagy több tárolóra lehetnek csomagolva, amelyek egy egységnek számítanak, emellett lehetnek azonos vagy különböző méretűek.</span><span class="sxs-lookup"><span data-stu-id="c9e2e-108">Packed items can be packaged into containers of either a single size or multiple sizes that are considered one unit.</span></span> <span data-ttu-id="c9e2e-109">Ömlesztett cikkre vonatkozó rendelések összesítésekor megtekintheti az összes kapcsolódó kötegrendelést egyetlen nézetben, amelynek segítségével könnyebben megállapítható a fennmaradó munka, amelyet el kell végezni.</span><span class="sxs-lookup"><span data-stu-id="c9e2e-109">By consolidating the orders for a bulk item, you can see all the related batch orders in a single view that can help you determine any remaining work that must be completed.</span></span>  

<span data-ttu-id="c9e2e-110">Az összesített kötegrendelés a következő rendelések bármely kombinációját tartalmazhatja:</span><span class="sxs-lookup"><span data-stu-id="c9e2e-110">A consolidated batch order can contain any combination of the following orders:</span></span>

-   <span data-ttu-id="c9e2e-111">Egyetlen tömeges rendelés, több csomagolt rendeléssel</span><span class="sxs-lookup"><span data-stu-id="c9e2e-111">A single bulk order and multiple packed orders</span></span>
-   <span data-ttu-id="c9e2e-112">Több tömeges rendelés, több csomagolt rendeléssel</span><span class="sxs-lookup"><span data-stu-id="c9e2e-112">Multiple bulk orders and multiple packed orders</span></span>
-   <span data-ttu-id="c9e2e-113">Több tömeges rendelés, egyetlen csomagolt rendeléssel</span><span class="sxs-lookup"><span data-stu-id="c9e2e-113">Multiple bulk orders and a single packed order</span></span>
-   <span data-ttu-id="c9e2e-114">Csak csomagolt rendelések</span><span class="sxs-lookup"><span data-stu-id="c9e2e-114">Only packed orders</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]