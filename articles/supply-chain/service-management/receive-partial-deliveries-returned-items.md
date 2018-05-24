---
title: "Visszaadott cikkek részleges szállításának bevételezése"
description: "A részleges szállítások visszárurendelés-sorok, nem pedig visszárurendelés-szállítmányok formájában vannak meghatározva."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: f9f596d31f2438a353b02bf939786b284937db86
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="receive-partial-deliveries-of-returned-items"></a><span data-ttu-id="d4715-103">Visszaadott cikkek részleges szállításának bevételezése</span><span class="sxs-lookup"><span data-stu-id="d4715-103">Receive partial deliveries of returned items</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="d4715-104">A részleges szállítások visszárurendelés-sorok, nem pedig visszárurendelés-szállítmányok formájában vannak meghatározva.</span><span class="sxs-lookup"><span data-stu-id="d4715-104">Partial deliveries are defined in terms of return order lines, not return order shipments.</span></span>

<span data-ttu-id="d4715-105">Ez azt jelenti, hogy ha a visszárurendelés egyik sorában szereplő teljes mennyiséget visszaküldik, de Ön a többi sor mennyiségéből semmit nem kap meg, akkor a szállítás nem részleges szállítás.</span><span class="sxs-lookup"><span data-stu-id="d4715-105">This means that if you receive the full quantity that is indicated on one return order line, but you receive nothing from the other lines in the return order, the delivery is not a partial delivery.</span></span> <span data-ttu-id="d4715-106">Ha viszont egy visszárurendelés-sorban az adott cikkből 10 kötelezően visszaküldendő egység szerepel, és ebből csak négyet kap meg, akkor ez egy részleges szállítás.</span><span class="sxs-lookup"><span data-stu-id="d4715-106">However, if a return order line requires 10 units of a particular item to be returned, but you receive only four, it is a partial delivery.</span></span>

<span data-ttu-id="d4715-107">Ha egy visszáruszállítmány nem tartalmazza a visszárurendelés-sor teljes mennyiségét, akkor félreteheti a szállítmányt, és megvárhatja, amíg a visszajuttatott mennyiség maradék része is megérkezik, vagy regisztrálhatja és feladhatja a részmennyiséget.</span><span class="sxs-lookup"><span data-stu-id="d4715-107">If a return shipment contains less than the full quantity of a return order line, you can set the shipment aside and wait for the rest of the returned quantity to arrive, or you can register and post the partial quantity.</span></span>

## <a name="register-and-post-a-partial-quantity"></a><span data-ttu-id="d4715-108">A részleges mennyiség regisztrálása és feladása</span><span class="sxs-lookup"><span data-stu-id="d4715-108">Register and post a partial quantity</span></span>

1.  <span data-ttu-id="d4715-109">Miután kiválaszt egy érkeztetendő visszárurendelést a **Beérkezés áttekintése - raktár: %1, Terület: %2, Napló neve: %3** képernyőn, kattintson az **Érkeztetés indítása** elemre egy cikkérkezési napló létrehozásához, majd kattintson a **Naplók**\>**Érkezések megjelenítése a bevételekből** elemre a **Helynapló** képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d4715-109">After you select a return order for arrival on the **Arrival overview - Warehouse: %1, Dock: %2, Journal name: %3** form, click **Start arrival** to create the arrival journal, and then click **Journals** \> **Show arrivals from receipts** to open the **Location journal** form.</span></span>

2.  <span data-ttu-id="d4715-110">Válassza ki azt a naplósort, amellyel dolgozni szeretne, és a **Sorok** gombra kattintva nyissa meg a **Naplósorok, helyek** képernyőt.</span><span class="sxs-lookup"><span data-stu-id="d4715-110">Select the line of the journal that you want to work with, and then click **Lines** to open the **Journal lines, locations** form.</span></span>

3.  <span data-ttu-id="d4715-111">Válassza ki azon cikkszámok sorait, amelyekből a mennyiségnek csak egy része érkezett meg, majd kattintson a **Funkciók** \> **Megosztás** parancsra a **Megosztás** képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="d4715-111">Select the line of the item number for which only a partial quantity has arrived, and then click **Functions** \> **Split** to open the **Split** form.</span></span>

4.  <span data-ttu-id="d4715-112">A **Megosztott mennyiség** mezőben írja be a beérkezett cikkek mennyiségét és teljes számát, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="d4715-112">In the **Split quantity** field, enter the quantity for the total number of items that have been received, and then click **OK**.</span></span>

5.  <span data-ttu-id="d4715-113">A **Naplósorok, helyek** képernyőn a beérkezett cikkmennyiség sorát, és kattintson a **Feladás** gombra.</span><span class="sxs-lookup"><span data-stu-id="d4715-113">On the **Journal lines, locations** form, select the line for the quantity of items that has arrived, and then click **Post**.</span></span> <span data-ttu-id="d4715-114">A további mennyiség sorát akkor adhatja fel, miután a cikkek megérkeznek.</span><span class="sxs-lookup"><span data-stu-id="d4715-114">You can post the line for the additional quantity after the items have arrived.</span></span>





