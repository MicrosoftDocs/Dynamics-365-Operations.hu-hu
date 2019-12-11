---
title: Videólejátszó modul
description: Ez a témakör a videólejátszó modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 32504351f712c83ba8f593c17d2e51c532374311
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785329"
---
# <a name="video-player-module"></a>Videólejátszó modul

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör a videólejátszó modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A videólejátszó modul a videólejátszás támogatására szolgál. Két videólejátszó modul található az áruházi kezdőkészletben: a háttérvideó-lejátszó modul és a videólejátszó modul. Mindkét lejátszó támogatja az .mp4 médiatípust.

## <a name="ambient-video-player-module"></a>Háttérvideó-lejátszó modul

A háttérvideó-lejátszó modul támogatja a rövid tájékoztató videókat. Ezt kell használni az öt másodpercnél rövidebb videók esetében. Ez a lejátszó korlátozott videólejátszási képességeket támogat, például a lejátszást és a szüneteltetést.

### <a name="examples-of-ambient-video-player-modules-in-e-commerce"></a>Példák az e-kereskedelem háttérvideó-lejátszó moduljaira

- Rövid tájékoztató videók, amelyek új termékekre hívják fel a figyelmet a kezdőlapon
- A termék jellemzőit kiemelő rövid tájékoztató videók a termék részletes lapján

### <a name="ambient-video-player-module-properties"></a>Háttérvideó-lejátszó modul tulajdonságai

| Tulajdonság neve     | Érték                 | Leírás |
|-------------------|-----------------------|-------------|
| Automatikus lejátszás          | **Igaz** vagy **Hamis** | Ha **Igaz** értékre van beállítva, akkor a program automatikusan lejátssza a videót. |
| Elnémítás              | **Igaz** vagy **Hamis** | Ha **Igaz** értékre van beállítva, akkor a hang le van némítva. Ennél a lejátszónál az alapértelmezett érték **Igaz**. A Google Chrome böngészőben alapértelmezés szerint az automatikusan lejátszott videók némítva vannak, és a hang lejátszása csak akkor történik meg, ha a felhasználó manuálisan játssza le a videót. |
| Ciklus              | **Igaz** vagy **Hamis** | Ha **Igaz** értékre van beállítva, akkor a program a videót ismétlődő hurokban játssza le. |
| Média             |  Videófájl elérési útja és neve | A videólejátszó által lejátszott videófájl. |
| Lejátszási vezérlőelemek | **Igaz** vagy **Hamis** | Ha **Igaz** értékre van állítva, akkor egy lejátszás/szünet gomb jelenik meg a videón. Ha **Hamis**értékre van beállítva, akkor a lejátszás/szünet gomb nem jelenik meg, de a felhasználók továbbra is szüneteltethetik a videót a billentyűzet segítségével. |

## <a name="video-player-module"></a>Videólejátszó modul

A videólejátszó modul egy e-kereskedelmi webhelyről származó videók bemutatására használható. Támogatja az összes lejátszási funkciót, például a lejátszást, szüneteltetést, teljes méretű módot és a feliratokat. A videólejátszó modul a Microsoft akadálymentesítési szabványoknak való megfelelés érdekében támogatja a feliratok testreszabását is. Testreszabhatja például a betűméretet és a háttérszínt.

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
| Lejátszási vezérlőelemek     | **Igaz** vagy **Hamis**               | Ha **Igaz** értékre van állítva, akkor egy lejátszás/szünet gomb jelenik meg a videón. Ha **Hamis**értékre van beállítva, akkor a lejátszás/szünet gomb nem jelenik meg, de a felhasználók továbbra is szüneteltethetik a videót a billentyűzet segítségével. |
| Teljes képernyős lejátszás       | **Igaz** vagy **Hamis**               | Ha **Igaz** értékre van beállítva, akkor a program a videót teljes képernyős üzemmódban játssza le. |
| Vezérlőelemek              | **Igaz** vagy **Hamis**               | Ha **Igaz** értékre van beállítva, akkor az összes vezérlőelem látható. Ezek közé a vezérlőelemek közé tartozik a lejátszás és szünet gomb, a folyamatjelző és a feliratok. |
| Poszter keretének elrejtése     | **Igaz** vagy **Hamis**               | A videó poszterkerettel jelenhet meg. Ha a tulajdonság értéke **Igaz**, akkor a program elrejti a poszterkeretet. |
| Maszk szintje            | **0** és **100** közötti szám | A stílus módosításához a videóra alkalmazott maszk. |
| Teljes képernyős ikon stílusa | **Négyzet** vagy **Nyíl**             | A videólejátszóban megjelenített teljes képernyős ikon stílusa. |

## <a name="add-a-video-player-module-to-a-page"></a>Videólejátszó modul hozzáadása egy laphoz

A videólejátszó modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Hozzon létre egy **videólejátszó sablon** nevű lapsablont.
1. Az alapértelmezett lap **Fő** helyén adjon hozzá egy tárolómodult.
1. A tárolómodulban adja hozzá a videólejátszó és háttérvideó-lejátszó modulokat.
1. Adja be a sablont és tegye közzé.
1. A most létrehozott videólejátszó sablon használatával hozzon létre egy **videólejátszó lap** nevű lapot.
1. Az új lap **Fő** helyén adjon hozzá egy háttérvideó-lejátszó modult.
1. A háttérvideó-lejátszó modul beállításaiban nyissa meg a **Média** elemet, és töltsön fel egy videófájlt. Az **Automatikus lejátszás**, **Hurok** és egyéb tulajdonságokat igényei szerint módosíthatja.
1. Mentse a lapot, és tekintse meg az előnézetét.
1. Az új lap **Fő** helyén adjon hozzá egy videólejátszó modult.
1. A videólejátszó modul beállításaiban nyissa meg a **Média** elemet, és töltsön fel egy videófájlt.
1. Mentse a lapot, és tekintse meg az előnézetét. A lapon mindkét videómodulnak látszania kell. A további beállítások módosításával testreszabhatja az egyes modulok viselkedését.
1. Adja be a lapot, és tegye közzé.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Figyelmeztetési modul](add-alert.md)

[Forgótármodul](add-carousel.md)

[Tartalomgazdag blokkmodul](add-content-rich-block.md)

[Tartalomelhelyezési modul](add-content-placement-modules.md)

[Funkciómodul](add-feature-module.md)

[Főképmodul](add-hero-module.md)
