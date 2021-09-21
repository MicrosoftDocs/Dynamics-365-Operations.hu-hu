---
title: Nem lehet áthelyezni a licenctáblát, ha az Üres kiadás és az Üres bevételezés engedélyezve van
description: Nem tudja áthelyezni a licenctáblát, ha a sorozatszámban az Üres kiadás és az Üres bevételezés engedélyezve van. Ez a sorozatszám mező választhatóvá tételével orvosolható.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 0047f79aa417c8fc910447505f07963d014f54e7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476544"
---
# <a name="cant-move-license-plate-if-serial-number-has-blank-issue-and-blank-receipt-allowed"></a>Nem lehet áthelyezni a licenctáblát, ha a sorozatszámban az Üres kiadás és az Üres bevételezés engedélyezve van

## <a name="symptoms"></a>Tünetek

Nem helyezhető át az azonosítótábla egy **Áthelyezés** menü használatával, ha a sorozatszámhoz a nyomon követési dimenzióban az *Üres kiadás megengedett* és az *Üres nyugta megengedett* beállítások vannak, és ha ugyanazon a helyen több azonosítótábla van megadva, amelyek közül néhány tartalmaz sorozatszámot, néhány pedig nem.

## <a name="resolution"></a>Megoldás

Ezt a hibát a [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687) részben lévő telepített változtatások javítják ki. Ezek a módosítások nem teszik kötelezővé a **Sorozatszám** mező kitöltését, ha az Üres nyugta és az Üres kiadás engedélyezve van.
