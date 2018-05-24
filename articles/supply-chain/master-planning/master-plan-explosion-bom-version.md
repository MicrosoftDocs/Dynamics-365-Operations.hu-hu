---
title: "Anyagjegyzék-verzió alábontása"
description: "Ez a cikk egy anyagjegyzék-verzió alábontásának alaptervezési forgatókönyvét ismerteti."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 80c9fa6ec98bd2cdc3edd5329e2a619ef9cc8cb2
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="explosion-of-a-bom-version"></a>Anyagjegyzék-verzió alábontása

[!include [banner](../includes/banner.md)]

Ez a cikk egy anyagjegyzék-verzió alábontásának alaptervezési forgatókönyvét ismerteti.

Egy anyagjegyzék-verzió igényalábontása létrehoz egy igényt minden anyagjegyzéksor-cikkhez egy adott telephelyen, esetleg egy adott raktárban. Egy telephely-specifikus anyagjegyzékben egy adott raktár határozható meg minden anyagjegyzék-sorhoz. Továbbá minden anyagjegyzék-sorhoz a cikk dimenzióbeállításai meghatározzák, hogy a raktár szükséges-e. Az egyes anyagjegyzékcikk-sorokhoz megjelenő igény ezután a további igényalábontás kezdőpontja lesz. Ez az alaptervezési eset a következő feltételeket tartalmazza:

-   A telephely dimenzió kötelező, és meg kell adni az igénytranzakcióban.
-   A hely dimenzió konzisztens. Az alsóbb szintű igények telephelye megegyezik a kiinduló igénytranzakció telephelyével.

A következő ábra mutatja az alaptervezési igényalábontás folyamatát. ![Alábontás igénylése az anyagjegyzék-verzió használatával](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="additional-resources"></a>További erőforrások
--------

[Alaptervezés - anyagjegyzék verzió meghatározása](master-plan-bom-version-determined.md)

[Az alaptervezés és a többhelyes funkció](master-plan-multisite-functionality.md)




