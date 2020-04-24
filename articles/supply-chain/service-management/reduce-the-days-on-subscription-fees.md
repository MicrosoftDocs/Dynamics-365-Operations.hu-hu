---
title: Előfizetési díjak napjainak csökkentése
description: Ha egy meglévő előfizetési díjnál csökkenteni szeretné a napok számát, létrehozhat egy új tranzakciót, amelyben eltávolítja azt az időtartamot, amelynek már nem kell szerepelnie az előfizetési intervallumban.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd76e30b14d0fd21617e0ab7d892ba5ea3e89f2f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/02/2020
ms.locfileid: "3217310"
---
# <a name="reduce-the-days-on-subscription-fees"></a><span data-ttu-id="f95b2-103">Előfizetési díjak napjainak csökkentése</span><span class="sxs-lookup"><span data-stu-id="f95b2-103">Reduce the days on subscription fees</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="f95b2-104">Ha egy meglévő előfizetési díjnál csökkenteni szeretné a napok számát, létrehozhat egy új tranzakciót, amelyben eltávolítja azt az időtartamot, amelynek már nem kell szerepelnie az előfizetési intervallumban.</span><span class="sxs-lookup"><span data-stu-id="f95b2-104">To reduce the number of days of an existing subscription fee, you can create a new transaction in which you remove the period of time that should no longer be part of the subscription fee interval.</span></span>

## <a name="reduce-the-days-on-a-subscription-fee"></a><span data-ttu-id="f95b2-105">Előfizetési díj napjainak csökkentése</span><span class="sxs-lookup"><span data-stu-id="f95b2-105">Reduce the days on a subscription fee</span></span>

1.  <span data-ttu-id="f95b2-106">Kattintson a következőkre: **Szolgáltatáskezelés**\>**Közös**\>**Szolgáltatási előfizetések**\>**Minden szolgáltatási előfizetés**.</span><span class="sxs-lookup"><span data-stu-id="f95b2-106">Click **Service management** \> **Common** \> **Service subscriptions** \> **All service subscriptions**.</span></span> <span data-ttu-id="f95b2-107">Jelölje ki a szolgáltatási előfizetést, majd a műveleti ablaktáblán kattintson az **Előfizetési díjak** elemre.</span><span class="sxs-lookup"><span data-stu-id="f95b2-107">Select the service subscription, and on the Action Pane, click **Subscription fees**</span></span>

2.  <span data-ttu-id="f95b2-108">Az **Előfizetés típusa** mezőben válassza ki a **Csökkentési napok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="f95b2-108">In the **Subscription type** field, select **Reduction days**.</span></span>

3.  <span data-ttu-id="f95b2-109">A **Kezdő dátum** és a **Záró dátum** mezőkkel adja meg az előfizetéses időszakból eltávolítani kívánt előfizetési díj dátumintervallumát, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="f95b2-109">Use the **From date** field and the **To date** fields to define the date interval of the subscription fee that you want to remove from the subscription fee period, and then click **OK**.</span></span>

<span data-ttu-id="f95b2-110">A létrehozott tranzakció megtekintéséhez kattintson az **Előfizetés** képernyőn a **Díjtranzakciók** elemre.</span><span class="sxs-lookup"><span data-stu-id="f95b2-110">To view the transaction that was created, in the **Subscription** form, click **Fee transactions**.</span></span>

## <a name="example"></a><span data-ttu-id="f95b2-111">Példa</span><span class="sxs-lookup"><span data-stu-id="f95b2-111">Example</span></span>

<span data-ttu-id="f95b2-112">Ha egy előfizetési tranzakció időszaka január 1-től január 31-ig tart, és az időtartamot 10 nappal csökkenteni szeretné, hozzon létre új tranzakciót, amelynél a csökkentési időszak január 1-től január 10-ig tart.</span><span class="sxs-lookup"><span data-stu-id="f95b2-112">If a subscription transaction period runs from January 1 to January 31, and you want to reduce the period by 10 days, create a new transaction in which the reduction period is January 1 to January 10.</span></span> <span data-ttu-id="f95b2-113">(A csökkentési időszak ugyanúgy tarthat január 5-től január 15-ig vagy lehet bármely más tíz napos időszak.)</span><span class="sxs-lookup"><span data-stu-id="f95b2-113">(The reduction period could also be January 5 to January 15, or any other ten day period).</span></span>

<span data-ttu-id="f95b2-114">Továbbá ha a csökkentési időszaknál a **Kezdő dátum** értéke január 21. (31-ből 10), a **Záró dátum** értékét január 31-e utáni bármilyen dátumra beállíthatja, akkor is 10 nappal lesz kevesebb az előfizetéses tranzakció tartama.</span><span class="sxs-lookup"><span data-stu-id="f95b2-114">Also, if the **From date** on the reduction period is January 21 (31 minus 10), you could set the **To date** to any date after January 31, and 10 days will still be removed from the fee transaction period.</span></span>

## <a name="see-also"></a><span data-ttu-id="f95b2-115">Lásd még</span><span class="sxs-lookup"><span data-stu-id="f95b2-115">See also</span></span>

[<span data-ttu-id="f95b2-116">Csökkentési napok – Példa</span><span class="sxs-lookup"><span data-stu-id="f95b2-116">Reduction days example</span></span>](reduction-days-example.md)

  


