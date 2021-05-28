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
ms.openlocfilehash: d54985707d82df2b947a7cb615fc25f90aa31702
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026583"
---
# <a name="directly-derived-firmed-orders-are-processed-by-an-in-review-workflow"></a>A közvetlenül származtatott megerősített rendeléseket egy Felülvizsgálat alatt állapotú munkafolyamat dolgozza fel

Tudásbáziscikk száma: 4612450

## <a name="symptoms"></a>Tünetek

A közvetlenül származtatott megerősített rendeléseket egy *Felülvizsgálat alatt* állapottal rendelkező munkafolyamat dolgozza fel.

## <a name="resolution"></a>Felbontás

Ha a nyomon követés engedélyezve van *Ellenőrzés alatt* állapot lesz hozzárendelve a megerősített származtatott rendelésekhez (alvállalkozói beszerzési rendelések). Ezért ha egy beszerzési rendelés származtatott (alvállalkozói beszerzési rendelés), akkor csak egy munkafolyamatba lesz elküldve. Ha egy beszerzési rendelés egy jóváhagyott tervezett beszerzési rendelés, a rendszer automatikusan jóváhagyja, hogy a tervezési motor ne hozzon létre új tervezett rendeléseket, amíg a beszerzési rendelés Még *Vázlat* állapotú.
