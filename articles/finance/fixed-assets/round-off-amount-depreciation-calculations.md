---
title: Az értékcsökkenési számítások kerekítési összegei
description: Ez a témakör az Értékcsökkenés kerekítése mezőt taglalja, amely a Könyv beállítása lapon található meg.
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
ms.openlocfilehash: 98d6a21bea4688d6f258a98eab174485ceee2cfc
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726725"
---
# <a name="round-off-amount-for-depreciation-calculations"></a>Az értékcsökkenési számítások kerekítési összegei

[!include [banner](../includes/banner.md)]

Ez a témakör az **Értékcsökkenés kerekítése** mezőt taglalja, amely a **Könyv beállítása** lapon található meg.

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
