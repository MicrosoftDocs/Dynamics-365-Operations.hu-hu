---
title: A rakománysorok súlymezői nem egyeznek meg a rakomány súlymezőivel
description: A rakománysorok súlymezői nem egyeznek meg a rakomány súlymezőivel
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSShipmentDetails_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 639b82a9d46b74f179d6904d2c3b8e7dfb813b58
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924351"
---
# <a name="the-weight-fields-on-load-lines-dont-match-the-weight-fields-on-the-load"></a>A rakománysorok súlymezői nem egyeznek meg a rakomány súlymezőivel

Hibakódok: WHSLoadWeightOnLinesDoNotMatchLoadWarning

## <a name="symptoms"></a>Tünetek

A rendszer a következő hibaüzenetet jeleníti meg:

> A rakománysorok súlymezői nem egyeznek meg a(z) %1 rakomány súlymezőivel. Futtassa a Raktári rakománysúly konzisztencia ellenőrzését a súlymezők újraszámítása érdekében.

## <a name="cause"></a>Ok

A **Nettó súly** és a **Tárasúly** mező *0* (nulla) értékre van állítva a rakománysoron. A súlymezők azonban nem *0*-ra vannak állítva a termék súlymérése során. Ha a rakománysoron nincsenek beállítva súlymezők, a rakománysor mennyiségének javításai helytelen tömegszámítást okozhatnak a rakományon. Ez a hiba akkor fordulhat elő, ha a rakománysor létrehozása óta módosultak a termék súlyai.

## <a name="resolution"></a>Felbontás

Rakománysor létrehozásakor a termék súlymezőit alapértelmezetten meg vannak adva. Ha a súly nulla, akkor a *Raktári rakománysúly konzisztencia ellenőrzése* funkcióval újraszámíthatja a súlyt.

1. Nyissa meg a **Rendszeradminisztráció \> Ismétlődő feladatok \> Adatbázis \> Konzisztenciaellenőrzés** lehetőségét.
1. A **Konzisztencia ellenőrzése** párbeszédpanelen állítsa a **Modul** mezőt *Raktárkezelés* beállításra.
1. Állítsa be a **Ellenőrzés/javítás** mezőt *Hiba javítása* értékre.
1. A jelölőnégyzetek listájában jelölje be a **Raktári rakománysúly konzisztencia ellenőrzése** jelölőnégyzetet, és győződjön meg arról, hogy csak ennek a jelölőnégyzetnek a sora van kijelölve.
1. A jelölőnégyzetek listájának tetején válassza a három pont gombot (**...**), majd válassza a **Párbeszéd** elemet a menüben.
1. A **Raktári rakománysúly konzisztencia ellenőrzése** jelölőnégyzetben a következő mezők beállításével adhatja meg, hogy a konzisztencia-ellenőrzésnél mely feltételeket kell ellenőrizni:

    - **Rakományazonosító:** Rakományazonosító megadása. Hagyja üresen, ha minden rakományazonosítót ellenőrizni kell.
    - **Cikkszám:** Cikkszám megadása. Hagyja üresen, ha minden cikket ellenőrizni kell.
    - **Rakományok súlyának újraszámítása mindig:** Állítsa Ezt a lehetőséget *Igen* beállításra.
    - **A rakománysorok súlyának felülírásának engedélyezése:** Állítsa ezt a beállítást *Igen* beállításra.

1. Az **OK** gomb kiválasztásával zárja be a **Raktári rakománysúly konzisztencia ellenőrzése** párbeszédpanelt.
1. Válassza ki a három pont gombot, majd válassza a menü **Végrehajtás** parancsát.

A rendszer a megadott feltételek alapján újraszámja a súlyt. A konzisztencia-ellenőrzés eredményének megtekintéséhez válassza az **Üzenet részletei** hivatkozást.
