---
title: "Az értékcsökkenési számítások kerekítési összegei."
description: "Ez a cikk az Értékcsökkenés kerekítése mezőt taglalja, amely a Könyv beállítása lapon található meg."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0ad57b076542c38d3c29dba4caacf830de6f7200
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="round-off-amount-for-depreciation-calculations"></a>Az értékcsökkenési számítások kerekítési összegei.

[!include [banner](../includes/banner.md)]

Ez a cikk az Értékcsökkenés kerekítése mezőt taglalja, amely a Könyv beállítása lapon található meg.

Az értékcsökkenések kerekítési összegei minden egyes könyvhöz beállíthatók. Az értékcsökkenés-kerekítési összegek a tárgyi eszközök értékcsökkenési profiljában használhatóak, amely megmutatja a tárgyi eszköz értékének jövőbeni értékcsökkenését és az értékcsökkenési javaslatot. Adja meg a könyvben engedélyezett értékcsökkenés legalacsonyabb összegét. 

A beállított kerekítéstől függetlenül az utolsó értékcsökkenési időszak értékcsökkenési összege nem kerül kerekítésre. Az utolsó értékcsökkenési időszak végén a tárgyi eszköz értékének nulla kell legyen, vagy a selejtérték összege, ha használ selejtértéket.

### <a name="example"></a>Példa

A kerekítés nélkül számított értékcsökkenés 2444,44 egység. Ahogy azt az alábbi tábla is mutatja, a javasolt összegek között különbség lehet, attól függően, milyen kerekítés van beállítva.

| Kerekítési mód | Értékcsökkenés összege |
|-----------------|---------------------|
| Kerekítés: 0,1    | 2444,40            |
| Kerekítés: 1,00   | 2,444.00            |
| Kerekítés: 10,00  | 2,440.00            |
| Kerekítés: 100,00 | 2,400.00            |






