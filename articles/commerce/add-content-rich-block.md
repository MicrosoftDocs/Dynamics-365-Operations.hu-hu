---
title: Szövegblokk modul
description: Ez a témakör a szövegblokkmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c6527ad00e74fa105f3873036eb56557b98b05aa
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817378"
---
# <a name="text-block-module"></a>Szövegblokk modul

[!include [banner](includes/banner.md)]

Ez a témakör a szövegblokkmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A szövegblokkmodul egy olyan modul, amely szöveges tartalom hozzáadására használatos. Ez a tartalom lehet tájékoztató vagy promóciós.

A szövegblokkmodulokat a tartalomkezelő rendszer (CMS) adatai vezérlik, és bármilyen lapra elhelyezhetők. Ezek önálló modulok, amelyek nem függnek a lap vagy egyéb modulok kontextusától.

## <a name="examples-of-text-block-modules-in-e-commerce"></a>Példák az e-Commerce szövegblokkmoduljaira

A szövegblokkmodulokat a következő módokon lehet használni:

* A termék részletes lapján a termék funkcióinak bemutatására.
* Tájékoztatás céljából bármilyen oldalon. Elmagyarázhatja például a hűségprogramok előnyeit, bemutathatja a szállítási és visszaküldési irányelveket, megválaszolhatja a gyakran feltett kérdéseket, illetve „Rólunk” tartalmat adhat meg.
* Egyéni üzeneteket vehet fel a termék részletes lapjára. (Például „Ingyenes szállítás 50 USD feletti megrendelések esetén”).
* Jogkizárásokhoz és kapcsolati adatokhoz a termék részletes lapjain, a kosár lapjain, a pénztár lapjain és egyéb lapokon (például: „A szállításra és visszaküldésre az áruház irányelvei érvényesek”).

A következő kép egy kezdőoldalon használt szövegblokk modul egy példáját jeleníti meg.

![Példa egy szövegblokk modulra](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a>Szövegblokk modul tulajdonságai

| Tulajdonság neve     | Érték                                            | Leírás |
|-------------------|--------------------------------------------------|-------------|
| Rich Text         | Rich Text                                        | Bekezdés szövege. A program néhány alapvető rich text képességet támogat, mint például a félkövér, az aláhúzott és a dőlt szöveg. |
| Egyéni osztály neve | Az egymásra épülő stílusalapok (CSS)-osztály neve        | Annak az egyéni CSS osztálynak a neve, amely a fejlesztő számára biztosítja a modul formátumát. Az osztálynevet a témacsomagban kell megadni. |
| Betűméret         | **Kis**, **közepes**, **Nagy**vagy **Nagyon nagy** | A tartalom betűmérete. |

## <a name="add-a-text-block-module-to-a-page"></a>A szövegblokkmodul hozzáadása a laphoz

A szövegblokkmodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.
1. Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **Tartalomsablon** értéket.
1. A **Törzs** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Alapértelmezett oldal** modult, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. A **Sablon kiválasztása** párbeszédpanelen válassza ki a **Tartalomsablon** sablonját. Az **Oldal neve** alatta adja meg a **Tartalom oldalt**, majd kattintson az **OK** gombra.
1. Az új oldal **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.
1. A tárolómodul tulajdonságlapján a **Szélesség** tulajdonságot állítsa **Tároló kitöltése** értékre.
1. Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Szövegblokk** modult, majd kattintson az **OK** gombra. 
1. A szövegblokkmodul tulajdonságlapján adja meg a **Multimédiás szöveg** mező szövegét.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Promóciós szalagcím modul](add-alert.md)

[Forgótármodul](add-carousel.md)

[Tartalomblokk-modul](add-hero-module.md)

[Videólejátszó modul](add-video-player.md)

