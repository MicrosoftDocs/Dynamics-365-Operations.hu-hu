---
title: Késleltetési tűréshatár (negatív napok)
description: Ez a cikk a késleltetett tűréshatár kiszámításáról és arról nyújt tájékoztatást, hogy hogyan befolyásolja a tervezett rendelések létrehozását a tervezési optimalizálásban.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 78ba4236705f1a200d9fe796eb80d0241b0fa537
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740468"
---
# <a name="delay-tolerance-negative-days"></a>Késleltetési tűréshatár (negatív napok)
<!-- KFM: Split topic into PO and classic -->

[!include [banner](../../includes/banner.md)]

A késleltetett tűréshatár funkcióval a tervezési optimalizálás **figyelembe** veszi a negatív napok értékét, amely be van állítva a fedezetcsoportokhoz, a cikkfedezethez és/vagy az alaptervhez. Az alaptervezés során alkalmazott késleltetett tűréshatár időszakának meghosszabbítása. Ily módon elkerülheti az új ellátási rendelések létrehozását, ha a meglévő készlet képes lesz fedezni az igényt egy rövid késleltetés után. A funkció célja annak meghatározása, hogy van-e értelme új ellátási rendelést létrehozni egy adott igényre.

## <a name="turn-delay-tolerance-features-on-or-off"></a>A késleltetett tűréshatár funkcióinak be- és kikapcsolása

Ha a késleltetett tűréshatár funkciót elérhetővé tenni a rendszerben, [használja a Funkciókezelést](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), és kapcsolja be a következő funkciókat:

- *Negatív napok a tervezési optimalizáláshoz* – ez a funkció a negatív napok beállítását engedélyezi fedezetcsoportokhoz és cikkfedezethez. Az Ellátásilánc-kezelés 10.0.29-es verziója szerint a funkció kötelező, és nem lehet kikapcsolni.
- *Rendelésre való ellátásautomatizálás* – ez a funkció a negatív napok beállítását engedélyezi az alaptervek számára. (További tájékoztatás: [Rendelésre való ellátásautomatizálás](../make-to-order-supply-automation.md).)

## <a name="delay-tolerance-in-planning-optimization"></a>A tervezési optimalizálás késleltetési tűréshatára

A késleltetési tűréshatár azt jelzi, hogy hány napot kell várnia az átfutási idő után, mielőtt új feltöltést rendel, amikor a meglévő készlet már meg van tervezve. A késleltetési tűréshatárt naptári napok, nem pedig munkanapok határozzák meg.

Az alaptervezéskor, amikor a rendszer kiszámítja a késleltetési tűréshatárt, figyelembe veszi a **Negatív napok** beállítását. A Negatív napok értéket **a** Fedezeti csoportok **lapon**, **·** **a Cikkfedezet lapon vagy az Alaptervek lapon állíthatja** be. Ha egynél több szinten vannak negatív napok hozzárendelve, a rendszer az alábbi hierarchiában határozza meg, hogy melyik beállítást használja:

- Ha az Alaptervek **lapon** engedélyezve van a negatív napok használata, ez a beállítás felülbírálja a terv futtatásakor megadott összes többi negatív napbeállítást.
- Ha a Cikkfedezet **lapon** negatív napok vannak beállítva, ez a beállítás felülbírálja a fedezeti csoport beállítását.
- A Fedezeti csoportok **lapon** beállított negatív napok csak akkor érvényesek, ha egy adott cikkhez vagy tervhez nincsenek beállítva negatív napok.

A rendszer a késleltetett tűréshatár számítását a *legkorábbi feltöltési dátumhoz* – amely a mai dátum és az átfutási idő értékével egyenlő – összeköti. A késleltetési tűréshatár számítása a következő képlettel történik, *ahol a max()* függvény két érték közül a nagyobbat találja meg:

*max(Legkorábbi feltöltési dátum, Igény esedékesség dátuma)* – *Igény esedékesség dátuma* + *Negatív napok*

Ez a képlet gondoskodik arról, hogy az alaptervezés ne hozzon létre új ellátási rendeléseket, ha a termék átfutási ideje alatt elegendő készlet létezik.

> [!NOTE]
> A tervezési optimalizálás késleltetési tűréshatárának számítása mindig az elavult alaptervezési motor dinamikus negatív napszámítását használja. Az **Alaptervezés paraméterei** lapon a **Dinamikus negatív napok** használata beállítás nincs hatással erre a viselkedésre.

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
