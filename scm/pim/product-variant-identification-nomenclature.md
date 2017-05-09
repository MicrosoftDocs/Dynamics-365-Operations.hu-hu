---
title: "Termékszámozási rendszer"
description: "Ez a témakör leírja, hogyan állíthat be termékszámozási rendszert a rögzített formátum lecserélése érdekében [Alaptermék száma - Konfiguráció - Méret - Szín - Stílus]: a célzott formátum tartalmazza az alaptermék számát, az aktív termékdimenziókat és tetszés szerinti szövegelválasztókat. A megszorításon alapuló termékkonfiguráló által létrehozott konfigurációk azonosítására szolgáló elnevezési rendszert is létrehozhat. Ezek az elnevezési rendszerek tetszés szerinti attribútumokat tartalmazhatnak."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 220104
ms.assetid: 31c9efb4-b5f6-4af3-b884-8f1e128469bd
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 58afcd62e7ef317e624fd26d198c2606bf53e6a5
ms.lasthandoff: 03/31/2017


---

# <a name="product-number-nomenclature"></a>Termékszámozási rendszer

[!include[banner](../includes/banner.md)]


Ez a témakör leírja, hogyan állíthat be termékszámozási rendszert a rögzített formátum lecserélése érdekében [Alaptermék száma - Konfiguráció - Méret - Szín - Stílus]: a célzott formátum tartalmazza az alaptermék számát, az aktív termékdimenziókat és tetszés szerinti szövegelválasztókat. A megszorításon alapuló termékkonfiguráló által létrehozott konfigurációk azonosítására szolgáló elnevezési rendszert is létrehozhat. Ezek az elnevezési rendszerek tetszés szerinti attribútumokat tartalmazhatnak.

Az új termékváltozat-számozási rendszer lehetővé teszi, hogy szegmenseket foglaljon bele szerepeljenek a termékváltozat-azonosítókba. Ezek a szegmensek tartalmazhatják az alaptermék számát, a termékdimenziókat, a számsorozatokat, szöveges konstansokat és az attribútumokat. Ezzel egy értékesítési rendelés vagy beszerzési rendelés létrehozásakor gyorsan megtalálhatja a konkrét termékváltozatot.

## <a name="nomenclature-of-predefined-product-variants"></a>Előre definiált termékváltozatok termékszámozási rendszere
Az alaptermékhez a termékváltozatokat a három konfigurációs technológia közül egyiknek megfelelően generálják:

-   Előre definiált változat
-   Megszorításon alapuló
-   Dimenzióalapú

Minden termékváltozatnak saját száma van, és a termékváltozat-azonosító elnevezési rendszere segítségével kiválaszthatja az egyes termékváltozatszámokba beemelendő szegmenseket. A következő szegmenseket a **Termékek elnevezési rendszere** lapon választhatja ki.

-   Alaptermék száma
-   Számsorozat értéke
-   Szöveges állandó
-   Termékdimenziók
    -   Konfiguráció
    -   Szín
    -   Méret
    -   Stílus

A termékváltozat-azonosító elnevezési rendszerének meghatározása után társíthatja azt egy termékdimenzió-csoporthoz. Következésképpen a termékdimenzió-csoportra hivatkozó összes alaptermék az elnevezési rendszer alapján termékváltozatszámokat kap. Közvetlenül is hozzárendelhet egy termékváltozat-azonosító elnevezési rendszert egy alaptermékhez: ebben az esetben az alaptermékhez tartozó termékváltozatokhoz termékváltozat-azonosítók lesznek hozzárendelve az elnevezési rendszer alapján.

### <a name="example"></a>Példa

Egy pólót (TS1234) 3 különböző méretben (S, M, L), 4 különböző színben (Piros, Zöld, Kék, Sárga) és 2 stílusban (Polo, V) állítanak elő: ez össze 24 lehetséges termékváltozat. A termékváltozat-azonosító elnevezési rendszerét a következő szegmensekkel hozzák létre:

1.  Alaptermék száma
2.  Szöveges állandó: '-'
3.  Szín
4.  Szöveges állandó: '-'
5.  Méret
6.  Szöveges állandó: '-'
7.  Stílus

A termékváltozat száma a Piros, Kicsi, Polo esetében: TS1234-Piros-Kicsi-Polo.

## <a name="nomenclature-of-constraintbased-configurations"></a>Megszorításon alapuló konfigurációk elnevezési rendszere
A megszorításon alapuló konfigurációk esetében dedikált elnevezési rendszer építhető a konfiguráció termékdimenzió számára. A következő szegmenseket a **Termékek elnevezési rendszere** lapon választhatja ki.

-   Számsorozat értéke
-   Szöveges állandó
-   Attribútumérték 

A termékkonfigurációs modell minden egyes összetevőjének saját konfigurációs elnevezési rendszere lehet. Csak az adott komponenshez tartozó attribútumok használhatók. Részösszetevő vagy a felhasználói igényeket attribútumok nem érhetők el.

### <a name="example"></a>Példa

A termékkonfigurációs modell két attribútummal rendelkező gyökérszintű összetevőből áll.

-   Anyagok (Műanyag, Fa, Acél)
-   Hossz (10.. 100)

A konfigurációs elnevezési rendszer meghatározása a következő szegmensek segítségével történik:

1.  Attribútumérték: Anyag
2.  Szöveges állandó: 'AAA'
3.  Attribútumérték: Hossz

A 78 hosszúságú fa anyag konfigurációs azonosítója a következő lesz: WoodAAA78.

## <a name="nomenclature-of-dimensionbased-configurations"></a>Dimenzión alapuló konfigurációk elnevezési rendszere
A dimenzión alapuló konfigurációk esetében dedikált elnevezési rendszer építhető a konfiguráció termékdimenzió számára. A következő szegmenseket a **Termékek elnevezési rendszere** lapon választhatja ki.

-   Számsorozat értéke
-   Szöveges állandó
-   Konfigurációs csoport eleme

Anyagjegyzékhez (BOM) meghatározhat egy konfigurációelnevezési rendszert.

### <a name="example"></a>Példa

Az anyagjegyzék 2 konfigurációcsoportra felosztott 4 anyagjegyzéksorból áll.

-   Anyagjegyzéksor: M0007, Standard kabinetfájl
    -   Konfigurációs csoport: Kabinetfájl
-   AJ-sor: M0008, Nagy záró kabinetfájl
    -   Konfigurációs csoport: Kabinetfájl
-   AJ-sor: M0021, az első rács szövetből
    -   Konfigurációs csoport: Első rács
-   AJ-sor: M0022, az első rács fémből
    -   Konfigurációs csoport: Első rács

A konfigurációs elnevezési rendszer meghatározása a következő szegmensek segítségével történik:

1.  Konfigurációs csoport: Kabinetfájl
2.  Szöveges állandó: '&'
3.  Konfigurációs csoport: Első rács

Az első rács szövetből standard kabinetfájl konfigurációs azonosítója: M0007&M0021.

## <a name="nomenclature-of-a-combination-of-product-variants-and-configurations"></a>Termékváltozatok és konfigurációk kombinációjának elnevezési rendszere
Akár megszorításon alapuló, akár dimenzión alapuló konfigurációs technológiát használ a termékváltozatok alaptermékre történő konfigurációja esetén, a termékváltozatok olyan termékváltozatszámokat kapnak, amelyek tartalmazzák a konfigurációdimenzió elnevezési rendszerét. A változatok konfigurálásához kövesse az alábbi lépéseket:

1.  A **Termékek elnevezési rendszere** lapon adja meg a termékváltozatszám elnevezési rendszerét, amely tartalmazza a konfigurációdimenziót.
2.  Rendelje ezt az elnevezési rendszert egy konfigurációdimenziót tartalmazó termékdimenzió-csoporthoz.
3.  Határozza meg a termékváltozat konfigurálásához használandó összetevők vagy anyagjegyzékek konfigurációs elnevezési rendszerét.

### <a name="example-for-constraint-based-configurations"></a>Példák megszorításon alapuló termékkonfigurációkra

Ebben a példában egy olyan termékváltozat-számozási rendszert használhat, amely a következő szegmensekből áll:

1.  Alaptermék száma
2.  Szöveges állandó: '\_'
3.  Konfiguráció

A konfigurációs elnevezési rendszer a következő szegmensekből állhat:

1.  Attribútumérték: Anyag
2.  Szöveges állandó: 'AAA'
3.  Attribútumérték: Hossz

A szegmensekhez a következő értékeket adhatja meg:

-   Alaptermék száma = M0099
-   Anyag = Műanyag
-   Hossz = 12

A termékváltozat száma: M0099\_PlasticAAA12.

### <a name="example-for-dimension-based-configurations"></a>Példák dimenzión alapuló konfigurációkra

Ebben a példában egy olyan termékváltozat-számozási rendszert használhat, amely a következő szegmensekből áll:

1.  Alaptermék száma
2.  Szöveges állandó '//'
3.  Konfiguráció

A konfigurációs elnevezési rendszer a következő szegmensekből állhat:

1.  Konfigurációs csoport: Kabinetfájl
2.  Szöveges állandó: '&'
3.  Konfigurációs csoport: Első rács

A szegmensekhez a következő értékeket adhatja meg:

-   Alaptermék száma = D0123
-   Kabinetfájl = M0008
-   Elülső rács = M0022

A termékváltozat száma: D0123//M0008&M0022.

## <a name="numbering-conflicts"></a>Ütközések számozása
Lehetőség van olyan termékváltozat-számozási rendszer beállítására, amely nem hoz létre egyedi termékváltozatszámokat. Ez például akkor fordulhat elő, ha egy aktív termékdimenzió nem szerepel az alaptermék előre definiált változatkonfigurálási technológiát használó elnevezési rendszerében. A különböző konfigurációs technológiák esetében a rendszer eltérően kezeli az ütközéseket.

### <a name="predefined-variants"></a>Előre definiált változatok

Hiba lép fel, ha kézzel vagy automatikusan próbál termékváltozatokat létrehozni olyankor, amikor egy vagy több változat ugyanazon termékváltozatszámmal rendelkezik. Ennek elkerülése érdekében a termékdimenzió-csoport minden aktív termékdimenzióját használnia kell, vagy vegyen fel egy számsorozatot az egyedi termékváltozatszámok biztosítása érdekében.

### <a name="constraint-based-configurations"></a>Megszorításon alapuló konfigurációk

Az elnevezési rendszertől függően a rendszer megkísérelhet nem egyedi számot hozzárendelni egy konfigurációhoz. Ilyenkor a rendszer a konfigurációdimenzió számsorozatát fogja használni a termékváltozatszám helyett. Ebben az esetben egy figyelmeztetést fog kapni. Ennek elkerülése érdekében elegendő attribútumot kell felvennie az elnevezési rendszerbe az egyediség biztosítása érdekében, valamint meg kell győződnie arról, hogy az **Újrahasználat** beállítás engedélyezve van az összetevő esetében.

### <a name="dimension-based-configurations"></a>Dimenzión alapuló konfigurációk

A konfigurálási folyamat egy lépést is tartalmaz, amelyben a rendszer az elnevezési rendszernek megfelelő konfigurációs értéket fog javasolni. Ebben a lépésben manuálisan módosíthatja a konfigurációs értéket. A konfiguráció mentésekor a rendszer ellenőrzi, hogy konfigurációs érték egyedi-e. Ha ez nem így van, hibaüzenet jelenik meg. A konfiguráció mentéséhez meg kell adnia egy egyedi konfigurációs értéket.



<a name="see-also"></a>Lásd még
--------

[Termékszámozási rendszer létrehozása előre definiált termékváltozatokhoz (feladat-útmutató)](http://ax.help.dynamics.com/en/wiki/create-a-product-number-nomenclature-for-predefined-product-variants/)

[Termékszámozási rendszer létrehozása konfigurált termékváltozatokhoz (feladat-útmutató)](http://ax.help.dynamics.com/en/wiki/create-a-product-number-nomenclature-for-configured-product-variants/)




