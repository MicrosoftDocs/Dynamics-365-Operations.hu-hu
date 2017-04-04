---
title: "Termékek és termékváltozatok keresése a rendelésbevitel során"
description: "Használja a <strong>Cikkszám</strong> mezőt termékek és termékváltozatok kereséséhez értékesítésirendelés-sor vagy beszerzésirendelés-sor manuális létrehozásakor.  Ez a megoldás lehetővé teszi a termékváltozatok gyors megtalálását, ha csak a konfigurációs karakterlánccal vagy a termék egyik dimenziójával rendelkezik."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: MCRFullTextIndexField, MCRFullTextParameters, PurchTable, SalesTable
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 248534
ms.assetid: 99dd5ce1-0029-4f06-90e7-865e6d46d86e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 5b0f3c1a853f8f5e61dedaf588b6f9d2da3a53b5
ms.lasthandoff: 03/31/2017


---

# <a name="search-for-products-and-product-variants-during-order-entry"></a>Termékek és termékváltozatok keresése a rendelésbevitel során

Használja a <strong>Cikkszám</strong> mezőt termékek és termékváltozatok kereséséhez értékesítésirendelés-sor vagy beszerzésirendelés-sor manuális létrehozásakor.  Ez a megoldás lehetővé teszi a termékváltozatok gyors megtalálását, ha csak a konfigurációs karakterlánccal vagy a termék egyik dimenziójával rendelkezik.

Egyes esetekben, amelyek túl nagy része valami nincs a legjobb helyzetben kell lennie, és ez különösen igaz, ha több hasonló termékek eladása és kívánt cikkszámokat, illetve a termék keresési nevek emlékszik annak érdekében, hogy a jobb termék értékesítési rendelés elhelyezése. Használhatja a **cikkszám** értékesítésirendelés-sor vagy a Keresés mező a beszerzési rendelési sor mezőt. Megadhatja a termék nevének, számának vagy méreteinek bármely részét, és a keresés megjeleníti az összes olyan cikket, amely megfelel a keresőkifejezésnek.

## <a name="how-search-works"></a>A keresés működése
Termékek vagy termékváltozatok keresésekor fontos, hogy megértsük, hogyan találja meg a keresési funkció a beírt szövegnek megfelelő termékeket. A keresési eredmények szállításakor a kulcsfontosságú keresési szabályok a következők:

-   A keresési eredmények minden egyező rekordot visszaadnak, függetlenül a mezőtől, amelybe a keresett szöveget megadták.
-   A keresett szövegnek teljes terjedelmében kell szerepelnie az egyező rekordban.
-   A rendszer akkor is egyezést ad vissza, ha a keresett szöveg az egyező rekordban egy szöveges karaktersor közepén található. Nem kell a szöveges karaktersor elején megjelennie.
-   A keresett szöveget a rendszer egyetlen szöveges karakterláncként kezeli még akkor is, ha üres karaktereket tartalmaz.

### <a name="examples"></a>Példák

Az alábbi példák termékek és termékváltozatok használatával illusztrálják a keresés kezelésének módját különböző helyzetekben. **Előfeltétel:** alatt **értékesítési és marketing &gt;a telepítő &gt;keresési &gt;keresési paraméterek**&gt;**keresés típusú**, jelölje be a **teljes egyezés** lehetőséget.

| Terméktípus     | Termék neve    | Termékszám megjelenítése | Cikkszám | Konfiguráció |
|------------------|-----------------|------------------------|-------------|---------------|
| Egyedi termék | SpeakerMidRange | D0001                  | D0001       | N. a.            |
| Termékváltozat  | Active speaker  | D0010:::Black:         | D0010       | 000005        |
| Termékváltozat  | Active speaker  | D0010:::White:         | D0010       | Fehér         |

Ha a **Cikkszám** mezőbe a „speak” kifejezést írja be, a keresés az összes fenti terméket visszaadja. Ha a **Cikkszám** mezőbe a „black” kifejezést írja be, eredményként a második termék jelenik meg, mert ez tartalmazza a „black” szöveget a termékszám megjelenítése részben. Ez a két példa bemutatja, hogy a keresés nem csak a mező elejét figyeli: a rendszer akkor is egyezést talál, ha a keresett szöveg az egyező rekordban egy szöveges karaktersor közepén található.  

Ha a „05” keresőkifejezést írja be, csak a második termékváltozatot kapja vissza eredményeként, mert a „05” szerepel a konfigurációban. Ez azt mutatja be, hogy a keresés az összes engedélyezett mezőre kiterjed a **Keresési feltételek** oldalon.  

A „speak 05” megadása esetén nem kap eredményt. Ennek az oka az, hogy a keresés a teljes megadott szövegre keres. A keresés nem próbál meg a „speak” kifejezésre keresni, hogy aztán a „05” kifejezésre szűkítse a találatokat.  

Segítségével korlátozhatja a keresési eredmények száma a **eredmények száma** mezőjében a **értékesítési és marketing &gt;telepítő &gt;keresési &gt;keresési paraméterek** oldalon. Ha ezt a mezőt 0-ra állítja, a rendszer minden keresési eredményt visszaad. Ha például 10-re állítja, a rendszer legfeljebb 10 keresési eredményt ad vissza.

## <a name="configure-the-product-search"></a>Termékkeresés beállítása
A termék és termékváltozat keresési funkció használata előtt hajtsa végre a következő lépéseket a termékkeresés konfigurálásához. [![termék keresés beállítása 3 lépések\_AXAppFall](./media/3-steps-to-configure-product-search_axappfall.png)](./media/3-steps-to-configure-product-search_axappfall.png)

### <a name="step-1-include-all-the-relevant-product-and-product-variant-identifiers-and-dimensions-in-the-search-criteria"></a>1. lépés: A keresési feltételek közé vegyen fel minden releváns termék- és termékváltozat-azonosítót és dimenziót

Néhány példa a kereséshez használható termék- és termékváltozat-azonosítókra és dimenziókra: **Terméknév, Cikkszám**, **Termékszám megjelenítése, Konfiguráció, Szín, Méret, Stílus, Keresési név stb.**.  

Keresse fel **értékesítési és marketing &gt;a telepítő &gt;keresési &gt;keresési feltételek** oldalon. A **Keresési feltételek** lap lehetővé teszi a vevő, a potenciális vevő és a termékek keresési feltételeinek meghatározását. Győződjön meg arról, hogy a termék keresési feltételek megadásával szűri a lapot. Ehhez váltson a **Termék** lehetőségre a lap menüjében.  

A megjelenített termék száma a keresési feltétel hozzáadásához kattintson **új** a lap menü. Ez lesz az új rekord hozzáadása a **keresési feltételek** rács. Nyissa meg a **Mezőnév** oszlop keresési lehetőségét, és válassza a **DisplayProductNumber** lehetőséget. A termék konfigurációs felvenni a keresési feltételek, hozzon létre egy új bejegyzést a ** keresési feltételek ** rács és a kiválasztott **configId** a a **mező neve** oszlop. Azonos módon hozzon létre egy rekord, amelynél a **Mezőnév** **InventColorId** a színdimenzió esetében, **InventSizeId** a méretdimenzió esetében és **InventStyleId** a stílusdimenzió esetében.

### <a name="step-2-populate-the-database-table-that-is-used-for-product-search"></a>2. lépés: Töltse fel a termékkereséshez használt adatbázistáblát

A **Keresési feltételek** lapon kattintson a **Keresési adatok frissítése** gombra. Ellenőrizze, hogy a **Keresési adatok frissítése** párbeszédpanelen a **Forrás** beállítása **Termék**, és kattintson az **OK** gombra. A rendszer egy táblázat összegzi az 1. lépésben megadott összes kiválasztott keresési feltételek. Ha sok termékek és termékváltozatok, lehet, hogy ez a művelet meglehetősen hosszú, és egy figyelmeztetés jelenhet meg. Azt ajánljuk, hogy a keresési tábla feltöltését a kötegkiszolgálón olyan időpontra ütemezze, amikor a kiszolgáló nincs túlságosan leterhelve.  

Mindaddig, amíg a tábla nincs feltöltve, a termékkeresés nem ad helyes eredményeket. Ha nem jelenik meg keresési eredmény, győződjön meg arról, hogy a tábla fel legyen töltve.  

A táblát csak akkor kell feltölteni, ha módosítja a keresési feltételeket. A rendszer az újonnan megjelent termékeket és változatokat automatikusan hozzáadja a táblához. A rendszer a törölt termékeket és változatokat automatikusan eltávolítja a táblából.

### <a name="step-3-enable-the-lookup-for-product-search-on-sales-and-purchase-order-lines"></a>3. lépés: Engedélyezze a kikeresést a termékkeresés számára az értékesítési és beszerzési rendelési sorokon

Méretéről engedélyezheti ezt a funkciót **értékesítési és marketing &gt;telepítő &gt;keresési &gt;keresési paraméterek** és **keresés engedélyezése keresési** a **Igen** a a **általános** lap.  

Az értékesítési rendelési sor bejegyzéseinek esetében az alapértelmezett viselkedés a **Termékkeresés** oldal megnyitása, amikor elkezd írni a **Cikkszám** mezőben, majd megnyomja a **tabulátor** gombot. A **Termékkeresés** oldal módosítja a kontextust a rendelési sor létrehozásakor, amit néhány felhasználó feleslegesen beavatkozásnak tekinthet. Ha szeretné a keresési eredményeket megkapni a kikeresésnél, és nem szeretné elveszíteni a kontextust a rendelési sorok bevitelekor, használja a keresési kikeresést. Ha termékre vagy termékváltozatra keres, de nem választ semmit a kikeresésnél, majd megnyomja a **tabulátor** gombot, a **Termékkeresés** lap jelenik meg.


