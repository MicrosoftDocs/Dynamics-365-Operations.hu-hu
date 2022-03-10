---
title: Visszárurendelés visszatérítése elutasítva
description: Ez a témakör hibaelhárítási útmutatást tartalmaz arra vonatkozóan, hogy segítséget nyújtson akkor, amikor a visszárurendelés visszatérítését elutasítják, mivel a számlázáshoz használt hitelkártya különbözik az eredeti fizetés engedélyezésekor használt kártyától.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: 8880d72d702758d611755bce48a331e3f2e28ca1b7abf485e8b4f7301317c875
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738624"
---
# <a name="refund-on-a-return-order-is-declined"></a>Visszárurendelés visszatérítése elutasítva

[!include [banner](../../includes/banner.md)]

Ez a témakör hibaelhárítási útmutatást tartalmaz arra vonatkozóan, hogy segítséget nyújtson akkor, amikor a visszárurendelés visszatérítését elutasítják, mivel a számlázáshoz használt hitelkártya különbözik az eredeti fizetés engedélyezésekor használt kártyától.

## <a name="description"></a>Leírás

A visszatérítés nem alkalmazható, ha a visszárurendelés számlázására használt hitelkártya eltér az eredeti fizetés engedélyezésekor használt kártyától. A következő hibaüzenet jelenik meg: „Egyes kifizetések feladási állapota nem megfelelő. Számlázás előtt ellenőrizze újra az összes kifizetés állapotát.”

A fizetésengedélyezési részletek a következő hibaüzenetet tartalmazzák: „Az Adyen gateway SendRequest() sikertelen volt "InternalServerError".22144; Adyen üres választ adott vissza. (22001);”

![Visszárurendelés visszatérítését elutasították.](media/refund-order-decline.jpg)

## <a name="resolution"></a>Megoldás

### <a name="enable-blind-returns-in-adyen"></a>Nyugta nélküli visszatérítések engedélyezése az Adyenben

A nyugta nélküli visszatérítések engedélyezéséhez kövesse a [Hibaelhárítás a Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](adyen-support.md) rész lépéseit az Adyen támogatási csapattal történő kapcsolatfelvételhez és annak kérvényezéséhez, hogy engedélyezzék Adyen kereskedői számláján a nyugta nélküli visszatérítéseket.

## <a name="additional-resources"></a>További erőforrások

[Dynamics 365 fizetési összekötő az Adyen szolgáltatáshoz](../dev-itpro/adyen-connector.md)

[Adyen fizetési összekötő a Dynamics 365 szolgáltatáshoz](https://docs.adyen.com/plugins/microsoft-dynamics)
