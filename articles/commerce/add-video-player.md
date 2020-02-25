---
title: Videólejátszó modul
description: Ez a témakör a videólejátszó modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e94658eed12b12d6666e63d2c06b86646c81a120
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025648"
---
# <a name="video-player-module"></a>Videólejátszó modul


[!include [banner](includes/banner.md)]

Ez a témakör a videólejátszó modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A videólejátszó modul a videólejátszás támogatására szolgál. A tartalmat bármilyen oldalra felveheti, feltéve, hogy a videotartalom feltöltése a tartalomkezelő rendszerben (CMS) történik. A videolejátszó modul támogatja az .mp4 média típusát.

## <a name="video-player-module"></a>Videólejátszó modul

A videólejátszó modul egy e-kereskedelmi webhelyről származó videók bemutatására használható. Támogatja az összes lejátszási funkciót, például a lejátszást, szüneteltetést, teljes méretű módot, audioleírásokat és a feliratokat. A videólejátszó modul a Microsoft akadálymentesítési szabványoknak való megfelelés érdekében támogatja a feliratok testreszabását is. Testreszabhatja például a betűméretet és a háttérszínt.

A videólejátszó modul támogatja a másodlagos hangsávot is. Videó CMS-be való feltöltése esetén másodlagos hangsávot is fel lehet tölteni. A videólejátszó modul lejátszhatja a másodlagos hangsávot, ha a felhasználó kiválasztja azt.

### <a name="examples-of-video-player-modules-in-e-commerce"></a>Példák az e-kereskedelem videólejátszó moduljaira

- Tájékoztató videók a termék részletes lapjain vagy marketinglapjain
- Promóciós videók vagy irányelvekkel kapcsolatos videók bármelyik marketinglapon
- A termék jellemzőit bemutató marketingvideók a termék részletes lapjain vagy marketinglapokon

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

1. Hozzon létre egy **videólejátszó sablon** nevű lapsablont.
1. Az alapértelmezett lap **Fő** helyén adjon hozzá egy tárolómodult.
1. A tárolómodulban adja hozzá a videólejátszó és háttérvideó-lejátszó modulokat.
1. Fejezze be a sablon szerkesztését, és tegye közzé.
1. A létrehozott videólejátszó sablon használatával hozzon létre egy **videólejátszó lap** nevű lapot.
1. Az új lap **Fő** helyén adjon hozzá egy videólejátszó modult.
1. A videolejátszó modul tulajdonságlapján válassza a **Videó hozzáadása** elemet.
1. A **Médiaválasztó** párbeszédablakon válasszon egy videót, majd válassza az **Új médiaelem feltöltése** elemet.
1. Mentse a lapot, és tekintse meg az előnézetét. A lapon a videómodulnak látszania kell. A további beállítások módosításával testreszabhatja a modul viselkedését.
1. Fejezze be a lap szerkesztését, és tegye közzé.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Promóciós szalagcím modul](add-alert.md)

[Forgótármodul](add-carousel.md)

[Szövegblokk modul](add-content-rich-block.md)

[Tartalomblokk modul](add-hero-module.md)
