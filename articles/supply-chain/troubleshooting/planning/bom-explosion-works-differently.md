---
title: Az anyagjegyzék-aláütemezés másképpen viselkedik a megerősített és a becsült termelési rendeléseknél
description: Az anyagjegyzék aláütemezése eltérően viselkedik a megerősített termelési rendeléseknél és a manuálisan létrehozott munka becsült termelési rendeléseinél
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 94d4b00ea30396923a61b2748cf1aaeedc0af8af
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476549"
---
# <a name="bom-explosion-behaves-differently-for-firmed-and-estimated-production-orders"></a>Az anyagjegyzék-aláütemezés másképpen viselkedik a megerősített és a becsült termelési rendeléseknél

## <a name="symptoms"></a>Tünetek

Ha egy gyártási rendelés meg van erősítve, a cikkek nem lesznek alábontva, amikor alábontja az anyagjegyzéket (BOM). Azonban ha manuálisan hoz létre egy munkarendelést, majd megbecsüli a termelési rendelést, a cikkek alábontásra kerülnek.

### <a name="resolution"></a>Megoldás

A termelési rendelés megerősítésekor bekövetkező alábontás a tervezett rendelésre mutat, de nem tűnik jelenik meg, hogy a tervezett rendelés ebben az esetben meg lennel erősítve. Ha azonban a termelési rendelés meg lett becsülve, az alábontás az engedélyezett termelési rendelésből aktiválódik, ahol nincs tervezett rendelés.
