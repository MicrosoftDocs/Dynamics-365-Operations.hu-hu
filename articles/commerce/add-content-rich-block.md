---
title: Tartalomgazdag blokkmodul
description: Ez a témakör a tartalomgazdag blokkmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 27dabb425b3c9a3015ffc54ff3c0e50b7ee11749
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785421"
---
# <a name="content-rich-block-module"></a>Tartalomgazdag blokkmodul

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör a tartalomgazdag blokkmodulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A tartalomgazdag blokkmodul egy speciális tároló, amelyben egy vagy több tartalomgazdag blokkelem helyezhető el. A tartalomgazdag blokkmodulokat a lap szöveges tartalmaként lehet használni. Ez a tartalom lehet tájékoztató vagy promóciós.

A tartalomgazdag blokkmoduljait a tartalomkezelő rendszer (CMS) adatai vezérlik, és bármilyen lapra elhelyezhetők. Ezek önálló modulok, amelyek nem függnek a lap vagy egyéb modulok kontextusától.

## <a name="examples-of-content-rich-block-modules-in-e-commerce"></a>Példák az e-Commerce tartalomgazdag blokkmoduljaira

A tartalomgazdag blokkmodulokat a következő módokon lehet használni:

* A termék részletes lapján a termék funkcióinak bemutatására.
* Tájékoztatás céljából bármilyen oldalon. Elmagyarázhatja például a hűségprogramok előnyeit, bemutathatja a szállítási és visszaküldési irányelveket, megválaszolhatja a gyakran feltett kérdéseket, illetve „Rólunk” tartalmat adhat meg.
* Egyéni üzeneteket vehet fel a termék részletes lapjára. (Például „Ingyenes szállítás 50 USD feletti megrendelések esetén”).
* Jogkizárásokhoz és kapcsolati adatokhoz a termék részletes lapjain, a kosár lapjain, a pénztár lapjain és egyéb lapokon (például: „A szállításra és visszaküldésre az áruház irányelvei érvényesek”).

## <a name="content-rich-block-module-properties"></a>Tartalomgazdag blokkmodul tulajdonságai

| Tulajdonság neve     | Érték                                 | Tulajdonság |
|-------------------|---------------------------------------|----------|
| Oszlopok száma | **1** és **4** közötti szám     | A tartalomgazdag tömb oszlopainak száma. Legfeljebb négy oszlop lehet. |
| Szélesség             | **Tároló kitöltése** vagy **Képernyő kitöltése** | Ha az érték **Tároló kitöltése**, akkor a tárolóban lévő elemek a tároló szélességére korlátozódnak. Ha **Képernyő kitöltése** értékre van beállítva, akkor az elemek mérete nem korlátozódik a tároló szélességére, hanem teljes képernyős üzemmódban jelenhetnek meg. A kívánt elrendezés elérése érdekében módosíthatja az értéket. |

## <a name="content-rich-block-item-module-properties"></a>Tartalomgazdag blokkelem-modul tulajdonságai

| Tulajdonság neve | Érték          | Leírás |
|---------------|----------------|-------------|
| Bekezdés     | Bekezdés szövege | Az a szöveg, amely az egyes tartalomgazdag blokkelemeket kíséri. A program néhány alapvető rich text képességet támogat, mint például a félkövér, az aláhúzott és a dőlt szöveg. |

## <a name="add-a-content-rich-block-module-to-a-page"></a>Tartalomgazdag blokkmodul hozzáadása a laphoz

A tartalomgazdag blokkmodul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Hozzon létre egy **Tartalomsablon** nevű oldalsablont.
1. Az alapértelmezett lap **Fő** helyén adjon hozzá egy tartalomgazdag blokkmodult.
1. Adja be a sablont és tegye közzé.
1. A most létrehozott tartalomsablon használatával hozzon létre egy **Tartalomlap** nevű lapot.
1. Az új lap **Fő** helyén adjon hozzá egy tartalomgazdag blokkmodult.
1. A tartalomgazdag blokkmodul tulajdonságai között adja meg az oszlopok számának a **2** értéket.
1. A tartalomgazdag blokkmodulban válassza ki a **Modul hozzáadása** elemet, majd adjon hozzá egy tartalomgazdag blokkelemet (például **elem1**).
1. Adjon hozzá bekezdésszöveget az új tartalomgazdag blokkelemhez.
1. A tartalomgazdag blokkmodulban válassza ki a **Modul hozzáadása** elemet, majd adjon hozzá egy tartalomgazdag blokkelemet (például **elem2**).
1. Adjon hozzá bekezdésszöveget az új tartalomgazdag blokkelemhez.
1. Mentse a lapot, és tekintse meg a módosítások előnézetét. Két rich text blokkot kell látnia kétoszlopos nézetben.
1. Adja be a lapot, és tegye közzé.

> [!NOTE]
> Ha hozzáad egy harmadik tartalomgazdag blokkelemet, akkor ez a korábban hozzáadott két elem alá lesz elhelyezve. A tárolóban lévő oszlopok és cikkek számának megváltoztatásával különböző elrendezéseket érhet el a szöveges tartalomhoz.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Figyelmeztetési modul](add-alert.md)

[Forgótármodul](add-carousel.md)

[Tartalomelhelyezési modul](add-content-placement-modules.md)

[Funkciómodul](add-feature-module.md)

[Főképmodul](add-hero-module.md)

[Videólejátszó modul](add-video-player.md)

