---
title: Készletbeállítások alkalmazása
description: Ez a cikk a készletbeállításokat ismerteti, és bemutatja, hogyan lehet azokat alkalmazni a készletben Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 49310a44f8b9c636734e04d4eed9445384b55791
ms.sourcegitcommit: 1d5cebea3e05b6d758cd01225ae7f566e05698d2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2022
ms.locfileid: "9405320"
---
# <a name="apply-inventory-settings"></a>Készletbeállítások alkalmazása

[!include [banner](includes/banner.md)]

Ez a cikk a készletbeállításokat ismerteti, és bemutatja, hogyan lehet azokat alkalmazni a készletben Microsoft Dynamics 365 Commerce.

A készlet beállításai határozzák meg, hogy ellenőrizni kell-e a készletet, mielőtt termékek kerülnek a kosárba. Meghatározzák a készlettel kapcsolatos értékesítési üzeneteket is, például a "Készleten" és a "Már csak néhány maradt". Ez a beállítás gondoskodik arról, hogy a termék nem vásárolható meg, ha elfogyott.

A Dynamics 365 Commerce becsléseket biztosít a termékek aktuális rendelkezésre állásáról. A becsült aktuális elérhetőségek számításával kapcsolatos további tudnivalókat lásd: [Kiskereskedelmi csatornák készletelérhetőségének kiszámítása](calculated-inventory-retail-channels.md).

A Commerce webhelykészítőben egy termékhez vagy egy kategóriához lehet definiálni a készlet-küszöbértékeket és a -tartományokat. Ezek határozzák meg, hogy a készlet minősíthető készleten, alacsony készlet vagy elfogyott értékkel. További részletek: [A készletpufferek és a készlet szintjeinek konfigurálása](inventory-buffers-levels.md).

> [!NOTE]
> A Dynamics 365 Commerce 10.0.12-kiadásban elérhető a készletküszöbök és a -tartományok támogatása.

## <a name="inventory-settings"></a>Készletbeállítások

A Commerce alkalmazásban a készletbeállítások a **Webhelybeállítások \> Bővítmények \> Készletkezelés** alatt adhatók meg a webhelykészítőben. Hat készletbeállítás van, amelyek közül az egyik elavult:

- **Készletellenőrzés engedélyezése az alkalmazásban** – Ez a beállítás bekapcsolja a termékkészlet ellenőrzését. A vásárlás mező, a kosár és az átvétel az üzletben modul is ellenőrzi a termék készletét, és lehetővé teszi a terméknek a kosárba történő felvételét, ha a készlet elérhető.
- **Készletszint alapja** – Ez a beállítás határozza meg a készletszint számításának módját. A rendelkezésre álló értékek a **Teljes rendelkezésre álló**, a **Rendelkezésre álló tényleges** és az **Elfogyott küszöbérték**. A Commerce webhelykészítőben minden termékhez ás kategóriához lehet definiálni a készletküszöbértéket és -tartományokat. A készlet API-k termékkészlet-információkat adnak vissza mind a **Teljes rendelkezésre álló** tulajdonság, mind a **Rendelkezésre álló tényleges** tulajdonság esetében. A kiskereskedő dönti el, hogy a **Teljes rendelkezésre álló** vagy a **Rendelkezésre álló tényleges** érték kerüljön felhasználásra a készletszám és a vonatkozó raktáron és elfogyott állapotok megállapításához.

    A **Készletszint alapja** beállítás **Elfogyott küszöbérték** értéke egy régi (örökölt), elavult érték. Ha ki van választva, akkor a leltározás a **Teljes rendelkezésre álló** érték eredményei alapján történik, de a küszöbértéket a későbbiekben meghatározott **Elfogyott küszöbérték** numerikus beállítása határozza meg. Ez a küszöbérték-beállítás minden termékre vonatkozik az e-kereskedelmi webhelyen. Ha a készlet nem éri el a küszöbértéket, akkor a termék elfogyottnak minősül. Ellenkező esetben raktáron levőnek kell tekinteni. Az **Elfogyott küszöbérték** érték képességei korlátozottak, ezért a használata nem ajánlott a 10.0.12-es és későbbi verziókban.

- **Több raktár készletszintje** – Ez a beállítás lehetővé teszi a készletszint kiszámítását az alapértelmezett raktárhoz vagy több raktárhoz. Az **Egyedi raktár alapján** lehetőség az alapértelmezett raktár alapján számítja ki a készletszinteket. Másik lehetőségként az e-kereskedelmi webhely több raktárra is mutathat, hogy megkönnyítse a teljesítést. Ebben az esetben a készlet rendelkezésre állásának jelzésére a **Szállítási és kitárazási raktárak összesítése alapján** beállítás használható. Ha például egy vevő vásárol egy cikket, és a szállítási módként a „szállítás” lehetőséget választja, akkor a cikk a teljesítési csoport bármelyik raktárába szállítható, amelynek van rendelkezésre álló készlete. A termék részleteit tartalmazó oldal (PDP) a szállításhoz egy „Készleten” üzenetet fog küldeni, ha a teljesítő csoportban bármelyik rendelkezésre álló szállító raktárnak van készlete. 

    > [!IMPORTANT] 
    > A **Több raktár készletszintje** beállítás a Commerce 10.0.19-es verziójától érhető el. Ha a Commerce egy korábbi verziójáról frissít, akkor manuálisan kell frissítenie az appsettings.json fájlt. Az utasításokat lásd itt: [SDK- és modultár-frissítések](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

- **Terméklistaoldalak készletbeállításai** – Ez a beállítás meghatározza, hogy hogyan jelennek meg a nem készleten található termékek a terméklistákban, amelyeket a termékgyűjtemény és keresési előzmények modulok hoztak létre. Az elérhető értékek: **Megjelenítés sorrendben más termékekkel**, **A nem készleten lévő termékek elrejtése** és **Nem készleten lévő termékek megjelenítése a lista végén**. A beállítás csak akkor használható, ha előbb konfigurál néhány előfeltételül szolgáló beállítást a Commerce Headquarters szolgáltatásban. További információ a készletre [vonatkozó terméklista-listában található](inventory-aware-product-listing.md).

    > [!IMPORTANT] 
    > A **Termékbeállítások terméklistaoldalakhoz** beállítás a Commerce 10.0.20-es verziójától érhető el. Ha a Commerce egy korábbi verziójáról frissít, akkor manuálisan kell frissítenie az appsettings.json fájlt. Az utasításokat lásd itt: [SDK- és modultár-frissítések](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

- **Készlettartományok** – ez a beállítás meghatározza a helymodulok készlettartomány-üzeneteit. Csak akkor alkalmazható, ha a **Teljes rendelkezésre álló** érték vagy a **Rendelkezésre álló tényleges** érték van kiválasztva a **Készletszint alapja** számára. A rendelkezésre álló értékek a **Mind**, az **Alacsony és elfogyott**, valamint az **Elfogyott**.

    - Ha a **Mind** van kiválasztva, akkor a program az összes készlettartomány esetében megjelenít üzeneteket a raktáron állapottól („Elérhető üzenet”) az elfogyott állapotig („Elfogyott” üzenet).
    - Ha az **Alacsony és elfogyott** van kiválasztva, akkor a program az összes készlettartomány esetében megjelenít üzeneteket a raktáron állapotot („Elérhető üzenet”) kivéve.
    - Ha az **Elfogyott** lehetőség van kiválasztva, akkor csak az „Elfogyott” üzenet jelenik meg.

- **Elfogyott küszöbérték** – Ez a régi numerikus beállítás csak akkor lép érvénybe, ha az **Elfogyott küszöbérték** érték van kiválasztva a **Készletszint alapja** beállítás számára.

> [!IMPORTANT] 
> Ezek a beállítások a Dynamics 365 Commerce 10.0.12-es kiadásában érhetők el. Ha a Dynamics 365 Commerce egy korábbi verziójáról frissít, akkor manuálisan kell frissítenie az appsettings.json fájlt. Az appsettings.json fájlok frissítésével kapcsolatos tudnivalókat lásd az [SDK- és modulkönyvtár-frissítések](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file) témakörben.

## <a name="modules-that-use-inventory-settings"></a>A készletbeállításokat használó modulok

A vásárlásmező, kívánságlista, üzletválasztó, kosár és kosárikon modulok készletbeállításokat használnak a készlettartományok és az üzenetek megjelenítéséhez.

A következő példában az alábbi ábra, PDP jelenít meg egy készleten („Elérhető”) üzenetet.

![Egy olyan PDP-modul példája, amely tartalmaz egy készleten üzenetet.](./media/pdp-InStock.png)

A következő példában az alábbi ábra, PDP jelenít meg egy „Elfogyott” üzenetet.

![Egy olyan PDP-modul példája, amely tartalmaz egy elfogyott üzenetet.](./media/pdp-outofstock.png)

A következő példában az alábbi ábra, kosár jelenít meg egy készleten („Elérhető”) üzenetet.

![Egy olyan kosármodul példája, amely tartalmaz egy készleten üzenetet.](./media/cart-instock.png)

## <a name="additional-resources"></a>További erőforrások

[Modultár áttekintése](starter-kit-overview.md)

[Készletpufferek és készletszintek konfigurálása](inventory-buffers-levels.md)

[Kosármodul](add-cart-module.md)

[Vásárlásmező-modul](add-buy-box.md)

[Számlakezelési oldalak és modulok](account-management.md)

[Üzletválasztó modul](store-selector.md)

[SDK- és modulkönyvtár-frissítések](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
