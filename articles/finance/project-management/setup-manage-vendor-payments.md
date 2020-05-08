---
title: Saját fizetés beérkezésekor fizetendő szállítói fizetések beállítása és használata
description: Ez a témakör azt mutatja be, hogyan lehet saját fizetés beérkezésekor fizetendő (PWP) feltételeket létrehozni részleges szállítói kifizetések engedélyezéséhez a vevői kifizetések alapján.
author: RadhikaRS
manager: AnnBe
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 390cec62d2790ed10892669e283f2283c6b8e686
ms.sourcegitcommit: 399f128d90b71bd836a1c8c0c8c257b7f9eeb39a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/23/2020
ms.locfileid: "3284113"
---
# <a name="set-up-and-use-pay-when-paid-vendor-payments"></a>Saját fizetés beérkezésekor fizetendő szállítói fizetések beállítása és használata

[!include [banner](../includes/banner.md)]

Amikor engedélyezi egy szállítónak, hogy alvállalkozóként dolgozzon, visszatarthatja a szállító kifizetését, amíg a vevő ki nem fizeti a projektet. Ezen forgatókönyv támogatásához állítsa be fizetés beérkezésekor fizetendő (PWP) feltételeket beállításakor a beszerzési rendelés (PO) a szállítóval beállításakor.

Például, amikor a vevő a projektszámlán szereplő összeget kifizeti, kiadhatja a kifizetéshez kapcsolódó szállítói számlák összegének egy részét vagy egészét. PWP feltételek beállításával meghatározhatja, hogy a szállítót a vevőtől származó kapcsolódó fizetés meghatározott százalékának fogadását követően fizetik ki. Ha egy vevőtől részleges kifizetés érkezik, manuálisan kiadhatja a kifizetéshez kapcsolódó szállítói számlákat.

A következő példa azokat a folyamatokat ismerteti, amikor PWP feltételeket alkalmaznak.

## <a name="example"></a>Példa

A szervezet beleegyezik abba, hogy 100 telepített szoftverrel rendelkező számítógépet szállít számítógépenként 150,00 dollárért (USD). Ezután felfogad egy szállítót, hogy biztosítsa a számítógépeket a telepített szoftverrel. A szerződésnek megfelelően a vevőnek jóvá kell hagynia a számítógépek minőségét, mielőtt kifizeti az Ön szervezetét. A szervezet eljárása, hogy amíg a vevő nem fizet visszatartja a kifizetést a szállítóknak. Ennélfogva a projekt úgy van beállítva, hogy a PWP százalék 100 százalék legyen.

A szállító elküldi a telepített szoftverrel rendelkező 100-es számítógépet, valamint a 10 000,00 dolláros számláját. Mivel a projekthez PWP-feltételek vannak beállítva, a számítógépek kézhezvételét követően nem fizeti ki a szállítót. Ehelyett a számítógépeket elküldi a vevőnek egy 15 000,00 dolláros számlával együtt. A vevő megvizsgálja a számítógépeket és jóváhagyja a projektszámla teljes összegét.

A vevőtől érkező teljes kifizetés megérkezését követően, kifizeti a szállító részére a 10 000,00-os szállítói számla teljes összegét.

## <a name="set-up-pwp-terms-for-a-project"></a>A projekt PWP feltételeinek beállítása

Ha PWP-feltételeket állít be egy projekthez, akkor százalékban kell megadni azt a minimális összeget, amelyet a vevőnek ki kell fizetnie a projektért, mielőtt kifizeti a szállítót. A rendszer a küszöbérték összegét automatikusan számítja ki a projekthez tartozó vevői számlákhoz. A küszöbérték százalékának beállításához a PWP-feltételekhez tegye a következőket:

1. Ugorjon a **Projektvezetés és könyvelés** \> **Projektek** \> **Minden projekt** pontra.
2. Keresse meg és nyissa meg azt a projektet, amelyhez be szeretné állítani a PWP-feltételeket.
3. A **Szállítói megállapodások** gyorslapon válassza a **Sor hozzáadása** lehetőséget.
3. A **Számlakód** mezőben válasszon egyet a következő lehetőségek közül:

    - **Tábla** – A „saját fizetés beérkezésekor fizetendő” feltételek egyetlen szállítóra vonatkoznak.
    - **Csoport** – A „saját fizetés beérkezésekor fizetendő” feltételek egy szállítócsoportba felvett összes szállítóra érvényesek.
    - **Mind** – A „saját fizetés beérkezésekor fizetendő” feltételek az összes szállítóra érvényesek.

4. Ha az előző lépésben kiválasztotta a **Tábla** vagy a **Csoportot** a **Szállító / Szállítói csoport** mezőben válassza ki azt a szállítót vagy szállítói csoportot, amelyre „saját fizetés beérkezésekor fizetendő” feltételek vonatkoznak. Ha az előző lépésben a **Mind** beállítást választotta, akkor a **Szállítói/ szállítói csoport** mező nem szerkeszthető.
5. Ha a projekthez a szállítóra vonatkozó visszatartási feltételek is be vannak állítva, a **Szállító visszatartási feltételei** mezőben válassza ki a visszatartási feltételek szabályazonosítóját.
6. A **PWP küszöbérték százalékértéke** mezőben adja meg a százalékos küszöbértéket a projekthez. A projekthez megadott százalék határozza meg azt a minimális összeget, amelyet a vevőnek ki kell fizetnie mielőtt Ön fizetne a szállítónak.

## <a name="create-a-po-that-has-pwp-terms"></a>PWP feltételeket tartalmazó beszerzési rendelés létrehozása

Amikor feladja a szállító számláját, ha a szállítóra a „saját fizetés beérkezésekor fizetendő” feltételek vonatkoznak, a beszerzési rendelés soraiban megjelennek ezek a feltételek. A PWP feltételeket tartalmazó beszerzési rendelés létrehozásához hajtsa végre az alábbi lépéseket.

1. Menjen a **Beszerzés és forrás** \> **Beszerzési rendelés** \> **Összes beszerzési rendelés** pontra.
2. A Műveleti ablaktáblán kattintson az **Új** elemre. Ezután a **Beszerzési rendelés létrehozása** párbeszédpanelen írja be a szükséges adatokat, és válassza az **OK** lehetőséget.

    Azt is megteheti, hogy megnyit egy létező beszerzési rendelést az **Összes beszerzési rendelés** listaoldalon.

4. A **Beszerzési rendelés** oldalon **Beszerzésirendelés-sorok** gyorslapon ellenőrizze a szállítóra vonatkozó beszerzésirendelés-sort. A **Saját fizetés beérkezésekor történő kifizetés** automatikusan be van jelölve , és a rendszer automatikusan átmásolja a **PWP küszöbérték százalékértéke** mező értékét a **PWP küszöbértékének százalékértéke** mezőből a **Projektek** oldalról.
6. Ha nem szeretné alkalmazni a PWP feltételeket egy beszerzésirendelés-sorhoz, törölje a **Saját fizetés beérkezésekor történő kifizetés** beállítás jelölését. Ebben az esetben a program a **PWP küszöbérték százalékértéke** mezőt 0 (nulla) értékre állítja vissza.

## <a name="update-a-customer-payment-and-pay-the-vendor"></a>Egy vevői fizetési frissítése, és a szállító kifizetése

Ha a szállító befejezi a munkát egy projekten, és számlát küld Önnek, ellenőriznie kell a projekt állapotát és a vevői számlákat, hogy megállapítsa, teljesültek-e a projekt „saját fizetés beérkezésekor fizetendő” feltételei. Ha a szállító „saját fizetés beérkezésekor fizetendő” feltételei teljesültek, a projekt vevői kifizetései alapján meghatározhatja, hogy a szállítói számla melyik sorai fizethetők ki. Ha úgy dönt, hogy kifizeti a szállítót annak ellenére, hogy a PWP-feltételek nem teljesülnek, akkor felülbírálhatja a PWP feltételeket a **Szállítói számlák saját fizetés beérkezésekor fizetendő módozattal** lapon.

1. Válassz a **Projektvezetés és könyvelés** \> **Lekérdezések és a jelentések** \> **Visszatartási lekérdezések** \> **Szállítói számlák saját fizetés beérkezésekor fizetendő módozattal** lehetőséget.
2. A **Szállítói számlák saját fizetés beérkezésekor fizetendő módozattal** lapon a keresés mezőbe írja be az áttekinteni kívánt szállítói számla megkereséséhez használandó értékeket, majd válassza a **Keresés** lehetőséget.
3. Válassza ki a módosítani kívánt sorokat a **Szállítói számlasorok** gyorslapon.
4. A **Saját fizetés beérkezésekor történő kifizetés** feltételeinek teljesülése esetén a számlasorban válassza a **Szállítói fizetés felszabadítása** lehetőséget. A **Saját fizetés beérkezésekor történő kifizetés** beállítás jelölése törlődik, és a **Fizetésre kész** mező értéke **Igen** értékre változik.
