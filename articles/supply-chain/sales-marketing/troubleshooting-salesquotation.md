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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 9a9cc821d2fe9accad1dae210271682cdd2ce4ba
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232206"
---
# <a name="troubleshoot-sales-quotations"></a>Értékesítési ajánlatok hibaelhárítása

Ez a témakör azt mutatja be, hogyan lehet javítani az értékesítési árajánlatok használata során felmerülő problémákat.

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a>Nem lehet módosítani egy szolgáltatási tétel értékesítési ajánlatának értékesítési mennyiségét.

### <a name="issue-description"></a>Probléma leírása

Ha az értékesítési mennyiséget (**SalesQty** mező) egy *Szolgáltatás* típusú elemhez próbálja beállítani egy értékesítési árajénlat sorában, a következő üzenetet kapja: „Frissítés nem engedélyezett a Mennyiség mezőhöz”.

### <a name="issue-resolution"></a>Probléma megoldása

Nem állíthat be értékesítési mennyiséget a szolgáltatási tétel termékekhez. Ha például egy terméket telepítésével kapcsolatos szolgáltatást kínál, akkor nincs értelme a mennyiséget rögzítenie, mert nincs tényleges tétel. Csak egy szolgáltatás van.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]