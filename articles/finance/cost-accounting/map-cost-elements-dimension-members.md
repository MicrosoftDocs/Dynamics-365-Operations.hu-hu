---
title: Költségösszetevő-dimenziótagok hozzárendelése a dimenziótagok általános készletéhez
description: Azzal, hogy a különböző költségösszetevő-dimenziótagokat hozzárendeli a költségösszetevő-dimenziótagok egy közös csoportjához, az adatokat egy közös formátumnak megfelelően egyesíti elemzési célokra.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimension, CAMDimensionMember, CAMDimensionMapping
audience: Application User
ms.reviewer: roschlom
ms.custom: 223234
ms.assetid: 4c66a231-aed2-48b5-9727-b3eb4fe6e6aa
ms.search.region: global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b9ac59f305afd55edfcfb3b47bf38ddd44d92a706904f55a069a6a9fc9050825
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728031"
---
# <a name="map-cost-element-dimension-members-to-a-common-set-of-dimension-members"></a>Költségösszetevő-dimenziótagok hozzárendelése a dimenziótagok általános készletéhez

[!include [banner](../includes/banner.md)]

Azzal, hogy a különböző költségösszetevő-dimenziótagokat hozzárendeli a költségösszetevő-dimenziótagok egy közös csoportjához, az adatokat egy közös formátumnak megfelelően egyesíti elemzési célokra.

Ha Ön vállalata egy globális vállalat, és teljesíti a kötelezően előírt számviteli követelményeket, akkor több számlatükröt is használhat. Amikor költségösszetevő-dimenziótagokat importál különböző számlatükrökből, előfordulhat, hogy a végén különböző számlái lesznek. Ezek a számlák azonban lehet, hogy azonos jellegűek, és érdemes a hozzájuk tartozó költségeket közös formátumban elemezni és felosztani.

## <a name="map-cost-element-dimension-members-to-a-common-format"></a>Költségösszetevő-dimenziótagok hozzárendelése egy közös formátumhoz
A következő példa azt mutatja meg, hogy Ön költségellenőrként létrehozhat egy olyan új költségösszetevő-dimenziótagot a költségkönyvelésben, amely az egyesült államokbeli számlatükör-struktúrából és a francia számlatükör-struktúrából származó költségösszetevő-dimenziótagokat hozzárendeli a költségösszetevő-dimenziótagok egy közös csoportjához. A költségösszetevő-dimenziótagok közös csoportjának segítségével elemezheti a két jogi entitás költségkönyvelési főkönyvéből származó költségadatokat.

| Forrás: egyesült államokbeli számlatükrök                                          | Forrás: francia számlatükrök                                          | A költségösszetevő-dimenziótagok új, közös csoportja                        |
|-----------------------------------------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------------------|
| Egyesült államokbeli számlatükrökből importált költségösszetevő-dimenziótagok | Francia számlatükrökből importált költségösszetevő-dimenziótagok | Egyesült államokbeli és francia költségösszetevő-dimenziótagok hozzárendelése egy közös csoporthoz |
| 5001: Értékesítés                                                           | 5001: Értékesítés és reklám                                               | 5000: Értékesítés és reklám                                             |
| 5030: Hirdetés                                                     | 6390: Készlet beszerzése\*                                                    | 7000: Takarítási költségek                                                 |
| 7001: Takarítási költségek                                               | 7001: Utazási költségek                                                      | 7001: Utazási költségek                                                   |

\*A készletbeszerzési francia költségösszetevő-dimenziótag nincs megfeleltetve.

## <a name="currency-conversion"></a>Pénznemátváltás
Az Ön által használt különböző számlatükröket be lehet állítani eltérő pénznemek használatához. Ebben az esetben mindenképpen adja meg a pénznemátváltást úgy, hogy költségadatok feldolgozása a megfelelő pénznem használatával történjen, a költségkönyvelés főkönyvvében meghatározott módon, ahol a költségösszetevő-dimenziótagokat használják. Az előző példában, ha amerikai dollárt (USD) használnak a költségkönyvelés főkönyvében, létre kell hoznia egy pénznemátváltást USD-ről euróra (EUR) a hozzárendelt költségösszetevő-dimenziótagra vonatkozó tranzakciók feldolgozásához.

## <a name="update-mappings-at-any-time"></a>A hozzárendelések bármikor frissíthetők
Bármikor frissítheti a költségösszetevő-dimenziókhoz tartozó hozzárendelési definíciókat. Mivel a hozzárendelések érvényessége nem kötődik dátumhoz, a változások akkor lépnek érvénybe, amikor legközelebb dolgoznak fel költségtranzakciókat vagy futtatnak költségszámításokat.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]