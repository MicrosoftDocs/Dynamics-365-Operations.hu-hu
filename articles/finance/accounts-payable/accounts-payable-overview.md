---
title: Kötelezettségek konfigurálása – áttekintés
description: Ez a témakör azokat az oldalakat ismerteti, amelyekkel a kötelezettségek alapvető és választható funkcióinak beállítására használható. Azokat a beállítási lépéseket is bemutatja, amelyeket a Kötelezettségek beállításának elkezdése előtt kell elvégezni.
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
ms.openlocfilehash: 4ed5664b5be11f013900d6411d4307692d5e8334
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/26/2022
ms.locfileid: "8358168"
---
# <a name="configure-accounts-payable-overview"></a>Kötelezettségek konfigurálása – áttekintés

[!include [banner](../includes/banner.md)]

Ez a cikk azoknak az oldalaknak a leírását tartalmazza, amelyek használatával beállíthatók a Kötelezettségek modul alapvető, illetve választható funkciói. Azokat a beállítási lépéseket is bemutatja, amelyeket a Kötelezettségek beállításának elkezdése előtt kell elvégezni.

## <a name="prerequisites-for-accounts-payable-setup"></a>Kötelezettségek beállításainak előfeltételei

Mielőtt beállítja a Kötelezettségeket el kell végezni az alábbiakat:

-   A főkönyvben:
    -   Ha kifizetési naplókat szeretne használni, állítsa be azokat a pénzügyben.
    -   Ha árfolyamkorrekciókat tervez futtatni, állítsa be a Pénznemek oldalt, állítsa be az **árfolyamtípusokat** az **Árfolyamtípusok** lapon, és állítsa be a valutaárfolyamokat a **Pénznem árfolyamok** oldalon.
-   A Készpénz és bank kezelés szakaszban beállíthatja a kifizetési módokkal használandó bankszámlákat.

## <a name="setup-pages-for-accounts-payable"></a>A Kötelezettségek modul beállítási oldalai

A következő oldalak segítségével minden egyes jogi személyeknél beállíthatja a Kötelezettségek modul alapvető funkcióit. Az oldalak a javasolt beállítási sorrendben vannak felsorolva. A beállítás egyszerűsítése érdekében az első létrehozott rekordból sablonokat hozhat létre. A sablonban az értékek általában több mezőben találhatók, hogy láthatók legyenek a tulajdonságok, amelyeket a szervezet alkalmazni kíván egy adott szállító típushoz.
1.  **A Fizetési** feltételek lapon határozza meg az értékesítési rendelésekhez, beszerzési rendelésekhez, vevőkhöz és szállítókhoz rendelt fizetési feltételeket, amelyek meghatározzák a számla esedékességét. További információkért lásd: [Szállítói kifizetési díjak meghatározása](tasks/define-vendor-payment-fees.md).
2.  **A Fizetési módok - szállítók** oldalon hozzon létre és tartson fenn információkat arról, hogy a szervezet hogyan fizeti a szállítóit.
3.  **A Szállítócsoportok** lapon hozzon létre és tartson fenn szállítói csoportokat, amelyek fontos paramétereket osztanak meg a könyveléshez, kiegyenlítéshez és kifizetéshez, a jelentéskészítéshez és az előrejelzéshez.
4.  **A Szállítói könyvelési profilok** lapon adja meg, hogy a szállítói tranzakciók hogyan legyenek könyvelve a főkönyvbe.
5.  A Kötelezettségek paraméterek **lapon állítsa be az** alapértelmezett beállításokat, amelyek akkor érvényesek, ha nincs megadva egy adottabb beállítás, a különböző típusú funkciók paraméterei és a kötelezettségek különböző számsorozatai.
6.  **Az Űrlap beállítása** lapon adja meg a szállítókhoz kapcsolódó különböző bizonylatok formátumát, és hogy a szervezet a szállítóktól származó bevételek nyomon követésére és a szállítóknak történő kifizetések folyamatának okaira használja.
7.  **A Szállítók** lapon hozzon létre és tartson fenn szállítói számlákat, valamint azokat az adóhatóságokat, amelyeknek a szervezet jelenti az értékesítési adókat.

## <a name="optional-setup-pages-for-accounts-payable"></a>A Kötelezettségek modul opcionális beállítási oldalai
Az alapvető funkciók mellett a Kötelezettségeknek egyéb funkcióit is megadhatja.

A következő beállítási oldalak funkciók szerint vannak csoportosítva.

**Irányelvek**
-   A Szállítói számlaházirend **lapon állítsa be a** szállítói számlaházirendeket.

**Számlaegyeztetés**

-   **A Számlaösszegek tűrések** lapon állítson be tűréshatárokat a számlaösszegekre.
-   Az Egyező házirend **lapon állítsa be a** kétirányú és a hármas egyeztetési házirendeket.
-   Az Ártűrések **lapon állítsa be az** egységárakra vonatkozó tűréshatárokat.
-   **A Cikkártűrési csoportok** lapon állítson be toleranciacsoportokat a cikkárakhoz.
-   **A Szállítói ártűrési csoportok** lapon állítson be toleranciacsoportokat a szállítói árakhoz.
-   **A Díjak tűréshatárok** lapon állítsa be a díjakra vonatkozó tűréshatárokat.

**Munkafolyamat**

-   A Kötelezettségek munkafolyamatok **lapon állítsa be a** munkafolyamat-konfigurációkat a napló-jóváhagyásokhoz és a beszerzési igénylésekhez.

**Okok**

-   A Szállítói okok **lapon állítsa be az** okkódokat.

**Költségek**

-   **A Díjak kódlapon** állítsa be a beszerzési rendelésekben használt díjak kódjait.
-   **A Szállítói költségek csoport** lapon hozzon létre és tartson fenn költségcsoportokat a szállítók számára.
-   **A Cikkköltségcsoportok** lapon hozzon létre és tartson fenn költségcsoportokat az elemekhez.
-   **Az Automatikus díjak** lapon adja meg a rendelésekhez automatikusan hozzárendelt díjakat.

**Kiegészítő cikkek**

-   **A Kiegészítő cikkcsoportok – Szállító** lapon kiegészítő cikkcsoportokat hozhat létre és tarthat karban a szállítók számára.
-   **A Kiegészítő cikkcsoportok – Készlet** lapon hozzon létre és tartson fenn kiegészítő cikkcsoportokat a cikkekhez.

**Kiosztás**

-   **A Szállítási** feltételek oldalon hozza létre és tartsa karban a cikk eladóról vevőre történő átvitelének feltételeit.
-   **A Szállítási** módok oldalon hozza létre és tartsa karban azokat a szállítási módokat, amelyeket akkor használnak, amikor a megrendelést az eladótól a vevőhöz szállítják.
-   **A Célkódok** lapon hozzon létre és tartson fenn azonosítókat és leírásokat a kézbesítési célokhoz.

**Képernyők**

-   **Az Űrlapjegyzetek** lapon hozza létre a különböző oldalakon megjelenő szabványos szöveget.
-   **Az Űrlap rendezési paraméterei** lapon állítsa be az igénylések, nyugtalmi listák, szállítólevelek és számlák rendezési sorrendjét.
-   A Nyomtatáskezelés beállítási **lapon állítsa be a** nyomtatáskezelési információkat az eredeti és az oldalak másolataihoz.

**Kifizetések**

-   **A Készpénzengedmények** oldalon állítsa be és kezelje a készpénzengedmények megszerzésének feltételeit. A készpénzfizetési engedmények kódjai a szállítókhoz kapcsolódnak, és a beszerzési rendelésekre vonatkoznak.
-   **A Fizetési ütemezések** lapon állítsa be a szállítóknak történő részletfizetések kezelésére használt fizetési ütemezéseket.
-   **A Fizetési napok** lapon határozza meg az esedékességi dátumok kiszámításához használt fizetési napokat, és adja meg a hét vagy hónap egy adott napjára vonatkozó fizetési napokat.
-   **A Fizetési díj** lapon hozza létre és tartsa karban a szállítókhoz társított fizetési díjakat.
-   **A Fizetési utasítás** oldalon hozzon létre és tartson fenn fizetési utasításokat.

**Statisztika**

-   Az Elévülési időszak definíciói **lapon állítsa be a** felhasználó által definiált intervallumokat, amelyek a szállítói számlák lejárati eloszlásának elemzésére szolgálnak.
-   **Az üzletág** lapon hozza létre a szállítókhoz rendelt üzletági (LOB) kódokat.

**Adó 1099**

-   A **1099-es mezők** oldalon ellenőrizze és frissítse a minimális mennyiségeket, amelyeket jelenteni kell az adóhatóságnak (IRS), a legfrissebb követelményeik alapján.

## <a name="optional-setup-for-other-modules"></a>**Opcionális beállítások egyéb modulokhoz**
**Szervezeti adminisztráció**

-   A Számsorozatok **lapon állítsa be a** számlaszámok számsorozat-csoportjait.
-   A következő oldalakon címeket kell beállítani:
    -   **Címbeállítás**
    -   **NAF-kódok**
    -   **Irányítószámok importálása**

**Főkönyv**

-   **A Pénzügyi dimenziók** lapon állítsa be a pénzügyi dimenziókat.
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

-   **A Fizetési célkódok** oldalon állítsa be a **központi bank célkódját**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
