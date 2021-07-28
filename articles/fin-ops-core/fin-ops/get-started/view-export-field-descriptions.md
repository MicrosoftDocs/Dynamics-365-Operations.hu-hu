---
title: Mezőleírások megtekintése és exportálása
description: Ez a cikk leírja, hogy hogyan tekinthetőek a mezőleírások, illetve hogy hogyan exportálhatóak a leírások a Mezőleírások oldal segítségével.
author: rschloma
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FieldDescriptions
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 11534
ms.assetid: e2795f51-a8a7-4c74-bdb9-b1be93bdd358
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9fe3a1b0c278839069ebd3d047f8052e9da25203
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6348581"
---
# <a name="view-and-export-field-descriptions"></a>Mezőleírások megtekintése és exportálása

[!include [banner](../includes/banner.md)]

Ez a cikk leírja, hogy hogyan tekinthetőek a mezőleírások, illetve hogy hogyan exportálhatóak a leírások a Mezőleírások oldal segítségével.

Néhány bonyolultabb mező mezőleírással is rendelkezik. Ezek a leírások akkor jelennek meg, ha az adott mező fölé húzza az egérmutatót. Ezenkívül a **Mezőleírások** oldalon megtekintheti és exportálhatja a leírásokat.

Nem minden lap rendelkezik mezőleírásokkal. Csak az összetettebb mezőkhöz kívánunk leírásokat nyújtani, azokhoz nem, amelyek használata nyilvánvaló. Ezért néhány oldalon egyáltalán nem található mezőleírás, egyes oldalakon csak néhány leírás jelenik meg, néhány összetettebb oldalon (ilyen például a legtöbb paraméteroldal) pedig sok leírás érhető el.

Amennyiben ön hozzáfér a fejlesztői környezethez, új mezőleírásokat adhat meg, illetve módosíthatja a meglévő leírásokat. Például cégspecifikus információt tehet hozzá egy mezőleíráshoz. További tájékoztatást a [Mezőleírások testreszabása](../../dev-itpro/user-interface/customize-field-help.md) pontnál talál.

## <a name="see-field-descriptions-in-the-user-interface"></a>Mezőleírások megtekintése a felhasználói felületen

A mezőleírásokat az egérmutató adott mező fölé navigálásával tekintheti meg. Ha nem tartozik leírás az adott mezőhöz, az egérmutató mező fölé vitelekor a mező neve jelenik meg.

> [!NOTE]
> A Microsoft Dynamics AX 7.0.0 verzióban (2016. február) a mezők leírásai csak a **Mezőleírások** oldalon érhetőek el.

Az alábbi ábrán az a mezőleírás látható, amely az egérmutató **Cikkek zárolása leltár közben** mező fölé vitelekor jelenik meg.

[![Példa egy mezőleírásra.](./media/field-description.png)](./media/field-description.png)

## <a name="use-the-field-descriptions-page-to-view-and-export-field-help"></a>A Mezőleírások oldal segítségével megtekintheti és exportálhatja a mezőkhöz tartozó súgót

A **Mezőleírások** oldal segítségével megtekintheti és exportálhatja a mezőleírásokat. Egyszerre csak egy lap leírásai tekinthetők meg.

### <a name="view-the-descriptions-for-a-page"></a>Egy lap leírásainak megtekintése:

Egy lap leírásainak megtekintéséhez kövesse az alábbi lépéseket.

- A **Lap kijelölése** mezőbe írja be a lap nevét. Másik lehetőségként a nyílra kattintva nyissa meg az összes lapot tartalmazó listát; keresse ki a kívánt lapot, vagy szűrje a listát.

Használhatja a felhasználói felületen megjelenő lapnevet (például: **Vevők**) vagy a lap kódnevét (AOT nevét), amely úgy érhető el, hogy jobb gombbal a lapra kattint (például: **CustTable**).

A lapok listájának különféle módon megvalósítható szűréséről bővebben a cikk „Lap keresése” szakaszában olvashat.

Ha a **Leírás nélküli mezőkkel együtt** beállításnál az **Igen** lehetőséget választja, az oldalon minden mező megjelenik, függetlenül attól, hogy rendelkezik-e mezőleírással.

### <a name="export-the-descriptions-for-a-page"></a>Egy lap leírásainak exportálása

Egy lap leírásainak exportálásához kövesse az alábbi lépéseket.

1. Válasszon egy lapot a **Lap kijelölése** mezőben.
2. Kattintson a jobb felső sarokban lévő **Megnyitás Microsoft Office** programban gombra, majd válassza a **FieldDescriptionTmp** lehetőséget.

### <a name="searching-for-a-page"></a>Egy lap keresése

Egy adott lap több módon is megkereshető a **Lap kijelölése** mezőben. Sok esetben a **Lap kijelölése** mezőben található nyílra kell kattintania a legördülő menü kinyitásához; ekkor egy szűrt laplistáról választhat.

- Írja be a név egy részét, majd a nyissa meg a legördülő listát, és válasszon a szűrt lapok listájából.
- Nyissa meg a legördülő listát, majd kattintson a lista tetején lévő **Lapnév** fejlécre vagy a **Lap AOT-neve** fejlécre. Ekkor megjelenik egy párbeszédpanel, ahol speciális szűrési lehetőségeket használhat, például **A lapnév kezdete**.
- Írja be a lap teljes nevét. Ha ezt a beállítást használja, célszerű megnyitni a legördülő listát, és megnézni, hogy mi szerepel még a listán, még akkor is, ha a mezőleírások megjelennek.

    - Ha egyetlen pontos egyezés található a névhez, akkor annak megfelelő lap mezőleírásai fognak megjelenni.
    - Ha egynél több pontos egyezés található, nem jelennek meg leírások. Ez esetben nyissa meg a legördülő listát és jelölje ki a kívánt lapot.
    - A beírt névnek megfelelő lap leírásai jelennek meg akkor is, ha a beírt név egy másik lap nevének részét képezi. Azonban ha megnyitja a legördülő listát, abban láthatóak lesznek az adott nevet tartalmazó lapok.

Például ha a **Leltár** kifejezést írja be a **Lap kijelölése** mezőbe, nem jelenik meg leírás. Ha rákattint a legördülő listára, két **Leltár** nevű lapot fog látni, valamint több olyan lapot, amelynek nevében szerepel a „Leltár” szó. Ha az **InventJournalCount** AOT-névvel rendelkező lapot választja, akkor megjelennek az adott laphoz tartozó mezőleírások. Azonban ha újra megnyitja a legördülő listát, látni fogja, hogy a lista most már tartalmaz minden olyan lapot, amelynél az AOT-lapnév része az „InventJournalCount”.

## <a name="troubleshooting"></a>Hibaelhárítás

Ez a szakasz a mezőleírások használata során felmerülő lehetséges problémák elhárításához nyújt segítséget.

### <a name="i-cant-find-a-field-description"></a>Nem található mezőleírás

Jelenleg zajlik az összetettebb mezők leírásának folyamata. Ha segítségre van szüksége egy adott mezőhöz, kérjük tudassa velünk azzal, hogy hozzászól ehhez a témakörhöz.

### <a name="the-field-description-isnt-helpful"></a>A mezőleírás nem ad segítséget

Kérjük, tudassa ezt velünk azzal, hogy hozzászól ehhez a témakörhöz. Ha lehetséges, írja le azokat a kiegészítő információkat, amelyekre szüksége van.

### <a name="i-cant-find-a-field-on-the-field-descriptions-page"></a>Nem találok egy mezőt a Mezőleírások oldalon

Az egy lapon lévő összes mező megjelenítéséhez, állítsa a **Tartalmazza a leírás nélküli mezőket** lehetőséget az **Igen** opcióra. A **Lap kijelölése** mezőre való kattintással ellenőrizze, hogy a megfelelő lapot választotta-e ki. Ha a beírt név egy másik lapnév része, előfordulhat, hogy a hosszabb nevű lapot választotta ki.

### <a name="i-cant-find-a-page-on-the-field-descriptions-page"></a>Nem találok egy lapot a Mezőleírások oldalon

A lapok különféle módon megvalósítható megkereséséről bővebben feljebb, a cikk „Lapok keresése” szakaszában olvashat. Ha a lap pontos nevét írta be, a mezőleírások lehet, hogy azért nem jelennek meg, mert egynél több azonos nevű lap létezik. Kattintson a nyílra a **Lap kijelölése** mezőben az elérhető lapok szűrt listájának megnyitásához.

## <a name="additional-resources"></a>További erőforrások

[Mezőleírások testreszabása](../../dev-itpro/user-interface/customize-field-help.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]