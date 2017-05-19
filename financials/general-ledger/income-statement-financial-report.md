---
title: "Bevételkimutatás pénzügyi jelentés"
description: "Ez a cikk a bevételkimutatások alapvető jelentését írja le. Emellett a jelentéshez tartozó építőelemeket is leírja."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: a57badea794667888aebb6b1653c187909afd3b1
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="income-statement-financial-report"></a>Bevételkimutatás pénzügyi jelentés

[!include[banner](../includes/banner.md)]


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

 

<a name="see-also"></a>Lásd még
--------

[Pénzügyi jelentések](financial-reporting-getting-started.md)

[Pénzügyi jelentések megtekintése](view-financial-reports.md)

[Dynamics Pénzügyi jelentések blog](http://blogs.msdn.com/b/dynamics_financial_reporting/)




