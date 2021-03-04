---
title: Raktár konfigurálása – áttekintés
description: Ez a cikk a raktárak konfigurálásának módját ismerteti. A raktárelrendezések és a raktári folyamatok engedélyezésének módjáról nyúlt információkat.
author: perlynne
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, WHSLocation, WHSLocationBuild, WHSLocationProfile, WHSLocationType, WHSLocDirTable, WHSParameters, WHSWaveTemplateTable, WHSWorkPool, WHSWorkTemplateTable, WHSZone, WHSZoneGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 11554
ms.assetid: 262b7b88-2cce-44f7-9a5b-77c12af1be20
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a8cd436f1b8324335cc39ce54344db834dddebc9
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429380"
---
# <a name="warehouse-configuration-overview"></a>Raktár konfigurálása – áttekintés

[!include [banner](../includes/banner.md)]

Ez a cikk a raktárak konfigurálásának módját ismerteti. A raktárelrendezések és a raktári folyamatok engedélyezésének módjáról nyúlt információkat.

> [!NOTE]
> Ez a cikk a **Raktárkezelés** modul funkcióira vonatkozik (speciális a raktárkészlet-nyilvántartás). A **Készletkezelés** modul raktár funkcióira nem vonatkozik.

## <a name="warehouse-layout"></a>Raktárelrendezés
A Supply Chain Management rendszerben a Raktárkezelési rendszer rugalmas lehetőségeket kínál a változó igényekhez alkalmas raktárelrendezés definiálásához, így optimális raktározást érhet el.

-   Magas és alacsony prioritású tárolók területeket hozhat létre a termékek optimális elhelyezéséhez.
-   A különböző raktározási igényeknek megfelelően, mint például hőmérsékleti követelmények vagy a cikkek változó forgalmi arányai, feloszthatja a raktárat különböző zónákra.
-   Raktárhelyeket bármilyen szinten megadhat (például telephely, raktár, folyosó, állvány, polc és rekesz pozíció).
-   Csoportosíthatja a helyeket fizikai kapacitás megszorítás beállításai alapján.
-   Szabályozhatja cikkek tárolását és kitárolását a lekérdezésben megadott szabályokon alapján.

A Supply Chain Management rendszer raktárkezelési használatához hozzon létre egy raktárat, és engedélyezzen több speciális vagy konkrét raktárkezelési tevékenységet. A **Raktárak** oldalon válassza a **Raktárkezelési folyamatok alkalmazása** lehetőséget.

### <a name="zone-groups-zones-location-types-and-locations"></a>Zónacsoportok, zónák, helytípusok és helyek

A raktárelrendezés engedélyezési folyamat során definiálni kell raktár zónacsoportokat, és zónákat, helyprofilokat, helytípusokat és helyeket.

-   **Zóna csoportok** – Zónák logikai vagy fizikai csoportosítása egy raktáron belül
-   **Zóna** – Helyek logikai vagy fizikai csoportosítása egy raktáron belül
-   **Helyprofilok** – Azoknak a helyeknek a logikai vagy fizikai csoportosítása, amelyeknek ugyanazok a raktározási helyfolyamat irányelvei (például különböző cikkszámok kombinációit tárolhatja itt, és ugyanazokat a fizikai kapacitási megszorításokat alkalmazhatja).
-   **Helytípusok** – Raktározási helyek logikai vagy fizikai csoportosítása. Például létrehozhat egy hely összes előkészítő hely típusa. A **Raktárkezelési paraméterek** oldalon lévő kötelező beállítások vezetik az előkészítő hely típus definiálását, és a végleges kiszállítási hely típusát.
-   **Helyek** – A hely megadásának legalacsonyabb szintje. A Helyek segítségével nyomon követheti az aktuális készlet tárolását és kitárolását egy raktárban.

A raktárelrendezések definiálásához létrehozott entitás azokban a munkasablonokban beállított lekérdezésekben használt, amelyekkel a raktárakban lévő rendeléseket vezetheti. Ezért a zónák, helytípusok, és hasonlók meghatározásakor figyelembe kell venni, hogy a raktárak különböző területeit hogyan használják a különböző folyamatokhoz. Ezenkívül figyelembe kell venni egyéb tényezőket, mint például az adott terület fizikai jellemzőit. Például lehetnek olyan területek, ahol csak bizonyos típusú emelővillás targoncákat lehet használni. Vagy ha a vállalat ugyanabban a létesítményben termeli és be is fejezi a termékeket, lehetséges, hogy a Supply Chain Management rendszerben egyetlen raktárt akar létrehozni, de ebben az esetben válassza szét a két műveletet két zónacsoportra. Adja meg az entitások jól felismerhető neveit, így könnyű lesz azonosítani azokat a sablonlekérdezések használatakor.

### <a name="location-stocking-limits-location-profiles-and-fixed-picking-locations"></a>Helyi rakodási korlátok, helyprofilok és fix kiviteli helyek

Figyelembe kell venni a raktárak fizikai elrendezését a tárolási kapacitások meghatározásához (helyi rakodási korlátok és helyprofilok), valamint a kísérletek részeként is, hogy optimális raktározási folyamatokat érjen el. 

A helyi raktározás korlátok garantálják, hogy a munka létrehozásakor ne legyen olyan igény, hogy egy készletet olyan helyre rakjanak, amelynek a fizikai kapacitása nem alkalmas ahhoz a készlethez. Például ha a raktár egyes helyei csak egy raklapot tudnak várakoztatni, helyi raktározási korlátot lehet engedélyezni. A **Mennyiség** érték beállítható **1** értékre, és az **Egység** érték beállítható **PL** értékre egy adott hely profil csoportosításán belül. 

Ha speciális számítások szükségesek a helyi kapacitási megszorítások vezérléséhez, a helyprofil beállításai használhatók. Ebben az esetben a súly és térfogat számít kapacitásszámítás elvégzésekor. 

Optimális kimenő folyamatok eléréséhez értékelnie kell, hogy fix kiviteli helyeket és/vagy a csomagolási helyeket használjon-e. Gyakran a minimális/maximális feltöltéseket a raktártól a fix kiviteli helyekre történő feltöltéseknél használják, a többszörös fix kiviteli helyek pedig engedélyezhetők ugyanabban a raktárban és ugyanazokra a termékváltozatokra. Figyelembe kell venni az elérhető rugalmasságot, amelyet azoknál a különböző igényfeltöltési túlcsordulás helyeknél engedélyez, amelyeket csak hullám/terhelési feltöltési folyamatokhoz használ.

### <a name="location-setup-wizard"></a>Hely beállítása varázsló

A hely a raktáron belül gyors létrehozására használható a **Hely beállítása** varázsló. Ennek a folyamatnak a részeként egyszerűen karbantarthatja a helynevek formátumát.

## <a name="warehouse-processes"></a>Raktárfolyamatok
A raktár konfiguráció részeként fontos, hogy az üzleti követelményeknek megfelelően engedélyezze a raktárkezelési folyamatokat. A legfontosabb összetevők, amelyeket konfigurálnia kell, a hullámsablonok, munkasablonok, munkagyűjtők és helyutasítások.

### <a name="wave-templates"></a>Hullámsablonok

A hullámsablonok segítenek a kimenő „Kiadás raktárba” folyamat engedélyezésében. Amint a rendeléssorokat kiadta (akár közvetlenül a forrásbizonylatból kötegelt folyamaton keresztül, vagy már létrehozott rakományokon keresztül), a hullámsablon funkció használt. 

A következő három hullámsablon hozható létre: 
-   **Szállítás**
-   **Termelési rendelés**
-   **Kanban** 

A paraméterek segítségével határozza meg, hogy a rendszer meddig mehet automatikusan a kimenő munkafolyamatokhoz. Egy hullámsablont a hullámsablon-sorrend és a sablonban megadott feltételek alapján választ ki. Ha egy sablon a sorozat elején szerepel, először ellenőrizze abban sablonban a feltételeket. Ha a feltétel teljesíthető, a hullámsablont a rendszer feldolgozza. Ellenkező esetben a rendszer a következő sablonban lévő feltételeket ellenőrzi, és így tovább. Ezért célszerű, hogy azt a sablont, ami a legtöbb kritériummal rendelkezik, a hullámsablon sorozat lista tetejére rakja, így ezt a rendszer ezt dolgozza fel először. Például ma szeretné egy bizonyos szállítóhoz tartozó összes munkát feldolgozni, és ideiglenesen késleltetni az egyéb szállítók munkáinak feldolgozását. Ebben az esetben azt a hullámsablont, amely az ehhez a szállítóhoz tartozó munkákat választja ki, a sorozatban magasabbra kell rakni, mint az egyéb sablonokat. Ellenkező esetben, a más szállítók végzett munkát a rendszer hamarabb dolgozza fel, mint ahogy az ehhez a szállítóhoz tartozó munkát teljesítette volna. 

Minden hullámsablonban meg kell adnia a hullámfeldolgozási módokat. A használható módok a kijelölt hullámsablon típusától függően eltérőek.

### <a name="work-templates"></a>Munkasablonok

A munkasablon definíciók fontos szerepet játszanak a raktárkezelési munkafolyamatok meghatározásában. Ezek határozzák meg, hogy milyen munkát és hogyan végez el a rendszer. A sablonok tartalmazhatnak egy olyan utasításkódot, amely egy olyan helyutasításhoz kapcsolódik, ami meghatározza azt a helyet, ahol a munkát végrehajtják. A munkasablonok tartalmazhatnak egy lekérdezést, amely meghatározza a munkafeltételeket. Mindegyik sablonnak tartalmaznia kell legalább egy Kitárolási műveletet és egy Bemeneti művelet, amely az aktuális készlet egyik helyről másikra szállításához tartozó alapvető műveletek vezetésére való. 

Ha több dolgozó szükséges a munka végrehajtásához egyes raktári műveletek esetén, használhatja az *előkészítés* koncepciót a készlethez és a munka végrehajtását különböző munkaosztályokba különítheti el.

### <a name="work-pools"></a>Munkagyűjtők

Munkagyűjtőket a munkát csoportokba rendezésére használja. Például létrehozhat egy munkagyűjtőt, hogy osztályozza azt a munkát, amelyet egy adott raktárhelyen történik. Minden munkatípushoz, kivéve a leltárhoz, a munkasablonhoz egy munkagyűjtőt lehet hozzárendelni. Ciklikus leltározásnál hozzárendelheti a munkagyűjtőt a következők oldalakhoz:

-   Ciklikus leltározási tervek
-   Ciklikus leltározás küszöbértékei
-   Ciklikus leltározási munka hely szerint
-   Ciklikus leltározási munka cikk szerint

Amikor munkasablonokat használ munka létrehozásához, a munkagyűjtő automatikusan hozzá van rendelve a munkához. 

Munkagyűjtő azonosítókat is használhat azoknak a munkatípusoknak a korlátozásához, amelyeket egy adott raktári dolgozóhoz rendel. Ez a funkció a szükséges mobileszköz menü cikkeihez van konfigurálva.

### <a name="location-directives"></a>Helyutasítások

Ahogy a név javasolja, a helyutasításokat a munkatranzakciók irányításához használja a megfelelő helyek esetén a raktárakban. Ez azt jelenti hogy ez határozza meg a kitárolások és a betárolások helyét. 

A különböző helyutasítássorokhoz tartozó tevékenységek meghatározása könnyebbé és gyorsabbá tehető, ha egy előre meghatározott stratégiát használ. Használhatja például az **Bejövő munka nélküli üres hely** stratégiát a raktárban lévő szabad helyek keresésére, vagy használhatja a **FEFO-Köteg lefoglalása** stratégiát a kimenő értékesítési kitárolási listához.

<a name="additional-resources"></a>További erőforrások
--------

[Helyek konfigurálása WMS szolgáltatással rendelkező raktárban](tasks/configure-locations-wms-enabled-warehouse.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]