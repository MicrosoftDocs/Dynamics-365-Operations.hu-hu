---
title: "A helyesbített előrejelzéseket engedélyezése"
description: "Nem szükséges minden előrejelzési adatot azonnal engedélyezni. Ez a cikk ismerteti, hogyan határozza meg azt a periódust, amelyre az előrejelzés engedélyezett. Továbbá azt is megmutatja, hogyan engedélyezheti az előrejelzést adott vállalatokra vagy előrejelzési modellekre vonatkozóan."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: f151f4b4290df0b2bf1b5d1159654bd248a439b1
ms.lasthandoff: 03/31/2017


---

# <a name="authorize-an-adjusted-forecast"></a>A helyesbített előrejelzéseket engedélyezése

Nem szükséges minden előrejelzési adatot azonnal engedélyezni. Ez a cikk ismerteti, hogyan határozza meg azt a periódust, amelyre az előrejelzés engedélyezett. Továbbá azt is megmutatja, hogyan engedélyezheti az előrejelzést adott vállalatokra vagy előrejelzési modellekre vonatkozóan.

Nem szükséges minden előrejelzési adatot azonnal engedélyezni. Meghatározhatja annak a periódusnak a kezdő és a záró dátumait amelyre az előrejelzés engedélyezett. Ennek a funkciónak a segítségével meghatározott időszakokat rögzíthet. 

A megadott kezdő és záró dátumát meg kell felelnie a kezdő és záró dátumát, a gyűjtő az előrejelzés készült. A rendszer ezt a korlátozást kényszerít, és automatikusan állítja be, ha szükséges korrekciós. 

Az **Engedélyezés** oldal **Részletek** lapján megtekintheti a legutóbb létrehozott előrejelzés részleteit. 

Kiválaszthatja a vállalatokat és az előrejelzési modelleket, hogy engedélyezze az előrejelzés használatát. Alapértelmezett állapotban a rács tartalmazza az összes olyan vállalatot, melynek számára előrejelzési igény lett kreálva. Az alaptervezésben felállított jelenlegi előrejelzési tervek (melyek megfelelnek az előrejelzési modellnek), minden vállalat esetében előre ki vannak töltve. Ettől függetlenül, ezt az előrejelzési modellt megváltoztathatja bármelyik másik, ahhoz a vállalathoz tartozó előrejelzési modellre. Amennyiben egy kiválasztott vállalat számára nincs adat az előrejelzési igényről, az importáláskor hibaüzenet jelzi a hiányt. 

Rendkívül fontos, hogy megértse hogyan működik a **Manuális beállítások mentése és az alapvető igény-előrejelzés beállítások felülírása** jelölőnégyzet. Végzett kiigazításokat a statisztikai eredeti előrejelzés, ha a módosított értékeket is felhasználásra engedélyezett, még akkor is, ha ez a jelölőnégyzet nincs bejelölve. A módosítások az engedélyezés után törlődnek. Így amikor következő alkalommal előrejelzést hoz létre, az előrejelzés csak statisztikai lesz és nem lesznek benne manuális felülírások akkor sem, ha a **Manuális kiigazítások átvitele az igény-előrejelzésbe** jelölőnégyzet be van jelölve. Megfontolandó tehát a **Manuális beállítások mentése és az alapvető igény-előrejelzés beállítások felülírása** jelölőnégyzet használata, mivel az megengedi, hogy megtartsa vagy elvesse az összes manuális változtatást.

<a name="see-also"></a>Lásd még
--------

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)

[Monitoring forecast accuracy](monitor-forecast-accuracy.md)


