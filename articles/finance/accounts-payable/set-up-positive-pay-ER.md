---
title: Fizetési pozitív fájlok beállítása és létrehozása az Elektronikus jelentés segítségével
description: Ez a témakör bemutatja, hogy hogyan lehet beállítani az elektronikus jelentéssel az pozitív fizetést.
author: panolte
ms.date: 03/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 43dd1a9cba1fe8df5cff26fe76af7e2957a0d6a4
ms.sourcegitcommit: cf7d4af11bf85638ee831a28ea5ee1a1e041a675
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/04/2022
ms.locfileid: "8544544"
---
# <a name="set-up-positive-pay-files-by-using-electronic-reporting"></a>Fizetési fájlok beállítása elektronikus jelentéssel

A fizetési ellenőrzés beállítása elektronikus csekklista generálásához, amely a banknak elküldhető. Ezután, amikor egy csekket bemutatnak a banknak a bank összehasonlítja azt a csekklistával. Ha a csekk megfelel a listában szereplő csekkel a bank törli azt. Ha a csekk nem egyezik meg a listában szereplő csekkel, akkor a bank bent tartja ellenőrzésre.

## <a name="set-up-the-electronic-reporting-configuration"></a>Az elektronikusjelentés-konfiguráció beállítása

1. Ugrás a Munkaterületek **elektronikus \> jelentéséhez**
2. A Microsoft **konfigurációs szolgáltató csempe** tárházát **jelölje ki**.
3. Válassza ki a **Globális**, majd a **Megnyitás** lehetőséget.
4. Ha kapcsolatot kell létesíteni a tárházzal, jelölje ki a kék kapcsolatot a párbeszédpanelen.
5. A konfigurációs listában keresse meg és válassza **a Pozitív fizetési modell \> fizetési formátumot**.
6. Válassza ki **a legújabb** verziót a Verziók gyorsgombra, majd válassza az Importálás **lehetőséget**.

## <a name="set-up-a-positive-pay-format"></a>Ellenőrzött fizetési formátum beállítása

1. Ugrás a Készpénz- **és bankkezelés beállítása \> pozitív \> fizetési formátumokhoz**.
2. Válassza az **Új** lehetőséget.
3. A Kifizetés formátuma **és** **Leírása mezők** beállítása.
4. Jelölje be az **Általános elektronikus exportálási formátum jelölőnégyzetet**.
5. Az Exportálás formátum **konfigurációs mezőjének** beállítása Pozitív **fizetési formátumra**.

## <a name="assign-a-positive-pay-format-to-a-bank-account"></a>Fizetési pozitív formátum hozzárendelése bankszámlához

1. Ugrás a Készpénz- **és bankkezelés – \> Bankok bankszámlákhoz \>**.
2. Nyissa meg a bankszámlát.
3. Az Általános **gyorstára** a Korábban **létrehozott** formátumra állítsa a Pozitív fizetési formátum mezőt.
4. A Fizetés pozitív **kezdő dátum mezőjének** beállítása az aktuális dátumra.

## <a name="generate-a-positive-pay-file"></a>Fizetési ellenőrző fájl előállítása

1. Váltson a Készpénz **- és bankkezelés bankszámláihoz \>\>**.
2. Annak a bankszámlának a megnyitása, amely számára a fizetési pozitív beállítás van beállítva.
3. Válassza a **Fizetések kezelése \> fizetési pozitív \> fizetési fájlt**.
4. Állítsa be **a Határidő mező** beállítását. A program az e dátum előtt létrehozott csekkeket is tartalmazza.

A kapott XML-fájl letölti.
