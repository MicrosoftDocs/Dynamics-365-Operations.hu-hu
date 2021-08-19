---
title: Nemzetközi bankszámlaszám (IBAN) számlák ellenőrzésének kezelése
description: Ez a témakör bemutatja a Nemzetközi bankszámlaszám (IBAN) számlák ellenőrzésének kezelését
author: mikefalkner
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: f7f6bcb9085630966310efb5af2e7def23d919d6653376b8f6637a6da915a8d5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6757145"
---
# <a name="manage-international-bank-account-number-iban-account-validation"></a>Nemzetközi bankszámlaszám (IBAN) számlák ellenőrzésének kezelése

[!include [banner](../includes/banner.md)]

A Nemzetközi bankszámlaszám (IBAN) ellenőrzése növeli az ellenőrzések mennyiségét, amikor IBAN-t ad hozzá egy bankszámlához.

Az IBAN szám felépítéséről szóló adatok a Microsoft Dynamics 365 Finance programban kerülnek tárolásra. Az IBAN szám első használatakor bankszámlákkal az adatokat automatikusan betöltődnek. Az IBAN-szám hosszát, a bankszámlaszám és a bank regisztrációs azonosítójának kezdő pozícióit, és a bankszámlaszám és a bank regisztrációs azonosítójának hosszát tartalmazza.

## <a name="set-up-iban-structures"></a>IBAN-szerkezetek beállítása

1. Nyissa meg a következőt: **Készpénz- és bankkezelés \> Beállítás \> IBAN-struktúrák**.
2. Láthatja, hogy minden egyes ország vagy régió IBAN-struktúrája automatikusan be van állítva.
3. Ha testre akarja szabni egy adott ország vagy régió struktúráit, szerkesztheti azokat.
4. A struktúradefiníciók az egyes új kiadások részei lesznek. Használhatja a **Struktúrák alaphelyzetbe állítása** menüt, hogy az egyes frissítések után betöltse a legfrissebb definíciókat.

## <a name="validate-the-iban-structure-in-a-bank-account"></a>A bankszámla IBAN-struktúrájának ellenőrzése

1. Menjen a **Készpénz és bankkezelés \> Bankszámlák \> Bankszámlák menüpontra**.
2. Hozzon létre bankszámlát
3. A **További információk** gyorslapon adjon meg egy IBAN-t.

    Ha az IBAN-szám hossza nem egyezik meg minden egyes ország vagy terület meghatározott hosszával, egy figyelmeztető üzenetet kap. Nem folytathatja, ha az IBAN-szám hossza nem egyezik meg az IBAN-struktúrában megadottal.

    Az ellenőrzés azt is ellenőrzi, hogy a bankszámla száma megegyezik-e az IBAN szám a bankszámlaszámot jelölő részével. Ha a bankszámlaszám nem egyezik meg, egy figyelmeztető üzenetet kap. Ez az üzenet csak egy figyelmeztetés. Folytathatja, még akkor is, ha a bankszámlaszám nem egyezik meg.

    Az ellenőrzés azt is ellenőrzi, hogy a bank regisztrációs azonosítója megegyezik-e az IBAN-szám a bank regisztrációs azonosítóját jelölő részével. A bank regisztrációs azonosítója tartalmazza a banki számot, és gyakran egy további bankfiókot is. Ha a bank regisztrációs azonosítója nem egyezik meg, egy figyelmeztető üzenetet kap. Ez az üzenet csak egy figyelmeztetés. Folytathatja, még akkor is, ha a bank regisztrációs azonosítója nem egyezik meg.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]