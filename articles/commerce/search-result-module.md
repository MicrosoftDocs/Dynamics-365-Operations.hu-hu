---
title: Keresési eredmények modul
description: Ez a témakör a keresési eredmények modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 05/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 645022000d8746db3793a8a8611ab8f17c7bcc6e
ms.sourcegitcommit: 53b797ff1b524f581046b48cdde42f50b37495bc
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/28/2021
ms.locfileid: "6117133"
---
# <a name="search-results-module"></a>Keresési eredmények modul

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Ez a témakör a keresési eredmények modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

A keresési eredmények modul megjeleníti a termékkeresési eredményeket és a termékekre alkalmazható finomítók listáját. A Dynamics 365 Commerce-webhelyek keresési eredmény moduljai a következő helyzetekben használhatók lapok megjelenítésére:

- Felhasználói keresés által kezdeményezett keresési eredmények
- Olyan keresési eredmények, amelyek adott termékhalmazt mutatnak, például a „hasonló megvásárlása” kifejezés
- Adott kategóriába tartozó termékek listái

A kategóriákról és a keresési eredmények oldalairól [Az alapértelmezett kategória céloldala és keresési találatoldala](category-search-page-overview.md) nyújt további tájékoztatást.

A következő ábra egy példát mutat be egy keresési eredmény oldal megjelenítésére egy kategóriához kapcsolódóan a Fabrikam webhelyen.

![Példa a Fabrikam webhelyén lévő keresési eredmények oldalra](./media/SimpleCategoryLandingDressCategory.png)

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

A következő lépésekkel lehet hozzáadni egy keresési eredmények modult egy kategóriaoldalhoz.

1. Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.
1. Az **Új sablon** párbeszédablakban írja be a **Keresési eredmények** nevet, majd válassza az **OK** gombot.
1. A **Törzs** helyben válassza a három pont (…) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Alapértelmezett oldal** modult, majd kattintson az **OK** gombra.
1. Az **Alapértelmezett oldal** modul **Fő** helyén válassza ki a három pont (…) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Tároló** modult, majd kattintson az **OK** gombra.
1. A **Tároló** helyben válassza a három pont (…) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Útkövetési** modult, majd kattintson az **OK** gombra.
1. Az **Útkövetés** tulajdonságok panelen írja be az **1** értéket az **Előfordulások minimális száma** pontban.
1. A **Tároló** helyben válassza a három pont (…) gombot, majd válassza a **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Keresési eredmények** modult, majd kattintson az **OK** gombra.
1. A **Keresési eredmények** tulajdonságok panelen adja meg az **1** értéket az **Előfordulások minimális száma** pontban, majd állítsa be az egyéb szükséges tulajdonságokat a keresési eredmények modulhoz. A tulajdonságoknak a sablonban való beállításával biztosíthatja, hogy az adott kategóriaoldal minden testreszabása automatikusan tartalmazza ezeket a beállításokat.
1. Válassza a **Szerkesztés befejezése** parancsot, majd a **Közzététel** elemet a sablon közzétételhez.
1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. A **Sablon kiválasztása** párbeszédpanelen válassza ki a létrehozott **Keresési eredmények** sablont, írja be a **Kategóriaoldal** lehetőséget az **OIdal neve** pontba, majd kattintson az **OK** gombra. Mivel a sablonban minden érték be van állítva, az oldal készen áll a közzétételre.
1. Válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="additional-resources"></a>További erőforrások

[Az alapértelmezett kategória-céloldal és keresési találatoldal áttekintése](category-search-page-overview.md)

[Modultár áttekintése](starter-kit-overview.md)

[Gyorsnézeti modul](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
