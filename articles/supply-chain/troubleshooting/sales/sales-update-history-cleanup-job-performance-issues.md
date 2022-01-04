---
title: Értékesítésfrissítések előzményadat-tisztítási feladata sikertelen vagy teljesítményproblémákat tapasztalt
description: Az Értékesítési előzmények tisztítása kötegelt feladat sikertelen lehet, vagy nagyon hosszú ideig tarthat, ha nagy mennyiségű értékesítési frissítési adat van.
author: myvakalo
ms.date: 10/05/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c02273adf90afc67b7c0ae1b82c19d489bfbd3b1
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920074"
---
# <a name="sales-update-history-cleanup-job-fails-or-has-performance-issues"></a>Értékesítésfrissítések előzményadat-tisztítási feladata sikertelen vagy teljesítményproblémákat tapasztalt

## <a name="symptoms"></a>Tünetek

Az **Értékesítésfrissítések előzményadat-tisztítás** feladata sikertelen vagy teljesítményproblémákat tapasztalt.  

## <a name="cause"></a>Ok

Ez akkor fordulhat elő, ha a rendszer nagy számú értékesítési frissítést tartalmaz, ami nagy mennyiségű értékesítési frissítési adatokat eredményezhet. A tisztítási feladat egy tranzakció minden adatának tisztítására tesz kísérletet. Emiatt a feladat futtatása nagyon hosszú ideig tarthat vagy akár sikertelen is lehet.

## <a name="resolution"></a>Megoldás

Az **Értékesítés frissítési előzményeinek tisztítása** kötegelt feladat egy új verziója elérhető a Supply Chain Management 10.0.19-es és újabb verzióiban. Alapértelmezés szerint ez a funkció nincs bekapcsolva. A funkció működésével és a funkciókezelésben való engedélyezésével kapcsolatos részleteket lásd az Értékesítési [előzmények tisztítása teljesítményjavítási fejlesztésekben](../../sales-marketing/sales-update-history-cleanup-performance-improvements.md).

