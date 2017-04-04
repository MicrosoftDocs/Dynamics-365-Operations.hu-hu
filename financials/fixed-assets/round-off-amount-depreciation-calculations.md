---
title: "Az értékcsökkenési számítások kerekítési összegei."
description: "Ez a cikk az Értékcsökkenés kerekítése mezőt taglalja, amely a Könyv beállítása lapon található meg."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 8e89a57dda8f2d392483ed13c686ea97b74926b0
ms.openlocfilehash: 0cb514dfb8c37b8c027ab895cb970af1b0135bf0
ms.lasthandoff: 03/31/2017


---

# <a name="round-off-amount-for-depreciation-calculations"></a>Az értékcsökkenési számítások kerekítési összegei.

Ez a cikk az Értékcsökkenés kerekítése mezőt taglalja, amely a Könyv beállítása lapon található meg.

Értékcsökkenés kerekítése összegek beállított minden egyes könyv. Értékcsökkenés kerekítése összegek a befektetett eszköz értékcsökkenési profilt, amely tartalmazza a jövőbeli értékcsökkenést és a tárgyi eszköz értéke, valamint értékcsökkenési javaslatot használják. Adja meg a könyvben engedélyezett értékcsökkenés legalacsonyabb összegét. 

A beállított kerekítéstől függetlenül az utolsó értékcsökkenési időszak értékcsökkenési összege nem kerül kerekítésre. Az utolsó értékcsökkenési időszak végén a tárgyi eszköz értékének nulla kell legyen, vagy a selejtérték összege, ha használ selejtértéket.

### <a name="example"></a>Példa

A kerekítés nélkül számított értékcsökkenés 2444,44 egység. Ahogy azt az alábbi tábla is mutatja, a javasolt összegek között különbség lehet, attól függően, milyen kerekítés van beállítva.

| Kerekítési mód | Értékcsökkenés összege |
|-----------------|---------------------|
| Kerekítés: 0,1    | 2444,40            |
| Kerekítés: 1,00   | 2444,00            |
| Kerekítés: 10,00  | 2440,00            |
| Kerekítés: 100,00 | 2400,00            |




