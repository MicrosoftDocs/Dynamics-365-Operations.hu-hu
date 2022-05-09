---
title: Bevétel-felosztási sablonok előfizetési számlázásban
description: Ez a témakör bemutatja a kötegként értékesített cikkek bevétel felosztási sablonjainak beállítását.
author: JodiChristiansen
ms.date: 04/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 5c2eb6c8e18770eb149c445f662ab7a90aad81a7
ms.sourcegitcommit: 367e323bfcfe41976e5d8aa5f5e24a279909d8ac
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/29/2022
ms.locfileid: "8660514"
---
# <a name="revenue-split-templates-in-subscription-billing"></a>Bevétel-felosztási sablonok előfizetési számlázásban

A Bevétel felosztása **sablonlapon** beállíthatja a bevétel felosztására vonatkozó sablonokat. A bevétel felosztása egy szülőcikkből áll, amely gyermekcikkeket tartalmaz. Az ilyen típusú cikkeket gyakran egyetlen cikkként vagy kötegként adják el a vevőknek.

Például a következő módon lehet létrehozni egy számítógépes elemet:

- **Szülőcikk:** előfizetési ezüst
- **Sor (gyermek) tétel:**

    - Támogatás
    - Karbantartás
    - Licenc

Szülőcikk létrehozásakor tartsa szem előtt a következő korlátozásokat:

- Egy cikk csak egyszer lehet szülőcikkként megadni.
- A szülőcikk gyermekelemként is kiválasztható ugyanabban a sablonban.
- Az érvényes sablonhoz legalább egy gyermekelem szükséges.
- Egy cikk egy kötegcikknél több gyermekcikkként is meg lehet adni.
- Minden szülő-gyermek kapcsolatnak egyedinek kell lennie.

## <a name="create-a-parent-item-that-has-child-items"></a>Szülőcikk létrehozása gyermekcikkekkel

A következő lépések szerint szülőcikkeket hozhat létre, amelyekben gyermekcikkek is vannak.

1. Válassza az **Új lehetőséget a Bevétel felosztása sablonoldalon** **·**.
1. A Szülő **cikk mezőben** válasszon ki egy szülő cikket. A **Változatszám mező** automatikusan frissül. Az érték szükség szerint megváltoztatható.
1. A Felosztási **mód mezőben** válasszon ki egy felosztási módszert.
1. Az Összetevő cikkek **listájában** válassza a Hozzáadás **lehetőséget** a gyermekelemek hozzáadásához.
1. Ha a Felosztási mód **mezőben** **a Százalék beállítást választotta, adja meg a százalékot a Százalék** mezőben **.**

    - Ha a Felosztási mód **mezőben** **az** Egyenlő összeget választotta, **a** Százalék mező automatikusan frissül, így minden cikkhez azonos százalék kerül.
    - Ha a **Változó összeg, a** Nulla **·** **szülőösszeg** vagy a Nulla összeg beállítást választotta a Felosztási **mód mezőben, a Százalék mező értéke 0 (nulla**) marad, **·** **és nem módosítható.**

1. Válassza a **Mentés** lehetőséget.

## <a name="fields"></a>Mezők

A **Bevétel felosztása sablonlap** a következő mezőket tartalmazza.

| Mező | Leírás |
|-------|-------------|
| Szülő cikk | Válasszon egy cikkszámot. Ez a cikk lesz a létrehozott kötegcikk szülőcikke. |
| Termék neve | A termék neve. |
| Felosztási mód | <p>Válassza ki a felosztási módot:</p><ul><li>**Egyenlő összeg** – a felosztási százalékokat a program automatikusan kiszámítja, és egyenlően osztja fel a sablonban található cikkek között.</li><li>**Százalék** – a felosztáshoz százalékos összeget lehet megadni. A százalékok összegének 100-nak kell lennie.</li><li>**Változó összeg** – a hozzáadott gyermek cikkek nettó összege 0 (nulla). A gyermekelemek árát tranzakciószinten kell megadni.</li><li>**Nulla összeg** – a szülőcikk megtartja egységárát és nettó összegét. Minden gyermek cikk nettó összege 0 (nulla).</li><li>**Nulla szülőösszeg** – a szülőcikk fix nettó összege 0 (nulla). A gyermekelemek a normál cikkekként kezelendők. Nem történik ellenőrzés annak ellenőrzésére, hogy a gyermekcikkek összege megegyezik-e a szülő cikk összegével.</li></ul> |
| **Összetevő cikkek** | |
| Összetevő cikk | Válasszon egy cikkszámot. Ez a cikk egy gyermekelem. |
| Változat száma | A cikk változatszámának kiválasztása. |
| Termék neve | A termék neve. |
| Százalék | <p>A foglalási százalék a mérföldkőhöz:</p><ul><li>Ha a **Felosztási mód** mező értéke **Százalék**, megadhatja a százalékos értéket.</li><li>Ha a **Felosztási mód** mező értéke **Egyenlő** összeg, a program automatikusan kiszámítja a százalékot, hogy a sablon minden cikkének azonos százalékban megjelenik a értéke.</li><li>Ha a **Felosztási** **mód mező értéke Változó** összeg, Nulla **szülőösszeg** **vagy** Nulla összeg, a százalékos érték 0 (nulla), ezért nem szerkeszthető.</li></ul><p>A mező értéke bármilyen pozitív szám lehet 0 (nulla) és 100 között. Az összes százalék összegének 100-nak kell lennie.</p> |
| Százalékarány összesen | <p>A Százalék oszlopban lévő **értékek** összege.</p><ul><li>Ha a **Felosztási mód** mező **értéke** **Egyenlő** összeg vagy Százalék, az összes százalék összegének 100-nak kell lennie.</li><li>Ha a **Felosztási mód** **mező értéke Változó** összeg, Nulla **szülőösszeg** **vagy Nulla** összeg, a teljes százalékos érték 0 (nulla).</li></ul> |

## <a name="revenue-split-on-a-sales-order"></a>Bevétel felosztása értékesítési rendelésre

A következő lépések szerint hozhat létre olyan értékesítési rendelést, amelynél be van állítva a bevétel felosztása.

1. Hozzon **létre egy értékesítési** rendelést az Értékesítési rendelés lapon.
2. A bevétel felosztása érdekében beállított cikkek sorában jelölje be **a Bevétel felosztása** jelölőnégyzetet. Ez a cikk lesz a szülő cikk. Ha a sablon már be van állítva, a gyermekelemek automatikusan megjelennek a listában.
3. Ha további gyermekcikkeket szeretne hozzáadni, **válassza** a Bevétel felosztása gyermek hozzáadása lehetőséget, majd válassza ki a hozzáadni kívánt gyermek cikket.
4. Mentse a rendelést.

## <a name="revenue-split-with-billing-schedules"></a>Bevétel felosztása számlázási ütemezésekkel

A következő lépések szerint hozhat létre olyan számlázási ütemezést, amely tartalmazza a bevétel felosztásához beállított cikket.

1. Hozzon létre **egy számlázási ütemezést a Mind/Aktív** számlázási ütemezések lapon.
2. A bevétel felosztása érdekében beállított cikkek sorában jelölje be **a Bevétel felosztása** jelölőnégyzetet. Ez a cikk lesz a szülő cikk. Ha a sablon már be van állítva, a gyermekelemek automatikusan megjelennek a listában.
3. Ha további gyermekcikkeket szeretne hozzáadni, **válassza** a Bevétel felosztása gyermek hozzáadása lehetőséget, majd válassza ki a hozzáadni kívánt gyermek cikket.
4. A számlázási ütemezéssel kapcsolatos lépések folytatása.

> [!NOTE]
> Ha a Bevétel **felosztásának** **·** **automatikus** létrehozása beállítás Az Ismétlődő szerződés számlázási paraméterei lapon Igen beállítás van megállítva, a következő műveletek fordulhatnak elő:
>
> - Ha a sorcikk szülőcikkként van beállítva a bevétel felosztási sablonjában, **a** Bevétel felosztása jelölőnégyzet automatikusan be van jelölve.
> - A gyermekelemek automatikusan megjelennek az értékesítési rendelés vagy a számlázási ütemezés sorában.
>
> Ha a Bevétel felosztásának **automatikus** létrehozása beállítás Nem **beállításra** van állítva, a viselkedés magyarázata a korábbiak szerint történik.
