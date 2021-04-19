---
title: Visszárurendelés visszatérítése elutasítva
description: Ez a témakör hibaelhárítási útmutatást tartalmaz arra vonatkozóan, hogy segítséget nyújtson akkor, amikor a visszárurendelés visszatérítését elutasítják, mivel a számlázáshoz használt hitelkártya különbözik az eredeti fizetés engedélyezésekor használt kártyától.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 5961e77de1de5dc23454fc1a6e16f8c0b4e7cc6a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801555"
---
# <a name="refund-on-a-return-order-is-declined"></a><span data-ttu-id="7907b-103">Visszárurendelés visszatérítése elutasítva</span><span class="sxs-lookup"><span data-stu-id="7907b-103">Refund on a return order is declined</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7907b-104">Ez a témakör hibaelhárítási útmutatást tartalmaz arra vonatkozóan, hogy segítséget nyújtson akkor, amikor a visszárurendelés visszatérítését elutasítják, mivel a számlázáshoz használt hitelkártya különbözik az eredeti fizetés engedélyezésekor használt kártyától.</span><span class="sxs-lookup"><span data-stu-id="7907b-104">This topic provides troubleshooting guidance that can help when a refund on a return order is declined because the credit card that is used for invoicing differs from the card that was used during the original payment authorization.</span></span>

## <a name="description"></a><span data-ttu-id="7907b-105">Leírás</span><span class="sxs-lookup"><span data-stu-id="7907b-105">Description</span></span>

<span data-ttu-id="7907b-106">A visszatérítés nem alkalmazható, ha a visszárurendelés számlázására használt hitelkártya eltér az eredeti fizetés engedélyezésekor használt kártyától.</span><span class="sxs-lookup"><span data-stu-id="7907b-106">A refund is declined when the credit card that is used to invoice a return order differs from the card that was used during the original payment authorization.</span></span> <span data-ttu-id="7907b-107">A következő hibaüzenet jelenik meg: „Egyes kifizetések feladási állapota nem megfelelő.</span><span class="sxs-lookup"><span data-stu-id="7907b-107">You receive the following error message: "Some payments are not in the correct status for posting.</span></span> <span data-ttu-id="7907b-108">Számlázás előtt ellenőrizze újra az összes kifizetés állapotát.”</span><span class="sxs-lookup"><span data-stu-id="7907b-108">Please re-validate the status of all payments prior to invoicing."</span></span>

<span data-ttu-id="7907b-109">A fizetésengedélyezési részletek a következő hibaüzenetet tartalmazzák: „Az Adyen gateway SendRequest() sikertelen volt "InternalServerError".22144; Adyen üres választ adott vissza. (22001);”</span><span class="sxs-lookup"><span data-stu-id="7907b-109">The payment authorization details will include the following error message: "Adyen gateway SendRequest() failed with status 'InternalServerError'.22144; Empty response returned from Adyen.(22001);"</span></span>

![Visszárurendelés visszatérítését elutasították](media/refund-order-decline.jpg)

## <a name="resolution"></a><span data-ttu-id="7907b-111">Felbontás</span><span class="sxs-lookup"><span data-stu-id="7907b-111">Resolution</span></span>

### <a name="enable-blind-returns-in-adyen"></a><span data-ttu-id="7907b-112">Nyugta nélküli visszatérítések engedélyezése az Adyenben</span><span class="sxs-lookup"><span data-stu-id="7907b-112">Enable blind returns in Adyen</span></span>

<span data-ttu-id="7907b-113">A nyugta nélküli visszatérítések engedélyezéséhez kövesse a [Hibaelhárítás a Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](adyen-support.md) rész lépéseit az Adyen támogatási csapattal történő kapcsolatfelvételhez és annak kérvényezéséhez, hogy engedélyezzék Adyen kereskedői számláján a nyugta nélküli visszatérítéseket.</span><span class="sxs-lookup"><span data-stu-id="7907b-113">To enable blind returns, follow the steps in [Troubleshoot Dynamics 365 Payment Connector for Adyen issues](adyen-support.md) to contact the Adyen support team and request that blind returns be enabled on your Adyen merchant account.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7907b-114">További erőforrások</span><span class="sxs-lookup"><span data-stu-id="7907b-114">Additional resources</span></span>

[<span data-ttu-id="7907b-115">Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz</span><span class="sxs-lookup"><span data-stu-id="7907b-115">Dynamics 365 Payment Connector for Adyen</span></span>](../dev-itpro/adyen-connector.md)

[<span data-ttu-id="7907b-116">Adyen fizetési összekötő a Dynamics 365 szolgáltatáshoz</span><span class="sxs-lookup"><span data-stu-id="7907b-116">Set up the Adyen payment connector for Dynamics 365</span></span>](https://docs.adyen.com/plugins/microsoft-dynamics)
