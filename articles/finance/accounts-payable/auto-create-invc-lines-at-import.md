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
ms.reviewer: roschlom
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 87dec3c142ae296975ab98432421be4548085c80
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647891"
---
# <a name="generate-invoice-lines-when-you-import-vendor-invoices"></a>Számlasorok létrehozása szállítói számlák importálásakor

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör azt a funkciót ismerteti, hogyan lehet automatikusan számlasorokat generálni a szállítói számlákon a számlák importálásakor.

Bizonyos esetekben a szállítói számlák csak korlátozott információkat tartalmaznak, például a címzett adatait és a részösszegeket. Nem tartalmaznak azonban információkat a sorcikkekről. Számlák importálása esetén a rendszer automatikusan létrehozhat számlasorokat a megfelelő beszerzési rendelés adatai alapján.

A következő lépések szerint engedélyezheti a számlasorok automatikus létrehozását.

1.  Ugorjon a **Kötelezettségek \> Beállítás \> Kötelezettségek paraméterei pontra**.
2.  A **Szállítói számla automatizálása** lapon, az **Automatikus sor létrehozása az importált számlákhoz** területen állítsa a **Számlasorok automatikus létrehozása** beállítást **Igen** beállításra. 
4.  Az **Alapértelmezett mennyiség kiválasztása automatikus számlasorok létrehozásához** mezőben válassza ki azt a mennyiséget, amely alapján a rendszer automatikusan létrehozza a számlasorokat:

    - **Megrendelt mennyiség** – a rendszer sorokat hoz létre a beszerzési rendelés soraiból. Ez az érték az alapértelmezett érték.
    - **Termékbevételezési mennyiség** – A rendszer a beszerzési rendelési számok alapján fogja megtalálni a megfelelő termékbevételezéseket. Ezt követően a termékbevételezési mennyiségek alapján hozza létre a számlasorokat.

## <a name="data-entity-changes"></a>Adatentitás-módosítások

Az ebben a témakörben ismertetett funkciók támogatása érdekében a **Szállítói számla fejléce** adatentitás bővítve lett. Három mező lett hozzáadva:

- **HeaderOnlyImport** – ahhoz, hogy a rendszer létrehozza a számlafejlécek sorait, **Igen** beállításúnak kell lennie ennek a mezőnek.
- **PurchIdRange** – A beszerzési rendelési számok listája. A számlaszámok lehetnek tartomány, például **INV0001..INV0009** (ahol két pont választja el a tartomány kezdő és záró értékét), vagy különálló értékek, például **INV0001, INV0003, INV0006**. Minden beszerzési rendelésnek ugyan ahhoz a szállítói számlához kell tartozni a számlafejlécben. Ellenkező esetben a következő hibaüzenet jelenik meg: "Nem sikerült számlasorokat generálni. A beszerzési rendelésekhez eltérő szállítói számlák tartoznak."
- **PackingslipRange** – A termékbevételezési számok listája. Szállítói számlasorokat termékbevételezésből lehet létrehozni. A termékbevételezési számok azonban általában nem szerepelnek a szállítói számlákon. Ebbe a mezőbe csak akkor írja be a termékbevételezési számokat, ha egyértelműen meg tudja határozni, hogy mely termékbevételezések mely meghatározott számlákhoz tartoznak. A Számlasorokat termékbevételezésből lehetséges létrehozni. Ha ezt a mezőt használja, a rendszer figyelmen kívül hagyja a **Kötelezettségek paraméterei lapon** található **Alapértelmezett mennyiség kiválasztása automatikus számlasorok létrehozásához** mező beállítását. 

**Korlátozás**: ha több termékbevételezési számot ad meg, több függő szállítói számla jön létre ugyanazzal a számlaszámmal. Ezeket manuálisan kell konszolidálni, mielőtt tovább feldolgozható lenne a számla. A későbbi verziókban azt tervezzük, hogy lehetővé tesszük a rendszer számára a számlák automatikus konszolidálását, így a korlátozás el lesz távolítva.

Minden termékbevételezésnek ugyanahhoz a szállítói számlához kell tartozni a számlafejlécben.

## <a name="result"></a>Eredmény

Ha a rendszer sikeresen generál sorokat, a rendszer a következő üzenetet naplózza a szállítói számla automatizálási előzményei között: "Számlasorok automatikus létrehozása: sikeres".

Ha a rendszer nem tud sorokat generálni, a rendszer a következő hibaüzenetet naplózza: "Számlasorok automatikus létrehozása: Sikertelen".
