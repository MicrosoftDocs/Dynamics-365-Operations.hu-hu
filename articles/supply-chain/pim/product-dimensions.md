---
title: Termékdimenziók
description: 'Öt termékdimenzió létezik: szín, konfiguráció, méret, stílus és verzió. A termékdimenziókat dimenziócsoportokban kombinálhatja és hozzárendelheti a dimenziócsoportokat az alaptermékekhez. A cikkdimenziók kombinációi meghatározzák a termékváltozatokat is.'
author: t-benebo
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle, EcoResVersionNameLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: acfd9be044818ab0f40171c25a8fc9e760173aa8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8867927"
---
# <a name="product-dimensions"></a>Termékdimenziók

[!include [banner](../includes/banner.md)]

Öt termékdimenzió létezik: szín, konfiguráció, méret, stílus és verzió. A termékdimenziókat dimenziócsoportokban kombinálhatja és hozzárendelheti a dimenziócsoportokat az alaptermékekhez. A cikkdimenziók kombinációi meghatározzák a termékváltozatokat is.

Termékdimenziók olyan jellemzőket termékváltozat azonosítására szolgál. Cikkdimenziók kombinációi használhatja termékváltozatok meghatározására. Termékváltozat létrehozásához meg kell adnia legalább egy termékdimenzió alaptermék.

## <a name="product-variants"></a>Termékváltozatok

Termékváltozatok is nevezik cikkeket. A cikkek kézzelfogható eszközök, vagyis különböznek a szolgáltatásoktól. Lehetőség van alaptermék szolgáltatástípussal való meghatározására. A szolgáltatástípus használatával megadhat szolgáltatásokat magukba foglaló termékváltozatokat. Megadhatja például a tanácsadói munkát alaptermékként és olyan, a munkához tartozó termékváltozatokat, amelyeket vezető és beosztott tanácsadók hajtanak végre.

## <a name="product-dimensions"></a>Termékdimenziók

Termékváltozat hozható létre a termékdimenzió-értékek alapján.

A méret, a szín és a stílus dimenzió termékdimenzióinak értéke a következő helyeken hozható létre:

- **Méret** oldal (**Termékinformáció-kezelés \> Beállítás \> Dimenzió- és változatcsoportok \> Méretek**)
- **Szín** oldal (**Termékinformáció-kezelés \> Beállítás \> Dimenzió- és változatcsoportok \> Színek**)
- **Stílus** oldal (**Termékinformáció-kezelés \> Beállítás \> Dimenzió- és változatcsoportok \> Stílusok**)

A konfigurációdimenzió termékdimenzió-értékei általában a Termékkonfiguráló vagy a Dimenzión alapuló konfiguráló használatával hozhatók létre. 

A termékverziók általában meghatározott verziókhoz jönnek létre, mivel a termék fejlődik az életciklusa alatt. A termékverziók részletesen ebben a cikkben olvashatók.

A termékdimenziók létrehozása és karbantartása a **Termékdimenziók** oldalon lehetséges, amely a következő helyekről érhető el:

- Ugorjon a **Termékinformációk kezelése \> Termékek \> Alaptermékek** lehetőségre. A Művelet ablaktáblán válassza ki a **Termékdimenziók** elemet.
- Lépjen a **Termékinformációk kezelése \> Termékek \> Minden termék és alaptermék** részre. Válasszon ki egy alapterméket. A Művelet ablaktáblán válassza ki a **Termékdimenziók** elemet.
- Lépjen a **Termékinformációk kezelése \> Kiadott termékek** részre. Válasszon ki egy alapterméket. A műveleti ablaktáblán a **Termék** lapon az **Alaptermék** csoportban válassza a **Termékdimenziók** lehetőséget.

A változatok létrehozható egy cikkhez száma lehetséges termék cikkdimenzió-kombinációk száma korlátozza.

> [!TIP]
> Ha terméket használ egy rendeléssoron, például kiválasztja a termékdimenziókat a használni kívánt termékváltozat azonosításához.

## <a name="example"></a>Példa

Egy vállalat farmernadrágokat értékesít. A *Farmernadrág* cikk a szín és a méret termékdimenziókat használja. A farmernadrágok három különböző színben és hat különböző méretben kaphatók. A színek: kék, fekete, barna. A méretek: XS, S, M, L, XL és XXL. A három szín nem minden méretben érhető el. Ha minden kombináció elérhető lenne, akkor 18 féle farmernadrág lenne. Ebben a példában viszont csak a következő kilenc termékváltozat kombinációja érhető el.

| Szín | Méret |
|-------|------|
| Kék  | XS   |
| Kék  | V    |
| Kék  | H    |
| Fekete | H    |
| Fekete | L    |
| Fekete | XL   |
| Barna | L    |
| Barna | XL   |
| Barna | XXL  |

## <a name="the-version-product-dimension"></a>A verzió termékdimenzió

A verzió olyan termékdimenzió, amellyel könnyebb karbantartani és nyomon követni a termék különböző verzióit az ellátási láncon keresztül. A verziókövetés rendkívül fontos az olyan gyártók sikerességéhez, amelyek a termék életciklusának folyamatos méretével, a jobb minőséggel és megbízhatósággal kapcsolatos követelmények területén tevékenykednek, és még inkább a termékbiztonságra fókuszálnak.

Normál termékdimenzióként a verzió a meglévő termékdimenziókhoz (méret, stílus, szín, konfiguráció) hasonlóan viselkedik. Ennek megfelelően a termékverziók nyomon követése mellett másra is használható.

### <a name="turn-on-the-version-dimension"></a><a name="enable-version-dim"></a>A verzió dimenzió bekapcsolása

#### <a name="before-you-turn-on-the-version-dimension"></a>Teendők a verzió dimenzió bekapcsolása előtt

A verzió dimenzió bekapcsolásakor néhány funkció helytelenül vagy nem a várt módon működhetett abban az esetben, ha olyan más megoldásokat telepített, amelyek testreszabásokat adtak a készletdimenziókhoz. Előfordulhat, hogy a verzió dimenzió tökéletes működéséhez frissítenie kell ezeket a megoldásokat, hogy a verzió dimenzió szerepeljen a hivatkozásaikban és a készletdimenzióikban.

A verzió dimenzióval való kompatibilitáshoz szükséges megoldások tesztelésekor a következő elemeket keresse meg:

1. **Funkcionalitás:** a legfontosabb, hogy minden készletdimenziót tartalmazó testreszabást ellenőrizni kell, hogy együttműködik a verzió dimenzióval.
1. **A készletdimenziókra való hivatkozások:** keresse meg a készletdimenziók hivatkozásait (azokat a helyeket, amelyekre a dimenziók kifejezetten hivatkoznak). Az `InventDimId` hivatkozásai a telepítés után egyből működnek, de a stílusra vagy a színre való hivatkozásokat célszerű ellenőrizni. Ellenőrizze például a következő elemeket:

    - API-hívások a kiterjesztett osztályokban
    - A bővítménykódban lévő konkrét készletdimenziókra történő összes hivatkozás (ennek a kódnak lebegőpontosnak kell lennie, a stílus, a szín és a méret dimenzióval együtt).

1. **Elavult API-hívásokra mutató hivatkozások:** a verzió dimenzió bevezetésekor a Microsoft próbálta elérni, hogy minél kevesebb API legyen elavult. A néhány elavult API figyelmeztetést küld, a **Termékdimenzió – verzió** konfigurációs kulcs bekapcsolásakor. Az ilyen API-k hívásait ki kell javítani a kiterjesztett megoldásokban, mielőtt termelési rendszerben aktiválná a verzió dimenziót. A verzióspecifikus elavult API-k a következők:

    - RetailTransactionServiceInventory::getProductRecordId
    - EcoResProductNumberIdentifiedProductVariantEntity::find
    - EGAISAlcoholProduction_RU::findByItemDim
    - PCVariantConfiguration::findByProductMasterAndDimensions

1. **Leképezések:** ha bármelyik leképezés használ készletdimenziót, akkor az ezeknek a leképezéseknek a kapcsolódó objektumkapcsolat-leképezését úgy kell frissíteni, hogy tartalmazza a verzió dimenziót. A kiterjesztett modellben vagy a táblabővítményekben keresse meg azokat a táblákat, amelyeknél a mezők készletdimenziókat tartalmaznak.
1. **Microsoft Dynamics 365 Commerce-funkciók:** Bekapcsolás után a verziódimenzió megjelenik a Dynamics 365 Supply Chain Management Commerce-specifikus kódjában. A Commerce csatorna-adatbázisa és a pénztári vagy e-kereskedelmi alkalmazások azonban még nem támogatják a verzió dimenziót. Ezek a Commerce-specifikus alkalmazások nem támogatják azokat a felhasználókat, akik értékesítenek/szállítanak vagy visszaküldenek/fogadnak készletet verziódimenzió szerint. A készlet elérhetőségének keresési funkciói nem határozzák meg a készletet verziódimenzió szerint a Commerce alkalmazásokban. Ez a viselkedés hasonlít a konfiguráció dimenzió Commerce-en belüli aktuális viselkedésére.

#### <a name="turn-on-the-version-dimension"></a>A verzió dimenzió bekapcsolása

A verzió dimenziót a használat előtt be kell kapcsolnia a rendszerben. A feladathoz rendszergazdai engedélyek szükségesek.

1. Lépjen a **Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés** részre.
1. Kapcsolja be a *Termékdimenzió – verzió* szolgáltatást. (További információ: [Funkciókezelés – áttekintés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).)
1. Állítsa [karbantartási módba](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) a rendszert.
1. Lépjen a **Rendszerfelügyelet \> Beállítás \> Licenckonfiguráció** elemre.
1. A **Konfigurációs kulcsok** lapon bontsa ki a **Kereskedelem** csomópontot , és jelölje be a **Termékdimenzió – verzió** jelölőnégyzetet.
1. Kapcsolja ki a [karbantartási módot](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

### <a name="areas-where-the-version-dimension-isnt-supported"></a>Területek, ahol a verzió dimenzió nem támogatott

A következő területek nem támogatják a verziódimenziót (továbbra is használhatja ezeket a területeket, de verziószámmal rendelkező termékeket – a verziódimenziót is használó termékeket – nem adhat hozzá). Verziószámmal rendelkező cikket nem lehet például szállítói katalógushoz hozzáadni. Ez azért van így, mert ha ezen területekhez verziódimenzióval rendelkező termékeket ad hozzá, akkor az kompatibilitástörő változásokat idézne elő.

- Költségobjektum havi kimutatása
- Költségobjektum-kimutatás gyorsítótára
- MCR-értékesítési statisztikák cikkenként
- Szállítói katalógusok
- EcoResProductDimensionGroupEntity

Ezenkívül a Commerce rendelés-létrehozási és -feldolgozási szolgáltatásai (például a pénztár, a hívásközpont és az e-kereskedelmi rendelések) sem támogatják a verzió dimenziót. Arra vonatkozóan, hogy a Commerce rendelések mikor fogják támogatni, nincs visszaigazolt idősor.

### <a name="functional-characteristics-of-the-version-dimension"></a>A verzió dimenzió működési jellemzői

A verzió dimenzió a többi termékdimenzióhoz hasonlóan működik. A sajátos természete miatt, és mivel arra szolgál, hogy egy termék több verzióját tartsa karban és kövesse nyomon, némileg eltérően működik. Néhány különbség és hasonlóság:

- **Nincs verziócsoport.**

    Csoportok használhatók a mérethez, a színhez vagy a stílushoz, (színcsoport, méretcsoport, stíluscsoport), verziócsoportok nem léteznek. A csoportokkal előre definiálhatók a megfelelő értékeket, így amikor például színcsoportot rendel a termékhez, a termék az adott színcsoport összes színét használhatja. Mindez fogalom nem vonatkozik a verzió dimenzióra, mert a termék verziói nem előredefiniáltak a termék létrehozásakor. Ehelyett a verziók a termék életciklusa alatt jönnek létre, szükség szerint. Általában ha a termék alakja, illeszkedése és funkciója ugyanaz marad, akkor nem új terméket, hanem új verziót szoktak létrehozni.

- **A termékváltozat javaslatai úgy működnek, ahogy jelenleg.**

    A termékváltozatok javaslatai a verzió dimenzió minden értékéhez adnak javaslatot, akárcsak a többi dimenzió esetében. A verziószámmal rendelkező termékek létrehozásának és kiadásának folyamata ugyanaz, mint a más dimenziókat használó termékek esetében. A verziószámozást használó termék létrehozásakor az első verzió (V1) termékdimenzióként jön létre, és megjelennek a változatok. Mivel a termék változik és új verziók lesznek szükségesek, az új verzió értékét (V2) hozzáadja a program, és a rendszer kiadja a szükséges változatokat. Nem kell minden verziót létrehozni (V1, V2 és V3) előre a termékhez.

> [!IMPORTANT]
> Ha bekapcsolja és használja a verzió dimenziót, akkor a készletdimenziókra hivatkozó bizonyos megoldások nem a várt módon működhetnek. A problémák megerősítéséhez és javításához forduljon az érintett megoldás független szoftverszállítójához (ISV). További információ: [A verzió dimenzió engedélyezése](#enable-version-dim).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]