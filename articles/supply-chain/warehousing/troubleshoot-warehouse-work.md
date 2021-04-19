---
title: Raktári munka – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a raktári munkát végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 08cc074fe851b952ebfc942ae3d1cb05240d3b91
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5837441"
---
# <a name="troubleshoot-warehouse-work"></a>Raktári munka – hibaelhárítás

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a raktári munkát végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.

## <a name="i-cant-move-license-plates-that-have-serial-number-items-when-blank-issue-and-blank-receipt-are-allowed-on-the-tracking-dimension-group"></a>Nem helyezhetők át a sorozatszámos cikkeket tartalmazó azonosítótáblák, ha a nyomon követési dimenzióban engedélyezve van az üres kiadás és az üres nyugta.

### <a name="issue-description"></a>Probléma leírása

Nem helyezhető át az azonosítótábla egy **Áthelyezés** menü használatával, ha a sorozatszámhoz a nyomon követési dimenzióban az *Üres kiadás megengedett* és az *Üres nyugta megengedett* beállítások vannak, és ha ugyanazon a helyen több azonosítótábla van megadva, amelyek közül néhány tartalmaz sorozatszámot, néhány pedig nem.

### <a name="issue-resolution"></a>Probléma megoldása

Ezt a hibát a [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687) részben lévő telepített változtatások javítják ki. Ezek a módosítások nem teszik kötelezővé a **Sorozatszám** mező kitöltését, ha az üres nyugta és az üres kiadás engedélyezve van.

## <a name="i-receive-the-following-error-message-in-the-warehouse-management-mobile-app-when-i-process-movements-the-inventory-owner-1-is-not-allowed-in-this-process"></a>A következő hibaüzenet jelenik meg a Raktárkezelés mobilalkalmazásban a készletmozgások feldolgozásakor: „A készlet tulajdonosa %1 nem engedélyezett ebben a folyamatban.”

### <a name="issue-description"></a>Probléma leírása

A **Tulajdonos** követési dimenziója hiányzik, amikor a Raktárkezelés mobilalkalmazásban készletmozgatásokat végeznek. Úgy látszik, hogy a Supply Chain Management kliens rendszeres készletmozgatási naplót használ, és csak akkor lehet feladni, ha a **Tulajdonos** dimenzió ki van töltve.

### <a name="issue-resolution"></a>Probléma megoldása

A Microsoft kiértékelte ezt a hibát, és megállapította, hogy ez egy funkciókorlátozás. A raktárkezelési folyamatok jelenleg csak a jogi személy tulajdonában álló készletet támogatják.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]