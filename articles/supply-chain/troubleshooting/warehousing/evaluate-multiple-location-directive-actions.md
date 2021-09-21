---
title: Összes művelet kiértékelése több raktározási egység helyutasításai esetében
description: Új funkcióval bővült a több termékváltozatos helyirányelvek összes műveletének kiértékelése. Ez a lap arról nyújt tájékoztatást, hogyan lehet bekapcsolni.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 45995ed6f051cdf6be2b2985ff0e2cb1decf4cf0
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476535"
---
# <a name="multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a>A több termékváltozat opció nem értékeli ki a több helyszínre vonatkozó irányelvi műveleteket

## <a name="symptoms"></a>Tünetek

Az *Értékesítési rendelések* munkarendelési típusának és a *Kitárolás* munkatípusnak nem kell több helyre vonatkozó irányelv-műveleteket kiértékelnie, ha a **Több termékváltozat** beállítás van kiválasztva. Csak az első hely irányelv-művelet van kiértékelve.

## <a name="resolution"></a>Megoldás

Egy új funkció, a *Több termékváltozatos helyirányelvek összes műveletének kiértékelése* hozzá lett adva a 10.0.15 verzióhoz (lásd: [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)). Ez a funkció kiértékeli a több termékváltozatos helyirányelvek összes műveletét. Ha szüksége van erre a funkcióra, használja a [Funkciókezelés](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) lehetőséget a funkció bekapcsolásához.
