---
title: Kifizetési ütemezések beállítása TDS-felosztással
description: Ez a témakör elmagyarázza, hogyan állíthatja be a fizetési ütemezéseket a Forrásnál levont adóval (TDS) történő felosztással.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 47551f52f35fec5ae49d696e3f4027b7d2eb2e19
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023306"
---
# <a name="set-up-payment-schedules-with-tds-allocation"></a><span data-ttu-id="a1d49-103">Kifizetési ütemezések beállítása TDS-felosztással</span><span class="sxs-lookup"><span data-stu-id="a1d49-103">Set up payment schedules with TDS allocation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a1d49-104">Ez a témakör elmagyarázza, hogyan állíthatja be a fizetési ütemezéseket a Forrásnál levont adóval (TDS) történő felosztással.</span><span class="sxs-lookup"><span data-stu-id="a1d49-104">This topic explains how to set up payment schedules with Tax Deducted at Source (TDS) allocation.</span></span>

1. <span data-ttu-id="a1d49-105">Ugrás a **Kötelezettségek \> Kifizetés beállítása \> Kifizetés ütemezése** elemre.</span><span class="sxs-lookup"><span data-stu-id="a1d49-105">Go to **Accounts payable \> Payment setup \> Payment schedules**.</span></span>

    <span data-ttu-id="a1d49-106">[![Kifizetési ütemezések oldal](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)</span><span class="sxs-lookup"><span data-stu-id="a1d49-106">[![Payment schedules page](./media/apac-ind-TDS-27.png)](./media/apac-ind-TDS-27.png)</span></span>

2. <span data-ttu-id="a1d49-107">A Műveletablakban válassza az **Új** lehetőséget a kifizetési ütemezés létrehozásához, és adja meg a szükséges adatokat.</span><span class="sxs-lookup"><span data-stu-id="a1d49-107">On the Action Pane, select **New** to create a payment schedule, and enter the required details.</span></span>
3. <span data-ttu-id="a1d49-108">A **Felosztás** mezőben válassza ki a fizetési ütemezéshez szükséges fizetési mód felosztásának módját:</span><span class="sxs-lookup"><span data-stu-id="a1d49-108">In the **Allocation** field, select the method to use to allocate the payment for the payment schedule:</span></span>

    - <span data-ttu-id="a1d49-109">Teljes</span><span class="sxs-lookup"><span data-stu-id="a1d49-109">Total</span></span>
    - <span data-ttu-id="a1d49-110">Rögzített összeg</span><span class="sxs-lookup"><span data-stu-id="a1d49-110">Fixed amount</span></span>
    - <span data-ttu-id="a1d49-111">Rögzített mennyiség</span><span class="sxs-lookup"><span data-stu-id="a1d49-111">Fixed quantity</span></span>
    - <span data-ttu-id="a1d49-112">Meghatározott</span><span class="sxs-lookup"><span data-stu-id="a1d49-112">Specified</span></span>

    <span data-ttu-id="a1d49-113">Az **Adóelőleg-felosztás** mező a fizetési ütemezés TDS-felosztási módját mutatja.</span><span class="sxs-lookup"><span data-stu-id="a1d49-113">The **Withholding tax allocation** field shows the TDS allocation method for the payment schedule.</span></span> <span data-ttu-id="a1d49-114">Ha a **Felosztás** mezőben az **Összes** lehetőséget választja, az **Adóelőleg-felosztás** mező automatikusan az **Összes** mezőre lesz állítva.</span><span class="sxs-lookup"><span data-stu-id="a1d49-114">If you select **Total** in the **Allocation** field, the **Withholding tax allocation** field is automatically set to **Total**.</span></span> <span data-ttu-id="a1d49-115">Ha a **Fix összeg**, **Fix mennyiség** vagy a **Meghatározott** lehetőséget választja a **Felosztás** mezőben, az **Adóelőleg-felosztás** mező automatikusan **Arányosra** lesz beállítva.</span><span class="sxs-lookup"><span data-stu-id="a1d49-115">If you select **Fixed amount**, **Fixed quantity**, or **Specified** in the **Allocation** field, the **Withholding tax allocation** field is automatically set to **Proportionally**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a1d49-116">Ha az **Adóelőleg-felosztás** mező az **Összes** értékre van állítva, a fizetési részletek kiszámítása a bruttó összeg alapján történik, amely tartalmazza a TDS-összegét.</span><span class="sxs-lookup"><span data-stu-id="a1d49-116">If the **Withholding tax allocation** field is set to **Total**, the payment installments are calculated based on the gross amount, which includes the TDS amount.</span></span> <span data-ttu-id="a1d49-117">Ha az **Adóelőleg-felosztás** mező az **Arányosan** értékre van állítva, a fizetési részletek kiszámítása a nettó számla alapján történik, a TDS-összeg levonását követően.</span><span class="sxs-lookup"><span data-stu-id="a1d49-117">If the **Withholding tax allocation** field is set to **Proportionally**, the payment installments are calculated based on the net invoice amount after the TDS amount is deducted.</span></span>

4. <span data-ttu-id="a1d49-118">Adja meg a többi kötelező adatot, majd zárja be az oldalt.</span><span class="sxs-lookup"><span data-stu-id="a1d49-118">Enter the other required details, and then close the page.</span></span>
