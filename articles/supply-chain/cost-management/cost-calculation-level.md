---
title: Költségszámítási szint
description: Ez a témakör az anyagjegyzék (BOM) szintet írja le, amelynek neve Költségszámítás szint. Ez az Anyagjegyzék szint kizárja a termelési és a kötegelt rendeléseket a számításokból.
author: AndersGirke
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: e08d11c8e9d98e56c5ef076cbab7bb68bedea62a
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7581032"
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