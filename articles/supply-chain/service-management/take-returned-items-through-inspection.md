---
title: "A visszaadott cikkek vizsgálatának végigvitele"
description: "A visszaadott cikkek vizsgálatának végigvitele."
author: YuyuScheller
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventQuarantineOrder
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
ms.openlocfilehash: df209cfdbdef591e9f24161b3651316c43d69ee0
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---


# <a name="take-returned-items-through-inspection"></a><span data-ttu-id="c8309-103">A visszaadott cikkek vizsgálatának végigvitele</span><span class="sxs-lookup"><span data-stu-id="c8309-103">Take returned items through inspection</span></span> 

[!include [banner](../includes/banner.md)]


1.  <span data-ttu-id="c8309-104">Kattintson ide: **Készletkezelés** \> **Időszakos** \> **Minőségkezelés** \> **Karanténutasítások**.</span><span class="sxs-lookup"><span data-stu-id="c8309-104">Click **Inventory management** \> **Periodic** \> **Quality management** \> **Quarantine orders**.</span></span>

2.  <span data-ttu-id="c8309-105">Keresse meg azt a rendeléssort, amely megfelel a vizsgált visszáru cikknek.</span><span class="sxs-lookup"><span data-stu-id="c8309-105">Locate the order line that corresponds to the returned item that you are inspecting.</span></span>

    > [!NOTE]
    > <P><span data-ttu-id="c8309-106">Egy karanténutasítás csak egyetlen cikkszámhoz társítható.</span><span class="sxs-lookup"><span data-stu-id="c8309-106">A quarantine order can be associated with just a single item number.</span></span> <span data-ttu-id="c8309-107">Ha 10 különböző cikkszámú cikk érkezik vissza egyetlen szállítmányban, és ezeket karanténba helyezik, akkor 10 külön karanténutasítást kell létrehozni.</span><span class="sxs-lookup"><span data-stu-id="c8309-107">If 10 items that have different item numbers are returned in a single shipment and sent to quarantine, 10 individual quarantine orders are created.</span></span></P>

3.  <span data-ttu-id="c8309-108">A cikk vizsgálata után az **Intézkedési kód** mező beállításával jelezheti, hogy mit kell tenni a cikkel, és milyen kapcsolódó pénzügyi tranzakciókat kell kezelni, amik a következők lehetnek:</span><span class="sxs-lookup"><span data-stu-id="c8309-108">After examining the item, make a selection in the **Disposition code** field to indicate what should be done with the item and how to handle the related financial transaction.</span></span> <span data-ttu-id="c8309-109">a cikk visszavétele a készletbe és az ár visszatérítése, a cikk leselejtezése és cserecikk küldése a vevőnek, vagy a cikk visszaküldése a vevőnek, és a költségek kiszámlázása.</span><span class="sxs-lookup"><span data-stu-id="c8309-109">Examples include returning the item to stock and refunding the customer, scrapping the item and sending a replacement to the customer, or returning the item to the customer without credit.</span></span>
    
    > [!NOTE]
    > <P><span data-ttu-id="c8309-110">Ha egy cikkszámkötegben több visszaadott cikk nem társítható ugyanahhoz az intézkedési kódhoz, akkor az egyes részkötegekre vonatkozó különböző intézkedési kódoknak megfelelően fel kell bontani a karanténutasítást (<STRONG>Funkciók</STRONG> &gt; <STRONG>Felosztás</STRONG>).</span><span class="sxs-lookup"><span data-stu-id="c8309-110">If multiple returned items in a single item number batch cannot be assigned the same disposition code, you must split the quarantine order (<STRONG>Functions</STRONG> &gt; <STRONG>Split</STRONG>) to assign a different disposition code to each sub-batch.</span></span></P>


4.  <span data-ttu-id="c8309-111">A kivizsgálás befejezése után a **Készként jelentés** lehetőségre kattintva kiadhatja a visszaadott cikkeket, és létrehozhat egy cikkérkezési naplóbejegyzést.</span><span class="sxs-lookup"><span data-stu-id="c8309-111">When you are finished with the inspection, click **Report as finished** to release the returned items and create an item arrival journal entry.</span></span> <span data-ttu-id="c8309-112">A cikkeket fogadó személy vagy részleg ezután feldolgozza a készletbe visszahelyezendő cikkek naplóját.</span><span class="sxs-lookup"><span data-stu-id="c8309-112">The person or department that receives the items then processes the journal for the items to be returned to inventory.</span></span>
    
    <span data-ttu-id="c8309-113">– vagy –</span><span class="sxs-lookup"><span data-stu-id="c8309-113">–or–</span></span>
    
    <span data-ttu-id="c8309-114">Fejezze be a karanténutasítást, és helyezze vissza a cikkeket közvetlenül a készletbe a **Készlet** gomb valamelyik funkciójával.</span><span class="sxs-lookup"><span data-stu-id="c8309-114">End the quarantine order, and move the items back into inventory directly by using one of the **Inventory** functions.</span></span>

5.  <span data-ttu-id="c8309-115">A módosítások mentéséhez zárja be a képernyőt.</span><span class="sxs-lookup"><span data-stu-id="c8309-115">Close the form to save your changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8309-116">Lásd még</span><span class="sxs-lookup"><span data-stu-id="c8309-116">See also</span></span>

[<span data-ttu-id="c8309-117">A visszaadott cikkek kivezetési módjának megadása</span><span class="sxs-lookup"><span data-stu-id="c8309-117">Specify how to dispose of returned items</span></span>](specify-how-to-dispose-of-returned-items.md)

  



