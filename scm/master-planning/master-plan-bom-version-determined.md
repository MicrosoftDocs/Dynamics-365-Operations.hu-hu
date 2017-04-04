---
title: "Határozza meg az AJ-verzió"
description: "Során igény szerint a robbanás Ha egy cikk alapértelmezett rendelési típus a termelés, a tervezési motor keresi meg a webhelyen alapuló érvényes Anyagjegyzék-verzió."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMConsistOf, BOMDesigner, BOMTable, InventItemOrderSetup
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 4e4f5f02dfa986669decbc8854148b5eff928c2a
ms.lasthandoff: 03/31/2017


---

# <a name="determine-the-bom-version"></a>Határozza meg az AJ-verzió

Során igény szerint a robbanás Ha egy cikk alapértelmezett rendelési típus a termelés, a tervezési motor keresi meg a webhelyen alapuló érvényes Anyagjegyzék-verzió. 

A helydimenzió mindig ismert és megjelenik az igénytranzakcióban. A következő folyamat használható, hogy meghatározza a használandó anyagjegyzék-verziót:

-   Ha van anyagjegyzék-verzió meghatározva a cikkhez az igény telephelyén, akkor a telephelyfüggő anyagjegyzék verzió kerül használatra.
-   Ha nincs telephelyfüggő anyagjegyzék-verzió meghatározva egy cikkhez az igény telephelyén akkor az általános anyagjegyzék-verzió kerül használatra. Az általános anyagjegyzék nem határozza meg a telephelyet, és több telephelyre is érvényes. Ha van általános anyagjegyzék, akkor használatra kerül.
-   Ha nincs használható általános anyagjegyzék, akkor az igény alábontása ezen a ponton leáll.

Minden érvényes anyagjegyzék-verziónak, legyen az telephelyre jellemző vagy általános verzió, teljesítenie kell a dátumra és a mennyiségre vonatkozó kötelező feltételeket.




