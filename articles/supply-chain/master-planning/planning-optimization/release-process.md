---
title: Tervezési optimalizálás kiadási folyamata és kiadási előzmények
description: Ez a témakör a tervezési optimalizálás kiadási folyamatához és kiadási előzményeihez nyújt tájékoztatást.
author: crytt
ms.date: 8/17/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: fcd18341629afcf3092a457ae711e27b0bbfeb2a
ms.sourcegitcommit: 03f53980a4bc67b73ac2be76a3b3e7331d0db705
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/18/2021
ms.locfileid: "7394414"
---
# <a name="planning-optimization-release-process-and-release-history"></a>Tervezési optimalizálás kiadási folyamata és kiadási előzmények

[!include [banner](../../includes/banner.md)]

A Microsoft havonta frissíti a Tervezési optimalizálást. Az üzleti követelmények alapján azonban időnként további frissítéseket adunk ki az ütemezett kiadások között.

Minden kiadás közzé van téve az egyes régiókban, ahol a Tervezési optimalizálás elérhető. A folyamat általában három napig tart.

A Tervezési optimalizálás frissítése közben előfordulhat, hogy az alaptervezés egy kissé lassabban fut a szokásosnál.

A Tervezési optimalizálást használt környezetek automatikusan a legújabb kiadást kapják meg. Nincs szükség felhasználói műveletre: a szolgáltatás automatikusan frissül. Kompatibilitástörő változás azonban soha nem kerül automatikusan környezetbe. Alapértelmezés szerint a kompatibilitástörő változásnak tekintett módosításokat kifejezetteb engedélyezni kell a [funkciókezelés](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) segítségével. Ezek a változtatások tehát csak akkor jelennek meg környezetben, ha úgy dönt, hogy engedélyezi azokat.

Mivel az értesítések nem jelennek meg, amikor a környezetben frissítik a Tervezési optimalizálást, az alábbi táblázat kiadási megjegyzései alapján megtudhatja, hogy mikor adták ki a módosításokat, és milyen funkciókat tartalmaznak. Ez a táblázat mutatja be a Tervezési optimalizálásra kiadott módosításokat, azt, hogy ezek a változtatások funkciókezelésből származó funkcióhoz vannak-e társítva, valamint a kiadás dátumát.

| Változások | Funkciókezelés részletei | Kiadás dátuma |
|---|---|---|
| <p>A tervezett megrendelésekhez hozzáadtuk **az átfutási idő** mezőt.</p><p>Általános teljesítmény-, minőség- és stabilitásjavítások.</p> | Nincs szükség funkciókezelésre. | 2021. augusztus 16. |
| <p>A végtelen kapacitású ütemezéshez hozzáadott erőforrás-típuskövetelmények.</p><p>Javított erőforrás- és naptárhatékonyság végtelen kapacitású ütemezés esetén.</p><p>További tájékoztatás: [Ütemezés végtelen kapacitással](infinite-capacity-planning.md). | <p>A funkciókezelésben a 10.0.20 verziótól elérhető.</p><p>Funkció neve: *Végtelen kapacitásütemezés a tervezési optimalizáláshoz*</p> | 2021. július 6. |
| Általános minőségjavítás. | Nincs szükség funkciókezelésre. | 2021. július 6. |

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]