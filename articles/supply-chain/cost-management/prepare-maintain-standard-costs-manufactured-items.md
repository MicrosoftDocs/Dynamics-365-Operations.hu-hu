---
title: "Felkészülés a gyártott cikkek elszámolóárának karbantartására"
description: "Ez a téma leírja a gyártott cikkek költségeinek karbantartásának előkészítésére irányuló lépéseket."
author: AndersGirke
manager: AnnBe
ms.date: 01/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: c1942d1f2c8eeb05a6cbaddd2d7911a93b7e05a1
ms.contentlocale: hu-hu
ms.lasthandoff: 03/08/2018

---


# <a name="prepare-to-maintain-standard-costs-for-manufactured-items"></a>Felkészülés a gyártott cikkek elszámolóárának karbantartására

[!include[banner](../includes/banner.md)]

Ez a téma leírja a gyártott cikkek költségeinek karbantartásának előkészítésére irányuló lépéseket. A gyártott cikkek lépései kissé eltérnek a megvásárolt cikkek lépéseitől.

A termékekhez hozzárendelt szabályok kihatással lehetnek a költségszámításokra a szülő gyártott termékek felé. Felkészüléshez a gyártott cikkek költségeinek karbantartására kövesse e lépéseket.

1. Rendeljen a termékhez egy cikkmodellcsoportot. 

   A cikkmodellcsoport azonosítja a használandó önköltségi árakat.

2. Rendeljen a termékhez egy cikkcsoportot. 

   A cikkcsoportok tartalmazzák azokat a főkönyvi számlákat, amelyek a termékre érvényesek. Egy elszámolóáras készletmodellel rendelkező termék főkönyvi számlái számos gyártási eltérést, költségváltozási eltérést és készletköltség átértékelést foglalhatnak magukba.

3. Rendelje a cikkhez a készlet mértékegységét. 

   A cikk költségei mindig a cikk készletbeli mértékegységében vannak kifejezve.

4. Ne rendeljen költségcsoportot a gyártott termékhez, hacsak a cikk nem lesz alapanyagként (beszerzett termékként) kezelve.

5. Rendeljen a gyártott termékhez egy anyagjegyzék-számítási csoportot. 

   A cikk anyagjegyzék-számítási csoportja határozza meg a vonatkozó figyelmeztetési feltételeket. Így az anyagjegyzék-számítás végeztével figyelmeztető üzenetek hozhatók létre az esetleges számítási hibák eredetére vonatkozóan. Például egy figyelmeztető üzenet hívhatja fel a figyelmet arra, ha egy aktív anyagjegyzék vagy útvonal nem létezik. Az anyagjegyzék-számítási csoport tartalmaz egy alábontás-leállítási szabályt, amely jelzi, hogy mettől kell a cikket alapanyagként kezelni.

6. Ha a gyártott cikk költségei állandók, rendeljen a termékhez egy szokásos rendelési mennyiséget. 

   A szokásos rendelési mennyiség az állandó költségek amortizációjának könyvelési adagmérete. Példa állandó költségekre a beállítási idők az útvonalműveleteknél vagy egy állandó összetevőmennyiség egy anyagjegyzékben (AJ).

7. Határozza meg a termék anyagjegyzékét. 

   Egy termék számára több anyagjegyzéket is meg lehet adni. Ellenőrizze, hogy a kívánt verziók jóváhagyott és aktív jelet kaptak-e, és hogy a dátum érvényessége megfelelő-e. Az anyagjegyzékverzió vállalatszintű és hely specifikus lehet.

8. Határozza meg a termék útvonalát. 

   Egy termék számára több útvonalat is meg lehet adni. Ellenőrizze, hogy a kívánt verziók jóváhagyott és aktív jelet kaptak-e, és hogy a dátum érvényessége megfelelő-e. Az útvonalverzió vállalatszintű és hely specifikus lehet.

Ha útvonaladatokat kíván használni a költségképzési célokra, az további előkészületi lépéseket igényel. Például az útvonalműveletekhez rendelt költségkategóriáknak pontosaknak és hiánytalanoknak kell lenniük.

<a name="related-topics"></a>Kapcsolódó témakörök
--------

[A legyártott cikkek állandó költségeinek amortizálása](amortize-constant-costs-manufactured-item.md)

[Gyártható vagy beszerezhető termékek beállítása](manufactured-items-treated-as-purchased-items.md)


