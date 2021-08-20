---
title: Az adó nincs kiszámítva, vagy az adó összege nulla
description: Ez a témakör olyan hibaelhárítási információkat tartalmaz, amelyek segíthetnek abban az esetben, ha az adó összege 0 (nulla), vagy ha az adó nincs kiszámítva.
author: shtao
ms.date: 04/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 45aa5931b5d958dd32bd165b414957fa7b366d077cef67621221ce19b56b67d8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772803"
---
# <a name="tax-isnt-calculated-or-the-tax-amount-is-zero"></a>Az adó nincs kiszámítva, vagy az adó összege nulla

[!include [banner](../includes/banner.md)]

Előfordulhat, hogy egy tranzakció sorösszege nem 0 (nulla), de vagy nincs kiszámítva adó, vagy a számított adóösszeg 0. A probléma elhárításához igény szerint kövesse az alábbi szakaszok lépéseit.

## <a name="verify-that-tax-codes-are-correctly-selected-by-the-transaction"></a>Annak ellenőrzése, hogy a tranzakció helyesen választotta-e ki az adókódokat

Ha a tranzakció nem a megfelelő adókódokat választja ki, vagy nem választ adókódokat, akkor az adók számítása nem történik meg. Kövesse az alábbi lépéseket annak ellenőrzéséhez, hogy a tranzakció helyesen választotta-e ki az adókódokat. 

1. A tranzakciósorban a **Sor részletei** gyorslapon a **Beállítás** lapon, az **Áfa** szakaszban ellenőrizze, hogy a megfelelő áfacsoportok vannak-e kiválasztva a **Cikk áfacsoportja** és az **Áfacsoport** mezőkben. Ha nem a megfelelő adócsoportok vannak kiválasztva, válassza ki őket.

    [![Cikkáfacsoportok és Áfacsoportok mezők.](./media/tax-not-calculated-tax-amount-zero-Picture1.png)](./media/tax-not-calculated-tax-amount-zero-Picture1.png)

2. Ugorjon az **Adó** \> **Közvetett adók** \> **Áfa** \> **Áfakódcsoportok** pontra.
3. Válassza ki a megfelelő áfacsoportot, majd a **Beállítás** gyorslapon jegyezze fel az áfakódot az **Áfakód** mezőben.

    [![Áfacsoportok lap.](./media/tax-not-calculated-tax-amount-zero-Picture2.png)](./media/tax-not-calculated-tax-amount-zero-Picture2.png)

4. Ugorjon az **Adó** \> **Közvetett adók** \> **Áfa** \> **Áfacsoportok** pontra.
5. Válassza ki a megfelelő cikkáfa-csoportot, majd a **Beállítás** gyorslapon ellenőrizze, hogy az **Áfakód mezőben** az áfakód megegyezik-e az áfacsoport áfakódjával.

    [![Cikkáfa-csoportok lap.](./media/tax-not-calculated-tax-amount-zero-Picture3.png)](./media/tax-not-calculated-tax-amount-zero-Picture3.png)

6. Ha az adókódok nem egyeznek meg, frissítse valamelyik csoport áfakódját.

## <a name="verify-that-the-selected-tax-codes-arent-exempt-and-that-they-have-the-correct-tax-rate-value"></a>Győződjön meg róla, hogy a kiválasztott áfakódok nem adómentesek, és helyes az adókulcsuk

Ha az adókódok adómentesek, vagy ha az adókulcs 0 (nulla), az adószámítás eredménye 0 lesz. A következő lépések szerint adhatja meg, hogy a kiválasztott áfakódok adómentesek-e, és ellenőrizze, hogy a megfelelő adókulcs van-e alkalmazva rájuk.

1. Ugorjon az **Adó** \> **Közvetett adók** \> **Áfa** \> **Áfakódcsoportok** pontra.
2. Válassza ki a megfelelő áfacsoportot, majd a **Beállítás** gyorslistában ellenőrizze, hogy nincs-e beállítva a **Mentesség** jelölőnégyzet. Ha be van jelölve, törölje.

    [![Mentesség jelölőnégyzet az Áfacsoportok lapon.](./media/tax-not-calculated-tax-amount-zero-Picture4.png)](./media/tax-not-calculated-tax-amount-zero-Picture4.png)

3. Ugrás az **Adó** \> **Közvetett adók** \> **Áfa** \> **Áfakódok** pontra.
4. Válassza ki a megfelelő áfakódot, majd ellenőrizze, hogy az **Érték** mezőben megadott adókulcs nem 0 (nulla). Ha 0, frissítse a mezőt úgy, hogy a megfelelő adókulcs legyen a mezőben.

    [![Érték mező az Áfakód-értékek lapon.](./media/tax-not-calculated-tax-amount-zero-Picture5.png)](./media/tax-not-calculated-tax-amount-zero-Picture5.png)

## <a name="determine-whether-zero-is-the-correct-tax-amount"></a>Annak meghatározása, hogy a nulla-e a helyes adóösszeg

Bizonyos helyzetekben 0 (nulla) adóösszeg helyes. A következő lépések alapján határozza meg, hogy a 0 helyes adóösszeg-e a tranzakcióhoz.

1. Menjen a **Főkönyv** \> **Főkönyv beállítás** \> **Főkönyv paraméterei** pontra.
2. Az **Áfa** lap **Számítás módja** mezőjében ellenőrizze, hogy az **Összesen** ki van-e választva.

    [![Számítási módszer mező a Főkönyvi paraméterek oldalon.](./media/tax-not-calculated-tax-amount-zero-Picture6.png)](./media/tax-not-calculated-tax-amount-zero-Picture6.png)

3. Ugrás az **Adó** \> **Közvetett adók** \> **Áfa** \> **Áfakódok** pontra.
4. Válassza ki a megfelelő áfakódot, válassza a **Számítás** \> **Számítás alapja** lehetőséget, és ellenőrizze, hogy a számítás alapja a **Számlaegyenleg nettó összege** vagy **Egyéb áfaösszegeket tartalmazó számlaösszeg**. A további tudnivalókat lásd a [Egyéb áfaösszegeket tartalmazó számlaösszeg](marginal-base-field.md#invoice-total-incl-other-sales-tax-amounts) részben.
5. Ha a 2. és a 4. lépésben helyes értékek vannak beállítva, döntse el, hogy a tranzakció teljes összege 0-e (nulla). Ha a teljes összeg 0, a várt eredmény a 0 adóösszeg. Mivel az adószámítás a számlaegyenleg teljes összegére épül, és ez az összeg nem soronként van lebontva, az adószámítás után minden sorhoz 0 összeget rendel hozzá a program.

## <a name="determine-whether-customization-exists"></a>Annak meghatározása, hogy létezik-e testreszabás

Ha az előző szakaszokban már befejezte a lépéseket, de nem találta meg a problémát, határozza meg, hogy van-e testreszabás. Ha nem létezik testreszabás, hozzon létre egy Microsoft szolgáltatáskérést további segítségért.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
