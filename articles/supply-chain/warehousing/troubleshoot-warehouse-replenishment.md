---
title: Raktárfeltöltés – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a raktári feltöltési munkákat végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e4d87e85520c2b6f2346fddf3b985d4e17fe35cb
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644873"
---
# <a name="troubleshoot-warehouse-replenishment"></a>Raktárfeltöltés – hibaelhárítás

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet megoldani gyakori problémákat, miközben a raktári feltöltési munkákat végzi a Microsoft Dynamics 365 Supply Chain Management szolgáltatásban.

## <a name="i-receive-the-following-error-message-work-1-cannot-be-unblocked-because-it-has-unfinished-replenishment-work"></a>A következő hibaüzenet jelenik meg: „%1 munkaazonosító nem zárolható, mert befejezetlen feltöltési munkával rendelkezik".

### <a name="issue-description"></a>Probléma leírása

A kitárolási munka a függő feltöltési munka miatt le van zárolva.

### <a name="issue-resolution"></a>Probléma megoldása

Ha a kereslet szerinti feltöltést használja, akkor a rendszer a feltöltési munkát és a kitárolási munkát egyaránt létrehozza, ha a kitárolási helyet fel kell tölteni a forrásrendelés igényének kielégítésére. A kitárolási munkát azonban csak akkor zárolja, ha a feltöltési munka be van fejezve. Ez a viselkedés szándékos, mert a kitárolási hely nem rendelkezik elegendő készlettel, ha a feltöltési munka be van fejezve. Fejezee be a feltöltési munkát, majd dolgozza fel a kitárolási munkát.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]