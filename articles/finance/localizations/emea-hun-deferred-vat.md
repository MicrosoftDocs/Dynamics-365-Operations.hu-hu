---
title: Halasztott áfa számítása
description: Ez a témakör azt ismerteti, hogyan lehet beállítani halasztott áfaszámításokat és áfafeladásokat Magyarországra.
author: AdamTrukawka
ms.date: 09/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Hungary
ms.author: atrukawk
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 10.0.0
ms.custom: 264684
ms.search.form: AssetParameters
ms.openlocfilehash: 03a0b5b5c549c24dd81918db046d3cc9c01569f3
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337368"
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
2. A **Cikkáfacsoportok** oldalon jelölje be a **Halasztott áfa** jelölőnégyzetet, ha meg szeretné adni, hogy az áfa feladása halasztott áfaszámlára történjen.

## <a name="set-up-ledger-accounts-for-deferred-vat-posting"></a>Főkönyvi számlák beállítása áfafeladáshoz

A halasztott áfa feladása a főkönyvi számlákra vonatkozóan is megadható.

1. Lépjen az **Adó \> Beállítás \> Áfa \> Főkönyvi feladási csoportok** elemre.
2. A **Főkönyvi feladási csoportok** lapon válasszon ki egy főkönyvi feladási csoportot a listáról, és adja hozzá a következő adatokat.

- **Halasztott áfa fizetendő** – Válassza ki a kijelölt főkönyvi feladási csoport halasztott áfaszámláját vagy adószámláját.
- **Halasztott áfa visszaigényelhető** – Válassza ki a kijelölt főkönyvi feladási csoport halasztott áfaszámláját vagy adószámláját.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
