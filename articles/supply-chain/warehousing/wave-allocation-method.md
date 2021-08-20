---
title: Hullámfelosztás
description: Ez a témakör a hullámfelosztási lépés beállítását ismerteti, beleértve a párhuzamos feldolgozás engedélyezését is.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 9c534f5e10f5797543d56ff4a5a7ada937edcb017228ebe395ae8a45efa10886
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781321"
---
# <a name="wave-allocation"></a>Hullámfelosztás

[!include [banner](../includes/banner.md)]

A hullámfeldolgozás időigényes lehet, és a feldolgozási idő nagy részét a felosztási lépésben és a munkalétrehozási lépésben költi el.

Most már ezeket a lépéseket párhuzamosan is futtathatja, ami javíthatja a hullámfeldolgozás teljesítményét, és ugyanabban a raktárban nagyobb hullámátviteli sebességet tesz lehetővé. Ez a témakör ismerteti, hogyan kell beállítani a hullámfelosztási mód párhuzamos futtatását. A munkalétrehozás párhuzamos futtatásának beállításához lásd: [Munkalétrehozás ütemezése hullám során](configure-wave-schedule-work-creation.md).

Korábban egyszerre csak egy hullámot lehetett felosztani egy raktárban. Ezt a korlátozást eltávolítottuk, és egy új korlát lépett a helyébe, amely csak azokat az elemeket és dimenziókat zátolja, amelyek a hely fölött találhatók a foglalási hierarchiában. A hely feletti dimenziók mindig termékdimenziókat is tartalmaznak. Ha például egy elem konfigurálva van a *Szín* tulajdonsággal, akkor a *Piros*, a *Kék* és a *Sárga* változatait párhuzamosan fel lehet dolgozni.

Ez azt jelenti, hogy ha egy hullám ugyanazt az elemet a hely feletti megegyező dimenziókkal felosztja, a többi hullámnak várnia kell a zárolásra ugyanahhoz az elemhez és dimenzióhoz. Ha a zárolás nem szerezhető be időben, hiba történik, és a hullámfeldolgozás sikertelen lesz.

A párhuzamos feldolgozás kihasználása érdekében a hullámnak kötegben kell futnia.

## <a name="performance-improvements"></a>Teljesítménynövelő fejlesztések

A párhuzamos feldolgozás teljesítményelőnyei két kategóriába sorolhatók:

- **Javított átviteli sebesség** – A hullámok átviteli sebessége általában akkor is javul, ha a párhuzamos feldolgozás nincs konfigurálva, különösen olyan esetekben, amikor nincs átfedés a hullámokon belüli elemek között.
- **Egyetlen hullám felosztásának javítása** – Az ügyféladatok tesztelése közel 50%-os teljesítményjavulást mutatott a párhuzamos felosztásra való átállás után. A párhuzamos feldolgozás cikkekenként és dimenziókonként történik a hely felett, így a javítások attól függenek, hogy egy hullám hány különböző elemet tartalmaz, a rendelkezésre álló infrastruktúrától és a felosztás időtartamától a munkalétrehozás időtartamához viszonyítva.

## <a name="configure-parallel-allocation"></a>Párhuzamos felosztás konfigurálása

### <a name="warehouse-management-parameters"></a>Raktárkezelési paraméterek

Párhuzamos felosztási feldolgozás használatához válassza a **Raktárkezelés > Telepítés > Raktárkezelési paraméterek** lehetőséget, nyissa meg a **Hullámfeldolgozás** lapot, és tegye a következő beállításokat:

- **Hullámfeldolgozási kötegcsoport** – Válassza ki azt a kötegcsoportot, amelyet a hullámok kezdeti feldolgozásának kell használnia. A felosztás későbbi feldolgozását különböző kötegcsoportok használatával is el lehet végezni.
- **Hullámok feldolgozása kötegben** - Állítsa ezt *Igen* értékre a párhuzamos feldolgozáshoz.
- **Várakozás zárolásra (ms)** – Adja meg azt az időt (ezredmásodpercben), amennyit egy felosztási lépésnek várakoznia kell egy olyan rendszererőforrásra, amelyet amely egy másik felosztási lépés zárolt. Ha ez az idő letelik, a hullám feldolgozása nem történik meg, és a rendszer egy hibaüzenetet jelenít meg. Javasoljuk, hogy legalább néhány másodpercet engedélyezzen egy logikai egység felosztásának befejezése érdekében.

Ezekről és más hullámfeldolgozási lehetőségekről a **Raktárkezelési paraméterek** oldalon lásd: [Raktárparaméterek a hullámfeldolgozáshoz](wave-warehouse-parameters.md).

## <a name="wave-process-methods"></a>Hullámfeldolgozási módok

Párhuzamos feldolgozás beállítása:

1. Ugorjon a **Raktárkezelés > Beállítás > Hullámok > Hullámfeldolgozás módszerei** lehetőségre.
1. Válassza ki az `allocateWave` módszert a rácson.
1. A Műveleti ablaktáblán kattintson a **Feladatkonfiguráció** elemre.
1. Megnyílik a **Hullámfeladás módszerének feladatkonfigurációja** oldal. Ez a rács felsorolja azokat a raktárakat, ahol konfigurálta a `allocateWave` metódust. A párhuzamos feldolgozás csak a felsorolt raktárakhoz használható. A Műveleti ablaktábla gombokkal szükség szerint raktárakat adhat hozzá vagy távolíthat el a rácsból. 
1. Minden raktárhoz állítsa be a következőket:
    - **Kötegelt feladatok maximális száma** – Adja meg a kijelölt raktár felosztásához használandó kötegelt feladatok számát. A kötegelt feladatok optimális száma a rendelkezésre álló infrastruktúrától és a kiszolgálón feldolgozás alatt álló egyéb kötegelt feladatoktól függ. A hullámfeldolgozásnak szentelt négy alapvető környezetben végzett tesztek azt mutatták, hogy nyolc feladat használata jó eredményeket hozott.
    - **Hullámfeldolgozási kötegcsoport** – A különböző raktárakhoz megadott kötegcsoportok használhatók, hogy a felosztás feldolgozása raktáranként horizontálisan felskálázható legyen.

## <a name="enable-or-disable-parallelization-across-all-legal-entities"></a>Párhuzamosítás engedélyezése vagy letiltása az összes jogi személy esetén

Azt javasoljuk, hogy állítsa be az `allocateWave` módszert, hogy párhuzamosan fusson az összes jogi személy között, mert ez segít a hullámfeldolgozás teljesítményének javításában. A Supply Chain Management 10.0.17-es verizójától kezdve a *Hullámpárhuzamosítás a Hullámfelosztás metódushoz* funkció apértelmezetten engedélyezve van az új és frissített telepítésekhez, és később nem kapcsolható ki. A funkció engedélyezése után a következő történik:

- Az `allocateWave` metódus frissül, és ezután szerepel benne a feladatkonfiguráció beállítása, amellyel használhatja a **Hullámfeldolgozási metódus** oldalát arra, hogy meghatározza az egyszerre futtatni kívánt feladatok száma, a párhuzamos folyamatok számával egyenlő. Ennek eredményeképp a hullámfelosztási lépésre felhasznált idő (ami általában a teljes feldolgozási idő 30–60%-a), nagyjából a feladatok számával egyenlő mennyiséggel csökken. Azt is kiválaszthatja, hogy melyik köteg lesz hozzárendelve a feladatok feldolgozásához. Fontos megjegyezni, hogy az összes jogi személy úgy lesz konfigurálva, hogy a hullámokat kötegben dolgozza fel. Az olyan raktáraknál, amelyeknél már konfigurálva van a hullámok kötegelt feldolgozása, és az olyan raktáraknál, ahol az `allocateWave` metódus párhuzamos használata van konfigurálva, a rendszer megtartja a meglévő konfigurációt.
- Alapértelmezés szerint az összes új jogi személy úgy van konfigurálva, hogy a hullámokat kötegben dolgozza fel. Minden új raktár esetén, ahol a **Raktárkezelési folyamatok** beállítás engedélyezve van, az `allocateWave` alapértelmezés szerint párhuzamos futtatásra lesz konfigurálva.
- A **Raktárkezelési paraméterek** lapon a **Hullámok kötegelt feldolgozása** beállítás értéke *Igen* és a **Várakozás zárolásra (ms)** értéke az alapértelmezett 15 másodperc. Ez azt jelenti, hogy minden hullámot kötegben hajtanak végre. Ha egy hullám fut, akkor a felosztási lépés során a program zárolja a cikket és a dimenziókat a fenti helyen. Ha egy másik hullámfeldolgozási feladat ugyanazon rekordhoz próbálja meg ugyanazt a zárolást beszerezni, akkor az zárolva van, amíg az aktuális folyamat be nem fejeződik. A **Várakozás a zárolásra (ms)** beállítás azt a maximális időt határozza meg, amit a rendszer megvár a zárolás felengedése előtt.

A párhuzamos felosztás feldolgozásához a hullámfeldolgozásnak kötegelten kell futnia. Ezért csökkenti a hullámfeldolgozási teljesítményt, ha kikapcsolja a **Hullámok kötegelt feldolgozása** beállítást, különösen akkor, ha a hullámfeldolgozás a megfelelő hullámmetódusok feladatkonfigurációja által meghatározott párhuzamos folyamatot használ.

Szükség esetén visszavonhatja az alapértelmezés szerint adott beállításokat, amikor a *Hullámpárhuzamosítás a Hullámfelosztás metódushoz* funkció automatikusan engedélyezve van a példányhoz. Megvalósítás:

- Ugorjon a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** elemre. A **Hullámfeldolgozás** lapon alkalmazza az előnyben részesített értékeket a **Hullámok feldolgozása kötegben** és a **Várakozás zárolásra (ms)** mezőkben.
- Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámfeldolgozás módszerei** lehetőségre. Válassza ki az `allocateWave` módot. A Művelet ablaktáblán válassza a **Feladatkonfiguráció** lehetőséget egy olyan lap megnyitásához, amely felsorolja azokat a raktárakat, ahol a metódus párhuzamosan fut. Szükség szerint módosíthatja vagy törölheti a kötegelt tevékenységek számát és a hozzárendelt hullámcsoportot az egyes felsorolt raktárakhoz.

## <a name="troubleshooting"></a>Hibaelhárítás

### <a name="troubleshoot-using-the-infolog"></a>Hibaelhárítás az Információs napló használatával

Mivel a kötegkeretrendszert használja, a hullámfeldolgozás során előforduló hibák a kötegelt feladatok információs naplója részeként kerülnek örökre. A hullámhoz kapcsolódó kötegelt feladatok olvasásához:

1. Ugorjon a **Raktárkezelés \> Kimenő hullámok \> Szállítmányhullámok \> Minden hullám** menübe.
1. Válassza ki a megvizsgálni kívánt hullámot.
1. A Művelet panelen nyissa meg az **Hullám** lapot, és a **Hullám** csoportban válassza az **Kötegelt feladatok** elemet.

A hullámfeldolgozás önjavító, ezért a feldolgozás során észlelt hibákat az információs napló segítségével kell jelenteni.

A párhuzamos feldolgozással kapcsolatos tipikus hiba lehet, hogy két hullám egyszerre próbálja lefoglalni ugyanazt az elemet, és az egyik nem fejeződik be, így a másik hullám a megadott határidőn belül nem tud zárolást szerezni. Ha ez a helyzet bekövetkezik, a kötegelt feladatok naplója olyan információkat tartalmaz, amelyek azt állítják, hogy az elem zárolása nem hajtható végre, ebben az esetben a sikertelen hullámot újra fel kell dolgozni.

Mivel a feldolgozás párhuzamosan történik, az adatokat különböző táblákban kell megtartani a feldolgozás állapotának nyomon követéséhez. Ez azt jelenti, hogy a kötegelt feladatok naplói hibákat tartalmazhatnak, például ismétlődő kulcshibákat.

A kötegelt feladatok hibái szintén a kötegelt feladatok naplójának részét képezik. A legfontosabb információk általában az alján vannak.

Ritka esetekben, például ha az SQL-kapcsolat véget ért, lehetséges, hogy a hullámfeldolgozás inkonzisztens állapotban végződik, ahol a kötegelt feladat fut, de a feldolgozás leáll. A hullám nem tudja kezelni az ilyen hibákat, így a sikertelen hullámok megtisztítására tett kísérlet akkor történik, amikor a következő hullám fut. Ha az aktuális hullám inkonzisztens állapotban van, hajtsa végre a következő lépéseket:

1. Ugorjon a **Raktárkezelés \> Kimenő hullámok \> Szállítmányhullámok \> Minden hullám** menübe.
1. Válassza ki a megtisztítani szükséges hullámot.
1. A Művelet panelen nyissa meg az **Hullám** lapot, és a **Hullám** csoportban válassza az **Hullámadatok megtisztítása** elemet.

### <a name="troubleshoot-using-the-wave-progress-log"></a>Hibaelhárítás a hullám előrehaladási naplójának használatával

Ha a **Hullám előrehaladási naplójának létrehozása** beállítás engedélyezve van a **Raktárkezelési paraméterek** lapon, akkor a rendszer minden alkalommal létrehoz egy naplórekordot, amikor egy elem és a dimenziói felosztása megkezdődik és véget ér. Ezt a naplót csak akkor engedélyezze, ha szüksége van rá, például a kezdeti tesztelés vagy a hibaelhárítás során. Ha ez a beállítás engedélyezve van, a naplót a következő lépésekkel tekintheti meg:

1. Ugorjon a **Raktárkezelés \> Kimenő hullámok \> Szállítmányhullámok \> Minden hullám** menübe.
1. Válassza ki a megvizsgálni kívánt hullámot.
1. A Műveleti ablaktáblán nyissa meg a **Hullám** lapot, és a **Hullám** csoportban válassza az **Előrehaladás** lehetőséget.
