---
title: Igényvezérelt tervezés
description: A cikk azt írja le, hogyan lehet tervezett rendeléseket generálni az olyan cikkekhez, amelyek összecsukó pontként vannak beállítva.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 8ba9a6d24923b66259bc8b6cc688ec667cb000de
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740302"
---
# <a name="demand-driven-planning"></a>Igényvezérelt tervezés

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

A cikk azt írja le, hogyan lehet tervezett rendeléseket generálni az olyan cikkekhez, amelyek összecsukó pontként vannak beállítva.

## <a name="net-flow-and-qualified-demand"></a>Nettó áramlás és minősített igény

*Az* alaptervezés során a rendszer a nettó áramlás koncepcióját alkalmazza, hogy meghatározza a tényleges aktuális készleten alapuló tényleges készletet, valamint a megrendelt készletet (a meglévő, még be nem érkezett ellátási rendeléseket), *mínusz* azt, amit minősített igénynek (minősített közelgő értékesítésnek) nevezzük, amint azt az alábbi ábra mutatja. Amikor a rendszer meghatározza, hogy melyik pufferzónába tartozik egy cikk, és milyen rendelt mennyiségnek kell lennie, a nettó áramlást vizsgálja, nem pedig a tényleges aktuális készletet.

![Példa a nettó áramlás számítási diagramjára.](media/ddmrp-net-flow-example.png "Példa a nettó áramlás számítási diagramjára")

Ha egy tervezési futtatás során egy tervezett rendelés indul el, a megrendelt mennyiség a maximális szint mínusz a nettó áramlás lesz. A rendelési prioritás hozzárendeléséhez a rendszer [a szükségletdát napok helyett prioritáson](priority-based-planning.md) alapuló tervezési funkciókat használ. Az igényvezérelt anyagigény-tervezés (DDMRP) a megrendelt mennyiség alapján a tervezett rendelés prioritását a maximális készlet százalékaként rendeli hozzá. Az előző példában a megrendelt mennyiség a maximális mennyiség 53 százaléka. Emiatt a feltöltés rendelési prioritása 53 lesz. (Környezetben a 0 a legmagasabb, a 100 a legalacsonyabb prioritás.)

*A minősített* igény a múltbeli igény, valamint a mai igény plusz a minősített rendelési igények a jövőben. Az alábbi ábra a mai és a következő három nap igényszintjét mutatja be (június 12.). A DDMRP lehetővé teszi a rendelési küszöbérték beállítását a normál várakozásnál nagyobb igény azonosítása érdekében. Ha a küszöbérték 25 darabra van állítva, az ábrán látható jövőbeli dátumok közül kettő rendelési időnek számít. Az egyes termékekre vonatkozó rendelési küszöbértéket **egyenként** kell hozzárendelni a cikkfedezeti lap használatával, [az egy-egy puffer beállítása pontcikkhez leírtak szerint](ddmrp-buffer-profile-and-levels.md#set-up-buffers).

![Példa egy minősített igényszámítási diagramra.](media/ddmrp-net-qualified-demand-example.png "Példa a megfelelő igényszámítási diagramra")

Feltéve, hogy nincs múltbeli igény, a mai igényt (18) hozzáadhatja a két rendelés mennyiséghez (29 és 26) a 73-as minősített igény megigénylése érdekében. Bár van is igény június 23-ra, figyelje meg, hogy nem szerepel a nettó folyamat számításában, mert a DDMRP a hagyományos tervezési fedezeti csoportoktól eltérő módon indítja el a tervezett rendelést.

## <a name="generating-planned-orders-with-ddmrp"></a>Tervezett rendelések létrehozása DDMRP-jelentéssel

Egy tervezési futtatás során a rendszer új tervezett rendelést hoz létre, ha egy cikk nettó áramlása az újrarendelési pont alá csökken. A DDMRP használata során általában minden nap tervez. Ennek megfelelően a készletszinteket gyakorlatilag naponta egyszer ellenőrzi, hogy melyik cikkeket kell feltölteni.

A következő ábra egy olyan helyzetre mutat be, amikor június 20-án 18 darabra, június 21-én 29 darabra, június 22-én 26 darabra, június 23-án pedig 20 darabra van megrendelés. Mivel a küszöb 25 darabra van állítva, ezért ezek közül a rendelések közül kettő is két különbözőnek lesz megjelölve. 220 darab van az adott cikkből.

![1. tervezési példa.](media/ddmrp-planning-example-1.png "1. tervezési példa")

Ha most futtatja az alaptervezést, az egy tervezett rendelést generál, ha a nettó áramlás az újrarendelési pont alá csökken (ebben a példában 219 darab).

![2. tervezési példa.](media/ddmrp-planning-example-2.png "2. tervezési példa")

Ez a példa egy tervezett beszerzési rendelést készít, amelynek mennyisége 130, amely egyenlő a maximális szint mínusz a nettó áramlás. A tervezett rendelés prioritása 53,07, a maximális mennyiség százalékos értéke alapján. Mivel ezek az értékek június 20-án találhatók, a rendszer létrehoz egy június 20-ai dátumra tervezett rendelést, valamint a cikkre vonatkozó le nem járt átfutási időt (ebben a példában öt munkanap). Ezért mivel öt munkanap egy hétre van a mai naptól, a tervezett rendelés június 27-e.

> [!NOTE]
> Az alaptervezés csak a DDMRP használatával számítja ki a lecsatolt cikkeket. Az összes többi cikk számítása az alapanyagigény-tervezés (MRP) alapján történik.
