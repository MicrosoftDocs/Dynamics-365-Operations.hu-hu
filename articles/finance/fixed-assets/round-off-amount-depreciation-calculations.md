---
title: Az értékcsökkenési számítások kerekítési összegei.
description: Ez a cikk az Értékcsökkenés kerekítése mezőt taglalja, amely a Könyv beállítása lapon található meg.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: kfend
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a93842f7cca483df89188695c945edf77e118cef
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870104"
---
# <a name="round-off-amount-for-depreciation-calculations"></a>Az értékcsökkenési számítások kerekítési összegei.

[!include [banner](../includes/banner.md)]

Ez a cikk a **Könyv** **beállítási lapjain található Kerekítési értékcsökkenés mezőt tárgyalja**.

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







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
