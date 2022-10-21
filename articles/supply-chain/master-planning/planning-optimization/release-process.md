---
title: Tervezési optimalizálás kiadási folyamata és kiadási előzmények
description: Ez a cikk a tervezési optimalizálás kiadási folyamatához és kiadási előzményeihez nyújt tájékoztatást.
author: t-benebo
ms.date: 10/14/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: e2437214b4a2a850f121bb86272bf7dc3d313507
ms.sourcegitcommit: b3579ac62e1ea15664a114abcc2409cad76d4f19
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/14/2022
ms.locfileid: "9682560"
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
| <p>[Kötegrendelkezési kódok](../../inventory/batch-disposition-codes.md)</p><p>Az aktuális készlet és a készlettranzakciók paramétereinek beszámozása az alaptervekbe</p><p>Általános teljesítmény-, minőség- és stabilságjavítások</p> | Nincs szükség szolgáltatáskezelésre. | 2022. október 10. 14. |
| <p>[Erőforrás-ütemezés véges kapacitással](finite-capacity.md)</p><p>Általános teljesítmény-, minőség- és stabilságjavítások</p> | Nincs szükség szolgáltatáskezelésre. | 2022. szeptember 19.23. |
| Általános teljesítmény-, minőség- és stabilságjavítások | Nincs szükség szolgáltatáskezelésre. | 2022. augusztus 29. – szeptember 3. |
| <p>[Központosított naptárkarbantartás](../supply-chain-calendars-master-planning.md)</p><p>[Javaslatok a meglévő készlet optimalizálására](../action-messages.md)</p><p>[Alvállalkozásba adás támogatása](../../production-control/manage-subcontract-work-production.md)</p><p>Általános teljesítmény-, minőség- és stabilságjavítások</p> | Nincs szükség szolgáltatáskezelésre. | 2022. március 7. 11. |
| Tervezési prioritás támogatása termelési rendelésekhez | A 10.0.25-ös verzióban elérhető a *Tervezés optimalizálása prioritás által vezérelt MRP-támogatás nevű funkció részeként*. | 2021. november 12.18. |
| Általános teljesítmény-, minőség- és stabilságjavítások | Nincs szükség szolgáltatáskezelésre. | 2021. november 12.18. |
| <p>Az időszámítási képletek, az átfedésben található termelési útvonal és a követelménytranzakciók termelési műveletszámának feldolgozásához nyújt segítséget.</p><p>Az időtúllépéshez, kapacitáshoz és a ciklikus útvonalhoz kapcsolódó termelési ütemezés továbbfejlesztett hibaüzenetei</p><p>Jobb konzisztencia a tervezett rendelések és a visszaeső rendelések kézhezvételi dátumának és kiadási dátumának számításakor</p><p>Általános teljesítmény-, minőség- és stabilságjavítások</p> | Funkció neve: *Végtelen kapacitásütemezés a tervezési optimalizáláshoz* | 2021. október 22. 27. |
| <p>A selejtszázalék figyelembe véve a feldolgozási idő számításában</p><p>A műveletszámok és anyagfelhasználás támogatása az ütemezés során</p> | Funkció neve: *Végtelen kapacitásütemezés a tervezési optimalizáláshoz* | 2021. október 5.7. |
| <p>Termelési útvonal feladattípusának támogatása: Várakozás **előtte**, **Várakozás utána** és **Szállítási idő**</p><p>Általános teljesítmény-, minőség- és stabilságjavítások</p> | Funkció neve: *Végtelen kapacitásütemezés a tervezési optimalizáláshoz* | 2021. szeptember 25.30. |
| <p>A Műveletek ütemezése beállítással **beállított ütemezési** mód alaptervek *támogatása*</p><p>Az Útvonalcsoportok lapon a **beállítási** vagy folyamat típusú sorok aktiválási, **·** **·** **·** **·** *munkaidő- és kapacitásellenőrzési beállításainak hatók meg.* *·* </p><p>Általános teljesítmény-, minőség- és stabilságjavítások</p> | <p>A műveletek ütemezése a 10.0.20 verziótól elérhető a szolgáltatáskezelésben.</p><p>Funkció neve: *Végtelen kapacitásütemezés a tervezési optimalizáláshoz*</p> | 2021. szeptember 9–17. |
| Általános teljesítmény-, minőség- és stabilságjavítások | Nincs szükség szolgáltatáskezelésre. | 2021. augusztus 25–30. |
| <p>A tervezett megrendelésekhez hozzáadtuk **az átfutási idő** mezőt.</p><p>Általános teljesítmény-, minőség- és stabilitásjavítások.</p> | Nincs szükség szolgáltatáskezelésre. | 2021. augusztus 12–17. |
| <p>Hozzáadott erőforrástípus-követelmények a korlátlan kapacitásütemezéshez</p><p>Jobb erőforrás-hatékonyság és naptár-hatékonyság a korlátlan kapacitásütemezéshez</p><p>A további tudnivalókat lásd: [ütemezés végtelen kapacitással.](infinite-capacity-planning.md)</p> | <p>Elérhető a funkciókezelésben a 10.0.20-as verziótól</p><p>Funkció neve: *Végtelen kapacitásütemezés a tervezési optimalizáláshoz*</p> | 2021. július 6–12. |
| Általános minőségi fejlesztések | Nincs szükség szolgáltatáskezelésre. | 2021. július 6–12. |

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
