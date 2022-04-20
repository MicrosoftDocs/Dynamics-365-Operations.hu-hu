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
ms.openlocfilehash: 124fb90ecafd4f4cccbd8a8bb443694c95365732
ms.sourcegitcommit: 197e6ddee84522fd587c6e4ee4f9089101e301c2
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2022
ms.locfileid: "8570310"
---
# <a name="sales-update-history-cleanup-job-fails-or-has-performance-issues"></a>Értékesítésfrissítések előzményadat-tisztítási feladata sikertelen vagy teljesítményproblémákat tapasztalt

## <a name="symptoms"></a>Tünetek

Az **Értékesítésfrissítések előzményadat-tisztítás** feladata sikertelen vagy teljesítményproblémákat tapasztalt.  

## <a name="cause"></a>Ok

Ez akkor fordulhat elő, ha a rendszer nagy számú értékesítési frissítést tartalmaz, ami nagy mennyiségű értékesítési frissítési adatokat eredményezhet. A tisztítási feladat egy tranzakció minden adatának tisztítására tesz kísérletet. Emiatt a feladat futtatása nagyon hosszú ideig tarthat vagy akár sikertelen is lehet.

## <a name="resolution"></a>Megoldás

Az **Értékesítés frissítési előzményeinek tisztítása** kötegelt feladat egy új verziója elérhető a Supply Chain Management 10.0.19-es és újabb verzióiban. Ez a funkció alapértelmezés szerint nincs bekapcsolva. A funkció működését és a funkciókezelésben való engedélyezését az Értékesítési [előzmények adatainak tisztításának ütemezése funkcióban olvashatja](../../sales-marketing/sales-update-history-cleanup-performance-improvements.md).

