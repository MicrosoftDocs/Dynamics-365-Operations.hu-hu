---
title: Vásárlásmező modul
description: Ez a témakör a vásárlásmező moduljaival foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 583937be92b62991cd13f0806df4a0a6c9ac049c
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411342"
---
# <a name="buy-box-module"></a>Vásárlásmező modul

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ez a témakör a vásárlásmező moduljaival foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A *vásárlásmező* kifejezés általában a termék részletes lapjának azon területére utal, amely „görgetés nélkül látható”, és a termék megvásárlásához szükséges legfontosabb adat mindegyikét tartalmazza. (A „görgetés nélkül látható” terület a lap első betöltésekor jelenik meg, így a felhasználóknak nem kell legörgetni, hogy lássák azt.)

A vásárlásmező egy speciális tároló, amely a termék részletes lapjának vásárlásmező részén látható összes modult tárolja.

A termék részletes lapjának URL-címe tartalmazza a termékazonosítót. A vásárlásmező modul megjelenítéséhez szükséges összes adat ebből a termékazonosítóból származik. Ha nincs megadva termékazonosító, akkor a program nem jeleníti meg megfelelően a vásárlásmező modult a lapon. Ezért a vásárlásmező modul csak a termék környezetét tartalmazó lapokon használható. Ha azt szeretné, hogy egy olyan oldalon használhassa, amely nem rendelkezik a termék környezetével (például egy Kezdőlap vagy egy marketinges lapon), további testreszabásokat kell végérehajtania.

A következő kép egy termékrészletek oldalon használt vásárlásmező modul egy példáját jeleníti meg.

![Példa egy vásárlásmező modulra](./media/ecommerce-pdp-buybox.PNG)

## <a name="buy-box-module-properties-and-slots"></a>A vásárlásmező modul tulajdonságai és helyei 

A termék részletes lapján a vásárlásmező két részre van osztva: a bal oldalon levő médiaterületre és a jobb oldali tartalomterületre. Alapértelmezés szerint a médiarégió oszlopainak szélessége a tartalmi terület oszlopainak szélességéhez képest 2:1. Mobileszközökön a két terület egymásra van halmozva, így az egyik terület a másik terület alatt jelenik meg. A témák segítségével testreszabhatja az oszlopok szélességét és a halmozási sorrendet.

A vásárlásmező modul a termék címét, leírását, árát és értékeléseit jeleníti meg. Ezenkívül a vevők a különböző termékattribútumokkal rendelkező termékváltozatokat is választhatnak, például a méret, a stílus és a szín. Egy termékváltozat kiválasztásakor a program frissíti a vásárlásmezőbe tartozó egyéb tulajdonságokat (például a termék leírását és a képeket) a változat adatainak megjelenítéséhez. 

A program mennyiségi választót biztosít, így a vevők meghatározhatják a beszerzésre kerülő cikkek mennyiségét. A maximálisan vásárolható mennyiség a webhely beállításai között adható meg.

A vásárlásmezőből a vevők olyan műveleteket is hajthatnak végre, mint például a termékek kosárba történő hozzáadása, egy termék kívánságlistához való hozzáadása, és átvételi hely kiválasztása. Ezek a műveletek a termékre vagy a termékváltozatra vonatkozóan is elvégezhetők. Ha terméket szeretne hozzáadni egy kívánságlistahoz, akkor a vevőnek be kell jelentkeznie.

A témák segítségével eltávolíthatja vagy megváltoztathatja a vásárlásmező terméktulajdonságainak és a műveleti vezérlőknek a sorrendjét. 

## <a name="module-properties"></a>Modul tulajdonságai

- **Címsorcímke** – ez a tulajdonság határozza meg a termék címének címsorcímkéjét. Ha a vásárlásmező a lap felső részén van, a tulajdonságot a **H1** értékre kell állítania a hozzáférhetőségi szabványok teljesítése érdekében. 

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>A vásárlásmező modulban használható modulok

- **Médiatár** – Ez a modul a termék képeinek bemutatására szolgál a termék részletes lapján. Egy vagy több képet is támogathat. Támogatja a miniatűr képeket is. A miniatűr képek vízszintes (a kép alatti sorként) vagy függőleges (a kép melletti oszlopként) elrendezésben is megadhatók. A médiatár modul a vásárlásmező modul **Média** helyén adható hozzá. Jelenleg csak képeket támogat. 
- **Áruházválasztó** – Ez a modul felsorolja azokat a közeli áruházakat, ahol a cikkek elérhetők és felvehetők. Ez lehetővé teszi a felhasználók számára, hogy a közelben levő üzleteket megtalálják. A modullal kapcsolatos további tudnivalókat lásd: [Áruházválasztó modul](store-selector.md).

## <a name="buy-box-module-settings"></a>Vásárlásmező modul beállításai

A vásárlásmező-modulok következő beállításai konfigurálhatók a **Webhelybeállítások \> Bővítmények** pontban:

- **Kosár mennyiségi korlátja** – Ez a tulajdonság megadja az egyes cikkek kosárhoz adható maximális számát. Előfordulhat például, hogy egy kiskereskedő úgy dönt, hogy egyetlen tranzakcióban csak 10 terméket lehet értékesíteni.
- **Készlet** – A készletbeállítások alkalmazásával kapcsolatban a következő témakör tartalmaz további tájékoztatást: [Készletbeállítások alkalmazása](inventory-settings.md).
- **Hozzáadás a kosárhoz** – Ezzel a tulajdonsággal lehet meghatározni, mi történjen, miután egy cikket a kosárhoz adtak. A lehetséges értékek **Navigálás a kosárhoz**, **Ne navigáljon a kosárhoz** és **Értesítések megjelenítése**. Ha az érték **Navigáció a kosárhoz**, akkor a felhasználók a kosár oldalra lesznek küldve, miután hozzáadtak egy cikket. Ha az érték **Ne navigáljon a kosárhoz**, akkor a felhasználók nem lesznek a kosár oldalra küldve, miután hozzáadtak egy cikket. Ha az érték az **Értesítések megjelenítése**, akkor a felhasználók visszaigazoló értesítést kapnak és tovább böngészhetnek a termék részletei oldalon. 

    A következő kép egy példát mutat egy „kosárhoz adva” visszaigazolási értesítésre a Fabrikam oldalon.

    ![Példa egy értesítési modulra](./media/ecommerce-addtocart-notifications.PNG)

## <a name="commerce-scale-unit-interaction"></a>Commerce Scale Unit-interakció

A vásárlásmező-modul a termék adatait a Commerce Scale Unit alkalmazásprogramozási felületek (API-k) használatával olvassa be. Az termék részletes lapjáról származó termékazonosító az összes információ lekérdezésére szolgál.

## <a name="add-a-buy-box-module-to-a-page"></a>Vásárlásmező modul felvétele egy oldalra

A vásárlásmező modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Lépjen az **Oldaltöredékek** pontra, majd válassza az **Új** lehetőséget új töredék létrehozásához.
1. Az **Új oldaltöredék** párbeszédablakban válassza ki a **Vásárlásmező** modult.
1. Az **Oldaltöredék neve** pontban adja meg a **Vásárlásmező-töredék** nevét, majd válassza az **OK** lehetőséget.
1. Válassza ki a három pont (**...**) elemet a **Médiagaléria** helyén, amely tartalmazza a váráslásmező modult, majd válassza a **Modul hozzáadása** lehetőséget.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki a **Médiagaléria** modult, majd kattintson az **OK** gombra.
1. Válassza ki a három pont (**...**) elemet az **Áruházválasztó** helyén, amely tartalmazza a váráslásmező modult, majd válassza a **Modul hozzáadása** lehetőséget.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Áruházválasztó** modult, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.
1. Az **Új sablon** párbeszédablakban a **Sablon neve** alatt adja meg a **PDP-sablon** elemet, majd válassza az **OK** gombot.
1. A **Törzs** helyben válassza a három pont (**…**) gombot, majd válassza az **Modul hozzáadása** elemet.
1. A **Modul hozzáadása** párbeszédpanelen válassza ki az **Alapértelmezett oldal** modult, majd kattintson az **OK** gombra.
1. Az alapértelmezett lap **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Oldaltöredék hozzáadása** elemet.
1. Az **Oldaltöredék kiválasztása** párbeszédpanelen válassza ki a **Vásárlásmező töredék** töredékét, amelyet korábban hozott létre majd kattintson az **OK** gombra.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. A **Sablon kiválasztása** párbeszédpanelen válassza ki a **PDP-sablon** sablonját. Az **Oldal neve** alatta adja meg a **PDP-oldalt**, majd kattintson az **OK** gombra.
1. Az új oldal **Fő** helyén válassza ki a három pont (**…**) gombot, majd válassza a **Oldaltöredék hozzáadása** elemet.
1. Az **Oldaltöredék kiválasztása** párbeszédpanelen válassza ki a **Vásárlásmező töredék** töredékét, amelyet korábban hozott létre majd kattintson az **OK** gombra.
1. Mentse a lapot, és tekintse meg az előnézetét. Hozzáadja a **?productid=&lt;product id&gt;** lekérdezési karakterlánc paramétert az előnézeti lap URL-címéhez. A termékkontextus így az előnézeti lap betöltésére és megjelenítésére kerül felhasználásra.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez. A termék részletes lapján meg kell jelennie vásárlásmezőnek.

## <a name="additional-resources"></a>További erőforrások

[Kezdő csomag áttekintése](starter-kit-overview.md)

[Üzletkiválasztó modul](store-selector.md)

[Tárolómodul](add-container-module.md)

[Kosármodul](add-cart-module.md)

[Kosárikon modul](cart-icon-module.md)

[Fizetésmodul](add-checkout-module.md)

[Rendelésmegerősítési modul](order-confirmation-module.md)

[Fejlécmodul](author-header-module.md)

[Láblécmodul](author-footer-module.md)

[Kiskereskedelmi csatornák készletelérhetőségének kiszámítása](calculated-inventory-retail-channels.md)
