---
title: "Kötelezettségek konfigurálása"
description: "Ez a cikk azoknak az oldalaknak a leírását tartalmazza, amelyek használatával beállíthatók a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition rendszer Kötelezettségek moduljának alapvető, illetve választható funkciói. Azokat a beállítási lépéseket is bemutatja, amelyeket a Kötelezettségek beállításának elkezdése előtt kell elvégezni."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankAccountTable, DeliveryMode, PaymTerm, VendGroup, VendParameters, VendPaymMode, VendTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 24671
ms.assetid: 82561fe7-b2d6-464c-9347-79d0ce0f9743
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 2a61cb86a4f2cfc6d701445c139e22df0db44f8c
ms.contentlocale: hu-hu
ms.lasthandoff: 06/13/2017


---

# <a name="configure-accounts-payable"></a>Kötelezettségek konfigurálása

[!include[banner](../includes/banner.md)]


Ez a cikk azoknak az oldalaknak a leírását tartalmazza, amelyek használatával beállíthatók a Microsoft Dynamics 365 for Finance and Operations, Enterprise edition rendszer Kötelezettségek moduljának alapvető, illetve választható funkciói. Azokat a beállítási lépéseket is bemutatja, amelyeket a Kötelezettségek beállításának elkezdése előtt kell elvégezni.

<a name="prerequisites-for-accounts-payable-setup"></a>Kötelezettségek beállításainak előfeltételei
----------------------------------------

Mielőtt beállítja a Kötelezettségeket el kell végezni az alábbiakat:

-   A Főkönyvben:
    -   Ha kifizetési naplókat szeretne használni, állítsa be azokat a pénzügyben.
    -   Ha árfolyam-korrekciókat szeretne futtatni, akkor adja meg a pénznemkódokat a Pénznemek oldalon, adja meg az árfolyamtípust az Árfolyamtípus oldalon és adja meg a pénznem árfolyamokat a Pénznem árfolyamok oldalon.
-   A Készpénz és bank kezelés szakaszban beállíthatja a kifizetési módokkal használandó bankszámlákat.

## <a name="setup-pages-for-accounts-payable"></a>A Kötelezettségek modul beállítási oldalai

A következő oldalak segítségével minden egyes jogi személyeknél beállíthatja a Kötelezettségek modul alapvető funkcióit. Az oldalak a javasolt beállítási sorrendben vannak felsorolva. A beállítás egyszerűsítése érdekében az első létrehozott rekordból sablonokat hozhat létre. A sablonban az értékek általában több mezőben találhatók, hogy láthatók legyenek a tulajdonságok, amelyeket a szervezet alkalmazni kíván egy adott szállító típushoz.
1.  A Fizetési feltételek oldalon adja meg a fizetés feltételeit, amelyeket értékesítési rendelésekhez, beszerzési rendelésekhez, vevőkhöz és szállítókhoz kíván hozzárendelni és amelyek meghatározzák a számlák határidejét.
2.  A Fizetési módok – szállítók oldalon hozzon létre és frissítse az információkat, hogyan fizet a szervezet a beszállítóknak.
3.  A Szállítói csoportok oldalon hozzon létre és frissítse az információkat a szállítókkal kapcsolatban, akik fontos paraméterekkel rendelkeznek feladással, kiegyenlítéssel, fizetéssel és előrejelzéssel kapcsolatban.
4.  A Szállítói feladási profilok oldalon adja meg hogyan kerüljenek postázásra a szállítói tranzakciók a főkönyvbe.
5.  A Kötelezettség paraméterek oldalon adjon meg alapértelmezett beállításokat amelyek alkalmazhatók, ha egy specifikusabb eset nincs meghatározva, paraméterek különböző funkciókhoz, és különböző számsorok Kötelezettségekhez.
6.  Az Űrlap beállítása oldalon adja meg a különböző dokumentumok formátumát, amelyek kapcsolódnak a szállítóhoz és amelyet a szervezet használ a szállítói bevételezések követéséhez és adjon meg okokat a fizetési folyamatnál a szállítóknak.
7.  A Szállítók oldalon hozzon létre és frissítse a szállítói számlákat, továbbá az adóhatóságokat amelyek áfabevallásra kötelezik a szervezetet.

## <a name="optional-setup-pages-for-accounts-payable"></a>A Kötelezettségek modul opcionális beállítási oldalai
Az alapvető funkciók mellett a Kötelezettségeknek egyéb funkcióit is megadhatja.

A következő beállítási oldalak funkciók szerint vannak csoportosítva.

**Irányelvek**
-   A Szállítói számla irányelvek oldalon adja meg a szállítói számla irányelveket.

**Számlaegyeztetés**

-   A Számlaösszegek tűréshatárai oldalon adja meg a számlaösszegek toleranciáit.
-   Az Egyeztetési irányelv oldalon adja meg a kétirányú és háromirányú egyeztetési irányelveket.
-   Az Ár tűréshatárok oldalon adja meg az egységárak toleranciáit.
-   A Cikkárak toleranciacsoportok oldalon adjon meg toleranciacsoportokat a cikkárakhoz.
-   A Szállítói árak toleranciacsoportok oldalon adjon meg toleranciacsoportokat a szállítói árakhoz.
-   A Díj tűréshatárok oldalon adja meg a díjak toleranciáit.

**Munkafolyamat**

-   A Kötelezettségek munkafolyamatai oldalon adjon meg munkafolyamat konfigurációkat naplójóváhagyásokhoz és beszerzési igénylésekhez.

**Okok**

-   A Szállítói okok oldalon adjon meg okkódokat.

**Költségek**

-   A Költségkódok oldalon adjon meg kódokat a költségekhez, amelyeket a beszerzési rendelésben használ.
-   A Szállító költségcsoportja oldalon hozzon létre és frissítse a szállítók költségcsoportjait.
-   A Cikk-költésgcsoportok oldalon hozza létre és frissítse a cikkek költségcsoportjait.
-   Az Automatikus díjak oldalon adja meg a költségeket amelyek automatikusan a rendelésekhez adódnak.

**Kiegészítő cikkek**

-   A Kiegészítő cikkcsoportok – Szállító oldalon hozza létre és frissítse a szállítók kiegészítő cikkcsoportjait.
-   A Kiegészítő cikkcsoportok – Készlet oldalonhozza létre és frissítse a cikkek kiegészítő cikkcsoportjait.

**Kiosztás**

-   A Szállítás feltételei oldalon hozza létre és frissítse egy cikktranszfer feltételeit az eladótól a vevőhöz.
-   A Szállítási módok oldalon hozza létre és frissítse a szállítási módok amelyek akkor használatosak amikor egy rendelést az eladótól a vevőnek szállítanak.
-   A Célkódok oldalon hozza létre és frissítse az azonosítókhoz és a szállítási célok leírásához.

**Képernyők**

-   Az Adatlap megjegyzései oldalon hozza létre a szabványos szöveget, ami megjelenik az egyes oldalakon.
-   A Képernyő-elrendezés paraméterei oldalon hozzon létre elrendezést igénylésekhez, bevételezési listákhoz, szállítólevelekhez és számlákhoz.
-   A Nyomatatáskezelési oldalon adjon meg nyomtatáskezelési információkat az eredeti és másolt oldalakhoz.

**Kifizetések**

-   A Készpénzfizetési engedmény oldalon adja meg és kezelje a készpénzfizetési engedmények megadásával kapcsolatos feltételeket. A készpénzfizetési engedmények kódjai a szállítókhoz kapcsolódnak, és a beszerzési rendelésekre vonatkoznak.
-   A Fizetési ütemezések oldalon adjon meg fizetési ütemezéseket, amelyeket a szállítóknak történő részletfizetések kezeléséhez használ.
-   A Fizetési napok oldalon adja meg a fizetési napokat, amelyeket a határidők számításához használ, és adja meg a hét vagy hónap sepcifikus fizetési napjait.
-   A Fizetési díj oldalonhozza létre és frissítse a szállítókhoz társított fizetési díjakat.
-   A Fizetési rendelkezés oldalon hozza létre és frissítse a fizetési rendelkezéseket.

**Statisztika**

-   A Korosítási időszak definíciók oldalon adja meg a felhasználó által megadott intervallumokat amelyek a szállítói számlák elosztásának esedékességéhez használatosak.
-   Az Üzletág oldalon hozzon létre üzletágkódokat (LOB) amelyek szállítókhoz rendelhetők.

**Adó 1099**

-   A **1099-es mezők** oldalon ellenőrizze és frissítse a minimális mennyiségeket, amelyeket jelenteni kell az adóhatóságnak (IRS), a legfrissebb követelményeik alapján.

## <a name="optional-setup-for-other-modules"></a>**Opcionális beállítások egyéb modulokhoz**
**Szervezeti adminisztráció**

-   A Számsorozatok oldalon adjon meg szám-szekvenciacsoportokat számlaszámokhoz.
-   A következő oldalakon címeket kell beállítani:
    -   Címbeállítás
    -   NAF-kódok
    -   Irányítószámok importálása

**Főkönyv**

-   A Pénzügyi dimenziók oldalon adjon meg pénzügyi dimenziókat.
-   Az alábbi oldalakon adjon meg adóinformációkat:
    -   Áfakódok
    -   Áfacsoportok
    -   Cikkáfacsoportok
    -   Számlacsoport
    -   Áfamentességi kódok
    -   Áfailletékességek
    -   Adóhatóságok
    -   Áfakiegyenlítési időszakok

**Készpénz- és bankkezelés**

-   A Fizetés célkódok oldalon adja meg a Központi bank célkódját.






