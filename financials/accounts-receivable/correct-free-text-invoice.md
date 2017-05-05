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
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: ab16c517abfd3fa2b59625fff04b7427ee3471bb
ms.lasthandoff: 03/31/2017


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



