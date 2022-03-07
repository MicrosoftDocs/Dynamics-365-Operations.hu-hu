---
title: Az értékesítési árajánlat sorában szereplő szolgáltatási cikk mennyisége nem állítható be
description: Értékesítési ajánlatok használatakor nem lehet beállítani értékesítési mennyiséget olyan termékekhez, amelyek szolgáltatási cikkek, mivel nincsenek megszámolható fizikai cikkek.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ea0f8f246e95f90b6ac5e78ee63950c9ca836a0e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476593"
---
# <a name="cant-change-the-sales-quantity-of-a-service-item-on-a-sales-quotation-line"></a>Az értékesítési ajánlat sorában szereplő szolgáltatási cikk értékesítési mennyisége nem változtatható

## <a name="symptoms"></a>Tünetek

Ha az értékesítési mennyiséget (**SalesQty** mező) egy *Szolgáltatás* típusú elemhez próbálja beállítani egy értékesítési árajénlat sorában, a következő üzenetet kapja:

> Frissítés nem engedélyezett a Mennyiség mezőhöz.

## <a name="cause"></a>Ok

Ez szándékosan van. Nem állíthat be értékesítési mennyiséget a szolgáltatási tétel termékekhez. Ha például egy terméket telepítésével kapcsolatos szolgáltatást kínál, akkor nincs értelme a mennyiséget rögzítenie, mert nincs tényleges cikk, ami megszámolható. Csak egy szolgáltatás van.
