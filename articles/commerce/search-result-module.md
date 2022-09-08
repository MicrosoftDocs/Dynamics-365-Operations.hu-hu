---
title: Keresési eredmények modul
description: Ez a témakör a keresési eredmények moduljait tartalmazza, és bemutatja, hogyan lehet őket webhelyoldalakhoz adni Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: eeb7cd0769fcb866a3d7dcc03e8e87daf24b2c5d
ms.sourcegitcommit: 1d5cebea3e05b6d758cd01225ae7f566e05698d2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2022
ms.locfileid: "9405293"
---
# <a name="search-results-module"></a>Keresési eredmények modul

[!include [banner](includes/banner.md)]

Ez a témakör a keresési eredmények moduljait tartalmazza, és bemutatja, hogyan lehet őket webhelyoldalakhoz adni Microsoft Dynamics 365 Commerce.

A keresési eredmények modul megjeleníti a termékkeresési eredményeket és a termékekre alkalmazható finomítók listáját. A Dynamics 365 Commerce-webhelyek keresési eredmény moduljai a következő helyzetekben használhatók lapok megjelenítésére:

- Felhasználói keresés által kezdeményezett keresési eredmények
- Olyan keresési eredmények, amelyek adott termékhalmazt mutatnak, például a „hasonló megvásárlása” kifejezés
- Adott kategóriába tartozó termékek listái

A kategóriákról és a keresési eredmények oldalairól [Az alapértelmezett kategória céloldala és keresési találatoldala](category-search-page-overview.md) nyújt további tájékoztatást.

A következő ábra egy példát mutat be egy keresési eredmény oldal megjelenítésére egy kategóriához kapcsolódóan a Fabrikam webhelyen.

![Példa a Fabrikam webhelyén lévő keresési eredmények oldalra.](./media/SimpleCategoryLandingDressCategory.png)

## <a name="search-results-module-properties"></a>Keresési eredmények modul tulajdonságai

Az alábbi táblázat felsorolja a keresési eredmények modulok tulajdonságait, valamint azok értékeit és leírásait.

| Tulajdonság | Értékek | Leírás |
|----------|--------|-------------|
| Cikkek száma oldalanként | Egész | Az egyes oldalakon megjelenítendő elemek száma. |
| Visszalépés engedélyezése a PDP-n | **Igaz** vagy **Hamis** | Ha a tulajdonság beállítása **Igaz**, amikor egy felhasználó kiválasztja a terméket a keresési eredmények oldalon, a termék részleteit tartalmazó megnyitott oldalon az útkövető navigációs rendszer megjeleníti a Vissza az eredményekhez hivatkozást. |
| Finomítók kibővítése | **Mind**, **1**, **2**, **3** vagy **4** | Az oldal betöltésekor kibontandó legjobb finomítók száma. Ha például a tulajdonság értéke **3**, a program az oldal első három finomítóját bontja ki. |
| Kategóriahierarchia megjelenítésének elrejtése | **Igaz** vagy **Hamis** | Ha ez a tulajdonság **Igaz**, a kategóriahierarchia nem jelenik meg az oldalon. Ha az [útvonalkövető modult](add-breadcrumb.md) használja a kategóriahierarchia megjelenítéséhez, ezt a tulajdonságot **Igaz** értékre kell beállítani.|
| Termékattribútumok hozzáadása a keresési eredményekhez | **Igaz** vagy **Hamis** | Ha a tulajdonság értéke **Igaz**, a keresési eredmények megjelenítik a termékek attribútumait. Bár ezek az attribútumok a Commerce webhelyen is megjeleníthetők, bővítményre van szükség.|
| Fiókárak megjelenítése | **Igaz** vagy **Hamis** | Ha ez a tulajdonság **Igaz**, a termékek fiókárai megjelennek a keresési eredményekben, amikor egy bejelentkezett felhasználó tallóz az oldalon. |
| A finomító panel frissítése | **Igaz** vagy **Hamis** | Ha ennek a tulajdonságnak az értéke **Igaz**, akkor a finomító panel frissül a finomítók kiválasztásakor. Ebben a módban a finomító panel frissítése esetén bizonyos többszörös kiválasztású finomítók úgy fognak viselkedni, mint az egyszeres kiválasztású finomítók. |

> [!IMPORTANT]
> A Commerce 10.0.16-os és későbbi kiadásában a **Fiókárak megjelenítése** konfiguráció használható a fiókárak oldalon történő megjelenítésére.
>
> A Commerce 10.0.20-as és újabb kiadásában **A finomító panel frissítése** konfigurációval frissíthető a finomító panel a finomító kiválasztásakor.

## <a name="supported-modules"></a>Támogatott modulok

A keresési eredmények modul támogatja a [gyorsnézet modult](quick-view-module.md), amellyel a felhasználók megtekinthetik a termékadatokat, és cikkeket adhatnak hozzá a kosárhoz egy keresési eredmények oldalról.

## <a name="add-a-search-results-module-to-a-category-page"></a>Keresési eredmények modul hozzáadása kategóriaoldalhoz

A webhelyszerkesztő kategóriaoldalára a következő lépésekkel lehet keresési eredménymodult hozzáadni.

1. Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.
1. Az **Új sablon** párbeszédablakban írja be a **Keresési eredmények** nevet, majd válassza az **OK** gombot.
1. Válassza ki a **három** pontból (...), **majd válassza a Modul hozzáadása lehetőséget a Törzsnél**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **az Alapértelmezett** lap modult, majd kattintson az **OK gombra**.
1. Az Alapértelmezett **lap** modul főbejáratában **válassza** ki a három pontból (...), **majd válassza a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a** Tároló modult, majd válassza az **OK gombra.**
1. A tárolóhelyen **válassza** ki a három pontból (...), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Navigációs modult**, majd kattintson az **OK gombra**.
1. Az **Útkövetés** tulajdonságok panelen írja be az **1** értéket az **Előfordulások minimális száma** pontban.
1. A tárolóhelyen **válassza** ki a három pontból (...), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Keresési** eredmények modult, majd válassza az **OK gombra.**
1. A **Keresési eredmények** tulajdonságok panelen adja meg az **1** értéket az **Előfordulások minimális száma** pontban, majd állítsa be az egyéb szükséges tulajdonságokat a keresési eredmények modulhoz. A tulajdonságoknak a sablonban való beállításával biztosíthatja, hogy az adott kategóriaoldal minden testreszabása automatikusan tartalmazza ezeket a beállításokat.
1. Válassza a **Szerkesztés befejezése** parancsot, majd a **Közzététel** elemet a sablon közzétételhez.
1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. Az Új lap **létrehozása párbeszédpanel** Lap neve **csoportban** adja **meg a Kategória** lapot, majd válassza a Tovább **gombra.**
1. Válassza **ki a Létrehozott** **keresési** eredmények sablonját a Sablon kiválasztása, majd a Tovább **gombra.**
1. Az **Elrendezés kiválasztása oldalon válasszon** egy lapelrendezést (például **rugalmas** elrendezés), majd válassza **a Tovább lehetőséget**.
1. Az Ellenőrzés **és befejezés lapon** ellenőrizze a lap konfigurációját. Ha szerkesztenie kell a lap adatait, válassza a Vissza **lehetőséget**. Ha a lap adatai helyesek, válassza a Létrehozás **lapot**.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="inventory-aware-search-results-module"></a>Készletre vonatkozó keresés eredménymodulja

A keresési eredmények modul beállítható úgy, hogy a készletadatok beleszámok, és a következő tapasztalatokat szolgáltatja:

- Készletszintű címkék megjelenítése a termékek mellett.
- A készleten nem található termékek elrejtése a terméklistáról.
- A készleten nem található termékek megjelenítése a terméklista végén.
- Készletalapú termékszűrés támogatása.

Az ilyen **tapasztalatok engedélyezéséhez először engedélyeznie kell, hogy a továbbfejlesztett e-Commerce** termék-észlelési funkció készleten legyen, majd konfigurálnia kell néhány előfeltételt a Commerce Headquarters szolgáltatásban. További információ a készletre [vonatkozó terméklista-listában található](inventory-aware-product-listing.md).

## <a name="additional-resources"></a>További erőforrások

[Az alapértelmezett kategória-céloldal és keresési találatoldal áttekintése](category-search-page-overview.md)

[Modultár áttekintése](starter-kit-overview.md)

[Gyorsnézeti modul](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
