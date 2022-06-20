---
title: Szövegterület-modul
description: Ez a témakör szövegesblokk-modulokat tartalmaz, és bemutatja, hogyan lehet őket a webhelyoldalakhoz adni Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 48714f172b12bbc10f1f682a9dec8be710748e6b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869224"
---
# <a name="text-block-module"></a>Szövegterület-modul

[!include [banner](includes/banner.md)]

Ez a témakör szövegesblokk-modulokat tartalmaz, és bemutatja, hogyan lehet őket a webhelyoldalakhoz adni Microsoft Dynamics 365 Commerce.

A szövegblokkmodul egy olyan modul, amely szöveges tartalom hozzáadására használatos. Ez a tartalom lehet tájékoztató vagy promóciós.

A szövegblokkmodulokat a tartalomkezelő rendszer (CMS) adatai vezérlik, és bármilyen lapra elhelyezhetők. Ezek önálló modulok, amelyek nem függnek a lap vagy egyéb modulok kontextusától.

## <a name="examples-of-text-block-modules-in-e-commerce"></a>Példák az e-Commerce szövegblokkmoduljaira

A szövegblokkmodulokat a következő módokon lehet használni:

* A termék részletes lapján a termék funkcióinak bemutatására.
* Tájékoztatás céljából bármilyen oldalon. Elmagyarázhatja például a hűségprogramok előnyeit, bemutathatja a szállítási és visszaküldési irányelveket, megválaszolhatja a gyakran feltett kérdéseket, illetve „Rólunk” tartalmat adhat meg.
* Egyéni üzeneteket vehet fel a termék részletes lapjára. (Például „Ingyenes szállítás 50 USD feletti megrendelések esetén”).
* Jogkizárásokhoz és kapcsolati adatokhoz a termék részletes lapjain, a kosár lapjain, a pénztár lapjain és egyéb lapokon (például: „A szállításra és visszaküldésre az áruház irányelvei érvényesek”).

A következő kép egy kezdőoldalon használt szövegblokk modul egy példáját jeleníti meg.

![Példa egy szövegterület-modulra.](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a>Szövegblokk modul tulajdonságai

| Tulajdonság neve     | Érték                                            | Leírás |
|-------------------|--------------------------------------------------|-------------|
| Rich Text         | Rich Text                                        | Bekezdés szövege. A program néhány alapvető rich text képességet támogat, mint például a félkövér, az aláhúzott és a dőlt szöveg. |
| Egyéni osztály neve | Az egymásra épülő stílusalapok (CSS)-osztály neve        | Annak az egyéni CSS osztálynak a neve, amely a fejlesztő számára biztosítja a modul formátumát. Az osztálynevet a témacsomagban kell megadni. |
| Betűméret         | **Kis**, **közepes**, **Nagy** vagy **Nagyon nagy** | A tartalom betűmérete. |

## <a name="add-a-text-block-module-to-a-page"></a>A szövegblokkmodul hozzáadása a laphoz

A szövegblokkmodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.
1. Adja meg a **Tartalomsablont az Új** sablon **párbeszédpanel Sablon** **neve listájában**.
1. Válassza ki a **három** pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget** a Törzsnél.
1. A Modulok kiválasztása párbeszédpanelen **válassza ki az Alapértelmezett** **lap modult, majd kattintson az** OK gombra **.**
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. Az Új lap **létrehozása párbeszédpanel** Lap neve **csoportban** írja **be** a Tartalom lapot, majd válassza a Tovább **gombra.**
1. Válasszon **egy sablont, válassza** ki a **Tartalomsablont**, majd válassza a Tovább **lehetőséget**.
1. Az **Elrendezés kiválasztása oldalon válasszon** egy lapelrendezést (például **rugalmas** elrendezés), majd válassza **a Tovább lehetőséget**.
1. Az Ellenőrzés **és befejezés lapon** ellenőrizze a lap konfigurációját. Ha szerkesztenie kell a lap adatait, válassza a Vissza **lehetőséget**. Ha a lap adatai helyesek, válassza a Létrehozás **lapot**. 
1. Az új **lap főbejáratában** válassza ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a** Tároló modult, majd válassza az **OK gombra.**
1. A tárolómodul tulajdonságlapján a **Szélesség** tulajdonságot állítsa **Tároló kitöltése** értékre.
1. A tárolóhelyen **válassza** ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a** Szövegblokk modult, majd válassza az **OK gombra.** 
1. A szövegblokkmodul tulajdonságlapján adja meg a **Multimédiás szöveg** mező szövegét.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Promóciós szalagcím modul](add-alert.md)

[Forgótármodul](add-carousel.md)

[Tartalomblokk-modul](add-hero-module.md)

[Videólejátszó modul](add-video-player.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
