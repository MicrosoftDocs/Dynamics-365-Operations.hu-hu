---
title: "Statisztikai kiinduló előrejelzés generálása"
description: "Ez a cikk az igény-előrejelzés számítása során használt paraméterekről és szűrőkről nyújt tájékoztatást."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 72683
ms.assetid: 42190463-2a64-4f63-b653-10cac3df0692
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6e55999dcbc1bb9e569f3ec2374f4efb95323fb8
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="generate-a-statistical-baseline-forecast"></a>Statisztikai kiinduló előrejelzés generálása

[!include[banner](../includes/banner.md)]


Ez a cikk az igény-előrejelzés számítása során használt paraméterekről és szűrőkről nyújt tájékoztatást. 

A kiinduló előrejelzés létrehozásakor először meg kell adni számításhoz használt paramétereket és szűrőket. Például létrehozhat olyan kiinduló előrejelzést, ami egy adott vállalat elmúlt évi tranzakcióadatai alapján hoz létre becslést a jövő hónapra, cikkek egy kiválasztott csoportjára. 

Igény-előrejelzés létrehozásához lépjen az **Alaptervezés &gt; Előrejelzés &gt; Igény-előrejelzés &gt; Statisztikai kiinduló előrejelzés generálása** lehetőségre. 

Az előrejelzési időszakot előrejelzés generálásakor lehet kiválasztani. Az elérhető értékek: Nap, Hét és Hónap. 

Az **Előrejelzési horizont** mezőben adható meg azoknak az időszakoknak a száma, amelyekre vonatkozóan létrejön az előrejelzés. 

Ha az előrejelzési stratégia **Korábbi igény átmásolása**-ként van megadva, az előzményhorizont végét a rendszer figyelmen kívül hagyja. A rendszer átmásolja az időszakok az **Előrejelzési horizont** mezőben beállított számát a jelzett igénybe az **Előzményhorizont** alatti **Kezdő dátum** mezőben megadott dátumtól indulva. Egy bizonyos dátumtól előrefelé elhelyezkedő előzményigények másolásával a termeléstervezők képesek elkészíteni a következő negyedév tervét. Az alábbi két módszer használható:

-   Igénymásolás az előző év ugyanazon negyedévéből.
-   Igénymásolás az előző negyedévből.

Annak érdekében, hogy a termelési tervek ne keveredhessenek össze, bizonyos számú előrejelzési időszak befagyasztható. Ezt a számot a **Befagyasztási időkorlát** mezőben lehet megadni. A **Módosított igény-előrejelzés** oldalon a befagyasztott időszakokhoz tartozó cellák letiltásra kerülnek, jelezve, hogy ezek az értékek nem változtathatók. 

A kiinduló igény-előrejelzés kezdő dátumának nem kell feltétlenül aktuális vagy jövőbeli dátumnak lennie. Egy másik kezdő dátum beállításához használja a **Kiinduló előrejelzés kezdő dátuma - Kezdő dátum** mezőt. Például júniusban a felhasználók létrehozhatnak következő évre vonatkozó előrejelzést. Mivel az igényelőzmények vége és a kiindulás kezdete közti előrejelzési időszakok hiányoznak, lehetséges, hogy az előrejelzés pontatlan lesz. A Microsoft Dynamics 365 for Finance and Operations Igény-előrejelzési szolgáltatás használatával négyféle módon is kitöltheti a hiányzó időszakok helyét. A kívánt módszert az **Igény-előrejelzési paraméterek** oldalon található MISSING\_VALUE\_SUBSTITUTION paraméter megadásával választhatja ki. 

A **Kiinduló előrejelzés kezdő dátuma** - **Kezdő dátum** mezőt az előrejelzési időszak kezdetére kell beállítani (például az USA-ban egy vasárnapi napra, amennyiben az előrejelzési időszak a hét). A rendszer automatikusan módosítja a **Kiinduló előrejelzés kezdő dátuma** - **Kezdő dátum** mezőt úgy, hogy az megegyezzen egy előrejelzési időszak kezdetével. 

A **Kiinduló előrejelzés kezdő dátuma** - **Kezdő dátum** mező múltbeli dátumra is beállítható. Azaz múltbeli igény-előrejelzés is generálható. Ez azért hasznos, mert lehetővé teszi a felhasználók számára, hogy úgy módosítsák az előrejelzési szolgáltatás paramétereit, hogy a generált múltbeli statisztikai előrejelzés megegyezzen a tényleges előzményigényekkel. Ezután a felhasználók ugyanezeket a paraméter-beállításokat felhasználva generálhatnak jövőre vonatkozó statisztikai kiinduló előrejelzést. 

A korábbi igény-előrejelzési iterációk során végrehajtott manuális kiigazítások a **Manuális kiigazítások átvitele az igény-előrejelzésbe** jelölőnégyzet bejelölésével az új kiinduló előrejelzésben automatikusan alkalmazhatók. Ha a jelölőnégyzet nincs bejelölve, a manuális kiigazítások nem kerülnek be a kiinduló előrejelzésbe – azonban nem törlődnek. Előrejelzésen végrehajtott manuális kiigazítások csak előrejelzés importálásakor törölhetők a **Kiinduló igény-előrejelzésen végrehajtott manuális kiigazítások mentése** jelölőnégyzetben lévő jelölés eltüntetésével. A manuális kiigazítások engedélyezéskor kerülnek mentésre. Ezért ha egy felhasználó manuális kiigazításokat hajt végre az előrejelzésen, de azt nem engedélyezi a Finance and Operations rendszerben, a változtatások elvesznek. A manuális kiigazításokkal és azok működésével kapcsolatos további tudnivalókat lásd: [Kiigazított előrejelzés engedélyezése](authorize-adjusted-forecast.md). 

Az igény-előrejelzés generálásához név és leírás adható a generált előrejelzések könnyebb beazonosíthatósága érdekében. Ezek az értékek láthatók az előrejelzés-létrehozási előzményekben, a **Statisztikai kiinduló előrejelzés létrehozási előzményei** oldalon. 

Előrejelzés generálásakor szűrők alkalmazhatók vállalatközi tervezőcsoport, cikkfelosztási kulcsok és egyéb szempontok szerint. Ezek a teljesítmény javítására használhatók, illetve segítségükkel az adatokat kezelhető csoportokká lehet felosztani. Azonban fontos megjegyezni, hogy nem jön létre igény-előrejelzés olyan cikkfelosztási kulcsnak a tagjaira, amely nincs vállalatközi tervezőcsoporthoz társítva, még akkor sem, ha a lekérdezésben ki van választva a cikkfelosztási kulcs. 

**Tipp**: egyes esetekben a felhasználók igény-előrejelzés generálása alatt hibaüzeneteket kaphatnak, vagy az előrejelzés generálása munkamenetnapló nélkül fejeződhet be. Ez az előrejelzés generálásához előzőleg használt lekérdezésben maradt adatok miatt fordulhat elő. A probléma megoldásához a **Kiválasztás** gombbal nyissa meg a **Lekérdezés** oldalt, kattintson az **Alaphelyzet** lehetőségre, majd generálja újra a kiinduló előrejelzést. 

Ha az előrejelzés generálása nagyszámú cikk esetén sikertelen, de például egyszerre egy cikk vagy egy cikkfelosztási kulcs esetén sikeres, akkor a nagyobb teljesítmény érdekében bejelölheti a **Kérelemre adott válasz mód használata** jelölőnégyzetet az **Alaptervezés - Beállítás - Igény-előrejelzés** - **Igény-előrejelzési paraméterek - Azure Machine Learning** lapon.

<a name="see-also"></a>Lásd még
--------

[Igény-előrejelzési beállítások](demand-forecasting-setup.md)

[A kiinduló előrejelzés manuális kiigazítása](manual-adjustments-baseline-forecast.md)

[Beállított előrejelzés engedélyezése](authorize-adjusted-forecast.md)




