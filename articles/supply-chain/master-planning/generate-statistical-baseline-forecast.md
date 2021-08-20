---
title: Statisztikai kiinduló előrejelzés létrehozása
description: Ez a témakör az igény-előrejelzés számítása során használt paraméterekről és szűrőkről nyújt tájékoztatást.
author: roxanadiaconu
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72683
ms.assetid: 42190463-2a64-4f63-b653-10cac3df0692
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b196018f67a8ac991566a703ec091ae13f100a27dbb77b310d59c6e2a55bb40
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6753987"
---
# <a name="generate-a-statistical-baseline-forecast"></a>Statisztikai kiinduló előrejelzés létrehozása

[!include [banner](../includes/banner.md)]

Ez a témakör az igény-előrejelzés számítása során használt paraméterekről és szűrőkről nyújt tájékoztatást. 

A kiinduló előrejelzés létrehozásakor először meg kell adni számításhoz használt paramétereket és szűrőket. Például létrehozhat olyan kiinduló előrejelzést, ami egy adott vállalat elmúlt évi tranzakcióadatai alapján hoz létre becslést a jövő hónapra, cikkek egy kiválasztott csoportjára. 

Igény-előrejelzés létrehozásához lépjen az **Alaptervezés &gt; Előrejelzés &gt; Igény-előrejelzés &gt; Statisztikai kiinduló előrejelzés generálása** lehetőségre. 

Az előrejelzési időszakot előrejelzés generálásakor lehet kiválasztani. Az elérhető értékek: Nap, Hét és Hónap. 

Az **Előrejelzési horizont** mezőben adható meg azoknak az időszakoknak a száma, amelyekre vonatkozóan létrejön az előrejelzés. 

Ha az előrejelzési stratégia **Korábbi igény átmásolása**-ként van megadva, az előzményhorizont végét a rendszer figyelmen kívül hagyja. A rendszer átmásolja az időszakok az **Előrejelzési horizont** mezőben beállított számát a jelzett igénybe az **Előzményhorizont** alatti **Kezdő dátum** mezőben megadott dátumtól indulva. Egy bizonyos dátumtól előrefelé elhelyezkedő előzményigények másolásával a termeléstervezők képesek elkészíteni a következő negyedév tervét. Az alábbi két módszer használható:

-   Igénymásolás az előző év ugyanazon negyedévéből.
-   Igénymásolás az előző negyedévből.

Annak érdekében, hogy a termelési tervek ne keveredhessenek össze, bizonyos számú előrejelzési időszak befagyasztható. Ezt a számot a **Befagyasztási időkorlát** mezőben lehet megadni. A **Módosított igény-előrejelzés** oldalon a befagyasztott időszakokhoz tartozó cellák letiltásra kerülnek, jelezve, hogy ezek az értékek nem változtathatók. 

A kiinduló igény-előrejelzés kezdő dátumának nem kell feltétlenül aktuális vagy jövőbeli dátumnak lennie. Egy másik kezdő dátum beállításához használja a **Kiinduló előrejelzés kezdő dátuma - Kezdő dátum** mezőt. Például júniusban a felhasználók létrehozhatnak következő évre vonatkozó előrejelzést. Mivel az igényelőzmények vége és a kiindulás kezdete közti előrejelzési időszakok hiányoznak, lehetséges, hogy az előrejelzés pontatlan lesz. Az Igény-előrejelzési szolgáltatás használatával négyféle módon is kitöltheti a hiányzó időszakok helyét. A kívánt módszert az **Igény-előrejelzési paraméterek** oldalon található MISSING\_VALUE\_SUBSTITUTION paraméter megadásával választhatja ki. 

> [!NOTE]
> A hiányzó érték helyettesítése csak a múltbeli adatok kezdő és befejező dátuma közötti adathézagokhoz használható. A program nem tölti ki az adatokat az utolsó fizikai adatpont előtt vagy után, és csak a tényleges meglévő adatpontok között következtet. 

A **Kiinduló előrejelzés kezdő dátuma** - **Kezdő dátum** mezőt az előrejelzési időszak kezdetére kell beállítani (például az USA-ban egy vasárnapi napra, amennyiben az előrejelzési időszak a hét). A rendszer automatikusan módosítja a **Kiinduló előrejelzés kezdő dátuma** - **Kezdő dátum** mezőt úgy, hogy az megegyezzen egy előrejelzési időszak kezdetével. 

A **Kiinduló előrejelzés kezdő dátuma** - **Kezdő dátum** mező múltbeli dátumra is beállítható. Azaz múltbeli igény-előrejelzés is generálható. Ez azért hasznos, mert lehetővé teszi a felhasználók számára, hogy úgy igazítsák az előrejelzési szolgáltatás paramétereit, hogy a generált múltbeli statisztikai előrejelzés megegyezzen a tényleges előzményigényekkel. Ezután a felhasználók ugyanezeket a paraméter-beállításokat felhasználva generálhatnak jövőre vonatkozó statisztikai kiinduló előrejelzést. 

A korábbi igény-előrejelzési iterációk során végrehajtott manuális kiigazítások a **Manuális kiigazítások átvitele az igény-előrejelzésbe** jelölőnégyzet bejelölésével az új kiinduló előrejelzésben automatikusan alkalmazhatók. Ha a jelölőnégyzet nincs bejelölve, a manuális kiigazítások nem kerülnek be a kiinduló előrejelzésbe – azonban nem törlődnek. Előrejelzésen végrehajtott manuális kiigazítások csak előrejelzés importálásakor törölhetők a **Kiinduló igény-előrejelzésen végrehajtott manuális kiigazítások mentése** jelölőnégyzetben lévő jelölés eltüntetésével. A manuális kiigazítások engedélyezéskor kerülnek mentésre. Ezért ha egy felhasználó manuális kiigazításokat hajt végre az előrejelzésen, de azt nem engedélyezi a Supply Chain Management rendszerben, a változtatások elvesznek. A manuális kiigazításokkal és azok működésével kapcsolatos további tudnivalókat lásd: [Kiigazított előrejelzés engedélyezése](authorize-adjusted-forecast.md). 

Az igény-előrejelzés generálásához név és leírás adható a generált előrejelzések könnyebb beazonosíthatósága érdekében. Ezek az értékek láthatók az előrejelzés-létrehozási előzményekben, a **Statisztikai kiinduló előrejelzés létrehozási előzményei** oldalon. 

Előrejelzés generálásakor szűrők alkalmazhatók vállalatközi tervezőcsoport, cikkfelosztási kulcsok és egyéb szempontok szerint. Ezek a teljesítmény javítására használhatók, illetve segítségükkel az adatokat kezelhető csoportokká lehet felosztani. Azonban fontos megjegyezni, hogy nem jön létre igény-előrejelzés olyan cikkfelosztási kulcsnak a tagjaira, amely nincs vállalatközi tervezőcsoporthoz társítva, még akkor sem, ha a lekérdezésben ki van választva a cikkfelosztási kulcs. 

> [!TIP]
> Egyes esetekben a felhasználók igény-előrejelzés generálása alatt hibaüzeneteket kaphatnak, vagy az előrejelzés generálása munkamenetnapló nélkül fejeződhet be. Ez az előrejelzés generálásához előzőleg használt lekérdezésben maradt adatok miatt fordulhat elő. A probléma megoldásához a **Kiválasztás** gombbal nyissa meg a **Lekérdezés** oldalt, válassza az **Alaphelyzet** lehetőséget, majd generálja újra a kiinduló előrejelzést. 

Ha az előrejelzés generálása nagyszámú cikk esetén sikertelen, de például egyszerre egy cikk vagy egy cikkfelosztási kulcs esetén sikeres, akkor a nagyobb teljesítmény érdekében bejelölheti a **Kérelemre adott válasz mód használata** jelölőnégyzetet az **Alaptervezés - Beállítás - Igény-előrejelzés** - **Igény-előrejelzési paraméterek - Azure Machine Learning** lapon.

> [!NOTE]
> Az esetlegesen lapos előrejelzés a múltbeli adatoknak tudható be, amelyeknek egy hosszabb történelmi időtartamot kell lefedniük (minimum 3 időszaknak kell lennie ahhoz, hogy ki lehessen választani a mintákat, például 3 év havi előrejelzései). Ha jobb eredményt szeretne kapni, próbálja meg módosítani az időtartomány részletességét vagy növelni az időtartomány.

## <a name="additional-resources"></a>További erőforrások

- [Igény-előrejelzés beállítása](demand-forecasting-setup.md)

- [A kiinduló előrejelzés manuális kiigazítása](manual-adjustments-baseline-forecast.md)

- [Módosított előrejelzés engedélyezése](authorize-adjusted-forecast.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]