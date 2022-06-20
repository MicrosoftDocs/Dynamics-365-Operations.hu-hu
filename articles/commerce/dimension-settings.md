---
title: Megjelenítési beállítások alkalmazása termékdimenziókra
description: Ez a témakör leírja a termékdimenziók megjelenítési beállításait, és bemutatja, hogyan lehet azokat alkalmazni a termékdimenziókban Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: d7575e205a9732259b00e424f66eeadfe8c659ee
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899175"
---
# <a name="apply-display-settings-for-product-dimensions"></a>Megjelenítési beállítások alkalmazása termékdimenziókra

[!include [banner](includes/banner.md)]


Ez a témakör leírja a termékdimenziók megjelenítési beállításait, és bemutatja, hogyan lehet azokat alkalmazni a termékdimenziókban Microsoft Dynamics 365 Commerce.

A Dynamics 365 Commerce támogatja a termékváltozatok megkülönböztetésére szolgáló méret-, stílus- és színdimenziókat. A dimenziók jellemzően szöveges értékként jelennek meg (például méretek esetén „Kicsi”, „Közepes” vagy „Nagy”; vagy színek esetén „Fekete” vagy „Barna”). Ha viszont egy termék számos változatot támogat, akkor nehéz lehet tallózással megkeresni a termékváltozatokat, mivel az egyes változatok képének megtekintéséhez több beállításra van szükség. A termékváltozatok közötti tallózás megkönnyítése érdekében a Commerce 10.0.20-as kiadása képek és hexadecimális (hex) kódok használatával, palettaként jeleníti meg a dimenziókat.

A Commerce webhelykészítőjében a dimenzióbeállítások a **Webhelybeállítások \> Bővítmények \> Dimenzióbeállítások** részen adhatók meg. Az alábbi ábra a webhelyszerkesztőn belüli dimenzióbeállításokra ad példát.

![Példa a Commerce webhelyszerkesztőjének webhelybeállításaira.](./dev-itpro/media/swatch_site_settings.PNG)

Két dimenzióbeállítás használható:

- **Dimenziók megjelenítése képként** – adja meg, hogy melyik dimenziók jelenjenek meg palettaként az e-kereskedelmi webhelyek oldalain, például a termékek részleteit tartalmazó oldalakon (PDP) vagy a keresési eredmények listaoldalán. A szín-, a méret- és a stílusdimenziók bármely kombinációja megjeleníthető palettaként. Ha egy dimenziót kiválaszt palettaként való megjelenítésre, a Commerce-modul renderelése megkeresi a hecadecimális kódú paletta megfelelő konfigurációját. Ha nincs konfigurálva hexadecimális kód, a rendszerlogika egy kép-URL palettájának konfigurációját fogja keresni. Ha sem hexadecimális kód, sem kép-URL nincs konfigurálva, akkor szöveg jelenik meg.

    Az alábbi képen olyan példa látható, ahol egy e-kereskedelmi webhelyen PDP szín- és méretpaletták vannak. Ebben a példában a szín dimenzióhoz egy hexadecimális kód van beállítva. Ennek megfelelően a paletták színekként jelennek meg. A méret dimenzióhoz viszont sem hexadecimális kód, sem kép-URL nincs beállítva. Ebből következően szöveg jelenik meg.

    ![Példa, amelyben egy termék részleteit tartalmazó e-kereskedelmi oldalon palettaként jelenik meg a színdimenzió.](./dev-itpro/media/swatch_pdp.png)

- **Termékkártyán megjelenítendő dimenziók** – adja meg, hogy melyik dimenziók jelenjenek meg a listákban és a listaoldalakon megjelenő termékkártyákban. Egy termékkártyán csak akkor jelenhet meg egy dimenzió, ha ezt a beállítást engedélyezi az adott dimenziónál. A **Dimenziók megjelenítése képként** beállítást is engedélyezni kell. A paletta termékkártyákon való kiválasztására szolgáló viselkedés a színdimenzióra van optimalizálva. Más dimenziók esetén szükség lehet egy nézetbővítményre a palettakiválasztási viselkedés testreszabásához.

    A következő ábrán lévő példán egy e-kereskedelmi webhely listaoldalán színpalettákat tartalmazó termékkártyák vannak.

    ![Példa, amelyben egy e-kereskedelmi listaoldalon palettaként jelenik meg a színdimenzió.](./dev-itpro/media/swatch_searchresults.PNG)

További információ arról, hogyan állítható be, hogy a termékdimenziók palettaként jelenjenek meg a webhely oldalain: [Termékdimenzió értékeinek konfigurálása palettaként való megjelenítésre](./dev-itpro/dimensions-swatch.md).

## <a name="additional-resources"></a>További erőforrások

[Modultár áttekintése](starter-kit-overview.md)

[Keresési eredmények modul](search-result-module.md)

[Vásárlásmező-modul](add-buy-box.md)

[Termékdimenzió értékeinek konfigurálása palettaként való megjelenítésre](./dev-itpro/dimensions-swatch.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
