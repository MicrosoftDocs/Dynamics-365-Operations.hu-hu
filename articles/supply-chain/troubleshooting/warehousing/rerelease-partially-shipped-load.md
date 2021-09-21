---
title: Nem adhat ki újból részlegesen szállított rakomány a raktárba
description: A korábbi verziókban nem lehetett újra kiadni a részlegesen szállított rakományt, ha a hiányos foglalásokkal bizonyos funkciókat használ. A probléma ki lett javítva.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0380e1963a38f2be55b31e06b3845f935661eed2
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476569"
---
# <a name="cant-re-release-a-partially-shipped-load-to-the-warehouse"></a>Nem adhat ki újból részlegesen szállított rakomány a raktárba

## <a name="symptoms"></a>Tünetek

Nem adhat ki részlegesen szállított rakomány a raktárba. Amikor elvégzi a kiadást a raktárba, megjelenik egy „Művelet befejezve” üzenet, de nem történik semmi, és nem jön létre munka a fennmaradó mennyiséghez. Ez a probléma akkor fordul elő, ha a szállítási rakomány funkciót használja, és hiányos a foglalás.

## <a name="resolution"></a>Megoldás

A [KB 470069 számú probléma](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) („A részlegesen szállított rakományok újrahullámosíthatók és újra feldolgozhatók”) [a 10.0.15 kiadásban](/dynamics365/supply-chain/get-started/whats-new-scm-10-0-15) lett kijavítva.
