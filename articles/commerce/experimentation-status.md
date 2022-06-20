---
title: Kísérlet állapotának áttekintése
description: Ez a cikk bemutatja, hogy milyen állapotú a kísérlet a következőben:Dynamics 365 Commerce
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 818435a7c901d2a6b876b9c9db27faffc8b322fc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877249"
---
# <a name="review-the-status-of-an-experiment"></a>Kísérlet állapotának áttekintése
A kísérletek Dynamics 365 Commerce rendszerben való beállítása és futtatása számos lépést igényel. A kísérletezési életciklussal kapcsolatos tudnivalókért lásd: [Kísérletezés a Dynamics 365 Commerce rendszerben](experimentation-overview.md).

Ha meg szeretné tudni, hol tart egy kísérlet az életciklusban, a Commerce webhelykészítőben lépjen a **Kísérletek** fülre a bal oldali navigációs panelen. A kísérletek listája az egyes kísérletek állapotával együtt megjelenik a Commerce modulban és a kísérletek létrehozásához, változatok hozzárendeléséhez és adatok elemzésére használt harmadik fél szolgáltatásban is.

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

[ ![Kísérletezés állapotai.](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)


[!INCLUDE[footer-include](../includes/footer-banner.md)]