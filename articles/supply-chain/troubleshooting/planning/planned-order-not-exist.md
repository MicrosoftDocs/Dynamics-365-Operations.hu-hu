---
title: A rendszer nem talált tervezett rendelést több rendelés műveletei során.
description: A "Tervezett rendelés" hiba akkor fordul elő, amikor több tervezett rendelésen végez műveleteket, és legalább két rendelés ugyan ahhoz a cikkazonosítóhoz tartozik.
author: t-benebo
ms.date: 12/07/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo_ReqTransPoMarkChangeType
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-12-07
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 0ece4a331b63b86e896c5b337a58185ed3ea1049
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920852"
---
# <a name="the-system-cant-find-a-planned-order-during-operations-on-multiple-orders"></a>A rendszer nem talált tervezett rendelést több rendelés műveletei során.

Hibakód: SYS24774

## <a name="symptoms"></a>Tünetek

A következő hibaüzenet jelenik meg, amikor egyszerre több tervezett rendelésen próbál műveletet végrehajtani, és legalább két rendelés ugyan ahhoz a cikkazonosítóhoz tartozik. Hiba történhet például akkor, amikor a rendelések megváltoztak, vagy módosul a rendeléstípusuk.

> A(z) %1 tervezett rendelés nem létezik.

## <a name="cause"></a>Ok

Amikor a rendszer visszahozja vagy módosítja egy rendelés típusát, felül kell vizsgálnia a cikk meglévő tervezett rendeléseit, hogy a tervezett készlet megegyezett-e az igényrel és a meglévő készletekkel. A folyamat részeként a rendszer újra létrehozza a cikk tervezett rendeléseit. Emiatt a második tervezett rendelés, amelytől a rendszer várhatóan már nem fog feldolgozni, nem létezik.

## <a name="workaround"></a>Megkerülő megoldás

A rendelések jóváhagyása a feldolgozás előtt. Ily módon a rendelések nem törlődnek, ha a rendszer feldolgozza a cikk első rendelését.
