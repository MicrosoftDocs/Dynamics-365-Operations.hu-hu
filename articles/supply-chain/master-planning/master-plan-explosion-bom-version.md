---
title: Anyagjegyzék-verzió alábontása
description: Ez a cikk egy anyagjegyzék-verzió alábontásának alaptervezési forgatókönyvét ismerteti.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ef8a04ce4ab2180f39a6d2bcdab976eb146d610
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741230"
---
# <a name="explosion-of-a-bom-version"></a>Anyagjegyzék-verzió alábontása

[!include [banner](../includes/banner.md)]

Ez a cikk egy anyagjegyzék-verzió alábontásának alaptervezési forgatókönyvét ismerteti.

Egy anyagjegyzék-verzió igényalábontása létrehoz egy igényt minden anyagjegyzéksor-cikkhez egy adott telephelyen, esetleg egy adott raktárban. Egy telephely-specifikus anyagjegyzékben egy adott raktár határozható meg minden anyagjegyzék-sorhoz. Továbbá minden anyagjegyzék-sorhoz a cikk dimenzióbeállításai meghatározzák, hogy a raktár szükséges-e. Az egyes anyagjegyzékcikk-sorokhoz megjelenő igény ezután a további igényalábontás kezdőpontja lesz. Ez az alaptervezési eset a következő feltételeket tartalmazza:

-   A telephely dimenzió kötelező, és meg kell adni az igénytranzakcióban.
-   A hely dimenzió konzisztens. Az alsóbb szintű igények telephelye megegyezik a kiinduló igénytranzakció telephelyével.

A következő ábra mutatja az alaptervezési igényalábontás folyamatát. ![Alábontás igénylése az anyagjegyzék-verzió használatával.](./media/multisitedemandexplosionscenariousingbomversion.gif)

## <a name="additional-resources"></a>További erőforrások

- [Anyagjegyzék-verzió meghatározása](master-plan-bom-version-determined.md)
- [Az alaptervezés és a több telephelyes funkció áttekintése](master-plan-multisite-functionality.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]