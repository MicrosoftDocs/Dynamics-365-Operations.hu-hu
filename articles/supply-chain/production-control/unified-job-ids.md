---
title: Egyesített számsorozat a feladatazonosítók esetén
description: Ez a funkció egyetlen, egységes számsorozatot biztosít, amely feladatazonosítókat hoz létre a Gyártásvezérlés, a Gyártásvégrehajtás és a Munkaidő és jelenlét modulokhoz.
author: johanhoffmann
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8ff8fae0bb20b11b15c7520fbb14727ff0372ca0255adc82599c6680a64671af
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6748715"
---
# <a name="unified-number-sequence-for-job-ids"></a>Egyesített számsorozat a feladatazonosítók esetén

[!include [banner](../includes/banner.md)]

Ez a funkció egyetlen, egységes számsorozatot biztosít, amely feladatazonosítókat hoz létre a Gyártásvezérlés, a Gyártásvégrehajtás és a Munkaidő és jelenlét modulokhoz. Korábban mindegyik modulhoz más számsorozatot választhatott, ami ütköző feladatazonosítókat eredményezhet, ha két vagy több ilyen sorozat azonos formátumot használt. Egy ilyen ütközés adatsérülést okozhat.

## <a name="turn-on-this-feature-for-your-system"></a>A funkció bekapcsolása a rendszerhez

Ha a rendszer még nem tartalmazza az ebben a témakörben leírt funkciót, lépjen a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lehetőségre, és a kapcsolja be az *Egyesített számsorozat a feladatazonosítók esetén* funkciót.

## <a name="set-up-the-unified-number-sequence-for-job-ids"></a>Egyesített számsorozat beállíítása a feladatazonosítók esetén

A funkció engedélyezése után a Gyártásvezérlés, a Gyártásvégrehajtás, valamint a Munkaidő és jelenlét modulok paraméteroldalán található meglévő **Feladatazonosító** számsorozat-beállítások elavultak lesznek, és egy új **Egyesített feladatazonosító** mező kerül hozzáadásra. Az **Egyesített feladatazonosító** értéket mindhárom modulban közös, így biztosítva, hogy minden modul ugyanerre a számsorozatra hivatkozzon. A feladatazonosítók ezért mindhárom modulban egyediek lesznek, és soha nem fordul elő ütközés.

Egyesített számsorozat beállíítása a feladatazonosítók esetén:

1. Kapcsolja be a funkciót az előző szakaszban leírtak szerint.
1. Azonosítsa az egyesített feladatazonosítókhoz használni kívánt számsorozatot, vagy hozzon létre egy újat. További információkért lásd: [Számsorozatok áttekintése](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).
1. Lépjen a **Gyártásvezérlés paraméterei**, a **Gyártásvégrehajtás paraméterei** vagy a **Munkaidő és jelenlét paraméterei** oldalra. Nem számít, melyiket választja, mert amikor ezt a beállítást bármelyik oldalon megteszi, az összes többi oldal automatikusan frissül.
1. Nyissa meg a **Számsorozatok** lapot a kiválasztott paraméterek lapon.
1. Rendelje hozzá a korábban azonosított **Számsorozatkódot** a rács **Egyesített feladatazonosítók** sorához.
