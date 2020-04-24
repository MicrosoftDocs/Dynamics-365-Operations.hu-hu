---
title: Eszközök számlálóinak manuális frissítése
description: Ez a témakör az Eszközkezelésben használt eszközszámlálók manuális frissítését ismerteti.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 9d9cd755f5dec125676a8dbefe63a64e226366ed
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204516"
---
# <a name="manual-update-of-asset-counters"></a><span data-ttu-id="2576d-103">Eszközök számlálóinak manuális frissítése</span><span class="sxs-lookup"><span data-stu-id="2576d-103">Manual update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="2576d-104">A számlálók egy tárgyi eszközre vonatkozó regisztrációk létrehozásához szükségesek, azoknak az eszköz üzemóráinak számára vonatkozóan, illetve a termelt mennyiség szerint.</span><span class="sxs-lookup"><span data-stu-id="2576d-104">Counters are used to create registrations on an asset, such as registrations about the number of hours that the asset has been in operation or the quantity that has been produced.</span></span>

<span data-ttu-id="2576d-105">Előfordulhat, hogy a számlálóhoz kiválasztott számlálótípus be van állítva a számlálóértékek öröklésére.</span><span class="sxs-lookup"><span data-stu-id="2576d-105">The counter type that is selected for a counter might be set to inherit counter values.</span></span> <span data-ttu-id="2576d-106">Más szóval, az **Eszközök számlálók öröklése** beállítás értéke **igen** **Számlálók** lap **Általános** gyorslapján (**Eszközkezelés** > **Beállítások** > **Eszköztípusok** > **Számlálók**).</span><span class="sxs-lookup"><span data-stu-id="2576d-106">In other words, the **Inherit asset counter values** option is set to **Yes** on the **General** FastTab of the **Counters** page (**Asset management** > **Setup** > **Asset types** > **Counters**).</span></span> <span data-ttu-id="2576d-107">Ebben az esetben az ilyen típusú új számláló sor létrehozásakor minden olyan származtatott eszköz automatikusan frissül, amely ugyanazt a számlálótípust használja.</span><span class="sxs-lookup"><span data-stu-id="2576d-107">In this case, when you create a new counter line of that type, every child asset that uses the same counter type is automatically updated.</span></span>

<span data-ttu-id="2576d-108">A **Minden eszköz** lapon, az eszköz leolvasott értékei alapján hozhatja létre az eszköz óraszám- vagy mennyiségszámláló regisztrációit.</span><span class="sxs-lookup"><span data-stu-id="2576d-108">On the **All assets** page, you create hours or quantity counter registrations on an asset, based on your readings on the asset.</span></span>

1. <span data-ttu-id="2576d-109">Válassza ki az **Eszközkezelés** > **Általános** > **Eszközök** > **Összes eszköz** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="2576d-109">Select **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="2576d-110">Jelölje ki az eszközt, majd az **Eszköz** lap műveleti ablakában a **Megelőző** csoportban válassza ki a **Számlálók** elemet.</span><span class="sxs-lookup"><span data-stu-id="2576d-110">Select the asset, and then, on the Action Pane, on the **Asset** tab, in the **Preventive** group, select **Counters**.</span></span> <span data-ttu-id="2576d-111">Az **Eszközszámlálók** oldalon látható a kiválasztott eszközhöz korábban létrehozott számlálóregisztrációk listája.</span><span class="sxs-lookup"><span data-stu-id="2576d-111">The **Asset counters** page shows a list of all previous counter registrations that have been made on the selected asset.</span></span>

3. <span data-ttu-id="2576d-112">Válassza ki az **Új** lehetőséget egy regisztráció létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="2576d-112">Select **New** to create a registration.</span></span> <span data-ttu-id="2576d-113">Az eszközazonosítót a program automatikusan beírja az **Eszköz** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="2576d-113">The asset ID is automatically entered in the **Asset** field.</span></span>

4. <span data-ttu-id="2576d-114">A **Számláló** mezőben válassza ki a megfelelő számlálót.</span><span class="sxs-lookup"><span data-stu-id="2576d-114">In the **Counter** field, select the relevant counter.</span></span> <span data-ttu-id="2576d-115">Csak az eszközön kiválasztott eszköztípushoz kapcsolódó számlálók érhetők el kiválasztásra.</span><span class="sxs-lookup"><span data-stu-id="2576d-115">Only counters that are related to the asset type selected on the asset are available for selection.</span></span> <span data-ttu-id="2576d-116">A program automatikusan beírja a kapcsolódó egységet az **Egység** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="2576d-116">The related unit is automatically entered in the **Unit** field.</span></span>

5. <span data-ttu-id="2576d-117">A **Regisztrált** mezőben válassza ki a számláló regisztrációjának dátumát és időpontját.</span><span class="sxs-lookup"><span data-stu-id="2576d-117">In the **Registered** field, select the date and time for the counter registration.</span></span>

6. <span data-ttu-id="2576d-118">Az **Érték** mezőbe írja be az utolsó számláló regisztrációja utáni számot.</span><span class="sxs-lookup"><span data-stu-id="2576d-118">In the **Value** field, enter the number since the last counter registration.</span></span> <span data-ttu-id="2576d-119">Azt is megteheti, hogy az **Összesített érték** mezőbe beírja a számláló teljes számát.</span><span class="sxs-lookup"><span data-stu-id="2576d-119">Alternatively, in the **Aggregated value** field, enter the total count number.</span></span>

<span data-ttu-id="2576d-120">Vegye figyelembe az alábbiakat:</span><span class="sxs-lookup"><span data-stu-id="2576d-120">Note the following points:</span></span>

- <span data-ttu-id="2576d-121">Ha egy eszközhöz fizikailag telepít új számlálót, akkor a módosítást regisztrálni kell az eszközön az **Eszközszámlálók** oldalon.</span><span class="sxs-lookup"><span data-stu-id="2576d-121">If you physically install a new counter on an asset, you must register the change on the asset on the **Asset counters** page.</span></span> <span data-ttu-id="2576d-122">Ezután két olyan regisztrációs sort kell létrehozni, amelyeknek azonosak az időbélyegei.</span><span class="sxs-lookup"><span data-stu-id="2576d-122">Next, you must create two registration lines that have identical timestamps.</span></span> <span data-ttu-id="2576d-123">Az első sornak a helyettesíteni kívánt számlálóhoz kell tartoznia.</span><span class="sxs-lookup"><span data-stu-id="2576d-123">The first line must be for the counter that you're replacing.</span></span> <span data-ttu-id="2576d-124">Jelölje be az új számlálóhoz kapcsolódó sorban a **Számláló alaphelyzetbe állítása** jelölőnégyzetet.</span><span class="sxs-lookup"><span data-stu-id="2576d-124">On the line that is related to the new counter, select the **Counter reset** check box.</span></span> <span data-ttu-id="2576d-125">Az **Összesen** mezőben lévő teljes szám az adott típusú számláló összes regisztrált értékének az összege.</span><span class="sxs-lookup"><span data-stu-id="2576d-125">In the **Totals** field, the total count number is the sum of the counter totals of all registered values on that counter type.</span></span>

- <span data-ttu-id="2576d-126">Ha a **Számláló alaphelyzetbe állítása** jelölőnégyzet be van jelölve egy olyan eszközön, amelyiknek az időköztípusa „Egyszer ettől...” vagy „Egyszer elérés után...”, akkor a számláló továbbra is aktív az új számlálósorban, mert külön számlálósor jön létre, és a rendszer az új számlálóval kezd újra.</span><span class="sxs-lookup"><span data-stu-id="2576d-126">If the **Counter reset** check box is selected on an asset using a maintenance plan that has a "Once from..." or "Once reached..." interval type, the counter is still active on the new counter line, because you create a separate counter line and start over with a new counter.</span></span>

<span data-ttu-id="2576d-127">Az alábbi ábra az **Eszköszámlálók** oldal egy példáját mutatja be.</span><span class="sxs-lookup"><span data-stu-id="2576d-127">The illustration below shows an example of the **Asset counters** page.</span></span>

![1. ábra](media/11-work-orders.png)

<span data-ttu-id="2576d-129">Az **Eszközszámlálók** oldalon (**Eszközkezelés** > **Lekérdezése** > **Eszközök** > **Eszközszámlálók**) egyszerre több eszközre vonatkozóan is lehet számlálókat regisztrálni.</span><span class="sxs-lookup"><span data-stu-id="2576d-129">On the **Asset counters** page (**Asset management** > **Inquiries** > **Assets** > **Asset counters**), you can make counter registrations on several assets at the same time, as you require.</span></span>

>[!NOTE]
><span data-ttu-id="2576d-130">Egy tartományt úgy állíthat be, hogy meghatározza az eltéréseket a manuális számlálóregisztrációk között.</span><span class="sxs-lookup"><span data-stu-id="2576d-130">You can set up a range to define deviations in manual counter registrations.</span></span> <span data-ttu-id="2576d-131">Azt is megadhatja, hogy milyen típusú üzenetet jelenítsen meg a program, ha a regisztrációk a meghatározott tartományon kívül esnek.</span><span class="sxs-lookup"><span data-stu-id="2576d-131">You can also specify the type of message that is shown if registrations are outside the defined range.</span></span> <span data-ttu-id="2576d-132">Az számlálók beállításával kapcsolatos további információkat lásd: [Számlálók](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="2576d-132">For more information about how to set up counters, see [Counters](../setup-for-objects/counters.md).</span></span>

