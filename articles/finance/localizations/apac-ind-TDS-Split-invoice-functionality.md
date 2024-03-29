---
title: Számla felosztása funkció
description: Ez a témakör leírja a számlák szállítási cím és adószámlaszám (TAN) szerinti felosztásának beállításait és funkcióit.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 7bbeb94429c2c69b7b8ea3089390db676a021b80
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874432"
---
# <a name="split-invoice-functionality"></a>Számla felosztása funkció

[!include [banner](../includes/banner.md)]

Ez a témakör leírja a számlák szállítási cím és adószámlaszám (TAN) szerinti felosztásának beállításait és funkcióit.

A **Kötelezettségek paraméterek** oldalon, az **Általános** lapon válassza ki a **Termék nyugta** vagy a **Számla** jelölőnégyzetet a termék nyugtának vagy számlának a **Beszerzési rendelés** oldalán található különböző szállítási címekkel és TAN-ekkel rendelkező feladásához és felosztásához. A feladott számlát ezután felosztjuk a szállítási cím és a TAN szerint.

Az **Összesített módosítás** lapon, a **Megosztás a következő szerint** gyorslapon, a **Szállítási információk** sorban állítsa be a **Visszaigazolás**, **Átvételi lista**, **Szállítólevél** vagy **Számla** opciót **Igen** értékre a visszaigazolás, a kitárolási lista, a szállítólevél vagy a számla feladásához és felosztásához, ahol az **Értékesítési rendelés** oldalon különböző szállítási címek és TAN-ok vannak meghatározva. A számlát ezután felosztjuk a szállítási cím, majd TAN szerint.

> [!IMPORTANT]
> - Ha a **Szállítási adatok** beállításának értéke **Igen**, a számla egyetlen számlaként kerül könyvelésre. Nem történik számlamegosztás.
> - Ha olyan szállítólevelet szeretne felosztani és könyvelni, ahol a számlasorok eltérő szállítási címmel és TAN-nel rendelkeznek, a **Szállítólevél** opciót be kell állítania a **Szállítási információk** elemhez **Igen** beállításra.
> - Ha olyan számlát szeretne felosztani és könyvelni, ahol a számlasorok eltérő szállítási címmel és TAN-nel rendelkeznek, a **Számla** opciót be kell állítania a **Szállítási információk** elemhez **Igen** beállításra.
> - Ha olyan számlát szeretne felosztani és könyvelni, ahol a számlasorok eltérő szállítási címmel, de ugyanazzal TAN-nel rendelkeznek, a **Számla** opciót be kell állítania a **Szállítási információk** elemhez **Nem** beállításra. A számlát ezután felosztjuk a szállítási cím szerint.

## <a name="example"></a>Példa

Ebben a példában a **Szállítási információk** **Számla** opciója a **Kötelezettségek paraméterek** oldal **Összegzés frissítése** lapján **Igen**-re van állítva. A beszerzési számla a következő beállítással rendelkezik a szállítási címekre és a TAN-ekre a sorokon:

- **1. cikksor:** Szállítási cím 1, TAN-ABCD12345A
- **2. cikksor:** Szállítási cím 1, TAN-ABCD12345A
- **3. cikksor:** Szállítási cím 2, TAN-ABCE12345B
- **4. cikksor:** Szállítási cím 3, TAN-ABCD12345A

Ebben az esetben az eredeti számlát két számlára osztjuk fel, és a következő módon könyveljük:

- Az 1. számla az 1. és a 2. cikksorhoz kerül könyvelésre, mivel mindkét sor szállítási címe és TAN-je azonos.
- A 2. számla a 3. cikksorhoz kerül feladásra.
- A 3. számla a 4. cikksorhoz kerül feladásra.
