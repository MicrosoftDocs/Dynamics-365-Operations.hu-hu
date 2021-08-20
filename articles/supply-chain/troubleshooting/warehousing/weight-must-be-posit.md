---
title: A súly csak pozitív érték lehet.
description: A súly csak pozitív érték lehet.
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSContainerCloseDiag_canClose
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 27ec37e0c0644ff10ece4626d5c136bca3c52ef12f1c6de947afd03003a5368a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776776"
---
# <a name="weight-must-be-positive"></a>A súly csak pozitív érték lehet.

Hibakód: WeightMustBePositive

## <a name="symptoms"></a>Tünetek

A rendszer a következő hibaüzenetet jeleníti meg:

> A súly csak pozitív érték lehet.

## <a name="cause"></a>Ok

A **Bruttó tömeg** mező értéke *0* (nulla) vagy negatív érték.

## <a name="resolution"></a>Felbontás

Súly meghatározásához hajtsa végre az alábbi lépések valamelyikét.

- A **Bruttó tömeg** mezőben állítsa be az értéket. Válasszon egy egységet a legördülő listából.
- Válassza a **rendszertömeg beolvasása** lehetőséget a **Bruttó tömeg** értékének kiszámításához.
