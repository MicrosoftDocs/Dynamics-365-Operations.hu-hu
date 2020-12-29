---
title: A termelési üzem végrehajtási felületének konfigurálása
description: Ez a témakör azt mutatja be, hogyan lehet egy vagy több konfigurációt létrehozni a termelési üzem végrehajtási felületéhez. Amikor megnyitja a termelési üzem végrehajtási felületét, a program automatikusan betölti a kiválasztott konfigurációt és a feladatra vonatkozó szűrőket, amelyek a böngészővel és az eszközzel kapcsolatosak. A konfigurációban be kell állítania azokat a szabályokat, amelyek az adott használathoz szükségesek.
author: johanhoffmann
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: ff68761ce1cf2174be8ebb9732b9348439a53a32
ms.sourcegitcommit: d24ebce50421f8656d23bb1e47cd636ad2e2ca0a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/02/2020
ms.locfileid: "4664296"
---
# <a name="configure-the-production-floor-execution-interface"></a>A termelési üzem végrehajtási felületének konfigurálása

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

A termelési üzem végrehajtási felületét az üzemszinten dolgozók használják a napi munkájuk regisztrálására, például, hogy mikor kezdtek el egy feladatot, a feladatokkal kapcsolatos visszajelzésekhez, a közvetett tevékenységek regisztrálására és a távollétek jelentésére. Ezek a regisztrációk alapot biztosítanak a termelési rendelések előrehaladásának és a költségeinek a nyomon követésére és a dolgozók fizetése kiszámításának alapjául szolgálnak.

Amikor megnyitja a termelési üzem végrehajtási felületét, a program automatikusan betölti a kiválasztott konfigurációt és a feladatra vonatkozó szűrőket, amelyek a böngészővel és az eszközzel kapcsolatosak. A konfigurációban be kell állítania azokat a szabályokat, amelyek az adott használathoz szükségesek. Íme néhány használati példa:

- A vállalati csarnokban lévő eszköznél az alkalmazottak beblokkolnak, mikor megjönnek, és a nap végén távozáskor kiblokkolnak.
- Az üzemi szinten an egy gép, amelyen a gépkezelők rögzítik egy munka megkezdésének és befejezésének idejét. Ezenfelül szüneteket és közvetett tevékenységeket is rögzítenek.

Ez a témakör a feladatkártya-eszközök konfigurálásához szükséges különböző beállításokat ismerteti.

## <a name="turn-on-the-production-floor-execution-interface-and-its-related-optional-features"></a>A termelési üzem végrehajtási felületének és a kapcsolódó választható funkcióinak bekapcsolása

A termelési üzem végrehajtási felületét, valamint a jelen témakörben leírt választható számos beállítást is be kell kapcsolni a rendszerben, mielőtt azokat használni lehetne. A [Funkció kezelése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lapon bekapcsolhatja a következő alszakaszokban ismertetett funkciók egyikét vagy mindegyikét szükség szerint.

### <a name="the-production-floor-execution-interface"></a>A termelési üzem végrehajtási felülete

Ez a témakörben leírt elsődleges funkció. Hozzáadja a termelési üzem végrehajtási felületét a rendszeréhez. Az engedélyezéséhez kapcsolja be a következő funkciót a [funkciókezelésben](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):  
- Termelési üzem végrehajtása

### <a name="generate-license-plates"></a>Azonosítótáblák előállítása

Ezek a funkciók elérhetővé teszik az azonosítótábla funkciót a termelési üzem végrehajtási felületéhez. Ha használni szeretné őket, kapcsolja be a [funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) modulban a következő szolgáltatásokat (ebben a sorrendben):

1. A Feladatkártya eszközhöz hozzáadott, készként történő jelentéshez használt azonosítótábla
1. Az azonosítótábla-szám automatikus létrehozásának engedélyezése, amikor a feladatkártya eszközében befejezettként jelentik

### <a name="print-labels"></a>Címkék nyomtatása

Ezek a funkciók elérhetővé teszik a címkenyomtatás funkciót a termelési üzem végrehajtási felületéhez. Ha használni szeretné őket, kapcsolja be a [funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) modulban a következő szolgáltatásokat (ebben a sorrendben):

1. A Feladatkártya eszközhöz hozzáadott, készként történő jelentéshez használt azonosítótábla
1. Címke nyomtatása a Feladatkártya eszközéből

### <a name="allow-locking-the-touch-screen"></a>Az érintőképernyő zárolásának engedélyezése

Ez a funkció egy gombot vesz fel a termelési üzem végrehajtási felületére, amely lehetővé teszi, hogy a dolgozók megtisztítsák a képernyőt. Ha használni szeretné, kapcsolja be a következő funkciót a [funkciókezelésben](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- A feladatkártya-eszköz és a feladatkártya-terminál zárolására alkalmas funkció az eszközök fertőtlenítése érdekében

## <a name="work-with-production-floor-execution-configurations"></a>A termelési üzem végrehajtási konfiguációinak használata

Az eszközök konfigurációinak létrehozásához és karbantartásához nyissa meg a **Termelési vezérlő \> Beállítások \> Gyártásvégrehajtás \>Termelési üzem végrehajtásának konfigurálása** elemet. A **Termelési üzem végrehajtásának konfigurálása** lapon látható a meglévő konfigurációk listája. Ezen az oldalon az alábbi műveleteket végezheti:

- Kiválaszthatja bal oldali oszlopban felsorolt termelésiüzem-konfigurációk bármelyikét, hogy megtekintse és szerkessze azt.
- Új eszközkonfiguráció hozzáadásához listához a műveleti ablaktáblán válassza az **Új** lehetőséget. Adjon meg egy nevet a **Konfiguráció** mezőben, amely lehetővé teszi az új konfiguráció azonosítását. Az itt megadott névnek egyedinek kell lennie az összes eszköz-konfiguráció között, és később már nem szerkeszthető.

Ezután konfigurálja a különböző beállításokat a kiválasztott eszköz konfigurációjában. Az alábbi mezők állnak rendelkezésre:

- **Mennyisége jelentése távozáskori blokkoláskor** – Ezt állítsa *Igen* értékre, és megkérheti a dolgozókat, hogy adjanak visszajelzést a folyamatban lévő munkákról a távozáskori blokkoláskor. Ha *Nem* értékre van állítva, akkor a dolgozókat nem figyelmezteti a rendszer.
- **Alkalmazott zárolása** – Ha a beállítás értéke *Nem*, akkor a program közvetlenül a regisztráció után (például új feladat) kilépteti a dolgozókat. Az eszköz visszatér a bejelentkezési oldalra. Ha a beállítás értéke *Igen*, akkor a dolgozók bejelentkezve maradnak a feladatkártya-eszközbe. Előfordulhat azonban, hogy egy dolgozó manuálisan kijelentkezik annak érdekében, hogy egy másik dolgozó jelentkezzen be, miközben a feladatkártya-eszköz továbbra is ugyanazon a rendszerszintű felhasználói fiókon fut. A fiókok típusairól a [Hozzárendelt felhasználók](config-job-card-device.md#assigned-users) című témakörben olvashat bővebben.
- **A regisztráció tényleges időpontjának használata** – Ezt a beállítást *Igen* értékre állíthatja, ha azt szeretné, hogy az egyes új regisztrációk időpontja megegyezzen a dolgozó által benyújtott regisztráció pontos időpontjával. Ha a beállítás értéke *Nem*, akkor a bejelentkezési időt használja a rendszer. Ezt a beállítást általában *Igen* értékre kell állítani, ha *Igen* értékre állította az **Alkalmazott zárolása** és/vagy az **Egy dolgozó** beállítást, aminek következtében a dolgozók általában hosszabb ideig bejelentkezve maradnak.
- **Egyetlen dolgozó** – Állítsa ezt a beállítást *Igen* értékre ha csak egy dolgozó használja a feladatkártya-eszközt, ha ez a konfiguráció aktív. Ha a beállítás értéke *Igen* akkor az **Alkalmazott zárolása** beállítás automatikusan *Igen* értékre lesz állítva. Ezenkívül ez a beállítás eltávolítja a dolgozónak a belépőkártya-azonosító (vagy hasonló) használatával történő bejelentkezésre vonatkozó követelményét (és képességét). Ehelyett a dolgozó a Microsoft Dynamics 365 Supply Chain Management alkalmazásba egy olyan rendszerfelhasználói fiókkal jelentkezik be, amely egy *időregisztrált dolgozóhoz* van társítva (a *dolgozók* táblából), és dolgozóval egy időben bejelentkezik a feladatkártya eszközbe.
- **Az érintőképernyő zárolásának engedélyezése** – Ezt a beállítást *Igen* értékre engedélyezheti a dolgozók számára, hogy zárolják a feladatkártya-eszköz érintőképernyőjét, hogy fertőtleníthessék azt. Ha a beállítás értéke *Igen*, akkor a rendszer hozzáad egy **Fertőtlenítési célú zárolási képernyőt** az eszköz bejelentkezési lapjához. Amikor egy dolgozó kiválasztja ezt a gombot, az érintőképernyő ideiglenesen zárolódik a véletlen bevitel elkerülésének céljára. Ezenfelül megjelenik egy időzítő. A dolgozó ezután biztonságosan megtisztíthatja a készüléket és a képernyőt. Amikor a visszaszámlálás befejeződött, az érintőképernyő automatikusan feloldódik.
- **Képernyő zárolásának időtartama** – Ha a **Képernyő zárolásának engedélyezése** beállítást *Igen* értékre állították akkor ezzel a beállítással adja meg, hogy hány másodpercig kell zárolni az érintőképernyőt a fertőtlenítéshez. Az időtartamnak 5 és 120 másodperc között kell lennie.
- **Azonosítótábla előállítása** – Ezt a lehetőséget *Igen* értékre állítsa új azonosítótábla előállításához minden alkalommal, amikor a dolgozó a feladatkártya eszközt készre jelentéshez használja. Az azonosítótábla a **Raktárkezelési paraméterek** lapon beállított számsorozatból jön létre. Ha a beállítás értéke *Nem*, akkor a dolgozóknak a készként való jelentéskor meg kell határozniuk egy meglévő azonosítótáblát.
- **Címke nyomtatása** – Ez a lehetőséget állítsa *Igen* értékre egy azonosítótábla-címke nyomtatásához, amikor a dolgozó a feladatkártya eszközt használja készre jelentéshez. A címke konfigurációja a dokumentumirányításban van beállítva, a [Dokumentumirányítási elrendezés azonosítótábla-címkékhez](../warehousing/document-routing-layout-for-license-plates.md) részben leírtak szerint.
- **Lap kiválasztása** – A szakasz beállításaival kiválaszthatja, hogy mely lapok jelenjenek meg a termelési üzem végrehajtási felületén, amikor az aktuális konfiguráció aktív. A tetszőleges számú lapot tervezhet meg, és szükség szerint hozzáadhatja és elrendezheti őket. A lapok tervezésével és az itt megadott beállításokkal kapcsolatos további tudnivalókat lásd: [A termelési üzem végrehajtási felületének tervezése](production-floor-execution-tabs.md).

## <a name="clean-up-job-configurations"></a>Feladatkonfigurációk megtisztítása

Amikor az üzemfelügyelő beállítja a termelési üzem végrehajtási felületét, kiválaszta a konfigurációt és a feladatra vonatkozó szűrőket. Ezeket a beállításokat egy hivatkozási táblában tárolja a Supply Chain Management alkalmazásban, és a böngésző egy helyi sütit tartalmazó azonosítót használ a tábla helyes sorának megtalálására. A tábla azt a dátumot és időpontot is bejegyzi, amikor a dolgozó utoljára bejelentkezett az egyes eszközökre.

A kötegelt feladat időszakonként törli a hivatkozásokat tartalmazó tábla azon elemeit, amelyek a legutóbbi 60 napban nem naplóztak tevékenységet. Az alábbi lépések követésével bármikor manuálisan is megtisztíthatja a tételeket.

1. Lépjen a **Gyártásvezérlés \> Beállítás \> Gyártásvégrehajtás \> termelési üzem végrehajtásának konfigurálása** részre.
1. A műveleti ablaktáblán válassza az **Ügyfélkonfigurációk megtisztítása** elemet.
1. Az **Ügyfélkonfigurációk megtisztítása** párbeszédpanelen állítsa be a **Napok száma** mezőt az (aktuális nap előtti) szükséges inaktivitási napok megadásához. A program minden olyan eszköz konfigurációját és bejelentkezési rekordját eltávolítja, amely nem volt aktív a megadott időszakban.
1. A **Napok száma** beállítás alapján megfelelő konfigurációk megtisztításához kattintson az **OK** gombra.
