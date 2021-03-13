---
title: Termékváltozat-elnevezési rendszer számai és nevei
description: Ez a témakör leírja, hogyan állíthat be termékszám-elnevezési rendszert, amelyre lecserélheti a rögzített [Alaptermék száma - Konfiguráció - Méret - Szín - Stílus] formátumot.
author: roxanadiaconu
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: f17f9e1401c68c11e23f327d96028663470b3245
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011322"
---
# <a name="nomenclature-of-product-variant-numbers-and-names"></a>Termékváltozat-elnevezési rendszer számai és nevei

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan állíthat be termékszám-elnevezési rendszert, amelyre lecserélheti a rögzített [Alaptermék száma - Konfiguráció - Méret - Szín - Stílus] formátumot. Az új elnevezési rendszer célzott formátumú, amely magában foglalja az alaptermék számát, az aktív termékdimenziókat és az Ön által választott szöveghatárolókat. A terméknevekhez is létrehozhat elnevezési rendszert. Végül pedig megszorításon alapuló termékkonfiguráló által létrehozott konfigurációk azonosítására szolgáló elnevezési rendszert is létrehozhat. Ezek az elnevezési rendszerek tetszés szerinti attribútumokat tartalmazhatnak.

A termékváltozatszámok és termékváltozatnevek új elnevezési rendszere révén szegmenseket adhat a termékváltozatok azonosítóihoz. Ezek a szegmensek tartalmazhatják az alaptermék számát és nevét, a termékdimenzió-azonosítókat és -neveket, a számsorozatokat, szöveges konstansokat és az attribútumokat. Ezzel egy értékesítési rendelés vagy beszerzési rendelés létrehozásakor gyorsan megtalálhatja a konkrét termékváltozatot. A termékváltozatszámokhoz és termékváltozatnevehez egyaránt a **Termékek elnevezési rendszere** lapon hozhat létre elnevezési rendszert. A lap megnyitásához kattintson a **Termékinformációk kezelése** &gt; **Beállítás** lehetőségre.

## <a name="nomenclature-of-predefined-product-variants"></a>Előre definiált termékváltozatok termékszámozási rendszere
Az alaptermékhez a termékváltozatokat a három konfigurációs technológia közül egyiknek megfelelően generálják:

-   Előre definiált változat
-   Megszorításon alapuló
-   Dimenzióalapú

Minden termékváltozatnak saját száma és neve van, és a termékváltozat-azonosító elnevezési rendszerei segítségével kiválaszthatja az egyes termékváltozatszámokba vagy -nevekbe beemelendő szegmenseket. A következő szegmenseket a **Termékek elnevezési rendszere** lapon választhatja ki:

-   Alaptermék száma
-   Alaptermék neve
-   Számsorozat értéke
-   Szöveges állandó
-   Termékdimenziók
    -   A konfiguráció azonosítója vagy elnevezése
    -   Szín azonosítója vagy neve
    -   Méret azonosítója vagy neve
    -   Stílus azonosítója vagy neve

A termékváltozat-azonosító számozási rendszerének meghatározása után társíthatja azt egy termékdimenzió-csoporthoz. A termékdimenzió-csoportra hivatkozó összes alaptermék az elnevezési rendszer alapján termékváltozatszámokat kap. A termékváltozatnevek elnevezési rendszere azonban nem társítható termékdimenzió-csoportokkal. A termékváltozat-azonosító elnevezési rendszerét közvetlenül is hozzárendelheti egy alaptermékhez. Ebben az esetben az alaptermékhez tartozó termékváltozatok az elnevezési rendszer alapján kapnak termékváltozatszámokat és -neveket.

### <a name="example"></a>Példa

Egy póló (TS1234) három méretben (S, M, L), négy színben (piros, zöld, kék, sárga), illetve két stílusban (póló, V-nyakú) érhető el. Emiatt 24 termékváltozat lehetséges (= 3 x 4 x 2). Ön létrehoz egy termékváltozatszám-elnevezési rendszert, amely a következő szegmensekből áll:

1.  Alaptermék száma
2.  Szöveges állandó: "-"
3.  Szín
4.  Szöveges állandó: "-"
5.  Méret
6.  Szöveges állandó: "-"
7.  Stílus

Ebben az esetben a termékváltozat száma a piros, kicsi póló esetében: TS1234-Piros-Kicsi-Polo.

## <a name="nomenclature-of-constraint-based-configurations"></a>Megszorításon alapuló konfigurációk elnevezési rendszere
A megszorításon alapuló konfigurációk esetében dedikált elnevezési rendszer hozható létre a konfiguráció termékdimenzió számára. A következő szegmenseket a **Termékek elnevezési rendszere** lapon választhatja ki:

-   Számsorozat értéke
-   Szöveges állandó
-   Attribútumérték

A termékkonfigurációs modell minden egyes összetevőjének saját konfigurációs elnevezési rendszere lehet. Csak az adott komponenshez tartozó attribútumok használhatók. Részösszetevők vagy felhasználói igények attribútumai nem érhetők el.

### <a name="example"></a>Példa

A termékkonfigurációs modell két attribútummal rendelkező gyökérszintű összetevőből áll:

-   Anyagok (Műanyag, Fa, Acél)
-   Hossz (10.. 100)

Ön létrehoz egy konfigurációelnevezési rendszert, amely a következő szegmensekből áll:

1.  Attribútumérték: Anyag
2.  Szöveges állandó: "AAA"
3.  Attribútumérték: Hossz

Ebben az esetben a 78-as hosszúságú faanyag konfigurációs azonosítója a FaAAA78 lesz.

## <a name="nomenclature-of-dimension-based-configurations"></a>Dimenzión alapuló konfigurációk elnevezési rendszere
A dimenzión alapuló konfigurációk esetében dedikált elnevezési rendszer hozható létre a konfiguráció termékdimenzió számára. A következő szegmenseket a **Termékek elnevezési rendszere** lapon választhatja ki:

-   Számsorozat értéke
-   Szöveges állandó
-   Konfigurációs csoport eleme

Anyagjegyzékhez (BOM) meghatározhat egy konfigurációelnevezési rendszert.

### <a name="example"></a>Példa

Egy anyagjegyzék négy anyagjegyzéksorral rendelkezik, amelyek két konfigurációs sorra oszlanak:

-   Anyagjegyzéksor: M0007, Standard kabinetfájl
    -   Konfigurációs csoport: Kabinetfájl
-   AJ-sor: M0008, Nagy záró kabinetfájl
    -   Konfigurációs csoport: Kabinetfájl
-   AJ-sor: M0021, az első rács szövetből
    -   Konfigurációs csoport: Első rács
-   AJ-sor: M0022, az első rács fémből
    -   Konfigurációs csoport: Első rács

Ön létrehoz egy konfigurációelnevezési rendszert, amely a következő szegmensekből áll:

1.  Konfigurációs csoport: Kabinetfájl
2.  Szöveges állandó: "&"
3.  Konfigurációs csoport: Első rács

Az első rács szövetből standard kabinetfájl konfigurációs azonosítója ebben az esetben: M0007&M0021.

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a>Termékváltozatok és konfigurációk kombinációjának elnevezési rendszere
Akár megszorításon alapuló, akár dimenzión alapuló konfigurációs technológiát használ a termékváltozatok alaptermékre történő konfigurációja esetén, a termékváltozatok olyan termékváltozatszámokat kaphatnak, amelyek tartalmazzák a konfigurációdimenzió elnevezési rendszerét. A változatok konfigurálásához kövesse az alábbi lépéseket.

1.  A **Termékek elnevezési rendszere** lapon adja meg a termékváltozatszám elnevezési rendszerét, amely tartalmazza a konfigurációdimenziót.
2.  Rendelje az elnevezési rendszert egy konfigurációdimenziót tartalmazó termékdimenzió-csoporthoz.
3.  Határozza meg a termékváltozat konfigurálásához használandó összetevők vagy anyagjegyzékek konfigurációs elnevezési rendszerét.

A termékváltozatnevekhez is létrehozhat elnevezési rendszereket. A termékváltozatnevek konfigurálhatók úgy, hogy tartalmazzák a konfiguráció azonosítóját vagy nevét.

### <a name="example-for-constraint-based-configurations"></a>Példák megszorításon alapuló termékkonfigurációkra

Ebben a példában egy olyan termékváltozat-számozási rendszert használhat, amely a következő szegmensekből áll:

1.  Alaptermék száma
2.  Szöveges állandó: "\_"
3.  Konfiguráció

A konfigurációs elnevezési rendszer a következő szegmensekből áll:

1.  Attribútumérték: Anyag
2.  Szöveges állandó: "AAA"
3.  Attribútumérték: Hossz

A szegmensekhez a következő értékeket adja meg:

-   Alaptermék száma = **M0099**
-   Anyag = **Műanyag**
-   Hossz = **12**

A termékváltozat száma ebben az esetben: M0099\_PlasticAAA12.

### <a name="example-for-dimension-based-configurations"></a>Példák dimenzión alapuló konfigurációkra

Ebben a példában egy olyan termékváltozat-számozási rendszert használhat, amely a következő szegmensekből áll:

1.  Alaptermék száma
2.  Szöveges állandó: "//"
3.  Konfiguráció

A konfigurációs elnevezési rendszer a következő szegmensekből áll:

1.  Konfigurációs csoport: Kabinetfájl
2.  Szöveges állandó: "&"
3.  Konfigurációs csoport: Első rács

A szegmensekhez a következő értékeket adja meg:

-   Alaptermék száma = **D0123**
-   Kabinet = **M0008**
-   Elülső rács = **M0022**

A termékváltozat száma ebben az esetben: D0123//M0008&M0022.

## <a name="numbering-conflicts"></a>Ütközések számozása
Bizonyos esetekben lehetőség van olyan termékváltozat-számozási rendszer beállítására, amely nem hoz létre egyedi termékváltozatszámokat. Például a termékváltozatszámok nem lehetnek egyediek, ha egy aktív termékdimenzió nem szerepel az alaptermék előre definiált változatkonfigurálási technológiát használó elnevezési rendszerében. Az ütközések kezelési módja eltérő a konfigurációs technológiától függően.

### <a name="predefined-variants"></a>Előre definiált változatok

Hiba lép fel, ha kézzel vagy automatikusan próbál termékváltozatokat létrehozni olyankor, amikor egy vagy több termékváltozat ugyanazon termékváltozatszámmal rendelkezik. Ennek elkerülése érdekében használja az összes aktív termékdimenziót a termékdimenzió-csoportból. Másik lehetőségként megadhat egy számsorozatot annak érdekében, hogy a termékváltozatszámok egyediek legyenek.

### <a name="constraint-based-configurations"></a>Megszorításon alapuló konfigurációk

Az elnevezési rendszertől függően a rendszer megkísérelhet nem egyedi számot hozzárendelni egy konfigurációhoz. Ilyenkor a rendszer a konfigurációdimenzió számsorozatát fogja használni a termékváltozatszám helyett. Ebben az esetben egy figyelmeztetést fog kapni. Ennek elkerülése érdekében elég attribútumot kell szerepeltetni az elnevezési rendszerben, hogy egyedi termékváltozat-számok lehessenek. Arról is gondoskodnia kell, hogy az **Újra** beállítás engedélyezve van az összetevőnél.

### <a name="dimension-based-configurations"></a>Dimenzión alapuló konfigurációk

A konfigurálási folyamat egyik lépésében a rendszer az elnevezési rendszernek megfelelő konfigurációs értéket fog javasolni. Ebben a lépésben manuálisan módosíthatja a konfigurációs értéket. A konfiguráció mentésekor a rendszer ellenőrzi, hogy konfigurációs érték egyedi-e. Ha a megadott érték nem egyedi, akkor megjelenik egy hibaüzenet. A konfiguráció mentéséhez meg kell adnia egy egyedi konfigurációs értéket.

<a name="additional-resources"></a>További erőforrások
--------

[Termékszám elnevezési rendszerének létrehozása előre definiált termékváltozatokhoz](tasks/create-product-number-nomenclature-predefined-variants-2016-11.md)

[Termékszámozás-elnevezési rendszer létrehozása konfigurált termékváltozatokhoz](tasks/create-product-number-nomenclature-product-variants_2016_11.md)

