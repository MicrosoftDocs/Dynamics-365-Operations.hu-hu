---
title: Üzletválasztó modul
description: Ez a cikk az üzletválasztó modulra vonatkozik, és bemutatja, hogyan lehet a webhely lapjaihoz hozzáadni Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
manager: annbe
ms.openlocfilehash: aa3aed837072cb6c3d4f7f92bec2f4b700408cf7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268340"
---
# <a name="store-selector-module"></a>Üzletválasztó modul

[!include [banner](includes/banner.md)]

Ez a cikk az üzletválasztó modulra vonatkozik, és bemutatja, hogyan lehet a webhely lapjaihoz hozzáadni Microsoft Dynamics 365 Commerce.

A vevők az üzletválasztó modulban kiválaszthatják, hogy melyik üzletben szeretnék felvenni a kiválasztott terméket az online vásárlás után. A Commerce 10.0.13 verziójában az üzletválasztó modul olyan további képességeket is tartalmaz, amelyek bemutatják az **Üzlet keresése** oldalt, ahol megjelennek a közelben található üzletek.

Az üzletválasztó modul lehetővé teszi a felhasználók számára, hogy beírjanak egy helyet (város, megye, cím stb.) a keresési sugárban lévő üzletek megtalálásához. A modul első megnyitásakor a program a vevő böngészőjének helyét használja a boltok megtalálásához (ha hozzájárulnak).

## <a name="store-selector-module-usage"></a>Üzletválasztó modul felhasználása

- Egy üzletválasztó modul használható a termék részletei oldalon (PDP), ahol kiválaszthatja az áruátvételi üzletet.
- Egy üzletválasztó modul használható a kosár oldalon, ahol kiválaszthatja az áruátvételi üzletet.
- Az üzletválasztó modul használható olyan különálló lapon, amely az összes rendelkezésre álló üzletet megjeleníti.

## <a name="fulfillment-group-setup-in-commerce-headquarters"></a>Teljesítési csoportok beállítása a Commerce központi felületén

Ahhoz, hogy az üzletválasztó megjelenítse az elérhető üzleteket, a teljesítési csoportot be kell állítani a Commerce központjában. További információ: [Teljesítési csoportok beállítása](customer-orders-overview.md#set-up-fulfillment-groups).

Ezenkívül a teljesítési csoportba sorolt minden egyes üzlethez meg kell határozni az üzlet helyének földrajzi szélességét és földrajzi szélességét is a központban.

Az üzlet helyének földrajzi hosszúságának és szélességének beállításához a Commerce központi felületén kövesse az alábbi lépéseket.

1. Ugrás a következő lehetőségre: **Készletgazdálkodás \> Beállítás \> Készlet részletezése**.
1. Válassza ki a raktár helyét a bal ablaktáblában.
1. Válassza a **Címek** gyorslapon a **Speciális** lehetőséget.

    ![Példa az üzlet a részleteire a központban.](./media/Store-address.png)

1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Adja meg az **Általános** gyorslapon a **Földrajzi szélesség** és a **Földrajzi hosszúság** értékét.

    ![Példa az áruház földrajzi szélességi és földrajzi hosszúsági beállítására a központban.](./media/Store-latitude-longitude.png)

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget. 

### <a name="hide-a-store-from-the-store-selector-module"></a>Üzlet elrejtése az üzletválasztó modulban

A teljesítőcsoportban található üzletek némelyike nem lehet érvényes felvételi hely. A Commerce Headquarters alábbi lépéseit követve gondoskodhatja arról, hogy csak érvényes felvételi helyek jelenjenek meg beállításként az üzletválasztó modulban.

1. Menjen a **Retail and Commerce \> telepítő \> Minden üzlet beállítási csoportjaihoz \>**.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A **Beállítás** helyen minden olyan üzlet számára, amely nem érvényes felvételi hely, **törölje** a Felvétel helye jelölőnégyzetet.
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. Futtassa a 1070-es **csatorna-konfiguráció elosztási** ütemezési feladatát.

## <a name="bing-maps-integration"></a>Bing Maps – integráció

Az üzletválasztó modul integrálva van a [Bing Maps REST alkalmazásfejlesztési felületei (API)](/bingmaps/rest-services/) funkcióval a Bing geokódolási és az Automatikus javaslat szolgáltatásainak használatához. A Bing Maps API-kulcsot kötelező megadni, és hozzá kell adni a Commerce központ megosztott paraméterei oldalhoz. A geokódolási API a helyet a hosszúsági és a szélességi adatok alapján alakítja értékekre. Az automatikusan javasolt API-val való integráció a keresési javaslatok megjelenítésére szolgál, amikor a felhasználók helyeket adnak meg a keresési mezőben.

Az Autosuggest REST API esetében gondoskodni kell arról, hogy a webhely tartalmának biztonsági házirendjében (CSP) a következő leképezési URL-címeket engedélyezzék. Ez a beállítás a Commerce webhelykészítőben végezhető el azzal, ha engedélyezett URL-címeket ad a webhely CSP-utasításokhoz (például **img-src**). További információ: [Tartalomra vonatkozó biztonsági irányelv (CSP)](manage-csp.md). 

- A **connect-src** utasításhoz adja hozzá a **&#42;.bing.com** kiterjesztést.
- Az **img-src** utasításhoz adja hozzá a **&#42;virtualearth.net** kiterjesztést.
- A **script-src** utasításhoz **adja hozzá a &#42;.bing.com, &#42;.virtualearth.net** kiterjesztést.
- A **script style-src** utasításhoz adja hozzá a **&#42;.bing.com** kiterjesztést.

## <a name="pickup-in-store-mode"></a>Felvétel az üzletben mód

Az üzletválasztó modul támogatja a **Felvétel az üzletben** módot, amely megmutatja azon üzletek listáját, amelyeknél a termék átvehető. A listán szereplő üzletek nyitvatartását és készletét is megjeleníti. Ha a termék szállítási módja a kiválasztott üzletnél **átvétel** módban van, akkor az üzletválasztó modulban meg kell adni a termék kontextusát a termék elérhetőségének kiszámításához, illetve ahhoz, hogy a felhasználó betehesse a terméket a kosarába. További információ: [Készletbeállítások](inventory-settings.md). 

Az üzletválasztó modul hozzáadható a PDP, amelyben megtekinthetők azok az üzletek, amelyekben a termék rendelkezésre áll felvételre. A kosár modulhoz is hozzáadhatók. Ebben az esetben az üzletválasztó modul a kosár minden sorához megjeleníti a felvételi beállításokat. Az üzletválasztó modul hozzáadható más oldalakhoz vagy modulokhoz a bővítményeken és a testreszabásokon keresztül.

A forgatókönyv működéséhez a termékeket az **átvétel** szállítási móddal kell használni. Máskülönben a modul nem fog megjelenni a megfelelő termékoldalakon. A szállítási mód konfigurálásával kapcsolatos további információkat lásd: [Szállítási módok beállítása](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

A következő kép a PDP-ben használt üzletválasztó modul egy példáját jeleníti meg.

![Példa egy üzletválasztó modulra, ami a PDP-ben van használva.](./media/BOPIS.PNG)

> [!NOTE]
> A 10.0.16-os és újabb verzióban egy új funkció engedélyezhető, amely lehetővé teszi a szervezet számára, hogy több szállítási módot határozzon meg az ügyfelek számára.  Ha ez a funkció engedélyezve van, az áruházválasztó és az e-kereskedelem egyéb moduljai javulni fognak, hogy a vásárló a potenciálisan több felvételi szállítási lehetőség közül választhasson, ha be van állítva.  A funkcióról többet is megtudhat, olvassa el [ezt a dokumentációt](./multiple-pickup-modes.md). 

## <a name="find-stores-mode"></a>Üzletek keresése mód

Az üzletválasztó modul az **Üzletek keresése** módot is támogatja. Ez a mód használható egy üzlethely oldal létrehozásához, amely megjeleníti az elérhető üzleteket és azok adatait. Ebben a módban az üzletválasztó modul a termék kontextusa nélkül működik, és különálló modulként használhatja a webhely bármely oldalán. Ezenkívül, ha a modulnál be vannak kapcsolva a megfelelő beállítások, a felhasználók az üzletet preferált üzletként is kiválaszthatják. Ha egy üzletet a felhasználó preferált üzletként választ, akkor az üzlet azonosítója a böngésző sütiben marad. Ezért a felhasználónak el kell fogadnia egy sütibeleegyezés üzenetet.

A következő ábra egy üzletválasztó modul példáját mutatja be, amely az üzlethelyek lap térkép moduljával együtt használható.

![Példa egy üzletválasztó modulra, és egy térkép modulra egy tárolási helyek lapon.](./media/ecommerce-Storelocator.PNG)

## <a name="render-a-map"></a>Térkép renderelése

Az üzletválasztó modul a térkép modullal együtt használva egy térképen jelenítheti mge az üzlethelyeket. A térkép modullal kapcsolatos további tudnivalókat lásd: [Térkép modul](map-module.md)

## <a name="store-selector-module-properties"></a>Az üzletkiválasztó modul tulajdonságai

| Tulajdonság neve | Érték | Leírás |
|---------------|-------|-------------|
| Címsor | Szöveg | A modul címe. |
| Mód | **Üzletek keresése** vagy **Átvétel üzletben** | Az **Üzletek keresése** mód megjeleníti az elérhető üzleteket. Az **Átvétel üzletben** módban lehetővé teszi a felhasználóknak, hogy kiválasszanak egy üzletet az átvételhez. |
| Stílus | **Párbeszéd** vagy **Szövegköz** | A modult akár szövegközi- vagy párbeszédpanellé is lehet renderelni. |
| Beállítás preferált üzletként | **Igaz** vagy **Hamis** | Ha a tulajdonság értéke **Igaz**, akkor a felhasználók megadhatnak preferált üzletet. Ez a funkció megköveteli, hogy a felhasználók elfogadják a sütibeleegyezés üzenetet. |
| Minden üzlet megjelenítése | **Igaz** vagy **Hamis** | Ha a tulajdonság értéke **Igaz**, a felhasználók kikerülhetik a **Keresési sugár** tulajdonságot, és megtekinthetik az összes üzletet. |
| Az Automatikus javaslat beállításai: max. eredmények | Szám | Ez a tulajdonság határozza meg, hogy legfeljebb hány olyan automatikus javaslat érhető el, amely a Bing automatikus javaslat API-n keresztül megjeleníthető. |
| Keresési sugár | Szám | Ez a tulajdonság az üzletek keresési sugarát határozza meg (mérföldben). Ha nincs megadva érték, akkor a program az alapértelmezett 50 mérföldes keresési sugarat használja. |
| Szolgáltatási feltételek | URL-cím |  Ez a tulajdonság meghatározza a szolgáltatási feltételek URL-címét, amely a Bing Maps szolgáltatás használatához szükséges. |

## <a name="site-settings"></a>Hely beállításai

Az üzletválasztó modulban figyelembe veszi a [Termék hozzáadása a kosárhoz beállítást](add-cart-settings.md). Miután az üzletválasztó modulból egy cikket hozzáadtak a kosárhoz, a webhely felhasználói látni fogják a megfelelő konfigurált munkafolyamatokat.

## <a name="add-a-store-selector-module-to-a-page"></a>Üzletválasztó modul hozzáadása a laphoz

A **Felvétel áruházban** módban a modul csak a PDP-k és a kosár oldalain használható. A modul tulajdonsága ablaktáblán a **Felvétel üzletben** módot kell beállítania.

- Az üzletválasztó modulnak egy vásárlásmező modulhoz való hozzáadásával kapcsolatos tudnivalókat lásd: [Vásárlásmező](add-buy-box.md) modul. 
- Az üzletválasztó modulnak egy kosármodulhoz való hozzáadásával kapcsolatos tudnivalókat lásd: [Kosár modul](add-cart-module.md).

A következő lépések szerint konfigurálhatja az üzletválasztó modult az üzletek helyoldalán elérhető áruházak megjelenítése érdekében, mint az ebben a cikkben korábban látható ábra.

1. Lépjen a **Sablonok** pontra, majd új sablon készítéséhez válassza az **Új** elemet.
1. Az Új **sablon párbeszédpanel** Sablon neve területén **adja** meg a **Marketingsablont**, majd válassza az **OK gombra.**
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Lépjen az **Oldalak** pontra, majd válassza az **Új** lehetőséget új oldal létrehozásához.
1. Az Új lap **létrehozása párbeszédpanel** Lap neve **csoportban** adja **meg** az áruházi helyeket, majd válassza **a Tovább gombra.**
1. A **Sablon kiválasztása mezőben válassza** ki **a létrehozott marketingsablont**, majd válassza a Tovább **gombra**.
1. Az **Elrendezés kiválasztása oldalon válasszon** egy lapelrendezést (például **rugalmas** elrendezés), majd válassza **a Tovább lehetőséget**.
1. Az Ellenőrzés **és befejezés lapon** ellenőrizze a lap konfigurációját. Ha szerkesztenie kell a lap adatait, válassza a Vissza **lehetőséget**. Ha a lap adatai helyesek, válassza a Létrehozás **lapot**. 
1. Az új **lap főbejáratában** válassza ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a** Tároló modult, majd válassza az **OK gombra.**
1. A tárolóhelyen **válassza** ki a három pontból (**...**), majd válassza a **Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Tároló 2 oszlop modult**, majd kattintson az **OK gombra**.
1. A modul tulajdonságai ablaktáblában a **Szélesség** értéket állítsa **Tároló kitöltése** lehetőségre.
1. Az **X-Small megtekintési terület oszlop konfigurációja** értéket állítsa **100%**-ra.
1. A **Small megtekintési terület oszlop konfigurációja** értéket állítsa **100%**-ra.
1. A **Medium megtekintési terület oszlop konfigurációja** értéket állítsa **33 % 67 %**-ra.
1. A **Large megtekintési terület oszlop konfigurációja** értéket állítsa **33 % 67 %**-ra.
1. A kétoszlopos **tárolóban** válassza ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **az** Üzletválasztó modult, majd kattintson az **OK gombra**.
1. A modul tulajdonságai ablaktáblában a **Mód** értéket állítsa **Üzletek keresése** lehetőségre.
1. A **keresési sugár** érték beállítása mérföldben.
1. Egyéb tulajdonságokat, például a **Preferált üzlet beállítása**, az **Összes üzlet megjelenítése**, valamint az **Automatikus javaslat engedélyezése** tetszés szerint állíthat be.
1. A kétoszlopos **tárolóban** válassza ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Leképezés** modult, majd kattintson az **OK gombra**.
1. A modul tulajdonságai ablaktáblában adja meg a szükséges további tulajdonságokat.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot az oldal ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
 
## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Vásárlásmező-modul](add-buy-box.md)

[Kosármodul](add-cart-module.md)

[A PDP rövid bemutatása](quick-tour-pdp.md)

[A kosár és a pénztár rövid bemutatása](quick-tour-cart-checkout.md)

[Szállítási módok beállítása](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[A szervezetéhez tartozó Bing Térképek kezelése](dev-itpro/manage-bing-maps.md)

[Bing Térképek REST API-k](/bingmaps/rest-services/)

[Térképek modul](map-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
