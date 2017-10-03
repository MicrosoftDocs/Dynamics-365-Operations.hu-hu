---
title: "Profilelemzés beállítása"
description: "Ez a témakör bemutatja, hogy miként állíthatók be a vevő Recency, gyakorisági és pénzügyi (RFM) elemzésének."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 78943
ms.assetid: 8ff9aac3-5ada-4150-85fd-18901c926d53
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 1d5deb781d938dd31326826049372f705bdf6938
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017



---

# <a name="set-up-rfm-analysis"></a>Profilelemzés beállítása

[!include[banner](includes/banner.md)]


Ez a témakör bemutatja, hogy miként állíthatók be a vevő Recency, gyakorisági és pénzügyi (RFM) elemzésének.

A Recency, gyakorisági és monetáris (RFM) analízis marketing célokat szolgál, amelyek a szervezet a beszerzések a vevő által generált adatok értékelésére használható. RFM analízis beállítása után vevők lesznek hozzájuk rendelve számított RFM-pontszám beszerzések élnek. Az RFM-pontszám háromjegyű minősítést vagy egy összesített szám, attól függően, hogy hogyan konfigurálta a szervezet az RFM analízis is lehet. Ha a szervezet háromjegyű minősítést használ pontszám ként, az első számjegy a vevő recency minősítése (milyen régen vásárolt a vevő a szervezettől). A második számjegy, a vevő gyakorisági minősítése (milyen gyakran vásárol a vevő a szervezettől). A harmadik számjegy a vevő monetáris minősítése (mennyit költ a vevő, amikor a szervezettől vásárol). Például, a szervezet 1-től 5-ig terjedő skálán határozza meg a minősítést, ahol az 5 a legmagasabb minősítés. Ebben az esetben az 535 vevői minősítés a következő információkat szolgáltatja a vevőről:

-   **5-ös recency minősítés** – a vevőnek nemrég vásárolt.
-   **3-as gyakorisági minősítés** – a vevő mérsékelten gyakran vásárol a szervezettől.
-   **5-ös monetáris minősítés** – amikor a vevő vásárol, akkor jelentős mennyiségű pénzt költ.

Ha a szervezet által használt szám egy összesített szám, az egyes minősítések összeadódnak. A példánál maradva a vevő minősítése 13 (5 + 3 + 5).




