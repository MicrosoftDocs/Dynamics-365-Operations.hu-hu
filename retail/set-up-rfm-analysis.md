---
title: "Profilelemzés beállítása"
description: "Ez a témakör bemutatja, hogy miként állíthatók be a vevő Recency, gyakorisági és pénzügyi (RFM) elemzésének."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 78943
ms.assetid: 8ff9aac3-5ada-4150-85fd-18901c926d53
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: b95d2c4d7d78e8c5ed8d3a04efdd2f8dfe8393ba
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-rfm-analysis"></a>Profilelemzés beállítása

[!include[banner](includes/banner.md)]


Ez a témakör bemutatja, hogy miként állíthatók be a vevő Recency, gyakorisági és pénzügyi (RFM) elemzésének.

A Recency, gyakorisági és monetáris (RFM) analízis marketing célokat szolgál, amelyek a szervezet a beszerzések a vevő által generált adatok értékelésére használható. RFM analízis beállítása után vevők lesznek hozzájuk rendelve számított RFM-pontszám beszerzések élnek. Az RFM-pontszám háromjegyű minősítést vagy egy összesített szám, attól függően, hogy hogyan konfigurálta a szervezet az RFM analízis is lehet. Ha a szervezet háromjegyű minősítést használ pontszám ként, az első számjegy a vevő recency minősítése (milyen régen vásárolt a vevő a szervezettől). A második számjegy, a vevő gyakorisági minősítése (milyen gyakran vásárol a vevő a szervezettől). A harmadik számjegy a vevő monetáris minősítése (mennyit költ a vevő, amikor a szervezettől vásárol). Például, a szervezet 1-től 5-ig terjedő skálán határozza meg a minősítést, ahol az 5 a legmagasabb minősítés. Ebben az esetben az 535 vevői minősítés a következő információkat szolgáltatja a vevőről:

-   **5-ös recency minősítés** – a vevőnek nemrég vásárolt.
-   **3-as gyakorisági minősítés** – a vevő mérsékelten gyakran vásárol a szervezettől.
-   **5-ös monetáris minősítés** – amikor a vevő vásárol, akkor jelentős mennyiségű pénzt költ.

Ha a szervezet által használt szám egy összesített szám, az egyes minősítések összeadódnak. A példánál maradva a vevő minősítése 13 (5 + 3 + 5).




