---
title: "Tárgyi eszközök tömeges módosítása"
description: "Ha könyveket használ, akkor egyszerre módosíthatja azoknak az eszközcsoportoknak az értékcsökkenési szabályát, amelyek ugyanahhoz a könyvhöz tartoznak."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3521
ms.assetid: 50207ffb-6b89-4fb9-92e9-928bc0729489
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: a16bae8f13dd53b5bbe380f03f6ca399bd6dbd9a
ms.contentlocale: hu-hu
ms.lasthandoff: 05/25/2017


---

# <a name="fixed-asset-mass-update"></a>Tárgyi eszközök tömeges módosítása

[!include[banner](../includes/banner.md)]


Ha könyveket használ, akkor egyszerre módosíthatja azoknak az eszközcsoportoknak az értékcsökkenési szabályát, amelyek ugyanahhoz a könyvhöz tartoznak.

Például ha az Egyesült Államokban tevékenykedik, és a tárgyi eszközök 40 százalékát az év utolsó negyedévében helyezte üzembe, akkor a negyedéven belüli értékcsökkenés szabályát kell alkalmaznia. A tömeges frissítés segítségével minden eszközt módosíthat, amelynek értékcsökkenését az új szabály szerint kell elszámolni. 

Ha frissíti a tárgyi eszközök értékcsökkenési szabályát, akkor ezzel törli ezen eszközök minden értékcsökkenési tranzakcióját. Emellett ezen eszközökre vonatkozóan törli az összes értékcsökkenési helyesbítés tranzakcióit, és a rendkívüli értékcsökkenési tranzakciókat. 

A már kivezetett eszközök értékcsökkenési szabályának frissítéséhez először törölni kell a meglévő kivezetési tranzakciókat. Emellett illetve a kivezetés következtében létrejött egyéb tranzakciókat is törölni kell. 

Az eszközök értékcsökkenési szabályainak frissítése után elszámolhatja az egyes eszközök rendes és soronkívüli értékcsökkenését. Emellett szükség esetén elvégezheti a manuális korrekciókat is.






