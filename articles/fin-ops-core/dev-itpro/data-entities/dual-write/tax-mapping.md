---
title: Integrált adó
description: Ez a témakör leírja az adózási adatok integrálását a pénzügyek és a műveletek, valamint a Dataverse.
author: josaw
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 8f148b710e2294edf1e402b9b8b22cb24e60a1f2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288794"
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

