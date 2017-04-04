---
title: "Előrejelzés statisztikai alapterv készítése"
description: "Ez a cikk az igény-előrejelzés számítása során használt paraméterekről és szűrőkről nyújt tájékoztatást."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72683
ms.assetid: 42190463-2a64-4f63-b653-10cac3df0692
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c0c918b94fe96d123bb6c25c42fe168a026cd8a9
ms.lasthandoff: 03/31/2017


---

# <a name="generate-a-statistical-baseline-forecast"></a>Előrejelzés statisztikai alapterv készítése

Ez a cikk az igény-előrejelzés számítása során használt paraméterekről és szűrőkről nyújt tájékoztatást. 

A kiinduló előrejelzés létrehozásakor először meg kell adni számításhoz használt paramétereket és szűrőket. Például létrehozhat olyan kiinduló előrejelzést, ami egy adott vállalat elmúlt évi tranzakcióadatai alapján hoz létre becslést a jövő hónapra, cikkek egy kiválasztott csoportjára. 

Igény-előrejelzés létrehozásához lépjen a **fő tervezési &gt;előrejelzés &gt;igény-előrejelzés &gt;előrejelzés létrehozása statisztikai eredeti**. 

Az előrejelzési időszakot előrejelzés generálásakor lehet kiválasztani. Az elérhető értékek: Nap, Hét és Hónap. 

Az** Előrejelzési horizont** mezőben adható meg azoknak az időszakoknak a száma, amelyekre vonatkozóan létrejön az előrejelzés. 

Ha az előrejelzési stratégia **Korábbi igény átmásolása**-ként van megadva, az előzményhorizont végét a rendszer figyelmen kívül hagyja. A rendszer másolja a megadott időszakok száma a **előrejelzés horizont** mezőben megjeleníti az előrejelzett igény, meghatározott időponttól kezdve a **dátumtól** mező alatt **történeti horizont**. Egy bizonyos dátumtól előrefelé elhelyezkedő előzményigények másolásával a termeléstervezők képesek elkészíteni a következő negyedév tervét. Az alábbi két módszer használható:

-   Igénymásolás az előző év ugyanazon negyedévéből.
-   Igénymásolás az előző negyedévből.

Annak érdekében, hogy a termelési tervek ne keveredhessenek össze, bizonyos számú előrejelzési időszak befagyasztható. Ezt a számot a **Befagyasztási időkorlát** mezőben lehet megadni. A **Módosított igény-előrejelzés **oldalon a befagyasztott időszakokhoz tartozó cellák letiltásra kerülnek, jelezve, hogy ezek az értékek nem változtathatók. 

A kiinduló igény-előrejelzés kezdő dátumának nem kell feltétlenül aktuális vagy jövőbeli dátumnak lennie. Egy másik kezdő dátum beállításához használja a **Kiinduló előrejelzés kezdő dátuma - Kezdő dátum** mezőt. Például júniusban a felhasználók létrehozhatnak következő évre vonatkozó előrejelzést. Mivel az igényelőzmények vége és a kiindulás kezdete közti előrejelzési időszakok hiányoznak, lehetséges, hogy az előrejelzés pontatlan lesz. Műveletek igény-előrejelzés szolgáltatás használata a Microsoft Dynamics 365, négy módja van, ahol a hiányzó hézagok kitöltheti. Kiválaszthatja a kívánt beállítást a hiányzó módszer\_érték\_helyettesítő paraméter a **igény-előrejelzés paraméterek** oldalon. 

A **eredeti előrejelzés kezdő dátuma** - **kezdő dátum** mezőben adhat meg egy előrejelzési időszak, például az elején az Egyesült Államokban, ha az előrejelzési időszak a hét vasárnap van. A rendszer automatikusan állítja be a **eredeti előrejelzés kezdő dátuma** - **kezdő dátum** megfelelően az előrejelzési időszak kezdete mezőben. 

A **eredeti előrejelzés kezdő dátuma** - **kezdő dátum** mező értéke lehet egy múltbeli dátumra. Azaz múltbeli igény-előrejelzés is generálható. Ez azért hasznos, mert lehetővé teszi a felhasználók számára, hogy úgy módosítsák az előrejelzési szolgáltatás paramétereit, hogy a generált múltbeli statisztikai előrejelzés megegyezzen a tényleges előzményigényekkel. Ezután a felhasználók ugyanezeket a paraméter-beállításokat felhasználva generálhatnak jövőre vonatkozó statisztikai kiinduló előrejelzést. 

A korábbi igény-előrejelzési iterációk során végrehajtott manuális kiigazítások a **Manuális kiigazítások átvitele az igény-előrejelzésbe** jelölőnégyzet bejelölésével az új kiinduló előrejelzésben automatikusan alkalmazhatók. Ha a jelölőnégyzet nincs bejelölve, a manuális kiigazítások nem kerülnek be a kiinduló előrejelzésbe – azonban nem törlődnek. Előrejelzésen végrehajtott manuális kiigazítások csak előrejelzés importálásakor törölhetők a **Kiinduló igény-előrejelzésen végrehajtott manuális kiigazítások mentése** jelölőnégyzetben lévő jelölés eltüntetésével. A manuális kiigazítások engedélyezéskor kerülnek mentésre. Ezért, ha a felhasználó kézi korrigálja az előrejelzés, de az előrejelzés vissza a Dynamics 365 műveletekhez nem engedélyezik, a módosítások elvesznek. További információt a manuális helyesbítések és a működésükről lásd: [kiigazított előrejelzés engedélyezése](authorize-adjusted-forecast.md). 

Az igény-előrejelzés generálásához név és leírás adható a generált előrejelzések könnyebb beazonosíthatósága érdekében. Ezek az értékek láthatók az előrejelzés-létrehozási előzményekben, a **Statisztikai kiinduló előrejelzés létrehozási előzményei** oldalon. 

Előrejelzés generálásakor szűrők alkalmazhatók vállalatközi tervezőcsoport, cikkfelosztási kulcsok és egyéb szempontok szerint. Ezek a teljesítmény javítására használhatók, illetve segítségükkel az adatokat kezelhető csoportokká lehet felosztani. Azonban fontos megjegyezni, hogy nem jön létre igény-előrejelzés olyan cikkfelosztási kulcsnak a tagjaira, amely nincs vállalatközi tervezőcsoporthoz társítva, még akkor sem, ha a lekérdezésben ki van választva a cikkfelosztási kulcs. 

**Tipp**: egyes esetekben a felhasználók igény-előrejelzés generálása alatt hibaüzeneteket kaphatnak, vagy az előrejelzés generálása munkamenetnapló nélkül fejeződhet be. Ez az előrejelzés generálásához előzőleg használt lekérdezésben maradt adatok miatt fordulhat elő. A probléma megoldásához a **Kiválasztás** gombbal nyissa meg a **Lekérdezés** oldalt, kattintson az **Alaphelyzet** lehetőségre, majd generálja újra a kiinduló előrejelzést. 

Ha az előrejelzés nem keletkezik olyan elemek nagy halmaza, hanem, például egy cikket vagy egy cikkfelosztási kulcs egyszerre, akkor ahhoz, hogy jobb teljesítményt, választhatja a **kérés-válasz mód használata** jelölőnégyzetet az **fő tervezési előrejelzés - Setup - igény szerint** - **előrejelzés paraméterek - gép tanulás Azure igény szerint** lap.

<a name="see-also"></a>Lásd még
--------

[Demand forecasting setup](demand-forecasting-setup.md)

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)


