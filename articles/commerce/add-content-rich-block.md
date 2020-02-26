---
title: Szövegblokk modul
description: Ez a témakör a szövegblokkmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: fc5b2fa35633b1ce7f7ffefacec318e14fa8db3f
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025597"
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

## <a name="text-block-module-properties"></a>Szövegblokk modul tulajdonságai

| Tulajdonság neve     | Value                                            | Leírás |
|-------------------|--------------------------------------------------|-------------|
| Rich Text         | Rich Text                                        | Bekezdés szövege. A program néhány alapvető rich text képességet támogat, mint például a félkövér, az aláhúzott és a dőlt szöveg. |
| Egyéni osztály neve | Az egymásra épülő stílusalapok (CSS)-osztály neve        | Annak az egyéni CSS osztálynak a neve, amely a fejlesztő számára biztosítja a modul formátumát. Az osztálynevet a témacsomagban kell megadni. |
| Betűméret         | **Kis**, **közepes**, **Nagy**vagy **Nagyon nagy** | A tartalom betűmérete. |

## <a name="add-a-text-block-module-to-a-page"></a>A szövegblokkmodul hozzáadása a laphoz

A szövegblokkmodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Hozzon létre egy **Tartalomsablon** nevű oldalsablont. 
1. Adja hozzá a **Törzs** tárolóhelyen az **Alapértelmezett oldal** modult.
1. Fejezze be a sablon szerkesztését, és tegye közzé.
1. A most létrehozott tartalomsablon használatával hozzon létre egy **Tartalomlap** nevű lapot.
1. Az új lap **Fő** helyén adjon hozzá egy tárolómodult.
1. A tárolómodul tulajdonságlapján a **Szélesség** tulajdonságot állítsa **Tároló kitöltése** értékre.
1. Vegyen fel egy szövegblokkmodult a tárolómodulba. 
1. A szövegblokkmodul tulajdonságlapján adja meg a **Multimédiás szöveg** mező szövegét.
1. Fejezze be a lap szerkesztését, és tegye közzé.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Promóciós szalagcím modul](add-alert.md)

[Forgótármodul](add-carousel.md)

[Tartalomblokk modul](add-hero-module.md)

[Videólejátszó modul](add-video-player.md)

