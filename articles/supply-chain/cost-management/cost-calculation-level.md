---
title: Költségszámítási szint
description: Ez a cikk a Költségszámítási szint nevű anyagjegyzékszintet ismerteti. Ez az Anyagjegyzék szint kizárja a termelési és a kötegelt rendeléseket a számításokból.
author: JennySong-SH
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 647ef4b13b864cfdbb7905fe7a0d340e85f6c1e6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850873"
---
# <a name="cost-calculation-level"></a>Költségszámítási szint

[!include [banner](../includes/banner.md)]

A **Költségszámítási szint** nevű anyagjegyzék (BOM) szint kizárja a termelési rendeléseket és a kötegelt rendeléseket a számításaiból. Ez a szint akkor használatos, amikor költségszámítási verziókban a rendszer költség-számításokat futtat. Olyan folyamatok, mint, például az újraszámítás és a készlet zárása során a rendszer a **Költségszint** anyagjegyzék szintet használja ehelyett.

A következő egyszerű forgatókönyv a **Költségszámítási szint** anyagjegyzék-szint és a **Költségtervezés szint** anyagjegyzék-szint közötti különbségeket tartalmazza.

Három termék van: A, B és C. a C termék a B termék összetevője, a B termék pedig az A termék összetevője.

- **A költségtervezési szint** a következő anyagjegyzék-szinteket rendeli hozzá:

    - **A termék:** 0
    - **B termék:** 1
    - **C termék:** 2

- **A költségszámítási szint** a következő anyagjegyzék-szinteket rendeli hozzá:

    - **A termék:** 0
    - **B termék:** 1
    - **C termék:** 2

Ezután létrejön egy termelési rendelés a C termékhez, és az A termék hozzáadódik a termelési rendelés anyagjegyzékéhez. A rendelés becslése után a program az anyagjegyzék-szinteket a következő módon frissíti:

- **A költségtervezési szint** a következő anyagjegyzék-szinteket rendeli hozzá:

    - **B termék:** 1
    - **C termék:** 2
    - **A termék:** 3

- **A költségszámítási szint** a következő anyagjegyzék-szinteket rendeli hozzá:

    - **A termék:** 0
    - **B termék:** 1
    - **C termék:** 2

Ez a viselkedés biztosítja, hogy a termelési rendelési anyagjegyzékeinek módosításai ne befolyásolják a későbbi költségszámításokat.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]