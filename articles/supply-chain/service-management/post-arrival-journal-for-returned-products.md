---
title: Érkezési napló feladása a visszaküldött termékekhez
description: Érkezési napló feladása a visszaküldött termékekhez.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverview
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 184ce418ff2ec4b891a24b2b75d37b6b4f5d23f3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006641"
---
# <a name="post-arrival-journal-for-returned-products"></a><span data-ttu-id="6131b-103">Érkezési napló feladása a visszaküldött termékekhez</span><span class="sxs-lookup"><span data-stu-id="6131b-103">Post arrival journal for returned products</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="6131b-104">Visszáru feldolgozásakor először érvényesítse a visszaküldött mennyiséget, és módosítsa a mennyiségi mezőt a cikkérkezési naplóban.</span><span class="sxs-lookup"><span data-stu-id="6131b-104">To process a return, first validate the return quantity, update the quantity field in the item arrival journal.</span></span> <span data-ttu-id="6131b-105">Ezután jelöljön ki egy intézkedési kódot, vagy jelezze, hogy a visszaküldött cikkeket meg kell vizsgálni.</span><span class="sxs-lookup"><span data-stu-id="6131b-105">Then select a disposition code or indicate that the returned items have to be inspected.</span></span> <span data-ttu-id="6131b-106">A lépések elvégzése után a visszárurendelés cikkérkezési naplója feladható.</span><span class="sxs-lookup"><span data-stu-id="6131b-106">After completing these steps, you can post the item arrival journal for the return order.</span></span>

1.  <span data-ttu-id="6131b-107">Kattintson a következőkre: **Készletkezelés** \> **Rendszeres** \> **Beérkezés áttekintése**.</span><span class="sxs-lookup"><span data-stu-id="6131b-107">Click **Inventory management** \> **Periodic** \> **Arrival overview**.</span></span>

2.  <span data-ttu-id="6131b-108">A **Beállítás neve** szűrőben válassza ki a **Visszárurendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="6131b-108">In the **Setup name** filter, select **Return order**.</span></span>

3.  <span data-ttu-id="6131b-109">Ha a bevételezések listája túl hosszú, akkor a **Tartomány** terület mezői segítségével szűkítheti a listát.</span><span class="sxs-lookup"><span data-stu-id="6131b-109">If the list of receipts is long, use the fields in the **Range** area to narrow the list.</span></span>

4.  <span data-ttu-id="6131b-110">Keresse meg a feladni kívánt visszárurendelés sorát, jelölje be a **Kijelölés beérkezésre** jelölőnégyzetét, majd kattintson az **Érkeztetés indítása** gombra.</span><span class="sxs-lookup"><span data-stu-id="6131b-110">Locate the line of the return order that you want to post, select its **Select for arrival** box, and then click **Start arrival**.</span></span>

5.  <span data-ttu-id="6131b-111">Kattintson a **Naplók** \>**Érkezések megjelenítése a bevételekből** lehetőségre a **Helynapló** képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="6131b-111">Click **Journals** \> **Show arrivals from receipts** to open the **Location journal** form.</span></span>
    

    > [!TIP]
    > <P><span data-ttu-id="6131b-112">A részletes adatok megjelenítéséhez válasszon egy naplót, majd kattintson a <STRONG>Sorok</STRONG> lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6131b-112">To view detailed information, select a journal, and then click <STRONG>Lines</STRONG>.</span></span></P>


6.  <span data-ttu-id="6131b-113">Végezze el a szükséges módosításokat, majd kattintson a **Küldés** gombra.</span><span class="sxs-lookup"><span data-stu-id="6131b-113">Make any necessary updates, and then click **Post**.</span></span>

<span data-ttu-id="6131b-114">A napló feladása után a program regisztrálja a visszárut a készletben, és a **Visszárurendelések** képernyőn jelzi, hogy a cikkek megérkeztek a raktárba.</span><span class="sxs-lookup"><span data-stu-id="6131b-114">After the journal is posted, the returned items are registered in inventory, and the **Return orders** form indicates that the items have arrived at the warehouse.</span></span>

## <a name="see-also"></a><span data-ttu-id="6131b-115">Lásd még</span><span class="sxs-lookup"><span data-stu-id="6131b-115">See also</span></span>

<span data-ttu-id="6131b-116">[Helynapló (képernyő)](https://technet.microsoft.com/library/aa584822\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="6131b-116">[Location journal (form)](https://technet.microsoft.com/library/aa584822\(v=ax.60\))</span></span>

  


