---
title: Halasztott áfa számítása
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a halasztott áfaszámításokat és a magyarországi áfafeladáshoz.
author: v-lurodi
manager: AnnBe
ms.date: 09/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 264684
ms.search.region: Hungary
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 467536f87fd4318ea82849ef6df62d4141fc22fa
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408037"
---
# <a name="deferred-sales-tax-calculations"></a>Halasztott áfa számítása

[!include [banner](../includes/banner.md)]

Magyarországon az általános forgalmi adót (áfa) folyamatos szolgáltatásteljesítés, például bérlés, lízingelés, konzultáció és fűtés során az esedékesség napján kell rögzíteni és jelenteni. Ez a funkció lehetővé teszi az áfa összegének főkönyvi feladásának a halasztott fizetendő áfa és halasztott bejövő áfa számlákra. A számla esedékességi dátumán is átviheti az összegeket a hagyományos forgalmiadó-számlákra.

A halasztott adófeladások a következő dokumentumtípusok és naplók esetén működnek:

- Értékesítési rendelés
- Szabadszöveges számlák
- Beszerzési rendelések
- Számlanaplók
- Számlaregiszterek
- Számla-jóváhagyási naplók

Ha ez a funkció be van állítva, akkor a tranzakció feladása alkalmával létrejönnek a következő áfatranzakciók:

- Az áfa összege a feladás napján feladásra kerül a halasztott adó számlára.
- Az áfa összege az áfatételjegyzék napján visszaforgatásra kerül a halasztott adó számláról.
- Az áfa összege az áfatételjegyzék napján feladásra kerül az alapértelmezett fizetendő áfa vagy levonható áfa számlára.

Szabad szöveges számlák és beszerzési rendelések esetén, ha a dokumentumsorok összegeit elosztják a pénzügyi dimenziók között, az ÁFA összegeket, csakúgy, mint a dokumentumsorok összegeit szintén el kell osztani.

## <a name="set-up-deferred-vat-posting"></a>Halasztott áfafeladás beállítása 

Megadhatja, hogy az áfa feladása halasztott áfaszámlára történjen.

1. Ugorjon az **Adó** \> **Közvetett adók** \> **Áfa** \> **Áfacsoportok** pontra.
2. A  **Cikkáfacsoport** lapon jelölje be a **Halasztott ÁFA** jelölőnégyzetet, ha meg szeretné adni, hogy az áfa feladása halasztott áfa számlára történjen.

## <a name="set-up-ledger-accounts-for-deferred-vat-posting"></a>Főkönyvi számlák beállítása áfafeladáshoz

A halasztott áfa feladása a főkönyvi számlákra vonatkozóan is megadható.

1. Ugrás az **Adó \> Beállítás \> Áfa > \> Főkönyvi feladási csoportok** elemre.
2. A **Főkönyvi feladási csoportok** lapon válasszon ki egy főkönyvi feladási csoportot a listáról, és adja hozzá a következő adatokat.

- **Halasztott áfa fizetendő** – Válassza ki a kijelölt főkönyvi feladási csoport halasztott áfaszámláját vagy adószámláját.
- **Halasztott áfa visszaigényelhető** – Válassza ki a kijelölt főkönyvi feladási csoport halasztott áfaszámláját vagy adószámláját.
