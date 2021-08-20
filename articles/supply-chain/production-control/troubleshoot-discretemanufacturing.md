---
title: Elkülönített gyártás – hibaelhárítás
description: Ez a témakör azt mutatja be, hogyan lehet javítani az elkülönített gyártás használata során felmerülő problémákat.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 895126d9c80c2eb6328c5c6c24140d1a7dc0818762f3f93c737a7858843d3eb7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6780028"
---
# <a name="troubleshoot-discrete-manufacturing"></a>Elkülönített gyártás – hibaelhárítás

Ez a témakör azt mutatja be, hogyan lehet javítani az elkülönített gyártás használata során felmerülő problémákat.

## <a name="i-receive-the-following-error-message-warehouse-management-processes-are-currently-being-used-if-work-lines-are-not-yet-registered-you-can-cancel-the-created-work-and-any-load-or-shipment-lines-and-then-continue-with-the-picking-or-shipping-process"></a>A következő hibaüzenet jelenik meg: „A raktárkezelési folyamatok jelenleg használatban vannak. Ha a munkasorok még nincsenek regisztrálva, visszavonhatja a létrehozott munkát és a rakomány- vagy szállítólevélsorokat, majd folytathatja a kitárolási vagy szállítási folyamatot."

### <a name="issue-description"></a>Probléma leírása

Ez a probléma akkor fordul elő, ha munkát próbál lefoglalni vagy kiadni egy sorhoz, de a készlettranzakció állapota *Kitárolva* értéken van, ami azt jelzi, hogy az anyag ki lett tárolva.

### <a name="issue-resolution"></a>Probléma megoldása

Ezen hiba javításához kövesse az alábbi lépések egyikét.

- Módosítsa a termelési rendelés állapotát *Becsült* vagy *Kiadott* értékre.
- Nyissa meg a részletek lapot a releváns termelési rendeléshez. A Művelet panel **Raktár** fülének **Leállítás** csoportjában válassza a **Leállítás és visszatárolás** lehetőséget, és törölje a jelet az összes tranzakció visszatárolásához. Ezután válassza a **Leállítás eltávolítása** lehetőséget a termelési rendelés feldolgozásához.

Itt van egy magyarázat a *Kitárolás* és *Leállítás* funkciókhoz:

- **Visszatárolás** – Ez a funkció visszaállítja a darabjegyzék- (BOM) és receptúrasorok *Kitárolt* és *Megrendelt* állapotú készlettranzakcióit. Amikor a nyersanyag-kitárolási munka befejeződött, a sorok állapota *Kitárolt* értékre lesz állítva. Ez az állapot megakadályozza, hogy a termelési rendelést visszaállítsák *Létrehozva* állapotúvá. Ebben az esetben a *Kitárolás* funkcióval visszaállíthatja a tranzakciókat a *Kitárolt* állapotból, majd visszaállíthatja a termelési rendelést *Létrehozva* állapotra.
- **Leállítás** – Ez a funkció **Leállított** jelölőt állít be a termelési rendelésen, hogy megakadályozza a rendelés állapotfrissítését. A **Leállított** jelző a gyártási rendelés részleteinek **Raktár** gyorslapján található.

> [!NOTE]
>
> - A gombok csak akkor láthatók, ha a gyártási rendelést a raktározási folyamatokhoz engedélyezett cikkekhez hozták létre.
> - A **Leállítás** csoport csak a gyártási rendelés részleteinek Művelet panelének **Raktár** lapján látható. Nem látható a **Termelési rendelések** listaoldalának **Raktár** gyorslapján.

## <a name="the-matching-resource-name-isnt-updated-after-i-change-a-worker-name-in-the-global-address-book"></a>Az egyező erőforrásnév nem frissül, miután módosította egy dolgozó nevét a globális címjegyzékben.

### <a name="issue-description"></a>Probléma leírása

Ha módosította egy dolgozó nevét a globális címjegyzékben, akkor az egyező erőforrásnév nem frissül az erőforráscsoport alapban.

### <a name="issue-resolution"></a>Probléma megoldása

Ez a forgatókönyv jelenleg nem támogatott. A probléma megoldásához manuálisan kell frissítenie az erőforrás nevét.

## <a name="when-i-create-a-new-production-order-i-dont-receive-the-following-message-insert-the-active-version-of-bill-of-material-and-route"></a>Amikor új termelési rendelést hozok létre, nem jelenik meg a következő üzenet: „Az anyagjegyzék és az útvonal aktív verziójának beszúrása?”

### <a name="issue-description"></a>Probléma leírása

Új termelési rendelés létrehozásakor a cikkszám megadása után a **Hely** és **Raktár** mezők automatikusan a késztermékek **Alapértelmezett rendelési beállítások** lapján megadott alapértelmezett helyre és raktárra lesznek beállítva. Ezenkívül az aktív anyagjegyzékszám és az útvonalszám is automatikusan meg lesz adva. Nem jelenik meg a következő üzenet, amely az értékekre vonatkozó utasításokat kéri:

> Szúrja be az aktív verziót az anyagjegyzékhez és az útvonalhoz?

### <a name="issue-resolution"></a>Probléma megoldása

Ha az **Alapértelmezett rendelési beállítások** lapon kiválaszt egy olyan terméket, amelyhez egy hely és egy raktár van megadva, a program nem kéri az anyagjegyzék- és útvonalszámok megadását. A program csak akkor kéri, ha ezek az értékek nincsenek megadva a kijelölt termékhez.

## <a name="production-orders-arent-shown-on-the-marking-page"></a>A termelési rendelések nem jelennek meg a Jelölés oldalon.

### <a name="issue-description"></a>Probléma leírása

Egyes termelési rendelések nem jelennek meg a **Jelölés** oldalon.

### <a name="issue-resolution"></a>Probléma megoldása

A következő konfigurációval rendelkező termékeket nem lehet megjelölni. Ezért ezek nem jelennek meg a **Jelölés** oldalon:

- A termékek *Tényleges súly* típusú termékekként vannak meghatározva.
- Ezek engedélyezve vannak a speciális raktári folyamatokhoz.
- Úgy vannak konfigurálva, hogy az *Elszámolóár* elve szabályozza őket.

## <a name="when-i-try-to-end-a-production-order-i-receive-the-following-error-message-calculating-bom-consumptioncost-value-must-be-negative-upon-issue-from-inventory"></a>Amikor egy termelési rendelést próbálok befejezni, a következő hibaüzenet jelenik meg: „Az anyagjegyzék-felhasználás költségértékének kiszámításának negatívnak kell lennie a készletből történő kiadáskor.”

A problémát a 10.0.15-ös kiadás javította.

## <a name="when-the-status-of-a-production-order-is-changed-from-reported-as-finished-to-end-i-receive-the-following-error-messages-update-conflict-the-standard-cost-does-not-match-with-the-financial-inventory-value-after-the-update-and-a-critical-error-has-occurred-in-function-inventcostmovementcheckvariance"></a>Amikor egy termelési rendelés állapota Készként jelentve befejezéskor értékről Befejezve értékre változik, a következő hibaüzenetek jelennek meg: "Frissítési ütközés. Az elszámolóár nem egyezik meg a pénzügyi készlet értékével a frissítés után" és „Kritikus hiba történt az InventCostMovement.checkVariance függvényben.”

A probléma oka az, hogy a háttéradatokat egy másik folyamat módosította. A folyamat legfeljebb ötször próbálja meg frissíteni az adatokat. Ha az ütközés öt kísérlet után is fennáll, a következő hibaüzenetek jelennek meg:

> Frissítési ütközés. Az elszámolóár nem egyezik meg a frissítés utáni pénzügyi készletértékkel.

> Kritikus hiba történt az InventCostMovement.checkVariance függvényben.

Ez szándékosan van. A probléma enyhítése érdekében folytassa a kötegelt feladatot. A futtatásnak be kell fejeződnie.

Ha a kötegelt feladat a folytatás után folyamatosan sikertelen, ellenőrizze, hogy a főkönyv alapértelmezett pénznemének kerekítési pontossága megfelel-e az InventSum tábla értékére alkalmazott kerekítésnek. Ha a kerekítési pontosság nem megfelelő értékre módosult, valószínűleg vissza kell állítania egy megfelelő értékre. Keresse meg a **ModifiedDateTime** lehetőséget. Ebben az esetben az érték általában azt mutatja, hogy a kerekítési pontosság nemrég megváltozott.

## <a name="when-i-release-to-a-warehouse-i-receive-the-following-error-message-item-rm-could-not-be-fully-reserved-ensure-that-the-full-quantity-is-available-or-reserve-the-items-manually-if-the-reservation-field-on-the-bom-line-is-set-to-manual-or-started-could-not-release-the-order-to-warehouse-because-some-materials-could-not-be-reserved-however-the-status-is-updated-to-released"></a>Amikor kiadok egy raktárnak, a következő hibaüzenet jelenik meg: „Az RM cikk nem foglalható le teljesen. Győződjön meg arról, hogy a teljes mennyiség rendelkezésre áll, vagy foglalja le a cikkeket manuálisan, ha az anyagjegyzéksor Foglalás mezőjének beállítása Manuális vagy Elindítva értéken van. Nem sikerült kiadni a rendelést a raktárba, mert bizonyos anyagokat nem lehetett lefoglalni.” Az állapot azonban Kiadott állapotra frissül.

### <a name="issue-description"></a>Probléma leírása

Ha a termelési rendelés kiadásakor fizikailag nem minden anyagjegyzéksor-cikk érhető el, és a **Kiadás raktárba** irányelv *Teljes foglalás szükséges* értékre van állítva a termelési rendelésen, akkor a következő hibaüzenet jelenik meg:

> Az RM cikk nem foglalható le teljesen. Győződjön meg arról, hogy a teljes mennyiség rendelkezésre áll, vagy foglalja le a cikkeket manuálisan, ha az anyagjegyzéksor Foglalás mezőjének beállítása Manuális vagy Elindítva értéken van. Nem sikerült kiadni a rendelést a raktárba, mert bizonyos anyagokat nem lehetett lefoglalni.

### <a name="issue-resolution"></a>Probléma megoldása

Ez a viselkedés szándékos, és a várt módon működik.

## <a name="when-i-try-to-end-a-production-order-and-report-as-finished-i-receive-the-following-error-message-total-good-quantity-reported-as-finished-for-the-production-will-be-1-feedback-for-the-last-operation-is-000-in-total"></a>Amikor megpróbálok befejezni egy termelési rendelést, és készként jelenteni, a következő hibaüzenet jelenik meg: „A termelés teljesen készként jelentett árumennyisége %1 lesz. Az utolsó művelet visszajelzése 0,00 az összesből.”

### <a name="issue-description"></a>Probléma leírása

Amikor kész naplóként próbál feladni egy jelentést egy termelési rendelésen, a következő hibaüzenet jelenik meg:

> A termeléshez befejezettként jelentett összes hibátlan mennyiség %1 lesz. Az utolsó művelet visszajelzése 0,00 az összesből.

### <a name="possible-cause"></a>Lehetséges ok

Ez a probléma akkor fordul elő, ha az utolsó műveletekben könyvelt mennyiségek helytelenek voltak. Ha például a termelés elindult, de a beindítandó mennyiség nincs lefoglalva, az útvonalkártya naplósorok nélkül kerül feladása. A helyzet megerősítéséhez nyissa meg a termelési rendelést, majd a Művelet panel **Nézet** fülön válassza az **Útvonalkártya** lehetőséget.

### <a name="workaround"></a>Megkerülő megoldás

A probléma megoldásához további naplókat adhat fel azokra a műveletekre vonatkozóan, amelyekhez a naplókat nem megfelelően könyvelték. Indítsa újra a termelési rendelést, és válassza a további naplók könyvelését. Ez a művelet nem indítja el a termelési rendelést, de könyveli a naplókat. Az útvonalkártyának ekkor meg kell jelennie a feladott mennyiségek között, és be kell tudnia fejezni a termelési rendeléseket.

## <a name="can-i-report-a-production-order-as-finished-while-i-report-the-error-quantity-but-not-while-i-report-the-time-or-material-quantity"></a>A termelési rendelést készként jelenthetem, amíg a hibamennyiséget jelentem, de az idő- vagy anyagmennyiség jelentése alatt nem?

A hibamennyiséget csak akkor jelentheti egy termelési rendelésen, ha a megfelelő mennyiséget is jelenti. Ez a forgatókönyv **nem** támogatott. A készként jelentett frissítés végül sikertelen lesz, amikor megpróbálja lemondani a termelési rendelést, és a következő hibaüzenet jelenik meg:

> Hiányzó befejezettként jelentett mennyiség.

## <a name="can-i-trace-the-serial-numbers-of-finished-goods-against-the-serial-numbers-of-consumed-goods"></a>Nyomon követhetem a késztermékek sorozatszámát a felhasznált áruk sorozatszámával?

A késztermékek sorozatszáma nem követhető nyomon a termelési rendelés által a késztermékek előállításához felhasznált anyagok sorozatszámával. Ez a forgatókönyv jelenleg nem támogatott. A megoldás az, hogy 1-es mennyiségre hoz létre termelési rendeléseket.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]