---
title: Értékesítési ajánlatok hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet javítani az értékesítési árajánlatok használata során felmerülő problémákat.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 92b77c1b7de1f5c946e677c810c0d0e43427473e7ba26679df23f7663946dbc0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765394"
---
# <a name="troubleshoot-sales-quotations"></a>Értékesítési ajánlatok hibaelhárítása

Ez a témakör azt mutatja be, hogyan lehet javítani az értékesítési árajánlatok használata során felmerülő problémákat.

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a>Nem lehet módosítani egy szolgáltatási tétel értékesítési ajánlatának értékesítési mennyiségét.

### <a name="issue-description"></a>Probléma leírása

Ha az értékesítési mennyiséget (**SalesQty** mező) egy *Szolgáltatás* típusú elemhez próbálja beállítani egy értékesítési árajénlat sorában, a következő üzenetet kapja: „Frissítés nem engedélyezett a Mennyiség mezőhöz”.

### <a name="issue-resolution"></a>Probléma megoldása

Nem állíthat be értékesítési mennyiséget a szolgáltatási tétel termékekhez. Ha például egy terméket telepítésével kapcsolatos szolgáltatást kínál, akkor nincs értelme a mennyiséget rögzítenie, mert nincs tényleges tétel. Csak egy szolgáltatás van.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]