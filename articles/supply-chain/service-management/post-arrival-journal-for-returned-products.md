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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c96f1499cf9ef93a56a636f990aa5d0d183f9627
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3202128"
---
# <a name="post-arrival-journal-for-returned-products"></a><span data-ttu-id="b2bd2-103">Érkezési napló feladása a visszaküldött termékekhez</span><span class="sxs-lookup"><span data-stu-id="b2bd2-103">Post arrival journal for returned products</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="b2bd2-104">Visszáru feldolgozásakor először érvényesítse a visszaküldött mennyiséget, és módosítsa a mennyiségi mezőt a cikkérkezési naplóban.</span><span class="sxs-lookup"><span data-stu-id="b2bd2-104">To process a return, first validate the return quantity, update the quantity field in the item arrival journal.</span></span> <span data-ttu-id="b2bd2-105">Ezután jelöljön ki egy intézkedési kódot, vagy jelezze, hogy a visszaküldött cikkeket meg kell vizsgálni.</span><span class="sxs-lookup"><span data-stu-id="b2bd2-105">Then select a disposition code or indicate that the returned items have to be inspected.</span></span> <span data-ttu-id="b2bd2-106">A lépések elvégzése után a visszárurendelés cikkérkezési naplója feladható.</span><span class="sxs-lookup"><span data-stu-id="b2bd2-106">After completing these steps, you can post the item arrival journal for the return order.</span></span>

1.  <span data-ttu-id="b2bd2-107">Kattintson a következőkre: **Készletkezelés** \> **Rendszeres** \> **Beérkezés áttekintése**.</span><span class="sxs-lookup"><span data-stu-id="b2bd2-107">Click **Inventory management** \> **Periodic** \> **Arrival overview**.</span></span>

2.  <span data-ttu-id="b2bd2-108">A **Beállítás neve** szűrőben válassza ki a **Visszárurendelés** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="b2bd2-108">In the **Setup name** filter, select **Return order**.</span></span>

3.  <span data-ttu-id="b2bd2-109">Ha a bevételezések listája túl hosszú, akkor a **Tartomány** terület mezői segítségével szűkítheti a listát.</span><span class="sxs-lookup"><span data-stu-id="b2bd2-109">If the list of receipts is long, use the fields in the **Range** area to narrow the list.</span></span>

4.  <span data-ttu-id="b2bd2-110">Keresse meg a feladni kívánt visszárurendelés sorát, jelölje be a **Kijelölés beérkezésre** jelölőnégyzetét, majd kattintson az **Érkeztetés indítása** gombra.</span><span class="sxs-lookup"><span data-stu-id="b2bd2-110">Locate the line of the return order that you want to post, select its **Select for arrival** box, and then click **Start arrival**.</span></span>

5.  <span data-ttu-id="b2bd2-111">Kattintson a **Naplók** \>**Érkezések megjelenítése a bevételekből** lehetőségre a **Helynapló** képernyő megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="b2bd2-111">Click **Journals** \> **Show arrivals from receipts** to open the **Location journal** form.</span></span>
    

    > [!TIP]
    > <P><span data-ttu-id="b2bd2-112">A részletes adatok megjelenítéséhez válasszon egy naplót, majd kattintson a <STRONG>Sorok</STRONG> lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="b2bd2-112">To view detailed information, select a journal, and then click <STRONG>Lines</STRONG>.</span></span></P>


6.  <span data-ttu-id="b2bd2-113">Végezze el a szükséges módosításokat, majd kattintson a **Küldés** gombra.</span><span class="sxs-lookup"><span data-stu-id="b2bd2-113">Make any necessary updates, and then click **Post**.</span></span>

<span data-ttu-id="b2bd2-114">A napló feladása után a program regisztrálja a visszárut a készletben, és a **Visszárurendelések** képernyőn jelzi, hogy a cikkek megérkeztek a raktárba.</span><span class="sxs-lookup"><span data-stu-id="b2bd2-114">After the journal is posted, the returned items are registered in inventory, and the **Return orders** form indicates that the items have arrived at the warehouse.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2bd2-115">Lásd még</span><span class="sxs-lookup"><span data-stu-id="b2bd2-115">See also</span></span>

<span data-ttu-id="b2bd2-116">[Helynapló (képernyő)](https://technet.microsoft.com/library/aa584822\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="b2bd2-116">[Location journal (form)](https://technet.microsoft.com/library/aa584822\(v=ax.60\))</span></span>

  


