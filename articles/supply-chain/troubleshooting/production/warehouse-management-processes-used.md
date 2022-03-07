---
title: Jelenleg raktárkezelési folyamatok vannak használatban
description: Munka lefoglalása vagy kiadása során üzenetet kaphat arról, hogy jelenleg raktárkezelési folyamatok vannak használatban. A probléma megoldásához kövesse az alábbi lépéseket.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: bfda2fae824cdc64d722310d20cf16e6306d766c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476504"
---
# <a name="cant-reserve-or-release-work-because-processes-are-currently-being-used"></a>Nem lehet lefoglalni vagy kiadni a munkát, mert jelenleg folyamatok vannak használatban.

## <a name="symptoms"></a>Tünetek

Az elkülönített gyártás során a következő hiba jelenhet meg:

> Jelenleg raktárkezelési folyamatok vannak használatban. Ha a munkasorok még nincsenek regisztrálva, visszavonhatja a létrehozott munkát és a rakomány- vagy szállítólevélsorokat, majd folytathatja a kitárolási vagy szállítási folyamatot.

## <a name="cause"></a>Ok

Ez a probléma akkor fordul elő, ha munkát próbál lefoglalni vagy kiadni egy sorhoz, de a készlettranzakció állapota *Kitárolva* értéken van, ami azt jelzi, hogy az anyag ki lett tárolva.

## <a name="resolution"></a>Megoldás

Ezen hiba javításához kövesse az alábbi lépések egyikét.

- Módosítsa a termelési rendelés állapotát *Becsült* vagy *Kiadott* értékre.
- Nyissa meg a részletek lapot a releváns termelési rendeléshez. A Művelet panel **Raktár** fülének **Leállítás** csoportjában válassza a **Leállítás és visszatárolás** lehetőséget, és törölje a jelet az összes tranzakció visszatárolásához. Ezután válassza a **Leállítás eltávolítása** lehetőséget a termelési rendelés feldolgozásához.

Itt van egy magyarázat a *Kitárolás* és *Leállítás* funkciókhoz:
  
- **Visszatárolás** – Ez a funkció visszaállítja a darabjegyzék- (BOM) és receptúrasorok *Kitárolt* és *Megrendelt* állapotú készlettranzakcióit. Amikor a nyersanyag-kitárolási munka befejeződött, a sorok állapota *Kitárolt* értékre lesz állítva. Ez az állapot megakadályozza, hogy a termelési rendelést visszaállítsák *Létrehozva* állapotúvá. Ebben az esetben a *Kitárolás* funkcióval visszaállíthatja a tranzakciókat a *Kitárolt* állapotból, majd visszaállíthatja a termelési rendelést *Létrehozva* állapotra.
- **Leállítás** – Ez a funkció **Leállított** jelölőt állít be a termelési rendelésen, hogy megakadályozza a rendelés állapotfrissítését. A **Leállított** jelző a gyártási rendelés részleteinek **Raktár** gyorslapján található.

> [!NOTE]
>
> - A gombok csak akkor láthatók, ha a gyártási rendelést a raktározási folyamatokhoz engedélyezett cikkekhez hozták létre.
> - A **Leállítás** csoport csak a gyártási rendelés részleteinek Művelet panelének **Raktár** lapján látható. Nem látható a **Termelési rendelések** listaoldalának **Raktár** gyorslapján.
