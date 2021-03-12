---
title: Vásárlásmező modul
description: Ez a témakör ismerteti a Vásárlásmező modulok működését és bemutatja, hogyan tudjuk hozzáadni azokat az egyes webhelyekhez, a Dynamics 365 Commerce segítségével.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ae3da8ee77636a2d2257e01f5876f5542469f7da
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4986054"
---
# <a name="buy-box-module"></a>Vásárlásmező modul

[!include [banner](includes/banner.md)]

Ez a témakör ismerteti a Vásárlási mező-modulok működését és bemutatja, hogyan tudjuk hozzáadni azokat az egyes webhelyekhez, a Dynamics 365 Commerce segítségével.

## <a name="overview"></a>Összegzés

A *Vásárlási mező* kifejezés általában a termék adatlapjának azon mezőjére utal, mely a „honlap felső részén" található, és a termék megvásárlásához szükséges legfontosabb információkat szolgáltatja. (A „honlap felső részén" alatt az a terület értendő, amely a honlap betöltésekor elsőként látható, azaz a felhasználóknak nem szükséges lejjebb görgetniük, hogy láthassák.)

A vásárlási mező-modul egy speciális tároló, amely arra használatos, hogy összekapcsolja az összes modult, amely a vásárlási mező területén jelenik meg a termék adatlapján.

A termék adatlapjának URL-je tartalmazza a termékazonosítót. Minden információ, ami a vásárlási mező-modul használatához szükséges, ebből a termékazonosítóból származik. Ha nincs megadva termékazonosító, akkor a vásárlási mező-modul nem fog megfelelően működni a honlapon. Ezért a vásárlási mező-modul csak olyan oldalakon használható, melyek tartalmazzák a termék részletes adatait. Hogy olyan oldalon hasznáhassa, amely nem tartalmazza a termék részletes adatait (pl. egy honlap főoldalán, vagy egy marketing weboldalon), további beállítások szükségesek.

A következő képen egy egy vásárlási mező-modul látható, egy termék adatlapján.

![Egy példa egy vásárlásmező modulra](./media/ecommerce-pdp-buybox.PNG)

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
- **Termék hozzáadása a kosárhoz** – Ezzel a tulajdonsággal lehet meghatározni, mi történjen, miután egy cikket a kosárhoz adtak. A lehetséges értékek **Navigálás a kosárhoz oldal**, **Ne navigáljon a kosárhoz oldal** és **Értesítés megjelenítése**. Ha az érték **Navigáció a kosárhoz oldal**, akkor a felhasználók a kosár oldalra lesznek küldve, miután hozzáadtak egy cikket. Ha az érték **Ne navigáljon a kosárhoz oldal**, akkor a felhasználók nem lesznek a kosár oldalra küldve, miután hozzáadtak egy cikket. Ha az érték az **Értesítés megjelenítése**, akkor a felhasználók visszaigazoló értesítést kapnak és tovább böngészhetnek a termék részletei oldalon. 

> [!IMPORTANT]
> A **Termék hozzáadása a kosárhoz** webhely beállításai a Dynamics 365 Commerce 10.0.11-es kiadásában érhetők el. Ha a Dynamics 365 Commerce egy korábbi verziójáról frissít, akkor manuálisan kell frissítenie az appsettings.json fájlt. Az appsettings.json fájlok frissítésével kapcsolatos tudnivalókat lásd az [SDK- és modulkönyvtár-frissítések](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file) témakörben. 

A következő kép egy példát mutat egy „kosárhoz adva” visszaigazolási értesítésre a Fabrikam oldalon.

![Példa egy értesítési modulra](./media/ecommerce-addtocart-notifications.PNG)

## <a name="commerce-scale-unit-interaction"></a>Commerce Scale Unit-interakció

A vásárlásmező-modul a termék adatait a Commerce Scale Unit alkalmazásprogramozási felületek (API-k) használatával olvassa be. Az termék részletes lapjáról származó termékazonosító az összes információ lekérdezésére szolgál.

## <a name="add-a-buy-box-module-to-a-page"></a>Vásárlásmező modul felvétele egy oldalra

A vásárlásmező modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen a **Töredékek** pontra, és válassza az **Új** lehetőséget új töredék létrehozásához.
1. Az **Új töredék** párbeszédpanelen válassza ki a **Vásárlásmező** modult.
1. Az **Töredék neve** pontban adja meg a **Vásárlásmező-töredék** nevét, majd válassza az **OK** lehetőséget.
1. Válassza ki a három pont (**...**) elemet a **Médiagaléria** helyén, amely tartalmazza a váráslásmező modult, majd válassza a **Modul hozzáadása** lehetőséget.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Médiagaléria** modult, majd kattintson az **OK** gombra.
1. Válassza ki a három pont (**...**) elemet az **Áruházválasztó** helyén, amely tartalmazza a váráslásmező modult, majd válassza a **Modul hozzáadása** lehetőséget.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Áruházválasztó** modult, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.
1. Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **PDP-sablon** elemet, majd válassza az **OK** gombot.
1. A **Törzs** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Alapértelmezett oldal** modult, majd kattintson az **OK** gombra.
1. Az alapértelmezett lap **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Töredék hozzáadása** elemet.
1. A **Töredék kiválasztása** párbeszédpanelen válassza ki a **Vásárlásmező töredék** töredékét, amelyet korábban hozott létre ezután kattintson az **OK** gombra.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. A **Sablon kiválasztása** párbeszédpanelen válassza ki a **PDP-sablon** sablonját. Az **Oldal neve** alatta adja meg a **PDP-oldalt**, majd kattintson az **OK** gombra.
1. Az új oldal **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Töredék hozzáadása** elemet.
1. A **Töredék kiválasztása** párbeszédpanelen válassza ki a **Vásárlásmező töredék** töredékét, amelyet korábban hozott létre ezután kattintson az **OK** gombra.
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

[Kiskereskedelmi csatornák készletelérhetőségének kiszámítása](calculated-inventory-retail-channels.md)

[SDK- és modulkönyvtár-frissítések](e-commerce-extensibility/sdk-updates.md)
