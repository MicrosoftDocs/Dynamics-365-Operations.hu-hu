---
title: Mérleg pénzügyi jelentés
description: Ez a cikk a mérlegek alapértelmezett jelentéseit mutatja be. Emellett az e jelentésekhez tartozó építőelemeket is leírja.
author: jinniew
ms.date: 10/10/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinanicalReports
audience: Application User
ms.reviewer: twheeloc
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4aad297f401143388d682da175a6b14727a8f2f0
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/12/2022
ms.locfileid: "9643823"
---
# <a name="balance-sheet-financial-reports"></a>Mérleg pénzügyi jelentés

[!include [banner](../includes/banner.md)]

Ez a cikk a mérlegek alapértelmezett jelentéseit mutatja be. Emellett az e jelentésekhez tartozó építőelemeket is leírja. 

## <a name="default-balance-sheet-reports"></a>Alapértelmezett mérlegkimutatások

Két alapértelmezett mérlegkimutatás áll rendelkezésre. Az egyik jelentésen a szakaszok halmozottak. A jelentésen a szakaszok egymás mellett vannak.

| Alapértelmezett jelentés                       | Mire szolgál?                                                                                                                           |
|--------------------------------------|--------------------------------------------------------------------------------------|
| Mérleg – Alapértelmezett              | Megtekinthető a szervezet éves pénzügyi helyzete.                    |
| Mérleg és kimutatás egymás mellett – alapértelmezett | A szervezet pénzügyi helyzetének egymás mellett való áttekintését biztosítja. |

## <a name="building-blocks"></a>Építőelemek
A mérleg pénzügyi jelentések a következő építőelemekből állnak.

| Alapértelmezett jelentés                       | Sor definíciója                       | Oszlopdefiníció             |
|--------------------------------------|--------------------------------------|-------------------------------|
| Mérleg – Alapértelmezett              | Mérleg – Alapértelmezett              | Idei és a Eltérés – Alapértelmezett    |
| Mérleg és kimutatás egymás mellett – alapértelmezett | Mérleg és kimutatás egymás mellett – alapértelmezett | Folyó év mai napig oszlop – Alapértelmezett |

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



## <a name="additional-resources"></a>További erőforrások

[Pénzügyi jelentéskészítés – áttekintés](financial-reporting-getting-started.md)

[Pénzügyi jelentések megtekintése](view-financial-reports.md)

[Dynamics Pénzügyi jelentések blog](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
