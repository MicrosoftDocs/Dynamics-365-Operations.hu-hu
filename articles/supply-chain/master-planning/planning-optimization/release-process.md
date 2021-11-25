---
title: Tervezési optimalizálás kiadási folyamata és kiadási előzmények
description: Ez a témakör a tervezési optimalizálás kiadási folyamatához és kiadási előzményeihez nyújt tájékoztatást.
author: ChristianRytt
ms.date: 09/21/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: b2e0145c28b40f4fbfb54ad7e7ed32fbc130c569
ms.sourcegitcommit: 8afd0cdb39ec443fb7631c39401967cce0fac34e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/01/2021
ms.locfileid: "7727432"
---
# <a name="planning-optimization-release-process-and-release-history"></a>Tervezési optimalizálás kiadási folyamata és kiadási előzmények

[!include [banner](../../includes/banner.md)]

A Microsoft havonta frissíti a Tervezési optimalizálást. Az üzleti követelmények alapján azonban időnként további frissítéseket adunk ki az ütemezett kiadások között.

Minden kiadás közzé van téve az egyes régiókban, ahol a Tervezési optimalizálás elérhető. A folyamat általában három napig tart.

A Tervezési optimalizálás frissítése közben előfordulhat, hogy az alaptervezés egy kissé lassabban fut a szokásosnál.

A Tervezési optimalizálást használt környezetek automatikusan a legújabb kiadást kapják meg. Nincs szükség felhasználói műveletre: a szolgáltatás automatikusan frissül. Kompatibilitástörő változás azonban soha nem kerül automatikusan környezetbe. Alapértelmezés szerint a kompatibilitástörő változásnak tekintett módosításokat kifejezetteb engedélyezni kell a [funkciókezelés](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) segítségével. Ezek a változtatások tehát csak akkor jelennek meg környezetben, ha úgy dönt, hogy engedélyezi azokat.

Mivel az értesítések nem jelennek meg, amikor a környezetben frissítik a Tervezési optimalizálást, az alábbi táblázat kiadási megjegyzései alapján megtudhatja, hogy mikor adták ki a módosításokat, és milyen funkciókat tartalmaznak. Ez a táblázat mutatja be a Tervezési optimalizálásra kiadott módosításokat, azt, hogy ezek a változtatások funkciókezelésből származó funkcióhoz vannak-e társítva, valamint a kiadás dátumát.

| Változások | Funkciókezelés részletei | Kiadási dátumok |
|---|---|---|
| <p>A program támogatja a számítási képleteket, az átfedésben található termelési útvonalat és a követelménytranzakciók termelési műveletének számát.</p><p>Nem található továbbfejlesztett hibaüzenet a termelés ütemezéséhez az időtúllépés, a kapacitás és a ciklikus útvonal egymáshoz kapcsolódóan.</p><p>Jobb konzisztencia a tervezett rendelések és a visszaeső rendelések kézhezvételi dátumának és kiadási dátumának számításakor.</p><p>Általános teljesítmény-, minőség- és stabilitásjavítások. | Funkció neve: *Végtelen kapacitásütemezés a tervezési optimalizáláshoz* | 2021. október 22. 27. |
| <p>Segítséget adott a selejtszázalék figyelembe venni a feldolgozási idő számításában.</p><p>Az ütemezés során a műveletszám és az anyagfelhasználás támogatással tért vissza. | Funkció neve: *Végtelen kapacitásütemezés a tervezési optimalizáláshoz* | 2021. október 5.7. |
| <p>Hozzáadva a termelési útvonal feladattípusához: **Várakozás** előtte, **Várakozás utána és** Szállítási **idő**.</p><p>Általános teljesítmény-, minőség- és stabilitásjavítások. | Funkció neve: *Végtelen kapacitásütemezés a tervezési optimalizáláshoz* | 2021. szeptember 25.30. |
| <p>Az alaptervek támogatása, ha a **Műveletek ütemezése** beállítása *Műveletek ütemezése*.</p><p>Az **Útvonalcsoportok** lapon tiszteletben tartja az **Aktiválás**, **Munkaidő** és **Kapacitás** jelölőmezőket az **Útvonal/munka típusa** vagy *Beállítás* vagy *Folyamat* értékkel rendelkező sorokhoz. </p><p>Általános teljesítmény-, minőség- és stabilitásjavítások. | <p>A műveltek ütemezése a funkciókezelésben a 10.0.20 verziótól elérhető.</p><p>Funkció neve: *Végtelen kapacitásütemezés a tervezési optimalizáláshoz*</p>  | 2021. szeptember 9–17. |
| Általános teljesítmény-, minőség- és stabilitásjavítások. | Nincs szükség funkciókezelésre. | 2021. augusztus 25–30. |
| <p>A tervezett megrendelésekhez hozzáadtuk **az átfutási idő** mezőt.</p><p>Általános teljesítmény-, minőség- és stabilitásjavítások.</p> | Nincs szükség funkciókezelésre. | 2021. augusztus 12–17. |
| <p>A végtelen kapacitású ütemezéshez hozzáadott erőforrás-típuskövetelmények.</p><p>Javított erőforrás- és naptárhatékonyság végtelen kapacitású ütemezés esetén.</p><p>További tájékoztatás: [Ütemezés végtelen kapacitással](infinite-capacity-planning.md). | <p>A funkciókezelésben a 10.0.20 verziótól elérhető.</p><p>Funkció neve: *Végtelen kapacitásütemezés a tervezési optimalizáláshoz*</p> | 2021. július 6–12. |
| Általános minőségjavítás. | Nincs szükség funkciókezelésre. | 2021. július 6–12. |

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
