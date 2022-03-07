---
title: A közvetlenül származtatott megerősített rendeléseket egy Felülvizsgálat alatt állapotú munkafolyamat dolgozza fel
description: A közvetlenül származtatott megerősített rendeléseket egy Felülvizsgálat alatt állapottal rendelkező munkafolyamat dolgozza fel.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: d20f1c1d6e8fc83dd996b04bf0321a41f7b39290f306d1ac9f4fcd17514832e6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6721175"
---
# <a name="directly-derived-firmed-orders-are-processed-by-an-in-review-workflow"></a>A közvetlenül származtatott megerősített rendeléseket egy Felülvizsgálat alatt állapotú munkafolyamat dolgozza fel

Tudásbáziscikk száma: 4612450

## <a name="symptoms"></a>Tünetek

A közvetlenül származtatott megerősített rendeléseket egy *Felülvizsgálat alatt* állapottal rendelkező munkafolyamat dolgozza fel.

## <a name="resolution"></a>Felbontás

Ha a nyomon követés engedélyezve van *Ellenőrzés alatt* állapot lesz hozzárendelve a megerősített származtatott rendelésekhez (alvállalkozói beszerzési rendelések). Ezért ha egy beszerzési rendelés származtatott (alvállalkozói beszerzési rendelés), akkor csak egy munkafolyamatba lesz elküldve. Ha egy beszerzési rendelés egy jóváhagyott tervezett beszerzési rendelés, a rendszer automatikusan jóváhagyja, hogy a tervezési motor ne hozzon létre új tervezett rendeléseket, amíg a beszerzési rendelés Még *Vázlat* állapotú.
