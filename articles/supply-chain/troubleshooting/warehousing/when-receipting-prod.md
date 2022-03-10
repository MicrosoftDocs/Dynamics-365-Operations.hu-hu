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
ms.openlocfilehash: cf307964a07c2b69eb5e4ef2cf9dc094482736d0970e333e84f674c9be6331c7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740527"
---
# <a name="only-one-label-is-printed-for-multiple-work-headers-on-a-single-receipt"></a>Egyetlen nyugta több munkafejlécéhez csak egy címke van nyomtatva

Tudásbáziscikk száma: 4614667

## <a name="symptoms"></a>Tünetek

Több munkafejléc jön létre ugyanahhoz a cél azonosítótáblához egy raktári alkalmazás bevételi eseményeként. Ugyanakkor a termék érkezésekor, csak egy táblacímke kerül nyomtatásra.

## <a name="resolution"></a>Felbontás

A rendszer úgy viselkedik, ahogy tervezték.

A jelenlegi kialakításban mindig egyetlen táblacímke jön létre, függetlenül a meglévő munkafejléc- és munkasorkombinációk számától. A létrehozott címke csak egy kombináció adatait tartalmazza.

A probléma megoldásához győződjön meg róla, hogy a munkafejléc létrehozása mindig csak egy célt azonosítótáblához van hozzárendelve.
