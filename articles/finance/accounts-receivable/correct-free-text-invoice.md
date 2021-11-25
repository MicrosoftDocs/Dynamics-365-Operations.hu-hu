---
title: Szabadszöveges számla helyesbítése
description: Ez a cikk a már feladott szabadszöveges számlák kijavításának és azok javított számlaként való újbóli kiadásának módszereit mutatja be.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: roschlom
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cf4503e3d4b200219d6b444b69c866871d21787d
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/05/2021
ms.locfileid: "7753802"
---
# <a name="correct-a-free-text-invoice"></a>Szabadszöveges számla helyesbítése

[!include [banner](../includes/banner.md)]

Ez a cikk a már feladott szabadszöveges számlák kijavításának és azok javított számlaként való újbóli kiadásának módszereit mutatja be.

Már elkönyvelt szabadszöveges számla javításához nyissa meg a könyvelt szabadszöveges számlát. A **Számla** lapon válassza a **Mégse** elemet, majd a **Helyes számla** lehetőséget. Válassza ki az okkódot, és adjon hozzá megjegyzéseket és válassza ki az új javított számla dátumát. Módosíthatja és feladhatja a javított számlát. 

A javított számla feladásakor egy érvénytelenítő számla jön létrea hitel összeghez, amit kiegyenlíti az eredeti számla összeget. Ezért az eredeti és az érvénytelenítő számla kombinált egyenlege 0 (nulla). Az érvénytelenítő számlát az eredeti számlával szemben számolnak el. 

A javított számla feladásakor, három számlája lesz:

-   **Eredeti számla** – Az a számla, amely a javítandó adatokat tartalmazza.
-   **Érvénytelenítési számla** – A rendszer által előállított jóváíró számla, amely a legutoljára helyesbített számla érvénytelenítéséhez lett létrehozva.
-   **Javított számla** – Az a számla, amely a helyesbített számlaadatokat tartalmazza.

Kétféle módon határozhatja meg a számlák érvénytelenítését és javítását:

-   Az **összes szabadszöveges számlák** lap tartalmazza a **Javítás** oszlopot, amelyen megtekintheti, hogy mely számlák érvénytelenítési számlák és javított számlák.
-   A szabadszöveges számla fejlécének állapotjelzője **Érvénytelenítési számla '\[ számlaszám\]'** vagy **Javított számla '\[ számlaszám\]'**.

> [!NOTE]
> Ez a funkció csak akkor használható, ha be van állítva a **Szabadszöveges számla javítása** konfigurációs kulcs. A konfigurációs kulcsok engedélyezésével (vagy letiltásával) kapcsolatos további tudnivalókért lásd a [Karbantartási mód](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md) konfigurációs kulcsok szakaszát. 





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
