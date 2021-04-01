---
title: Vevői hitelcsoportok
description: Ez a témakör a vevői hitelcsoportokkal kapcsolatban tartalmaz információkat.
author: mikefalkner
manager: AnnBe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76b1e93d562e66cb8d4c5819a749459ea8783b1e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237542"
---
# <a name="customer-credit-groups"></a>Vevői hitelcsoportok

[!include [banner](../includes/banner.md)]

Meghatározhatja a vevők olyan csoportjait, akiknek megosztott hitelkerete van. A program a vevői számlafiókjában megadott egyéni hitelkeretet is figyelembe veszi.

A vevői hitelcsoport tagjait különböző jogi személyek közül lehet kiválasztani. Amikor egy vevőt ad hozzá a vevők listájához a vevői hitelcsoportban, akkor az egyes vevők hitelkeretének lejárati dátuma a csoporthoz rendelt lejárati dátumra módosul.

Beállíthat vevői hitelcsoportokat a **Vevői hitelcsoportok** oldalon (**Hitelkezelés \> Vevői hitelcsoportok \> Vevői hitelcsoportok**).

1. A **Csoport száma** és **Leírás** mezőkben adja meg a csoport azonosítóját és leírását.
2. A **Hitelkeret** és a **Pénznem** mezőkben adja meg azt a hitelkeretet és pénznemet, amelyet akkor kell használni, amikor a rendszer a csoport bármely tagja számára ellenőrzi a hitelkeretet.
3. A **Hitelkeret dátuma** mezőbe írja be a dátumot, amikor a hitelkeret lejár. A vevői hitelcsoportoknak lejárati dátummal kell rendelkezniük.

Miután befejezte a vevői hitelcsoport beállítását, vevőket adhat hozzá azok jogi személyének és vevői számlaazonosítójának meghatározásával. Amikor új vevőt ad hozzá egy vevői hitelcsoporthoz, a rendszer az összes jogi személy között ugyanarra a vevői számlára keres, és a felkéri, hogy adja hozzá a vevői hitelcsoporthoz.

A **Korosított egyenlegek** menü használatával megtekintheti a vevői hitelcsoportban szereplő összes számlaügyfél korosítási egyenlegének adatait. A **Korosítási egyenleg** lap a korosított egyenlegek összegzését jeleníti meg a számlaügyfél-fiókokhoz.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]