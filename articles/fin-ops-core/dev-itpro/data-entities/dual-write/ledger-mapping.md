---
title: Integrált főkönyv
description: Ez a témakör a főkönyvi adatok Finance and Operations és más Dynamics 365 alkalmazások közötti, a Dataverse használatával történő integrációját ismerteti.
author: tonyafehr
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: tfehr
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 0deb4198acb59b90bf06e4050889d028df2223e3
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2022
ms.locfileid: "8063647"
---
# <a name="integrated-ledger"></a>Integrált főkönyv

[!include [banner](../../includes/banner.md)]



Egy üzleti pályázatban a főkönyvi adatok határozzák meg a vállalat üzleti tevékenységének alapbeállítását. A főkönyvi adatok például tartalmazzák a vállalat üzleti évét, a tranzakciók pénznemét és a vállalat által használt számlákat. Ez a témakör az alapvető pénzügyi adatok integrálását írja le.

## <a name="templates"></a>Sablonok

A főkönyvi adatok tartalmazzák azokat a központi pénzügyi táblaleképezéseket, amelyek – az alábbi táblázatban látható módon – együttműködnek az adatok interakciója során.

Finance and Operations alkalmazások | Customer Engagement alkalmazások     | Leírás
---------------------------------|----------------------------------|------------
[CDS-árfolyamok](mapping-reference.md#123) | msdyn_currencyexchangerates |
[Számlatükör](mapping-reference.md#121) | msdyn_chartofaccountses |
[Pénznemek](mapping-reference.md#218) | transactioncurrencies |
[Az árfolyam pénznempárja](mapping-reference.md#122) | msdyn_currencyexchangeratepairs |
[Árfolyamtípus](mapping-reference.md#129) | msdyn_exchangeratetypes |
[Pénzügyi dimenzió formátuma](mapping-reference.md#130) | msdyn_financialdimensionformats |
[Pénzügyi dimenziók](mapping-reference.md#128) | msdyn_dimensionattributes |
[Pénzügyi naptár integrációs entitása](mapping-reference.md#132) | msdyn_fiscalcalendars |
[Pénzügyi naptári időszak](mapping-reference.md#131) | msdyn_fiscalcalendarperiods |
[Pénzügyi naptári év integrációs entitása](mapping-reference.md#133) | msdyn_fiscalcalendaryears |
[Ledger](mapping-reference.md#148) | msdyn_ledgers |
[Fő számla](mapping-reference.md#152) | msdyn_mainaccounts |
[Főszámla-kategóriák](mapping-reference.md#151) | msdyn_mainaccountcategories |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
