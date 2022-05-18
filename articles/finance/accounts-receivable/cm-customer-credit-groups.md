---
title: Vevői hitelcsoportok
description: Ez a témakör a vevői hitelcsoportokkal kapcsolatban tartalmaz információkat.
author: JodiChristiansen
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 0815aa41b034d8ba5c9b09f4003ff3df7311190a
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735492"
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
