---
title: "Készlethelyek"
description: "A készlethelyek az alapvető raktározással (WMS I) együtt alkalmazandóak, a cikkek tárolási helyének és a cikkek WMS I raktárból történő felvételének meghatározásához."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSLocation
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2134
ms.assetid: 69bf6922-4151-447f-b678-4ba95637f54c
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 95d93c9d471cc86877f35340693c171958db71df
ms.contentlocale: hu-hu
ms.lasthandoff: 07/27/2017

---

# <a name="inventory-locations"></a>Készlethelyek

[!include[banner](../includes/banner.md)]


A készlethelyek az alapvető raktározással (WMS I) együtt alkalmazandóak, a cikkek tárolási helyének és a cikkek WMS I raktárból történő felvételének meghatározásához.

Ez a témakör a Készletkezelés modul szolgáltatásaira vonatkozik. Nem vonatkozik a Raktárkezelés modul funkcióira..

A hely megnevezés azt a helyet jelenti, ahol a cikkek tárolása és kivétele történik.

Minden egyes hely esetén meg lehet adni a cikk tárolási helyét is. Alapértelmezés szerint ezek megegyeznek. A cikkek kivétele és betétele általában ugyanazon a helyen történik, de nem mindig. Például az élő tároló állványoknál a tételek behelyezése az egyik folyosón történik, a kivétel azonban egy másikon. A fő bemenetet a hely nevével adják meg, amelyet általában a koordinátái határoznak meg: raktár, folyosó, állvány, polc, és rekesz. Ezt a nevet vagy azonosítót manuálisan vagy a helykoordináták alapján lehet bevinni – például a 01-02-03-4 az 1-es folyosót, 2-es állványt, 3-as polcot, és a 4-es rekeszt jelöli a Készlethelyek képernyőn.
Helytulajdonságok
-------------------

Egy hely a következő jellemzőkkel rendelkezik:
-   Méret (magasság, szélesség, mélység, és ezzel terjedelem)
-   Raktár, folyosó, állvány, polc és rekesz pozíciója.
-   Hely típusa (ömlesztett tárolóhely, kitárolási hely, érkeztetési terület, kiszállítási területre, termelési bemeneti hely, vizsgálat helye vagy kanban szupermarket)

Online rendszereknél ellenőrzőszövegekkel ellenőrizhető, hogy a kezelő a megfelelő helyet választotta-e ki az adott cikkhez. Az ellenőrzőszöveget létre lehet hozni kézzel vagy egy alapértelmezésnek megfelelően.

## <a name="sort-codes"></a>Rendezési kódok
A rendezési kódok segítségével lehet optimalizálni a válogatási sorok kezelését, amelyek részletezik a készletből kivenni kívánt cikkek szükséges adatait, így a válogatás sorrendjét is. A rendezési kódokat a folyosó és más koordináták alapján lehet megadni, vagy manuálisan a helyhez lehet őket rendelni.

## <a name="blocked-locations"></a>Blokkolt helyek
Időnként jelezheti a helyek lezárását, például hogy el lehessen végezni a javításokat. Más esetekben előfordulhat, hogy csak a bejövő vagy a kimenő forgalom blokkolását szeretné jelezni.
Fastruktúra
--------------

A Készlethelyek lapon tekintheti meg a raktárelrendezést egy fastruktúrában a készlethelyek koordinátái alapján, egy meghatározott kijelzési formátumban.
Készlethelyek karbantartása a raktári képernyőn keresztül
---------------------------------------------------

Lehetséges a helyek másolása egyik raktárból a másikba, és egy varázsló segítségével helyeket is hozhat létre. Mielőtt futtatná a varázslót, gondoskodnia kell arról, hogy meg vannak adva az alapértelmezett helynevek a Raktár lapon.



<a name="see-also"></a>Lásd még
--------

[Új raktárelrendezés létrehozása (Feladat-útmutató)](/dynamics365/unified-operations/supply-chain/inventory/tasks/create-new-warehouse-layout)




