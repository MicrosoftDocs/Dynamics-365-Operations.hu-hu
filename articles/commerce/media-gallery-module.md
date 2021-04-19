---
title: Médiatár modul
description: Ez a témakör a médiatár modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: b0b1ec7324ff60ee7cdd01c97c8c08260bd8c947
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802815"
---
# <a name="media-gallery-module"></a>Médiagaléria modul

[!include [banner](includes/banner.md)]

Ez a témakör a médiatár modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

A médiatár modulok egy vagy több képet jelenítenek meg a galéria nézetben. A médiatár modulok támogatják a miniatűr képek vízszintes (a kép alatti sorként) vagy függőleges (a kép melletti oszlopként) elrendezését is. A médiatár modulok olyan képességeket is biztosítanak, amelyek lehetővé teszik a képek nagyítását vagy teljes képernyős módban való megtekintését. A médiatár modulban történő megjelenítéshez egy képnek a Commerce webhelykészítő médiatárában kell lennie. Jelenleg a médiatár modulok csak képeket támogatnak.

Az alapértelmezett módban a médiatár modul a termék részletes adatait tartalmazó (PDP) lapján elérhető termékazonosítót használja a termék megfelelő képeinek megjelenítéséhez. A Commerce központ alkalmazásban minden termék esetében meg kell adni a médiafájlok elérési útját. A képeket ezután a Commerce központ alkalmazásban megadott fájlelérési út alapján fel kell tölteni a webhelykészítő médiatárba. Ezek a képek a termékek és termékváltozatok minden változatát tartalmazzák. A képek webhelykészítő médiatárba történő feltöltésével kapcsolatos további tudnivalókat lásd: [Képek feltöltése](dam-upload-images.md).

Ugyanígy a médiatár modulja a képtár olyan oldalán is tárolhatja a teljesen kiválogatott képek készletét, ahol a termékazonosító vagy az oldal környezete nem tartalmaz függőséget. Ebben az esetben a képeket fel kell tölteni a webhelykészítő médiatárba, és meg kell őket határozni a webhelyszerkesztőben.

Íme néhány példa a médiatár moduljainak használatára:

- Termék képeinek PDP-ben történő renderelése
- Termék képeinek renderelése a termék marketing oldalán
- A kiválogatott képek marketing oldalon történő bemutatása, például egy galérialapon

A következő ábrán szereplő példában egy médiatár modul segítségével tekinthetők meg a PDP-n található vásárlásmezőben lévő képek.

![Példa egy termék részletei oldalon található vásárlásmezőre, amely a médiatár modul használatával hosztol termékképeket](./media/ecommerce-pdp-buybox.PNG)

## <a name="media-gallery-properties"></a>Médiatár tulajdonságok

| Tulajdonság neve | Értékek | Leírás |
|---------------|--------|-------------|
| Képforrás | **Oldalkontextus** vagy **Termékazonosító** | Az alapértelmezett érték az **Oldalkontextus**. Ha az **Oldalkontextus** ki van jelölve, akkor a modul elvárja, hogy az oldalon adja meg a termékazonosító adatait. Ha a **Termékazonosító** kivan jelölve, akkor a kép termékazonosítóját meg kell adni a **Termékazonosító** tulajdonság értéknél. Ez a funkció a Commerce 10.0.12 verzióban érhető el. |
| Termékazonosító | Egy termékazonosító | Ez a tulajdonság csak akkor használható, ha a **Kép erőforrása** tulajdonság értéke **Termékazonosító**. |
| Kép nagyítása | **Szövegköz** vagy **Tároló** | Ez a tulajdonság lehetővé teszi a felhasználó számára a médiatár modulban a nagyítást. A kép egy szövegközi, vagy akár egy különálló tárolóban, a kép mellett is nagyítható. Ez a képesség a 10.0.12-es verzióban érhető el |
| Nagyítás méretezése | Egy tizedesérték | Ez a tulajdonság a képek nagyításának nagyságrendi tényezőjét határozza meg. Ha például az értéket **2,5**-re állítjék, a képeket 2,5-szörösen nagyítják fel.|
| Teljes képernyő | **Igaz** vagy **Hamis** | Ez a tulajdonság azt határozza meg, hogy a képeket meg lehet-e teljes képernyős módban jeleníteni. Teljes képernyős módban a képeket tovább is lehet nagyíthatani, ha a nagyítási képesség be van kapcsolva. Ez a funkció a Commerce 10.0.13 verzióban érhető el. |
| Képek | Webhelykészítő médiatárból kiválasztott képek | A termékből való renderelésen kívül a képek a médiatár modulban is összeválogathatók. Ezeket a képeket a program hozzáfűzi az elérhető termékképekhez. Ez a funkció a Commerce 10.0.12 verzióban érhető el. |
| Miniatűr tájolása | **Vízszintes** vagy **Függőleges** | Ez a tulajdonság azt határozza meg, hogy a miniatűrök képei függőleges vagy vízszintes csíkban jelenjenek-e meg. |

A következő ábra egy olyan médiatár-modult mutat be, amelyben elérhetők a teljes képernyős és a nagyítási lehetőségek.

![A példa egy olyan médiatár-modult mutat be, amelyben elérhetők a teljes képernyős és a nagyítási lehetőségek](./media/ecommerce-media-zoom.png)

A következő ábra egy olyan médiatár-modult mutat be, amely válogatott képeket tartalmaz (azaz a meghatározott képek nem függnek a termékazonosítótól vagy az oldalkontextustól).

![A példa egy olyan médiatár-modult mutat be, amely válogatott képeket tartalmaz](./media/ecommerce-media-curated.PNG)

## <a name="commerce-scale-unit-interaction"></a>Commerce Scale Unit-interakció

Amikor a kép forrása a lap kontextusából származik, a PDP termékazonosítóját a képek beolvasásához használják. A médiatár-modul a termékhez tasrtozó kép elérési útját a Commerce Scale Unit alkalmazásprogramozási felületek (API-k) használatával olvassa be. A képeket ezután kiveszik a médiatárból, hogy renderelni lehessen őket a modulban.

## <a name="add-a-media-gallery-module-to-a-page"></a>A médiatár hozzáadása a laphoz

A következő lépésekkel lehet hozzáadni egy médiatár-modult egy marketing laphoz.

1. Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.
1. Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **Marketingsablon** elemet, majd válassza az **OK** gombot.
1. A **Törzs** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Alapértelmezett oldal** modult, majd kattintson az **OK** gombra.
1. Az Alapértelmezett lap **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. A **Sablon kiválasztása** párbeszédpanelen válassza ki a **Marketingsablon** sablonját. Az **Oldal neve** alatta adja meg a **Médiatár oldalt**, majd kattintson az **OK** gombra.
1. Az új oldal **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.
1. Az **Tároló** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Médiagaléria** modult, majd kattintson az **OK** gombra.
1. A médiatár modul tulajdonság lapján, a **Kép forrása** lehetőség alatt válassza a **Termékazonosító** elemet. Majd a **Termékazonosító** mezőbe írja be a termékazonosítót.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet. A termék képeit a Gyűjtemény nézetben láthatja.
1. Ahhoz, hogy csak a válogatott képeket használja, a tulajdonság ablaktáblában, a **Kép forrása** lehetőség alatt válassza a **Termékazonosító** elemet. Ezután a **Képek** lehetőségben válassza ki a **Kép hozzáadása** elemet annyiszor, amennyiszer képet szeretne hozzáadni a médiatárból.
1. Szükség szerint állítson be további tulajdonságokat, például a **Kép nagyítása**, a **Nagyítási tényező**, és a **Miniatűrök tájolása** lehetőségeket.
1. Miután befejezte, válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Vásárlásmező-modul](add-buy-box.md)

[Tárolómodul](add-container-module.md)

[Képek feltöltése](dam-upload-images.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]