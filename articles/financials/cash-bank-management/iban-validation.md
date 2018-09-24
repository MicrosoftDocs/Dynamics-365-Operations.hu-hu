---
title: "Nemzetközi bankszámlaszám (IBAN) számlák ellenőrzésének kezelése"
description: "Ez a témakör bemutatja a Nemzetközi bankszámlaszám (IBAN) számlák ellenőrzésének kezelését"
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: e091aab70a98e0f4b96c41c1ee48926947539105
ms.contentlocale: hu-hu
ms.lasthandoff: 08/31/2018

---

# <a name="manage-international-bank-account-number-iban-account-validation"></a>Nemzetközi bankszámlaszám (IBAN) számlák ellenőrzésének kezelése

[!include [banner](../includes/banner.md)]

A Nemzetközi bankszámlaszám (IBAN) számla ellenőrzése növeli az ellenőrzések mennyiségét, amikor IBAN-t ad hozzá egy bankszámlához.

Az IBAN szám szerkezete tárolva van a Microsoft Dynamics 365 for Finance and Operations alkalmazásban, és az IBAN szám első használatakor a bankszámlák esetén automatikusan betöltődik. A bankszámlaszám az IBAN-számhoz definiált szerkezet része. A szerkezet alapján ha számlaszám helye és hossza az IBAN számban nem egyezik meg az egyes országokhoz vagy területekhez meghatározott szerkezetnek, figyelmeztető üzenet fog kapni.

## <a name="set-up-iban-structures"></a>IBAN-szerkezetek beállítása

1. Nyissa meg a következőt: **Készpénz- és bankkezelés \> Beállítás \> IBAN-struktúrák**.
2. Láthatja, hogy minden egyes ország vagy régió IBAN-struktúrája automatikusan be van állítva.
3. Ha testre szabja egy adott ország vagy régió struktúráit, szerkesztheti azokat.
4. A struktúradefiníciók az egyes új kiadások részei lesznek. Használhatja a **Struktúrák alaphelyzetbe állítása** menüt, hogy az egyes frissítések után betöltse a legfrissebb definíciókat.

## <a name="validate-the-iban-structure-in-a-bank-account"></a>A bankszámla IBAN-struktúrájának ellenőrzése

1. Menjen a **Készpénz és bankkezelés \> Bankszámlák \> Bankszámlák menüpontra**.
2. Hozzon létre bankszámlát
3. A **További információk** gyorslapon adjon meg egy IBAN-t.

    Ha számlaszám helye és hossza az IBAN számban nem egyezik meg az egyes országokhoz vagy területekhez meghatározott szerkezetnek, egy üzenetet fog kapni. Nem folytathatja, ha az IBAN-szám hossza nem egyezik meg az IBAN-struktúrában megadottal.

    Az ellenőrzés azt is ellenőrzi, hogy a bankszámla száma megegyezik-e az IBAN szám a bankszámlaszámot jelölő részével. Ha a bankszámlaszám nem egyezik meg, egy figyelmeztető üzenetet kap. Ez az üzenet csak egy figyelmeztetés. Folytathatja, még akkor is, ha a bankszámlaszám nem egyezik meg.

