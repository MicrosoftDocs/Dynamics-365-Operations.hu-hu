---
title: "ÁFA-számítási módok kiválasztása az Kiindulás mezőben"
description: "Ez a cikk ismerteti az áfa kódok lapon található Eredet mező opcióit és azt, hogy hogyan kerül kiszámításra az áfa a kiválasztott áfa kód alapján."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TaxTable
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 5f3d0e2016a3ffe5500ecae9508d44a115c56880
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="sales-tax-calculation-methods-in-the-origin-field"></a>ÁFA-számítási módok kiválasztása az Kiindulás mezőben

[!include[banner](../includes/banner.md)]


Ez a cikk ismerteti az áfa kódok lapon található Eredet mező opcióit és azt, hogy hogyan kerül kiszámításra az áfa a kiválasztott áfa kód alapján.

Az Áfakódok oldalon létrehozott áfakódokhoz az Kiindulás mezőben ki kell választani az adóalap összegére alkalmazott számítási módszert.

## <a name="percentage-of-net-amount"></a>A nettó összeg százaléka
Az Kiindulás mezőben a Nettó összeg százalékos értéke számítási módszer az alapértelmezett érték. A program az áfát a beszerzési vagy értékesítési összeg százalékaként számítja ki, és az esetleges további forgalmi adókat nem foglalja bele a számításba.
### <a name="example"></a>Példa

Adó mértéke: 25%. A számlasorban 10 cikk szerepel, mindegyik 1,00 dollárba kerül, és a vevő 10% sorkedvezményt kap. Nettó összeg: (10 x 1,00) -10% = 9,00 Áfa: 9,00 x 25% = 2,25 Teljes összeg: 9,00 + 2,25 = 11,25

## <a name="percentage-of-gross-amount"></a> A bruttó összeg százaléka
Ha A bruttó összeg százaléka módszer választja, az áfát a rendszer a bruttó értékesítési összeg százalékaként számítja ki. A bruttó összeg egyenlő a soron szereplő nettó összeg, a sorra vonatkozó összes adóval és díjjal megnövelt összegével, kivéve azt az egy adót, ahol Kiindulás = Bruttó összeg százaléka.
### <a name="example"></a>Példa

Az adóhatóság különleges adókat szabott ki egy cikkre. Az adó összegét a program az áfa kiszámítása előtt hozzáadja a nettó összeghez. Az alábbi Áfakódok esetén:
-   1. ADÓ = 10% a Nettó összeg százaléka számítási módszer használata mellett
-   2. ADÓ = 20% a Nettó összeg százaléka számítási módszer használata mellett
-   ÁFA = 25% a Bruttó összeg százaléka számítási módszer használata mellett

Ha a nettó összeg 10,00, akkor az 1. ADÓ 1,00 (10.00 x 10%) a 2. ADÓ pedig 2,00 (10.00 x 20%). Az összegek a következők lesznek: Bruttó összeg: Nettó összeg + 1. ADÓ összege + 2. ADÓ összege (10,00 + 1,00 + 2,00) = 13.00 ÁFA = 13,00 x 25 % = 3,25 ADÓK és ÁFA összege: 1,00 + 2,00 + 3,25 = 6,25 Teljes összeg: 10,00 + 6,25 = 16,25
| **Megjegyzés**                                                                                                                                                                                                                 |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A tranzakciókhoz csak egy olyan adó használható, ahol Kiindulás = Bruttó összeg százaléka. Ha egynél több ilyen adókódot állít be egy tranzakcióhoz, úgy a rendszer arra vonatkozó hibaüzenetet jelenít meg, hogy az áfa kiszámítása nem lehetséges. |

 
<a name="percentage-of-sales-tax"></a>Az áfa százaléka
-----------------------

Ha az Kiindulás mezőben az Áfa százaléka lehetőséget választja, a rendszer az áfa mezőben kiválasztott Áfa kapcsán meghatározott áfa százalék alapján számítja ki az adót. Elsőként az áfa mezőben kiválasztott Áfa került kiszámításra. A második forgalmi adó kiszámítása az első forgalmi adó összege alapján történik.
### <a name="example"></a>Példa

Az alábbi Áfakódok esetén:
-   1. ADÓ = 10% a Nettó összeg százaléka módszer használata mellett
-   2. ADÓ = 20%, Az afa százaléka módszerrel, ahol az 1. adó az áfa mezőben megadott Áfa
-   ÁFA = 25% a Bruttó összeg százaléka módszer használata mellett

Nettó összeg: 10,00 1. ADÓ: 10,00 x 10 % = 1,00 2. ADÓ: 1,00 x 20 = 0,20 Bruttó összeg: 10,00 + 1,00 + 0,20 = 11,20 ÁFA: 11,20 x 25 % = 2.80 ADÓK és ÁFA összege: 1,00 + 0,20 + 2,80 = 4,00 Teljes összeg: 10,00 + 4,00 = 14,00
| **Megjegyzés**                                                                                                                                                                                                                    |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Az adók kiszámítása során nem alkalmazhatók többszintű adók. Az adó kiszámításának alapja nem lehet olyan adó, amely eleve egy másik adó függvénye. Több, az adókódoknál rögzített egyszintű adó is alkalmazható egy adott tranzakcióra. |

## <a name="amount-per-unit"></a> Egységenkénti összeg
Ha az Egységenkénti összeg lehetőséget választja az Kiindulás mezőben, az áfa kiszámítási módja: az egységenkénti fix összeg megszorozva a dokumentumsorban rögzített mennyiséggel. Kötelező kiválasztani egy egységet az Egység mezőben. Az Áfaértékek oldal rögzíti az egységenkénti összeget.
### <a name="example"></a>Példa

Az Áfakód beállítása a következő 1,20 USD egységenkénti összeg = doboz. Az értékesítési számla 25 db adott cikket tartalmazó sora esetén az Áfa-számítás módja: 25 x 1.20 = 30,00
| **Megjegyzés**                                                                                                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ha a tranzakció rögzítése az áfakódban rögzítettől eltérő mértékegységben történik, úgy azt a rendszer automatikusan konvertálja a Mértékegység-konverzió oldalon beállított arányoknak megfelelően. |

###  <a name="amount-per-unit-additional-option"></a> Egységenkénti összeg módszer, további beállítások

A Számítás lapon meg tudja adni, hogy az egységenkénti adó más adókódok előtt kerüljön-e kiszámításra, valamint a nettó összeghez hozzáadásra kerüljön-e, mielőtt a Kiindulás = Nettó összeg százaléka típusú adók alkalmazásra kerülnek.

### <a name="examples"></a>Példák

Tegyük fel, hogy 2 adókódot alkalmazunk egy tranzakció kapcsán:

-   ADÓ: Kiindulás = Egységenkénti összeg, valamint egy áfa, melynek beállított értéke: 5,00 egységenként (db)
-   ÁFA: Kiindulás = a beállított érték 25%, az alábbi példákban szemléltetett módon

Eladunk 1 darabot az adott cikkből 10,00 egységáron
#### <a name="example-1"></a>1. példa

ÁFA: Kiindulás = Bruttó összeg százaléka módszer. Az Áfa előtt számolandó lehetőségnek nincs jelentősége, mivel az ÁFA a bruttó összeg százalékaként kerül kiszámításra. ADÓ: 1 x 5,00 = 5,00 Bruttó összeg: 10,00 + 5,00 = 15,00 ÁFA: 15,00 x 25% = 3,75 Áfa összesen: 5,00 + 3,75 = 8,75 Teljes összeg: 10,00 + 8,75 = 18,75

#### <a name="example-2"></a>2. példa

ÁFA: Kiindulás = Nettó összeg százaléka. Az Áfa előtt számolandó lehetőség nincs kiválasztva az ADÓ kiszámításhoz. Nettó összeg: 10,00 ADÓ: 1 x 5,00 = 5,00 ÁFA: 10,00 x 25% = 2,50 Áfa összesen: 5,00 + 2,50 = 7,50 Teljes összeg: 10,00 + 7,50 = 17,50

#### <a name="example-3"></a>3. példa

ÁFA: Kiindulás = Nettó összeg százaléka. Az Áfa előtt számolandó lehetőség ki van választva az ADÓ kiszámításhoz. Nettó összeg: 10,00 ADÓ: 1 x 5,00 = 5,00 ÁFA: (10,00 + 5,00) x 25 % = 3,75 Áfa összesen: 5,00 + 3,75 = 8,75 Teljes összeg: 10,00 + 8,75 = 18,75

#### <a name="example-4"></a>4. példa

Az 1. és a 3. példa eredménye megegyezik, mivel ezekben a példákban csak egy adó szerepel. Tegyük fel, hogy két ADÓ létezik, és az áfaszámítás szempontjából a nettó összeg csak az egyiket tartalmazza: 1. ADÓ: 5,00 az Egységenkénti összeg módszerrel és ki van választva Az áfa előtt számítandó lehetőség; 2. ADÓ: 2,50 az Egységenkénti összeg módszerrel és nincs kiválasztva Az áfa előtt számítandó lehetőség; Áfa: 25% a Nettó összeg százaléka módszerrel: 10,00 1. ADÓ: 1 x 5,00 = 5.00 2. ADÓ: 1 x 2,50 = 2.50 Áfaköteles nettó összeg: 10,00 + 5,00 = 15,00 ÁFA: 15,00 x 25% = 3,75 Áfa összesen, adókkal együtt: 5,00 + 2,50 + 3,75 = 11.25 Teljes összeg: 10,00 + 11,25 = 21,25; A 25%-os ÁFA a nettó összeg értékére kerül kiszámításra (10,00) + 1. ADÓ (5,00) = 15,00. A 2. ADÓT a program az áfa kiszámítása után adja hozzá az adó összegéhez.

## <a name="calculated-percentage-of-net-amount"></a> Nettó összeg számított százalékos értéke
A Nettó összeg számított százalékos értéke az adott dokumentumra vagy naplóra vonatkozó Az összegek tartalmazzák az áfát paraméter beállításának függvényében más-más módon számítja ki az adó értékét.
### <a name="example-1"></a>1. példa

Amennyiben a dokumentum / napló beállítása: Az összegek tartalmazzák az áfát = Igen Tranzakciósor összege: 10,00 Adókulcs: 25% Áfa: Tranzakciósor összege x adókulcs (10,00 x 25%) = 2,50 Adóalap összege (kiindulási összeg): Tranzakciósor összege - áfa = (10,00 - 2,50) = 7,50

### <a name="example-2"></a>2. példa

Amennyiben a dokumentum / napló beállítása: Az összegek tartalmazzák az áfát = Nem Tranzakciósor összege: 10,00 Adókulcs: 25% Áfa: (Tranzakciósor összege x adókulcs) / (100 - adókulcs) (10,00 x 25%) / (100% - 25%) = 3,33 Adóalap összege = 10,00



<a name="see-also"></a>Lásd még
--------

[Az áfaérték megállapítása a Számítás alapja és a Számítási módszer mezők alapján](marginal-base-field.md)

[Teljes összeg és Intervallumszámítás opciók áfakódokhoz](whole-amount-interval-options-sales-tax-codes.md)




