---
title: A beszerzési megállapodás maximális korlátja nem érvényes egy beszerzési igénylésen
description: A beszerzési megállapodás maximális korlátja nem érvényes egy beszerzési igénylésen
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: c19d40dce65acbe80d4572bfc4e925aa87ea4f02
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476530"
---
# <a name="the-purchase-agreement-maximum-limit-isnt-effective-on-a-purchase-requisition"></a>A beszerzési megállapodás maximális korlátja nem érvényes egy beszerzési igénylésen

## <a name="symptoms"></a>Tünetek

Amikor egy beszerzési igénylés egy beszerzési szerződéshez van kapcsolva, a beszerzési szerződés maximálisan megengedett határértéke nem érvényes a beszerzési igénylésre. A program helyesen írja be az alapértelmezett árat, de a beszerzési megállapodásban szereplő maximális korlátozásnál többet is lehetséges rendelni a beszerzési igénylésben.

## <a name="resolution"></a>Megoldás

Ez a viselkedés várható. Mivel az igényléseket nem mindig hagyják jóvá, egy mennyiséget vagy összeget nem szabad lefoglalni a beszerzési szerződésen. Ennélfogva nem fogja elérni a beszerzési szerződés maximális határértékét.
