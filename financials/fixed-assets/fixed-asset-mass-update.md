---
title: "Tárgyi eszközök tömeges módosítása"
description: "Ha könyveket használ, akkor egyszerre módosíthatja azoknak az eszközcsoportoknak az értékcsökkenési szabályát, amelyek ugyanahhoz a könyvhöz tartoznak."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3521
ms.assetid: 50207ffb-6b89-4fb9-92e9-928bc0729489
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 55bf62c2a3ad385038763a7fe56ddca048d4847b
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="fixed-asset-mass-update"></a>Tárgyi eszközök tömeges módosítása

[!include[banner](../includes/banner.md)]


Ha könyveket használ, akkor egyszerre módosíthatja azoknak az eszközcsoportoknak az értékcsökkenési szabályát, amelyek ugyanahhoz a könyvhöz tartoznak.

Például ha az Egyesült Államokban tevékenykedik, és a tárgyi eszközök 40 százalékát az év utolsó negyedévében helyezte üzembe, akkor a negyedéven belüli értékcsökkenés szabályát kell alkalmaznia. A tömeges frissítés segítségével minden eszközt módosíthat, amelynek értékcsökkenését az új szabály szerint kell elszámolni. 

Ha frissíti a tárgyi eszközök értékcsökkenési szabályát, akkor ezzel törli ezen eszközök minden értékcsökkenési tranzakcióját. Emellett ezen eszközökre vonatkozóan törli az összes értékcsökkenési helyesbítés tranzakcióit, és a rendkívüli értékcsökkenési tranzakciókat. 

A már kivezetett eszközök értékcsökkenési szabályának frissítéséhez először törölni kell a meglévő kivezetési tranzakciókat. Emellett illetve a kivezetés következtében létrejött egyéb tranzakciókat is törölni kell. 

Az eszközök értékcsökkenési szabályainak frissítése után elszámolhatja az egyes eszközök rendes és soronkívüli értékcsökkenését. Emellett szükség esetén elvégezheti a manuális korrekciókat is.






