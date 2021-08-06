---
title: Integrált adó
description: Ez a témakör az adóügyi adatok integrációját ismerteti a Finance and Operations és a Dataverse között.
author: robinarh
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: rhaertle
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: e1b5d62e56dd1f87dbfedc6a8ca7379587481ff4
ms.sourcegitcommit: f65bde9ab0bf4c12a3250e7c9b2abb1555cd7931
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/13/2021
ms.locfileid: "6542319"
---
# <a name="integrated-tax"></a>Integrált adó

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Az adóadatok beállítása határozza meg mind a közvetett adók (áfa, GST), mind az adóelőleg beállításait. Leírja az adószámítási szabályt, az adókulcsot, az adókönyvelés és az elszámolás részleteit, illetve további fogalmakat.

## <a name="templates"></a>Sablonok

Az adóadatok tartalmazzák azokat a táblaleképezéseket, amelyek – az alábbi táblázatban látható módon – együttműködnek az adatok interakciója során.

| Finance and Operations-alkalmazásoknak | Customer Engagement alkalmazások | Leírás |
|-----------------------------|-----------------------------------|-------------|
[Cikkáfacsoport](mapping-reference.md#196) | msdyn_taxitemgroups | |
[Adóhatóságok](mapping-reference.md#193) | msdyn_taxauthorities | |
[Áfamentességi kódentitáshoz tartozó CDS](mapping-reference.md#194) | msdyn_taxexemptcodes | |
[Áfacsoportok](mapping-reference.md#195) | msdyn_taxgroups | |
[Áfás főkönyvi feladási csoportok V2](mapping-reference.md#197) | msdyn_taxpostinggroups | |
[Adóelőlegkódok](mapping-reference.md#210) | msdyn_withholdingtaxcodes | |
[Adóelőleg-csoportok](mapping-reference.md#211) | msdyn_withholdingtaxgroups | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
