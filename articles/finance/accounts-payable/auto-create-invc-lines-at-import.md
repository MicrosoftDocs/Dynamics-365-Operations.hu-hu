---
title: Számlasorok létrehozása szállítói számlák importálásakor
description: Ez a témakör azt a funkciót ismerteti, hogyan lehet automatikusan számlasorokat generálni a szállítói számlákon a számlák importálásakor.
author: sunfzam
ms.date: 09/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: e745ab1fb39edf69fabd147e46e1da8cc98ba6e5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903507"
---
# <a name="generate-invoice-lines-when-you-import-vendor-invoices"></a>Számlasorok létrehozása szállítói számlák importálásakor

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör azt a funkciót ismerteti, hogyan lehet automatikusan számlasorokat generálni a szállítói számlákon a számlák importálásakor.

Bizonyos esetekben a szállítói számlák csak korlátozott információkat tartalmaznak, például a címzett adatait és a részösszegeket. Nem tartalmaznak azonban információkat a sorcikkekről. Számlák importálása esetén a számlasorok automatikusan létrejönnek a megfelelő beszerzési rendelés adatai alapján.

A következő lépések szerint engedélyezheti a számlasorok automatikus létrehozását.

1.  Ugorjon a **Kötelezettségek \> Beállítás \> Kötelezettségek paraméterei pontra**.
2.  A **Szállítói számla automatizálása** lapon, az **Automatikus sor létrehozása az importált számlákhoz** területen állítsa a **Számlasorok automatikus létrehozása** beállítást **Igen** beállításra. 
4.  Az Automatikus számlasor-létrehozási **mennyiség** kiválasztása mezőben válassza ki azt a mennyiséget, amely automatikusan létrehozza a számlasorokat:

    - **Megrendelt** mennyiség – a sorok a beszerzési rendelés soraiból jönnek létre. Ez az érték az alapértelmezett érték.
    - **Termékbevételezési mennyiség** – a beszerzési rendelés száma alapján lehet megtalálni a megfelelő termékbevételezéseket. Ezt követően a termékbevételezési mennyiségek alapján hozza létre a számlasorokat.

## <a name="data-entity-changes"></a>Adatentitás-módosítások

Az ebben a cikkben ismertetett funkciók támogatása érdekében **a szállítói** számla fejlécadat-entitása továbbfejlesztett módon fel lett bővítve. Három mező lett hozzáadva:

- **HeaderOnlyImport** – a számlafejlécek sorait csak Igen **beállítású** mezőben állíthatja elő.
- **PurchIdRange** – A beszerzési rendelési számok listája. A számlaszámok lehetnek tartomány, például **INV0001..INV0009** (ahol két pont választja el a tartomány kezdő és záró értékét), vagy különálló értékek, például **INV0001, INV0003, INV0006**. Minden beszerzési rendelésnek ugyan ahhoz a szállítói számlához kell tartozni a számlafejlécben. Ellenkező esetben a következő hibaüzenet jelenik meg: "Nem sikerült számlasorokat generálni. A beszerzési rendelésekhez eltérő szállítói számlák tartoznak."
- **PackingslipRange** – A termékbevételezési számok listája. Szállítói számlasorokat termékbevételezésből lehet létrehozni. A termékbevételezési számok azonban általában nem szerepelnek a szállítói számlákon. Ebbe a mezőbe csak akkor írja be a termékbevételezési számokat, ha egyértelműen meg tudja határozni, hogy mely termékbevételezések mely meghatározott számlákhoz tartoznak. A Számlasorokat termékbevételezésből lehetséges létrehozni. Ha ezt a mezőt használja, **·** **a rendszer figyelmen kívül hagyja az Automatikus számlasor-létrehozási mennyiség kiválasztása mező beállítását a Kötelezettségek** paraméterei lapon. 

**Korlátozás**: ha több termékbevételezési számot ad meg, több függő szállítói számla jön létre ugyanazzal a számlaszámmal. Ezeket manuálisan kell konszolidálni, mielőtt tovább feldolgozható lenne a számla. A későbbi verziókban úgy tervezjük, hogy a számlákat automatikusan összevonja, így a korlátozás el lesz távolítva.

Minden termékbevételezésnek ugyanahhoz a szállítói számlához kell tartozni a számlafejlécben.

## <a name="result"></a>Eredmény

Ha sikeresen megtörtént a sorok létrehozása, a rendszer a következő üzenetet naplózza a szállítói számla automatizálási előzményei között: "Számlasorok automatikus létrehozása: sikeres".

Ha nem generálnak sorokat, a rendszer a következő hibaüzenetet naplózza: "Számlasorok automatikus létrehozása: Sikertelen".
