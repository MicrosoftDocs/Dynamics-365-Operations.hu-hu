---
title: Egyetlen nyugta több munkafejlécéhez csak egy címke van nyomtatva
description: Egyetlen nyugta több munkafejlécéhez csak egy címke van nyomtatva.
author: perlynne
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8e11dc918eb3c9085018d15b43819522cc8bebe3
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026574"
---
# <a name="only-one-label-is-printed-for-multiple-work-headers-on-a-single-receipt"></a>Egyetlen nyugta több munkafejlécéhez csak egy címke van nyomtatva

Tudásbáziscikk száma: 4614667

## <a name="symptoms"></a>Tünetek

Több munkafejléc jön létre ugyanahhoz a cél azonosítótáblához egy raktári alkalmazás bevételi eseményeként. Ugyanakkor a termék érkezésekor, csak egy táblacímke kerül nyomtatásra.

## <a name="resolution"></a>Felbontás

A rendszer úgy viselkedik, ahogy tervezték.

A jelenlegi kialakításban mindig egyetlen táblacímke jön létre, függetlenül a meglévő munkafejléc- és munkasorkombinációk számától. A létrehozott címke csak egy kombináció adatait tartalmazza.

A probléma megoldásához győződjön meg róla, hogy a munkafejléc létrehozása mindig csak egy célt azonosítótáblához van hozzárendelve.
