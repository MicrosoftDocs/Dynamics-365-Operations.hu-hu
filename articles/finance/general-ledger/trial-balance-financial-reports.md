---
title: Főkönyvi kivonat pénzügyi jelentés
description: Ez a cikk a főkönyvi kivonatok alapértelmezett jelentéseit mutatja be. Ismerteti továbbá azokat az építőelemeket, amelyek ezekhez a jelentésekhez kapcsolódnak, illetve beszámol arról, hogy miként módosíthatja a jelentéseket, hogy azok megfeleljenek az üzleti követelményeinek.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1b48510febf5a5f9f4a01728b242d9750b3c62c2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4443827"
---
# <a name="trial-balance-financial-reports"></a>Főkönyvi kivonat pénzügyi jelentés

[!include [banner](../includes/banner.md)]

Ez a cikk a főkönyvi kivonatok alapértelmezett jelentéseit mutatja be. Ismerteti továbbá azokat az építőelemeket, amelyek ezekhez a jelentésekhez kapcsolódnak, illetve beszámol arról, hogy miként módosíthatja a jelentéseket, hogy azok megfeleljenek az üzleti követelményeinek. 

<a name="default-trial-balance-reports"></a>Alapértelmezett főkönyvi kivonat jelentés
-----------------------------

A Pénzügyi jelentéskészítésben három főkönyvi kivonatra vonatkozó jelentés áll rendelkezésre.

| Alapértelmezett jelentés                                 | Mire szolgál?                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Részletes főkönyvi kivonat – Alapértelmezett               | Egyenleginformációkat ad minden olyan számlához, amely hitel- vagy bankkártya egyenleggel rendelkezik, valamint ezen egyenlegek nettó értéke, a tranzakció dátumával, a bizonylattal és a napló leírással együtt.                  |
| Összegző főkönyvi kivonat – Alapértelmezett                | Egyenleg-adatokat ad az összes számlához, amelyekhez nyitó és záró egyenleg tartozik, hitel- vagy bankkártya egyenleggel rendelkeznek nettó eltéréssel.                                        |
| Éves összegző főkönyvi kivonat – Alapértelmezett | Az egyenleg-adatokat ad az összes olyan számlához, amelyekhez nyitó és záró egyenleg tartozik, hitel- vagy bankkártya egyenleggel rendelkeznek nettó eltéréssel. |

## <a name="building-blocks"></a>Építőelemek
A főkönyvi kivonat pénzügyi jelentések a következő építőelemekből állnak.

| Alapértelmezett jelentés                                 | Sor definíciója          | Oszlopdefiníció                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| Részletes főkönyvi kivonat – Alapértelmezett               | Főkönyvi kivonat – Alapértelmezett | Részletes főkönyvi kivonat – Alapértelmezett               |
| Összegző főkönyvi kivonat – Alapértelmezett                | Főkönyvi kivonat – Alapértelmezett | Összegző főkönyvi kivonat – Alapértelmezett                |
| Éves összegző főkönyvi kivonat – Alapértelmezett | Főkönyvi kivonat – Alapértelmezett | Éves összegző főkönyvi kivonat – Alapértelmezett |

### <a name="row-definition"></a>Sor definíciója

A sordefiníció, Főkönyvi kivonat – Alapértelmezett, egy sort tartalmaz, amely behúzza az összes fő számlát. Ezért bárki létrehozhat jelentést anélkül, hogy módosításokat végezne. A jelentés megtekintésekor, láshat egy sorhoz, az egyes számlák részleteinek megtekintéséhez. Módosíthatja a sordefiníciót, hogy további részleteket tartalmazzon. A főkönyvi kivonat módosítása – Alapértelmezett sordefiníció, ezért tartalmazza az összes számla sorait, kövesse az alábbi lépéseket.

1.  Kattintson a **Szerkesztés** lehetőségre, majd kattintson a **Sorok beszúrása dimenziókból** elemre. A **Sorok beszúrása dimenziókból** parancs segítségével kiválaszthatja, milyen dimenziókat szeretne a sordefiníciójában. Ehhez a sordefinícióhoz a **Fő számlát** fogja használni.
2.  Győződjön meg róla, hogy a **Fő számla** tartalmaz minden és-jelet (&), majd kattintson az **OK** gombra.

A sordefiníció most tartalmazza az alapértelmezett jogi személy minden fő számláját.

### <a name="column-definition"></a>Oszlopdefiníció

Minden egyes főkönyvi kivonati jelentés külön oszlopdefiníciót használ. Ezek az oszlopdefiníciók tartalmaznak különböző típusú oszlopokot, a különböző szintű részletességre és pénzügyi adatokra.

-   **Részletes főkönyvi kivonat – Alapértelmezett oszloptípusok:**
    -   **DESC** – A leírás a sordefinícióból
    -   **ACCT** – Számlakódok
    -   **ATTR (3)** – Attribútumok:
        -   Tranzakció dátuma
        -   Bizonylat
        -   Napló leírása
    -   **FD** – Csak kötelezettségeket tartalmazó pénzügyi adat
    -   **FD** – Csak jóváírásokat tartalmazó pénzügyi adat
    -   **CALC** – Nettó eltérés
-   **Összesítő főkönyvi kivonat – Alapértelmezett oszloptípusok:**
    -   **ACCT** – Számlakódok
    -   **DESC** – A leírás a sordefinícióból
    -   **ATTR** – Egy attribútum:
        -   Bizonylat
    -   **FD** – A pénzügyi adatok kezdőegyenlege
    -   **FD** – Csak kötelezettségeket tartalmazó pénzügyi adat
    -   **FD** – Csak jóváírásokat tartalmazó pénzügyi adat
    -   **CALC** – Nettó eltérés
    -   **CALC** – Záró egyenleg
-   **Éves összegző főkönyvi kivonat – Alapértelmezett:**
    -   **ACCT** – Számlakódok
    -   **DESC** – A leírás a sordefinícióból
    -   **ATTR** – Egy attribútum
        -   Bizonylat
    -   **FD** – A folyó év kezdő egyenleg pénzügyi adata
    -   **FD** – A folyó évre csak kötelezettségeket tartalmazó pénzügyi adatok
    -   **FD** – A folyó évre csak jóváírásokat tartalmazó pénzügyi adatok
    -   **CALC** – Nettó eltérés
    -   **CALC** – Záró egyenleg
    -   **FD** – A előző évre csak kötelezettségeket tartalmazó pénzügyi adatok
    -   **FD** – A előző évre csak jóváírásokat tartalmazó pénzügyi adatok



<a name="additional-resources"></a>További erőforrások
--------

[Pénzügyi jelentéskészítés – áttekintés](financial-reporting-getting-started.md)

[Pénzügyi jelentések megtekintése](view-financial-reports.md)

[Dynamics Pénzügyi jelentések blog](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]