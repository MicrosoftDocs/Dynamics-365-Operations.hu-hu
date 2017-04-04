---
title: "Navigációs keresés"
description: "Ez a cikk ismerteti a keresés funkció segítségével keresse meg a Microsoft Dynamics 365 műveletek lapjára."
author: aneesmsft
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25991
ms.assetid: eef0676f-c4b1-490e-a032-e9c8580f3fea
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 87fed576f8cf358520d94f5cd5b326ff9801913a
ms.lasthandoff: 03/31/2017


---

# <a name="navigation-search"></a>Navigációs keresés

Ez a cikk ismerteti a keresés funkció segítségével keresse meg a Microsoft Dynamics 365 műveletek lapjára.

365 Dynamics műveletek széles skáláját iparágak és a referenciaegyenesen lehetővé teszi. Az alkalmazás számos területek és a lapok segítségével különböző műveletek végrehajtásához. Gyorsan keresni azokat a lapokat, a feladatok elvégzéséhez szükséges, használja a Keresés funkciót. A funkció használatához kattintson a **Keresés** ikonra a **Keresés** doboz megjelenítéséhez. Ezután gépelhet a mezőbe. A rendszer azonnal felkeresi a kapcsolódó lapokat az alkalmazásban, amik megfelelnek a begépelt szavaknak. Például begépelheti, hogy "szállítói számla", majd a rendszer megjeleníti a megfelelő keresési eredményeket. **Megjegyzés:** A **Keresés** doboz segít a lapok megtalálásában és a navigálásban. Azonban nem nyújt segítséget adatok és műveletek megtalálásához. 

[![keresőmező](./media/search-box.png)](./media/search-box.png) is szolgál a Keresés funkciót egy nagyszerű módja annak, hogy gyorsan navigálhat egy adott lapra. Például, ha egy kötelezettségek adminisztrátor aki gyakran használja a **kifizetési napló** lap, a Keresés mezőbe beírhatjuk a "kifizetési napló". Mivel a bemeneti egyezést a lap címe, az oldal felső részén a keresési eredményekben szerepel, és azt gyorsan navigálhat. 

[![Keresés-a-fizetési-napló](./media/searching-for-payment-journal.png)](./media/searching-for-payment-journal.png) 

A keresési eredmények listáján a lap címe, valamint a navigációs elérési útját jeleníti meg. Ez segíti az alkalmazáson belül annak a bizonyos lapnak a felkutatását. Ennek segítségével különbséget is tehet két vagy több hasonló lap között. Egy lap keresésekor a begépelt karakterek egyeztetve vannak a lap címével, valamint a navigációs útvonallal. Például, ha a "követelés" beviszi a ** ** keresőmező, látni fogja a lapokat a Kinnlevőségek területen – rendelkezésre álló eredményeket annak ellenére, hogy a weblapok címét nem tartalmazzák a szó "követelés". 

[![Keresés-az-a-word-követelés](./media/search-for-the-word-receivable.png)](./media/search-for-the-word-receivable.png) 

Egy felügyeleti és biztonsági szempont a Navigálás funkció csak felületek keresése:

-   Azokat a lapokat, amik engedélyezve vannak a jelenlegi konfigurációban (konfigurációs gombok segítségével).
-   Azokat a lapokat, amikhez a felhasználó a szerepköre alapján hozzáféréssel rendelkezik.

A keresési eredmények lista 10 cikkre van korlátozva. Ha az eredmények között nem találja, amit keres, próbálja meg finomítani vagy frissíteni a keresés paramétereit. Fejlesztői szempontból a navigációs keresés funkcionalitását könnyű emelni, mivel virtuálisan nincs késleltetés a menüelemek telepítése és a keresési eredményekben való megjelenítése között. Mindaddig, amíg a menüelemek a navigációs ablakhoz vagy az irányítópulthoz vannak kapcsolva, automatikusan kereshetőek lesznek. A navigációs keresés funkcióban elérhető, a kiemelt felhasználók által sokat kért funkció: a műszaki űrlap alapján történő, gyors navigálás egy bizonyos laphoz. Néhány felhasználó annyira rutinosan használja a rendszert, hogy tudják a pontos nevét az aktuálisan használt űrlapnak. Ha Ön egy, ezen felhasználók közül, begépelheti, hogy **Űrlap:**, majd rögtön utána a keresett űrlap nevét. Ha például Ön megadja, hogy **Űrlap: vendinvoice**, az eredmény az összes olyan lapot megjeleníti, ahol az űrlap neve a **vendinvoice** szóval kezdődik. 

[![Keresés az űrlap vendinvoice](./media/search-for-form-vendinvoice.png)](./media/search-for-form-vendinvoice.png)


