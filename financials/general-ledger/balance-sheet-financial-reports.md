---
title: "Mérleg pénzügyi jelentés"
description: "A cikk ismerteti a mérleget alapértelmezett jelentéseket. Bemutatja az építőelemek társított ezeket a jelentéseket is."
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
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 664d32c2bfecb50e24fd48a66ab5b34cef6c09a3
ms.lasthandoff: 03/31/2017


---

# <a name="balance-sheet-financial-reports"></a>Mérleg pénzügyi jelentés

A cikk ismerteti a mérleget alapértelmezett jelentéseket. Bemutatja az építőelemek társított ezeket a jelentéseket is. 

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

 

<a name="see-also"></a>Lásd még
--------

[Financial reporting](financial-reporting-getting-started.md)

[View financial reports](view-financial-reports.md)

[Dynamics pénzügyi jelentési Blog](http://blogs.msdn.com/b/dynamics_financial_reporting/)


