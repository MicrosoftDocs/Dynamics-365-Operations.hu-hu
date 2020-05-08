---
title: Vásárlásmező modul
description: Ez a témakör a vásárlásmező moduljaival foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.
author: anupamar-ms
manager: annbe
ms.date: 04/14/2020
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
ms.openlocfilehash: 095374c14cddf1ae3608ae1427a7144b3e7ca7b2
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269751"
---
# <a name="buy-box-module"></a>Vásárlásmező modul


[!include [banner](includes/banner.md)]

Ez a témakör a vásárlásmező moduljaival foglalkozik, és bemutatja, hogy hogyan lehet őket hozzáadni webhelyek lapjaihoz a Microsoft Dynamics 365 Commerce alkalmazásban.

## <a name="overview"></a>Áttekintés

A *vásárlásmező* kifejezés általában a termék részletes lapjának azon területére utal, amely „görgetés nélkül látható”, és a termék megvásárlásához szükséges legfontosabb adat mindegyikét tartalmazza. (A „görgetés nélkül látható” terület a lap első betöltésekor jelenik meg, így a felhasználóknak nem kell legörgetni, hogy lássák azt.)

A vásárlásmező egy speciális tároló, amely a termék részletes lapjának vásárlásmező részén látható összes modult tárolja.

A termék részletes lapjának URL-címe tartalmazza a termékazonosítót. A vásárlásmező modul megjelenítéséhez szükséges összes adat ebből a termékazonosítóból származik. Ha nincs megadva termékazonosító, akkor a program nem jeleníti meg megfelelően a vásárlásmező modult a lapon. Ezért a vásárlásmező modul csak a termék környezetét tartalmazó lapokon használható. Ha azt szeretné, hogy egy olyan oldalon használhassa, amely nem rendelkezik a termék környezetével (például egy Kezdőlap vagy egy marketinges lapon), további testreszabásokat kell végérehajtania.

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
- **Áruházválasztó** – Ez a modul felsorolja azokat a közeli áruházakat, ahol a cikkek elérhetők és felvehetők. Ez lehetővé teszi a felhasználók számára, hogy a közelben levő üzleteket megtalálják. A modullal kapcsolatos további tudnivalókat lásd: [Üzletkiválasztó modul](store-selector.md).

## <a name="buy-box-module-settings"></a>Vásárlásmező modul beállításai

A vásárlásmező-modulok három beállítása a **Webhelybeállítások \> Bővítmények** pontban konfigurálhatók:

- **Maximális mennyiség** – Ez a tulajdonság megadja az egyes cikkek kosárhoz adható maximális számát. Előfordulhat például, hogy egy kiskereskedő úgy dönt, hogy egyetlen tranzakcióban csak 10 terméket lehet értékesíteni.
- **Készletellenőrzés** – Ha **Igaz** értékre van beállítva, akkor a program a kosárba csak azután veszi fel a cikket, hogy a vásárlásmező modul meggyőződött róla, hogy az adott termék készleten van. Ez a készletellenőrzés végrehajtásra kerül azokban az esetekben, amikor a cikk kiszállításra kerül, mind azokban az esetekben, amikor a vevő az áruházban veszi fel. Ha **Hamis** értékre van állítva, akkor a program nem végez készletellenőrzést, mielőtt a cikkeket felveszi a kosárba, és a rendelés leadásra kerül. A készlet beállításainak konfigurálásával kapcsolatos további tudnivalókat lásd: [Kiskereskedelmi csatornák készletelérhetőségének kiszámítása](calculated-inventory-retail-channels.md).

- **Készletpuffer** – ez a tulajdonság a készlethez tartozó pufferméret meghatározására szolgál. A készlet leltározása valós időben történik, és sok vevői rendelés esetén nehéz a készlet pontos leltározása. A készletellenőrzés során, ha a készlet kisebb, mint a puffermennyiség, akkor a rendszer a terméket kifogyottként kezeli. Ezért ha az értékesítések gyorsabban történnek több csatornán keresztül, és a leltározás nem teljes mértékben szinkronizált, akkor kisebb a kockázata annak, hogy a kifogyott cikkek eladásra kerülnek.

## <a name="commerce-scale-unit-interaction"></a>Commerce Scale Unit-interakció

A vásárlásmező-modul a termék adatait a Commerce Scale Unit API-k használatával olvassa be. Az termék részletes lapjáról származó termékazonosító az összes információ lekérdezésére szolgál.

## <a name="add-a-buy-box-module-to-a-page"></a>Vásárlásmező modul felvétele egy oldalra

A vásárlásmező modul új oldalra való felvételéhez és a kötelező tulajdonságok beállításához hajtsa végre az alábbi lépéseket.

1. Hozzon létre egy **vásárlásmező töredék** nevű töredéket, majd adjon hozzá egy vásárlásmező modult.
1. A vásárlásmező **Média** helyén adjon hozzá egy médiatár modult.
1. A vásárlásmező-modul **Áruházválasztó** helyén vegye fel az áruházválasztó modult.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a töredék ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. Hozzon létre egy sablont a termék részletes lapjához, majd nevezze el **PDP-sablon** néven.
1. Adjon hozzá egy alapértelmezett lapot.
1. Az alapértelmezett lap **Fő** helyén adjon hozzá egy vásárlásmező töredékét.
1. Válassza a **Mentés** elemet, válassza a **Szerkesztés befejezése** parancsot a sablon ellenőrzéséhez, majd a **Közzététel** elemet a közzétételhez.
1. A most létrehozott sablon használatával hozzon létre egy **PDP-lap** nevű lapot.
1. Az új lap **Fő** helyén adjon hozzá egy vásárlásmező töredékét.
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
