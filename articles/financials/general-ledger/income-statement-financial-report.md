---
title: "Bevételkimutatás pénzügyi jelentés"
description: "Ez a cikk a bevételkimutatások alapvető jelentését írja le. Emellett a jelentéshez tartozó építőelemeket is leírja."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 9310508082ff710cd040b74519044f5a90c23988
ms.contentlocale: hu-hu
ms.lasthandoff: 05/08/2018

---

# <a name="income-statement-financial-report"></a>Bevételkimutatás pénzügyi jelentés

[!include [banner](../includes/banner.md)]

Ez a cikk a bevételkimutatások alapvető jelentését írja le. Emellett a jelentéshez tartozó építőelemeket is leírja. 

<a name="default-income-statement-report"></a>Alapértelmezett bevételkimutatás jelentés
-------------------------------

| Alapértelmezett jelentés             | Mire szolgál?                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| Bevétel-kimutatás – Alapértelmezett | Megmutatja a szervezet nyereségességét az aktuális időszakra és a folyó év mai napjáig. |

## <a name="building-blocks"></a>Építőelemek
Az eredménykimutatás pénzügyi jelentések a következő építőelemekből állnak.

| Alapértelmezett jelentés             | Sor definíciója                     | Oszlopdefiníció          |
|----------------------------|------------------------------------|----------------------------|
| Bevételkimutatás – Alapértelmezett | Összesített bevételkimutatás – Alapértelmezett | Időszakos és Idei – Alapértelmezett |

### <a name="row-definition"></a>Sor definíciója

A sordefiníció, Összesítő Eredménykimutatás – Alapértelmezett, a hagyományos eredménykimutatás minden részére tartalmaz egy szakaszt. A Főszámla-kategória dimenzió a sordefiníció létrehozásához használatos. Ezért bárki létrehozhat jelentést anélkül, hogy módosításokat végezne.

### <a name="column-definition"></a>Oszlopdefiníció

Az oszlopdefiníciók tartalmaznak különböző típusú oszlopokot, a különböző szintű részletességre és pénzügyi adatokra.

-   **Szakaszos és Idei – Alapértelmezett oszloptípusok:**
    -   **DESC** – A leírás a sordefinícióból
    -   **FD** – Az aktuális időszak pénzügyi adatai
    -   **FD** – Pénzügyi év adatai, a mai napig.



<a name="additional-resources"></a>További erőforrások
--------

[Pénzügyi jelentéskészítés](financial-reporting-getting-started.md)

[Pénzügyi jelentések megtekintése](view-financial-reports.md)

[Dynamics Pénzügyi jelentések blog](http://blogs.msdn.com/b/dynamics_financial_reporting/)




