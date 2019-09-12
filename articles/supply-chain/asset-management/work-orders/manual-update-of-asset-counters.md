---
title: Eszközök számlálóinak manuális frissítése
description: Ez a témakör az Eszközkezelésben használt eszközszámlálók manuális frissítését ismerteti.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1e7c5ec288404c18b00f9dcd0e66f50744d0aa2f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875695"
---
# <a name="manual-update-of-asset-counters"></a><span data-ttu-id="d2313-103">Eszközök számlálóinak manuális frissítése</span><span class="sxs-lookup"><span data-stu-id="d2313-103">Manual update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="d2313-104">A számlálókkal regisztrációk hozhatók létre egy eszközön, például a művelet óraszámával vagy a gyártott mennyiséggel kapcsolatban.</span><span class="sxs-lookup"><span data-stu-id="d2313-104">Counters are used to create registrations on an asset regarding, for example, number of hours in operation, or the number of quantities produced.</span></span>

<span data-ttu-id="d2313-105">Ha a számlálóhoz kiválasztott típust a számláló értékeinek öröklésére állítja (az **Eszközkezelés** > **Beállítás** > **Eszköztípusok** > **Számlálók** > **Általános** gyorslap > **Elem számlálóértékeinek öröklése** váltógomb „Igen” értékű), és új adott típusú számlálósort hoz létre, akkor az adott számlálótípust használó alárendelt eszközök automatikusan frissülnek.</span><span class="sxs-lookup"><span data-stu-id="d2313-105">If the counter type selected for a counter is set to inherit counter values (**Asset management** > **Setup** > **Asset types** > **Counters** > **General** FastTab > **Inherit asset counter values** toggle button set to "Yes"), then, when you create a new counter line of that type, every child asset that uses the same counter type is automatically updated.</span></span>

<span data-ttu-id="d2313-106">A **Minden eszköz** részen, az eszköz leolvasott értékei alapján hozhatja létre az eszköz óraszám- vagy mennyiségszámláló regisztrációit.</span><span class="sxs-lookup"><span data-stu-id="d2313-106">In **All assets**, you create hours or quantity counter registrations on an asset, based on your readings on the asset.</span></span>

1. <span data-ttu-id="d2313-107">Kattintson az **Eszközkezelés** > **Általános** > **Eszközök** > **Összes eszköz** elemre.</span><span class="sxs-lookup"><span data-stu-id="d2313-107">Click **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="d2313-108">Válassza ki az eszközt a listából, majd kattintson a **Számlálók** elemre.</span><span class="sxs-lookup"><span data-stu-id="d2313-108">Select the asset in the list, and click **Counters**.</span></span> <span data-ttu-id="d2313-109">Az **Eszközszámlálók** képernyőn látható a kiválasztott eszköz korábbi számlálóregisztrációinak a listája.</span><span class="sxs-lookup"><span data-stu-id="d2313-109">In the **Asset counters** form, you see a list of all previous counter registrations on the selected asset.</span></span>

3. <span data-ttu-id="d2313-110">Új regisztráció létrehozásához kattintson az **Új** gombra.</span><span class="sxs-lookup"><span data-stu-id="d2313-110">Click **New** to create a new registration.</span></span> <span data-ttu-id="d2313-111">A program automatikusan beszúrja az eszközazonosítót.</span><span class="sxs-lookup"><span data-stu-id="d2313-111">The asset ID is automatically inserted.</span></span>

4. <span data-ttu-id="d2313-112">A **Számláló** mezőben válassza ki a megfelelő számlálót.</span><span class="sxs-lookup"><span data-stu-id="d2313-112">In the **Counter** field, select the relevant counter.</span></span> <span data-ttu-id="d2313-113">Csak az eszközön kiválasztott eszköztípushoz kapcsolódó számlálók érhetők el.</span><span class="sxs-lookup"><span data-stu-id="d2313-113">Only counters related to the asset type selected on the asset are available.</span></span> <span data-ttu-id="d2313-114">A program automatikusan beilleszti a kapcsolódó egységet az **Egység** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="d2313-114">The related unit is automatically inserted in the **Unit** field.</span></span>

5. <span data-ttu-id="d2313-115">Válassza ki a számláló regisztrációjának dátumát és időpontját.</span><span class="sxs-lookup"><span data-stu-id="d2313-115">Select date and time for the counter registration.</span></span>

6. <span data-ttu-id="d2313-116">Az **Érték** mezőbe írja be a legutóbbi számlálóregisztráció óta létrehozott számot, vagy az **Összesített érték** mezőbe írja be a teljes számot.</span><span class="sxs-lookup"><span data-stu-id="d2313-116">In the **Value** field, insert the number since the last counter registration, or, in the **Aggregated value** field, insert the total count number.</span></span>

- <span data-ttu-id="d2313-117">Ha egy eszközhöz fizikailag telepít új számlálót, akkor a módosítást regisztrálni kell az eszközön az **Eszközszámlálók** részen.</span><span class="sxs-lookup"><span data-stu-id="d2313-117">If you physically install a new counter on an asset, you need to register the change on the asset in **Asset counters**.</span></span> <span data-ttu-id="d2313-118">Ezután két, azonos időbélyegzővel rendelkező regisztrációs sort kell létrehoznia, és az új számláló sorában be kell jelölni a **Számláló alaphelyzetbe állítása** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="d2313-118">Next, you must create two registration lines with identical timestamps, and on the line regarding the new counter, you select the **Counter reset** check box.</span></span> <span data-ttu-id="d2313-119">A két regisztrációs sor létrehozásakor az első sor tartozzon a helyettesíteni kívánt számlálóhoz.</span><span class="sxs-lookup"><span data-stu-id="d2313-119">When you create the two registration lines, the first line must be for the counter that you are replacing.</span></span> <span data-ttu-id="d2313-120">Az **Összesen** mezőben lévő teljes szám az adott típusú számláló összes regisztrált értékének az összege.</span><span class="sxs-lookup"><span data-stu-id="d2313-120">In the **Totals** field, the total count number is the sum of the counter total of all registered values on that counter type.</span></span>  
- <span data-ttu-id="d2313-121">Ha a **Számláló alaphelyzetbe állítása** jelölőnégyzet be van jelölve egy olyan eszközön, amelyiknek az időköztípusa „Egyszer ettől...” vagy „Egyszer elérés után...”, akkor a számláló továbbra is aktív az új számlálósorban, mert külön számlálósor jön létre, és a rendszer az új számlálóval kezd újra.</span><span class="sxs-lookup"><span data-stu-id="d2313-121">If the **Counter reset** check box is selected on an asset using a maintenance plan with a "Once from..." or "Once reached..." interval type, the counter is still active on the new counter line because you create a separate counter line and start over with a new counter.</span></span>

![1. ábra](media/11-work-orders.png)


<span data-ttu-id="d2313-123">Ha több eszközön kell számlálót regisztrálnia, akkor ezt az **Eszközkezelés** > **Lekérdezések** > **Eszközök** > **Eszközszámlálók** részen teheti meg.</span><span class="sxs-lookup"><span data-stu-id="d2313-123">If you need to make counter registrations on several assets, that can be done in **Asset management** > **Inquiries** > **Assets** > **Asset counters**.</span></span>

>[!NOTE]
><span data-ttu-id="d2313-124">A manuális számlálóregisztrációk eltéréseinek meghatározásához beállíthat tartományt, illetve megadhatja azt az üzenettípust, amelyet meg kell jeleníteni, ha a regisztrációk a megadott tartományon kívül esnek.</span><span class="sxs-lookup"><span data-stu-id="d2313-124">You can set up a range to define deviations in manual counter registrations, and the type of message that should be displayed if registrations are outside the defined range.</span></span> <span data-ttu-id="d2313-125">A számlálók beállításáról a [Számlálók](../setup-for-objects/counters.md) című cikkben talál további információt.</span><span class="sxs-lookup"><span data-stu-id="d2313-125">Refer to the [Counters](../setup-for-objects/counters.md) topic regarding setup of counters.</span></span>
