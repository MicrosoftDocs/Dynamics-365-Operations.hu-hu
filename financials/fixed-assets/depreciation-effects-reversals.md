---
title: "A sztornírozások értékcsökkenésre gyakorolt hatására"
description: "Ez a cikk egy tárgyieszköz-tranzakció sztornírozásának lehetséges következményeit tárgyalja."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTrans
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2961
ms.assetid: 63a3ac92-c321-4379-a86a-b1b14915f340
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: d061ad8df477943259bff853d032c3df620e0b27
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="depreciation-effects-with-reversals"></a>A sztornírozások értékcsökkenésre gyakorolt hatására

[!include[banner](../includes/banner.md)]


Ez a cikk egy tárgyieszköz-tranzakció sztornírozásának lehetséges következményeit tárgyalja. 

Sztornírozhatja a tárgyieszköz-tranzakciókat és a azokat a tranzakciókat, amelyek egy tárgyi eszközhöz vannak társítva. Továbbá visszavonhatja a sztornírozott tranzakciót. 

Sztornírozhat vagy visszavonhat egy tranzakciót, amely nem a legutóbbi feladott tranzakció a könyvben az eszközhöz. Előbb érdemes megállapítania, hogy lett-e értékcsökkenési tranzakció feladva az után a tranzakció után, amelyet sztorníroz. Ennek oka az, hogy az értékcsökkenés nem kerül kiszámításra amikor sztorníroz egy tranzakciót. Ezért értékcsökkenés gyakran túl nagy vagy túl alacsony, a sztornírozás után, ahogy azt a példák mutatják. 

Hogy megbizonyosodjon, hogy az értékcsökkenés helyes, amikor sztorníroz egy tranzakciót ne folytassa a sztornírozást, ha egy olyan üzenetet kap, amelyben az áll, hogy a sztornírozás nem lesz újraszámolva. Ehelyett előbb sztornírozza az értékcsökkenési tranzakciót, amit az után a tranzakció után adtak föl, amit épp sztornírozni próbált, majd folytassa a sztornírozást. Nem lesz figyelmeztetve az értékcsökkenés újraszámításáról és folytathatja a sztornírozást. 

A következő példák bemutatják a számításokat, amelyek akkor történnek, ha folytatja a sztornírozást az üzenet után mielőtt sztornírozta volna a korábbi értékcsökkenési tranzakciókat.

## <a name="example-1-depreciation-is-overstated"></a> 1. példa: túl nagy értékcsökkenés
Az eszköznek 5 év hasznos élettartam és lineáris értékcsökkenés (60 értékcsökkenési időszak) van beállítva. Ebben a példában túl nagy az értékcsökkenés.
#### <a name="asset-transaction-history"></a>Tárgyieszköz-tranzakciók előzményei

| Dátum       | Tranzakció típusa                                                          | Összeg                                    |
|------------|---------------------------------------------------------------------------|-------------------------------------------|
| Január 1.  | Beszerzés                                                               | 59 000,00                                 |
| Január 1.  | Beszerzés helyesbítése                                                    | 1000,00                                  |
| Január 31. | Értékcsökkenés (az értékcsökkenés egy időszakának javaslatával létrehozva) | 1 000,00 Számítás: Könyv szerinti érték (59 000 + 1 000) / Hátra lévő értékcsökkenési időszakok száma (60) |

#### <a name="reversal-action"></a>Sztornírozási művelet

| Dátum      | Tranzakció típusa                | Összeg    |
|-----------|---------------------------------|-----------|
| Január 1. | Beszerzés-helyesbítési sztornírozás | –1000,00 |

#### <a name="depreciation-effect"></a>Az értékcsökkenés hatása

| Dátum        | Tranzakció típusa        | Összeg                                                                                |
|-------------|-------------------------|---------------------------------------------------------------------------------------|
| Február 28. | Értékcsökkenés (javaslat) | 983,05 Számítás: Könyv szerinti érték (59 000 - 1 000 értékcsökkenés) / Hátralévő értékcsökkenési időszakok száma (59) |

Az értékcsökkenés túl nagy, mértéke 16,95 (1000 - 983,05).

## <a name="example-2-depreciation-is-understated"></a> 2. példa: túl alacsony értékcsökkenés
Az eszköznek 5 év hasznos élettartam és lineáris értékcsökkenés (60 értékcsökkenési időszak) van beállítva. Ebben a példában túl alacsony az értékcsökkenés.
#### <a name="asset-transaction-history"></a>Tárgyieszköz-tranzakciók előzményei

| Dátum       | Tranzakció típusa                                                          | Összeg                                      |
|------------|---------------------------------------------------------------------------|---------------------------------------------|
| Január 1.  | Beszerzés                                                               | 59 000,00                                   |
| Január 1.  | Leértékelési helyesbítés                                                     | 1000,00                                    |
| Január 31. | Értékcsökkenés (az értékcsökkenés egy időszakának javaslatával létrehozva) | 966,67 Számítás: könyv szerinti érték (59 000 - 1 000) / Hátralévő értékcsökkenési időszakok száma (60) |

#### <a name="reversal-action"></a>Sztornírozási művelet

| Dátum      | Tranzakció típusa               | Összeg    |
|-----------|--------------------------------|-----------|
| Január 1. | Leértékelési helyesbítés sztornírozás | –1000,00 |

#### <a name="depreciation-effect"></a>Az értékcsökkenés hatása

| Dátum        | Tranzakció típusa        | Összeg                                                                                       |
|-------------|-------------------------|----------------------------------------------------------------------------------------------|
| Február 28. | Értékcsökkenés (javaslat) | 983,62 Számítás: könyv szerinti érték (59 000 - 966,67 értékcsökkenés) / Hátralévő értékcsökkenési időszakok száma (59) |

Az értékcsökkenés túl alacsony, mértéke 16,95 (983,62 - 966,67).



<a name="see-also"></a>Lásd még
--------

[Tárgyi eszközök értékcsökkenése](fixed-asset-depreciation.md)




