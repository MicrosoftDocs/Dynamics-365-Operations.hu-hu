---
title: Az alapterv paraméterei nem léteznek
description: Amikor rendelést próbál megerősíteni, olyan hibaüzenetet kap, amely szerint az alaptervhez nincsenek paraméterek.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d4b64af2e30109b8560d40c4c532504611528bbe
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294094"
---
# <a name="parameters-for-the-master-plan-dont-exist"></a>Az alapterv paraméterei nem léteznek

Hibakód: SYS25368

## <a name="symptoms"></a>Tünetek

Amikor tervezett rendelést próbál megerősíteni, a következő hibaüzenetet kapja:

> A(z) %1 alapterv paraméterei nem léteznek.

## <a name="cause"></a>Ok

Konfigurációs problémák miatt a rendszer nem találja a megadott terv beállításait.

## <a name="resolution"></a>Megoldás

- Lépjen az **Alaptervezés \> Beállítás \> Konstrukciók \> Alaptervek** részre, és győződjön meg róla, hogy létezik a megadott nevű terv.
