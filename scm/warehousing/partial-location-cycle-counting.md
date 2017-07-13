---
title: "Helyek részleges ciklikus leltározása"
description: "A ciklikus leltározási tervek vezérlik a tényleges leltározási tevékenységeket. Kérhető az, hogy csak bizonyos termékek és termékváltozatok leltározása történjen meg a hely összes aktuális készlete helyett."
author: perlynne
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
keywords: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 856ac2a61bc06a772b586a0cf77496fc360db623
ms.contentlocale: hu-hu
ms.lasthandoff: 06/13/2017

---

# <a name="partial-location-cycle-counting"></a>Helyek részleges ciklikus leltározása

[!include[banner](../includes/banner.md)]


A ciklikus leltározási tervek vezérlik a tényleges leltározási tevékenységeket. Kérhető az, hogy csak bizonyos termékek és termékváltozatok leltározása történjen meg a hely összes aktuális készlete helyett.

Ha ciklikus leltározási terveket használ a leltározási munka létrehozásához, irányíthatja a tényleges leltározási műveleteket. Kérhető az, hogy csak bizonyos termékek és termékváltozatok leltározása történjen meg a hely összes aktuális készlete helyett. Adott termékekre való szűréssel a raktárvezető csökkentheti az ellenőrzéssel járó költségeket, elkerülheti a konszolidációs hibákat és időt takaríthat meg.

## <a name="how-to-configure-partial-location-cycle-counting"></a>Hogyan kell konfigurálni a részleges helyre vonatkozó ciklikus leltározást
Ha a raktár munkafolyamatot használja a leltározási művelethez, minden egyes helyhez munkafejléc jön létre. A ciklikus leltározási terv meghatározásakor fel lehet használni a **Helyek kiválasztása** lekérdezést a létrehozott ciklikus leltározási munka korlátozásához. A ciklikus leltározási tervhez a termékek kiválasztásakor termék- és termékváltozat-lekérdezések is kiválaszthatók a leltározás hatókörének pontosításához. 

A ciklikus leltározási tervvel társítani lehet egy **munkasablont** annak a meghatározásához, hogy hogyan történjen a ciklikus leltározási munka létrehozása. A leltározási műveletek munkasablonjára közvetlenül hivatkozik a ciklikus leltározási terv. 

A munkasablon részleteinek definiálásakor használhatja a **Munkasorszünetek** beállítást annak a megadásához, hogy a leltári munkasorokat cikkszám vagy a termékváltozatszám szerint kell-e csoportosítani. Ez a beállítás akkor szükséges, ha csak bizonyos termékekre szeretne leltározást végrehajtani egy helyen. A létrehozott ciklikus leltározási munkasorok az itt megadott információszinttel jönnek létre, és az irányított leltározási művelet kezelése ennek a szintnek az alapján történik. 

Ha a ciklikus leltározási terveket társítja a munkasablonokkal a **Munkasorszünetek** lehetőség használatával, a **Részleges ciklikus leltár** mező be van jelölve a létrehozott leltározási munkához, és több ciklikus leltározási munkasorok jön létre a munkasablon definíciója alapján. 

A részleges ciklikus leltározási munka feldolgozása előtt minimális követelményként ki kell választani a **Cikkszám megjelenítése** elemet a mobileszköz menüeleméhez a ciklikus leltározás telepítésének részeként. A raktárkezelőt a rendszer arra kéri, hogy csak a leltársorokhoz kapcsolódó leltározási adatokat (cikkszámok és termékdimenziók) rögzítése. A leltározási folyamat figyelmen kívül hagyja az összes többi aktuális készletet. 

A részleges ciklikus leltározási folyamatban az **Utolsó ciklikus leltár** dátuma és időpontja nem frissül a helyre nézve.

## <a name="example"></a>Példa
Ebben a példában csak az A0001 cikkszámot kell leltározni a 61-es raktárban.

1.  A ciklikus leltározáshoz új munkasablon jön létre. A **Munkasorszünetek** beállítás szolgál a leltári munkasorok csoportosítására cikkszám szerint. Emiatt a létrehozott ciklikus leltározási munka sorokkal fog rendelkezni cikkszámonként. A sorokat termékváltozatszám szerint is lehet csoportosítani.
2.  Létrejön egy új ciklikus leltári terv, amely az újonnan létrehozott munkasablonra hivatkozik. A ciklikus leltározási terv minden helyet tartalmaz a 61-es raktárban (**Helyek kiválasztása** lekérdezés), ahol készleten van az A0001-es cikkszám. A konkrét termékek körét a **Ciklikus leltározási terv termékkiválasztások** szakasz határozza meg.
3.  A ciklikus leltározási tervekhez úgy lehet termékeket kiválasztani, hogy az **Üres helyek** mezőt **Üresek nélkül** beállításra állítjuk. A ciklikus leltározási terv feldolgozásakor az A0001 cikkszámhoz részleges ciklikus leltározási munka jön létre. A tényleges leltározási folyamat az irányított ciklikus leltározás mobileszköz-menüelemének használatával hajtható végre.



<a name="see-also"></a>Lásd még
--------

[Ciklikus leltározás](cycle-counting.md)


