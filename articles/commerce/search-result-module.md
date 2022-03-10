---
title: Keresési eredmények modul
description: Ez a témakör a keresési eredmények modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 10/15/2021
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
ms.openlocfilehash: bae825ed7093494c48abac119c480be0dba4f951
ms.sourcegitcommit: 9c2bc045eafc05b39ed1a6b601ccef48bd62ec55
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/14/2021
ms.locfileid: "7919474"
---
# <a name="search-results-module"></a>Keresési eredmények modul

[!include [banner](includes/banner.md)]


Ez a témakör a keresési eredmények modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

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

## <a name="enable-inventory-awareness-for-the-search-results-module"></a>Készletérzékenység engedélyezése a keresési eredmények modulban

Az ügyfelek általában azt várják, hogy egy e-commerce webhely a böngészési élmény során figyelembe vegye a készletet, hogy eldöntsék, mi történjen, ha egy termékből nincs készlet. A keresési eredmények modul tovább javítható, hogy készletadatokat tartalmazzon, és a következő élményeket nyújtsa:

- Készlet elérhetőségi címkéjének megjelenítse a termékekkel együtt.
- Készleten nem lévő termékek elrejtése.
- A készleten nem található termékek megjelenítése a keresési eredmények listájának végén.
    
Az élmények engedélyezéséhez konfigurálnia kell a Commerce Headquarters következő előfeltétel-beállításait.

### <a name="enable-the-enhanced-e-commerce-product-discovery-to-be-inventory-aware-feature"></a>Engedélyezze a Továbbfejlesztett e-Commerce-termékészlelés, amely figyelembe veszi a készletet funkciót

> [!NOTE]
> A **Továbbfejlesztett e-Commerce-termékészlelés, amely figyelembe veszi a készletet** a Commerce 10.0.20-as verziójú kiadásában érhető el.

A következő lépésekkel engedélyezheti a **Továbbfejlesztett e-Commerce-termékészlelés, amely figyelembe veszi a készletet** funkciót a Commerce Headquarters szolgáltatásban.

1. Menjen a **Munkaterületek \> Funkciókezelés** lehetőségre.
1. Keressen rá a **Továbbfejlesztett e-Commerce-termékészlelés, amely figyelembe veszi a készletet** funkcióra, majd engedélyezze.

### <a name="configure-the-populate-product-attributes-with-inventory-level-job"></a>Konfigurálja a Termékattribútumok feltöltése készletszinttel feladatot

A **Termékattribútumok feltöltése készletszinttel** feladat új termékattribútumot hoz létre a készlet elérhetőségének rögzítéséhez, majd az attribútumot az egyes alaptermékekkel kapcsolatos legutóbbi készletszint-értékre állítja. Mivel az eladott termékek vagy szortimentek készlet rendelkezésre állása folyamatosan változik, ezért kifejezetten ajánljuk, hogy a feladatot kötegfolyamatként ütemezze.

A Következő lépések szerint konfigurálhatja a **Termékattribútumok feltöltése készletszinttel** feladatot a Commerce központban.

1. Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem IT \> Termékek és készlet** lehetőségre.
1. Válassza a **Termékattribútumok feltöltése készletszinttel** lehetőséget.
1. A **Termékattribútumok feltöltése készletszinttel** párbeszédpanelen a következő lépéseket kövesse:

    1. A **Paraméterek** területen **Termékattribútum és típus neve** mezőben adja meg a kijelölt termékattribútum nevét, amely a készlet rendelkezésre állásának rögzítéséhez fog létrejönni.
    1. A **Paraméterek** területen a **Készlet rendelkezésre állása a következő alapján:** mezőben válassza ki azt a mennyiséget, amelyen a készletszint-számításnak alapulnia kell (például **Elérhető fizikai**).
    1. A **Futtatás a háttérben** alatt állítsa be a feladatot a háttérben való futtatásra, és opcionálisan kapcsolja be e **Kötegfeldolgozás** lehetőséget. 

> [!NOTE]
> Az egységes készletszint-számításhoz a PDP-k és az e-commerce webhely terméklistaoldalai között, győződjön meg róla, hogy ugyanazt a mennyiségbeállítást válassza a Commerce központ **Készlet rendelkezésre állása a következő alapján:** és Commerce oldalkészítő **Készletszint alapja** beállításánál is. Az oldaltervező készletbeállításaival kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Készletbeállítások alkalmazása](inventory-settings.md).

### <a name="configure-the-new-product-attribute"></a>Az új termékattribútum konfigurálása

Miután futtatta a **Termékattribútumok feltöltése készletszinttel** feladatot konfigurálnia kell az újonnan létrehozott termékattribútumokat az e-commerce webhelyen, ahol engedélyezni szeretné a készlet észlelését a keresési eredmények modul számára.

A Commerce központban az új termékattribútum konfigurálásához kövesse az alábbi lépéseket.

1. Nyissa meg a következőt: **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Csatornakategóriák és termékattribútumok**, és válasszon egy e-kereskedelmi oldalt.
1. Válasszon ki és nyisson meg egy társított attribútumcsoportot, adja hozzá az újonnan létrehozott termékattribútumot, majd zárja be a lapot.
1. Válassza ki az **Attribútum-metaadatok beállítása** lehetőséget, válassza ki az újonnan hozzáadott termékattribútumot, majd kapcsolja be az **Attribútum megjelenítése a csatornában**, **Lekérhető**, **Finomítható** és **Lekérdezhető** beállításokat.

> [!NOTE]
> A keresési eredmények modulban megjelenő termékeknél a készletszint az alaptermék szintjén kerül bevitelre az egyes változatok szintje helyett. Csak két lehetséges érték áll rendelkezésre: "elérhető" és a "nincs készleten". Az értékek tényleges szövegét a [készletszint-profil](inventory-buffers-levels.md) definíciója olvassa be. Az alaptermék csak akkor minősül készlethiányosnak, ha az egyik változata nincs készleten. A változat készletszintje a termék készletszintű profiljának meghatározása alapján határozható meg. 

Miután az előző konfigurációs lépések mindegyikét befejezte, a keresési eredményoldalak finomítói egy készlet alapú szűrőt fognak mutatni, és a keresési eredménymodul beolvassa a mögöttes készletadatokat. Ezután a Commerce webhelyszerkesztőben konfigurálhatja a **Termékbeállítások terméklistaoldalakhoz** beállítást, hogy szabályozza, a keresési eredmények modulban hogyan jelenítse meg a raktáron nem lévő termékeket. További információk: [Készletbeállítások alkalmazása](inventory-settings.md).

## <a name="additional-resources"></a>További erőforrások

[Az alapértelmezett kategória-céloldal és keresési találatoldal áttekintése](category-search-page-overview.md)

[Modultár áttekintése](starter-kit-overview.md)

[Gyorsnézeti modul](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
