---
title: "Robbanás egy Anyagjegyzék-verzió"
description: "Ez a cikk ismerteti az Alaptervezés forgatókönyv, amely magában foglalja az anyagjegyzék-verzió anyagjegyzék alábontása."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 6461a07f8c8f02f584e5ef70b21ebaf04f29b57b
ms.lasthandoff: 03/31/2017


---

# <a name="explosion-of-a-bom-version"></a>Robbanás egy Anyagjegyzék-verzió

Ez a cikk ismerteti az Alaptervezés forgatókönyv, amely magában foglalja az anyagjegyzék-verzió anyagjegyzék alábontása.

Egy anyagjegyzék-verzió igényalábontása létrehoz egy igényt minden anyagjegyzéksor-cikkhez egy adott telephelyen, esetleg egy adott raktárban. Egy telephely-specifikus anyagjegyzékben egy adott raktár határozható meg minden anyagjegyzék-sorhoz. Továbbá minden anyagjegyzék-sorhoz a cikk dimenzióbeállításai meghatározzák, hogy a raktár szükséges-e. Az egyes anyagjegyzékcikk-sorokhoz megjelenő igény ezután a további igényalábontás kezdőpontja lesz. Ez az alaptervezési eset a következő feltételeket tartalmazza:

-   A telephely dimenzió kötelező, és meg kell adni az igénytranzakcióban.
-   A hely dimenzió konzisztens. Az alsóbb szintű igények telephelye megegyezik a kiinduló igénytranzakció telephelyével.

A következő ábra mutatja az alaptervezési igényalábontás folyamatát. ![Alábontás igénylése az anyagjegyzék-verzió használatával](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="see-also"></a>Lásd még
--------

[Alaptervezés - hogyan határozza meg az AJ-verzió](master-plan-bom-version-determined.md)

[Master planning and multisite functionality](master-plan-multisite-functionality.md)


