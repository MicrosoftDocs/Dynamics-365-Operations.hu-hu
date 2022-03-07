---
title: Anyagjegyzék-verzió alábontása
description: Ez a cikk egy anyagjegyzék-verzió alábontásának alaptervezési forgatókönyvét ismerteti.
author: roxanadiaconu
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 617d9c3f05f2db30ec075a07b54c4827e668c20e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220848"
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

[Anyagjegyzék-verzió meghatározása](master-plan-bom-version-determined.md)

[Az alaptervezés és a többhelyes funkció áttekintése](master-plan-multisite-functionality.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]