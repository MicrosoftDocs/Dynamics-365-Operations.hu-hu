---
title: A folyamatban található Közvetett költségek jelentés törölt termelési rendeléseket tartalmaz
description: A folyamatban található Közvetett költségek jelentés a részlegesen feldolgozott, majd később törölt termelési rendelések adatait jeleníti meg.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdIndirectCostInProgress
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 707fa9bb30129c3656e10c6756dee770a7712e65
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026576"
---
# <a name="the-indirect-costs-in-process-report-includes-deleted-production-orders"></a>A folyamatban található Közvetett költségek jelentés törölt termelési rendeléseket tartalmaz

Tudásbáziscikk száma: 4612748

## <a name="symptoms"></a>Tünetek

A **Folyamatban lévő közvetett költségek** jelentés a részlegesen feldolgozott, majd később törölt termelési rendelések adatait jeleníti meg.

## <a name="resolution"></a>Felbontás

Termelési rendelés sztornírozása esetén az adott termelési rendelés összes tranzakcióját is sztornírozza. A termelési rendelés törlésekor az analitikus táblák és a főkönyv a hozzá kapcsolódó tranzakciókat is megtartja. A jelentések meg fogják jelenni a tranzakciókat az analitikus táblákban. Az adott termelési rendelés nettó értéke csak 0,00 lehet.
