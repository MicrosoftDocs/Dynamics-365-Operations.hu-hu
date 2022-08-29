---
title: Költségszámítási szint
description: Ez a cikk a Költségszámítási szint nevű anyagjegyzékszintet ismerteti. Ez az Anyagjegyzék szint kizárja a termelési és a kötegelt rendeléseket a számításokból.
author: JennySong-SH
ms.date: 08/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: e63a868696e36c1d4f5d19ea87bdf4d682c39f8c
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334955"
---
# <a name="cost-calculation-level"></a>Költségszámítási szint

[!include [banner](../includes/banner.md)]

A **Költségszámítási szint** nevű anyagjegyzék (BOM) szint kizárja a termelési rendeléseket és a kötegelt rendeléseket a számításaiból. Ez a szint akkor használatos, amikor költségszámítási verziókban a rendszer költség-számításokat futtat. Olyan folyamatok, mint, például az újraszámítás és a készlet zárása során a rendszer a **Költségszint** anyagjegyzék szintet használja ehelyett.

## <a name="turn-the-cost-calculation-level-feature-on-or-off"></a>A Költségszámítási szint szolgáltatás be- és kikapcsolása

A funkció használatához be kell kapcsolva lennie a rendszeren. Az Ellátásilánc-kezelés 10.0.29-es verziója szerint a funkció alapértelmezés szerint be van kapcsolva. A rendszergazdák a *Funkciókezelés*[munkaterület Költségszámítási szint szolgáltatását keresve kapcsolhatják be és kapcsolják ki ezt a](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) funkciót.

## <a name="example-scenario"></a>Példaforgatókönyv

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