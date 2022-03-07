---
title: A tervezett rendelések a termelési rendelésekkel együtt létrehozott készleten vannak.
description: A tervezett rendelések akkor jönnek létre, ha a készleten lévő cikkek és termelési rendelések már léteznek.
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
ms.openlocfilehash: aa803bcd7d43aa36675596050ccbe06831f1724d
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476601"
---
# <a name="planned-orders-are-generated-for-in-stock-with-production-orders"></a>A tervezett rendelések a termelési rendelésekkel együtt létrehozott készleten vannak.

## <a name="symptoms"></a>Tünetek

A tervezett rendelések akkor jönnek létre, ha a készleten lévő cikkek és termelési rendelések már léteznek.

## <a name="resolution"></a>Megoldás

Ezt a problémát úgy oldhatja meg, hogy növeli a **Fedezeti csoport** oldalon lévő **Pozitív napok** értékét. Ezen módosítás hatására a rendszer megállapítja, hogy az aktuális készlet használható-e a keresletre. Ezután nem jön létre új tervezett rendelés a készleten lévő cikkekhez.
