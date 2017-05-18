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
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 5ee2d132f0b23ceec2a79ee6b0ee33862d6a0518
ms.contentlocale: hu-hu
ms.lasthandoff: 04/25/2017


---

# <a name="financial-dimensions"></a>Pénzügyi dimenziók

[!include[banner](../includes/banner.md)]


Ez a cikk bemutatja a pénzügyi dimenziók különféle típusait és azok beállításának módját.

Használja a Pénzügyi dimenziók oldalt pénzügyi dimenziók létrehozásához, melyeket számlaszegmensként használhat számlatükrökhöz. Kétféle pénzügyi dimenzió van, egyéni és entitás által támogatott dimenzió. Az egyéni dimenziók jogi entitások között oszlanak meg, és az értékeket a felhasználó adja meg és tartja karban. Az entitás által támogatott dimenziók értéke a rendszerben máshol van meghatározva, például Vevők vagy Üzletek. Néhány entitás által támogatott dimenzió megoszlik a jogi személyek között, és néhány entitás által támogatott dimenzió vállalatspecifikus. 

A pénzügyi dimenziók létrehozása után használja a Pénzügyi dimenzióértékek oldalt, és rendeljen hozzá további tulajdonságokat az egyes pénzügyi dimenziókhoz. 

Annak ellenére, hogy a pénzügyi dimenziók felhasználhatók jogi személyek képviseletére jogi személyek létrehozása nélkül a Microsoft Dynamics 365 for Operations alkalmazásban, a pénzügyi dimenziókat nem jogi személyek működési vagy üzleti igényeinek kielégítésére tervezték. A Microsoft Dynamics 365 for Operations rendszerben a Egységközi könyvelés funkció csak az egyes tranzakciók által létrehozott könyvelési tételek kezelését szolgálja. 

Jogi személyiséggel rendelkező pénzügyi dimenziók beállítása előtt a következő területeken értékelje ki az üzleti folyamatait annak meghatározására, hogy ez a beállítás működik-e a szervezete esetében:

-   Készlet
-   Értékesítések és beszerzések üzleti dimenziók és jogi személyek között
-   Áfa számítás és jelentés
-   Üzemi jelentés

A következőkben néhány példa szerepel a korlátozásokra:

-   Az áfa funkciók csak jogi személyekhez használhatók, a pénzügyi dimenziókhoz pedig nem.
-   Egyes jelentések nem tartalmazzák a pénzügyi dimenziókat, ezért nem mindig jelenthet pénzügyi dimenziók szerint, csak ha ezeket a jelentéseket módosítják.

**Egyéni dimenziók** 

A felhasználó által definiált pénzügyi dimenziók létrehozásához az Értékek használata innen mezőben jelölje be az &lt; Egyéni dimenzió &gt; lehetőséget. A formátummaszk megadásával továbbá korlátozhatja a dimenzióértékekhez megadható adatok mennyiségét és típusát. Megadhat olyan karaktereket, például betűket vagy kötőjelet, amelyek minden egyes dimenzióértéknél változatlanok maradnak. Emellett megadhat kettős kereszt (\#) vagy és-jelet (&) olyan karaktereket, számok és betűk helyőrzőjeként, amelyek változni fognak a dimenzióértékek minden létrehozásakor. A kettős kereszt (\#) a számok, míg az és-jel (&) a betűk helyőrzője. 

**példa** 

Ha például a dimenzióértéket két C betűre és három számra szeretné korlátozni, formátummaszkként a CC-\#\#\# értéket adja meg. Ez a mező csak akkor érhető el, ha az &lt; Egyéni dimenzió &gt; opciót választja ki az Értékek használata innen mezőből. 

**Entitás által támogatott dimenziók** 

Entitás által támogatott pénzügyi dimenzió létrehozásához az Értékek használata innen mezőben válasszon ki egy a pénzügyi dimenzió alapjául szolgáló rendszer által definiált entitást. A kijelölés alapján létrejönnek a pénzügyi dimenzióértékek. Például projektek dimenzióértékeinek létrehozásához jelölje ki a Projekteket. A rendszer minden projektnévhez létrehozza a dimenzióértéket. A dimenzióértékek oldal megjeleníti az entitás értékeit, és ha ezek vállalatspecifikusak, az értékhez tartozó vállalatot. 

**Dimenziók aktiválása** 

A pénzügyi dimenzió aktiválásával frissítheti a pénzügyi dimenzió nevét tartalmazó táblázatot, és eltávolíthatja a törölt dimenziókat. A pénzügyi dimenziók aktiválása előtt megadhat dimenzióértékeket, de a pénzügyi dimenzió nem használható fel sehol, amíg nincs aktiválva. Például nem adhat hozzá pénzügyi dimenziót számlastruktúrához, amíg nem aktiválódik a pénzügyi dimenzió. Az aktiválásra kattintva minden állapotmódosítással rendelkező dimenzió frissül. 

**Fordítások** 

A szövegek fordítása oldalon megadhat egy szöveget, amelyet a kijelölt pénzügyi dimenzióhoz különböző nyelveken megjeleníthet. A Fő számla fordítási oldalon a fő számlához különböző nyelveken megjeleníteni kívánt szöveget adhat meg. 

**Jogi személy felülbírálásai** 

Nem minden dimenzió érvényes minden jogi személyre, és néhány csak egy adott időszakra vonatkozhat. Ebben az esetben a Jogi személy felülbírálása szakasz használható annak azonosítására, hogy mely vállalatok számára kell felfüggeszteni a dimenziót, ki a tulajdonos, és mely időszakban aktív a dimenzió.






