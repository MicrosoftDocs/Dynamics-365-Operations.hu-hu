---
title: Késleltetési tűréshatár (negatív napok)
description: Ez a témakör a késleltetett tűréshatár kiszámításáról, valamint arról nyújt tájékoztatást, hogy hogyan befolyásolja a tervezett rendelések létrehozását a tervezési optimalizálásban.
author: crytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 748e047e89747f2eabccc04a40c79bcb1e6f3dea
ms.sourcegitcommit: f21659f1c23bc2cd65bbe7fb7210910d5a8e1cb9
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306463"
---
# <a name="delay-tolerance-negative-days"></a>Késleltetési tűréshatár (negatív napok)

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

A késleltetett tűréshatár funkcióval a tervezési optimalizálás figyelembe veszi a **Negatív napok** értékét, amely be van állítva a fedezetcsoportokhoz. Az alaptervezés során alkalmazott késleltetett tűréshatár időszakának meghosszabbítása. Ily módon elkerülheti az új ellátási rendelések létrehozását, ha a meglévő készlet képes lesz fedezni az igényt egy rövid késleltetés után. A funkció célja annak meghatározása, hogy van-e értelme új ellátási rendelést létrehozni egy adott igényre.

## <a name="turn-on-the-feature-in-your-system"></a>A funkció bekapcsolása a rendszerben

Ha a késleltetési tűréshatár funkciót elérhetővé szeretné tenni a rendszerben, menjen a [Funkciókezelés](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) elemre, és kapcsolja be a *Negatív napok tervezési optimalizáláshoz* funkciót.

## <a name="delay-tolerance-in-planning-optimization"></a>A tervezési optimalizálás késleltetési tűréshatára

A késleltetési tűréshatár azt jelzi, hogy hány napot kell várnia az átfutási idő után, mielőtt új feltöltést rendel, amikor a meglévő készlet már meg van tervezve. A késleltetési tűréshatárt naptári napok, nem pedig munkanapok határozzák meg.

Az alaptervezéskor, amikor a rendszer kiszámítja a késleltetési tűréshatárt, figyelembe veszi a **Negatív napok** beállítását. A **Negatív napok** értéket a **Fedezeti csoportok** vagy a **Cikk fedezete** oldalakon állíthatja be.

A rendszer a késleltetett tűréshatár számítását a *legkorábbi feltöltési dátumhoz* – amely a mai dátum és az átfutási idő értékével egyenlő – összeköti. A késleltetési tűréshatár számítása a következő képlettel történik, ahol a *max()* függvény két érték közül a nagyobbat találja meg:

*max(Legkorábbi feltöltési dátum, Igény esedékesség dátuma)* – *Igény esedékesség dátuma* + *Negatív napok*

Ez a képlet gondoskodik arról, hogy az alaptervezés ne hozzon létre új ellátási rendeléseket, ha a termék átfutási ideje alatt elegendő készlet létezik.

> [!NOTE]
> A Tervezési optimalizálásnál a késleltetett tűréshatár számítása mindig a beépített alaptervezés dinamikus negatív napszámítását használja. Az **Alaptervezés paraméterei** lapon a **Dinamikus negatív napok** használata beállítás nincs hatással erre a viselkedésre.

Ha a meglévő készlet a számított késleltetési tűréshatárnál kisebb vagy azzal egyenlő igény-késleltetést jelent, akkor a Tervezési optimalizálás a meglévő készletet az igénynek megfelelő mennyiséggel egyenlíti ki. Bizonyos esetekben jobb késleltetni az igényt, mint ha a végén túl sok idő lenne.

Az alábbi alszakaszok olyan példákat mutatnak be, amelyek bemutatják, hogy a késleltetés tűréshatára hogyan befolyásolja a tervezett rendelések létrehozását a tervezési optimalizálásban.

### <a name="example-1"></a>1. példa

Egy termék a következő konfigurációval rendelkezik:

- **Átfutási idő:** *10*
- **Negatív napok:** *2*

A termékre a következő ellátás és igény létezik:

- **Igény a mai napra:** Értékesítési rendelés 10 mennyiségre
- **Készlet 12 napon belül:** Beszerzési rendelés 10 mennyiségre

A meglévő készlet 12 napon belül fedezheti az igényt, és ez az időszak megegyezik a késleltetett tűréshatársal. Ezért az alaptervezés futtatásakor nem jön létre tervezett rendelés.

### <a name="example-2"></a>2. példa

Egy termék a következő konfigurációval rendelkezik:

- **Átfutási idő:** *10*
- **Negatív napok:** *0*

A termékre a következő ellátás és igény létezik:

- **Igény a mai napra:** Értékesítési rendelés 10 mennyiségre
- **Készlet 12 napon belül:** Beszerzési rendelés 10 mennyiségre

A meglévő készlet csak 12 nap után fedezheti az igényt. A késleltetési tűréshatár azonban 10 nap. Ezért az alaptervezés futtatásakor egy 10 mennyiségű tervezett rendelés jön létre.

### <a name="example-3"></a>3. példa

Egy termék a következő konfigurációval rendelkezik:

- **Átfutási idő:** *10*
- **Negatív napok:** *2*

A termékre a következő ellátás és igény létezik:

- **Igény 11 napon belül:** Értékesítési rendelés 10 mennyiségre
- **Készlet 14 napon belül:** Beszerzési rendelés 10 mennyiségre

A meglévő készlet csak három nap után fedezheti az igényt. A késleltetési tűréshatár azonban két nap. (Ebben az esetben a késleltetési tűréshatár csak a két negatív napot tartalmazza. Az igény dátuma nem szerepel, mert a termék átfutási ideje után van.) Ezért az alaptervezés futtatásakor egy 10 mennyiségű tervezett rendelés jön létre.
