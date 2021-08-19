---
title: Rakománysablonok
description: Ez a témakör leírja a rakománysablonok beállításának és új rakományhoz való hozzárendelésének folyamatát.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 35e858970114224fe6c4dabf05675d1204b8fd49c3147dab5b8758ab3de47f5a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6745430"
---
# <a name="load-templates"></a>Rakománysablonok

Új rakomány létrehozásakor hozzárendelhet egy rakománysablont. A rakománysablon információkat tartalmaz a berendezésekről, valamint az olyan mértékekről, mint a rakomány magassága, szélessége, mélysége és térfogata.

Ez a témakör leírja a rakománysablonok beállításának és új rakományhoz való hozzárendelésének folyamatát.

## <a name="set-up-a-load-template"></a>Rakománysablon beállítása

1. Lépjen a **Szállításkezelés \> Beállítás \> Rakomány-összeállítás \> Rakománysablon** pontra.
1. A művelet ablakban válassza az **Új** lehetőséget új sablon hozzáadásához, vagy a **Szerkesztés** lehetőséget egy meglévő sablon szerkesztéséhez.
1. Az új vagy meglévő sablon sorában állítsa be a következő mezőket:

    - **Rakománysablon azonosítója** – Írja be a rakománysablon egyedi azonosítóját.
    - **Berendezés** – Válassza ki a rakomány szállításához használandó berendezést.
    - **Rakomány magassága**, **Rakomány szélessége** és **Rakomány mélysége** – Adja meg a rakomány méreteit.
    - **Rakomány max. megengedett térfogata** és **Rakomány max. megengedett súlya** – Adja meg a rakomány megengedett legnagyobb térfogatát és súlyát.
    - **Legnagyobb megengedett bruttó tömeg** – Adja meg a rakomány megengedett legnagyobb bruttó tömegét. A rakomány bruttó tömege magába foglalja a göngyöleg súlyát és a raksúlyt is.
    - **A megengedett fuvardarabok maximális száma** – Adja meg a rakomány által tartalmazható fuvardarabok maximális számát.
    - **Rakomány halmozása a padlón** – Jelölje be ezt a jelölőnégyzetet a padlóra rakodás használatához. Padlószinti rakodás esetben a dobozok padlótól mennyezetig, faltól falig töltik ki a tárolót, hogy optimálisan kihasználják annak kapacitását.

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

## <a name="associate-a-load-template-with-a-new-load"></a>Rakománysablon társítása egy új rakományhoz

1. Ugorjon a **Szállításkezelés \> Tervezés \> Rakománytervező munkaterület** elemre.
1. A lap felső részén válasszon az alábbi lapok egyikéből, attól függően, hogy milyen típusú forrásbizonylathoz hoz létre rakományt: **Szállítások**, **Értékesítési sorok**, **Átmozgatási sorok** vagy **Beszerzésirendelés-sorok**. 
1. Válassza ki azt a dokumentumot, amelyhez a rakományt meg szeretné tervezni.
1. A műveleti ablaktáblán a **Kínálat és kereslet** lapon, a **Hozzáadás** csoportban válassza az **Új rakományba** elemet.
1. A **Rakománysablon** párbeszédpanelen, a **Rakománysablon azonosítója** mezőben válassza ki az alkalmazni kívánt sablont.
1. A sablon alkalmazásához kattintson az **OK** gombra.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]