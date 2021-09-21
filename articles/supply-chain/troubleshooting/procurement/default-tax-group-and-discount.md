---
title: Az alapértelmezett adócsoport és készpénzfizetési engedmény nem kerül kitöltésre a számlázási fiókból
description: Egy alapértelmezett adócsoport és egy alapértelmezett készpénzfizetési engedmény nem kerül kitöltésre a számlázási fiókból
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: bb984eb17209dc92e336df5ad475bb0f70c6e35c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476545"
---
# <a name="default-tax-group-and-cash-discount-arent-filled-in-from-the-invoice-account"></a>Az alapértelmezett adócsoport és készpénzfizetési engedmény nem kerül kitöltésre a számlázási fiókból

## <a name="symptoms"></a>Tünetek

Ha olyan számlázási fiókot használ, amely eltér a vevői számlától, akkor egy alapértelmezett áfacsoport és egy alapértelmezett készpénzfizetési engedmény nem lesz kitöltve a számlázási fiókból a beszerzési rendelés létrehozásakor.

## <a name="resolution"></a>Megoldás

Ez szándékosan van. Az adócsoport, készpénzfizetési engedmények és egyéb áradatok alapértelmezett értékei a vevői fiókon, nem pedig a számlázási fiókon alapulnak.
