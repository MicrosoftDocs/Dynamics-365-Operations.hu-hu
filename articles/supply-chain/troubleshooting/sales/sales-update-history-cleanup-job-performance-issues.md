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
ms.openlocfilehash: 4f04dc204c705b40ed25fadc75118feaef4d6b6e
ms.sourcegitcommit: 42bd701179e664947b6eafcd1804c83a5e64abcb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2021
ms.locfileid: "7641463"
---
# <a name="sales-update-history-cleanup-job-fails-or-has-performance-issues"></a>Értékesítésfrissítések előzményadat-tisztítási feladata sikertelen vagy teljesítményproblémákat tapasztalt

## <a name="symptoms"></a>Tünetek

Az **Értékesítésfrissítések előzményadat-tisztítás** feladata sikertelen vagy teljesítményproblémákat tapasztalt.  

## <a name="cause"></a>Ok

Ez akkor fordulhat elő, ha a rendszer nagy számú értékesítési frissítést tartalmaz, ami nagy mennyiségű értékesítési frissítési adatokat eredményezhet. A tisztítási feladat egy tranzakció minden adatának tisztítására tesz kísérletet. Emiatt a feladat futtatása nagyon hosszú ideig tarthat vagy akár sikertelen is lehet.

## <a name="resolution"></a>Megoldás

Az **Értékesítés frissítési előzményeinek tisztítása** kötegelt feladat egy új verziója elérhető a Supply Chain Management 10.0.19-es és újabb verzióiban. Alapértelmezés szerint ez a funkció nincs bekapcsolva. A működésről és a funkciókezelésben való engedélyezéséről az [Értékesítési előzmények tisztítása teljesítményjavításai](../../sales-marketing/sales-update-history-cleanup-performance-improvements.md) szakasz tartalmaz részletes információkat.

