---
title: "Az AJ verziójának meghatározása"
description: "Igény alábontása során, ha egy cikk az alapértelmezett Termelés rendeléstípushoz tartozik, a tervezési motor megkeresi az érvényes anyagjegyzék-verziót a telephely alapján."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConsistOf, BOMDesigner, BOMTable, InventItemOrderSetup
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ee265d0ab7807cd92c70096111ffb3dbec11ad62
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="determine-the-bom-version"></a>Az AJ verziójának meghatározása

[!include[banner](../includes/banner.md)]


Igény alábontása során, ha egy cikk az alapértelmezett Termelés rendeléstípushoz tartozik, a tervezési motor megkeresi az érvényes anyagjegyzék-verziót a telephely alapján. 

A helydimenzió mindig ismert és megjelenik az igénytranzakcióban. A következő folyamat használható, hogy meghatározza a használandó anyagjegyzék-verziót:

-   Ha van anyagjegyzék-verzió meghatározva a cikkhez az igény telephelyén, akkor a telephelyfüggő anyagjegyzék verzió kerül használatra.
-   Ha nincs telephelyfüggő anyagjegyzék-verzió meghatározva egy cikkhez az igény telephelyén akkor az általános anyagjegyzék-verzió kerül használatra. Az általános anyagjegyzék nem határozza meg a telephelyet, és több telephelyre is érvényes. Ha van általános anyagjegyzék, akkor használatra kerül.
-   Ha nincs használható általános anyagjegyzék, akkor az igény alábontása ezen a ponton leáll.

Minden érvényes anyagjegyzék-verziónak, legyen az telephelyre jellemző vagy általános verzió, teljesítenie kell a dátumra és a mennyiségre vonatkozó kötelező feltételeket.






