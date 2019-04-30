---
title: Projekt értékesítési rendelései
description: Ez a témakör ismerteti az idő-és anyagelszámolású projekteknél a projekt alapú értékesítési rendelések létrehozását.
author: KimANelson
manager: AnnBe
ms.date: 04/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2019-04-05
ms.dyn365.ops.version: AX 10.0.2
ms.openlocfilehash: 1d54c98a08dc7cccb5cafbbe401d0ce25a276c25
ms.sourcegitcommit: 9796d022a8abf5c07abcdee6852ee34f06d2eb57
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/12/2019
ms.locfileid: "976664"
---
# <a name="project-sales-orders-for-time-and-material-projects"></a>Projekt alapú értékesítési rendelések idő és anyag projektekhez.

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

Ez a témakör bemutatja hogyan hozhat létre értékesítési rendelést egy projekthez. Értékesítési rendelések csak **idő- és anyag** típusú projektekhez használhatók.

Ha az idő- és anyagalapú projektnél több finanszírozási forrás is engedélyezve van a **Projektvezetési paraméterek** beállítás **Több finanszírozási forrással rendelkező projekthez tartozó értékesítési rendelések engedélyezése** értékével. 

> [!NOTE]
> - Projekt értékesítési rendelések támogatása több finanszírozási forrással támogatása a 10.0.2 alkalmazáskiadástól kezdődően érhető el.
> - A paraméter, amely lehetővé teszi a több finanszírozási forrással rendelkező projekt értékesítési rendeléseket a 2020 április hullámban kivezetésre kerül, amely után a funkció mindig engedélyezve lesz.

Értékesítési rendelések alapján kétféleképpen hozhat létre projektet:

- Magából a projektből. A Művelet panelen válassza a **Kezelés > Cikkfeladatok > Értékesítési rendelés** lehetőséget. A projektadatok a projekt értékesítési rendeléséből érkeznek. Ha a projektszerződés egynél több finanszírozási forrást tartalmaz, szükséges lesz a finanszírozási forrás beállítása a vevő beállításához az értékesítési rendeléshez. Ha a projekthez csak egy finanszírozási forrás tartozik, a vevő automatikusan lesz beállítva.
- Menjen az **Összes értékesítési rendelés** listaoldalra, és hozzon létre egy új értékesítési rendelést. Ki kell választania a projektet az értékesítési rendeléshez. A projekt kiválasztása után, a vevő a finanszírozási forrásból lesz beállítva, vagy Önnek kell kiválasztania a finanszírozási forrást, ha a projekt több finanszírozási forrással rendelkezik.

