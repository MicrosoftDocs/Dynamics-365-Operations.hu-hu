---
title: Talent – előnézeti funkciók elérése
description: Ez a témakör leírja, hogy a rendszergazda hogyan engedélyezheti az előnézeti funkciókat, és felsorolja azokat a funkciókat, amelyek előnézet céljára jelenleg engedélyezettek.
author: tracykeya
manager: AnnBe
ms.date: 04/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: trkeya
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2019 update
ms.openlocfilehash: 72e2a3c62c7aab0f5cf8900c540a22d91be00609
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518218"
---
# <a name="access-preview-features-in-talent"></a>Talent – előnézeti funkciók elérése

[!include[banner](../includes/banner.md)]

A termék képességeit folyamatosan bővítjük, ennek részeként azt szeretnénk, hogy az ügyfelek a lehető leghamarabb használhassák az új funkciókat. A rendszergazdák láthatják és környezetükben használhatják az előnézeti szolgáltatásokat. Ezek a funkciók majdnem általános rendelkezésre állnak, és kiterjedt tesztelésen mentek keresztül. Az általános kibocsátás előtt egy utolsó visszajelzési és validálási kört végzünk az ügyfelekkel.

Ez a témakör leírja, hogy a rendszergazda hogyan engedélyezheti az előnézeti funkciókat, és felsorolja azokat a funkciókat, amelyek előnézet céljára jelenleg rendelkezésre állnak. Ez a lista frissül, ahogy a funkciókat általánosan elérhetővé tesszük, és ahogy új szolgáltatások előzetes kiadása történik meg. Nincsenek értesítések új funkciók előzetes kiadásakor. A felhasználók egyszerűen csak látni fogják a szolgáltatásokat.

## <a name="enable-or-disable-preview-features"></a>Előnézeti szolgáltatások engedélyezése vagy letiltása

Használhatja a Microsoft Dynamics 365 for Talent felügyeleti központjában az **Előzetes funkciók** beállítását az előnézeti funkciók engedélyezéséhez vagy letiltásához. Alapértelmezés szerint a beállítás be van kapcsolva. A előnézeti szolgáltatások engedélyezésének és letiltásának művelete környezetfüggő.

> [!IMPORTANT]
> Az **Előnézeti funkciók** beállításának bekapcsolásával a szervezet összes olyan felhasználója számára engedélyezi az előnézeti funkciókat, akik az adott környezetben vannak. A beállítás kikapcsolásával letiltja le az előnézeti funkciókat, és azok a felhasználók számára nem érhetők el. Az előnézeti funkciók támogatása korlátozott a Talentben. Előfordulhat, hogy ezek kevesebb adatvédelmi és biztonsági intézkedést használnak, és azok nem szerepelnek a Talent szolgáltatásiszint-szerződésében. Ne használja az előnézeti funkciókat személyes adatok (azaz az Önt bármilyen módon azonosítani képes adatok) feldolgozására, illetve más jogi vagy szabályozási, megfelelési követelmények hatálya alá tartozó adatok feldolgozására.

### <a name="enable-or-disable-preview-features-for-your-organization"></a>Az előnézeti funkciók engedélyezése vagy letiltása a szervezet számára

#### <a name="attract"></a>Attract

1. Jelentkezzen be a Microsoft Dynamics 365 for Talent: Attract szolgáltatásba.
2. A **Beállítás** menü (fogaskerék szimbólum) a jobb felső sarkában válassza ki az **Adminisztratív beállítások** lehetőséget.
3. A **Funkciók kezelése** lapon válassza ki az **Előnézeti funkciók** beállítás melletti lehetőséget úgy, hogy az kékre változzon.
4. Opcionálisan az egyes funkciókat az egyes szolgáltatások engedélyezésével vagy letiltásával lehet meghatározni az oldalon.
5. Frissítse a böngészőjét, hogy elindítsa el az új szolgáltatások megjelenítését. (Bármely, már bejelentkezett felhasználó számára a következő bejelentkezéskor jelenik meg a funkció, illetve frissíthetik a böngészőt a szolgáltatások azonnal megjelenítéséhez.)

#### <a name="core-hr"></a>Alapvető HR

1. Jelentkezzen be a Talentbe. Az emberi erőforrások alapvető munkaterülete megnyílik, ahol ki kell töltenie a fennmaradó lépéseket. 
2. Válassza ki: **Rendszerfelügyelet \> Rendszerparaméterek hivatkozásai**.
3. A **Rendszerparaméterek oldalon**, az **Előnézeti funkciók** lapon állítsa az **Előnézeti mód engedélyezése minden felhasználóra vonatkozóan** lehetőséget **Igenre** az előnézeti funkciók elérhetővé tételéhez.

> [!NOTE]
> Az előnézeti funkciók letiltásához használja ugyanazokat az alapvető lépéseket. Előnézeti funkciók letiltása esetén azok elérhetetlenné válnak a felhasználók számára, és hibák fordulhatnak elő a szolgáltatásokkal kapcsolatos folyamatokban.

## <a name="features-that-are-currently-in-preview"></a>Az előnézetben jelenleg szereplő funkciók.

### <a name="attract"></a>Attract

- **Egy feladatban releváns pályázók** – A toborzók és a felvételi vezetők könnyen megállapíthatják, hogy a jelentkezők keresztül mely pályázók a feladatra a leginkább megfelelők. A legjobb 5 pályázó az alapján jelenik meg, hogy az életrajzuk/profiljuk mennyire felel meg a munkaköri leírásnak.
- **Releváns feladatok** – A jelentkezők az életrajzuk/profiljuk és a munkaköri leírás alapján most már láthatják a számukra releván más feladatok listáját is.  Jelenleg ez akkor jelenik meg a pályázóknak, ha más lehetőségekre javaslatként jelentkeznek.
- **EEO/OFCCP-támogatás** – Új tevékenységtípusok egy előre meghatározott képernyő használatát engedélyezik az egyenlő foglalkoztatási lehetőség (EEO) és a szövetségi szerződés megfelelési program (OFCCP) adatok gyűjtésére a jelentkezőtől.  Ez egy előre meghatározott képernyő, ezért nem szerkeszthető.

    > [!NOTE]
    > A közzétett álláslehetőségek csak azon ügyfelek számára láthatók, akik egy vagy több LinkedIn álláslehetőség-szolgáltatásra előfizetnek. Ellenkező esetben az ügyfelek csak akkor látnak egy álláslehetőséget, ha arra kifejezetten rákeresnek. Az álláslehetőségek közzététele késéssel történik a LinkedIn-en. Előfordulhat, hogy egy állás csak az Attract-on való közzététel után csak néhány órával jelenik meg.

- **Pályázó jelentkezése** – A belső és külső jelentkezők most közvetlenül a karrier webhely állásoldaláról jelentkezhetnek.
- **Ajánlatkezelés** – A felhasználók ajánlati leveleket hozhatnak létre helyőrzőket tartalmazó sablonokból. Ahogyan a jelöltek tovább lépnek az ajánlati szintre, a toborzók és a felvételi menedzserek az ajánlati eszközzel formális ajánlatokat hozhatnak létre a sablonok segítségével, és elküldhetik az ajánlatot belső jóváhagyásra, majd végül elküldhetik az ajánlatot aláírásra a pályázónak. Idővel az ajánlati eszközhöz számos új lehetőség hozzáadódik, és az előnézeti funkció frissül ezekkel a lehetőségekkel, amint ezek készen állnak előzetes megtekintése.
- **[Analitikus jelentések](analytic-reports.md)** – A felvételi munkacsoportok az Elemzési központban megtekinthetik az egyes feladatok kulcsfontosságú mutatóit vagy összesített mutatókat az összes feladatra vonatkozóan.

### <a name="core-hr"></a>Alapvető HR

- **Beléptetés megnyitása** – A juttatásokra való nyitott jelentkezés lehetővé teszi az alkalmazottak számára, hogy egyszerű, önkiszolgáló módon válasszák ki a juttatásaikat. Az emberi erőforrás (HR) rendszergazdák beállíthatják a juttatásokra való nyitott jelentkezés folyamatát a szervezetük számára, valamint a feliratkozás lehetőségét az alkalmazottak számára, egy könnyen érthető, irányított megoldás használatával.

## <a name="feedback"></a>Visszajelzés

Függetlenül attól, hogy a visszajelzés pozitív vagy negatív, szeretnénk ha megosztaná velünk az előnézeti funkciói használatára vonatkozó tapasztalatait. Javasoljuk, hogy a rendszeresen küldje el a visszajelzését a következő helyeken, amikor ezeket a funkciókat használja vagy bármilyen más funkciót használ.

- [Közösségi](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – Ez a webhely remek fórum, ahol a felhasználók megbeszélhetik az eseteket, kérdéseket tehetnek fel és segítséget kaphatnak a közösségtől.
- A következő helyek segítségével küldheti el az ötleteit a termékkel kapcsolatban. Tájékoztasson bennünket, hogy mely funkciókat szeretné látni a termékben, illetve milyen változásokat kellene a meglévő szolgáltatásokban elvégezni.

    - [Ötletek kérése](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [Alapvető HR](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)

Ne adjon meg személyes adatokat (azaz az Önt bármilyen módon azonosítani képes adatokat) a visszajelzésében vagy a termék értékelése benyújtásakor. Előfordulhat, hogy az összegyűjtött információkat továbbelemzik, és azokat nem használjuk fel kérdések megválaszolására az alkalmazandó adatvédelmi törvényekkel összhangban. A programokhoz kapcsolódóan külön gyűjtött személyes adatokra a [Microsoft adatvédelmi nyilatkozat](https://privacy.microsoft.com/privacystatement) vonatkozik.

> [!TIP]
> Tegyen Könyvjelzőt ehhez a témakörhöz, és a jöjjön vissza gyakran, hogy naprakész legyen az előnézeti funkciókkal kapcsolatban, ahogy azok megjelennek.
