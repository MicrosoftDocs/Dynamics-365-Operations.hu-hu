---
title: Hiányzó mezőbeállítások cikkmodellcsoportoknak egy másik jogi személybe való másolásakor
description: Hiányzó mezőbeállítások vannak a cikkmodellcsoportoknak egy másik jogi személybe való másolásakor.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6f6fdfef0bc377418ed8a9c8830e74526a0b95eb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026570"
---
# <a name="missing-field-settings-when-item-model-groups-are-copied-to-another-legal-entity"></a>Hiányzó mezőbeállítások cikkmodellcsoportoknak egy másik jogi személybe való másolásakor

Tudásbáziscikk száma: 4612800

## <a name="symptoms"></a>Tünetek

Ha cikkmodellcsoportokat *Cikkmodellcsoport készlet házirend* entitás használatával másol egy másik jogi személybe (vállalat), néhány mezőbeállítás (például a készletmodell és a leírás) hiányzik a cél jogi személy új modellcsoportjaból.

## <a name="resolution"></a>Felbontás

Ha egy cikkmodellcsoport teljes másolatát egy másik jogi személynek is létre kell hoznia, akkor a cikkmodellcsoport készletirányelvei, a cikkmodellcsoporthoz társított cikkmodellcsoport készletirányelveket (`InventInventoryPolicyEntity`) és a költségforgalom-feltételezés házirendjeit (`InventCostFlowAssumptionPolicyEntity`) is át kell másolnia.
