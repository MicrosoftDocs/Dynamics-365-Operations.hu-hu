---
title: Kísérlet állapotának áttekintése
description: Ez a témakör azt mutatja be, hogy a Dynamics 365 Commerce rendszeren belüli kísérletezési életciklusban mi lehet egy adott kísérlet állapota.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 097206c0aa487e14499bdf3907465e17b7d337e2
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930209"
---
# <a name="review-the-status-of-an-experiment"></a>Kísérlet állapotának áttekintése
A kísérletek Dynamics 365 Commerce rendszerben való beállítása és futtatása számos lépést igényel. A kísérletezési életciklussal kapcsolatos tudnivalókért lásd: [Kísérletezés a Dynamics 365 Commerce rendszerben](experimentation-overview.md).

Ha meg szeretné tudni, hol tart egy kísérlet az életciklusban, lépjen a **Kísérletek** fülre a webhelykészítőben. A kísérletek listája az egyes kísérletek állapotával együtt megjelenik a Commerce modulban és a kísérletek létrehozásához, változatok hozzárendeléséhez és adatok elemzésére használt harmadik fél szolgáltatásban is.

A **Commerce állapot** oszlopban a következő értékek jelenhetnek meg. 
- **Piszkozat** – A kísérletet egy Commerce modulon belüli oldalhoz vagy töredékhez csatlakoztatták, és éppen a szerkesztése tart.
- **Közzétéve** – A kísérlet változatai készen állnak a webhelyen való megjelenítésre. Ha a kísérlet a harmadik féltől származó szolgáltatásban fut, akkor a webhely felhasználói az oldal vagy töredék harmadik fél szolgáltatás által kiválasztott változatát láthatják.
- **Nem közzétett** – A kísérlet már nem érhető el a webhelyen. A webhely felhasználói csak az oldal vagy töredék alapértelmezett változatát láthatják, ha a kísérlet harmadik fél szolgáltatásban fut.
- **Befejezett** – A kísérlet végbement, és a változatot élő állapotba léptették elő a webhely összes felhasználója számára.

Hasonlóképpen a **Harmadik fél állapot** oszlopban a következő értékek jelenhetnek meg annak jelzésére, hogy milyen állapotúak a kísérletek a harmadik fél szolgáltatásban.
- **Piszkozat** – A kísérletet a harmadik fél szolgáltatásban beállították, de még nem indították el.
- **Fut** – A kísérletet elindították a harmadik fél szolgáltatásban, és éppen adatokat gyűjt.
- **Szüneteltetve** – A kísérlet szüneteltetve van, és nem gyűjt adatokat. A kísérletet folytatnia kell ahhoz, hogy újra elkezdjen adatokat gyűjteni.
- **Archivált** – A kísérlet végbement, és későbbi kikereshetőség érdekében katalogizálták a harmadik fél szolgáltatásban.

Az alábbi ábra a két állapotot mutatja be, valamint azt, hogy hogyan kapcsolódnak egymáshoz.

[ ![Kísérletezés állapotai](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)
