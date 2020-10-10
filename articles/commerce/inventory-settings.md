---
title: Készlet beállításainak alkalmazása
description: Ez a témakör a készlet beállításaival foglalkozik, és leírja, hogy hogyan kell alkalmazni azokat a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: d7d25fd62efca52dd2d60ed3435104c3507a1d19
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817609"
---
# <a name="apply-inventory-settings"></a>Készlet beállításainak alkalmazása

[!include [banner](includes/banner.md)]

Ez a témakör a készlet beállításaival foglalkozik, és leírja, hogy hogyan kell alkalmazni azokat a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A készlet beállításai határozzák meg, hogy ellenőrizni kell-e a készletet, mielőtt termékek kerülnek a kosárba. Meghatározzák a készlettel kapcsolatos értékesítési üzeneteket is, például a "Készleten" és a "Már csak néhány maradt". Ez a beállítás gondoskodik arról, hogy a termék nem vásárolható meg, ha elfogyott.

A Dynamics 365 Commerce becsléseket biztosít a termékek aktuális rendelkezésre állásáról. A becsült aktuális elérhetőségek számításával kapcsolatos további tudnivalókat lásd: [Kiskereskedelmi csatornák készletelérhetőségének kiszámítása](calculated-inventory-retail-channels.md).

A Commerce webhelykészítőben egy termékhez vagy egy kategóriához lehet definiálni a készlet-küszöbértékeket és a -tartományokat. Ezek határozzák meg, hogy a készlet minősíthető készleten, alacsony készlet vagy elfogyott értékkel. További részletek: [A készletpufferek és a készlet szintjeinek konfigurálása](inventory-buffers-levels.md).

> [!NOTE]
> A Dynamics 365 Commerce 10.0.12-kiadásban elérhető a készletküszöbök és a -tartományok támogatása.

## <a name="inventory-settings"></a>Készletbeállítások

A Commerce alkalmazásban a készletbeállítások a **Webhelybeállítások \> Bővítmények \> Készletkezelés** alatt adhatók meg a webhelykészítőben. Négy készletbeállítás van, amelyek közül az egyik elavult:

- **Készletellenőrzés engedélyezése az alkalmazásban** – Ez a beállítás bekapcsolja a termékkészlet ellenőrzését. A vásárlás mező, a kosár és az átvétel az üzletben modul is ellenőrzi a termék készletét, és lehetővé teszi a terméknek a kosárba történő felvételét, ha a készlet elérhető.
- **Készletszint alapja** – Ez a beállítás határozza meg a készletszint számításának módját. A rendelkezésre álló értékek a **Teljes rendelkezésre álló**, a **Rendelkezésre álló tényleges** és az **Elfogyott küszöbérték**. A Commerce webhelykészítőben minden termékhez ás kategóriához lehet definiálni a készletküszöbértéket és -tartományokat. A készlet API-k termékkészlet-információkat adnak vissza mind a **Teljes rendelkezésre álló** tulajdonság, mind a **Rendelkezésre álló tényleges** tulajdonság esetében. A kiskereskedő dönti el, hogy a **Teljes rendelkezésre álló** vagy a **Rendelkezésre álló tényleges** érték kerüljön felhasználásra a készletszám és a vonatkozó raktáron és elfogyott állapotok megállapításához.

    A **Készletszint alapja** beállítás **Elfogyott küszöbérték** értéke egy régi (örökölt), elavult érték. Ha ki van választva, akkor a leltározás a **Teljes rendelkezésre álló** érték eredményei alapján történik, de a küszöbértéket a későbbiekben meghatározott **Elfogyott küszöbérték** numerikus beállítása határozza meg. Ez a küszöbérték-beállítás minden termékre vonatkozik az e-Commerce webhelyen. Ha a készlet nem éri el a küszöbértéket, akkor a termék elfogyottnak minősül. Ellenkező esetben raktáron levőnek kell tekinteni. Az **Elfogyott küszöbérték** érték képességei korlátozottak, ezért a használata nem ajánlott a 10.0.12-es és későbbi verziókban.

- **Készlettartományok** – Ez a beállítás határozza meg a készlettartományokat, amelyekhez üzenetek kerülnek megjelenítésre a helyi modulok esetében. Csak akkor alkalmazható, ha a **Teljes rendelkezésre álló** érték vagy a **Rendelkezésre álló tényleges** érték van kiválasztva a **Készletszint alapja** számára. A rendelkezésre álló értékek a **Mind**, az **Alacsony és elfogyott**, valamint az **Elfogyott**.

    - Ha a **Mind** van kiválasztva, akkor a program az összes készlettartomány esetében megjelenít üzeneteket a raktáron állapottól („Elérhető üzenet”) az elfogyott állapotig („Elfogyott” üzenet).
    - Ha az **Alacsony és elfogyott** van kiválasztva, akkor a program az összes készlettartomány esetében megjelenít üzeneteket a raktáron állapotot („Elérhető üzenet”) kivéve.
    - Ha az **Elfogyott** lehetőség van kiválasztva, akkor csak az „Elfogyott” üzenet jelenik meg.

- **Elfogyott küszöbérték** – Ez a régi numerikus beállítás csak akkor lép érvénybe, ha az **Elfogyott küszöbérték** érték van kiválasztva a **Készletszint alapja** beállítás számára.

> [!IMPORTANT] 
> Ezek a beállítások a Dynamics 365 Commerce 10.0.12-es kiadásában érhetők el. Ha a Dynamics 365 Commerce egy korábbi verziójáról frissít, akkor manuálisan kell frissítenie az appsettings.json fájlt. Az appsettings.json fájlok frissítésével kapcsolatos tudnivalókat lásd az [SDK- és modulkönyvtár-frissítések](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file) témakörben.

## <a name="modules-that-use-inventory-settings"></a>A készletbeállításokat használó modulok

A vásárlásmező, kívánságlista, üzletválasztó, kosár és kosárikon modulok készletbeállításokat használnak a készlettartományok és az üzenetek megjelenítéséhez.

A következő képen a termék részleteit tartalmazó oldal (PDP) egy példája látható, amely egy raktáron lévő ("elérhető") üzenetet jelenít meg.

![Egy olyan PDP-modul példája, amely tartalmaz egy készleten üzenetet.](./media/pdp-InStock.png)

A következő képen a termék részleteit tartalmazó oldal (PDP) egy példája látható, amely egy „Elfogyott” üzenetet jelenít meg.

![Egy olyan PDP-modul példája, amely tartalmaz egy elfogyott üzenetet.](./media/pdp-outofstock.png)

A következő képen a kosár egy példája látható, amely egy raktáron („Elérhető”) üzenetet jelenít meg.

![Egy olyan kosármodul példája, amely tartalmaz egy készleten üzenetet.](./media/cart-instock.png)

## <a name="additional-resources"></a>További erőforrások

[Modulkönyvtár – áttekintés](starter-kit-overview.md)

[Készletpufferek és készletszintek konfigurálása](inventory-buffers-levels.md)

[Kosármodul](add-cart-module.md)

[Vásárlásmező-modul](add-buy-box.md)

[Számlakezelési oldalak és modulok](account-management.md)

[Üzletválasztó modul](store-selector.md)

[SDK- és modulkönyvtár-frissítések](e-commerce-extensibility/sdk-updates.md)
