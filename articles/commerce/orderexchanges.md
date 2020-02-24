---
title: Csere konfigurálása és feldolgozása visszárurendelésen
description: Ez a témakör a cserék visszáru esetén való konfigurálását részletezi a Dynamics 365 Commerce szolgáltatásban.
author: josaw1
manager: AnnBe
ms.date: 11/12/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: a6d7688e78a375bc262b1156c5439c0fff7cd1f0
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004435"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a><span data-ttu-id="2accd-103">Csere konfigurálása és feldolgozása visszárurendelésen</span><span class="sxs-lookup"><span data-stu-id="2accd-103">Configure and process an exchange on a return order</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2accd-104">A Dynamics 365 Commerce korábbi verzióiban a vevő rendelésekre vonatkozó visszárukat a Headquarters szolgáltatásban található visszárurendelési dokumentummal dolgozták fel.</span><span class="sxs-lookup"><span data-stu-id="2accd-104">In previous versions of Dynamics 365 Commerce, returns against customer orders were processed by using the return order document in Headquarters.</span></span> <span data-ttu-id="2accd-105">Azonban a visszárurendelési dokumentumot csak visszaküldött termékek feldolgozására lehet használni.</span><span class="sxs-lookup"><span data-stu-id="2accd-105">However, the return order document can be used to process only products that are being returned.</span></span> <span data-ttu-id="2accd-106">A visszaküldött termékeket a visszárurendelési sorokban negatív mennyiséggel jelölik.</span><span class="sxs-lookup"><span data-stu-id="2accd-106">The returned products are indicated by a negative quantity on the return order lines.</span></span> <span data-ttu-id="2accd-107">Az értékesítéseket ezzel szemben pozitív mennyiséggel jelölik.</span><span class="sxs-lookup"><span data-stu-id="2accd-107">By contrast, sales are indicated by a positive quantity.</span></span> <span data-ttu-id="2accd-108">A visszárurendelési dokumentum azonban nem támogat pozitív mennyiségeket.</span><span class="sxs-lookup"><span data-stu-id="2accd-108">However, the return order document doesn't support positive quantities.</span></span> <span data-ttu-id="2accd-109">Ez a korlátozás azt jelenti, hogy az alkalmazás korábbi verziói nem támogatták az olyan forgatókönyveket, ahol a termékek cseréjét a visszárurendelési dokumentum segítségével végezték.</span><span class="sxs-lookup"><span data-stu-id="2accd-109">Because of this limitation, previous versions of the app didn't support scenarios where product exchanges are done by using the return order document.</span></span>

<span data-ttu-id="2accd-110">Azonban a funkció hozzáadásra került azokhoz a támogatási forgatókönyvekhez, ahol a cseréket visszárurendeléseken végzik.</span><span class="sxs-lookup"><span data-stu-id="2accd-110">However, functionality has been added to support scenarios where exchanges are done on return orders.</span></span> <span data-ttu-id="2accd-111">A Commerce most az ilyen típusú tranzakciók feldolgozásához a visszárurendelés dokumentum helyett az értékesítési rendelési dokumentumot használja.</span><span class="sxs-lookup"><span data-stu-id="2accd-111">Commerce now uses the sales order document instead of the return order document to process these types of transactions.</span></span>

## <a name="configure-commerce-to-support-exchanges-on-return-orders"></a><span data-ttu-id="2accd-112">A Commerce konfigurálása a visszárurendeléseken történő cserék támogatására</span><span class="sxs-lookup"><span data-stu-id="2accd-112">Configure Commerce to support exchanges on return orders</span></span>

<span data-ttu-id="2accd-113">Kövesse az alábbi lépéseket, ha szeretné a rendszert úgy konfigurálni, hogy támogassa a visszárurendeléseken történő cseréket.</span><span class="sxs-lookup"><span data-stu-id="2accd-113">Follow these steps to configure the system to support exchanges on return orders.</span></span>

1. <span data-ttu-id="2accd-114">Lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Commerce paraméterek** menüpontra.</span><span class="sxs-lookup"><span data-stu-id="2accd-114">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**.</span></span> <span data-ttu-id="2accd-115">A **Vevői rendelések** gyorslapon állítsa a **Visszárurendelések feldolgozása értékesítési rendelésként** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="2accd-115">On the **Customer orders** FastTab, set the **Process return orders as sales orders** option to **Yes**.</span></span>
2. <span data-ttu-id="2accd-116">Futtassa a **Globális konfigurációelosztási ütemezés** feladatot (**1110**).</span><span class="sxs-lookup"><span data-stu-id="2accd-116">Run the **Global configuration distribution schedule** job (**1110**).</span></span>

## <a name="make-an-exchange"></a><span data-ttu-id="2accd-117">Csere elvégzése</span><span class="sxs-lookup"><span data-stu-id="2accd-117">Make an exchange</span></span>

<span data-ttu-id="2accd-118">Miután konfigurálta a rendszert az előző lépésben leírtak szerint, a pénztár (POS) felhasználó a visszáru feldolgozására továbbra is értékesítési rendelést vagy értékesítési számlát választ majd, ahogy az alkalmazás korábbi verzióiban is.</span><span class="sxs-lookup"><span data-stu-id="2accd-118">After the system is configured as described in the previous section, the point of sale (POS) user will still select a sales order or sales invoice to process a return, as in previous versions of the app.</span></span> <span data-ttu-id="2accd-119">Azonban miután a visszárucikkeket a kosárhoz adta, a felhasználó új értékesítési sorokat is adhat a kosárhoz.</span><span class="sxs-lookup"><span data-stu-id="2accd-119">However, after the return items are added to the cart, the user will be able to add new sales lines to the cart.</span></span>

<span data-ttu-id="2accd-120">A felhasználónak ezekhez az új értékesítési sorokhoz meg kell határoznia a vevői rendelési sorok feldolgozásához szükséges összes attribútumot.</span><span class="sxs-lookup"><span data-stu-id="2accd-120">For these new sales lines, the user must define all the attributes that are required in order to process a customer order line.</span></span> <span data-ttu-id="2accd-121">Az attribútumok között szerepel a szállítás módja és a teljesítési hely is.</span><span class="sxs-lookup"><span data-stu-id="2accd-121">These attributes include the delivery method and fulfillment location.</span></span> <span data-ttu-id="2accd-122">A tranzakcióra vonatkozóan esedékes fizetés a visszárurendelési sorok és az értékesítési rendelési sorok nettó összege lesz.</span><span class="sxs-lookup"><span data-stu-id="2accd-122">The payment that is due for the transaction will be a net of the return order lines and sales order lines.</span></span> <span data-ttu-id="2accd-123">Amikor a tranzakció kifizetése megtörténik, a visszárurendelés értékesítési rendelési dokumentumként kerül feladásra a Headquarters szolgáltatásban, a rendszer pedig azonnal számlázza a visszárusorokat.</span><span class="sxs-lookup"><span data-stu-id="2accd-123">When payment is tendered for the transaction, the return order will be posted as a sales order document in Headquarters, and the system will immediately invoice the return lines.</span></span>

<span data-ttu-id="2accd-124">Annak érdekében, hogy a kosár különböző összegei kellően átláthatóak legyenek, három új összegmező található a kosárban.</span><span class="sxs-lookup"><span data-stu-id="2accd-124">To provide better visibility into the various amounts for the cart, three new amount fields have been added to the cart.</span></span> <span data-ttu-id="2accd-125">A képernyőtervező segítségével láthatóvá teheti ezeket az új mezőket a pénztár felhasználói felületén (UI).</span><span class="sxs-lookup"><span data-stu-id="2accd-125">You can use the screen designer to make these new fields available in the POS user interface (UI).</span></span>

- <span data-ttu-id="2accd-126">**Alkalmazott letét** – A letét összege, amelyet a rendszer a tranzakcióra alkalmaz, amikor a felhasználó vevői rendelés felvételét végzi.</span><span class="sxs-lookup"><span data-stu-id="2accd-126">**Deposit applied** – The deposit amount that is applied on a transaction when the user does a customer order pickup.</span></span> <span data-ttu-id="2accd-127">Ha nincs letét-felülbírálat, és 10 százalékos letét van beállítva, akkor a mezőben található összeg a vevői rendelés teljes összegének 90 százalékát jeleníti meg.</span><span class="sxs-lookup"><span data-stu-id="2accd-127">If there is no deposit override, and a 10-percent deposit is configured, the amount in this field is 90 percent of the total amount of the customer order.</span></span>
- <span data-ttu-id="2accd-128">**Végrehajtott összeg** – Az olyan sorok teljes összege, ahol a szállítási mód **Végrehajtás** állapotú volt, amikor a vevői rendelést létrehozták vagy szerkesztették, vagy a vevői rendelés cseréje során.</span><span class="sxs-lookup"><span data-stu-id="2accd-128">**Carry out amount** – The total amount for lines where the delivery mode was set to **Carry out** when the customer order was created or edited, or during a customer order exchange.</span></span> <span data-ttu-id="2accd-129">A mezőben található összeg tartalmazza az adókat és díjakat.</span><span class="sxs-lookup"><span data-stu-id="2accd-129">The amount in this field includes taxes and charges.</span></span>
- <span data-ttu-id="2accd-130">**Visszáru összege** – Az olyan sorok teljes összege, amelyek negatív mennyiségekkel rendelkeznek a vevői rendelés cseréje során.</span><span class="sxs-lookup"><span data-stu-id="2accd-130">**Return amount** – The total amount for lines that have negative quantities during the customer order exchange.</span></span> <span data-ttu-id="2accd-131">A mezőben található összeg tartalmazza az adókat és díjakat.</span><span class="sxs-lookup"><span data-stu-id="2accd-131">The amount in this field includes taxes and charges.</span></span>
