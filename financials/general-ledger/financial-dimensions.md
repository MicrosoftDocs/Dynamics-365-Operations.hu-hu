---
title: "Pénzügyi dimenziók"
description: "Ez a cikk bemutatja a pénzügyi dimenziók különféle típusait és azok beállításának módját."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25871
ms.assetid: af54621c-c8be-4b72-b6df-dcf886c40ce4
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: f849b98cac88d182875aca88aaf04cd3575ed99f
ms.lasthandoff: 03/31/2017


---

# <a name="financial-dimensions"></a>Pénzügyi dimenziók

Ez a cikk bemutatja a pénzügyi dimenziók különféle típusait és azok beállításának módját.

Használja a Pénzügyi dimenziók oldalt pénzügyi dimenziók létrehozásához, melyeket számlaszegmensként használhat számlatükrökhöz. Kétféle pénzügyi dimenzió van, egyéni és entitás által támogatott dimenzió. Az egyéni dimenziók jogi entitások között oszlanak meg, és az értékeket a felhasználó adja meg és tartja karban. Az entitás által támogatott dimenziók értéke a rendszerben máshol van meghatározva, például Vevők vagy Üzletek. Néhány entitás által támogatott dimenzió megoszlik a jogi személyek között, és néhány entitás által támogatott dimenzió vállalatspecifikus. 

A pénzügyi dimenziók létrehozása után használja a Pénzügyi dimenzióértékek oldalt, és rendeljen hozzá további tulajdonságokat az egyes pénzügyi dimenziókhoz. 

Bár a pénzügyi dimenziók segítségével Microsoft Dynamics 365 műveletek esetében a jogi személy létrehozása nélkül jogi személyek képviseletére, pénzügyi dimenziók a működési megoldására nem terveztek vagy jogi személyek üzleti igények. A Microsoft Dynamics 365 műveletek egységközi könyvelési funkció csak az egyes tranzakciók által létrehozott könyvelési tételek megoldását szolgálja. 

Jogi személyiséggel rendelkező pénzügyi dimenziók beállítása előtt a következő területeken értékelje ki az üzleti folyamatait annak meghatározására, hogy ez a beállítás működik-e a szervezete esetében:

-   Készlet
-   Értékesítések és beszerzések üzleti dimenziók és jogi személyek között
-   Áfa számítás és jelentés
-   Üzemi jelentés

A következőkben néhány példa szerepel a korlátozásokra:

-   Az áfa funkciók csak jogi személyekhez használhatók, a pénzügyi dimenziókhoz pedig nem.
-   Egyes jelentések nem tartalmazzák a pénzügyi dimenziókat, ezért nem mindig jelenthet pénzügyi dimenziók szerint, csak ha ezeket a jelentéseket módosítják.

**Custom dimensions** 

A használat mező értékei a felhasználó által definiált pénzügyi dimenzió, létrehozásához jelölje ki &lt;egyéni dimenzió&gt;. A formátummaszk megadásával továbbá korlátozhatja a dimenzióértékekhez megadható adatok mennyiségét és típusát. Megadhat olyan karaktereket, például betűket vagy kötőjelet, amelyek minden egyes dimenzióértéknél változatlanok maradnak. Kettős kereszteket is megadhat (\#) és a változónevekben (&) betűk és számok, amelyek módosítják a dimenzió érték jön létre minden egyes helyőrzőjeként. Használja a kettős kereszt (\#) számára egy számot és egy ampersand jelet (&) levél helyőrzője. 

**példa** 

A dimenzió értéket a levelek másolatot kap és a három számának korlátozásához meg CC -\#\#\# a formátum maszkként. Ez a mező csak akkor használható választja &lt;egyéni dimenzió &gt;a használandó értékek mezőjéből. 

**Biztonsági entitás dimenziók** 

Mező értékei használja egy biztonsági szervezet pénzügyi dimenzió létrehozásához válassza ki a rendszer által definiált entitást a pénzügyi dimenzió alapjául. A kijelölés alapján létrejönnek a pénzügyi dimenzióértékek. Például projektek dimenzióértékeinek létrehozásához jelölje ki a Projekteket. A rendszer minden projektnévhez létrehozza a dimenzióértéket. A dimenzióértékek oldal megjeleníti az entitás értékeit, és ha ezek vállalatspecifikusak, az értékhez tartozó vállalatot. 

**Dimenzió aktiválása** 

A pénzügyi dimenzió aktiválásával frissítheti a pénzügyi dimenzió nevét tartalmazó táblázatot, és eltávolíthatja a törölt dimenziókat. A pénzügyi dimenziók aktiválása előtt megadhat dimenzióértékeket, de a pénzügyi dimenzió nem használható fel sehol, amíg nincs aktiválva. Például nem adhat hozzá pénzügyi dimenziót számlastruktúrához, amíg nem aktiválódik a pénzügyi dimenzió. Az aktiválásra kattintva minden állapotmódosítással rendelkező dimenzió frissül. 

**Translations** 

A szöveg fordítása lap segítségével adja meg a kiválasztott pénzügyi dimenzió más nyelven megjeleníteni kívánt szöveget. A Fő számla fordítási oldalon a fő számlához különböző nyelveken megjeleníteni kívánt szöveget adhat meg. 

**Legal entity overrides** 

Nem minden méretek az alábbiakra érvényesek minden jogi személy, és néhány csak vonatkozhat egy adott ideig. Ebben az esetben a Jogi személy felülbírálása szakasz használható annak azonosítására, hogy mely vállalatok számára kell felfüggeszteni a dimenziót, ki a tulajdonos, és mely időszakban aktív a dimenzió.




