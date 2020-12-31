---
title: Eszközlízing fizetési ütemezések megerősítése kötegben
description: Ez a témakör azt mutatja be, hogyan lehet több fizetési ütemezést megerősíteni egy kötegben.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b5a90b96ac598d145e2b0697627de04731b55f59
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444180"
---
# <a name="confirm-asset-leasing-payment-schedules-in-a-batch"></a><span data-ttu-id="a8ee8-103">Eszközlízing fizetési ütemezések megerősítése kötegben</span><span class="sxs-lookup"><span data-stu-id="a8ee8-103">Confirm Asset leasing payment schedules in a batch</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8ee8-104">Ez a témakör azt mutatja be, hogyan lehet több fizetési ütemezést megerősíteni egy kötegben.</span><span class="sxs-lookup"><span data-stu-id="a8ee8-104">This topic explains how to confirm multiple payment schedules in a batch.</span></span> <span data-ttu-id="a8ee8-105">A kifizetési ütemezéseket vagy a lízingtől-lízingig alapján vagy a megerősítési köteg folyamatán keresztül lehet megerősíteni.</span><span class="sxs-lookup"><span data-stu-id="a8ee8-105">Payment schedules are confirmed either on a lease-to-lease basis or through the confirmation batch process.</span></span> <span data-ttu-id="a8ee8-106">A naplóbejegyzés csak a jóváhagyott fizetési ütemezéssel rendelkező lízingek esetében adható fel.</span><span class="sxs-lookup"><span data-stu-id="a8ee8-106">A journal entry can be posted only against a lease that has a confirmed payment schedule.</span></span> <span data-ttu-id="a8ee8-107">A kifizetési ütemezés megerősítése a lízing pénzügyi adatainak végleges jóváhagyására szolgál.</span><span class="sxs-lookup"><span data-stu-id="a8ee8-107">Confirmation of the payment schedule serves as a final approval of the financial information for the lease.</span></span> <span data-ttu-id="a8ee8-108">A lízing pénzügyi adatainak jövőbeli változásai – például a kifizetések és a lízingfutamidő – a lízingkiigazítást jelentik, és ennek megfelelően kell feldolgozni.</span><span class="sxs-lookup"><span data-stu-id="a8ee8-108">All future changes to the financial information for the lease, such as payments and the lease term, constitute a lease adjustment and should be processed in that way.</span></span>

<span data-ttu-id="a8ee8-109">Több fizetési ütemezés jóváhagyásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="a8ee8-109">To confirm multiple payment schedules, follow these steps.</span></span>

1. <span data-ttu-id="a8ee8-110">Nyissa meg az **Eszközlízing \> Időszakos \> Megerősített köteg** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a8ee8-110">Go to **Asset leasing \> Periodic \> Confirmation batch**.</span></span>
2. <span data-ttu-id="a8ee8-111">A **Megerősített köteg** lapon válassza ki a **Megerősített köteg** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="a8ee8-111">On the **Confirmation batch** page, select **Confirmation batch**.</span></span>
3. <span data-ttu-id="a8ee8-112">A megjelenő párbeszédpanelen szűrje a megerősíteni kívánt könyveket.</span><span class="sxs-lookup"><span data-stu-id="a8ee8-112">In the dialog box that appears, filter for the books that you want to confirm.</span></span>

    - <span data-ttu-id="a8ee8-113">Egy adott lízingcsoportba tartozó összes könyv jóváhagyásához válassza ki a csoportot a **Lízingcsoport** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a8ee8-113">To confirm all the books in a specific lease group, select the group in the **Lease group** field.</span></span>
    - <span data-ttu-id="a8ee8-114">Meghatározott könyvek jóváhagyásához válassza ki a könyveket a **Könyvazonosító** mezőben.</span><span class="sxs-lookup"><span data-stu-id="a8ee8-114">To confirm specific books, select the books in the **Book ID** field.</span></span>
    - <span data-ttu-id="a8ee8-115">Az összes könyv jóváhagyásához kapcsolja be az **Összes könyvhöz** paramétert.</span><span class="sxs-lookup"><span data-stu-id="a8ee8-115">To confirm all books, turn on the **For all books** parameter.</span></span>

<span data-ttu-id="a8ee8-116">Az újonnan visszaigazolt könyvekre vonatkozó információk a **Megerősített könyvek** oldalon láthatók.</span><span class="sxs-lookup"><span data-stu-id="a8ee8-116">Information for the newly confirmed books is shown on the **Confirmed books** page.</span></span> <span data-ttu-id="a8ee8-117">A kifizetési ütemezések jóváhagyása után a rendszer a lízingek alapján feladja a kezdeti megjelenítési naplóbejegyzéseket.</span><span class="sxs-lookup"><span data-stu-id="a8ee8-117">After the payment schedules are confirmed, the initial recognition journal entries can be posted against the leases.</span></span>
