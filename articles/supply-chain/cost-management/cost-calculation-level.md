---
title: Költségszámítási szint
description: Ez a témakör az anyagjegyzék (BOM) szintet írja le, amelynek neve Költségszámítás szint. Ez az Anyagjegyzék szint kizárja a termelési és a kötegelt rendeléseket a számításokból.
author: AndersGirke
manager: tfehr
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 42088d8c005cf3fc04e768f1b8e8c8ca0b8c6993
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967729"
---
# <a name="cost-calculation-level"></a>Költségszámítási szint

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
