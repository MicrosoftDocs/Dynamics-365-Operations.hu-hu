---
title: Kötelezettségek konfigurálása – áttekintés
description: Ez a cikk azoknak az oldalaknak a leírását tartalmazza, amelyek használatával beállíthatók a Kötelezettségek modul alapvető, illetve választható funkciói. Azokat a beállítási lépéseket is bemutatja, amelyeket a Kötelezettségek beállításának elkezdése előtt kell elvégezni.
author: abruer
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BankAccountTable, DeliveryMode, PaymTerm, VendGroup, VendParameters, VendPaymMode, VendTable, DeliveryReason, DeliveryTerms, DestinationCode
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "24671"
- intro-internal
ms.assetid: 82561fe7-b2d6-464c-9347-79d0ce0f9743
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bce5da0c9593bcfcfb9589f8fe7e09b8acd63726
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906532"
---
# <a name="configure-accounts-payable-overview"></a>Kötelezettségek konfigurálása – áttekintés

[!include [banner](../includes/banner.md)]

Ez a cikk azoknak az oldalaknak a leírását tartalmazza, amelyek használatával beállíthatók a Kötelezettségek modul alapvető, illetve választható funkciói. Azokat a beállítási lépéseket is bemutatja, amelyeket a Kötelezettségek beállításának elkezdése előtt kell elvégezni.

## <a name="prerequisites-for-accounts-payable-setup"></a>Kötelezettségek beállításainak előfeltételei

Mielőtt beállítja a Kötelezettségeket el kell végezni az alábbiakat:

-   A főkönyvben:
    -   Ha kifizetési naplókat szeretne használni, állítsa be azokat a pénzügyben.
    -   Ha árfolyam-korrekciókat is futtatni tervez, **állítsa** be a pénznemkódokat a Pénznemek lapon, **állítsa** be az árfolyamtípusokat az Árfolyamtípusok lapon, **és állítsa be az árfolyamokat a Pénznemek** lapon.
-   A Készpénz és bank kezelés szakaszban beállíthatja a kifizetési módokkal használandó bankszámlákat.

## <a name="setup-pages-for-accounts-payable"></a>A Kötelezettségek modul beállítási oldalai

A következő oldalak segítségével minden egyes jogi személyeknél beállíthatja a Kötelezettségek modul alapvető funkcióit. Az oldalak a javasolt beállítási sorrendben vannak felsorolva. A beállítás egyszerűsítése érdekében az első létrehozott rekordból sablonokat hozhat létre. A sablonban az értékek általában több mezőben találhatók, hogy láthatók legyenek a tulajdonságok, amelyeket a szervezet alkalmazni kíván egy adott szállító típushoz.
1.  A Fizetési **feltételek** lapon határozza meg az értékesítési rendelésekhez, beszerzési rendelésekhez, vevőkhöz és szállítókhoz hozzárendelt fizetési feltételeket, amelyek meghatározzák a számla esedékességeit. További információkért lásd: [Szállítói kifizetési díjak meghatározása](tasks/define-vendor-payment-fees.md).
2.  A Fizetési **módok – szállítók lapon** hozza létre és tarthatja karban a szervezet szállítóit kifizető adatokat.
3.  A Szállítói **csoportok** lapon hozhatja létre és tarthatja karban a szállítócsoportok olyan csoportjait, amelyeknél a feladás, a kiegyenlítés és a fizetés, a jelentés és az előrejelzés fontos paramétereik vannak.
4.  A Szállítói feladási **profilok** lapon adja meg, hogyan adja fel a rendszer a szállítói tranzakciókat a főkönyvbe.
5.  **A Kötelezettségek** paraméterei lapon állítsa be az olyan alapértelmezett beállításokat, amelyeket akkor alkalmaz a program, ha konkrétabb beállítás nincs megadva, a különböző funkciók paramétereit, valamint a Kötelezettségek különböző számsorozatokat.
6.  A képernyőbeállítási **lapon** definiálja a szállítókhoz kapcsolódó különféle dokumentumok formátumát, valamint azt, hogy a szervezet nyomon kövesse a szállítóktól való bevételezéseket, és adja meg a szállítóknak történő fizetés folyamatának okát.
7.  A Szállítók **lapon hozhatja** létre és tarthatja karban a szállítói számlákat, valamint az adóhatóságokat, amelyek számára a szervezet bevallja az áfáit.

## <a name="optional-setup-pages-for-accounts-payable"></a>A Kötelezettségek modul opcionális beállítási oldalai
Az alapvető funkciók mellett a Kötelezettségeknek egyéb funkcióit is megadhatja.

A következő beállítási oldalak funkciók szerint vannak csoportosítva.

**Irányelvek**
-   A Szállítói **számla irányelvlapon** állítsa be a szállítói számla irányelveit.

**Számlaegyeztetés**

-   A Számlaösszegek **tűréshatárai** lapon állítsa be a számlaösszegek tűréshatárát.
-   Az Egyeztetési **irányelv** oldalon állítsa be a oda-vissza megfeleltetési irányelveket.
-   Az Ártűréshatárok **lapon** állítsa be az egységárak tűréshatárát.
-   Az ártűréshatár **szerint a cikkek árcsoportja** lapon állítsa be a cikkárak tűrési csoportjait.
-   Az ártűréshatár **szerint szállítócsoportok** lapon állítsa be a szállítói árak tűrési csoportjait.
-   A Költségek **tűréshatára** lapon állítsa be a költségek tűrési tűréshatárát.

**Munkafolyamat**

-   A Kötelezettségek **munkafolyamatok lapon** állítsa be a napló-jóváhagyások és a beszerzési igénylések munkafolyamat-konfigurációit.

**Okok**

-   A Szállítói **okok** lapon állítsa be az okkódokat.

**Költségek**

-   A Költségek kódja **lapon** állítsa be a beszerzési rendelésekben használt költségek kódjait.
-   A Szállítói **költségcsoport** lapon hozza létre és tarthatja karban a szállítók költségcsoportját.
-   A Cikk-költségcsoportok **lapon** hozza létre és tarthatja karban a cikkek költségcsoportját.
-   Az Automatikus **költségek** lapon határozza meg a rendelésekhez automatikusan hozzárendelt költségeket.

**Kiegészítő cikkek**

-   A Kiegészítő cikkcsoportok **– Szállító** lapon hozza létre és tarthatja karban a szállítókhoz tartozó kiegészítő cikkcsoportokat.
-   A Kiegészítő cikkcsoportok **– Készlet lapon** hozza létre és tarthatja karban a cikkekhez tartozó kiegészítő cikkcsoportokat.

**Kiosztás**

-   A Szállítási **feltételek lapon** a cikkek eladótól a vevőhöz történő átvitelére vonatkozó feltételeket hozhat létre és tarthatja karban.
-   A Szállítási **módok lapon** hozhatja létre és tarthatja karban a rendelés eladótól a vevőhöz történő szállítása során használt szállítási módokat.
-   A Célkódok **lapon** hozza létre és tartsa karban a szállítási célok azonosítóit és leírásait.

**Képernyők**

-   A Képernyő megjegyzései **lapon** hozza létre a különböző lapokon megjelenő szabványos szöveget.
-   A képernyőrendezési **paraméterek** lapon állítsa be az igénylések, bevételezési listák, csomagjegyzékek és számlák rendezési sorrendjét.
-   A Nyomtatáskezelés **beállítása** lapon állítsa be a lapok eredeti és másolati példányának nyomtatáskezelési adatait.

**Kifizetések**

-   A Készpénzfizetési **engedmények** lapon lehet beállítani és kezelni a készpénzfizetési engedmények megszerzésének feltételeit. A készpénzfizetési engedmények kódjai a szállítókhoz kapcsolódnak, és a beszerzési rendelésekre vonatkoznak.
-   A Fizetés **ütemezése** lapon állítsa be a fizetési ütemezéseket, amelyek a szállítóknak történő részletfizetések kezelésére használatosak.
-   A Fizetési **napok** lapon határozza meg a határidők kiszámításához használt fizetési napokat, és adja meg a fizetési napokat a hét vagy a hónap egy adott napjára.
-   A Kifizetési **díj lapon** hozza létre és tartsa karban a szállítókhoz társított kifizetési díjakat.
-   A Fizetési **utasítások lapon** hozza létre és tartsa karban a fizetési utasításokat.

**Statisztika**

-   A Korosítási **időszak definíciója** lapon állítsa be a felhasználó által definiált intervallumokat, amelyek a szállítói számlák esedékességi eloszlását elemzik.
-   Hozza létre **a** szállítókhoz rendelt üzletágkódokat az Üzletág lapon.

**Adó 1099**

-   A **1099-es mezők** oldalon ellenőrizze és frissítse a minimális mennyiségeket, amelyeket jelenteni kell az adóhatóságnak (IRS), a legfrissebb követelményeik alapján.

## <a name="optional-setup-for-other-modules"></a>**Opcionális beállítások egyéb modulokhoz**
**Szervezeti adminisztráció**

-   A Számsorozatok **lapon** állítsa be a számlaszámok számsorozatcsoportját.
-   A következő oldalakon címeket kell beállítani:
    -   **Címbeállítás**
    -   **NAF-kódok**
    -   **Irányítószámok importálása**

**Főkönyv**

-   A Pénzügyi **dimenziók** lapon állítsa be a pénzügyi dimenziókat.
-   Az alábbi oldalakon adjon meg adóinformációkat:
    -   **Áfakódok**
    -   **Áfacsoportok**
    -   **Cikkáfacsoportok**
    -   **Számlacsoport**
    -   **Áfamentességi kódok**
    -   **Áfailletékességek**
    -   **Adóhatóságok**
    -   **Áfakiegyenlítési időszakok**

**Készpénz- és bankkezelés**

-   A Kifizetés célkódok **lapján** állítsa be a **Központi Bank célkódját**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
