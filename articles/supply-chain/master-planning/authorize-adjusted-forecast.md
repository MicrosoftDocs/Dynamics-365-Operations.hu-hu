---
title: "Módosított előrejelzés engedélyezése"
description: "Nem szükséges minden előrejelzési adatot azonnal engedélyezni. Ez a cikk ismerteti, hogyan határozza meg azt a periódust, amelyre az előrejelzés engedélyezett. Továbbá azt is megmutatja, hogyan engedélyezheti az előrejelzést adott vállalatokra vagy előrejelzési modellekre vonatkozóan."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanImportForecastDialog
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 72734
ms.assetid: cb8fd809-605a-4a8b-a390-636edfec21f9
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 399a7a21ec71fe50e280ccb24699cda76d571990
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="authorize-an-adjusted-forecast"></a>Módosított előrejelzés engedélyezése

[!include[banner](../includes/banner.md)]


Nem szükséges minden előrejelzési adatot azonnal engedélyezni. Ez a cikk ismerteti, hogyan határozza meg azt a periódust, amelyre az előrejelzés engedélyezett. Továbbá azt is megmutatja, hogyan engedélyezheti az előrejelzést adott vállalatokra vagy előrejelzési modellekre vonatkozóan.

Nem szükséges minden előrejelzési adatot azonnal engedélyezni. Meghatározhatja annak a periódusnak a kezdő és a záró dátumait amelyre az előrejelzés engedélyezett. Ennek a funkciónak a segítségével meghatározott időszakokat rögzíthet. 

A megadott kezdő és záró dátumoknak meg kell egyezniük annak az időszaknak a kezdő és záró dátumaival, amelyben az előrejelzés létrejön. A rendszer ezt a korlátozást kikényszeríti, és automatikusan kiigazítja a dátumokat, amennyiben ez szükséges. 

Az **Engedélyezés** oldal **Részletek** lapján megtekintheti a legutóbb létrehozott előrejelzés részleteit. 

Kiválaszthatja a vállalatokat és az előrejelzési modelleket, hogy engedélyezze az előrejelzés használatát. Alapértelmezett állapotban a rács tartalmazza az összes olyan vállalatot, melynek számára előrejelzési igény lett kreálva. Az alaptervezésben felállított jelenlegi előrejelzési tervek (melyek megfelelnek az előrejelzési modellnek), minden vállalat esetében előre ki vannak töltve. Ettől függetlenül, ezt az előrejelzési modellt megváltoztathatja bármelyik másik, ahhoz a vállalathoz tartozó előrejelzési modellre. Amennyiben egy kiválasztott vállalat számára nincs adat az előrejelzési igényről, az importáláskor hibaüzenet jelzi a hiányt. 

Rendkívül fontos, hogy megértse hogyan működik a **Manuális beállítások mentése és az alapvető igény-előrejelzés beállítások felülírása** jelölőnégyzet. Amennyiben hajtott végre manuális beállításokat a statisztikai kiinduló előrejelzésen, a kiigazított értékek akkor is engedélyezve vannak használatra, ha ez a jelölőnégyzet nincs bejelölve. A módosítások az engedélyezés után törlődnek. Így amikor következő alkalommal előrejelzést hoz létre, az előrejelzés csak statisztikai lesz és nem lesznek benne manuális felülírások akkor sem, ha a **Manuális kiigazítások átvitele az igény-előrejelzésbe** jelölőnégyzet be van jelölve. Megfontolandó tehát a **Manuális beállítások mentése és az alapvető igény-előrejelzés beállítások felülírása** jelölőnégyzet használata, mivel az megengedi, hogy megtartsa vagy elvesse az összes manuális változtatást.

<a name="see-also"></a>Lásd még
--------

[A kiinduló előrejelzés manuális kiigazítása](manual-adjustments-baseline-forecast.md)

[Az előrejelzési pontosság megfigyelése](monitor-forecast-accuracy.md)




