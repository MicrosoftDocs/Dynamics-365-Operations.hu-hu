---
title: Vállalatközi paraméterek
description: Ez a témakör a vállalatközi paramétereket mutatja be
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 705efee84b255105ba39c603d23d2509e77b331a
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548310"
---
# <a name="intercompany-parameters"></a>Vállalatközi paraméterek

[!include [banner](../../includes/banner.md)]

Vállalatközi szervezeteknél meg lehet adni azokat a paramétereket, amelyek megszabják a különböző jogi személyek közötti kereskedelem módját. Ezeket a paramétereket a kiválasztott mezők határozzák meg. Különféle kombinációk kiválasztásával tükrözheti a különböző kereskedelmi helyzeteket.

A következő példák egyikében egy kétszintű, a másikban pedig egy háromszintű vállalatközi szervezet szerepel.

## <a name="example-1-two-level-intercompany-chain"></a>1. példa: kétszintű vállalatközi lánc

A vállalatközi szervezet a következő jogi személyeket tartalmazza:

- A jogi személy – külső vevőknek ad el, de nincs részvénye. Ez a jogi személy a B jogi személytől vásárol.
- B jogi személy – csak az A jogi személynek ad el.

Mindkét jogi személy vásárolhat és eladhat egymásnak.

Ebben a példában az eredeti értékesítési rendelés külső vevővel szemben alkalmazott árképzése mindig az eladási áron alapul. A vállalatközi értékesítési rendelések és vállalatközi beszerzési rendelések esetén azonban az árképzés B jogi személy vállalatközi értékesítési rendelésén szereplő belső vevői/átmozgatási árképzésen alapul.

A rendelési fejlécben szereplő adatok az eredeti értékesítési rendelésről kerülnek a külső vevőhöz. A vállalatközi értékesítési rendelésen végrehajtott módosítások nem lesznek szinkronizálva az eredeti értékesítési rendelésen.

Az A jogi személy szállítókkal kapcsolatos **Vállalatközi** lapján válassza ki a **Beszerzési rendelés irányelvek** lehetőséget. Válassza a következő mezőket az **Eredeti értékesítési rendelés (közvetlen kiszállítás)** mezőcsoportban:

- **Szállítólevél automatikus nyomtatása**
- **Számla automatikus feladása**
- **Számla automatikus nyomtatása**

Válassza a következő mezőket a **Vállalatközi értékesítési rendelés (közvetlen kiszállítás)** mezőcsoportban:

- **Számla automatikus feladása**

Válassza a következő mezőket az **Eredeti értékesítési rendelés <-> Vállalatközi értékesítési rendelés** csoportban:

- **Vevő adatai**
- **RMA-szám**

Válassza a következő mezőket a **Vállalatközi értékesítési rendelés <-> Vállalatközi értékesítési rendelés** mezőcsoportban:

- **Vevő adatai**
- **RMA-szám**
- **Köteg száma**
- **Sorozatszám**

A B jogi személy vevőkkel kapcsolatos **Vállalatközi** lapján válassza ki az **Értékesítési rendelés irányelvek** lehetőséget. Válassza a következő mezőket a **Vállalatközi értékesítési rendelés létrehozása** mezőcsoportban:

- **Értékesítési rendelés számozása**: **Vállalat + eredeti szám**
- **Eredeti vevőhöz tartozó dokumentumok összesítő frissítésének engedélyezése**

Válassza a következő mezőket a **Vállalatközi értékesítési rendelés árai** mezőcsoportban:

- **Ár és engedmény keresése**
- **Ár szerkesztésének engedélyezése**
- **Engedmény szerkesztésének engedélyezése**

Válassza a következő mezőket a **Vállalatközi értékesítési rendelés \> Vállalatközi beszerzési rendelés** mezőcsoportban:

- **Köteg száma**
- **Sorozatszám**

## <a name="example-2-three-level-intercompany-chain"></a>2. példa: Háromszintű vállalatközi lánc

A vállalatközi szervezet a következő jogi személyeket tartalmazza:

- A jogi személy – Olyan értékesítő jogi személy, amely külső vevőknek ad el, és a B jogi személytől vásárol.
- B jogi személy – Olyan termelési vagy terjesztési jogi személy, amely nem tud termékeket szállítani, és C jogi személytől vásárol.
- C jogi személy – Olyan termelési vagy terjesztési jogi személy, amely termékeket szállít a B jogi személynek.

A B és C jogi személyek között a belső transzfer-árképzése a lánc elejének megfelelő értékesítő jogi személy költségére van megállapítva. Az A jogi személynél is költségszintű, amely külső vevőknek ad el. Az eredeti értékesítési rendelés árképzése a külső vevőnek azonban mindig az eladási áron alapul.

Minden vállalatközi értékesítési rendelés és vállalatközi beszerzési rendelés esetén a vállalatközi értékesítési rendelés szabályozza az árképzést. A lánc elején történik a szabályzás. Emiatt a B jogi személy számára értékesítő C jogi személy szabályozza az árat. A vállalatközi értékesítési rendelés árképzése a C belső értékesítő vállalatnál beállított eladási vagy transzferáron alapul.

A rendelési fejlécben szereplő adatok az eredeti értékesítési rendelésről kerülnek a külső vevőhöz. A vállalatközi rendeléseken végrehajtott módosítások nem lesznek szinkronizálva az eredeti értékesítési rendelésen.

Az alábbi paramétereket ajánlott megadni:

Az A jogi személy szállítókkal kapcsolatos **Vállalatközi** lapján válassza ki a **Beszerzési rendelés irányelvek** lehetőséget. Válassza a következő mezőket az **Eredeti értékesítési rendelés (közvetlen kiszállítás)** mezőcsoportban:

- **Szállítólevél automatikus nyomtatása**
- **Számla automatikus feladása**
- **Számla automatikus nyomtatása**

Válassza a következő mezőket a **Vállalatközi értékesítési rendelés (közvetlen kiszállítás)** mezőcsoportban:

- **Számla automatikus feladása**

Válassza a következő mezőket az **Eredeti értékesítési rendelés <-> Vállalatközi értékesítési rendelés** mezőcsoportban:

- **Vevő adatai**
- **RMA-szám**

Válassza a következő mezőket a **Vállalatközi értékesítési rendelés <-> Vállalatközi értékesítési rendelés** mezőcsoportban:

- **Vevő adatai**
- **RMA-szám**
- **Köteg száma**
- **Sorozatszám**

A B jogi személy vevőkkel kapcsolatos **Vállalatközi** lapján válassza ki az **Értékesítési rendelés irányelvek** lehetőséget. Válassza a következő mezőket a **Vállalatközi értékesítési rendelés létrehozása** mezőcsoportban:

- **Értékesítési rendelés számozása**: **Vállalat + eredeti szám**
- **Eredeti vevőhöz tartozó dokumentumok összesítő frissítésének engedélyezése**

Válassza a következő mezőket a **Vállalatközi értékesítési rendelés \> Vállalatközi beszerzési rendelés** mezőcsoportban:

- **Köteg száma**
- **Sorozatszám**

Válassza a következő mezőket a **Vállalatközi ügyfélszámla-feladás** mezőcsoportban:

- **Az egységár egyenlő az önköltségi árral**
- **Eredeti vevői számla feladásának kezdeményezése**

A B jogi személy szállítókkal kapcsolatos **Vállalatközi** lapján válassza ki a **Beszerzési rendelés irányelvek** lehetőséget. Válassza a következő mezőket az **Eredeti értékesítési rendelés (közvetlen kiszállítás)** mezőcsoportban:

- **Szállítólevél automatikus nyomtatása**
- **Számla automatikus feladása**
- **Számla automatikus nyomtatása**

Válassza a következő mezőket a **Vállalatközi értékesítési rendelés (közvetlen kiszállítás)** mezőcsoportban:

- **Számla automatikus feladása**

Válassza a következő mezőket az **Eredeti értékesítési rendelés <-> Vállalatközi értékesítési rendelés** mezőcsoportban:

- **Vevő adatai**
- **RMA-szám**
- **Ár és engedmény**

Válassza a következő mezőket a **Vállalatközi értékesítési rendelés <-> Vállalatközi értékesítési rendelés** mezőcsoportban:

- **Vevő adatai**
- **RMA-szám**
- **Köteg száma**
- **Sorozatszám**

A C jogi személy vevőkkel kapcsolatos **Vállalatközi** lapján válassza ki az **Értékesítési rendelés irányelvek** lehetőséget. Válassza a következő mezőket a **Vállalatközi értékesítési rendelés létrehozása** mezőcsoportban:

- **Értékesítési rendelés számozása**: **Számsorozat kódja**
- **Eredeti vevőhöz tartozó dokumentumok összesítő frissítésének engedélyezése**

Válassza a következő mezőt a **Vállalatközi értékesítési rendelés árai** mezőcsoportban:

- **Ár és engedmény keresése**

Válassza a következő mezőket a **Vállalatközi ügyfélszámla-feladás** mezőcsoportban:

- **Az egységár egyenlő az önköltségi árral**
- **Eredeti vevői számla feladásának kezdeményezése**

Válassza a következő mezőket a **Vállalatközi értékesítési rendelés <-> Vállalatközi beszerzési rendelés** mezőcsoportban:

- **Köteg száma**
- **Sorozatszám**

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
