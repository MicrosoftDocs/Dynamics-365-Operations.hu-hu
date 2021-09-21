---
title: Vegyes készlettípusok a kikötőkezelési profilok használatakor
description: Ahhoz, hogy a kikötőkezelési profil hatékonyan kezelje a készletkötegek vegyítését, először munkafejléc-törést kell beállítani. Ez a lap bemutatja, hogyan lehet ezt megtenni.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: cc660a2f9839e886240c97a7f60d2e264653074a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476536"
---
# <a name="inventory-types-are-being-mixed-when-using-a-dock-management-profile"></a>A készlettípusok vegyesek a kikötőkezelési profilok használatakor

## <a name="symptoms"></a>Tünetek

*Szállítmánykonszolidációs irányelveket* használ. *Kikötőkezelési profilt* állított be egy *helyprofilhoz*, de a munka létrehozásakor a készlettípusok vegyesek a végleges helyen.

## <a name="resolution"></a>Megoldás

A kikötőkezelési profilokhoz szükség van a munka előzetes felosztására. Más szóval a kikötőkezelési profil azt várja, hogy egy munkafejlécben ne legyen több betárolási hely.

Ahhoz, hogy a kikötőkezelési profil hatékonyan kezelje a készletkötegek vegyítését, munkafejléc-törést kell beállítani.

Ebben a példában a kikötőkezelési profil úgy van beállítva, hogy a **Nem vegyíthető készlettípusok** értéke *Szállítmány azonosítója*, és ehhez munkafejléc-törést állítunk be:

1. Lépjen a **Raktárkezelés \> Beállítás \> Munka \> Munkasablonok** elemre.
1. Válassza ki a szerkeszteni kívánt **Munkarendelés típusa** lehetőséget (például *Beszerzési rendelések*).
1. Válassza ki a szerkeszteni kívánt munkasablont.
1. A műveleti ablaktáblán válassza a **Lekérdezés szerkesztése** lehetőséget.
1. Nyissa meg a **Rendezés** lapot, és adjon hozzá egy sort a következő beállításokkal:
    - **Tábla** - *Ideiglenes munkatranzakciók*
    - **Származtatott tábla** - *Ideiglenes munkatranzakciók*
    - **Mező** - *Szállítmány azonosítója*
1. Válassza ki az **OK** lehetőséget.
1. Visszatér a **Munkasablonok** oldalra. A Műveleti ablaktáblán kattintson a **Munkafejléc-törések** elemre.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Jelölje be a **Mezőnév** *Szállítmány azonosítója* mezőhöz tartozó jelölőnégyzetet.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
