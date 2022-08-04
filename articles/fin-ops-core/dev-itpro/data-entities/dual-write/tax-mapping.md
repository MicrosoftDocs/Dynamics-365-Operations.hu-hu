---
title: Integrált adó
description: Ez a témakör leírja az adózási adatok integrálását a pénzügyek és a műveletek, valamint a Dataverse.
author: tonyafehr
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: tfehr
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 29d8b2079b5d1cd70f14e096780f83a4a38d4b63
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111536"
---
# <a name="integrated-tax"></a>Integrált adó

[!include [banner](../../includes/banner.md)]



Az adóadatok beállítása határozza meg mind a közvetett adók (áfa, GST), mind az adóelőleg beállításait. Leírja az adószámítási szabályt, az adókulcsot, az adókönyvelés és az elszámolás részleteit, illetve további fogalmakat.

## <a name="templates"></a>Sablonok

Az adóadatok tartalmazzák azokat a táblaleképezéseket, amelyek – az alábbi táblázatban látható módon – együttműködnek az adatok interakciója során.

| Finance and Operations alkalmazások | Customer Engagement alkalmazások | Leírás |
|-----------------------------|-----------------------------------|-------------|
[Cikkáfacsoport](mapping-reference.md#196) | msdyn_taxitemgroups | |
[Adóhatóságok](mapping-reference.md#193) | msdyn_taxauthorities | |
[Áfamentességi kódentitáshoz tartozó CDS](mapping-reference.md#194) | msdyn_taxexemptcodes | |
[Áfacsoportok](mapping-reference.md#195) | msdyn_taxgroups | |
[Áfás főkönyvi feladási csoportok V2](mapping-reference.md#197) | msdyn_taxpostinggroups | |
[Adóelőlegkódok](mapping-reference.md#210) | msdyn_withholdingtaxcodes | |
[Adóelőleg-csoportok](mapping-reference.md#211) | msdyn_withholdingtaxgroups | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

