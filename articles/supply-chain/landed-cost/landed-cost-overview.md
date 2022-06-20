---
title: Partraszállási költség modul
description: A Partraszállási költség modul segít a vállalkozásoknak a bejövő szállítási műveletek leegyszerűsítésében, azáltal, hogy a felhasználóknak teljes pénzügyi és logisztikai ellenőrzést ad az importált szállítmány fölött, a gyártótól a raktárig.
author: Weijiesa
ms.date: 12/07/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 2ac62678ca9bf7250271727fe83b8a8ba2fca59b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907435"
---
# <a name="landed-cost-module"></a>Partraszállási költség modul

[!include [banner](../../includes/banner.md)]

A **Partraszállási költség** modul segít a vállalkozásoknak a bejövő szállítási műveletek leegyszerűsítésében, azáltal, hogy a felhasználóknak teljes pénzügyi és logisztikai ellenőrzést ad az importált szállítmány fölött, a gyártótól a raktárig. Az importált áruk esetében a partraszállás költsége az importált cikkek teljes költségének 40 százalékának vagy többnek megfelelő lehet. Ebből következően kihívás, hogy pontos becsléseket adjanak a partraszállási költségekről.

A vállalkozások a partraszállási költséget a következő feladatok elvégzésére használják:

- Az hajóút létrehozásának ideje alatt partraszállási költségek becslése.
- A partraszállási költség arányosítása több cikkre és beszerzési vagy átmozgatási rendelésre nézve egyetlen hajóútban.
- Az áruk fizikai helyek közötti átvitelének támogatása a partraszállási költségeinek elszámolásával.
- Az úton lévő áruk elhatárolásainak elszámolása.

A partraszállási költség pontos és megfelelő időben történő becslést biztosít a járulékos partraszállási költségről. Ugyanakkor nagyobb pénzügyi és logisztikai rálátást biztosít a kiterjesztett ellátási láncra. A költségszámítás és költségszámítási hibák adminisztrációját is csökkenti.

## <a name="highlights"></a>Fontosabb jellemzők

### <a name="voyages"></a>Utak

A partraszállási költségnél a hajóút egy olyan elkülönült mozgás, amely a kimenő helyről egy megadott időszakban, megadott célhelyek csoportján keresztül egy megadott bemeneti raktár helyéig tart. A beszerzési rendelések és a rendeléssorok egy hajóút egyetlen tárolójához vagy több tárolójához is hozzáadhatók, és a költségek felosztása helyesen történik egy cikksorra megadva. 

### <a name="item-ownership"></a>Cikk tulajdonjoga

A Microsoft Dynamics 365 Supply Chain Management szolgáltatásnál az árukat jellemzően a raktári célhelyen kapják meg, majd számláznak. A legtöbb nemzetközi kereskedelmi megállapodás szerint azonban a vállalkozás az eredeti kikötő elhagyásakor átveszi az áruk tulajdonjogát, mielőtt még fizikailag megkapták volna őket. A partraszállási költség lehetővé teszi a vállalkozások számára, hogy az áruk fizikai beérkezését megelőzően számlázzanak. Ez a fogalom az úton lévő áruk megrendeléseként ismert. Új rendeléstípust hoz létre, hogy kezelni tudja az árubevételezéseket az eredeti beszerzési rendelés számlázása után.

### <a name="costs"></a>Költségek

Hajóút létrehozásakor a Partraszállási költség modulban a költségeket a rendszer automatikusan hozzáadja. Ezek a költségek a partraszállási költség modulban vannak beállítva, és számos költségbeállítás és költségelem elérhető hozzájuk. Minden egyesköltség beállítható a hajóút különböző szintjeihez, és arányosítható a cikkek szintjén az arányosítási szabályoknak köszönhetően, amelyek támogatják a mennyiséget, térfogatot, súlyt, összeget és megadott térfogati felosztásokat. Ezek a becsült költségek egy hajóút összes költségének pontos becslését biztosítják.

A partraszállási költség ezt követően előzetes feladást/elhatárolást futtat a becsült partraszállási költséghez, hogy a hajóút létrehozásakor a becsült költségek pontos számítása álljon rendelkezésre. Ahogy ezek az automatikus költségek számlázása megtörténik, a becsült költségeket a költségszámlák alapján sztornírozzák és felülírják a tényleges költségekkel.

A tényleges költségek a költségszámlázás pillanatában elszámolt sztornírozott becsült költségek, amelyeket az egyes költségtípusokhoz (pl. vám, fuvardíj és biztosítás) beállított elszámolószámlákkal kezelnek. Ezek az elszámolások az adott cikkhez kapcsolódó elszámolási viselkedést követik. Automatikusan frissítik a készletfeladást, függetlenül attól, hogy a feladás típusa elsőként be, elsőként ki (FIFO), utolsóként be, elsőként ki (LIFO), mozgó súlyozott átlag vagy mozgó átlag. Minden készletmodellcsoport-feladási típus támogatott. A mozgóátlag és az elszámolóár-feladás esetén a beszerzésiár-különbözeti számlák a becsült költségek és a tényleges költségek közötti különbözetek feladására használhatók.

### <a name="item-and-order-tracking"></a>Cikk- és rendeléskövetés

Ahogy a hajóút halad az eredeti kimeneti helyről a végső célként megadott raktárba, a felhasználók szükség esetén frissíthetik az utazás egyes lépéseit, azaz *szakaszait*. Minden egyes szakasz esetében egy átfutási idő és egy szállítmányállapot azonosítása történik. Az utazás következő szakaszába történő mozgás visszaigazolt szállítási dátumai is azonosítva vannak. Ezek a szállítási dátumok együtt az áruk becsült szállítási dátumát biztosítják a bejövő raktárba. A felhasználók módosíthatják ezeket a szállítási dátumokat. Ebben az esetben az áruk becsült szállítási dátuma automatikusan frissül az utazás átfutási ideje és szakaszai alapján. A hajóúton és hajóval úton lévő árukba való betekintés tárolónkénti alapon áll rendelkezésre az áruk bevételezése előtt. Mivel a dátumok minden beszerzésirendelés-sorban frissülnek, a vállalkozások nagyobb ellenőrzés alatt tarthatják a logisztikát és a raktártervezést.

## <a name="landed-cost-concepts"></a>Partraszállási költség koncepciói

Az alábbi táblázat összefoglalja a partraszállási költség alapfogalmait.

| Koncepció | Leírás |
|---|---|
| Út | A hajóút általában egy hajót jelent. A gyakorlattól és a eljárásoktól függően azonban lehet egy szállító vagy egy beszerzési rendelés is. Ennek a fogalomnak a használatát semmilyen korlátozás nem korlátozza. |
| Ívlap | A leveleket gyakran vámszabályok határozzák meg. Egy szállító szállításonként egy entitásnak vagy vállalatnak szánt termékeiből állhat. A levélben található áruk lehetnek egy konténerben vagy több konténer között elosztva is. |
| Szállítási konténer | Szállítási tárolók – üzleti beszerzésirendelés-sorai. A szállítmány szintje alatti szinten vannak. Rendszerint akkor használatosak, ha az árukra vonatkozó költségeket tárolónként arányosítják, vagy ha a bevételezés tárolónként történik. |
| Szállítási konténer típusa | A szállítási tárolótípusok meghatározhatják egy költségtípus (például fuvardíj) árát. Hasznos szállítási információkat is szolgáltatnak. |
| Költségtípus | A költségtípusok azonosítják az importhoz kapcsolódó költségeket, például a vámot, a fuvardíjat és a biztosítást. |
| Automatikus költség | Az automatikus költségek a kereskedelmi megállapodásokhoz hasonlóan működnek. Az automatikus költségek hajóútszinthez kapcsolódnak. |
| Kikötő | A kikötők olyan területek, ahova az áruk beérkeznek, és ahonnak átmozgatásra kerülnek. |
| Hajó | A hajó az áruk szállítására használt eszköz, például egy hajó vagy egy repülőgép. |
| Úton lévő áruk | A beállításoktól függően az áruk a számla frissítése után egy átszállítási raktárba kerülnek. |
| Tevékenység | A tevékenységek segítségével tárolni lehet két kikötő közötti utazás minden fontos lépését. A dátumok frissítésére használhatók. |
| Utazássablon | Az utazássablonok olyan útvonalak, amelyeken az áruk két kikötő között áthaladnak. |

A **Partraszállási költség** és a **Szállításkezelés** (TMS) modul szakkifejezéseinek és funkcióinak összehasonlításáért lásd: [Partraszállási költség és szállításkezelés](landed-cost-vs-tms.md).
