---
title: Útkövetési modul
description: Ez a témakör az útkövető modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: aa7f6e2f2b15c3e5d89cd645b3f1cc4c83c5b8d9
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780334"
---
# <a name="breadcrumb-module"></a>Útkövetési modul

[!include [banner](includes/banner.md)]

Ez a témakör az útkövető modulokkal foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

Az útkövetési modulok másodlagos navigálás biztosítására szolgálnak a webhelyoldalakon. Általában a lap tetején láthatók, a fejléc alatt. Bár az útkövetési modulok bármilyen lapra hozzáadhatók, leggyakrabban a termékrészletek oldalakon (PDP-k) vannak használatban, a termékkategóriák hierarchiáját megjelenítéséhez, és gyors mozgást biztosítanak az oldalon. Az útkövetési modul egy „Visszatérés az eredményekhez" hivatkozás megjelenítésére is használható, amikor a felhasználók megnyitnak egy PDP-t a keresési vagy listaoldalon. Ily módon a felhasználók gyorsan visszatérhetnek a szűrt listaoldalukra a vásárlás folytatásához.

A termékkategóriák környezetét tartalmazó lapokon, például a PDP-k és a kategóriaoldalakon az útkövetési modul a kategória-hierarchiát jeleníti meg. A kategóriakörnyezettel nem rendelkező oldalaknál az útkövetési modul alapértelmezésben a **&lt;Webhely gyökere&gt; / &lt;Aktuális oldal&gt;** helyet jeleníti meg. Az útkövetési modulokat a webhely más típusú oldalain is lehet konfigurálni, hogy a webhely adott oldalaira mutató hivatkozásokat jelenítsen meg.

> [!NOTE]
> Az útkövető modul a Dynamics 365 Commerce 10.0.12-es verziójában érhető el.

A következő kép egy olyan útkövető modult mutat be, amely a kategóriahierarchiát jeleníti meg egy PDP-n.

![Példa egy útkövető modulra.](./media/ecommerce-breadcrumb.PNG)

## <a name="breadcrumb-module-settings"></a>Útkövetési modul beállításai

Az útkövetési modul az **Útkövető megjelenítési típus PDP** beállításon alapul, amely a webhelykészítő **Oldalbeállítások \> bővítmények** részében van konfigurálva. Ennek a beállításnak három lehetséges értéke van:

- **Kategóriahierarchia megjelenítése** – Ha ez az érték van kiválasztva, akkor a útkövetési modul a PDP-ben megtekintett termék teljes kategóriahierarchiáját jeleníti meg.
- **Megjelenítés vissza az eredményekhez** – Ha ez az érték van kiválasztva, akkor a navigációs modul a PDP-ben egy „Visszatérés az eredményekhez” hivatkozást jelenít meg, ha a felhasználó egy olyan modulból nyitotta meg a PDP-t, amely lehetővé teszi a „Visszatérés az eredményekhez” linket. Ez a funkció akkor érhető el, ha a felhasználók a kategória-, keresés-, lista-és ajánlás listaoldalakról navigálnak. Ennek a funkciónak a támogatásához a termékgyűjtemény és a keresési eredmények modulban van egy **Visszalépés engedélyezése az eredményekhez a PDP-ben** tulajdonság. Ez a tulajdonság biztosítja a rugalmasságot annak meghatározására, hogy mely modulok támogatják a „Visszatérés az eredményekhez” linket a PDP-ben. Ha például a **Megjelenítés vissza az eredményekhez** van kiválasztva az útkövető modul **Útkövető megjelenítési típus PDP-n** beállításban, és a **Visszalépés engedélyezése az eredményekhez a PDP-ben** ki van választva a keresési oldal találatok moduljában, a „Vissza az eredményekhez” hivatkozás meg lesz jelenítve, amikor a felhasználók a keresési oldalról a PDP-re navigálnak.
- **Kategóriahierarchia és visszatérés az eredményekhez megjelenítése** – Ez az érték az előző kettő kombinációja. Ha ez az érték ki van választva, akkor a navigációs modul a teljes kategóriahierarchiát és a „Visszatérés az eredményekhez” hivatkozást is megjeleníti (ha be van állítva) egy PDP-ben.

> [!IMPORTANT]
> Ezek a beállítások a Dynamics 365 Commerce 10.0.12-es kiadásában érhetők el. Ha a Dynamics 365 Commerce egy korábbi verziójáról frissít, akkor manuálisan kell frissítenie az appsettings.json fájlt. Az appsettings.json fájlok frissítésével kapcsolatos tudnivalókat lásd az [SDK- és modulkönyvtár-frissítések](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file) témakörben.

## <a name="breadcrumb-module-properties"></a>Útkövetési modul tulajdonságai

| Tulajdonság neve | Értékek | Leírás |
|---------------|--------|-------------|
| Gyökér | Szöveg vagy hivatkozás| Ez a választható tulajdonság azt határozza meg a hivatkozás szövegét és a hivatkozás célját az ütkövető oldalgyökeréhez. Ha ez a tulajdonság nincs beállítva, akkor nem lesz gyökér meghatározva. |
| Útkövető hivatkozása | Összekapcsolás | Ez a választható tulajdonság határozza meg a manuálisan konfigurált útkövető hivatkozásait, ha szükség van ezekre a hivatkozásokra. A hivatkozások a listán szereplő sorrendben jelennek meg. |

## <a name="add-a-breadcrumb-module-to-a-new-page"></a>Útkövető modul hozzáadása egy új oldalhoz

Egy útkövetési modul a PDP-re való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Nyissa meg a **Webhelybeállítások \> Bővítmények** elemet, majd az **Útkövető megjelenítési típus PDP-n** beállításnál válassza a **Kategória-hierarchia megjelenítése** parancsot.
1. Nyissa meg a **Sablonok** lehetőséget, és válassza ki a PDP-sablont.
1. A tárolóhely **modult** tartalmazó tárolóban válassza ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Navigációs modult**, majd kattintson az **OK gombra**.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Ugorjon a **Lapok** lehetőségre, és nyissa meg a PDP-sablont használó PDP-t. Ha még nincs egy PDP sem, hozzon létre egyet.
1. A tárolóhely **modult** tartalmazó tárolóban válassza ki a három pontból (**...**), **majd válassza a Modul hozzáadása lehetőséget**.
1. A Modulok **kiválasztása párbeszédpanelen** válassza ki **a Navigációs modult**, majd kattintson az **OK gombra**.
1. Az **Útkövető** hely tulajdonságok panelén a **Gyökér** alatt válassz a **Hivatkozás szövege** lehetőséget.
1. A **Hivatkozás szövege** párbeszédpanelen írja be a **Kezdőlap** kifejezést, majd a **Hivatkozás célja** területen válassza a **Hivatkozás hozzáadása** lehetőséget.
1. A **Hivatkozás hozzáadása** párbeszédpanelen jelölje ki az útkövető gyökerét, majd kattintson az **OK** gombra.
1. Válassza a **Mentés** lehetőséget, majd az oldal előnézetének megtekintéséhez az **Előnézet** elemet.
1. Válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.

## <a name="additional-resources"></a>További erőforrások

[Modultár áttekintése](starter-kit-overview.md)

[Navigációs menü modul](nav-menu-module.md)

[Webhelyválasztó modul](site-selector.md)

[Az alapértelmezett kategória-céloldal és keresési találatoldal áttekintése](category-search-page-overview.md)

[Termékgyűjtemény modulok](product-collection-module-overview.md)

[Vásárlásmező-modul](add-buy-box.md)

[SDK- és modulkönyvtár-frissítések](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
