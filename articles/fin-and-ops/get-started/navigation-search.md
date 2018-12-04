---
title: "Navigációs keresés"
description: "A témakör ismerteti, hogy hogyan navigálhat a Microsoft Dynamics 365 for Finance and Operations lapjaihoz a kereső funkció használatával."
author: aneesmsft
manager: AnnBe
ms.date: 04/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 25991
ms.assetid: eef0676f-c4b1-490e-a032-e9c8580f3fea
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: be4ed89982e27d9b46a83bc945d7cd99ef892fbe
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="navigation-search"></a>Navigációs keresés

[!include [banner](../includes/banner.md)]

A témakör ismerteti, hogy hogyan navigálhat a Microsoft Dynamics 365 for Finance and Operations lapjaihoz a kereső funkció használatával.

A Finance and Operations programban számos különböző ágazathoz és szektorhoz tartozó funkció érhető el. Az alkalmazás számos területe és lapja segít a különböző feladatok elvégzésében. A feladatokhoz szükséges lapok gyors megtalálásához használja a navigációs keresés funkciót. 

A funkció használatához kattintson a **Keresés** ikonra a **Keresés** doboz megjelenítéséhez. Ezután gépelhet a mezőbe. A rendszer azonnal felkeresi a kapcsolódó lapokat az alkalmazásban, amik megfelelnek a begépelt szavaknak. Például begépelheti, hogy "szállítói számla", majd a rendszer megjeleníti a megfelelő keresési eredményeket. 

**Megjegyzés:** A **Keresés** doboz segít a lapok megtalálásában és a navigálásban. Azonban nem nyújt segítséget adatok és műveletek megtalálásához. 

[![keresőmező](media/navigation-search.png "Keresőmező") 

## <a name="quickly-navigate-to-a-particular-page"></a>Gyors navigáció adott oldalhoz
A navigációs keresés funkció nagyszerű lehetőséget biztosít egy adott lapra történő gyors navigálásra. Például ha Ön egy kötelezettségekért felelős adminisztrátor, aki gyakran használja a **Kifizetési napló** oldalt, begépelheti a „kifizetési napló” szavakat a **Keresés** mezőbe. Mivel pontosan beírta a keresett oldal címét, az oldal az eredmények tetején jelenik meg, így azonnal odanavigálhat. 

A keresés eredménye megjeleníti mind az oldal címét, mind pedig a navigációs útvonalat. Az alkalmazásban lévő oldal helyét jeleníti meg. Ennek segítségével különbséget is tehet két vagy több hasonló lap között. 

Egy lap keresésekor a begépelt karakterek egyeztetve vannak a lap címével, valamint a navigációs útvonallal. Például ha a begépeli a „kinnlevőségek" szót a **Keresés** mezőbe, az eredmények a Kinnlevőségek területen elérhető lapokat is megjelenítik – még akkor is, ha a „kinnlevőségek" szó nem is szerepelt a lapok címeiben. 

## <a name="quickly-navigate-to-a-page-based-on-the-technical-form-name"></a>Gyors navigálás egy bizonyos laphoz a műszaki űrlap neve alapján
A navigációs keresés funkcióban elérhető, a kiemelt felhasználók által sokat kért funkció: a műszaki űrlap alapján történő, gyors navigálás egy bizonyos laphoz. Néhány felhasználó annyira rutinosan használja a rendszert, hogy tudják a pontos nevét az aktuálisan használt űrlapnak. Ha Ön egy, ezen felhasználók közül, begépelheti, hogy **Űrlap:**, majd rögtön utána a keresett űrlap nevét. Ha például Ön megadja, hogy **Űrlap: vendinvoice**, az eredmény az összes olyan lapot megjeleníti, ahol az űrlap neve a **vendinvoice** szóval kezdődik. 

## <a name="administration-and-security"></a>Adminisztráció és biztonság
Adminisztrációs és biztonsági szempontból a navigációs keresés csak kétféle találatot jelenít meg:

-   Azokat a lapokat, amik engedélyezve vannak a jelenlegi konfigurációban (konfigurációs gombok segítségével).
-   Azokat a lapokat, amikhez a felhasználó a szerepköre alapján hozzáféréssel rendelkezik.

A keresési eredmények lista 10 cikkre van korlátozva. Ha az eredmények között nem találja, amit keres, próbálja meg finomítani vagy frissíteni a keresés paramétereit. 

## <a name="development"></a>Fejlesztés 
Fejlesztői szempontból a navigációs keresés funkcionalitását egyszerű javítani, mivel virtuálisan nincs késleltetés a menüelemek telepítése és a keresési eredményekben való megjelenítése között. Mindaddig, amíg a menüelemek a navigációs ablakhoz vagy az irányítópulthoz vannak kapcsolva, automatikusan kereshetőek lesznek. 

