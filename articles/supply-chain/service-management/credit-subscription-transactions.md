---
title: Előfizetési tranzakciók jóváírása
description: Ez a témakör bemutatja, hogy hogyan lehet előfizetésidíj-tranzakciót jóváírni.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4238c625930767990d28a206b10a4d71841f2ad8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247502"
---
# <a name="credit-subscription-transactions"></a><span data-ttu-id="6f273-103">Előfizetési tranzakciók jóváírása</span><span class="sxs-lookup"><span data-stu-id="6f273-103">Credit subscription transactions</span></span> 

[!include [banner](../includes/banner.md)]


## <a name="credit-subscription-transactions"></a><span data-ttu-id="6f273-104">Előfizetési tranzakciók jóváírása</span><span class="sxs-lookup"><span data-stu-id="6f273-104">Credit subscription transactions</span></span>

1.  <span data-ttu-id="6f273-105">Kattintson a következőkre: **Szolgáltatáskezelés**\>**Közös**\>**Szolgáltatási előfizetések**\>**Minden szolgáltatási előfizetés**.</span><span class="sxs-lookup"><span data-stu-id="6f273-105">Click **Service management** \> **Common** \> **Service subscriptions** \> **All service subscriptions**.</span></span>

2.  <span data-ttu-id="6f273-106">Válassza ki azt az előfizetést, amely ahhoz az előfizetési tranzakcióhoz van csatolva, amelyet jóvá szeretne írni.</span><span class="sxs-lookup"><span data-stu-id="6f273-106">Select the subscription attached to the subscription transaction for which you want to create a credit note.</span></span>

3.  <span data-ttu-id="6f273-107">A Műveleti ablaktáblán válassza ki az **Elemzés** lapot, majd kattintson a **Díjtranzakciók** gombra.</span><span class="sxs-lookup"><span data-stu-id="6f273-107">Select the **Analyze** tab, and then click the **Fee transactions** button on the Action Pane.</span></span>

4.  <span data-ttu-id="6f273-108">A **Díjtranzakciók** képernyőn válassza ki azt a tranzakciót, amelyhez jóváírást szeretne létrehozni.</span><span class="sxs-lookup"><span data-stu-id="6f273-108">From the **Fee transactions** form, select the transaction for which you want to create a credit note.</span></span>

5.  <span data-ttu-id="6f273-109">Kattintson a **Funkciók** \> **Kijelölés jóváíráshoz** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="6f273-109">Click **Functions** \> **Select for credit note**.</span></span>

6.  <span data-ttu-id="6f273-110">A **Kijelölés jóváíráshoz** képernyőn válassza ki azt a tranzakciót, amelyet jóvá akar írni, majd kattintson az **OK** gombra.</span><span class="sxs-lookup"><span data-stu-id="6f273-110">From the **Select for credit note** form, select the transaction that you want to credit and then click **OK**.</span></span>


> [!NOTE]
> <P><span data-ttu-id="6f273-111">A jóváírás létrehozásakor feltétlenül a <STRONG>Jóváírások</STRONG> beállítást kell választani.</span><span class="sxs-lookup"><span data-stu-id="6f273-111">When you create the credit note, make sure that you select <STRONG>Credit notes</STRONG>.</span></span> <span data-ttu-id="6f273-112">Ez a <STRONG>Számlázás módja</STRONG> listán található, a <STRONG>Számla létrehozása</STRONG> párbeszédpanelben.</span><span class="sxs-lookup"><span data-stu-id="6f273-112">This is found in the <STRONG>Invoicing method</STRONG> list in the <STRONG>Create invoice</STRONG> dialog box.</span></span></P>

<span data-ttu-id="6f273-113">Ha a **Szolgáltatáskezelés paraméterei** képernyő **Könyvelések sztornírozása jóváíráskor** beállítása a **Manuális** értékre van állítva, egyenként sztorníroznia kell minden elhatárolt árbevétel-tranzakciót, és csak ezt követően hozhatja létre a tranzakció jóváírási javaslatát.</span><span class="sxs-lookup"><span data-stu-id="6f273-113">If the **Reverse accruals on crediting** field in the **Service management parameters** form is set to **Manual**, you have to reverse each accrued revenue transaction individually before you create a credit note proposal for the transaction.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f273-114">Lásd még</span><span class="sxs-lookup"><span data-stu-id="6f273-114">See also</span></span>

[<span data-ttu-id="6f273-115">Előfizetési tranzakciók számlázása</span><span class="sxs-lookup"><span data-stu-id="6f273-115">Invoice subscription transactions</span></span>](invoice-subscription-transactions.md)


 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]