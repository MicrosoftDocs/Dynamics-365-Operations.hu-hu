---
title: Videólejátszó modul
description: Ez a témakör a videólejátszó modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: aa1efa6ce959439c49983553edfaf247c8e8dcd5
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797407"
---
# <a name="video-player-module"></a>Videólejátszó-modul

[!include [banner](includes/banner.md)]

Ez a témakör a videólejátszó modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

A videólejátszó modul a videólejátszás támogatására szolgál. A tartalmat bármilyen oldalra felveheti, feltéve, hogy a videotartalom feltöltése a tartalomkezelő rendszerben (CMS) történik. A videolejátszó modul támogatja az .mp4 média típusát.

## <a name="video-player-module"></a>Videólejátszó modul

A videólejátszó modul egy e-kereskedelmi webhelyről származó videók bemutatására használható. Támogatja az összes lejátszási funkciót, például a lejátszást, szüneteltetést, teljes méretű módot, audioleírásokat és a feliratokat. A videólejátszó modul a Microsoft akadálymentesítési szabványoknak való megfelelés érdekében támogatja a feliratok testreszabását is. Testreszabhatja például a betűméretet és a háttérszínt.

A videólejátszó modul támogatja a másodlagos hangsávot is. Videó CMS-be való feltöltése esetén másodlagos hangsávot is fel lehet tölteni. A videólejátszó modul lejátszhatja a másodlagos hangsávot, ha a felhasználó kiválasztja azt.

### <a name="examples-of-video-player-modules-in-e-commerce"></a>Példák az e-kereskedelem videólejátszó moduljaira

- Tájékoztató videók a termék részletes lapjain vagy marketinglapjain
- Promóciós videók vagy irányelvekkel kapcsolatos videók bármelyik marketinglapon
- A termék jellemzőit bemutató marketingvideók a termék részletes lapjain vagy marketinglapokon

A következő kép egy kezdőoldalon használt videólejátszó modul egy példáját jeleníti meg.

![Példa a videólejátszó modulra](./media/ecommerce-videoplayer.PNG)

### <a name="video-player-module-properties"></a>Videólejátszó modul tulajdonságai

| Tulajdonság neve         | Érték                               | Leírás |
|-----------------------|-------------------------------------|-------------|
| Automatikus lejátszás             | **Igaz** vagy **Hamis**               | Ha **Igaz** értékre van beállítva, akkor a program automatikusan lejátssza a videót. |
| Elnémítás                  | **Igaz** vagy **Hamis**               | Ha **Igaz** értékre van beállítva, akkor a hang le van némítva. Ennél a lejátszónál az alapértelmezett érték **Hamis**. A Chrome böngészőben alapértelmezés szerint az automatikusan lejátszott videók némítva vannak, és a hang lejátszása csak akkor történik meg, ha a felhasználó manuálisan játssza le a videót. |
| Ciklus                  | **Igaz** vagy **Hamis**               | Ha **Igaz** értékre van beállítva, akkor a program a videót ismétlődő hurokban játssza le. |
| Média                 | Videófájl elérési útja és neve | A videólejátszó által lejátszott videófájl. |
| Teljes képernyős lejátszás       | **Igaz** vagy **Hamis**               | Ha **Igaz** értékre van beállítva, akkor a program a videót teljes képernyős üzemmódban játssza le. |
| Lejátszás/szüneteltetés eseményindítója    | **Igaz** vagy **Hamis**               | Ha **Igaz** értékre van állítva, akkor egy lejátszás/szünet gomb jelenik meg a videón. |
| Videolejátszó vezérlői | **Igaz** vagy **Hamis**               | Ha **Igaz** értékre van beállítva, akkor az összes videolejátszó-vezérlő látható. Ezek közé a vezérlőelemek közé tartozik a lejátszás és szünet gomb, a folyamatjelző és a feliratbeállítások. |
| Plakátkép elrejtése     | **Igaz** vagy **Hamis**               | A videó poszterkerettel jelenhet meg. Ha a tulajdonság értéke **Igaz**, akkor a program elrejti a poszterkeretet. |
| Maszk szintje            | **0** és **100** közötti szám | A stílus módosításához a videóra alkalmazott maszk. |

## <a name="add-a-video-player-module-to-a-page"></a>Videólejátszó modul hozzáadása egy laphoz

> [!NOTE] 
> A videolejátszó modul létrehozása előtt fel kell töltenie egy videót a médiatárba.

A videólejátszó modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.
1. Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **Videólejátszó sablon** elemet, majd válassza az **OK** gombot.
1. A **Törzs** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Alapértelmezett oldal** modult, majd kattintson az **OK** gombra.
1. Az **Alapértelmezett lap** modul **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.
1. Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Videólejátszó** modult, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez. 
1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. A **Sablon kiválasztása** párbeszédpanelen válassza ki a létrehozott videólejátszó-sablont. Az **Oldal neve** alatta adja meg a **Videólejátszó oldalt**, majd kattintson az **OK** gombra.
1. Az új oldal **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.
1. Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Videólejátszó** modult, majd kattintson az **OK** gombra.
1. A videolejátszó modul tulajdonságlapján válassza a **Videó hozzáadása** elemet.
1. A **Médiaválasztó** párbeszédablakon válasszon egy videót, majd válassza az **Új médiaelem feltöltése** elemet.
1. A Fájlkezelő területen jelöljön ki egy vagy videófájlt, majd válassza a **Megnyitás** lehetőséget.
1. A **Mediaelem feltöltése** párbeszédpanelen írjon be egy címet és egyéb adatokat, majd kattintson az **OK** gombra.
1. A **Médiaválasztó** párbeszédpanelen válassza a **Bezárás** elemet.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet. A lapon a videómodulnak látszania kell. A további beállítások módosításával testreszabhatja a modul viselkedését.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez. 

## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Promóciós szalagcím modul](add-alert.md)

[Forgótármodul](add-carousel.md)

[Szövegterület-modul](add-content-rich-block.md)

[Tartalomblokk modul](add-hero-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]