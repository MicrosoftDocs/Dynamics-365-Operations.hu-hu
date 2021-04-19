---
title: Részleges kiadások és részleges szállítmányok – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a részleges kiadásokat és a részleges szállításokat végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.
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
ms.openlocfilehash: 5534099f81a97a1dcf4908784fd71dd03cf94eaf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828154"
---
# <a name="troubleshoot-partial-releases-and-partial-shipments"></a>Részleges kiadások és részleges szállítmányok – hibaelhárítás

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a részleges kiadásokat és a részleges szállításokat végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.

## <a name="the-release-status-of-a-sales-order-remains-partially-released-even-after-the-sales-order-is-invoiced"></a>Egy értékesítési rendelés kiadási állapota még az értékesítési rendelés számlázása után is részlegesen jelenik meg.

### <a name="issue-description"></a>Probléma leírása

Egy értékesítési rendelés szállítási rendelés, de egy vagy több cikknek más a szállítási módja. A rendelés számlázása után a program továbbra is *Részlegesen kiadott* kiadási állapotú.

Például egy értékesítési rendelésnek két eleme van: egy szállításra és egy kitárolásra. A szállítás és a kitárolás is megtörtént. Ennélfogva mindkét sor számlázva van. A kiadási állapot azonban továbbra is *Részleges kiadásként* jelenik meg, ami félrevezető.

### <a name="issue-resolution"></a>Probléma megoldása

A kiadás állapota csak azokra a rendelési sorokra vonatkozik, amelyeknél a cikkek engedélyezve vannak a raktárkezelésben. Emiatt a kiadási állapot továbbra is *Részlegesen kiadott* marad ebben a forgatókönyvben. A Microsoft kiértékelte ezt a hibát, és megállapította, hogy ez egy funkciókorlátozás. A kiadási állapot frissítéséhez egy kiterjesztés adható a szállítólevél és a számlázási folyamat részeként.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]