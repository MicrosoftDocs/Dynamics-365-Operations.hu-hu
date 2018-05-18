---
title: "A legyártott cikkek állandó költségeinek amortizálása"
description: "A legyártott cikk állandó költségei a művelet beállítási idejét és az állandó mennyiséggel vagy állandó selejtmennyiséggel megadott összetevőket tükrözik."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcDialog, BOMCalcTable, BOMCalcTrans
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 274503
ms.assetid: 535ab25d-a031-4e8c-84ec-478f2987a1ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 75c0f5bcff0aae63aa8c7dae9b0767f8c7e6a81c
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="amortize-constant-costs-for-a-manufactured-item"></a>A legyártott cikkek állandó költségeinek amortizálása

[!include [banner](../includes/banner.md)]

A legyártott cikk állandó költségei a művelet beállítási idejét és az állandó mennyiséggel vagy állandó selejtmennyiséggel megadott összetevőket tükrözik. 

Ezeket az állandó költségeket a költségszámítási adagméret koncepciójának használatával kell amortizálni a legyártott cikk számított költségében. A koncepciónak több neve is van, ilyen például a könyvelési adagméret is. Az állandó költségek amortizálási koncepciójának is többféle neve van, egyik ilyen az arányos állandó költség.

Az anyagjegyzék-számítások a legyártott cikk költségszámítási adagméretét használják. A mennyiség attól függ, hogyan történik az anyagjegyzék-számítás indítása és végrehajtása, mint azt az alábbiak mutatják:

-   Alapértelmezett számítási mennyiség cikk anyagjegyzék-számításában – A cikk alapértelmezett rendelési mennyisége készletre a költségszámítási adag méretének alapértelmezéseként viselkedik, de az alapértelmezett érték lehet nagyobb mennyiség is, hogy a cikk rendelési mennyiségének többszörösét tükrözze. A cikk alapértelmezett rendelési mennyisége és többszöröse meghatározható az alapértelmezett rendelési beállításoknál vagy a helyspecifikus rendelési beállításokban is.
-   Cikk anyagjegyzék-számításában megadott számítási mennyiség – A megadott mennyiség a cikk költségszámítási adagméreteként viselkedik. A számítási mennyiség kezdetben a cikk alapértelmezett rendelési mennyiségét használja, de az alapértelmezett érték manuálisan felülbírálható. A megadott számítási mennyiség a költségszámítási adagméretet jelenti az adott cikkre vonatkozóan, illetve az anyagjegyzéksor típusú gyártású gyártott összetevőkre vonatkozóan. Ennek oka az a feltételezés, hogy az összetevő előállítása a pontos mennyiségben történik. A költségszámítási adagméret az egyéb legyártott összetevőkre vonatkozóan anyagjegyzéksor típus esetén az alapértelmezett rendelési mennyiségnek felel meg.
-   Adott rendelésre gyártási mennyiség cikk anyagjegyzék-számításában – a megadott számítási mennyiség viselkedik költségszámítási adagméretként a cikk és gyártott összetevői szempontjából, amikor az anyagjegyzék-számítások rendelésre gyártási alábontási módot alkalmaznak. A feltételezés az, hogy az összetevők előállítása ugyanúgy a pontos mennyiségben történik, mint a termelési típusú anyagjegyzéksorok esetében.
-   Megadott számítási mennyiség rendelésspecifikus anyagjegyzék-számításban – rendelésspecifikus anyagjegyzék-számítást beszerzési rendelés, értékesítési ajánlat vagy szervizrendelés sorára vonatkozóan lehet végezni. A megadott számítási mennyiség a kiindulási sor mennyiségét veszi fel, de az alapértelmezett mennyiség felülbírálható. Be lehet állítani, hogy a rendelésspecifikus anyagjegyzék-számítás rendelésre készítési vagy többszintű alábontási módot használjon.

A legyártott cikk amortizált állandó költségeinek számított mennyiségét nevezik költségnek.






