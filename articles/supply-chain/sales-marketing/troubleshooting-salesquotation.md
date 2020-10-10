---
title: Értékesítési ajánlatok hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet javítani az értékesítési árajánlatok használata során felmerülő problémákat.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 67610a833be132399b2d47ae8c6b27119be9ce95
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834367"
---
# <a name="troubleshoot-sales-quotations"></a>Értékesítési ajánlatok hibaelhárítása

Ez a témakör azt mutatja be, hogyan lehet javítani az értékesítési árajánlatok használata során felmerülő problémákat.

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a>Nem lehet módosítani egy szolgáltatási tétel értékesítési ajánlatának értékesítési mennyiségét.

### <a name="issue-description"></a>Probléma leírása

Ha az értékesítési mennyiséget (**SalesQty** mező) egy *Szolgáltatás* típusú elemhez próbálja beállítani egy értékesítési árajénlat sorában, a következő üzenetet kapja: „Frissítés nem engedélyezett a Mennyiség mezőhöz”.

### <a name="issue-resolution"></a>Probléma megoldása

Nem állíthat be értékesítési mennyiséget a szolgáltatási tétel termékekhez. Ha például egy terméket telepítésével kapcsolatos szolgáltatást kínál, akkor nincs értelme a mennyiséget rögzítenie, mert nincs tényleges tétel. Csak egy szolgáltatás van.

