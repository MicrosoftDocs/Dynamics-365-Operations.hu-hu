---
title: Készletre vonatkozó terméklista
description: Ez a cikk azt írja le, hogyan konfigurálják a szervezetek Microsoft Dynamics 365 Commerce az e-commerce webhelyük terméklistaoldalait úgy, hogy a készletben legyenek figyelembe vétele.
author: boycez
ms.date: 08/31/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2022-08-23
ms.openlocfilehash: e33a4dd8650ee2e371c51c5a19e955f2d2bdade2
ms.sourcegitcommit: 1d5cebea3e05b6d758cd01225ae7f566e05698d2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2022
ms.locfileid: "9405515"
---
# <a name="inventory-aware-product-listing"></a>Készletre vonatkozó terméklista

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Ez a cikk azt írja le, hogyan konfigurálják a szervezetek Microsoft Dynamics 365 Commerce az e-commerce webhelyük terméklistaoldalait úgy, hogy a készletben legyenek figyelembe vétele. A terméklistaoldalak kategória- és keresési eredményoldalakat tartalmaznak.

A vásárlók általában azt várják az e-commerce webhely teljes területén, hogy a készletben tudják, mi legyen a készleten, ha egy termék nincs készleten. A [Commerce modultár kategóriája](starter-kit-overview.md) és a keresési eredmények modulja úgy konfigurálható, hogy a készletadatok is beleszámadnak. Ily módon a következő tapasztalatokat szolgáltathatja:

- Készletszintű címkék megjelenítése a termékek mellett.
- A készleten nem található termékek elrejtése a terméklistáról.
- A készleten lévő termékek áthelyezése a terméklistaoldalak aljára.
- Készletalapú termékszűrés támogatása.

A tapasztalatok engedélyezéséhez először **engedélyeznie kell, hogy a Commerce Headquarters továbbfejlesztett e-Commerce** termékfelleltárási funkciója legyen a készletre vonatkozó funkció.

> [!NOTE]
> A Commerce rendszer 10.0.29-es **és** újabb verzióiban alapértelmezés szerint engedélyezve van a továbbfejlesztett e-Commerce termékfelleltárási funkció, amely a készletértesítést teszi lehetővé.

## <a name="set-up-product-attribute-for-inventory-availability"></a>Termékattribútum beállítása a készlet rendelkezésre állására

A készletre vonatkozó terméklista a termékattribútumok keretrendszerét használja. Előfeltételként egy külön termékattribútumnak kell létrejönnie a készlet elérhetőségi adatainak rögzítéséhez.

A következő lépések szerint állíthatja be a Commerce Headquarters készlet rendelkezésre állásának termékattribútumát.

1. Menjen a **Retail and Commerce \> Retail and Commerce it-termékekhez \>, és adja \> meg a készletszint termékattribútumainak feltöltését**.
1. **A Termékattribútumok** **feltöltése** a készletszinttel párbeszédpanel Termékattribútum és típusnév mezőjébe írja be a kijelölt termékattribútum egyéni nevét, amely a készletadatok rögzítésére fog létrejönni.
1. A készlet **rendelkezésre állása mező** alapján válassza ki azt a mennyiségtípust, amely alapján a készletszint-számításnak alapulni kell: **Rendelkezésre álló fizikai** **vagy Teljes rendelkezésre álló**.
1. A kötegelt feldolgozás **beállítása** Igen **beállításra**.
1. Válassza ki az **OK** lehetőséget.

> [!NOTE]
> Ha az e-commerce webhely lapjain egységes készletszint-számítást végez, győződjön meg róla, **·** **·** **hogy** ugyanazt a mennyiségtípust választja a Készlet rendelkezésre állása mező alapján a Készletszint-feladat feltöltése és a Készletszint a Commerce webhelyszerkesztőben beállított érték alapján.

A kijelölt termékattribútum létrehozása után a következő lépés az online csatorna attribútumának konfigurálása.

A Commerce Headquarters online csatornája attribútumainak konfigurálásánál hajtsa végre a következő lépéseket.

1. Nyissa meg a következőt: **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Csatornakategóriák és termékattribútumok**.
1. Az online csatorna kiválasztása a készletre vonatkozó terméklista-tapasztalat engedélyezéséhez.
1. Válasszon ki és nyisson meg egy társított attribútumcsoportot, majd adja hozzá az új termékattribútumot.
1. Menjen a **Retail and Commerce \> Retail and Commerce IT \> Distribution** ütemezéshez, **és futtassa a 1150** -es (**katalógus**- és katalógus-) feladatot. Javasoljuk, hogy ezt a feladatot ugyanolyan gyakorisággal ütemezi kötegfolyamatként, mint a **Termékattribútumok feltöltése készletszintű feladattal**.

> [!NOTE]
> A Commerce rendszer 10.0.26-os és korábbi verzióiban a **készlet elérhetőségi termékattribútumának attribútumcsoporthoz való hozzáadása után meg kell adni az Attribútum-metaadatok beállítása lehetőséget is,** majd be kell kapcsolnia az Attribútum megjelenítése csatornán **,** **·** **·** **beolvasásra, finomítható és lekérdezhető beállítások az új termékattribútumhoz.**

## <a name="configure-the-display-behavior-for-out-of-stock-products-on-product-listing-pages"></a>A készleten nem található termékek megjelenítési viselkedésének konfigurálása a terméklistaoldalakon

Miután az előző konfigurációs lépések mindegyikét befejezte, a kategória- és keresési eredményoldalak finomítói készlet alapú szűrőt fognak tartalmazni. Az oldalon megjelenő minden egyes termékcsemólyhoz megjelenik egy készletszintű címke.

A kategória és a keresés eredménylapja az alapszinten jeleníti meg a termékeket, nem pedig a termékváltozat szintjén. Az egyes termékekkel párhuzamosan megjelenített készletszint egy összesített készletszint, amelyet a termékváltozatok készletszintje határoz meg. A változat készletszintje a Commerce Headquarters online csatornája alapértelmezett raktárában található változat aktuális készlete alapján számítható ki. Az alaptermék készletszintje két lehetséges értékkel rendelkezik, amelyek a készleten vannak és a készleten nem található államoknak. Az alaptermék akkor minősül készleten nem készleten, ha az összes változata nincs készleten. Ellenkező esetben a termék készleten van. Az érték címkéje a készletszint-definícióból [van beolvasva](inventory-buffers-levels.md). Ha nincs megadva készletszint, az alapértelmezett címkék (angol nyelven) **Elérhetőek** és **Készleten lévőek**.

**A** Commerce Webhely-szerkesztő terméklistaoldalak beállításainál beállíthatja a készletbeállításokat, hogy a kategória és a keresési eredmények oldal hogyan jelenítsen meg készleten nem készleten található termékeket. További információk: [Készletbeállítások alkalmazása](inventory-settings.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
