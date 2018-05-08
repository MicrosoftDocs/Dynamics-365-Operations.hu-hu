---
title: "Feltöltés visszavonási kanbanokkal"
description: "Ez a témakör a visszavonási kanban használatát írja le gyártási tevékenységek anyagfeltöltéséhez."
author: johanhoffmann
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoardTransferJob, KanbanFlow, KanbanRules
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 011da8cd894cc044b6af8b740e49ed8d7c3c0c67
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="replenishment-with-withdrawal-kanbans"></a>Feltöltés visszavonási kanbanokkal

[!include [banner](../includes/banner.md)]

Ez a témakör a visszavonási kanban használatát írja le gyártási tevékenységek anyagfeltöltéséhez.

## <a name="workflow-for-material-replenishment-that-uses-the-withdrawal-kanban"></a>Az visszavonási kanbant használó anyagfeltöltési munkafolyamat
-------------------------------------------------------------------

A visszavonási kanban használatával egy cikk kanbanja mozgatható az anyag felhasználását megvalósító raktárak és termelési helyek között. A visszavonási kanban az anyagfeltöltés lekéréses alapú megoldását támogatja, amelynél lekérési jel szükséges egy adott igény ellátásának kiváltására. 

A következő forgatókönyv egy lekéréses alapú feltöltést mutat be, ahol lekéréses jel kezdeményezi a kanban létrehozását a termelési folyamathoz szükséges anyagok feltöltéséhez. 

[![Lekéréses jel kezdeményezi a kanban létrehozását a termelési folyamathoz szükséges anyagok feltöltéséhez.](./media/material-replenishment-with-withdrawal-kanban.png)](./media/material-replenishment-with-withdrawal-kanban.png)

1.  Visszavonási kanban
2.  Kanban kiindulási és betárolási helye a raktári munkához.
3.  Kanban betárolási helye és a termelés bemeneti helye
4.  Gyártási folyamat
5.  Kanbankitárolási raktári munka
6.  Raktárhelyek a nyersanyagnak
7.  Nyersanyagraktár
8.  Gyártási raktár

Ennek a forgatókönyvnek az esetében a gyártási folyamat (4) egy termelési beérkezési helyről (3) használ fel anyagokat, a gyártási raktárban (8). Amikor megtörténik az anyag (kanban) anyagkezelési egységének felhasználása, üresként lesz regisztrálva. Egy feltöltési jel jön létre a cikk származási helyére, és létrejön egy új kanban (1). Ebben az esetben a cikk származási helye a nyersanyagraktár (7) helyeiből áll. Megtörténik a kanban anyagának kitárolása, és a betárolása egy helyre (2) ugyanabban a raktárban. Amikor megtörtént az anyag kitárolása, készen áll az átvitelre 2-es helyről a termelési bemeneti helyre (3) a gyártási raktárban (8).

## <a name="configure-warehouse-work-for-kanban-picking-for-the-withdrawal-kanban"></a>Raktári munka konfigurálása a kanbankitároláshoz a visszavonási kanban esetében

Ahhoz, hogy a nyersanyag kitárolható legyen a visszavonási kanban esetében, konfigurálja a hullámsablonokat, munkasablonokat és helyutasításokat a **Kanban kitárolás** munkarendelés-típushoz. Ez a munkarendelés-típus nem csak a visszavonási kanban esetében támogatja a kitárolási folyamatot. A kitárolási folyamatot a gyártási kanban esetében is támogatja. Ugyanakkor mindegyik kanbantípushoz konfigurálható külön kitárolási folyamat a hullámsablonok, a munkasablonok és a helyutasítások elválasztásával. A hullámsablonok, a munkasablonok és a helyutasítások elválasztására állítson be feltételeket a tevékenység típusára (**Folyamat** vagy **Átvitel**) az érintett entitások lekérdezéseiben.

## <a name="configure-the-withdrawal-kanban"></a>A visszavonási kanban konfigurálása

A visszavonási kanban esetében használt átviteli tevékenység az aktív műveletterv részeként van konfigurálva a lean típusú termelési folyamatban. Az átmozgatási tevékenység konfigurációjának részeként meg kell adni a kiindulást és a célt az átvitelhez. Miután beállította az átmozgatási tevékenységet, hozzárendelheti egy **Visszavonás** típusú kanbanszabályhoz. A kanbanszabály határozza meg az irányelveket és a konfigurációkat a visszavonási kanbanhoz. A kanban mennyisége határozza meg, hogy a kanban az anyagkezelési egység hány egységét viszi át az átviteli folyamat során. A rögzített kanbanmennyiség akkor használatos, ha a Rögzített feltöltési stratégiára be van jelölve. Ez a mennyiség határozza meg, hogy hány kanban szükséges ahhoz, hogy megakadályozza a készlet kifogyását az igény forrásánál. A fix mennyiség a tényleges igény, az előzményigény és szolgáltatási szintek alapján számítható ki. A következő két forgatókönyv bemutatja, hogyan kezelheti a visszavonási kanbant használó anyagfeltöltést.

## <a name="scenario-1-replenish-a-production-input-location-by-using-a-fixed-withdrawal-kanban"></a>1. forgatókönyv: Egy termelésbeérkezési-hely feltöltése rögzített visszavonási kanban segítségével

Egy gyártási folyamat használ fel egy megvásárolt nyersanyagot egy termelési beérkezési helyről, amely a gyártási raktárban van. Amikor a nyersanyag beérkezik a szállítótól, a nyersanyagraktáron belüli helyeken történik a tárolása. Mivel a nyersanyagra vonatkozó igényt egy adott időszakra stabilnak tekintjük, úgy állítjuk be, hogy rögzített mennyiségű kanbanfolyamatként lássa el a termelést. Ha a termelés bemeneti helyén megtörténik a kanban felhasználása, üres jel regisztrálása történik, és a rendszer azonos típusú új kanbant ad hozzá a folyamathoz. 

Az üres jel beállítható úgy, hogy automatikusan aktiválódjon a kanban befejezésekor. Másik lehetőségként az üres jelet be lehet állítani kézi beavatkozásként is, amely vagy a kanban átviteli tábláról érkezik, vagy a kézi eszköz egyik menüjéből. A kanban átviteli tábla az a munkaterület, ahol a kanban életciklusának összes tevékenységét kezelik. 

A kanban létrehozásakor a rendszer hozzáadja a nyersanyag hullámsorát a nyersanyagraktár egyik kanbanhullámához. A kanban átviteli tábla kitárolási lista csoportjában nyomon követhető az anyag és a kapcsolódó raktár állapota a hullám létrehozásától a munka létrehozásáig, amíg az anyag elérhető nem lesz az átviteli helyen, és készen nem áll az átvitelre a termelési bemeneti helyekre. A kanban befejezettként jelölhető meg a kanban átviteli tábláról vagy a kézi eszköz egyik menüjéből. 

Ennek a forgatókönyvnek az esetében a nyersanyagraktárban végzett kitárolási munka egy tevékenységként lesz feldolgozva. A nyersanyag- és a termelési raktár közötti átmozgatási tevékenység feldolgozása külön tevékenységként történik. Ez a megközelítés akkor lehet hasznos, ha például nagy fizikai távolság van a két raktár között. Ebben az esetben a kanban átviteli tevékenység egy teherautó-rakományt képezhet le. 

Ha a raktárak és a termelési bemeneti hely közötti távolság kicsi, hatékonyabb lehet, ha az átmozgatási tevékenységet belefoglalják a kitárolási folyamatba. Ezután, az anyag kitárolását követően, az anyag közvetlenül vihető a termelés bemeneti helyére. A folyamat támogatása érdekében konfigurálja úgy az átmozgatási tevékenységet, automatikusan befejeződjön, amikor megtörténik visszavonási kanban kitárolási munkájának feldolgozása.

## <a name="scenario-2-automatically-complete-the-transfer-activity-when-kanban-picking-work-is-processed"></a>2. forgatókönyv: Az átmozgatási tevékenység automatikus befejezése a kanban kitárolási munkájának feldolgozásakor

A következő forgatókönyv esetében a visszavonási kanban átviteli tevékenysége úgy van konfigurálva, hogy ugyanannak a raktárnak a két helye között végezzen átmozgatást. A visszavonási kanban átviteli tevékenysége úgy van beállítva, hogy automatikusan befejeződjön. 

[![Az átmozgatási tevékenység automatikusan befejeződik a kanban kitárolási munkájának feldolgozásakor](./media/transfer-activities-when-processing-kanban-picking.png)](./media/transfer-activities-when-processing-kanban-picking.png)

1.  A nyersanyag és a termelés raktára megosztott
2.  Raktárhelyek a nyersanyagnaknak
3.  Kanban kiindulási és betárolási helye a raktári munkához.
4.  Visszavonási kanban
5.  Termelések beérkezési helye
6.  Gyártási folyamat

Miután a termelés bemeneti helyén megtörtént a kanban felhasználása, a rendszer üresként jelenti a kanbant, és a rendszer új kanbant ad hozzá a folyamathoz. A kanban létrehozásakor a rendszer hullámsort ad a kanban hullámához. A kanbanhullám feldolgozása után létrejön a kanbankitárolási raktár munka. A raktári dolgozó feldolgozza a kanbankitárolási munkát, és a munka vezérli ahhoz, hogy kitárolja a kanbant a raktári helyen. Amikor az érintett raktári dolgozó megerősíti a kitárolást, a kanban automatikusan befejezett állapotra áll, és a raktári dolgozó utasítást kap az anyag elhelyezésére a termelés bemeneti helyén.


