---
title: Átvételi információ modul
description: Ez a témakör az átvételi információk modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni a fizetési oldalakhoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-09021
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: d04e2650f9c601d008ebf19080059b70416d7917
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000609"
---
# <a name="pickup-information-module"></a><span data-ttu-id="8707f-103">Átvételi információ modul</span><span class="sxs-lookup"><span data-stu-id="8707f-103">Pickup information module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8707f-104">Ez a témakör az átvételi információk modullal foglalkozik, és bemutatja, hogy hogyan lehet azt hozzáadni a fizetési oldalakhoz a Microsoft Dynamics 365 Commerce alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="8707f-104">This topic covers the pickup information module and describes how to add it to checkout pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8707f-105">Az átvételi információk modul egy fizetési modulban használható a rendelésfelvételi információk megjelenítéséhez.</span><span class="sxs-lookup"><span data-stu-id="8707f-105">The pickup information module can be used in a checkout module to show order pickup information.</span></span> <span data-ttu-id="8707f-106">Az ügyfelek megtekinthetik a rendelkezésre álló felvételi dátumokat és időközöket, majd kiválaszthatják a megfelelő időpontot a rendelés felvételéhez.</span><span class="sxs-lookup"><span data-stu-id="8707f-106">Customers can view available pickup dates and time slots, and then select a suitable time to pick up their order.</span></span> <span data-ttu-id="8707f-107">Például egy vevő választhat, hogy március 21-én 15:00 órakor vesz fel egy rendelést a San Francisco-i üzletből.</span><span class="sxs-lookup"><span data-stu-id="8707f-107">For example, a customer can choose to pick up an order at 3 PM on March 21 from the San Francisco store.</span></span>

<span data-ttu-id="8707f-108">A megfelelő üzletek felvételi időközeit a Commerce központjában kell konfigurálni.</span><span class="sxs-lookup"><span data-stu-id="8707f-108">Pickup time slots for the appropriate stores must be configured in Commerce headquarters.</span></span> <span data-ttu-id="8707f-109">További információért lásd: [Időközök létrehozása és frissítése a vevői átvételhez](dev-itpro/pickup-timeslots.md).</span><span class="sxs-lookup"><span data-stu-id="8707f-109">For more information, see [Create and update time slots for customer pickup](dev-itpro/pickup-timeslots.md).</span></span>

<span data-ttu-id="8707f-110">Ha egy felvételi információs modul jön létre a pénztár oldalon, de nincs időköz meghatározva a csomagfelvételre kiválasztott üzlethez, a modul információkat jelenít meg, de a felhasználó nem tud időközöket kiválasztani.</span><span class="sxs-lookup"><span data-stu-id="8707f-110">If a pickup information module is created on a checkout page, but no time slots are defined for the store that is selected for pickup, the module will show information, but the user won't be able to select any time slots.</span></span> <span data-ttu-id="8707f-111">Az időközök nem kötelezőek, és nem kell rendelést leadniuk.</span><span class="sxs-lookup"><span data-stu-id="8707f-111">Time slots are optional and aren't required to place an order.</span></span>

<span data-ttu-id="8707f-112">Ha több cikket választ ki több üzletben történő felvételhez, a felvételi információs modul lehetővé teszi a felhasználó számára, hogy minden üzlethez válasszon egy idősávot, feltéve, hogy rendelkezésre állnak időközök.</span><span class="sxs-lookup"><span data-stu-id="8707f-112">If multiple items are selected for pickup across multiple stores, the pickup information module will let the user select a time slot for each store, provided that time slots are available for it.</span></span>

> [!NOTE]
> <span data-ttu-id="8707f-113">Az időközök és a fizetési felvételi információs modul támogatása a Dynamics 365 Commerce 10.0.15-ös és újabb verzióban érhető el.</span><span class="sxs-lookup"><span data-stu-id="8707f-113">Support for time slots and the checkout pickup information module is available in Dynamics 365 Commerce version 10.0.15 and later.</span></span>

<span data-ttu-id="8707f-114">A következő ábra egy példát mutat be az idősáv kiválasztására a felvételi információs modulon keresztül a pénztár oldalon.</span><span class="sxs-lookup"><span data-stu-id="8707f-114">The following illustration shows an example of time slot selection through the pickup information module on a checkout page.</span></span>

![Példa egy átvételi információk modulra egy fizetési oldalon](./dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="module-properties"></a><span data-ttu-id="8707f-116">Modul tulajdonságai</span><span class="sxs-lookup"><span data-stu-id="8707f-116">Module properties</span></span>

- <span data-ttu-id="8707f-117">**Címsor** – Adja meg a modul címsora.</span><span class="sxs-lookup"><span data-stu-id="8707f-117">**Heading** – Enter a heading for the module.</span></span>

## <a name="show-time-slot-information-after-an-order-is-placed"></a><span data-ttu-id="8707f-118">Időközadatok megjelenítése a megrendelés után</span><span class="sxs-lookup"><span data-stu-id="8707f-118">Show time slot information after an order is placed</span></span>

<span data-ttu-id="8707f-119">A megrendelés elküldése után a kiválasztott idősávra vonatkozó információk megtekinthetők a [rendelés-visszaigazolási modulban](order-confirmation-module.md) és a [rendelés részletei modulban](account-management.md#order-details-page).</span><span class="sxs-lookup"><span data-stu-id="8707f-119">After an order is placed, information about the selected time slot can be viewed in the [order confirmation module](order-confirmation-module.md) and the [order details module](account-management.md#order-details-page).</span></span> <span data-ttu-id="8707f-120">Mindkét modul rendelkezik az **Időközadatok megjelenítése** tulajdonsággal.</span><span class="sxs-lookup"><span data-stu-id="8707f-120">Both these modules have a **Show timeslot information** property.</span></span> <span data-ttu-id="8707f-121">Mielőtt a rendelési folyamat során megmutathatják a kijelölt időközt, a tulajdonságot **Igaz** értékre kell állítani.</span><span class="sxs-lookup"><span data-stu-id="8707f-121">Before they can show the selected time slot during the order process, this property must be set to **True**.</span></span>

## <a name="add-a-checkout-pickup-information-module-to-a-page"></a><span data-ttu-id="8707f-122">Fizetési átvételi információk modul hozzáadása egy fizetési oldalhoz</span><span class="sxs-lookup"><span data-stu-id="8707f-122">Add a checkout pickup information module to a page</span></span>

<span data-ttu-id="8707f-123">Az átvételi információk modulnak a pénztár laphoz való hozzáadásával és a szükséges tulajdonságok beállításával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Fizetési modul](add-checkout-module.md).</span><span class="sxs-lookup"><span data-stu-id="8707f-123">For instructions about how to add a pickup information module to a checkout page and set the required properties, see [Checkout module](add-checkout-module.md).</span></span>

<span data-ttu-id="8707f-124">A következő ábra egy e-kereskedelmi fizetési oldalt mutat be, amely időközöket tartalmaz a sorelemek átvételéhez.</span><span class="sxs-lookup"><span data-stu-id="8707f-124">The following illustration shows an example of an e-Commerce checkout page that includes time slots for pickup line items.</span></span>

![Egy e-kereskedelmi fizetési oldal példája, amely időközöket tartalmaz a sorelemek átvételéhez](./dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="additional-resources"></a><span data-ttu-id="8707f-126">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="8707f-126">Additional resources</span></span>

[<span data-ttu-id="8707f-127">Időközök létrehozása és frissítése a vevői átvételhez</span><span class="sxs-lookup"><span data-stu-id="8707f-127">Create and update time slots for customer pickup</span></span>](dev-itpro/pickup-timeslots.md)

[<span data-ttu-id="8707f-128">Pénztármodul</span><span class="sxs-lookup"><span data-stu-id="8707f-128">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="8707f-129">Rendelésmegerősítési modul</span><span class="sxs-lookup"><span data-stu-id="8707f-129">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="8707f-130">Rendelési részletek modul</span><span class="sxs-lookup"><span data-stu-id="8707f-130">Order details module</span></span>](account-management.md)
