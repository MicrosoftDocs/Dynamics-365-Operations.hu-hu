---
title: "Szabadszöveges számla helyesbítése"
description: "Ez a cikk a már feladott szabadszöveges számlák kijavításának és azok javított számlaként való újbóli kiadásának módszereit mutatja be."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: df94cf12accd2b18c1f8cfd43d7de5dff16e7aea
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="correct-a-free-text-invoice"></a>Szabadszöveges számla helyesbítése

[!include[banner](../includes/banner.md)]


Ez a cikk a már feladott szabadszöveges számlák kijavításának és azok javított számlaként való újbóli kiadásának módszereit mutatja be.

Már elkönyvelt szabadszöveges számla javításához nyissa meg a könyvelt szabadszöveges számlát. A **Számla** lapon válassza a **Mégse** elemet, majd a **Helyes számla** lehetőséget. Válassza ki az okkódot, és adjon hozzá megjegyzéseket és válassza ki az új javított számla dátumát. Módosíthatja és feladhatja a javított számlát. 

A javított számla feladásakor egy érvénytelenítő számla jön létrea hitel összeghez, amit kiegyenlíti az eredeti számla összeget. Ezért az eredeti és az érvénytelenítő számla kombinált egyenlege 0 (nulla). Az érvénytelenítő számlát az eredeti számlával szemben számolnak el. 

A javított számla feladásakor, három számlája lesz:

-   **Eredeti számla** – Az a számla, amely a javítandó adatokat tartalmazza.
-   **Érvénytelenítési számla** – A rendszer által előállított jóváíró számla, amely a legutoljára helyesbített számla érvénytelenítéséhez lett létrehozva.
-   **Javított számla** – Az a számla, amely a helyesbített számlaadatokat tartalmazza.

Kétféle módon határozhatja meg a számlák érvénytelenítését és javítását:

-   Az **összes szabadszöveges számlák** lap tartalmazza a **Javítás** oszlopot, amelyen megtekintheti, hogy mely számlák érvénytelenítési számlák és javított számlák.
-   A szabadszöveges számla fejlécének állapotjelzője **Érvénytelenítési számla '\[számlaszám\]'** vagy **Javított számla '\[számlaszám\]'**.

> [!NOTE]
> Ez a funkció csak akkor használható, ha be van állítva a **Szabadszöveges számla javítása** konfigurációs kulcs.




