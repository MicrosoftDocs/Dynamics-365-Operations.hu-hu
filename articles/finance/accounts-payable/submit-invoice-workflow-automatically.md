---
title: Számlák elküldése a munkafolyamat-rendszerbe és a terméknyugtasorok egyeztetése
description: Ez a témakör a szállítói számlák munkafolyamat-rendszerbe történő elküldését és a feladott terméknyugta sorainak a szállítói számlák soraival való automatikus egyeztetését ismerteti.
author: abruer
manager: AnnBe
ms.date: 09/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 534b5dbc54a516fea0b3f7090042d247c1076737
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231542"
---
# <a name="submit-invoices-to-the-workflow-system-and-match-product-receipt-lines"></a>Számlák elküldése a munkafolyamat-rendszerbe és a terméknyugtasorok egyeztetése

[!include [banner](../includes/banner.md)]

Ez a témakör a szállítói számlák munkafolyamat-rendszerbe történő elküldését és a feladott terméknyugta sorainak a szállítói számlák soraival való automatikus egyeztetését ismerteti.

## <a name="submitting-imported-vendor-invoices-to-the-workflow-system-and-matching-posted-product-receipt-lines-to-pending-vendor-invoice-lines"></a>Az importált szállítói számlák munkafolyamat-rendszerbe történő beküldése és a feladott terméknyugta sorainak egyeztetése a függőben lévő szállítói számlák soraival.

Az érintés nélküli, Kötelezettségeken belüli számlázási folyamat részeként a rendszer automatikusan elküldhet importált számlákat a munkafolyamat-rendszerbe. Az importált számláknak a munkafolyamat-rendszerbe történő elküldésének folyamatát a **Kötelezettségek paraméterei** oldal **Szállítói számla automatizálása** fülén konfigurálhatja (**Kötelezettségek \> Beállítás \> Kötelezettségek paraméterei**). A munkafolyamatba való beküldés folyamata a háttérben történik, az Ön által megadott gyakorisággal (óránként vagy naponta).

Amikor a számlákat automatikusan küldi el a munkafolyamat-rendszerbe, akkor a folyamatnak egy importált számlával kell kezdődnie. Ha azt szeretné, hogy a számla manuális beavatkozás nélkül is feldolgozható legyen az elejétől a végéig, akkor a munkafolyamat-konfigurációban szerepelnie kell egy automatikus feladási feladatnak. A vételi megbízásokhoz (PO-k) kapcsolódó számlák, valamint a nem PO-beszerzési kategóriát és nem raktározott sorokat tartalmazó számlák automatikusan elküldhetők a munkafolyamat-rendszerbe. A manuálisan bevitt számlákat manuálisan kell elküldeni a munkafolyamat-rendszerbe.

A munkafolyamatban a **Beküldte** elemhez megadott érték az a felhasználói azonosító, amelyet a rendszer a **Szállítói számlák elküldése a munkafolyamatba** háttérfeladathoz megadott a **Folyamatautomatizálás** oldalon. Az a felhasználó, akié az adott felhasználóazonosító, szükség szerint le tudja hívni a számlát a munkafolyamat-rendszerből.

## <a name="matching-posted-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>A terméknyugták sorainak egyeztetése olyan számlasorokkal, amelyekhez háromirányú egyeztetési irányelv tartozik

Az érintés nélküli, kötelezettségeken belüli számlázási folyamat részeként a rendszer automatikusan egyezteti a feladott terméknyugtákat a számlasorokkal. Ehhez a feladathoz egy háromirányú egyeztetési irányelvet kell definiálni. Ez a funkció akkor érhető el, ha a **Szállítói számla automatizálása** funkció engedélyezett a **Funkciókezelés** oldalon.

A folyamat addig fog futni, amíg az egyeztetett terméknyugták mennyisége nem egyezik meg a számla szerinti mennyiséggel. E folyamat részeként kiválaszthatja, hogy hány alkalommal próbálja meg a rendszer egyeztetni a terméknyugtákat egy adott számlasorral, mielőtt a folyamatot sikertelenként lezárná. A folyamat a háttérben fog futni, óránként vagy naponta. Az automatizált egyeztetési folyamat futtatható a számlák munkafolyamat-rendszerbe történő elküldéséhez kapcsolódó eljárás részeként. Azt is megteheti, hogy önálló folyamatként futtatja. A terméknyugták egyeztetések a számlasorokkal folyamat beállításait a **Kötelezettségek paraméterei** oldal **Szállítói számla automatizálása** fülén konfigurálhatja (**Kötelezettségek \> Beállítás \> Kötelezettségek paraméterei**).

Azon háromirányú egyeztetési irányelvet tartalmazó számlasorok, amelyeknél az egyeztetett nyugta mennyisége kisebb, mint a számlamennyiség, az automatikus terméknyugtákkal való egyeztetési folyamatba kerülnek.

Ha meg szeretné tekinteni az automatikus munkafolyamatba küldési folyamat részét nem képező számlák **Utolsó egyeztetésének** állapotát, akkor nyissa meg a számlát a **Szállítói számlák** oldalról. A számla megtekintésekor a program frissíti a megfelelő érvényesítési adatokat. Az **Utolsó egyeztetés** állapot automatikusan frissíthető a **Számlaegyeztetés ellenőrzése** háttérfeladat segítségével. A folyamatot az **Utolsó egyeztetés** állapot automatikus frissítésével konfigurálhatja, amelyet a **Folyamatautomatizálások** oldal **Háttérfolyamatok** lapján (**Rendszerfelügyelet \> Beállítás \> Folyamatautomatizálás**) pontban állíthat be.

A program kizárja az automatizált feldolgozásból azokat a számlasorokat, amelyeknél a következő feltételek bármelyike teljesül:

- A számlasorhoz tartozó **Automatikus nyugtaegyeztetési állapot** értéke **Sikertelen**.
- A számla használatban van.
- A számla a munkafolyamat-rendszerben van.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]