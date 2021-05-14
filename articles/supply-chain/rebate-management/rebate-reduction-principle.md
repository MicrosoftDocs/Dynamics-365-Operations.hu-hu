---
title: Visszatérítés-csökkentési elvek
description: Ez a témakör a csökkentési elvek beállítását ismerteti. A csökkentési elvek befolyásolják a viselkedést, amikor több visszatérítés vonatkozik ugyanarra a cikkre vagy tranzakcióra.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TAMRebateCategory
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 5a8bbfaff05b665cb85e9166cfc76363c4aedb64
ms.sourcegitcommit: 890a0b3eb3c1f48d786b0789e5bb8641e0b8455e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/20/2021
ms.locfileid: "5919843"
---
# <a name="rebate-reduction-principles"></a>Visszatérítés-csökkentési elvek

[!include [banner](../includes/banner.md)]

A visszatérítés-kezelési ügyleteket *csökkentési elvekbe* csoportosíthatja, hogy csökkentse a cikkhez kapcsolódó egyéb tartalékokat, és/vagy csökkentse a visszatérítési számításokból eredő értékeket. A visszatérítés-csökkentési elvek beállítása után igény szerint hozzárendelheti őket a visszatérítés-kezelési ügyletek soraihoz.

A visszatérítés-csökkentési elv szabályai csak akkor érvényesek, ha a visszatérítési ügyletek átfedik egymást. Emiatt több visszatérítést is adhatnak olyan helyzetekben, ahol nem tartoznak több visszatérítéssel.

## <a name="manage-rebate-reduction-principles"></a>Visszatérítés-csökkentési elvek kezelése

A visszatérítések csökkentési elveinek használatához lépjen a **Visszatérítés-kezelés \> Beállítás \> Visszatérítés-csökkentési elvek** pontra. Ezután a műveleti panel gombjaival lehet szükség szerint csökkentési elveket hozzáadni és eltávolítani. Minden egyes elvhez állítsa be a mezőket, az alábbi táblában megadott módon.

| Mező | Leírás |
|---|---|
| Visszatérítés-csökkentési elv | Írjon be egy egyedi nevet a visszatérítés-csökkentési elvhez. |
| Leírás | Írjon be egy leírást a visszatérítés-csökkentési elvhez. |
| Csökkentés alkalmazása | Jelölje be ezt a jelölőnégyzetet, ha a visszatérítés-csökkentési elvhez tartozó visszatérítésekre csökkentési alapot fog alkalmazni. |
| Csökkentési alap | Ha be van jelölve a **Csökkentés alkalmazása** jelölőnégyzet, válassza ki a csökkentés alapját (*Tartalék*, *Visszatérítések* vagy *Mindkettő*). Ha a *Mindkettő* lehetőséget választja, és ha egy korábbi ügylethez mind egy tartalékot, mind visszatérítést feladtak, csak a visszatérítést alkalmazza a rendszer. |
| Kihagyás a csökkentésből | Ha ez a jelölőnégyzet be van jelölve, akkor az ehhez a visszatérítés-csökkentési elvhez tartozó tartalékok és visszatérítések ki lesznek zárva az ezt követő levonásokból. Erre a beállításra nem vonatkozik a **Csökkentési alap** mező beállítása. |

## <a name="examples-of-rebate-reduction-principle-setups"></a>Visszatérítés-csökkentés elvének beállításai – példák

Az alábbi táblázat a visszatérítések csökkentési elvének jellemző beállításait mutatja be. A **Leírás** mező értéke mindegyik visszatérítés-csökkentési alapelvnél leírja a visszatérítés-csökkentési elv célját.

| visszatérítés-csökkentési elv | Leírás | Csökkentés alkalmazása | Csökkentési alap | Kihagyás a csökkentésből |
|---|---|---|---|---|
| Halasztott | Visszatérítés csökkentése | Igen | Mindkettő | Nincs |
| Exclreb | Visszatérítés kihagyása | Igen | Visszatérítés | Igen |
| Többszörös | Több visszatérítés | Igen | Mindkettő | Igen |
| None | Csak tartalék és visszatérítés | Nincs | Mindkettő | Igen |
| Üzembe helyezés | Csak tartalék | Igen | Üzembe helyezés | Nincs |
| Visszatérítés | Csak visszatérítés | Igen | Visszatérítés | Igen |

## <a name="examples-of-rebate-reduction-principle-calculations"></a>Visszatérítés-csökkentés elvének számításai – példák

Olyan értékesítési rendelése van, amely egyetlen értékesítésirendelés-sort tartalmaz. Ennek a sornak az értéke 1000 USD. A következő ügyletek vonatkoznak a rendelésre:

- **1. ügylet:** 10 százalék 1000 USD-ból
- **2. ügylet:** 15 százalék 1000 USD-ból
- **3. ügylet:** 20 százalék 1000 USD-ból
- **4. ügylet:** 25 százalék 1000 USD-ból

A feldolgozás sorrendje nagyon fontos. A feldolgozási rendelés a munka módján alapul, a [Visszatérítések feldolgozása, ellenőrzése és feladása](process-review-post.md) részben leírtak szerint.

Például az alábbi táblázat összegzi az eredményt, ha a használt sorrend *1, 2, 3, 4*, és ha csak a tartalékokat dolgozza fel.

| Ügylet | Leírás és beállítások | Tartalék eredménye |
|---|---|---|
| 1 | <p>Az osztályozás nem ellenőrzi a többi ügyletet a csökkentések alapján. Az ellenőrzés a tartalékokra és visszatérítésekre is vonatkozik.</p><ul><li>**Csökkentés alkalmazása:** *Nem*</li><li>**Csökkentési alap:** *Mindkettő*</li><li>**Kihagyás a csökkentésből:** *Nem*</li></ul> | 1000 USD x 10% = 100 USD |
| 2 | <p>Az osztályozás ellenőrzi, hogy van-e más ügylet a csökkentésekhez, de úgy van megjelölve, hogy magát a figyelmen kívül hagyja. Az ellenőrzés csak a visszatérítésekre vonatkozóan történik meg.</p><ul><li>**Csökkentés alkalmazása:** *Igen*</li><li>**Csökkentés alapja:** *Visszatérítés*</li><li>**Kihagyás a csökkentésből:** *Igen*</li></ul> | 1000 USD x 15% = 150 USD |
| 3 | <p>Az osztályozás ellenőrzi a többi ügyletet a csökkentések alapján. Az ellenőrzés a tartalékokra és visszatérítésekre is vonatkozik.</p><ul><li>**Csökkentés alkalmazása:** *Igen*</li><li>**Csökkentési alap:** *Mindkettő*</li><li>**Kihagyás a csökkentésből:** *Nem*</li></ul> | (1000 USD – 1. ügylet) x 20% = 180 USD |
| 4 | <p>Az osztályozás ellenőrzi a többi ügyletet a csökkentések alapján. Az ellenőrzés a tartalékokra és visszatérítésekre is vonatkozik.</p><ul><li>**Csökkentés alkalmazása:** *Igen*</li><li>**Csökkentési alap:** *Mindkettő*</li><li>**Kihagyás a csökkentésből:** *Nem*</li></ul> | (1000 USD – 1. ügylet – 3. ügylet) x 25% = 180 USD |

Az alábbi táblázat néhány példát mutat be, amelyekben a tartalék feldolgozása különböző rendelésekben történt, és így különböző összegeket lehet elérni. A különbözet a tartalékok eltérése attól függ, hogy a rendszer milyen sorrendben dolgozza fel az ügyleteket. Fontos megérteni, hogy a feldolgozási sorrend hogyan befolyásolja a végleges visszatérítési összeget.

| Sorrend | Számítás |
|---|---|
| 1<br>(1, 2, 3, 4) | <ul><li>**1. ügylet:** 1000 USD x 10% = 100 USD</li><li>**2. ügylet:** 1000 USD x 15% = 150 USD</li><li>**3. ügylet:** (1000 USD – 1. ügylet) × 20% = 180 USD</li><li>**4. üzlet:** (1000 USD – 1. üzlet – 2. üzlet) × 25% = 180 USD</li><li>**Teljes tartalék:** 610 USD</li></ul> |
| 2<br>(4, 3, 2, 1) | <ul><li>**4. ügylet:** 1000 USD x 25% = 250 USD</li><li>**3. ügylet:** (1000 USD – 4. ügylet) × 20% = 150 USD</li><li>**2. ügylet:** 1000 USD x 15% = 150 USD</li><li>**1. ügylet:** 1000 USD x 10% = 100 USD</li><li>**Teljes tartalék:** 650 USD</li></ul> |
| 3<br>(3, 2, 1, 4) | <ul><li>**3. ügylet:** 1000 USD x 20% = 200 USD</li><li>**2. ügylet:** 1000 USD x 15% = 150 USD</li><li>**1. ügylet:** 1000 USD x 10% = 100 USD</li><li>**4. ügylet:** (1000 USD – 3. ügylet – 1. ügylet) × 25% = 175 USD</li><li>**Teljes tartalék:** 625 USD</li></ul> |
| 4<br>(2, 4, 1, 3) | <ul><li>**2. ügylet:** 1000 USD x 15% = 150 USD</li><li>**4. ügylet:** 1000 USD x 25% = 250 USD</li><li>**1. ügylet:** 1000 USD x 10% = 100 USD</li><li>**3. ügylet:** (1000 USD – 4. ügylet – 1. ügylet) × 20% = 130 USD</li><li>**Teljes tartalék:** 630 USD</li></ul> |
