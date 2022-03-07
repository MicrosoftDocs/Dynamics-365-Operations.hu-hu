---
title: Minőségi rendelések
description: Ez a témakör bemutatja, hogyan lehet manuálisan vagy automatikusan minőségi rendeléseket létrehozni, és hogyan lehet velük vizsgálatot végezni, illetve rögzíteni a teszteredményeket a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 69a4a61a599f1279ec7ad68ebb20c7b4b0f37005
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571857"
---
# <a name="quality-orders"></a>Minőségi rendelések

[!include [banner](../includes/banner.md)]

Ez a témakör bemutatja, hogyan lehet manuálisan vagy automatikusan minőségi rendeléseket létrehozni, és hogyan lehet velük vizsgálatot végezni, illetve rögzíteni a teszteredményeket a Microsoft Dynamics 365 Supply Chain Management alkalmazásban.

## <a name="automatically-created-quality-orders"></a>Automatikusan létrehozott minőségi rendelések

A rendszer beállítható úgy, hogy a cikkmintavételi szabályok alapján automatikusan minőségi rendeléseket hozzon létre. További információért lásd: [Minőségkezelési cikk mintavételezése](quality-item-sampling.md).

## <a name="manually-create-quality-orders"></a><a name="manual-quality-orders"></a>Minőségi rendelések manuális létrehozása

A minőségi rendelés manuális létrehozásához kövesse az alábbi lépéseket.

1. Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Minőségi rendelések** lehetőségre.
1. Válassza az **Új** lehetőséget.
1. A **Minőségi rendelések** párbeszédpanel **Hivatkozástípus** mezőjében válassza ki azt a készlethivatkozást, amelyhez a minőségi rendelés kapcsolódik majd. A kiválasztásra elérhető hivatkozástípusok leírását lásd a témakör későbbi [Minőségi rendelések hivatkozástípusai](#ref-types) című részében.

    > [!NOTE]
    > Elérhetőnek kell lennie a kiválasztott hivatkozáshoz kapcsolódó készletnek. Ha a kiválasztott hivatkozástípus, mennyiség és készletdimenzió kombinációjához nem áll rendelkezésre készlet, egy hibaüzenet jelenik meg.

1. Hajtsa végre a **Hivatkozástípus** mezőben kiválasztott értéktől függően az alábbi lépések egyikét:

    - Ha a **Készlet** lehetőséget választja, akkor nincs szükség további hivatkozási információkra.
    - Ha az **Értékesítés** vagy a **Beszerzés** beállítást választotta, adja meg a következő adatokat:

        - **Partner kiválasztása** – Hivatkozás a vevői vagy szállítói számra.
        - **Hivatkozási szám** – Hivatkozás az értékesítési vagy beszerzési rendelés számára.
        - **Hivatkozott tétel** – Hivatkozás az adott értékesítésirendelés-sorra vagy beszerzésirendelés-sorra.

    - Ha a **Termelés**, a **Karantén** vagy a **Társtermék gyártása** beállítást választotta a **Hivatkozási szám** mezőben, akkor a termelési rendelés, a kötegrendelés vagy a karanténrendelés száma van megjelölve.
    - Ha az **Útvonalművelet** beállítást választotta, adja meg a következő adatokat:

        - **Hivatkozási szám** – Hivatkozás a termelési rendelés vagy a kötegelt rendelés számára.
        - **Műveletszám** – Az adott útvonalműveletszámra való hivatkozás.
        - **Művelet** – Az adott útvonalműveletre való hivatkozás.
        - **Erőforrás** – Az útvonalművelethez szükséges konkrét erőforrásra való hivatkozás.

1. A **Tesztcsoport** mezőben válassza ki az elvégzendő tesztcsoportot.
1. A **Mennyiség** mezőbe írja be a tesztelni szükséges cikkek mennyiségét.
1. A **Készletdimenziók** szakaszban adja meg a kiválasztott cikkhez szükséges további készletdimenziókat.
1. Válassza ki az **OK** lehetőséget.

A minőségi rendelés létrehozása után megkezdheti a készlet vizsgálatát, és rögzítheti a teszteredményeket. A teszteredmények rögzítésével és ellenőrzéssel kapcsolatos további tudnivalókat lásd: [Az áruk minőségének vizsgálata](tasks/inspect-quality-goods.md).

## <a name="quality-order-reference-types"></a><a name="ref-types"></a>Minőségi rendelés hivatkozástípusai

A minőségi rendelések segítségével nyomon követhetők a raktár meghatározott készletének vizsgálatai és teszteredményei. A minőségi rendelésnek tartalmaznia kell egy olyan hivatkozást, amely a vizsgált készlet forrását képviseli. A minőségi rendelések a következő hivatkozástípusokhoz köthetők:

- **Készlet** – Ez a hivatkozástípus azt jelzi, hogy rendelkezésre álló készletet vizsgál. Az ilyen típusú vizsgálatok általában véletlenszerűek vagy nem tervezettek, és akkor történik meg, amikor a raktári dolgozó problémát azonosít.
- **Értékesítés** – Ez a hivatkozástípus azt jelzi, hogy egy meghatározott értékesítési rendeléshez kapcsolódó készletet vizsgál. Az ilyen típusú vizsgálatok általában a vevői specifikációkhoz, illetve olyan elemzési tanúsítvány (CoA) generálásaihoz kapcsolódnak, amelyről a vevőnek a szállítás részeként információt kell adni. (A CoA tanúsítványt megfelelési tanúsítványnak is nevezik \[CoC\].)
- **Vásárlás** – Ez a hivatkozástípus azt jelzi, hogy egy meghatározott beszerzési rendeléshez kapcsolódó készletet vizsgál. Az ilyen típusú vizsgálatok gyakran használatosak a bejövő áruk készletezése vagy a termelési folyamatokban való felhasználása előtt.
- **Termelés** – Ez a hivatkozástípus azt jelzi, hogy egy meghatározott termelési rendeléshez kapcsolódó készletet vizsgál. Az ilyen típusú vizsgálatok gyakran használatosak a készáruk készletezése előtt.
- **Karantén** – Ez a hivatkozástípus azt jelzi, hogy egy meghatározott karanténrendeléshez kapcsolódó készletet vizsgál. A karanténrendelések olyan különleges rendelési típust jelentik, amely a készletet egy elkülönített raktárban vagy a raktár egy eltárolt területén követi nyomon. Az ilyen típusú vizsgálatok gyakran használatosak olyan áruk vizsgálatára, amelyek vevő által visszaküldött áruk, illetve amelyek további elemzés céljából karanténba kerültek. Minőségi rendelésekből karanténrendelések generálhatók. Másik lehetőségként ezek más forrásokból is generálhatók, és a minőségi rendelések társíthatók a karanténrendelésekhez.
- **Útvonalművelet** – Ez a hivatkozástípus azt jelzi, hogy egy termelési rendelés meghatározott lépéséhez vagy útvonalához kapcsolódó készletet vizsgál. Az ilyen típusú vizsgálatok rendszerint a termék befejezetlen termelés (WIP) állapotának elemzésére használatosak, mielőtt a termelési folyamat következő lépésére lépne.
- **Társtermék gyártása** – Ez a hivatkozástípus azt jelzi, hogy egy társtermékhez kapcsolódó termelési rendeléshez kapcsolódó készletet vizsgál. Az ilyen típusú vizsgálatok rendszerint a kötegelt rendelés társtermékének vizsgálatára használatosak, még mielőtt a társterméket a készletbe helyeznék.

## <a name="view-and-create-quality-orders-from-various-parts-of-the-system"></a>Minőségi rendelések megtekintése és létrehozása a rendszer különböző részeiből

Minőségi rendelések manuálisan hozhatók létre. Más megoldásként létre lehet ezeket hozni automatikusan is meghatározott minőségi társítások alapján. A minőségi rendelések automatikus létrehozásának létrehozásával és kezelésével kapcsolatos további tudnivalókat lásd: [Minőségi társítások](quality-associations.md).

A minőségi rendelés lap használatával manuálisan létrehozhat új minőségi rendelést, vagy megtekintheti egy másik rekordhoz kapcsolódó minőségi rendelés állapotát. A minőségi rendelés oldal elérésére többféle lehetőség van.

### <a name="from-the-quality-orders-page"></a>A Minőségi rendelések lapról

Minőségi rendelések manuális létrehozásához és az összes meglévő minőségi rendelés megtekintéséhez, menjen a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Minőségi rendelések** elemre. A témakör további részei a **Minőségi rendelések** lap használatáról nyújtanak további tájékoztatást.

### <a name="from-sales-orders"></a>Értékesítési rendelésekből

Az értékesítési rendelésekhez kapcsolódó minőségi rendeléseken való munkához menjen az **Értékesítési és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** menübe, majd hajtsa végre a következő lépések valamelyikét:

- Nyisson meg egy értékesítési rendelést, vagy válassza ki a rácsban. Ezután a Műveleti panelen a **Kitárolás és csomagolás** lap **Minőségkezelési** csoportjában válassza a **Minőségi rendelések** lehetőséget a **Minőségi rendelések** lap megnyitásához. Itt lehet megtekinteni, létrehozni vagy frissíteni az értékesítési rendeléshez kapcsolódó minőségi rendeléseket.
- Nyisson meg egy értékesítési rendelést, majd a **Fejléc** lapon válassza az **Általános** gyorslapot. A **Minőségi rendelés állapota** mező az értékesítési rendeléshez kapcsolódó valamennyi minőségi rendelés általános állapotát mutatja.
- Nyisson meg egy értékesítési rendelést, majd a **Sorok** lapon válassza az **Értékesítésirendelés-sorok** gyorslapot. A **Minőségi rendelés állapota** oszlop az értékesítési rendelés minden sorának állapotát mutatja.

### <a name="from-purchase-orders"></a>Beszerzési rendelésekből

A beszerzési rendelésekhez kapcsolódó minőségi rendeléseken való munkához menjen az **Beszerzés és források \> Beszerzési rendelések \> Minden beszerzési rendelés** menübe, majd hajtsa végre a következő lépések valamelyikét:

- Nyisson meg egy beszerzési rendelést, vagy válassza ki a rácsban. Ezután a Műveleti panelen a **Fogadás** lap **Minőségkezelési** csoportjában válassza a **Minőségi rendelések** lehetőséget a **Minőségi rendelések** lap megnyitásához. Itt lehet megtekinteni, létrehozni vagy frissíteni a beszerzési rendeléshez kapcsolódó minőségi rendeléseket.
- Nyisson meg egy beszerzési rendelést, majd a **Fejléc** lapon válassza az **Általános** gyorslapot. A **Minőségi rendelés állapota** mező az értékesítési rendeléshez kapcsolódó valamennyi beszerzési rendelés általános állapotát mutatja.
- Nyisson meg egy beszerzési rendelést, majd a **Sorok** lapon válassza a **Beszerzésirendelés-sorok** gyorslapot. A **Minőségi rendelés állapota** oszlop a beszerzési rendelés minden sorának állapotát mutatja.

### <a name="from-production-orders"></a>Termelési rendelésekből

A beszerzési rendelésekhez kapcsolódó termelési rendeléseken való munkához menjen a **Termelésszabályozás \> Termelési rendelések \> Minden termelési rendelés** menübe, majd hajtsa végre a következő lépések valamelyikét:

- Nyisson meg egy termelési rendelést, vagy válassza ki a rácsban. Ezután a Műveleti panelen a **Nézet** lap **Minőség kezelése** csoportjában válassza a **Minőségi rendelések** lehetőséget a **Minőségi rendelések** lap megnyitásához. Itt lehet megtekinteni, létrehozni vagy frissíteni a beszerzési rendeléshez kapcsolódó termelési rendeléseket.
- Nyisson meg egy termelési rendelést, vagy válassza ki a rácsban. A Műveleti panel **Termelési rendelés** lapján a **Termelési részletek** csoportban válassza az **Útválasztás** elemet a **Termelési út** oldal megnyitásához. Az útvonalműveletekkel kapcsolatos minőségi rendelések megtekintéséhez hajtsa végre a következő lépések valamelyikét:

    - Válassza ki a cél útvonalműveletet a rácsban. Ezután a műveleti panelen válassza a **Lekérdezések \> Minőségi rendelések** lehetőséget.
    - A **Művelet száma** mezőben válassza ki az értéket. célútvonal műveletéhez a **Termelési útvonal** részletei oldal megnyitásához. Az **Általános** gyorslapon a **Minőségi rendelés állapota** mező az útvonalművelethez kapcsolódó minőségi rendelések állapotát mutatja.

- Nyisson meg egy termelési rendelést, és válassza az **Általános** gyorslapot. A **Minőségi rendelés állapota** mező a termelési rendeléshez kapcsolódó minőségi rendelések állapotát mutatja.

### <a name="from-quarantine-orders"></a>Karanténrendelésekből

A karanténrendelésekhez kapcsolódó termelési rendeléseken való munkához menjen a **Készletkezelés \> Ismétlődő feladatok \> Minőségkezelés \> Karanténrendelések** menübe, majd hajtsa végre a következő lépések valamelyikét:

- Ellenőrizze a **Minőségi rendelés állapota** oszlopban lévő értékeket. Ily módon meg lehet ismerkedni a rácson belül az egyes karanténrendelésekhez kapcsolódó minőségi rendelések általános állapotával.
- Jelöljön ki egy karanténutasítást a rácsban, majd a Műveleti panelen válassza ki a **Minőségi rendelések** lehetőséget karanténrendeléshez kapcsolódó minőségi rendelések megtekintéséhez, létrehozásához vagy frissítéséhez.

## <a name="advanced-actions-for-quality-orders"></a>Minőségi rendelések speciális műveletei

Az állapot kezelésére, dokumentumok generálása és a további részletek lekérdezése érdekében a minőségi rendeléseken több műveletet is végezhet.

### <a name="reopen-a-quality-order"></a>Minőségi rendelés újranyitása

Az ellenőrzés és a tesztek után alapértelmezés szerint a minőségi rendelés már nem szerkeszthető és nem frissíthető. Bizonyos esetekben előfordulhat azonban, hogy a minőségi rendelést a befejezése után újra kell nyitni.

A minőségi rendelés újranyitásához kövesse az alábbi lépéseket.

1. Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Minőségi rendelések** lehetőségre.
1. Nyisson meg egy ellenőrzött minőségi rendelést, vagy válassza ki a rácsban.
1. A műveleti ablaktáblán válassza ki a **Minőségi rendelés újranyitása** elemet.

### <a name="create-a-certificate-of-analysis-for-a-quality-order"></a>Elemzési tanúsítvány létrehozása minőségi rendeléshez

Az CoA olyan jelentés, amelyet a szervezet minőségbiztosítási csapata generál. Hitelesíti hogy a termék megfelel az egyes szabályozások és követelmények követelményeinek. Előfordulhat, hogy a vevői vagy az Ön földrajzi elhelyezkedésének megfelelő szabályozások CoA-kat írnak elő. Előfordulhat, hogy az iparág, valamint az Ön által kezelt, vásárolt, gyártott vagy eladott alapján van ezekre szükség.

A Supply Chain Management segítségével minőségi rendelésből lehet CoA-t létrehozni. A jelentés tartalmazza a minőségi rendelés minden tesztjének eredményét, ahol az **Elemzési tanúsítvány - jelentés** beállítás értéke *Igen*. Ez a beállítás alapértelmezetten beállítható a **Tesztek** lapon beállított teszt alapján. Felülbírálhatja azonban a beállítást egy adott minőségi rendelés specifikus tesztjeihez.

CoA generálásához egy minőségi rendeléshez kövesse az alábbi lépéseket.

1. Ugorjon a **Készletkezelés \> Időszakos feladatok \> Minőségkezelés \> Minőségi rendelések** lehetőségre.
1. Válassza ki azt a minőségi rendelést, amelyhez CoA-t szeretne létrehozni.
1. Válassza ki a Műveleti panelen a **Lekérdezések \> Elemzési tanúsítvány** lehetőséget.
1. Az **Elemzési tanúsítvány** oldalon a Műveleti panelen válassza az **Új** lehetőséget.
1. Nem kötelező: A **Kapcsolattartó** mezőben válassza ki azt a kapcsolattartót, akinek a tanúsítványt címezni kell.
1. A Művelet ablaktáblán válassza ki a **Nyomtatás** elemet.
1. Az **Elemzési tanúsítvány** párbeszédpanelen határozza meg, hogyan kell kinyomtatni a jelentést. Ezután az **OK** gombot választva kinyomtathatja a jelentést egy nyomtatóra, a képernyőre, egy fájlba vagy e-mailbe.
1. Zárja be a lapokat.

### <a name="block-or-unblock-inventory-for-a-quality-order"></a>Minőségi rendelés készletének zárolása vagy zárolásának feloldása

Amikor a minőségi rendelés automatikusan létrejön egy minőségi társítás alapján, a minőségi társításhoz hozzárendelt cikkmintavétel úgy konfigurálható, hogy a tesztelt referencia teljes készletmennyiséget blokkolja. A cikkmintavételezéssel kapcsolatos további információért lásd: [Minőségkezelési cikk mintavételezése](quality-item-sampling.md).

Ha nem használ teljes zárolást, vagy ha manuálisan hoz létre minőségi rendelést, a rendszer automatikusan létrehoz egy készletzárolási rekordot a minőségi rendelés alapján tesztelt cikkmennyiségre. A **Készletzárolás** lapon létrehozott rekordban a **Készletzárolás típusa** mezője a *Minőségi rendelés* beállításra van állítva.

A **Készletzárolás** lapon kiválasztott minőségi rendelés készletzárolásának megtekintéséhez és szerkesztéséhez válassza a Műveleti panelen a **Lekérdezések \> Készletzárolás** lehetőséget. További információ: [Készletzárolás](inventory-blocking.md).

### <a name="inquire-about-the-details-of-a-quality-order"></a>Minőségi rendelés részleteinek lekérdezése

A **Minőségi rendelések** lap műveleti panelén a következő gombokkal lehet a minőségi rendeléssel kapcsolatos további információkat megtekinteni:

- **Lekérdezések \> Munka részletes adatai** – Megnyithat egy oldalt, ahol megtekintheti a minőségi rendeléshez kapcsolódó raktári munkát.
- **Lekérdezések \> Szabálytalanságok** – Megnyit egy lapot, ahol megtekintheti a minőségi rendeléshez kapcsolódó esetleges szabálytalanságokat.
- **Készlet** – A menü parancsai az összes készlettranzakcióra általánosak. Ezeket a tranzakciók, az aktuális készlet, a foglalások és a jelölések részleteinek megtekintése és frissítése használhatja.

### <a name="create-cases-related-to-quality-orders"></a>Minőségi rendelésekhez kapcsolódó esetek létrehozása

A minőségi rendelésekkel kapcsolatos eseteket lehet létrehozni. Ily módon nyomon követheti a problémák részleteit, és dolgozhat a megoldáson. Ezután az esetkezelés munkafolyamat-funkcióival egy eset előre meghatározott üzleti folyamaton keresztül továbbirányítható, további jóváhagyások megszerzéséhez, illetve további információk lekéréséhez egy adott kérdésről. A tudásbáziscikkek funkció segítségével a gyakori problémák megoldásának tudásbázisát is létrehozhatja.

## <a name="case-management-examples-for-quality-management"></a>Esetkezelési példák a minőségkezelésre

### <a name="example-1"></a>1. példa

Olyan gyártóvállalatnál dolgozik, amely szigorú előírások szerint kell működnie a szabályozott termékek, például az élelmiszer előállításával kapcsolatban. A minőségi rendelésekkel lehet a termelési folyamat során a cikkek minőségére vonatkozó adatokat rögzíteni és nyomon követni. Ha egy minőségi rendelés nem felel meg az egyes teszteken, akkor probléma lehet a berendezésrel. Az esetek segítségével egy üzleti folyamat követhető, és a probléma eszkalálható a megfelelő technikusok számára, hogy meg tudják határozni a kiváltó okát. Hogy könnyebb legyen követni az üzleti folyamatokat a vállalat egy tudásbázist tart fent a fontosabb problémákról, amelyek a minőségi rendelésekhez és berendezésekkel kapcsolatos problémákhoz kapcsolódnak.

### <a name="example-2"></a>2. példa

Egy elosztási vállalatnak dolgozik, amely a különböző országokban és régiókban testreszabható termékeket szállít. Egyes vevőknek szigorú specifikációik vannak, melyeket követni kell. Egyéb esetben díjak és visszaküldések vagy visszaterhelések történhetnek. A minőségi rendelések segítségével nyomon követhetők a vevői követelményeknek megfelelő tesztek és eredmények részletei. Az esetek segítségével lehet áttekintenék és jóváhagyni a CoA adatait, mielőtt a dokumentumot létrehozná és csatolná más szállítási dokumentumokkal együtt.

## <a name="additional-resources"></a>További erőforrások

- [Minőségkezelési folyamatok](quality-management-processes.md)
- [Minőségteszt](quality-tests.md)
- [Minőségteszt-csoportok](quality-test-groups.md)
- [Minőségi társítások](quality-associations.md)
- [Minőségkezelési folyamatok](quality-management-processes.md)
- [A minőség- és a szabálytalanságkezelés engedélyezése](enable-quality-management.md)
- [Raktári folyamatok minőségkezelése](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
