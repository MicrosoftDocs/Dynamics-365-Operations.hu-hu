---
title: Ennél a helynél meg kell adni az azonosítótáblát.
description: Ha ezt a hibaüzenetet látja egy WMS-kompatibilis raktárhoz való átmozgatási rendelés létrehozása után, akkor az Alapértelmezett bevételezési hely üres az egyik tranzitraktárnál.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 2e562ad2b41dd149f215adc83bd2d54e55dccc05
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476519"
---
# <a name="license-plate-specification-error-when-confirming-shipment-for-a-transfer-order"></a>Azonosítótábla meghatározási hiba átrendelési rendelés szállításának megerősítésekor

## <a name="symptoms"></a>Tünetek

Ha átmozgatási rendelést hoz létre olyan raktárral, amely engedélyezve van a speciális raktárkezelésnél (WMS), majd a munka befejezése után megpróbálja megerősíteni a szállítmányt, a következő hibaüzenet jelenhet meg:

> Ennél a helynél meg kell adni az azonosítótáblát.

## <a name="cause"></a>Ok

Ennek oka, hogy az **Alapértelmezett bevételezési hely** mező üres a raktár tranzitraktár „érkezési” raktárában.

## <a name="resolution"></a>Megoldás

A probléma megoldásához adjon meg egy alapértelmezett bevételezési helyet a tranzitraktárban. Győződjön meg arról, hogy ez a hely azonosítótábla-vezérelt.
