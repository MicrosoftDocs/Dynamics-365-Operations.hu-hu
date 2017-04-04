---
title: "Készlethelyek"
description: "A készlethelyek az alapvető raktározással (WMS I) együtt alkalmazandóak, a cikkek tárolási helyének és a cikkek WMS I raktárból történő felvételének meghatározásához."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WMSLocation
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2134
ms.assetid: 69bf6922-4151-447f-b678-4ba95637f54c
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: cdf9eaeba076576d4adaa5fb5e18cd5a3f1c7b2d
ms.lasthandoff: 03/31/2017


---

# <a name="inventory-locations"></a>Készlethelyek

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

[Hozzon létre egy új raktári elrendezést (feladat guide)](https://ax.help.dynamics.com/en/wiki/create-a-new-warehouse-layout/)


