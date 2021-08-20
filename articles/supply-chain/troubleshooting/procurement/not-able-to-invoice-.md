---
title: Vevő által értékesített értékesítési rendelést nem lehet számlázni
description: A Számla automatikus feladása beállítás engedélyezése után a továbbiakban nem lehet kiszámlázni az eredeti értékesítési rendelést és az eredeti közvetlen kiszállítású beszerzési rendelést.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 30c485be79be5ebbec8b51272b8bbe6e0c7df9d81bbaaaef316dbfede03abf68
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756751"
---
# <a name="you-cant-invoice-a-customer-facing-sales-order"></a>Vevő által értékesített értékesítési rendelést nem lehet számlázni

Tudásbáziscikk száma: 4611793

## <a name="symptoms"></a>Tünetek

A **Számla automatikus feladása** beállítás engedélyezése után a szállító **Vállalatközeli** oldalán a továbbiakban nem lehet kiszámlázni az eredeti értékesítési rendelést és az eredeti közvetlen kiszállítású beszerzési rendelést.

## <a name="resolution"></a>Felbontás

A vállalatközi és a közvetlen kiszállítású rendelési számlák szinkronizálási viselkedését a [Paraméterek beállítása vállalatközi rendelés feladása során](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order) helyen szereplő paraméterek vezérlik és kényszerítik.

A paraméterek beállítása után először számlázni kell a vállalatközi értékesítési rendelést. A program ezután szinkronizálja az eredeti értékesítési és beszerzési rendeléseket.
