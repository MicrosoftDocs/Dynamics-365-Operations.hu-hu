---
title: "Helyek részleges ciklikus leltározása"
description: "A ciklikus leltározási tervek vezérlik a tényleges leltározási tevékenységeket. Kérhető az, hogy csak bizonyos termékek és termékváltozatok leltározása történjen meg a hely összes aktuális készlete helyett."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0e0f9d81f4d5943a89d8ac87776e05acb32cb8d9
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="partial-location-cycle-counting"></a>Helyek részleges ciklikus leltározása

[!INCLUDE [banner](../includes/banner.md)]

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
3.  Ciklikus leltározási tervekhez úgy lehet termékeket kiválasztani, hogy az **Üres helyek** mező beállításának az **Üresek nélkül** lehetőséget adja meg. A ciklikus leltározási terv feldolgozásakor létrejön a részleges ciklikus leltározási munka az A0001 cikkszámhoz. A tényleges leltározási folyamat az irányított ciklikus leltározás mobileszköz-menüelemének használatával hajtható végre.



<a name="see-also"></a>Lásd még
--------

[Ciklikus leltározás](cycle-counting.md)


