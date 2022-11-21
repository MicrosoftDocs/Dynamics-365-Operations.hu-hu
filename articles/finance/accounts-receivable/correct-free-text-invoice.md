---
title: Szabadszöveges számla helyesbítése
description: Ez a cikk a már feladott szabadszöveges számlák kijavításának és azok javított számlaként való újbóli kiadásának módszereit mutatja be.
author: abruer
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b3cc07a1f0ba444250eddcf892681e2ca63e9c1a
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780234"
---
# <a name="correct-a-free-text-invoice"></a>Szabadszöveges számla helyesbítése

[!include [banner](../includes/banner.md)]

Ez a cikk a már feladott szabadszöveges számlák kijavításának és azok javított számlaként való újbóli kiadásának módszereit mutatja be.

A már feladott szabadszöveges számlák kijavítása: 
1. A feladott szabadszöveges számla megnyitása. 
2. A **Számla** lapon válassza a **Mégse** elemet, majd a **Helyes számla** lehetőséget. 
3. Válassza ki az okkódot, és adjon hozzá megjegyzéseket és válassza ki az új javított számla dátumát.
4. Módosíthatja és feladhatja a javított számlát. 

A javított számla feladásakor egy érvénytelenítő számla jön létrea hitel összeghez, amit kiegyenlíti az eredeti számla összeget. Ezért az eredeti és az érvénytelenítő számla kombinált egyenlege 0 (nulla). Az érvénytelenítő számlát az eredeti számlával szemben számolnak el. 

A javított számla feladásakor, három számlája lesz:

-   **Eredeti számla** – Az a számla, amely a javítandó adatokat tartalmazza.
-   **Érvénytelenítési számla** – A rendszer által előállított jóváíró számla, amely a legutoljára helyesbített számla érvénytelenítéséhez lett létrehozva.
-   **Javított számla** – Az a számla, amely a helyesbített számlaadatokat tartalmazza.

Kétféle módon határozhatja meg a számlák érvénytelenítését és javítását:

-   Az **összes szabadszöveges számlák** lap tartalmazza a **Javítás** oszlopot, amelyen megtekintheti, hogy mely számlák érvénytelenítési számlák és javított számlák.
-   A szabadszöveges számla fejlécének állapotjelzője **Érvénytelenítési számla '\[számlaszám\]'** vagy **Javított számla '\[számlaszám\]'**.

> [!NOTE]
> Ez a funkció csak akkor használható, ha be van állítva a **Szabadszöveges számla javítása** konfigurációs kulcs. A konfigurációs kulcsok engedélyezéséről a Karbantartási mód című cikk Enable (vagy disable) [konfigurációs kulcsokat című szakasza tartalmaz](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md). 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
