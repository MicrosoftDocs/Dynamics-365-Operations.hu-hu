---
title: Integrált adó
description: Ez a témakör az adóügyi adatok integrációját ismerteti a Finance and Operations és a Dataverse között.
author: robinarh
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: rhaertle
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: a7992520b57b4c19b6dc8e13bd8e9ffc87b40f5a
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750642"
---
# <a name="integrated-tax"></a>Integrált adó

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Az adóadatok beállítása határozza meg mind a közvetett adók (áfa, GST), mind az adóelőleg beállításait. Leírja az adószámítási szabályt, az adókulcsot, az adókönyvelés és az elszámolás részleteit, illetve további fogalmakat.

## <a name="templates"></a>Sablonok

Az adóadatok tartalmazzák azokat a táblaleképezéseket, amelyek – az alábbi táblázatban látható módon – együttműködnek az adatok interakciója során.

Finance and Operations-alkalmazásoknak | Modellvezérelt alkalmazások a Dynamics 365-ben | Leírás |
-------------------------|---------------------------------|----|
Cikkáfacsoport | msdyn_taxitemgroups |
Adóhatóságok | msdyn_taxauthorities |
Áfamentességi kódentitáshoz tartozó CDS | msdyn_taxexemptcodes |
Áfacsoportok | msdyn_taxgroups |
Áfás főkönyvi feladási csoportok V2 | msdyn_taxpostinggroups |
Adóelőlegkódok | msdyn_withholdingtaxcodes |
Adóelőleg-csoportok | msdyn_withholdingtaxgroups | 


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Tax item groups](includes/TaxItemGroupHeadings-msdyn-taxitemgroups.md)]

[!include [Tax Authorities](includes/SalesTaxAuthorities-msdyn-taxauthorities.md)]

[!include [Tax Exemptions](includes/CdsTaxExemptCodes-msdyn-taxexemptcodes.md)]

[!include [Tax groups](includes/TaxGroupEntity-msdyn-taxgroups.md)]

[!include [Tax Ledger Account Group](includes/TaxPostingGroupsV2--msdyn-taxpostinggroups.md)]

[!include [Withholding tax codes](includes/WithholdingCode-msdyn-withholdingtaxcodes.md)]

[!include [Withholding tax groups](includes/WithholdingGroups-msdyn-withholdingtaxgroups.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]