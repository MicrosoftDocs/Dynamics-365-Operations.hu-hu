---
title: Termékdimenzió értékeinek konfigurálása palettaként való megjelenítésre
description: Ez a témakör azt tekinti át, hogyan konfigurálhatók a termékdimenzió értékei palettaként a Microsoft Dynamics 365 Commerce-központban.
author: anupamar-ms
ms.date: 05/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-09-20
ms.dyn365.ops.version: Retail 10.0.20 update
ms.openlocfilehash: 513ec2f48a3c7c81a41fd64a9752067d12eb4ec8
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6353862"
---
# <a name="configure-product-dimension-values-to-appear-as-swatches"></a>Termékdimenzió értékeinek konfigurálása palettaként való megjelenítésre

[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

Ez a témakör azt tekinti át, hogyan konfigurálhatók a termékdimenzió értékei palettaként a Microsoft Dynamics 365 Commerce-központban. További információ a termékdimenziókról: [Termékdimenziók](../../supply-chain/pim/product-dimensions.md).

A Dynamics 365 Commerce támogatja a termékváltozatok megjelenítésére szolgáló méret-, stílus- és színdimenziók használatát. A termékdimenziók felhasználóbarát névvel rendelkeznek; ezek a nevek megjelennek a termék részleteit tartalmazó oldalakon (PDP), így kiválaszthatók a megfelelő termékváltozatok. Ilyen felhasználóbarát név például a „Kicsi”, a „Közepes” és a „Nagy” (méreteknél) vagy a „Fekete” és a „Barna” (színeknél). Ha viszont egy termék számos változatot támogat, akkor az egyes termékváltozatok képének megtekintéséhez több kiválasztásra van szükség. Ezért a vevők számára lassú és fárasztó lehet a termékváltozatok tallózása és kiválasztása.

Ha a PDP oldalakon palettaként jelennek meg a dimenziók, akkor a vevők előnézetet kapnak a termék változatairól. A különféle színek, minták és textúrák között könnyen lehet tallózni, és a termékváltozatok különböző kombinációi gyorsan megtekinthetők.

A dimenziók palettaként való megjelenítésére szolgáló funkció lehetővé teszi, hogy a Commerce hexadecimális (hex) kódokat és képeket használjon a dimenziók palettaként való megjelenítéséhez. Ezenkívül a hasonló dimenziók (például a színek) csoportosíthatóak a termékek listaoldalain. Tegyük fel például, hogy egy vevő kék termékeket keres. Ha a különféle kék dimenzióértékeket csoportosítja, akkor a keresési eredmények listaoldalán azok a termékek jelennek meg, amelyek különböző árnyalatú kék színűek. A dimenziók csoportosításával jelentősen finomíthatók a termékek, és a megoldás megkönnyíti a vevők számára, hogy egyetlen termékkeresési lekérdezéssel több terméket találjanak.

> [!NOTE]
> A dimenziók palettaként való megjelenítése a Dynamics 365 Commerce 10.0.20-as kiadásában áll rendelkezésre.

Az alábbi képen olyan példa látható, ahol a színek palettaként jelennek meg egy kereskedelmi PDP oldalon.

![Példa a színeknek palettaként való megjelenítésére a termék részleteit tartalmazó oldalon.](../dev-itpro/media/swatch_pdp.png)

Az alábbi képen olyan példa látható, ahol a színek palettaként jelennek meg a keresési eredményeket mutatót Commerce-listaoldalon.

![Példa a színeknek palettaként való megjelenítésére a keresési eredményeket mutató listaoldalon.](../dev-itpro/media/swatch_searchresults.PNG)

## <a name="enable-the-display-dimensions-as-swatches-feature-in-commerce-headquarters"></a>A dimenziók palettaként való megjelenítésének engedélyezésére szolgáló funkció a Commerce központjában

Ha engedélyezni szeretné a dimenziók palettaként való megjelenítését a Commerce központjában, lépjen a **Munkaterületek \> Funkciókezelés** részre, és kapcsolja be a **Képek támogatásának engedélyezése a termékek dimenzióértékeihez** funkciót. Ha ez a funkciójelölő engedélyezve van, a Commerce központjában lévő megfelelő táblázatokban három új mező jelenik meg az egyes dimenzióknál: **Hexadecimális kód**, **URL** (képeknél) és **Finomító csoport**.

## <a name="configure-dimension-values-in-commerce-headquarters"></a>Dimenzióértékek konfigurálása a Commerce központjában

A dimenziók palettaként való megjelenítése a méret, a stílus és a szín dimenziók esetében támogatott. A hexadecimális kód és a kép_URL értéke a Commerce központjában adható meg a megfelelő dimenziókhoz. Ha egy dimenzióhoz nincs megjelölve hexadecimális kód és kép-URL, a rendszer alapértelmezés szerint a dimenzió felhasználóbarát nevének szövegét jeleníti meg.

A konfiguráció a következő szintek bármelyikén elvégezhető:

- **Dimenzió** – A Commerce központjában nyissa meg a dimenzióhoz tartozó oldalt: keressen a **Színre**, a **Méretre** vagy a **Stílusra**. A dimenzióértékek minden oldalon rácsban láthatók. A megjelenítési sorrendet, a hexadecimális kódot és a kép-URL értékét kezelheti. A következő képen a **Színek** oldal példakonfigurációját mutatja.

    ![Dimenziókonfiguráció példája a Színek oldalon.](../dev-itpro/media/swatch_Color.PNG)

- **Dimenzió csoport** – A Dynamics 365 Commerce rendszerben a **Finomító csoport** tulajdonsággal hozhatók létre dimenziócsoportok. Ha dimenziócsoportokat szeretne meghatározni, nyissa meg a megfelelő oldalt: keressen a **Színcsoportra**, a **Méretcsoportra** vagy a **Stíluscsoportra**. Az egyes oldalakon kezelni lehet a hexadecimális kódot, a kép-URL-t és a finomító csoport értékét. A következő képen a **Színcsoportok** oldal példakonfigurációját mutatja.

    ![Dimenziókonfiguráció példája a Színcsoportok oldalon.](../dev-itpro/media/swatch_colorGroup.PNG)

- **Termékdimenzió (termék létrehozása során)** – Amikor új terméket hoz létre, a **Termékdimenziók** oldalon megadhatja a dimenzió értékeit. Meglévő termékek esetében lehet, hogy már be van állítva a **Hexadecimális kód**, az **URL** (képeknél) vagy a **Finomító csoport** mező. Az értékek azonban igény szerint módosíthatók. A következő képen a **Termékdimenziók** oldalon lévő példakonfiguráció látható.

    ![Dimenziókonfiguráció példája a Termékdimenziók oldalon.](../dev-itpro/media/swatch_product_dimensions.PNG)

> [!NOTE]
> A hexadecimális kód és kép-URL konfigurációinak kezelési folyamata a dimenziók megjelenítési sorrendjének kezelésénél használt mintát követi.

## <a name="configure-dimension-values-by-using-hex-codes"></a>Dimenzióértékek konfigurálása hexadecimális kódokkal

A legtöbb színdimenziónál a Commerce központjában lévő dimenzióoldalakon meg kell adni hexadecimális kódban egy színértéket. A fekete színnél például a hexadecimális kód a **#00000** érték. Amikor a Commerce megjeleníti a webhely egyik oldalát, a hexadecimális kódot színezett paletta jelzi.

A következő ábrán lévő példa a színdimenziók hexadecimális kódú értékekkel történő konfigurálását mutatja.

![Hexadecimális kódokat használó dimenziókonfiguráció példája.](../dev-itpro/media/swatch_color_hexcode.png)

## <a name="configure-dimension-values-by-using-image-urls"></a>Dimenzióértékek konfigurálása kép-URL-lel

Egyes színdimenziók nem egységes színt, hanem mintákat jeleznek. A színdimenzió például leírható „leopárdmintásként”. Ilyen esetekben hatékonyabban jelenítheti meg a színdimenziókat, ha hexadecimális kód helyett közzétett képeket használ a palettáknál.

Minden képet fel kell töltenie a Commerce webhelyszerkesztőjébe, majd közzé kell tennie. Ezután adja meg a közzétett kép URL-címét a Commerce központjának megfelelő dimenzióoldalain. Ha egy dimenziónál ki van választva a palettaként való megjelenítés, de nincs meghatározva hexadecimális kód, akkor a Commerce az oldal megjelenítésekor megpróbálja megkeresni a képet. Ha a kép nem található, a Commerce a dimenzió felhasználóbarát nevének szövegét fogja megjeleníteni.

A következő képen látható példában a kép URL-jét használtuk a konfigurációhoz a **Színek** oldalon.

![Kép-URL-eket használó dimenziókonfiguráció példája.](../dev-itpro/media/swatch_color_urls.PNG)

Ahogy a termék- és kategóriaképek esetében, a képek URL-je meghatározható multimédiás sablonokkal. Amikor képeket tölt fel a webhelyszerkesztőbe, a fájlnevek használatának és a fájlok elérési útjának egységesnek kell lennie.

A következő képen látható példában a kép URL-jét használtuk egy multimédiás sablon konfigurációjához.

![Példa multimédiás sablon konfigurációjára.](../dev-itpro/media/swatch_media_template.PNG)

## <a name="configure-dimension-values-by-using-both-hex-codes-and-image-urls"></a>Dimenzióértékek konfigurálása mind hexadecimális kódokkal, mind kép-URL-ekkel

A legtöbb színdimenzióhoz mind hexadecimális kód, mind kép-URL beállítható. A Commerce-renderelés helyettesítő logikája automatikusan vagy hexadecimális kódot, vagy kép-URL-t keres a színpaletta megjelenítéséhez. Ha a színdimenziók konfigurálásához hexadecimális kódot és kép-URL-t is használ, azzal leegyszerűsítheti a képkezelést, ha nagy a színek száma.

A következő képen látható példában mind hexadecimális kódot, mind kép-URL-t használtunk a konfigurációhoz a **Színek** oldalon.

![Kép-URL-eket és hexadecimális kódot egyaránt használó dimenziókonfiguráció példája.](../dev-itpro/media/swatch_color_hexandimage.png)

## <a name="configure-refiner-groups"></a>Finomító csoportok konfigurálása

Ha egy dimenzióértékhez hexadecimális kódot vagy kép-URL-t konfigurál, akkor a **Finomító csoport** mező értékét is megadhatja. Ez a mező azt a dimenziót határozza meg, amelyet a hasonló dimenzióértékek csoportosításához használni kell a finomítói környezetben.

Ha például a szín dimenzióértékei „kék”, „kék kockás”, "halványkék” és „sötétkék”, akkor a rendszer mindegyik értéket másik hexadecimális kódhoz vagy kép-URL-hez rendeli hozzá. Ez azt jelenti, hogy minden érték más színnel jelenik meg a PDP oldalakon és a megfelelő termékek termékkártyáin. Ha viszont ezeket a színdimenziókat a **Kék** **Finomító csoportjának** egyik értékéhez rendeli hozzá, akkor a „kék” termékekre való keresés eredményeként olyan listaoldal jelenik meg a keresési eredményekkel, amelyen a „kék”, a „kék kockás”, a "halványkék” és a „sötétkék” színértékek szerepelnek.

Az alábbi képen a **Szín** és a **Finomító csoport** tulajdonságai közötti kapcsolat látható a Commerce központjában.

![Példa a finomító csoport kezelésére.](../dev-itpro/media/swatch_refiner_group.png)

## <a name="manage-images-in-commerce-site-builder"></a>Képek kezelése a Commerce webhelyszerkesztőjében

Ha kép-URL-eket használ valamelyik dimenzióértékhez, akkor a megfelelő képeket fel kell töltenie a Commerce webhelyszerkesztőjébe. Az egyes képek helyének meg kell egyeznie a Commerce központjában megadott fájlnévvel és mappaelérési úttal. A képfájlokat a webhelyszerkesztő megfelelő kategóriahelyeire kell feltölteni. A színes képeket például a **Szín** kategóriamappába kell feltölteni. További információ a képek webhelykészítőbe történő feltöltéséről: [Képek feltöltése](../dam-upload-images.md).

A következő képen lévő példában a **Fájlok feltöltése** párbeszédpanel használatával töltöttünk fel képeket a webhelykészítő médiatárába. A képen kiemelten jelennek meg a kijelöléshez rendelkezésre álló **Méret**, **Szín** és **Stílus** kategóriák.

![Példa képfájl-kategóriákra a webhelyszerkesztő médiatárába való feltöltés során.](../dev-itpro/media/swatch_sitebuilder.png)

## <a name="enable-swatch-display-on-e-commerce-site-pages"></a>A paletta megjelenítésének engedélyezése az e-kereskedelmi webhely oldalain

A paletták csak akkor jelenhetnek meg az e-kereskedelmi webhely olyan oldalain, ahol dimenzióválasztás szükséges (például a PDP oldalakon vagy a listaoldalakon), ha konfigurálja a dimenzió helybeállításait a Commerce központjában. További információ: [Helybeállítások alkalmazása dimenziókra](../dimension-settings.md).

Ezenkívül engedélyeznie kell a **Termékattribútumok hozzáadása a keresési eredményekhez** tulajdonságot a keresési eredmények moduljaiban. Ha a webhely testre szabott kategóriaoldalakat használ, frissítenie kell a keresési eredmények ilyen lapokon használt moduljait, hogy a **Termékattribútumok hozzáadása a keresési eredményekhez** tulajdonság engedélyezhető legyen. További információ: [Keresési eredmények modul](../search-result-module.md).

## <a name="display-swatches-in-pos-and-other-channels"></a>Paletták megjelenítése a pénztári és az egyéb csatornákban

A Commerce jelenleg nem rendelkezik olyan beépített implementációval, amely támogatja a paletták pénztári és egyéb csatornákban való megjelenítését. A palettamegjelenítési funkció azonban megvalósítható olyan bővítményként, amely használatakor a csatorna API-jai visszaadják a paletták megjelenítéséhez szükséges hexadecimális kódokat és kép-URL-eket.

## <a name="additional-resources"></a>További erőforrások

[Keresési eredmények modul](../search-result-module.md)

[Helybeállítások alkalmazása dimenziókra](../dimension-settings.md)

[Termékdimenziók](../../supply-chain/pim/product-dimensions.md)

[Kép feltöltése](../dam-upload-images.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
