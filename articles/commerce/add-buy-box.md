---
title: Vásárlásmező-modul
description: Ez a témakör a dobozvásárlási modulokról és a webhelyoldalakhoz való hozzáadásukról tartalmaz a témakörben Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 7a3dfa347aac7b1ee7b318761c873beef8322bd9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270509"
---
# <a name="buy-box-module"></a>Vásárlásmező-modul

[!include [banner](includes/banner.md)]

Ez a témakör a dobozvásárlási modulokról és a webhelyoldalakhoz való hozzáadásukról tartalmaz a témakörben Microsoft Dynamics 365 Commerce.

A *Vásárlási mező* kifejezés általában a termék adatlapjának (PDP) azon mezőjére utal, mely a „hajtás felett" található, és a termék megvásárlásához szükséges legfontosabb információkat szolgáltatja. (A „honlap felső részén" alatt az a terület értendő, amely a honlap betöltésekor elsőként látható, azaz a felhasználóknak nem szükséges lejjebb görgetniük, hogy láthassák.)

A vásárlási mező-modul egy speciális tároló, amely arra használatos, hogy összekapcsolja az összes modult, amely a vásárlási mező területén jelenik meg a termék adatlapján.

A termék adatlapjának URL-je tartalmazza a termékazonosítót. Minden információ, ami a vásárlási mező-modul használatához szükséges, ebből a termékazonosítóból származik. Ha nincs megadva termékazonosító, akkor a vásárlási mező-modul nem fog megfelelően működni a honlapon. Ezért a vásárlási mező-modul csak olyan oldalakon használható, melyek tartalmazzák a termék részletes adatait. Hogy olyan oldalon hasznáhassa, amely nem tartalmazza a termék részletes adatait (pl. egy honlap főoldalán, vagy egy marketing weboldalon), további beállítások szükségesek.

A következő képen egy egy vásárlási mező-modul látható, egy termék adatlapján.

![Egy példa egy vásárlásmező modulra.](./media/ecommerce-pdp-buybox.PNG)

## <a name="buy-box-module-properties-and-slots"></a>A vásárlási mező-modul részletei és helyei 

A termék adatlapján a vásárlásmező két részre van osztva: a bal oldalon levő médiaterületre és a jobb oldali tartalomterületre. Alapértelmezés szerint a médiaterület oszlopainak szélességének aranya 2:1 a tartalomterület oszlopainak szélességéhez képest. Mobileszközökön a két terület egymásra van halmozva, így az egyik terület a másik terület alatt jelenik meg. A témák segítségével testreszabhatja az oszlopok szélességét és a halmozási sorrendet.

A vásárlásmező modul a termék címét, leírását, árát és értékeléseit jeleníti meg. Ezenkívül a vevők a különböző termékattribútumokkal rendelkező termékváltozatokat is választhatnak, például a méret, a stílus és a szín. Egy termékváltozat kiválasztásakor a program frissíti a vásárlásmezőbe tartozó egyéb tulajdonságokat (például a termék leírását és a képeket) a változat adatainak megjelenítéséhez. 

A program mennyiségi választót biztosít, így a vevők meghatározhatják a beszerzésre kerülő cikkek mennyiségét. A maximálisan vásárolható mennyiség a webhely beállításai között adható meg.

A vásárlásmezőből a vevők olyan műveleteket is hajthatnak végre, mint például a termékek kosárba történő hozzáadása, egy termék kívánságlistához való hozzáadása, és átvételi hely kiválasztása. Ezek a műveletek a termékre vagy a termékváltozatra vonatkozóan is elvégezhetők. Ha terméket szeretne hozzáadni egy kívánságlistahoz, akkor a vevőnek be kell jelentkeznie.

A témák segítségével eltávolíthatja vagy megváltoztathatja a vásárlásmező terméktulajdonságainak és a műveleti vezérlőknek a sorrendjét. 

## <a name="module-properties"></a>Modul tulajdonságai

- **Címsorcímke** – ez a tulajdonság határozza meg a termék címének címsorcímkéjét. Ha a vásárlásmező a lap felső részén van, a tulajdonságot a **H1** értékre kell állítania a hozzáférhetőségi szabványok teljesítése érdekében. 

- **„Hasonló szettek vásárlása” javaslatok engedélyezése** – Ez a tulajdonság lehetővé teszi a vásárlásmező számára, hogy a jelenleg nézett cikkhez hasonló termékre mutató hivatkozásokat jelenítse meg. Ez a funkció elérhető a Commerce alkalmazás 10.0.13 vagy újabb verziójában.

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>A vásárlásmező modulban használható modulok

- **Médiatár** – Ez a modul a termék képeinek bemutatására szolgál a termék részletes lapján. A modullal kapcsolatos további tudnivalókat lásd: [Médiatár modul](media-gallery-module.md).
- **Áruházválasztó** – Ez a modul felsorolja azokat a közeli áruházakat, ahol a cikkek elérhetők és felvehetők. Ez lehetővé teszi a felhasználók számára, hogy a közelben levő üzleteket megtalálják. A modullal kapcsolatos további tudnivalókat lásd: [Áruházválasztó modul](store-selector.md).
- **Közösségi megosztás** – Azt a modult hozzáadhatja a vásárlásmezőhöz, amely lehetővé teszi a felhasználók számára a termék információinak a megosztását a közösségi médiában. További információ: [Közösségi megosztás modul](social-share-module.md).

## <a name="buy-box-module-settings"></a>Vásárlásmező modul beállításai

A vásárlásmező-modulok következő beállításai konfigurálhatók a **Webhelybeállítások \> Bővítmények** pontban:

- **Kosár mennyiségi korlátja** – Ez a tulajdonság megadja az egyes cikkek kosárhoz adható maximális számát. Előfordulhat például, hogy egy kiskereskedő úgy dönt, hogy egyetlen tranzakcióban csak 10 terméket lehet értékesíteni.
- **Készlet** – A készletbeállítások alkalmazásával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Készletbeállítások alkalmazása](inventory-settings.md).
- **Termék hozzáadása a kosárhoz** – A **Termék hozzáadása a kosárhoz** beállításainak alkalmazásával kapcsolatos további tudnivalókat lásd a [Termék hozzáadása a kosárhoz beállításai](add-cart-settings.md) témakört.

## <a name="buy-box-module-definition-extensions-in-the-adventure-works-theme"></a>Vásárlásmezőmodul-definíciós bővítmények az Adventure Works témában

Az Adventure Works téma által biztosított vásárlásmező-modul olyan moduldefiníciós bővítménnyel rendelkezik, amely támogatja a PDP vásárlási mezőjén belüli harmonikamodulban lévő termékspecifikációs modult. Ha be szeretné mutatni a termékspecifikációs attribútumokat a PDP vásárlási mezőjében, vegyen fel egy termékspecifikációs modult a vásárlási mező helyén belüli harmonikamodul helyére.


> [!IMPORTANT]
> Az Adventure Works téma a Dynamics 365 Commerce 10.0.20-as kiadásában érhető el.


## <a name="commerce-scale-unit-interaction"></a>Commerce Scale Unit-interakció

A vásárlásmező-modul a termék adatait a Commerce Scale Unit alkalmazásprogramozási felületek (API-k) használatával olvassa be. Az termék részletes lapjáról származó termékazonosító az összes információ lekérdezésére szolgál.

## <a name="add-a-buy-box-module-to-a-page"></a>Vásárlásmező modul felvétele egy oldalra

A vásárlásmező modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Töredékek** pontra, és válassza az **Új** lehetőséget új töredék létrehozásához.
1. Az **Új töredék** párbeszédpanelen válassza ki a **Vásárlásmező** modult.
1. Az **Töredék neve** pontban adja meg a **Vásárlásmező-töredék** nevét, majd válassza az **OK** lehetőséget.
1. A buy **box modul Médiagaléria-slotjában** válassza ki a három pontból (**...**), majd válassza **a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Médiagaléria** modult, majd válassza az **OK gombra.**
1. A buy **box** modul üzletválasztó-párbeszédpanelen válassza ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **az** Üzletválasztó modult, majd kattintson az **OK gombra**.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.
1. Az Új **sablon párbeszédpanel** Sablon neve listájában **adja** meg a **PDP-sablont**, majd válassza az **OK gombra.**
1. Válassza ki a **három** pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget** a Törzsnél.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **az Alapértelmezett** lap modult, majd kattintson az **OK gombra**.
1. Az alapértelmezett lap **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Töredék hozzáadása** elemet.
1. A Részlet **kiválasztása párbeszédpanelen** válassza **ki a létrehozott Buy box -** részletet, majd válassza **az OK gombra.**
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. Adjon meg **egy PDP-lapot** **az Új** oldal létrehozása párbeszédpanel Oldal neve **csoportban,** majd válassza a **Tovább lehetőséget**.
1. A **Sablon kiválasztása mezőben válassza** ki **a PDP-sablont**, majd válassza a Tovább **lehetőséget**.
1. Az **Elrendezés kiválasztása oldalon válasszon** egy lapelrendezést (például **rugalmas** elrendezés), majd válassza **a Tovább lehetőséget**.
1. Az Ellenőrzés **és befejezés lapon** ellenőrizze a lap konfigurációját. Ha szerkesztenie kell a lap adatait, válassza a Vissza **lehetőséget**. Ha a lap adatai helyesek, válassza a Létrehozás **lapot**.
1. Az új oldal **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Töredék hozzáadása** elemet.
1. A Részlet **kiválasztása párbeszédpanelen** válassza **ki a létrehozott Buy box -** részletet, majd válassza **az OK gombra.**
1. Mentse a lapot, és tekintse meg az előnézetét. Hozzáadja a **?productid=&lt;product id&gt;** lekérdezési karakterlánc paramétert az előnézeti lap URL-címéhez. A termékkontextus így az előnézeti lap betöltésére és megjelenítésére kerül felhasználásra.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez. A termék részletes lapján meg kell jelennie vásárlásmezőnek.

## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Üzletválasztó modul](store-selector.md)

[Médiagaléria modul](media-gallery-module.md)

[Tárolómodul](add-container-module.md)

[Kosármodul](add-cart-module.md)

[Pénztármodul](add-checkout-module.md)

[Rendelésmegerősítési modul](order-confirmation-module.md)

[Fejlécmodul](author-header-module.md)

[Láblécmodul](author-footer-module.md)

[Közösségi megosztási modul](social-share-module.md)

[Termék kosárhoz adási beállításai](add-cart-settings.md)

[Kiskereskedelmi csatornák készletelérhetőségének kiszámítása](calculated-inventory-retail-channels.md)

[SDK- és modultár-frissítések](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
