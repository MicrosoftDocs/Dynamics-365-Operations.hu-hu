---
title: "A tároló tömegének és térfogatának feltüntetése a rakományon"
description: "Ez a témakör a tároló tömegének és térfogatának feltüntetése a rakományon funkció beállítását és alkalmazását írja le."
author: pjacobse
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: b137db6f67da30d6ac3a973940c1df1fd7268a1a
ms.openlocfilehash: ac1df9b430feb025e4a544a7ecd7baa0c919cbe4
ms.contentlocale: hu-hu
ms.lasthandoff: 10/02/2017

---

# <a name="include-container-weight-and-volume-on-load"></a>A tároló tömegének és térfogatának feltüntetése a rakományon

[!include[banner](../includes/banner.md)]

A tároló tömegének és térfogatának feltüntetése a rakományon funkció világosan jelzi a rakományba bekerülő tárolók összsúlyát és térfogatát.

A rakomány egyetlen szállítmányt vagy több szállítmányt tartalmaz, és ezek a szállítmányok egy vagy több értékesítési rendeléshez tartozó egyedi cikkeket tartalmaznak. A cikkek tárolása tárolón belül történik, a tárolókat rakományba töltjük be. A rakomány tárolón kívüli cikkeket is tartalmazhat. Ezek a feltételek alapján a rendszer kiszámítja a rakomány súlyát és térfogatát, figyelembe véve a tárolók és a cikkek mennyiségét és súlyát egyaránt.

Ha a számított értékek nem pontosak, módosíthatja őket – írja be a rakomány súlyának és térfogatának tényleges értékét. A súly és térfogat értéke szállításkezelő folyamatokban használatos. Például az értékek szerepelnek a díj és útvonal munkaterületen, ahol segítségével meghatározható a rakományok díja és útvonala, illetve használatos szállítási ajánlatoknál és járművezetői bejelentkezéseknél is.

## <a name="where-it-applies"></a>Alkalmazási kör

A tároló tömegének és térfogatának feltüntetése a rakományon funkció a szállításkezelési folyamatokra vonatkozik, például a díj és útvonal munkaterületen, szállítási ajánlatoknál és járművezetők bejelentkezésénél.

## <a name="how-it-is-set-up"></a>Hogyan van beállítva

A rakománynál figyelembe veendő tárolók számának kiszámítása a tároló súlya és térfogata és a tároló százalékos kihasználtsága alapján történik.

-   A tároló súlyának és térfogatának beállításához kattintson **Raktárkezelés** \> **Beállítás** \> **Tárolók** \> **Tárolótípusok** elemre.

-   A tároló százalékos kihasználtsága beállításához kattintson a **Raktárkezelés** \> **Beállítás** \> **Tárolók** \> **Tárolócsoportok** elemre, majd írjon be egy értéket a **Tároló százalékos kihasználtsága** mezőbe.

