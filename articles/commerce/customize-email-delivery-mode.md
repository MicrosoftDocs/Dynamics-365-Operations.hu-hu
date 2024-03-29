---
title: Tranzakciós e-mailek testreszabása kézbesítési mód szerint
description: Ez a témakör azt ismerteti, hogyan lehet beállítani egyéni e-mail sablonokat a megadott értesítési típusokhoz és szállítási módokhoz Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.16
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 0c0bd218c10a373d142ddcc7780c5339569f7a07
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275704"
---
# <a name="customize-transactional-emails-by-mode-of-delivery"></a>Tranzakciós e-mailek testreszabása kézbesítési mód szerint

[!include [banner](includes/banner.md)]

Ez a témakör azt ismerteti, hogyan lehet beállítani egyéni e-mail sablonokat a megadott értesítési típusokhoz és szállítási módokhoz Microsoft Dynamics 365 Commerce.

A tranzakciós e-mailek mostantól testreszabhatók egy értesítési típus (például **Rendelés létrehozva**, **Rendelés csomagolva** vagy **Rendelés számlázva**) és egy kézbesítési mód (pl. egynapos, átvétel üzletben, átvétel utcán) kombinációjára vonatkozóan. Az egyéni tranzakciós e-mailek lehetővé teszik a kiskereskedők számára, hogy ügyfeleik rendeléseinek olyan teljesítési élményeket nyújtsanak, amelyek a megrendelés szállítási módjához igazodnak. A "rendelés csomagolva" esemény például testre szabható, így útszéli felvételi utasításokat biztosít azoknak az ügyfeleknek, akik a járdaszéli felvételeket választják. Másik lehetőségként szállítmányozói és szállítási információkat is biztosíthat azoknak az ügyfeleknek, akik úgy döntenek, hogy a rendelésüket szállíttatják.

> [!NOTE]
> A testreszabott tranzakciós e-mailek funkcióinak használatához először be kell kapcsolnia a **Tranzakciós e-mail sablonok testreszabása kézbesítési mód szerint** funkciót a Commerce központ **Munkaterületek \> Funkciókezelés** megnyitásával.

Az e-mailek a következő értesítési típusoknál szabhatók testre a kézbesítési mód szerint:

- **Rendelés törlése** – Ez az e-mail értesítéstípus új.
- **Rendelés létrehozva**
- **Rendelés visszaigazolva**
- **Rendelés számlázva** – Ez az e-mail értesítéstípus új. Ez a **Rendelés szállítva** értesítési típus helyett használható, amely értesítést küld bármely olyan számlázási esemény esetén, amelynél a kézbesítési mód szállítva (nem átvétel, nem azonnali szállítás vagy elektronikus szállítási mód).
- **Rendelés kitárolva**
- **Rendelés csomagolva**
- **Rendelésre kitárolásra kész** – Ez az értesítési típus testreszabható kézbesítési mód szerint, csak akkor ha a **Több felvételi szállítási mód engedélyezése** funkció be van kapcsolva. Ebben az esetben ez az értesítéstípus funkcionálisan egyenértékű a **Rendelés csomagolva** értesítéstípussal.
- **Fizetés sikertelen**
- **Csererendelés létrehozva**

## <a name="configure-email-templates-for-specific-modes-of-delivery"></a>E-mail sablonok konfigurálása adott kézbesítési módokhoz

Ebben az eljárásban a feltételezés az, hogy már létrehozta az új, egyéni e-mail sablonokat, és hozzáadta őket a **Szervezet e-mail sablonok** laphoz. Az e-mail-sablonok létrehozásáról és feltöltéséről a [E-mail-sablonok létrehozása tranzakciós eseményekhez](email-templates-transactions.md).

Ha a Commerce központban bizonyos kézbesítési módokhoz szeretne e-mail sablonokat beállítani, kövesse az alábbi lépéseket.

1. Nyissa meg a **Commerce e-mail értesítési profilját**.
1. A **Kiskereskedelmi esemény értesítési beállításai** részben válasszon ki egy meglévő értesítéstípust.
1. Amíg az értesítés típusa még mindig ki van jelölve, válassza a **Szállítási módok konfigurálása** lehetőséget.
1. A **Szállítási módok** párbeszédablakban válassza az **Új** elemet.
1. Az új sorban a **Szállítás módja** mezőben válassza ki a szállítási módot.
1. Az **E-mail-azonosító** mezőben válassza ki azt az e-mail sablont, amelyet a kézbesítés módhoz szeretne leképezni.
1. Jelölje be az **Aktív** jelölőnégyzetet.
1. Ismételje meg a 4-7. lépéseket a többi kézbesítési módok hozzáadásához.
1. Amikor elkészült, válassza az **OK** elemet.

> [!NOTE]
> - Ha egy értékesítési rendelés sorai között egynél több szállítási mód van jelen, a program az alapértelmezett sablont fogja használni. Az alapértelmezett sablon az a sablon, amely le van képezve az értesítési típushoz a **Commerce e-mail értesítési profil** oldalán.
> - Ha egy értékesítési rendelés kézbesítési módja nincs beállítva egyéni e-mail sablonhoz, a rendszer az alapértelmezett e-mail sablont fogja használni.

## <a name="additional-resources"></a>További erőforrások

[Hívásközponti rendelések létrehozása](tasks/create-call-center-orders.md)

[Szállítási mód módosítása a pénztárban](pos-change-delivery-mode.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
