---
title: Anyagjegyzék-számítási csoportok
description: Ez a cikk bemutatja az anyajegyzék (AJ) számítási csoportjait, valamint azok felállítását. Az AJ számítás futtatásához be kell állítania egy számítási csoportokat, majd ezeket hozzá kell rendelnie különböző cikkekhez, vagy be kell állítania egy alapértelmezett számítási csoportot. A számítási csoport számítási beállításai az alapértelmezett értékek az Anyagjegyzék-számítás oldalon az Anyajegyzék számításának ideje alatt.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMCalcGroup, BOMCalcTable, BOMCalcTrans, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94063
ms.assetid: 63e1b7dc-c2c5-41b0-81ed-e3e02d1b39e0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5927b1c31cf15e2fb92c15d4abc06bfa0403e33d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5266295"
---
# <a name="bom-calculations-groups"></a>Anyagjegyzék-számítási csoportok

[!include [banner](../includes/banner.md)]

Ez a cikk bemutatja az anyajegyzék (AJ) számítási csoportjait, valamint azok felállítását. Az AJ számítás futtatásához be kell állítania egy számítási csoportokat, majd ezeket hozzá kell rendelnie különböző cikkekhez, vagy be kell állítania egy alapértelmezett számítási csoportot. A számítási csoport számítási beállításai az alapértelmezett értékek az Anyagjegyzék-számítás oldalon az Anyajegyzék számításának ideje alatt. 

A **Készlet- és raktárkezelési paraméterek** oldalon egy alapértelmezett számítási csoportra, vagy a **Megjelent termék részletei** lapon egy termékkel kapcsolatos számítási csoportra van szükség. A rendszer először a számítási csoport beállításait keresi meg a **Megjelent termék részletei** lapon. Ha itt nem talál számítási csoportot, a **Készlet- és raktárkezelési paraméterek** oldalon keres tovább. Ha a rendszer nem talál számítási csoportot, a felhasználó egy hibaüzenetet kap a számítás során. A számítási csoport irányelveket tartalmaz az önköltségiár-modellhez, az eladásiár-modellhez, és a figyelmeztetések feladatlistához. A számítási csoport számítási beállításai az alapértelmezett értékek az **Anyagjegyzék-számítás** oldalon az Anyajegyzék számításának ideje alatt.

## <a name="purposes-of-bom-calculation-groups"></a>Az Anyajegyzék-számítási csoportok céljai
Több ok miatt is hozzárendelhet Anyajegyzék-számítási csoportot egy cikkhez:

-   Az **Önköltségi ármodell** mező beállításával jelezheti a megvásárolt összetevők költségfelosztási adatainak forrását a legyártott cikk tervezett költségének számítása során. Egyes gyártók a tervezett költségek kiszámításához a beszerzett összetevők beszerzési árára vonatkozó kereskedelmi megállapodásokat akarják felhasználni, vagy egyéb alapon, például a költségszámítási verzión belüli beszerzésiár-rekordok felhasználásával.
-   A **Eladásiár-modell** mező beállításával jelezheti a cikk adatainak a javasolt eladási ár számításában való felhasználási módját. Megadhatja, hogy a tétel eladási árát vagy a költségcsoportot. Egyes gyártók a legyártott cikkekhez javasolt eladási árat kívánnak kiszámítani. A kiszámított eladási ár tükrözheti a az összetevő eladásiár-rekordján alapuló árösszesítéses megközelítést. A kiszámított eladási ár tükrözheti a az összetevő költségén és vonatkozó nyereségszázalékán alapuló költség + árrés módszert, ami a cikk költségcsoportjához van társítva.
-   Az **Alábontás leállítása** mező használatával jelezheti, hogy az Anyajegyzék-számítás során a legyártott cikket beszerzett cikként kell-e kezelni, költségösszesítési célzattal. Rendszerint ez olyan helyzetben fordul elő, amikor egy beszerzett cikket időnként gyártanak, vagy amikor egy gyártott cikket már beszereznek. A cikk kezdetben gyártott cikként lesz megadva az anyagjegyzék- és útvonal-információk megadásához, valamint a cikkre vonatkozó termelési rendelések alátámasztására. Azonban az **Alábontás leállítása** jelző megakadályozza, hogy a költség számítás a termék Anyajegyzékét és útvonalát használja. Ehelyett az Anyagjegyzék-számítás a cikk meghatározott költségét használja.

## <a name="calculation-groups"></a>Számítási csoportok
Meghatározhatja a számítási csoportokat a Költségkezelésen belül az **Előre meghatározott költségirányelvek beállítása** lehetőségnél. A cikkhez rendelt számítási csoportok segítségével meghatározhatja, hogy az összetevők számítási csoport szerinti költsége vagy eladási ára legyen a forrás a számításhoz. A **Számítási csoportok** lapon határozhat meg önköltségiár-modellt, alternatív önköltségiár-modellt, eladásiár-modellt és figyelmeztetéseket.

### <a name="cost-price-model"></a>Önköltségiár-modell

Az **Önköltségiár-modell** mezőnek négy beállítása lehetséges:

-   **Cikk önköltségi ára** – A **Megjelent termék** tábla önköltségi árát, vagy a cikk dimenzióinak kombinációját használja önköltségi árként.
-   **Cikk beszerzési ára** – A **Kiadott termékek lista** lap **Beszerzés** fülén az **Önköltségi ár** mező beszerzési árai lesznek használva.
-   **Kereskedelmi megállapodások** – Beállíthatja a kereskedelmi megállapodásokat bizonyos cikkek, szállítók és webhelyek kombinációihoz. Majd mikor kiválasztja a **Kereskedelmi megállapodások** beállítást, az a kereskedelmi megállapodás lesz használva, amit a beszerzési árnak, a cikknek és a webhelynek együtt hozott létre.
-   **Készletár** – Annak a cikknek a jelenlegi készletára, amelyet az Anyajegyzékben használt az egységköltség kiszámításához. Az önköltségi egységár csak akkor kerül kiszámításra, ha a feladott és a tényleges mennyiség több, mint 0 (nulla).

### <a name="alternative-cost-price"></a>Másodlagos önköltségiár

A **Másodlagos önköltségiár** mező ugyan azokkal a beállításokkal rendelkezik, mint az **Önköltségiár-modell** mező. Azonban ezt a mezőt csak akkor használjuk, ha egy ár nem található az elsődleges önköltségiár-modellben.

### <a name="sales-price-model"></a>Eladásiár-modell

Két beállítás van az **Eladási árak** mező kiszámításához:

-   **Költségcsoport** – Ha ezt a beállítást választja, az eladási ár kiszámításánál az önköltségi ár és a költségcsoport nyereség-beállítás százalékos értéke lesz figyelembe véve.
-   **Cikk eladási ára** – Ha ezt a beállítást választja, a Megjelent termék tábla **Eladás** gyorslapján lévő eladási árak lesznek használva.

### <a name="stop-explosion"></a>Alábontás leállítása

Az **Alábontás leállítása** jelölőnégyzet segítségével jelezheti, ha egy legyártott cikket beszerzési cikként kell kezelni. A legtöbb esetben az **Alábontás leállítása** jelölőnégyzetet hagyja üresen. Ennek a jelölőnégyzetnek a bejelölésével jelezheti, hogy a gyártott cikket az anyagjegyzék-számításokban beszerzett összetevőként, nem pedig gyártott összetevőként kell kezelni, A webhelytől függően a cikk költségei kiszámíthatók az anyagjegyzék-számításokkal. A tervezett beszerzési rendelés és termelési rendelés alábontása leáll az Anyajegyzék azon összetevőinél, amelyek egy olyan számítási csoporthoz tartoznak, ahol az **Alábontás leállítása** jelölőnégyzet be van jelölve. Az alapütemezés magán az anyagjegyzéken generálja a tervezett rendeléseket, nem pedig az anyagjegyzékben szereplő cikkeken. Alapvetően ennek a jelölőnégyzetnek a bejelölésével azt adja meg, hogy egy költség ne legyen hozzáadva az Anyajegyzéki-számításhoz azon cikkek esetében, amik rendelkeznek ezzel a számítási csoporttal.

### <a name="warnings"></a>Figyelmeztetések

A **Figyelmeztetések** gyorslapon kiválaszthatja, hogy mely figyelmeztető üzenetek jelenjenek meg a felhasználóknak, mikor az Anyajegyzék-számításokat csinálják. 

Ha például kiválasztja a **Nincs AJ** jelölőnégyzetet, a felhasználó egy figyelmeztetést kap, ha nem található aktív Anyajegyzék-verzió valamelyik összetevőhöz, vagy azon fölérendelt cikkhez, amihez az Anyajegyzék-számítás készül. Ha bejelöli a **Nincs útvonal** jelölőnégyzetet, a felhasználó figyelmeztetést kap, ha nem található aktív útvonalverzió. Ha forrást használ az útvonalakhoz és műveletekhez, utasíthatja a rendszert, hogy ellenőrizze ezeket az erőforrásokat. Ezután ha egy erőforrás nem található az aktív útvonal minden sorában, a felhasználó figyelmeztetést kap. 

Jóváhagyhatja és ellenőrizheti a fogyasztást is. A fogyasztás a mennyiség a megadott útvonalon. Általában a termelési folyamat egy adott műveletének végrehajtásához szükséges idő mennyiségét jelzi. Ellenőrizheti, hogy egy cikk rendelkezik-e önköltségi árral. Ha nem rendelkezik önköltségi árral, akkor nem kerül költség hozzáadásra az Anyajegyzék-számításhoz. 

Jóváhagyhatja és ellenőrizheti az önköltségi ár korát is. Például adjon meg értéknek **60**-at, hogy jelezze, hogy az egység önköltségi árát 60 nap után felül kell vizsgálni. Ha a rendszer eléri ezt a határt, egy figyelmeztetést hoz létre. Például egy cikk önköltségi ára ezen év januárjában lett megadva. Ha most augusztus van, ami több, mint 60 nappal a cikk önköltségi árának megadása után van, a felhasználó egy figyelmeztetést fog kapni az Anyajegyzéki-számítás során. A **Minimálisan engedélyezett árrés** mezőben megadhat százalékos értéket. Ez az érték azt a pontot jelöli, ahol nem lett elérve a minimálisan engedélyezett árrés. Ha egy bizonyos összetevő esetében nem lett elérve a minimálisan engedélyezett árrés, a felhasználó kap egy figyelmeztetést. Ezért ez a mező segít biztosítani, hogy az árát és a további szállítási költségeket a cikk számára ne állítsa túl alacsonyra.

### <a name="default-setup-in-inventory-and-warehouse-management-parameters"></a>A Készlet- és raktárkezelési paraméterek alapértelmezett beállítása

Mivel a számítási csoportok szükségesek a számítások futtatásához, ezért be kell állítania egy alapértelmezett számítási csoportot a készletkezelési paramétereknél. Ez a beállítási lehetővé teszi a vállalatoknak az általános költségcsoport és a nyereség beállítását az összes cikkhez. Ezután ha egy adott cikkhez speciális számítási követelmények szükségesek, a felhasználó hozzárendelhet különböző számítási csoportokat. Általában beállíthat számítási csoportokat az AJ összetevő cikkekhez az AJ cikkek helyett. Azonban ha figyelmeztető üzenetek jelennek meg, akkor számítási csoportok is alkalmazhatóak. Egy cikkhez hozzárendelt számítási csoport felülírja a készletkezelési paramétereknél megadott alapértelmezett értéket. 

Alapértelmezett paramétereket beállíthat a **Költségkezelés** &gt; **Készletkönyvelési irányelvek beállítása** &gt; **Paraméterek** &gt; **Készletkönyvelés** &gt; **Számítási csoport** menüben. Alapértelmezett konfigurációs csoport beállításával konfigurálhatja azokat a figyelmeztetési feltételeket is, amelyek az AJ számítási folyamat során jelennek meg a felhasználóknak, ha a kiválasztott összetevő számítási hibákat okozhat.

### <a name="view-warning-messages-on-the-complete-page"></a>Figyelmeztető üzenetek megtekintése a Teljesített oldalon

Az AJ számítások figyelmeztető üzeneteket hoznak létre. Megtekintheti a kijelölt cikkhez kapcsolódó figyelmeztetéseket. Például hozzon létre az Értékesítés és marketingnél egy új eladási rendelést a D0001-es cikkhez. Ezután az értékesítési rendelés sorban a **Sor frissítése** menüben kattintson a **Számítás az AJ/Receptúra alapján** lehetőségre, hogy megtekintse a számítás részleteit és a figyelmeztetéseket. A **Teljesített** lapon megtekintheti az AJ számítások eredményeit is. A figyelmeztető üzeneteket illetően, csak két figyelmeztetési feltétel vonatkozik a gyártott cikkekre, míg négy figyelmeztetési feltétel minden cikkre.
-   Azonosítja, ha egy gyártott cikkhez nem tartozik aktív anyagjegyzék.
-   Azonosítja, ha a gyártott cikkhez nem tartozik aktív útvonal.
-   Azonosítja, ha az egyik anyagjegyzék-sorban szereplő cikkhez 0 (nulla) mennyiség tartozik.
-   Azonosítja, ha az egyik anyagjegyzék-sorban szereplő cikkhez 0 (nulla) költség tartozik, vagy nem tartozik hozzá költségrekord.
-   Azonosítja, ha az egyik anyajegyzék-sorban elavult költség van. A figyelmeztetés tükrözi a számítás dátuma és az önköltség maximális korához megadott napok számának összehasonlítását.
-   Azonosítja, ha az egyik anyagjegyzék-sorban szereplő cikkhez a kívántnál kisebb nyereségességi százalék tartozik.

A figyelmeztető üzenetek közötti eltérések alapján azonosíthat több AJ számítási csoportot. Elég lehet például egy anyagjegyzék-számítási csoport is, amely figyelmeztetési feltételeket tartalmaz az aktív anyagjegyzékre, a nulla összetevő-mennyiségre és a nulla összetevőköltségre vonatkozóan. Amikor elindít egy AJ számítást, felülírhatja az anyagjegyzék-számítási csoporthoz társított figyelmeztetési feltételeket. Valamint hozzá is adhat, illetve el is távolíthat figyelmeztetési feltételeket. Eltávolítható például az aktív útvonalra vonatkozó figyelmeztetési feltétel, amikor az adott helyzetben nem kell útvonaladatokat kezelni. **Megjegyzés:** A munkaidő és jelenlét tartalmazza a **Számítási csoportok** oldalt, azonban ennek az oldalnak nincsen kapcsolata az AJ számítási csoportokhoz. A Munkaidő és jelenlétben a dolgozók hozzárendelhetőek olyan számítási csoportokhoz, amelyek megmutatják, hogy kik azok a dolgozók, akik ugyan ahhoz a felügyeleti személyhez vagy vezetőhöz tartoznak. A dolgozói regisztrációk számítása elvégezhető automatikusan vagy manuálisan egy felügyeleti személy vagy vezető által.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]