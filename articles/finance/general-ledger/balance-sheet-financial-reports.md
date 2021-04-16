---
title: Mérleg pénzügyi jelentés
description: Ez a cikk a mérlegek alapértelmezett jelentéseit mutatja be. Emellett az e jelentésekhez tartozó építőelemeket is leírja.
author: jcart1106
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinanicalReports
audience: Application User
ms.reviewer: roschlom
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d916b6593b641ec1c8365475103b1520e07e3768
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821937"
---
# <a name="balance-sheet-financial-reports"></a>Mérleg pénzügyi jelentés

[!include [banner](../includes/banner.md)]

Ez a cikk a mérlegek alapértelmezett jelentéseit mutatja be. Emellett az e jelentésekhez tartozó építőelemeket is leírja. 

<a name="default-balance-sheet-reports"></a>Alapértelmezett mérlegkimutatások
-----------------------------

Két alapértelmezett mérlegkimutatás áll rendelkezésre. Az egyik jelentésen a szakaszok halmozottak. A jelentésen a szakaszok egymás mellett vannak.

| Alapértelmezett jelentés                       | Mire szolgál?                                                                                                                           |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Mérleg – Alapértelmezett              | Megtekinthető a szervezet éves pénzügyi helyzete.                                                                 |
| Mérleg egymás mellett – Alapértelmezett | Megtekinthető a szervezet éves pénzügyi helyzete. Az eszközöket és a kötelezettséget, valamint a részvényesek saját tőkéjét jeleníti meg egyidejűleg. |

## <a name="building-blocks"></a>Építőelemek
A mérleg pénzügyi jelentések a következő építőelemekből állnak.

| Alapértelmezett jelentés                       | Sor definíciója                       | Oszlopdefiníció             |
|--------------------------------------|--------------------------------------|-------------------------------|
| Mérleg – Alapértelmezett              | Mérleg – Alapértelmezett              | Idei és a Eltérés – Alapértelmezett    |
| Mérleg egymás mellett – Alapértelmezett | Mérleg egymás mellett – Alapértelmezett | Folyó év mai napig oszlop – Alapértelmezett |

### <a name="row-definition"></a>Sor definíciója

A mindkét mérlegkimutatás sordefiníciói tartalmaznak szakaszokat a hagyományos mérleg minden részére. A párhuzamos jelentés oszloptörést tartalmaz, így a kötelezettség és a tulajdonos saját tőkéje az eszközök mellett jelennek meg. A Főszámla-kategória dimenzió mindkét sordefiníciók létrehozásához használatos. Ezért bárki létrehozhat jelentéseket anélkül, hogy módosításokat végezne.

### <a name="column-definition"></a>Oszlopdefiníció

Az oszlopdefiníciók tartalmaznak különböző típusú oszlopokot, a különböző szintű részletességre és pénzügyi adatokra.

-   **Idei és a Különbözet – Alapértelmezett oszloptípusok:**
    -   **DESC** – A leírás a sordefinícióból
    -   **FD** – Folyó év pénzügyi adatai, a mai napig.
    -   **FD** – Előző év pénzügyi adatai, a mai napig.
    -   **CALC** – Az előző év az aktuális év különbsége

<!-- -->

-   **Folyó év mai napig oszlop – Alapértelmezett**
    -   **DESC** – A leírás a sordefinícióból
    -   **FD** – Folyó év pénzügyi adatai, a mai napig.



<a name="additional-resources"></a>További erőforrások
--------

[Pénzügyi jelentéskészítés – áttekintés](financial-reporting-getting-started.md)

[Pénzügyi jelentések megtekintése](view-financial-reports.md)

[Dynamics Pénzügyi jelentések blog](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]