---
title: Szállításkezelésből származó vegyes költségek
description: Ez a témakör azt mutatja be, hogyan kell társítani a szállítás által generált költséget a költségkódhoz.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 2b703d770c7f9ea684716368cf1e7dbe5fec8710
ms.sourcegitcommit: fe7ac653efcb1ac6318083f482394b96ed82b4c7
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/29/2020
ms.locfileid: "4429988"
---
# <a name="transportation-management-miscellaneous-charges"></a><span data-ttu-id="1de75-103">Szállításkezelésből származó vegyes költségek</span><span class="sxs-lookup"><span data-stu-id="1de75-103">Transportation management miscellaneous charges</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1de75-104">Mint minden vegyes költségnél, a szállítás által generált költséghez is hozzá kell társítani a költségkódot.</span><span class="sxs-lookup"><span data-stu-id="1de75-104">As with all miscellaneous charges, transportation-generated charges must be associated with a charge code.</span></span> <span data-ttu-id="1de75-105">Ellenkező esetben nem kerülnek a rendelésbe vegyes költségként.</span><span class="sxs-lookup"><span data-stu-id="1de75-105">Otherwise, they won't be added back to the order as a miscellaneous charge.</span></span> <span data-ttu-id="1de75-106">A **Költségek kódja** határozza meg, hogyan történik a költség elszámolása annál a rendelésnél és rendelési sornál, amelyhez hozzá lett adva.</span><span class="sxs-lookup"><span data-stu-id="1de75-106">The **Charges code** determines how the charge is accounted for in relation to the order and order line where it is added.</span></span>

<span data-ttu-id="1de75-107">Menjen a **Szállításkezelés > Beállítás > Minősítés > Vegyes költségek** lehetőségre, és határozza meg a minősítési feltételeket, amelyek meghatározzák, hogy mikor alkalmaznak egy adott **Költségkódot** a költségnél.</span><span class="sxs-lookup"><span data-stu-id="1de75-107">Go to **Transportation management > Setup > Rating > Miscellaneous charges** to define the qualifying criteria that determine when a specific **Charges code** is applied to a charge.</span></span>

<span data-ttu-id="1de75-108">Legalább egy beállítást ki kell választania minden olyan releváns **Költségmodul** beállításhoz (*Ügyfél* és *Szállító*), amelyben a **Vegyes költség típusa** *Egyik sem* értékre van állítva.</span><span class="sxs-lookup"><span data-stu-id="1de75-108">You should have at least one setup for each relevant **Charges module** setting (*Customer* and *Vendor*) where the **Miscellaneous charge type** is set to *None*.</span></span> <span data-ttu-id="1de75-109">Ha nincs megadva, a vegyes költséget *nem* adja hozzá a program a rendeléshez.</span><span class="sxs-lookup"><span data-stu-id="1de75-109">If this is missing, the miscellaneous charge will *not* be added to the order.</span></span>
