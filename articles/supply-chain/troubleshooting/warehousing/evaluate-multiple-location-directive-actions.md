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
ms.openlocfilehash: 2d5f7cf548eb6c18d9700c73ef084f197b78542e
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/09/2022
ms.locfileid: "8102963"
---
# <a name="multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a>A több termékváltozat opció nem értékeli ki a több helyszínre vonatkozó irányelvi műveleteket

## <a name="symptoms"></a>Tünetek

Az *Értékesítési rendelések* munkarendelési típusának és a *Kitárolás* munkatípusnak nem kell több helyre vonatkozó irányelv-műveleteket kiértékelnie, ha a **Több termékváltozat** beállítás van kiválasztva. Csak az első hely irányelv-művelet van kiértékelve.

## <a name="resolution"></a>Megoldás

Egy új funkció, a *Több termékváltozatos helyirányelvek összes műveletének kiértékelése* hozzá lett adva a 10.0.15 verzióhoz (lásd: [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)). Ez a funkció kiértékeli a több termékváltozatos helyirányelvek összes műveletét. Az Ellátásilánc-kezelés 10.0.21-es verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva.  A 10.0.25-ös ellátásilánc-kezelésben ez a funkció kötelező, és nem lehet kikapcsolni. A rendszergazdák a Szolgáltatáskezelés [lapon ellenőrizhetik](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a funkció állapotát, és szükség esetén engedélyezhetik vagy letilthatják azt.
