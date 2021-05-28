---
title: Szállítási konténerek
description: Ez a témakör azt ismerteti, hogyan lehet szállítókonténereket beállítani a Partraszállítási költség modulhoz.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMContainerTypeTable, ITMContainerTable, ITMContainerUnitTypeTable, ITMRefrigerationTypeTable, ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 8f86f3603b64093214bb7cf7d165ba0fc2229ca3
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021540"
---
# <a name="shipping-container-setup"></a>Szállítókonténerek beállítása

[!include [banner](../../includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet szállítókonténereket beállítani a **Partraszállítási költség** modulhoz.

## <a name="set-up-shipping-container-types"></a><a id="shipping-container-types"></a>Szállítókonténer-típusok beállítása

A Szállítókonténer-típusok lehetőség beállítása határozza meg a szállítás és hajóút során használható szállítókonténerek típusait.

A szállítókonténer-típusokkal a **Partraszállítási költség \> Konténerek beállítása \> Szállítókonténer-típusok** részben dolgozhat. Itt megtekintheti, hozzáadhatja és eltávolíthatja a konténertípusok rekordjait. Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Szállítási konténer típusa | Adja meg a szállítókonténer-típus egyedi azonosító nevét/számát. |
| Leírás | Adja meg a szállítókonténer-típus leírását. |
| Térfogat | Adja meg az ilyen típusú szállítókonténer esetében engedélyezett maximális térfogatot. |
| Betűvastagság | Adja meg az ilyen típusú szállítókonténer esetében engedélyezett maximális tömeget. |
| Visszaküldhető | Adja meg, hogy az ilyen típusú szállítókonténerek visszaküldhetők-e a szállítónak a hajóút után. Ha ez a beállítás *Igen*, az ilyen típusú szállítókonténerek származási kikötőbe való visszaszállítására további költségek vonatkozhatnak. |

## <a name="set-up-shipping-containers"></a>A szállítókonténerek beállítása

A szállítókonténer-rekordok segítségével azonosíthatja a hajúutak során használt konténereket. Hajóút létrehozásakor az itt megadott összes szállítókonténer-rekord listájában kiválaszthat egy konkrét konténert. Ez a funkció különösen akkor hasznos, ha a vállalatnak saját szállítókonténerei vannak.

Nem kell megadnia a szállítókonténer számát az egyszer használatos szállítókonténerek esetében. Hajóút létrehozásakor ehelyett hozzáadhatja a szállítókonténer számát.

A szállítókonténer rekordjai csak a Partraszállítási költség pontban használatosak. Ezek nem érhetők el a szabványos **Szállításkezelés** modulban (TMS).

A szállítókonténerekkel a **Partraszállítási költség \> Konténerek beállítása \> Szállítókonténerek** részben dolgozhat. Itt megtekintheti, hozzáadhatja és eltávolíthatja a szállítókonténerek rekordjait. Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Szállítási konténer | Adja meg a szállítókonténer egyedi azonosító nevét/számát. |
| Szállítási konténer típusa | Válassza ki a szállítókonténer típusát. További tudnivalókért lásd a [Szállítókonténer-típusok beállítása](#shipping-container-types) című részt a témakör korábbi részében. |

> [!NOTE]
> - A szállítókonténer beállítása nem kötelező. Általában csak akkor használja, ha a vállalat saját szállítókonténereket használ, vagy gyakran használja fel újra ugyanazokat a szállítókonténereket.
> - A szállítókonténerek számához a rendszer nem számol ellenőrző számjegyeket.

## <a name="set-up-unit-types"></a><a name="unit-types"></a>Egységtípusok beállítása

Az egységtípusok további csoportosításokat és azonosítási módszereket hoznak létre a szállítókonténerekhez. Az egységtípus rendszerint az áruk csomagolásának típusát határozza meg, ilyenek például a raklapok vagy hordók. Az egységtípust akkor választhatja ki, amikor az **Összes szállítókonténer** oldalon beállít egy konténert.

Az egységtípusok csak a Partraszállítási költség lehetőségben használatosak. Nem érhetők el a TMS-ben.

Az egységtípusokkal a **Partraszállítási költség \> Konténerek beállítása \> Egységtípusok** részben dolgozhat. Itt megtekintheti, hozzáadhatja és eltávolíthatja az egységtípusok rekordjait. Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Egységtípus | Adja meg az egységtípus egyedi azonosító nevét/számát. |
| Leírás | Az egységtípus leírása. |

## <a name="set-up-refrigeration-types"></a><a name="refrigeration-types"></a>Hűtéstípusok beállítása

A hűtéstípusok a szállítókonténerek (általában hűtött konténerek) csoportosításának és azonosításának további eszközként használhatók. A hűtéstípust akkor választhatja ki, amikor az **Összes szállítókonténer** oldalon beállít egy konténert.

A hűtéstípusokkal a **Partraszállítási költség \> Konténerek beállítása \> Hűtéstípusok** részben dolgozhat. Itt megtekintheti, hozzáadhatja és eltávolíthatja a hűtéstípusok rekordjait. Az alábbi táblázat bemutatja az egyes rekordokhoz rendelkezésre álló mezőket.

| Mező | Leírás |
|---|---|
| Hűtés típusa | Adja meg a hűtéstípus egyedi azonosító nevét/számát. |
| Leírás | Adja meg a hűtéstípus rövid leírását. |
