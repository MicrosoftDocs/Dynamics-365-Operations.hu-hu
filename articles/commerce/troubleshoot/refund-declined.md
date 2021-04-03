---
title: Visszárurendelés visszatérítése elutasítva
description: Ez a témakör hibaelhárítási útmutatást tartalmaz arra vonatkozóan, hogy segítséget nyújtson akkor, amikor a visszárurendelés visszatérítését elutasítják, mivel a számlázáshoz használt hitelkártya különbözik az eredeti fizetés engedélyezésekor használt kártyától.
author: Reza-Assadi
manager: AnnBe
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
ms.openlocfilehash: e202c6b4b9e025d5af1cd5eb6235884aab6444e6
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585363"
---
# <a name="refund-on-a-return-order-is-declined"></a>Visszárurendelés visszatérítése elutasítva

[!include [banner](../../includes/banner.md)]

Ez a témakör hibaelhárítási útmutatást tartalmaz arra vonatkozóan, hogy segítséget nyújtson akkor, amikor a visszárurendelés visszatérítését elutasítják, mivel a számlázáshoz használt hitelkártya különbözik az eredeti fizetés engedélyezésekor használt kártyától.

## <a name="description"></a>Leírás

A visszatérítés nem alkalmazható, ha a visszárurendelés számlázására használt hitelkártya eltér az eredeti fizetés engedélyezésekor használt kártyától. A következő hibaüzenet jelenik meg: „Egyes kifizetések feladási állapota nem megfelelő. Számlázás előtt ellenőrizze újra az összes kifizetés állapotát.”

A fizetésengedélyezési részletek a következő hibaüzenetet tartalmazzák: „Az Adyen gateway SendRequest() sikertelen volt "InternalServerError".22144; Adyen üres választ adott vissza. (22001);”

![Visszárurendelés visszatérítését elutasították](media/refund-order-decline.jpg)

## <a name="resolution"></a>Felbontás

### <a name="enable-blind-returns-in-adyen"></a>Nyugta nélküli visszatérítések engedélyezése az Adyenben

A nyugta nélküli visszatérítések engedélyezéséhez kövesse a [Hibaelhárítás a Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](adyen-support.md) rész lépéseit az Adyen támogatási csapattal történő kapcsolatfelvételhez és annak kérvényezéséhez, hogy engedélyezzék Adyen kereskedői számláján a nyugta nélküli visszatérítéseket.

## <a name="additional-resources"></a>További erőforrások

[Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](../dev-itpro/adyen-connector.md)

[Adyen fizetési összekötő a Dynamics 365 szolgáltatáshoz](https://docs.adyen.com/plugins/microsoft-dynamics)
