---
title: Készlet költségszámítási gyakori kérdések
description: Ez a cikk megválaszol néhány, a Microsoft készletköltségszámítását kapcsolatban leggyakrabban feltett kérdést Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 05/03/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-05-03
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 5a1d86e7e9cca159d0a820680714a08dc73c0688
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/29/2022
ms.locfileid: "9068393"
---
# <a name="inventory-costing-faq"></a>Készlet költségszámítási gyakori kérdések

[!include [banner](../includes/banner.md)]

Ez a cikk megválaszol néhány, a Microsoft készletköltségszámítását kapcsolatban leggyakrabban feltett kérdést Dynamics 365 Supply Chain Management.

## <a name="inventory-close-adjustments-and-recalculation"></a>Készletzárás, helyesbítések és újraszámítás

### <a name="is-the-inventory-close-required"></a>Szükséges a készletzárás?

Ha a készletarchiválási funkciót tervezi használni, a készletzárást meg kell adni. Ha nem tervezi a készletarchiválási funkció használatát, javasoljuk, hogy a használt költségszámítási modellektől függetlenül futtassa a készletzárást.

### <a name="how-often-should-the-inventory-close-be-run"></a>Milyen gyakran fusson a készletzárás?

A készletzárást főkönyvi időszakonként legalább egyszer le kell futtatni. Ha például a főkönyv beállítása naptári hónap alapú pénzügyi naptár, akkor a készletzárást havonta egyszer kell futtatnia.

### <a name="is-the-inventory-recalculation-required"></a>Szükséges a készlet újraszámítása?

Nem, a készlet-újraszámítás nem szükséges. Ha időszakos költségszámítási modellt használ, például elsőként be, elsőként ki (FIFO), utolsóként be, elsőként ki (LIFO) vagy súlyozott átlagot, gondosan mérlegelje, hogy futtatja-e a készlet-újraszámítást. Pontosabb költségszámítást tesz elérhetővé a kiválasztott heuristic modellben.

### <a name="how-often-should-the-inventory-recalculation-be-run"></a>Milyen gyakran kell futtatni a készlet-újraszámítást?

Ha azt tervezi, hogy futtatja a készlet-újraszámítást, érdemes megfontolni a napi futtatást kötegfolyamatként. Ha szervezete nem igényli a készletértékek gyakori jelentését az időszakos költségszámítási modellekhez, érdemes lehet ritkábban végezni a készletszámítást.

### <a name="when-should-i-use-the-on-hand-inventory-adjustment-on-the-closing-and-adjustments-page"></a>Mikor kell az aktuális készlet korrekcióját használni a Zárás és helyesbítések lapon?

Az aktuális készlet korrekciója csak a készletzárás befejezése után futtatható. Általában az utolsó zárás utáni dátumon futtatják. Az aktuális készlet korrekciója csak azt a készletet korrigálhatja, amely a korrekció futtatásakor még aktuális készletben van.

### <a name="when-should-i-use-the-inventory-transaction-adjustment-on-the-closing-and-adjustments-page"></a>Mikor kell használni a készlettranzakció helyesbítését a Zárás és helyesbítések lapon?

A készlettranzakció helyesbítését készletzárás futtatása előtt kell használnia. Rendszerint helytelen bevételezés javíthatja ki. Készletzárás futtatása és a tranzakció kiegyenlítet követően nem lehet feladni a készlettranzakció-helyesbítést.

### <a name="are-purchase-order-returns-treated-like-other-issues-during-the-inventory-close"></a>A beszerzési rendelések visszaküldése a készletzárás során a többihez hasonló módon kezelendő?

Igen. A beszerzési rendelés bevételezése olyan kiadás, amely a cikkhez kiválasztott heuristic modellben egy bevételezéshez van kiegyenlítve. Ha időszakos költségszámítási modellt használ, a jelöléssel felülbírálhatja a heurista költséget.

### <a name="what-happens-to-sales-order-returns-during-the-inventory-close"></a>Mi történik az értékesítési rendelések visszaküldése a készletzárás során?

A készletzárás futtatásakor az értékesítési rendelés visszáruja bevételezésként van kezelve a készletbe. A problémák a cikkhez kiválasztott heurista modell alapján, a készlettel szemben vannak kiegyenlítve.

### <a name="what-cost-price-is-used-on-a-sales-order-return"></a>Milyen önköltségi árat használ egy értékesítési rendelés visszáruja?

Értékesítési rendeléshez kapcsolódó visszáru létrehozásakor az Egységár mező értékét a **program** az eredeti értékesítési rendelésből másolja át, **és** a visszáru visszáru-önköltségi ár mezőjében a visszaküldött rendelési sorhoz tartozó eredeti készlettranzakcióban beállított önköltségi ár lesz beállítva. Ha a **kapcsolódó készlettranzakció** *Nyitott* érték beállítása Igen, a készletzárás az eredeti értékesítési rendelés kiadási költségének frissítését okozhatja. Ebben **az esetben** a Visszáru önköltségi ár mezője nem frissül. Ugyanakkor a visszárurendelés csomagjegyzékének feladott összege esetén a rendszer ellenőrzi az önköltségi árat, és a frissített költséget használja a visszáru-készlettranzakcióban.

Az értékesítési rendelésekhez kapcsolódó elszámoló áras cikkek visszáruja esetén a rendszer az eredeti értékesítési rendeléstől származó elszámoló költséget fogja használni, még akkor is, ha a cikkhez új elszámoló költség van aktiválva.

Ha olyan visszárut hoz létre, amely nem értékesítési rendeléshez kapcsolódik, **akkor** a Visszáru önköltségi ár mezője az aktív cikkára lesz annak a cikknek a telephelyen, amelyről a visszárurendelést létrehozza. Ha nincs aktív önköltségi ár a cikk költségszámítási verziójában, az érték 0 (nulla). Ha az értéket nullaként (0) hagyja, egy figyelmeztetés jelenik meg, amely szerint nincs megadva a visszáru-tétel azonosítója vagy a visszáru önköltségi ára.

### <a name="what-is-the-expected-performance-of-the-inventory-close"></a>Milyen teljesítményre számít a készletzárás?

Számos tényező befolyásolhatja a készletzárás teljesítményét. A tényezők közé tartozik a cikkek száma, az adott időszakban tranzakciók összesített száma, a használt készletmodellek, valamint a készlet- és raktárkezelési paraméterek között konfigurált kötegsegítők száma. A zárás akár néhány percig vagy akár több óráig is eltarthat. Nincs konkrét útmutatás arra vonatkozóan, hogy mennyi ideig tart, hogy a lezárás lefuthat. A készletzárás teljesítményének nem megfelelő üzleti követelményeit meg kell határoznia, és szorosan együtt kell működnie a partnerével, hogy meghatározza a készletzárási folyamat ütemezését. Ha váratlanul alacsony teljesítményt tapasztal a készletzárási folyamatban, egy támogatási jegyet kell megnyitnia.

## <a name="costing-sheet-and-indirect-costs"></a>Költségszámítási táblázat és közvetett költségek

### <a name="which-costing-models-support-the-costing-sheet"></a>Mely költségszámítási modellek támogatják a költségszámítási táblázatot?

Bár a költségszámítási táblázatot általában az elszámolóátszámítást alkalmazzák, az ellátásilánc-kezelésben elérhető bármely költségszámítási modellhez használható.

### <a name="can-i-have-multiple-costing-sheets-for-various-parts-of-my-organization"></a>Lehet több költségszámítási lap a szervezet különböző részeihez?

Nem. Jogi személyenként csak egy költségszámítási táblázat lehet.

### <a name="can-i-have-different-costing-sheets-for-each-site"></a>Lehet különböző költségszámítási táblázatok az egyes helyekhez?

Nem, nem lehet minden telephelyhez eltérő költségszámítási táblázat. Jogi személyenként csak egy költségszámítási táblázatot hozhat létre. Helyenként azonban konfigurálhat összcsomópontokat, költségcsoportokat és közvetett költségcsomópontokat. Ez a konfiguráció manuális folyamat, és szervezeti vagy üzemeltetési változások esetén a költségszámítási táblázatban meg kell tartani a hierarchia és a cikk-hozzárendeléseket. Ha egy cikket egynél több helyen gyártják vagy vásárolnak, nincs olyan mechanizmus, amely lehetővé teszi a cikk különböző kezeléset az egyes helyek költségszámítási táblázatában. Emellett minden közvetett költségkódhoz a költségszámítási verzióban meghatározott díj vagy pótdíj is van beszámadva. A megadott költségek mindig helyspecifikusak.

### <a name="can-i-deactivate-and-activate-versions-of-the-costing-sheet"></a>Inaktiválható és aktiválható a költségszámítási táblázat verziói?

Bár a költségszámítási táblázatban nem tartanak részletes verzióelőzményeket, a költségszámítási táblázatot szükség szerint módosíthatja, majd amikor készen áll, mentse és ellenőrizze. Nincs olyan mechanizmus, amely lehetővé teszi a költségszámítási táblázat régebbi verziójának a megtekintését, illetve a költségszámítási táblázaton végrehajtott módosítások megtekintését. Ha elindítja a módosításokat, és nem szeretné hatályba lépni, akkor a lap úgy is bezárhatja, hogy nem menti és nem érvényesíti a módosításokat. A program megkérdezi, hogy elveti-e a módosításokat.

### <a name="can-i-create-indirect-costs-for-each-item"></a>Létrehozhatok közvetett költségeket minden egyes cikkhez?

A költségszámítási táblázatban olyan közvetett költségkódokat hozhat létre, **·** *amelyeknél* a Csomópont típusa mezőben a Pótdíj, *·* *Díj vagy Kimeneti egység van beállítva.* Ezután meghatározhatja a pótdíjat vagy pótdíjat, hogy az adott cikkszámra vonatkozzon. Az Óradíj **vagy** pótdíj **gyorséten** adjon hozzá egy sort a rácshoz. Az Érvényes **mező beállítása** Tábla *, a* **Kapcsolat** mező pedig az adott cikkszámra.

### <a name="can-i-create-an-indirect-cost-that-isnt-related-to-a-specific-item"></a>Létrehozhatok olyan közvetett költséget, amely nem kapcsolódik egy adott cikkhez?

Igen. Közvetettköltség-kódot is létrehozhat, ahol **a Csomópont típusa** mező kimeneti *egységen alapulóra van állítva*. Ezt követően állítsa be az **Altípus** mezőt *Mennyiség*, *·* *Súly vagy Térfogat* értékre, hogy meghatározza az termelni kívánt cikk mennyiségét, súlyát vagy térfogatát. A díj gyorslapon **megadott** díj a kiválasztott altípusra lesz érvényes. Állítsa például **az Altípus** *·* **mezőt Mennyiség, a Díj** *mezőben pedig 1,00 USD*, majd hozzon létre egy termelési vagy kötegrendelést 10 mennyiséggel. Ebben az esetben a késztermékhez hozzáadható közvetett költséget 10.00 USD.

### <a name="can-i-use-the-costing-sheet-to-split-my-production-costs-by-hours-and-materials"></a>Használhatom a költségszámítási táblázatot a termelési költségek órák és anyagok szerint való felosztására?

Igen. A költségszámítási **táblázatban** összcsomópontokat hozhat létre, hogy a költségeket bármelyik választott csoporttal elválasztsa egymástól. Létre lehet hozni például egy **Órák nevű Total** *csomópontot*, és egy másikat Anyagok nevű *csomópontból*. Az Órák **csomópont** alatt adjon hozzá minden, az órákhoz kapcsolódó kódcsoportot. Az Anyagok **csomópont** alatt adjon hozzá minden, az anyagokhoz kapcsolódó költségcsoportot.

## <a name="dimension-groups"></a>Dimenziócsoportok

### <a name="can-i-manage-cost-at-the-batch-or-serial-number-level"></a>Kezelhetők a költségek a köteg- vagy sorozatszám szintjén?

Igen, ha olyan időszakos költségszámítási modellt használ, mint például FIFO, LIFO, LIFO dátum, súlyozott átlag vagy dátummal súlyozott átlag, **·** **·** **akkor** a nyomon követési dimenziócsoport Köteg vagy Sorozatszám dimenzió pénzügyi készletének beállításával lehet a költségeket részletes szinten nyomon követni.

### <a name="can-i-manage-costs-at-the-location-level"></a>A költségek kezelhetők a hely szintjén?

Nem, nem engedélyezheti a **Pénzügyi** készlet beállítást a **Tárolási** dimenziócsoport Hely dimenzióhoz. Ha a szervezetnek részletesebb szinten kell nyomon követnie a költségeket, fontolja meg, hogy létrehozhat-e virtuális raktárat, **majd válassza a Pénzügyi készlet** **beállítást** a Raktár dimenzióhoz a tárolási dimenziócsoportban.

### <a name="should-i-enable-the-use-warehouse-management-processes-option-for-the-storage-dimension-group"></a>Engedélyezzem a Raktárkezelési folyamatok használata beállítást a tárolási dimenziócsoporthoz?

Ha úgy gondolja, hogy a jövőben használni szeretné a raktárkezelési folyamatokat (WMS), **engedélyeznie** kell a Raktárkezelési folyamatok használata beállítást. A tárolásidimenzió-csoportok **mentése** után már nem lehet módosítani a Raktárkezelési folyamatok használata beállítását. Ha később úgy dönt, hogy használni fogja a raktárkezelési folyamatokat, létre kell hoznia egy új raktárat, ahol ez a lehetőség engedélyezve van. Nincs olyan automatizált folyamat, amely a készlet egyik raktárból a másikba történő áthelyezését, illetve a kapcsolódó konfigurációk új raktárba történő másolását nem használhatja.

### <a name="can-i-enable-the-use-warehouse-management-processes-for-the-storage-dimension-group-even-if-im-not-planning-to-use-warehouse-management-processes-wms"></a>Engedélyezhetik a Raktárkezelési folyamatok használatát a tárolásidimenzió-csoporthoz akkor is, ha nem tervezem a raktárkezelési folyamatok (WMS) használatát?

Igen, még akkor is, ha nem tervezi a raktárkezelési folyamatok (WMS) szolgáltatások használatát, **engedélyezheti** a Raktárkezelési folyamatok használata beállítást a tárolási dimenziócsoporthoz. A tranzakciók létrehozásához és feldolgozásához be kell fejeződni a minimális konfiguráció, például a foglalási hierarchiák és az egységszekvencia-csoportok. A WMS beállításai ugyanakkor általában figyelmen kívül maradnak, ha a kitárolási listákat, a csomagjegyzékeket és a termékbevételezéseket manuálisan kell feldolgozni (például az értékesítési rendelések és a beszerzési rendelések lapjain).

### <a name="when-should-i-enable-the-physical-inventory-option-for-a-storage-or-tracking-dimension-group"></a>Mikor kell engedélyezni a Fizikai készlet beállítást tárolási vagy nyomon követési dimenziócsoportokhoz?

Ha a dimenzió alapján **részletes** készletrekordokat kell megtartani, engedélyeznie kell a Fizikai készlet beállítást tárolási és nyomon követési dimenziócsoportokban. Általában minden aktív dimenzió fizikai nyomon követése is meg fog jelenni. Ebből következően a kiválasztott dimenzió nyomon követi a készlet bevételezését, kiadását vagy mozgását. Ha egy dimenzió nem kötelező (például az tábla), **·** **akkor** engedélyezheti az Üres bevételezés engedélyezve és az Üres kiadás beállításnál, hogy a felhasználók még akkor is bevételezést, kiadást vagy készletet fogadjanak, amikor a dimenzió nincs megadva.

### <a name="when-should-i-enable-the-financial-inventory-option-for-a-storage-or-tracking-dimension-group"></a>Mikor engedélyezzem a Pénzügyi készlet beállítást tárolási vagy nyomon követési dimenziócsoportokhoz?

Ha a dimenzió alapján **részletes** pénzügyi rekordokat kell tartania, engedélyeznie kell a Pénzügyi készlet beállítást tárolási és nyomon követési dimenziócsoportokhoz. A **telephely** dimenzióit a rendszer minden esetben pénzügyileg nyomon követi, míg a többi dimenziót nem kötelező megadni a pénzügyi nyilvántartásban. Ha egy időszaki költségszámítási modellt, például FIFO, LIFO vagy súlyozott átlagot használ, a dimenziók Pénzügyi készlet beállításának engedélyezése azt jelzi, **hogy** csak abban az esetben kerül elszámolásra, ha a bevételezés és a kiadás dimenzióértéke megegyezik. Ha például **engedélyezi** **a** Pénzügyi készlet beállítást a Raktár dimenzióhoz, akkor minden raktárban eltérő költség lesz, és a különböző raktárakból származó bevételezéseket és bevételezéseket nem lehet kiegyenlíteni.

### <a name="can-i-make-changes-to-a-product-storage-or-tracking-dimension-group-after-transactions-exist"></a>Lehet módosításokat eszközlni egy termék-, tárolási vagy nyomon követési dimenziócsoporton, ha léteznek tranzakciók?

Miután létrehozott egy cikkmodellcsoportot, **·** **dimenzió** szerint módosíthatja a Fedezeti terv, a Beszerzési árak és az Eladási ár mezők beállítását, **·** **ha** a cikkmodellcsoport egyik dimenziójának aktív jelölőnégyzete be van jelölve. Egyéb módosítás nem megengedett. Például az Aktív, **·** **Az** üres kiadás engedélyezve, az Üres bevételezés engedélyezve, **·** **·** **a Tényleges készlet és a Pénzügyi készlet beállítás nem engedélyezhető és nem tiltható** le.

### <a name="can-i-change-the-product-storage-or-tracking-dimension-group-for-a-released-product"></a>Megváltoztathatom a termék, a tárolás vagy a nyomon követési dimenziócsoportot egy kiadott termékre?

Ha egy termék aktuális készlete 0 (nulla), **·** *és* a Nyitott érték beállítás Nem értékre van állítva az összes készlettranzakciónál, a kiadott termelési lapon módosíthatja a tárolási és nyomon követési dimenziócsoportokat. A rekord létrehozása után nem lehet módosítani a termékdimenzió-csoportot.

## <a name="item-model-groups"></a>Cikkmodellcsoportok

### <a name="when-should-i-enable-the-stocked-product-option"></a>Mikor kell engedélyezni a Raktárolt termék beállítást?

Engedélyeznie kell a " **Raktárolt** termék" beállítást minden olyan cikkhez, amely nyomon lesz követi a készletben. Ha ez a beállítás engedélyezve van, akkor a rendszer a cikk bevételezését és kiadását nyomon követi a részletes készlettranzakciók nyilvántartására. Ez a beállítás általában engedélyezve van minden olyan materiális cikkre, amit a raktárban tart, például. Akkor is engedélyeznie kell ezt a beállítást, ha nem materiális cikket, például szolgáltatási cikket szeretne hozzáadni az anyagjegyzékhez vagy receptúrákhoz. Ha nem engedélyezi **a** "Raktározott termék" beállítást, a rendszer egyetlen készlettranzakciót sem követ nyomon a készlet areligerében, és a cikkek költségét általában a főkönyv költségként könyveli a rendszer. Ez a beállítás gyakran használatos például olyan üzletekben, amelyek nem szerepelnek az AJ-ekben vagy receptúrákban.

### <a name="when-should-i-enable-the-post-physical-inventory-option"></a>Mikor engedélyezzem a Tényleges készlet felezése beállítást?

A **Tényleges készlet felezése** beállítás jellemzően engedélyezve van a **Raktárolt termék** beállítás engedélyezése esetén. Ha engedélyezi ezt a beállítást, a rendszer nyomon követi a cikk fizikai frissítését a készlettranzakción belül. Ez a beállítás a Kötelezettségek, Kinnlevőségek és Gyártásvezérlés paramétereivel együtt használatos, amelyek meghatározzák, hogy a tényleges frissítés bizonylatot hozzon létre. Ezt a beállítást általában akkor engedélyezi, amikor a készlet tényleges frissítése esetén frissíteni szeretné a főkönyvet. Ha az Ellátásilánc-kezelés nem az Ön pénzügyi nyilvántartási rendszere, akkor érdemes letiltani ezt a beállítást.

### <a name="when-should-i-enable-the-post-financial-inventory-option"></a>Mikor engedélyezzem a Pénzügyi készlet felének beállítását?

A **Pénzügyi készlet felezése** beállítás jellemzően engedélyezve van a **Raktárolt termék** beállítás engedélyezése esetén. Ez a beállítás a Kötelezettségek, Kinnlevőségek és Gyártásvezérlés paramétereivel együtt használatos, amelyek meghatározzák, hogy a pénzügyi frissítés bizonylatot hozzon létre. Ez a beállítás általában akkor engedélyezhető, amikor a készlet pénzügyi frissítése esetén (például az értékesítési és beszerzési rendelések számlázása, vagy termelési rendelés befejezése esetén) a főkönyv frissítésére van szükség. Ha az Ellátásilánc-kezelés nem az Ön pénzügyi nyilvántartási rendszere, akkor érdemes letiltani ezt a beállítást.

### <a name="when-should-i-enable-the-post-to-deferred-revenue-account-on-sales-delivery-option"></a>Mikor engedélyezzem a Halasztott bevétel számlára történő feladás beállítást az értékesítések kiszállításán?

A Feladás halasztott **bevételi** számlára beállítással jelezheti, hogy az értékesítési rendelés csomagjegyzékének feladása esetén szeretné-e elismerni a főkönyvben a bevételt. Ez a beállítás általában akkor használatos, ha nagy késés van egy értékesítési rendelés csomagjegyzéke és számlája között, vagy ha az adott időszakban nem lehetséges az összes értékesítési rendelés számlázása. Ezt a beállítást általában akkor tiltja le, ha az értékesítési rendelés számláit közvetlenül a csomagjegyzék feladja. Így elkerülheti, hogy olyan további főkönyvi feladásokat generál, amelyek azonnal sztornírozva lesznek az értékesítési rendelések számlázásakor.

### <a name="when-should-i-enable-the-accrue-liability-on-product-receipt-option"></a>Mikor kell engedélyezni a kötelezettség elhatárolása a termékbevételezésen beállítást?

A legtöbb szervezetnél **engedélyezni** szeretné a kötelezettség elhatárolása a termékbevételezéskor beállítást minden cikkmodellcsoportra attól függetlenül, hogy van-e raktáron vagy nem raktárott termék. Ezzel a beállítással a termékbevételezési ár alapján történik az elhatárolás feladása a főkönyvbe. Mivel jellemzően késés van egy beszerzési rendelés termékbevételezésének feladása és a számla feladása között, a legtöbb szervezetnek a helyi szabályozások (például a CAAP) szerint fel kell ismernie a mérlegben szereplő kötelezettséget. Ha az Ellátásilánc-kezelés nem az Ön pénzügyi nyilvántartási rendszere, akkor érdemes letiltani ezt a beállítást. Ha a szervezet beszerzési kategóriákat használ a beszerzési rendelésekhez, a könyvelés követelményét úgy szabályozhatja, **·** **hogy** engedélyezi a Beszerzési irányelvek lapon a kategória irányelvszabályának Beszerzési irányelvszabályhoz tartozó Elhatárolt beszerzési költség bevételezéskor beállítását.

### <a name="how-can-i-prevent-a-user-from-posting-a-purchase-order-product-receipt-if-a-receipt-registration-isnt-yet-posted"></a>Hogyan lehet megakadályozni egy felhasználó számára a beszerzési rendelés termékbevételezésének feladását, ha még nincs feladva bevételezési regisztráció?

Ha még nem történt meg a beszerzési rendelés regisztrálása, a felhasználó megakadályozhatja a beszerzési rendelés termékbevételezésének feladását a **cikkmodellcsoport** Regisztrációs követelmények beállításának engedélyezésével. Ez a beállítás jellemzően olyan szervezeteknél használatos, amelyek két lépésből áll bevételi folyamatot használnak, vagy olyan helyzetekben, amikor köteg- vagy sorozatszámot kell regisztrálni, például a bevételt cikkeken. A **Regisztrációs szükséglet** beállítás a *cikk* minden készletbevételezését érvényes, nem csak a beszerzési rendelésekre. Például olyan készletnaplóra vonatkozik, amely pozitív mennyiséget és egy termelési rendelés készként jelentési naplóját alkalmazza.

### <a name="how-can-i-prevent-a-user-from-posting-a-purchase-order-invoice-if-a-product-receipt-isnt-yet-posted"></a>Hogyan lehet megakadályozni, hogy egy felhasználó beszerzési rendelési számlát adjon fel, ha még nem adott fel termékbevételezést?

Ha még **nem** történt meg a beszerzési rendelés termékbevételezése, a felhasználó megakadályozhatja a beszerzési rendelés termékszámlának a feladását, ha engedélyezi a cikkmodellcsoport Bevételezési követelmények beállítását. Ez a beállítás általában olyan szervezeteknél használatos, amelyek megkövetelik, hogy a bevételezések könyveléshez ténylegesen elismerve legyen a főkönyvben. A **Bevételezési** szükséglet beállítás a *cikk* minden készletbevételezését tartalmazza, nem csak a beszerzési rendelésekre. Például olyan készletnaplóra vonatkozik, amely pozitív mennyiséget és egy termelési rendelés készként jelentési naplóját alkalmazza. Ha a szervezet beszerzési kategóriákat használ a beszerzési rendeléseken, a Beszerzés irányelvszabály kategória-irányelvszabályhoz tartozó Bevételezési követelmények beállítás engedélyezésével szabályozhatja **a** **bevételezés követelményét.**

### <a name="how-can-i-prevent-a-user-from-posting-a-sales-order-packing-slip-if-a-sales-order-picking-list-isnt-yet-posted"></a>Hogyan lehet megakadályozni, hogy egy felhasználó feladja az értékesítési rendelés csomagjegyzékét, ha még nincs feladva értékesítési rendelés kitárolási listája?

Ha még nem történt meg az értékesítési rendelés kitárolási listája, a felhasználó megakadályozhatja az értékesítési rendelés csomagjegyzékének vagy számlájának feladását a **cikkmodellcsoport** Kitárolási követelményeket beállításának engedélyezésével. Ez a beállítás jellemzően olyan szervezeteknél használatos, amelyek fizikai kitárolási folyamatot hajtnak végre a raktárban (például a raktári mobileszköz használatával a kitárolás elvégzésére). A kitárolási **szükséglet** beállítás a *cikk* minden készlet-kitárolására vonatkozik, nem csak az értékesítési rendelésekre. Például olyan készletnaplóra vonatkozik, amely negatív mennyiséget és termelési rendelés kitárolásilista-naplóját tartalmazza.

### <a name="how-can-i-prevent-a-user-from-posting-a-sales-order-invoice-if-the-sales-order-packing-slip-isnt-yet-posted"></a>Hogyan lehet megakadályozni, hogy egy felhasználó értékesítési rendelési számlát ad fel, ha még nincs feladva az értékesítési rendelés csomagjegyzéke?

Ha még nem történt értékesítési rendelés csomagjegyzéke, a felhasználó megakadályozhatja az értékesítési rendelés számlájának feladását a **cikkmodellcsoport** Levonási követelmények beállításának engedélyezésével. Ez a beállítás jellemzően olyan szervezeteknél használatos, amelyek fizikai csomagolási folyamatot hajtanak végre a raktárban (például a Csomagolás végrehajtása a Raktárkezelés mobilalkalmazás használatával, vagy olyan dokumentum generálása, amely a leszállított cikkekhez fog tartozni). A **Levonási** szükséglet beállítás egy *cikk minden készlet-bevételezésre* vonatkozik, nem csak az értékesítési rendelésekre. Például olyan készletnaplóra vonatkozik, amely negatív mennyiséget és termelési rendelés kitárolásilista-naplóját tartalmazza.

### <a name="can-i-prevent-items-that-are-registered-from-being-sold"></a>Megakadályozhatom a regisztrált cikkek eladását?

Ha egy cikket regisztrálnak a készletben az Ellátásilánc-kezelésben, akkor a mennyiség fizikailag elérhető a rendszerben. *Ha* a regisztrált, de még be nem érkezett cikkek nem érhetők el értékesítési vagy termelési rendelésekhez való kibocsáthatóként, például fontolja meg az üzleti folyamat kezelésére a készletállapotot, a készletzárolást, a minőségi rendeléseket, a karanténutasításokat vagy a foglalási funkciókat.

## <a name="production-costing"></a>Termelés költségszámítása

### <a name="can-i-use-one-costing-model-for-raw-materials-and-a-different-costing-model-for-finished-goods"></a>Használhatok egy költségszámítási modellt a nyersanyagokhoz, és egy másik költségszámítási modellt a késztermékek számára?

Igen, mindegyik cikkhez különböző költségszámítási modelleket használhat. A gyártók számára nem fontos a nyersanyagokra vonatkozó időszakos költségszámítási modell, illetve a félkész és késztermékek elszámolóára.

### <a name="how-can-i-drive-overhead-off-machine-costs"></a>Hogyan lehet a többletköltségeket a gépek költségeiről le vezetni?

A gépek költségeinek csökkentése érdekében erőforrásokat és erőforráscsoportokat kell létrehozni minden géphez, az üzleti követelményeknek megfelelően. Minden erőforrást vagy erőforráscsoportot költségkategóriákhoz lehet hozzárendelni a gép költségének szabályozása érdekében. Minden költségkategóriát egy költségcsoporthoz lehet kapcsolni, és minden költségcsoport felhasználható a költségszámítási táblázatban a közvetett költségek számításához.

### <a name="how-do-i-recognize-cost-that-is-related-to-energy-consumption-for-example-water-energy-or-gas-consumption-on-the-costing-sheet"></a>Hogyan ismerhető fel a költségszámítási táblázatban az energiafelhasználáshoz (például víz-, energia- vagy gázfelhasználáshoz) kapcsolódó költség?

Az energiafelhasználással kapcsolatos költségeket általában kétféleképpen lehet elismerni:

- Hozzon létre egy sort az anyagjegyzékben vagy receptúrában. Ez a sor általában szolgáltatási cikkként jön létre, és megadhatja, hogy milyen mértékegységet vesz igénybe a termelésben használt mennyiséggel kapcsolatban. Ily módon a felhasználó más összeget is felhasználhatja a termelési folyamat során. A cikkeket automatikusan felhasználhatja az **Ürítési** elv mezőben kiválasztott érték alapján.
- Közvetett költség létrehozása a költségszámítási táblázatban. Ez a megközelítés általában az energiafelhasználás teljes költségét osztja fel a termelési folyamat során. A költségcsoport és a teljes költségkönyvelési alap segítségével például az útvonal anyag- vagy munkafelhasználása alapján skálázhatja a felhasználást.

A legjobb beállítást ajánlott választani a jelentési, egyeztetési és üzemeltetési követelmények alapján.

### <a name="can-i-capture-resource-details-in-the-bom-or-formula"></a>Rögzítheti az erőforrás adatait az anyagjegyzékben vagy a receptúrában?

Az erőforrás adatai csak útvonalműveletben rögzítettek. Bár létrehozhat olyan szolgáltatási cikket, amely egy erőforrást képvisel, és a költséggel megnöveli a késztermék költségszámítását, ezt a megközelítést általában nem ajánljuk. Ehelyett javasoljuk, hogy hozzon létre egy egyszerű útvonalat, amely egy sort használ az erőforrásköltségek nyomon követésére, és konfigurálja úgy a műveletet, hogy az automatikusan fel legyen használva a termelési rendelés elején vagy végén.

### <a name="can-i-view-the-calculation-details-if-the-cost-is-manually-entered"></a>Meg lehet tekinteni a számítás részleteit, ha a költséget manuálisan kell megadni?

Nem. Ha manuálisan adja meg az árat a **Cikkár** lapon, **akkor a Számítás részleteinek** **megtekintése** és a Jelentésszámítás részletei gomb nem érhető el. Ha egy manuálisan **megadott önköltségi árhoz a Költségösszesítés költségcsoport** szerint gombot választja, megjelenik egy összegző sor, és minden költség felfelé áll a késztermékhez.

### <a name="does-the-system-calculate-variances-on-a-production-order-when-i-manually-enter-the-cost"></a>Kiszámítja a rendszer a termelési rendelés eltérését, amikor manuálisan beírom a költséget?

Igen, a rendszer az elszámoló ár manuális beíratáskor kiszámítja az eltéréseket. Ha azonban manuálisan ad meg elszámolóárat a számítás helyett, akkor a termelési rendelésben található összes anyag-, útvonal- és közvetettköltség-felhasználás helyettesítési különbözetnek számít. Ha további eltérések vannak, például a extra anyagfelhasználás vagy a munkafelhasználás, akkor a termelési anyagjegyzék eltéréseiként is rögzítve lesznek. Ezért javasoljuk, hogy mindig számoljon olyan cikkekre, amelyek anyagjegyzéket, útvonalat vagy közvetett költségeket tartalmaznak.

### <a name="how-can-i-carry-the-variances-from-a-subproduction-order-to-the-parent-production-order"></a>Hogyan lehet áthozni az altermelési rendelés eltérései a szülő termelési rendelésbe?

Időszakos költségszámítási modell (például FIFO, LIFO vagy súlyozott átlag) használata esetén az altermelés költségeit a cikkekhez kiválasztott heuristic modellben ismeri fel a program. Ha tényleges költségszámítást igényel, használja a jelölési elvet annak jelzésére, hogy melyik résztermelés kerül a szülő termelési rendeléshez. A másik lehetőség az, **·** **·** **hogy** a köteg- vagy sorozatszám dimenziónál célszerű a Pénzügyi készlet beállítást használni a nyomon követési dimenziócsoportban.

### <a name="how-does-the-flushing-principle-affect-consumption"></a>Hogyan befolyásolja az ürítési elv a felhasználást?

Az anyagjegyzék-, receptúra- vagy útvonalsor ürítési elve határozza meg a cikk vagy munka felhasznált időzítését és módszerét. Ha az Indítás *lehetőséget választja*, akkor a termelési rendelés indítani automatikusan a cikket vagy a munkát is felhasználja. Ha a Befejezés *lehetőséget választja*, akkor a program automatikusan felhasználja a cikket vagy a munkát, amikor a termelési rendelést készként jelenti. Ha a Manuális lehetőséget *választja*, akkor egy felhasználónak manuálisan kell ki válogatnia az anyagokat, vagy rögzítenie kell az időt a feladatban vagy útvonalkártya-naplóban. Az AJ-hez és receptúrákhoz is *van elérhető hely beállítás*. Ha ezt a lehetőséget választja, a cikkek automatikusan felhasználódnak, miután átkerültek a termelési emeletre.

### <a name="how-should-i-run-cost-calculations-if-i-have-multi-level-boms-or-formulas"></a>Hogyan kell futtatni a költségszámításokat, ha többszintű AJ-aim vagy receptúraim vannak?

Általában azt ajánljuk, hogy a számításhoz használt receptúrák vagy receptúrák legalsó szintjén kezdődjon. A költségszámítások tömeges futtatásakor a szűrést úgy megkönnyítheti, hogy számítási csoportokkal megkönnyíti a termékek szétválasztását. Azt is ajánljuk, hogy *futtassa* az Anyagjegyzékszintek újraszámítása ismétlődő feladatot, mielőtt elindítja a költségszámítások tömeges futtatását. Minden szervezetnek figyelembe kell vennie a termékek kombinációit, és olyan stratégiát kell meghatároznia, amely megfelel a termék, az anyagjegyzék vagy receptúrastruktúrák egyedi szükségleteinek.

## <a name="transfer-order-costing"></a>Átrendelt rendelés költségszámítása

### <a name="is-there-a-way-to-allocate-freight-to-a-transfer-order-cost"></a>Van mód a fuvardíj átszámítási rendelés költségének felosztásra?

Költségek hozzáadásához költségeket adhat hozzá az átátviteli rendeléshez. A költségkód határozza meg a tartozik és követel tételeket a hozzáadt költséghez. Először költségkódokat kell létrehozni a **Készletkezelés modulban**. Ha díjat szeretne hozzáadni egy átátviteli rendeléshez, **válassza** ki a Költségeket az átrendelés sorában, amelybe költséget szeretne felvenni.

## <a name="variances"></a>Eltérések

### <a name="can-i-treat-variances-differently-based-on-the-site-or-warehouse"></a>A hely vagy raktár alapján másképp kezelem az eltéréseket?

Nincs lehetőség az eltérési számlák hely szerinti konfigurálára. Ha elszámolóáras költségszámítást használ egy kiadott termékhez, akkor kiválaszthatja azt a fő számlát, amely az elszámolóáras **különbözetek feladására használatos a Feladás lapon**. Beállíthatja egy cikk, egy cikkcsoport vagy az összes cikk számláit. Egy költségcsoportot, egy költségcsoportot vagy minden költségcsoportot konfigurálhat.

### <a name="can-i-separate-variances-that-are-the-result-of-currency-exchange-rates-from-other-types-of-variances"></a>Lehet elválasztani az árfolyamból származó különbözeteket a többi különbözettípustól?

Ha az eltérés a beszerzési rendelés ára és a cikk elszámolóára közötti átváltási árfolyam eltérése miatt van, nincs mód az árfolyam-különbözetnek az egyéb eltérésektől való elválasztára.

## <a name="reporting"></a>Jelentéskészítés

### <a name="how-many-inventory-value-report-configurations-can-i-create-and-use"></a>Hány készletérték-jelentési konfigurációt hozhatok létre és használhatok?

Nincs korlátozás a létrehozható készletérték-jelentési konfigurációk számára. Ki kell értékelnie a specifikus jelentési követelményeket, és létre kell hoznia azt a számú konfigurációt, amely ezeknek a követelményeknek meg kell felelnie. A jelentés vagy a jelentés tárolási beállításának futtatásához legalább egy készletérték-jelentési konfiguráció szükséges.

### <a name="can-i-use-the-inventory-value-report-to-analyze-the-cost-of-an-item-in-each-warehouse"></a>A készletérték-jelentés segítségével elemezheti egy cikk költségét az egyes raktárakban?

Igen. A készletérték-jelentés **·** **·** **konfigurációjában** minden egyes Raktár dimenzióhoz engedélyezheti a Nézet vagy az Összesítés beállítást. A jelentés azonban csak olyan **dimenziók** értékeit mutatja, amelyeknél engedélyezve van a Pénzügyi készlet beállítás a tárolási dimenziócsoporthoz. Az egyéb dimenziókban üres oszlopok fognak láthatók. További tájékoztatás a Készletérték-jelentés [példákban és logikájában található](inventory-value-report-examples.md).

### <a name="how-can-i-view-the-inventory-quantity-as-of-a-specific-date-with-the-weighted-average"></a>Hogyan lehet megtekinteni a készletmennyiséget egy adott dátumra a súlyozott átlaggal?

A Készletkorosítás jelentés **használható**, amely egy Átlagos egységköltség oszlopot tartalmaz, **amely** egy adott dátum készletértékét mutatja. További információ a Készletkorosítási [jelentés példákban és logikájában található](inventory-aging-report.md).

### <a name="how-can-i-view-which-receipt-transactions-are-settled-against-an-issue-transaction"></a>Hogyan lehet megtekinteni, hogy mely bevételezési tranzakciókat kell kiegyenlíteni egy kiadási tranzakcióval szemben?

A készlettranzakciók kiegyenlítését **a** **·** **·** **·** **Készlettranzakciók és a Készlettranzakciók részletei lap Készlet lapján található Kiegyenlítések vagy Költség intézőben lehet** megtekinteni. Ha kiválaszt egy nyugtát, és megmutatja a tranzakcióhoz kapcsolódó problémákat, a költség intéző nem mutatja a részleteket. A részletek csak akkor jelennek meg, ha ki van választva egy kiadási tranzakció.

### <a name="how-does-the-inventory-value-report-show-items-that-have-a-positive-physical-quantity-and-a-negative-financial-value"></a>Hogyan mutatja a készletérték-jelentés a pozitív fizikai mennyiséget és negatív pénzügyi értékű cikkeket?

A készletérték-jelentés a fizikai és pénzügyi összegeket és mennyiségeket a saját oszlopaikra választja el. A jelentésen megjelenő értékek a jelentés futtatásakor kiválasztott dátumtartománynak megfelelőek. Az összegzés megjelenő szintje a kiválasztott beállításoktól függ. Ha egy cikkhez ténylegesen beérkezett és pénzügyileg kiadott tranzakciók vannak, a mennyiségek és értékek egymástól függetlenül összegezve vannak. Ha a részletezett szint tranzakcióként való megtekintését választotta, akkor az egyes bevételezések és kiadások sorai külön, a fizikai és pénzügyi mennyiségek és összegek pedig külön-külön jelennek meg. További tájékoztatás a Készletérték-jelentés [példákban és logikájában található](inventory-value-report-examples.md).

### <a name="what-is-the-impact-of-storage-and-tracking-dimension-groups-on-the-inventory-value-report"></a>Milyen hatással vannak a tárolási és nyomon követési dimenziócsoportok a készletérték-jelentésre?

Ha egy tárolási **vagy** nyomon követési dimenziócsoportban engedélyezi a Pénzügyi érték beállítást egy dimenzióhoz, **·** **akkor** a készletérték-jelentés konfigurációjában kiválaszthatja a dimenzióHoz a Nézet vagy az Összesen beállítást. Ha **a** **Nézet** vagy az Összesítés lehetőséget választja egy olyan dimenzióhoz, ahol nincs kiválasztva a **Pénzügyi** érték beállítás, a jelentés kimenetében üresen marad az oszlop. **Ha** egy tárolási vagy nyomon követési dimenziócsoportban engedélyezte egy dimenzió pénzügyi érték beállítását, **·** **és** a készletérték-jelentés konfigurációjában nem választotta a Nézet vagy az Összesen lehetőséget, a rendszer összegzi a kiválasztott dimenziók értékeit, amelyekben pénzügyileg nyomon követhetők.

### <a name="can-i-customize-the-power-bi-embedded-reports-for-costing"></a>Testre lehet szabni a beágyazott Power BI jelentéseket a költségszámításhoz?

Igen, a megfelelő biztonsági engedélyekkel rendelkező felhasználók frissíthetik Power BI az Ellátásilánc-kezelésbe ágyazott jelentések jelentéstervező vásznait. A további tudnivalókat lásd [a Beágyazott jelentések testreszabása az analitikus munkaterületeken](../../fin-ops-core/dev-itpro/analytics/customize-analytical-workspace.md).

### <a name="where-can-i-view-the-variance-analysis-statement"></a>Hol lehet megtekinteni az eltéréselemzési kimutatást?

Az eltéréselemzési **\>\>** **kimutatáshoz a Készletkezelés lekérdezése és jelentései – elemzési jelentések és költséggazdálkodási \> lekérdezések \> és jelentések – elemzési jelentések – férhetnek hozzá.** Mindkét beállítás ugyanazt a jelentést nyitja meg, és a jelentés viselkedése azonos.

## <a name="item-prices-and-default-costs"></a>Cikkárak és alapértelmezett költségek

### <a name="can-i-maintain-the-cost-for-each-product-variant"></a>Karbantartható az egyes termékváltozatok költsége?

Igen. Az Önköltségi **ár** **·** **változatok** szerint beállítás engedélyezése a Kiadott termékoldal Költség gyorslapján engedélyezhető a termékváltozatok alapján való árképzés engedélyezéséhez. (Ez a beállítás csak az egyes termékekhez áll rendelkezésre.) **Ezután** a Cikk ároldalán (**·** **amelyet** a Költségszámítási verzió vagy a Kiadott termék lapról lehet megnyitni) **·** **kiválaszthatja** a Dimenziók megjelenítését, és megadhatja, hogy a Konfiguráció, Méret, **·** **·** **Szín vagy Stílus** dimenziót szeretné-e megjeleníteni. Ha a lap minden megnyitásakor menteni szeretné a beállításokat, és használni szeretné a kiválasztott dimenziókat **,** engedélyezze a Mentés beállítási **lehetőséget, majd válassza az OK gombra.** Csak olyan cikkek dimenzióit adhatja meg, amelyeknél aktívak a dimenziók a termékdimenzió-csoportban.

### <a name="can-i-maintain-the-cost-for-each-warehouse"></a>Karbantartható az egyes raktárak költsége?

Nem, nem lehet raktáranként karbantartani a cikk árát. A beszerzési és eladási árakra vonatkozó kereskedelmi megállapodásokat azonban raktáranként karbantarthatja. Először a Tárolási dimenziócsoport lapon **válassza a Beszerzési** **·** **árakhoz** vagy az Eladási árakhoz lehetőséget a dimenzióhoz. Ezután amikor létrehozza a kereskedelmi megállapodási naplót, és megnyitja a dimenziók sorait, válassza ki a Készlet megjelenítése dimenziókat, **\>** és válassza ki, hogy melyik dimenziót jelenítse meg a rácsban. Ha a lap minden megnyitásakor menteni szeretné a beállításokat, és használni szeretné a kiválasztott dimenziókat **,** engedélyezze a Mentés beállítási **lehetőséget, majd válassza az OK gombra.** Csak olyan cikkek dimenzióit adhatja meg, amelyeknél aktívak a dimenziók a termékdimenzió-csoportban.

### <a name="what-are-price-charges"></a>Mi az ár költségei?

Az árdíjak lehetőséget nyújtanak arra, hogy rögzített összeget adjanak a cikkárhoz vagy kereskedelmi megállapodáshoz. Amikor beír egy összeget az Ár **költségei** mezőbe, **a Költségek mennyisége mezőben is beírhat** egy értéket. Az árköltségeket a program a megadott költségmennyiségre amortizálja. Az Egységárba **foglalva** beállítás engedélyezése, ha a cikk egységárában szerepelíteni szeretné az árköltségeket. Ez a beállítás mindig engedélyezve van elszámoló ár esetén.

### <a name="how-should-i-configure-prices-for-items-that-are-procured-in-multiple-currencies"></a>Hogyan kell konfigurálni az árakat olyan cikkekhez, amelyek több pénznemben vannak beállítva?

Ha a Kiadott termék lapon **a** **Beszerzési** ár mezőben az alapértelmezett árat adja meg, akkor a feltételezés szerint az a jogi személy főkönyvi könyvelési pénznemében van, amely a vállalatnál van. Hasonlóképpen, ha beszerzési árat **ad** *meg* egy olyan költségszámítási verzióban, amelyben az Ártípus mező be van állítva Beszerzés, a program azt feltételezi, hogy az ár a jogi személy könyvelési pénznemében van megszava. Ha olyan szállítóhoz hoz létre beszerzési rendelést, amely más pénznemben van meghatározva, **akkor** a rendszer automatikusan átváltja a pénznemet a könyvelési pénznem összegére a tranzakció pénznemére a főkönyv Könyvelési pénznem árfolyamtípus mezőjében megadott árfolyam alkalmazásával.

A kereskedelmi megállapodási napló létrehozásakor megadhatja, hogy az egyes sorokban mely pénznemben fejezi ki az árat. Kereskedelmi megállapodásokat több pénznemhez, meghatározott szállítóhoz és számos más tényező-kombinációhoz lehet létrehozni. Ha olyan beszerzési rendelést hoz létre, amelyben a kiválasztott pénznemre létezik kereskedelmi megállapodás, a rendszer azt a kereskedelmi megállapodást használja, amely rendelkezik az egyező pénznemvel. Amikor olyan tranzakciókat ad fel, mint a termékbevételezések vagy -számlák, akkor a rendszer a könyvelési pénznemben megadott árfolyamon átváltja az összeget a főkönyv könyvelési pénznemére.

### <a name="how-should-i-configure-costs-for-items-that-are-procured-in-multiple-currencies"></a>Hogyan kell konfigurálni a különböző pénznemekben áteső cikkek költségeit?

A költségek nem konfigurálhatóak több pénznemben. A cikk **árára** **·** **vagy** alapértelmezett költségeire megadott költséget, amely a Kiadott termék lap Költség kezelése gyorslapJán található Ár mezőben van megadva, mindig a kijelölt jogi személy főkönyvének könyvelési pénznemében vannak kifejezve.

Ha a szervezet szabványos költségszámítást használ, meg kell határoznia azt a stratégiát, amely meghatározza a költségeket, ha több pénznem van. Meg kell határozni egy folyamatot a költség rendszeres frissítéséhez is, hogy csökkentse a feladott eltérések számát.

### <a name="can-i-use-the-profit-setting-on-the-cost-group-page-to-calculate-sales-prices"></a>A Költségcsoport lapon található Nyereség beállítással lehet kiszámítani az eladási árakat?

Igen, a **Költségcsoport** **lapon** található Nyereség beállítással lehet százalékos értékeket hozzáadni, amikor az eladási árak számítása költségszámítással történik. További információ az anyagjegyzék-számításokban [található](bom-calculations.md).

## <a name="marking"></a>Jelölés

### <a name="how-does-marking-affect-periodic-costing-models"></a>Hogyan befolyásolja a jelölés az időszakos költségszámítási modelleket?

Ha időszaki költségszámítási modellt, például FIFO, LIFO vagy súlyozott átlagot használ, és egy bevételezési tranzakciót jelölt meg egy kiadási tranzakcióval szemben, a rendszer figyelmen kívül hagyja a cikk heurista modelljét a készletzárási folyamat során. Ehelyett a rendszer a bevételezés tényleges költségét használja a kiadás költségére.

### <a name="what-happens-during-the-inventory-close-when-i-use-marking"></a>Mi történik a készletzárás során, amikor jelölést használok?

Amikor megjelöli a bevételezéseket és a problémákat, a készletzárás az együtt megjelölt tranzakciókat egyenlíti ki. Ha a kiegyenlítés létrehozásához jelölést használ, **a Kiegyenlítés lapon az** **Alapelv mező jelölésre lesz** állítva *.* Ha egy tranzakciót még a fizikai vagy pénzügyi frissítés előtt megjelölnek, akkor a kiadás a megjelölt bevételezés költségét használja a mozgóátlagon áteső költség helyett. Ha a tranzakciók jelölése a pénzügyi frissítés után történik, akkor a készletzárás és a korrekció folyamata úgy módosítja a kiadási költséget, hogy az megegyezni fog a bevételezési költséggel.

### <a name="can-i-manually-mark-transactions-when-i-use-standard-costing-or-moving-average"></a>Megjelölhetők manuálisan a tranzakciók az elszámolóáras költségszámítás vagy a mozgó átlag használata esetén?

Nem, elszámolóáras vagy mozgó átlag használata során nem jelölheti meg manuálisan a bevételezéseket és a problémákat. Ha a tranzakciók (például közvetlen kiszállítás vagy vállalatközi rendelések) automatikusan be vannak jelölve, a jelölési rekord megmarad, és nehéz foglalásként viselkedik. Ha azonban elszámolóáras vagy mozgóátlagot használ, akkor a rekordok jelölése nincs hatással a cikkek költségére.

### <a name="how-does-marking-affect-the-profit-and-loss-statement"></a>Hogyan befolyásolja a jelölés az eredménykijelölést?

Amikor egy kiadási tranzakciót elismervényhez jelöl meg, a kiadás költsége meg fog egyezni a kiválasztott bevételezéslel. Amikor ténylegesen és pénzügyileg feladja a kiadást, **a feladás befolyásolja az eladott áruk beszerzési költségét,** **a leszállított áruk beszerzési költségét és az eladott áruk beszerzési költségét,** a készletfeladási profilban megadott számlázott számlákat. Ha a tényleges vagy pénzügyi frissítés után be van jelölve egy tranzakció, *akkor* a készletzárási és -helyesbítési folyamat olyan helyesbítést hoz létre, amely egyező bizonylattal korrigálja az eladott áruk költségét, **a** **számlázott számlát és az ellentételeket ahhoz a számlához, amely az egységek önköltségéhez,** számlázva (készlethez) van megadva.

### <a name="how-does-marking-affect-master-planning"></a>Hogyan befolyásolja a jelölés az alaptervezést?

Az Alaptervezés **paraméterei** lap **Szokásos** frissítés lapja tartalmaz egy Frissítés jelölés **nevű mezőt**. Az itt kiválasztott beállítást használja a rendszer, amikor az alaptervezés által létrehozott tervezett rendelést biztosra adja. Ehhez a következő lehetőségek állnak rendelkezésre:

- *Nem* – a rendszer nem végez jelölést.
- *Normál* – a rendszer a bevételek ellenében megjelöli az pegging szerinti bevételezéseket. Egy szükségleti rendelést egy teljesítménnyel szemben kell megjelölni. Ha valamilyen mennyiség még a teljesítésen marad, nincs megjelölve a teljesítő rendelés.
- *Kiterjesztett* – a rendszer megjelöli mind a szükségleti rendeléseket, mind a teljesítménnyel kapcsolatos rendeléseket, függetlenül attól, hogy a teljesítő rendelésen marad-e bármilyen mennyiség.

## <a name="negative-inventory"></a><a name="negative-inventory"></a>Negatív készlet

### <a name="when-should-i-allow-physical-negative-inventory"></a>Mikor engedélyezzem a tényleges negatív készletet?

Általában nem ajánljuk a fizikai negatív készlet használatát, mert a raktárban nem lehet 0-nál kisebb (nulla) mennyiségnél kisebb. Egyes ágazatok üzleti folyamatai és üzleti helyzetei korlátozhatják az olyan műveleteket, amelyek megkövetelik, hogy a készlet fizikailag negatív legyen. Előfordulhat például, hogy a kiskereskedők nem szeretnék megakadályozni egy, a pénztárgéphez bevitt cikk értékesítését, még akkor sem, ha a rendszer azt jelzi, hogy nincsenek rendelkezésre álló cikkek. A folyamat gyártói egy másik példát mutatnak be. Ezeknek a gyártóknak a felhasznált összege meghaladhatja a képletben javasolt mennyiséget. Arra is lehetőség van, hogy a felhasználás becslése nem pontos, tehát a felhasználás meghaladja az adott helyen található összeget, például egy helyről.

Amikor lehetséges, ki kell értékelni az üzleti folyamatot, és javítani kell a folyamaton, hogy a készlet ne legyen negatív. Ha engedélyeznie kell a negatív készletet, a negatív készlet korrekciója érdekében egyértelmű üzleti folyamatot kell használhatja, mert ez hátrányosan érintheti a költségszámítást.

### <a name="when-should-i-allow-financial-negative-inventory"></a>Mikor engedélyezzem a pénzügyi negatív készletet?

Általában azt ajánljuk, hogy a legtöbb szervezet engedélyezze a pénzügyi negatív készletet. (A legtöbb esetben a beszerzési rendelési számlákat nem kell feldolgozni a cikkek szállításához.) Akkor engedélyezze ezt a beállítást, ha olyan meghatározott üzleti folyamatok vannak, amelyek megkövetelik, hogy az eladási ár tükrözze a beszerzési rendelés végső költségét. Ez a követelmény vonatkozhat például rendelésre rendelésre gyártási iparágban vagy csak bizonyos régiókban, ahol a törvény határozza meg.

### <a name="what-happens-to-the-cost-of-my-issues-when-the-inventory-is-negative"></a>Mi történik a saját problémák költségével, ha a készlet negatív?

Ha a cikk készlete negatív, és több cikket ad ki, mint ami ténylegesen van, akkor a rendszer az alapértelmezett cikkárat használja a mozgóátlag kiszámítására, ha olyan időszaki költségszámítási modellt használ, mint például FIFO, LIFO vagy súlyozott átlag. Ha nincs megadva alapértelmezett ár a cikkhez, a rendszer nulla (0) értékű készletet ad ki. Ez a viselkedés a mozgóátlag vagy a mozgó átlag jövőbeli számításai helytelenek lehetnek.

### <a name="can-i-prevent-items-from-being-picked-packed-or-sold-on-sales-orders-and-production-orders-if-there-isnt-enough-on-hand-inventory"></a>Megakadályozhatom az értékesítési rendelések és termelési rendelések cikkeit kitárolni, csomagolni vagy értékesíteni, ha nem elegendő az aktuális készlet?

Igen. Javasoljuk **·**, hogy tiltsa le a Tényleges negatív beállítást a cikkmodellcsoportnál, hogy megakadályozza az értékesítési rendeléseken és termelési rendeléseken található cikkek ki- vagy csomagolását.

### <a name="can-i-prevent-items-from-being-invoiced-on-a-sales-order-if-no-purchase-orders-have-been-invoiced-for-the-same-item"></a>Megakadályozhatom az értékesítési rendelésen szereplő cikkek számlázását, ha ugyanannak a cikknek egyetlen beszerzési rendelése sem lett kiszámlázva?

Igen. Javasoljuk **·**, hogy tiltsa le a Pénzügyi negatív beállítást a cikkmodellcsoportnál, hogy ne számlázzék ki az értékesítési rendelésen szereplő cikkeket, ha ugyanannak a cikknek egyetlen beszerzési rendelése sem lett kiszámlázva.

### <a name="how-does-negative-inventory-affect-financial-ratios-such-as-gross-profit-margin"></a>Hogyan befolyásolja a negatív készlet a pénzügyi arányokat, például a bruttó nyereséget?

Ha engedélyezi, hogy a készlet negatívra induljon, akkor a mérlegen lévő készletérték és az eredménykivallékban található eladott áruk költsége túl alacsony lehet, különösen akkor, ha nincs beállítva alapértelmezett ár a cikkekhez. Ebből következően túl nagy lehet a pénzügyi jelentéskészítés és az olyan arányok, mint például a bruttó nyereségráta, mivel a költség helytelen. Ha időszaki költségszámítási modellt, például FIFO, LIFO vagy súlyozott átlagot használ, akkor a negatív készletmennyiségek korrigálása után a készletzárás és a korrekciós folyamat futtatásakor korrigálható a problémák értéke. Ha viszont mozgó átlagot használ, akkor nincs mód az egyes tranzakciók átértéklére.

### <a name="how-should-i-correct-negative-inventory"></a>Hogyan kell korrigálni a negatív készletet?

Javasoljuk, hogy gyakran figyelje és javítsa a negatív készletet, ha a szervezet vagy az üzleti követelmények határozzák meg, hogy a készlet negatívra változjon. A készletértékeket ciklikus leltározás, helyesbítés feladása vagy mozgási napló feladása alapján lehet korrigálni. Ha fel kell ismernie a készlet váratlan nyereségét egy adott főkönyvi számlán, akkor mozgási naplót kell használnia. **·** **Ellenkező esetben a ciklikus leltározási vagy készletkorrekciós folyamat használata esetén a rendszer feladja a készletkorrekciót a készletbevételi számlára,** és ellentételként könyveli a készletkiadások és a készletfeladási profilban megadott nyereségszámlák ellenszámláit.

### <a name="do-i-have-to-create-a-new-item-if-my-inventory-has-gone-negative-and-i-use-moving-average"></a>Kell új cikket létrehozni, ha a készlet negatív lett, és mozgó átlagot használok?

Nem. Ha a szervezet lehetővé teszi a készlet fizikai negatív működését, és a mozgó átlagot használja készletmodellként, **a** rendszer a Készlet- és raktárkezelési paraméterek lapon hozzárendelt tartalékköltség-sorozatot használja annak meghatározására, hogy hogyan lesz hozzárendelve a költség a problémákhoz. Általában javasoljuk, hogy a készlet fizikai negatív hatása ne legyen megengedve. A további tudnivalókat lásd a [cikk Negatív készlet](#negative-inventory) szakaszban található további kérdéseknél.

## <a name="not-stocked-products"></a>Nem raktárkészlet-termékek

### <a name="can-i-post-sales-order-picking-lists-for-not-stocked-products"></a>Fel lehet adni az értékesítési rendelések kitárolási listáját a nem raktárkészletű termékekhez?

Ha olyan értékesítési rendeléshez hoz létre kitárolási listát, amely olyan cikkmodellcsoportba sorolt cikkeket tartalmaz, amelyek nem készleten vannak, a nem készleten lévő cikkekhez nem lát sorokat. A Raktárkezelés mobilalkalmazás nem használható a nem raktárkészleten lévő cikkek feldolgozására.

Ha olyan értékesítési rendeléshez hoz létre csomagjegyzéket, amely olyan cikkmodellcsoportba tartozik, amely nem raktárott cikkmodellcsoportba tartozik, állítsa a Mennyiség mezőt Kitárolt mennyiség beállításra, **·** *nem* raktárott termékekre, hogy a nem raktárott cikkeket is tartalmazzák a dokumentum létrehozásában. Ha a Mind lehetőséget *választja*, akkor a csomagjegyzéken csak a készleten lévő cikkek fognak szerepelni.

### <a name="should-i-use-a-not-stocked-product-or-a-category-sales-category-or-procurement-category"></a>Nem raktári terméket vagy kategóriát (értékesítési kategóriát vagy beszerzési kategóriát) használok?

A nem raktári termék és a kategória közötti választás az adott üzleti követelményektől függ. A nem készleten álló termékek általában jobban szabályozják az alapértelmezett értékeket, például a beszerzési és értékesítési rendeléseken megadott mennyiségeket és árakat. Emiatt a nem raktárkészletbe vett termékek olyan helyzetekben előnyösek, amikor ugyanazt a terméket vagy szolgáltatást egynél több alkalommal vásárolják vagy adják el. A kategóriák olyan helyzetekben hasznosak, amikor az ár, a cikkek, a leírások stb. a tranzakciótól a tranzakció között inkonzisztensek. A kategóriák bármely termékhez használhatók az eladott vagy beszerzett termékek típusának besorolására.

## <a name="service-items"></a>Szolgáltatási tételek

### <a name="what-is-the-difference-between-a-service-item-and-a-not-stocked-product"></a>Mi a különbség a szolgáltatási cikk és a nem raktárkészlet-termék között?

A szolgáltatási cikk terméktípus. Újonnan kiadott termék létrehozása során **a** *Terméktípus* mezőt Cikk vagy Szolgáltatás beállításra állíthatja.*·* *A* cikk kiválasztása általában azt jelzi, hogy a cikk materiális, *míg* a Szolgáltatás beállítással a cikk immateriális tulajdonságát lehet jelezni.

Bármelyik kiadott termék– tekintet nélkül arra, hogy cikkről vagy szolgáltatási termékről van szó – raktáron lehet vagy nem. A készlet vagy a nem raktárkészlet beállítását a kiadott termékhez kiválasztott cikkmodellcsoport vezérli. Ha olyan cikkcsoportot választ, amely nem raktárkészlet, akkor a rendszer nem hoz létre készlettranzakciókat például a kapcsolódó értékesítési vagy beszerzési rendeléshez.

### <a name="can-i-include-not-stocked-items-in-a-bom"></a>Be lehet foglalni a nem készleten lévő cikkeket az anyagjegyzékbe?

Nem, nem foglalhat **bele** olyan kiadott terméket, amely olyan cikkmodellcsoporthoz van kapcsolva, ahol az anyagjegyzékben vagy receptúrában a Raktározott beállítás le van tiltva. A program nem számít, hogy a **Terméktípus mező** beállítása Cikk *vagy* *Szolgáltatás*. Csak a raktárkészlettel cikkeket lehet szerepelni az anyagjegyzék- vagy receptúrasorok között.

## <a name="costing-modelspecific-questions"></a>Költségszámítási modell specifikus kérdései

### <a name="which-costing-model-should-i-use"></a>Melyik költségszámítási modellt használjam?

A kiválasztott költségszámítási modellek az üzleti követelményektől függenek. Mielőtt kiválaszt egy költségszámítási modellt az Ellátásilánc-kezelésben, ellenőriznie kell, hogy a modell engedélyezve van-e a helyi szabályozások szerint. Javasoljuk, hogy a kiválasztást egy tanúsított könyvelővel ellenőrizze az adott régió területén.

### <a name="can-i-use-more-than-one-costing-model-in-my-organization"></a>Egynél több költségszámítási modellt használhatok a saját szervezetben?

Igen. Az Ellátásilánc-kezelésben kiválasztható cikkmodellcsoportok és költségszámítási modellek száma nincs korlátozva.

### <a name="can-i-use-more-than-one-costing-model-for-each-item"></a>Egynél több költségszámítási modellt használhatok minden egyes cikkhez?

Nem. Minden egyes kiadott termékhez csak egy költségszámítási modellt választhat. Ezt a viselkedést a cikkmodellcsoport vezérli. Ha egynél több költségszámítási modellt kell használnia a készletértékek jelentéséhez, fontolja meg a Globális készletkönyvelés bővítmény használatát.

### <a name="when-i-use-manufacturing-execution-which-costing-methodology-should-i-use"></a>A gyártásvégrehajtás használata során melyik költségszámítási módszert használjam?

A kiválasztott költségszámítási modellek az üzleti követelményektől függenek. Ha a szervezet a gyártásvégrehajtást is használja, akkor nincs külön előny vagy gyártási modell használata.

### <a name="when-is-fefo-used"></a>Mikor használja a FEFO-t?

Az első lejárt, elsőként ki (FEFO) módszer nem egy költségszámítási módszer. Ehelyett ez egy foglalási módszer, amely gyakran használatos a gyártási szervezetekben. Fefo foglalásokat úgy engedélyezhet egy **cikkmodellcsoportnál, hogy engedélyezi a FEFO** dátumvezérelt beállítást, majd kiválaszt egy értéket a Kiválhat a **feltételek mezőben**.

### <a name="are-there-performance-benefits-to-selecting-one-costing-model-over-another"></a>Vannak teljesítménybeli juttatások, ha az egyik költségszámítási modellt ki kell választani a másik fölött?

Általában a cikkhez kiválasztott költségszámítási modellnek minimális hatása van a rendszer általános teljesítményére. A kiválasztott készlet-költségszámítási modell befolyásolhatja a készletzárás vagy újraszámítási folyamat futtatásához szükséges időt. Ha például elszámolóáras vagy mozgó átlagot használ, akkor a készletzárási folyamatnak minimális hatása van a rendszerre, mivel nem frissíti az egyes készlettranzakciókat, és nem hoz létre kiegyenlítéseket. Az időszakos költségszámítási modell, például a FIFO, LIFO vagy súlyozott átlag növelheti a készletzárási folyamat befejezéséhez szükséges időt. Pontosabban a zárási folyamat hosszabb is lehet, ha magas számot ad meg a **cikkmezőnként** engedélyezett legnagyobb iterációk számához, vagy egy alacsony számot **a** *Készletzárás* folyamat Minimális összeg megengedett mezőjében.

### <a name="when-should-i-use-the-fixed-receipt-price-option"></a>Mikor használjam a Rögzített bevételezési ár beállítást?

Ha egy cikk **cikkmodellcsoport** **lapján** bejel választja a Rögzített bevételezési ár jelölőnégyzetet, akkor a rendszer a bevételezési árat fogja használni elszámolóárként a készletbevételezéshez. Ha eltérés van a beszerzési ár és a cikk alapértelmezett önköltségi ára között, **·** **akkor** a program feladja a különbözetet a rögzített bevételezési ár eredményszámlájára vagy a Rögzített bevételezési ár veszteség számlájára, **és ellentételét a rögzített bevételezési ár ellenszámlájára.** (Ezek a számlák mind a következő dátumon vannak megadva: **Feladási** oldal.)

**A** Rögzített bevételezési ár jelölőnégyzetet be kell jelölje be, ha időszakos költségszámítási modellt, például FIFO, LIFO vagy súlyozott átlagot használ, és ha a bevételezés ára eltér az alapértelmezett cikk-költségtől, akkor a beszerzési ár eltérését kell követni a főkönyvben.

### <a name="moving-average"></a>Mozgó átlag

### <a name="is-moving-average-the-same-as-a-floating-average"></a>A mozgó átlag megegyezik a mozgó átlaghoz?

A mozgó átlagot, a mozgó átlagot és a mozgó átlagot gyakran rokon értelműen használják. Ilyen szempontból az ellátásilánc-kezelésben a mozgóátlag az egyetlen olyan hivatalos költségszámítási modell, amely elérhető. Bár a mozgóátlag nem egy hivatalos költségszámítási modell, ez a módszer az időszakos költségszámítási modell, például FIFO, LIFO vagy súlyozott átlag alkalmazásakor használatos. A mozgóátlag nem használatos az ellátásilánc-kezelésben, és más rendszerekben eltérő otációk lehetnek.

### <a name="how-can-i-accommodate-the-difference-between-the-product-receipt-price-and-invoice-price-when-i-use-moving-average"></a>Hogyan lehet befogadni a termékbevételezési ár és a számlaár közötti különbséget a mozgó átlag használatakor?

Mozgó átlag használata esetén a fizikai költség (bevételezési ár) alapján történik az összes kiadási tranzakció mozgó átlagának kiszámítása. Ha eltérés van a tényleges költség (bevételezési ár) és a pénzügyi költség (számlázási ár) között, **·** **·** **a rendszer automatikusan feladja a különbözetet arra a fő számlára, amely a Készletfeladási profil oldal Készlet lapján a mozgóátlagon keresztüli feladáshoz megadott áreltérésnek van megadva.**

### <a name="where-is-the-price-difference-for-moving-average-presented-in-the-general-ledger"></a>Hol van a főkönyvben a mozgó átlag árának eltérése?

Ha áreltérés van a tényleges és a pénzügyi frissítés feladása között a bevételezések esetén, akkor a rendszer arra a fő számlára adja fel a különbözetet, **·** **·** **amely a készletfeladási profil lap Készlet lapján a mozgóátlag feladási típusának áreltéréséhez van megadva.** További tájékoztatás: Mozgóátlag [...](moving-average.md).

### <a name="when-i-use-moving-average-what-happens-if-there-is-an-issue-before-the-receipt"></a>Mozgó átlag használata esetén mi történik, ha kiadás van a bevételezés előtt?

Általában a bevételezés előtt probléma lehet, vagy azért, mert a cikkmodellcsoportban engedélyezi a tényleges negatív készletet, vagy mert a kiadás visszadátumolt. A további tudnivalókat lásd a [cikk](#negative-inventory) Negatív készlet című részében.

Ha vissza szeretné vezetni a tranzakciókat, javasoljuk, hogy alaposan mérlegelje az üzleti folyamatot és a műveleteket, hogy megállapítsa, van-e mód ennek az esetnek az elkerülésére. Ha mozgó átlagot használó cikkhez hoz háttérbe egy tranzakciót, a rendszer hozzárendeli az aktuális mozgó átlagot a tranzakcióhoz. A későbbi problémák nincsenek kiigazítva. A visszadátumos tranzakciók mozgó átlagával kapcsolatos további tudnivalókat lásd [: Mozgó átlag](moving-average.md).

### <a name="standard-costing"></a>Elszámolóár

### <a name="what-is-the-difference-between-standard-costing-and-fixed-receipt-price"></a>Mi a különbség az elszámolóár és a rögzített bevételezési ár között?

Az elszámolóár meghatározásához meg kell határozni a cikk árát, és aktiválni kell a költséget a költségszámítási verzióban. Ez a költség minden bevételezéshez és -bevételezéshez használható. A készletre **való** **bevételezések eltérései a Készletfeladási profil oldal Elszámolóáras lapjának elszámolóáras különbözeti számlái segítségével rögzítenek a főkönyvbe.**

Rögzített bevételezési ár használata esetén azonban csak a bevételezések költsége fix, **·** **és a rendszer a Kiadott termék lap Költségek kezelése gyorslapján megadott költséget használja.** Az alapértelmezett költség és a beszerzési rendelés ára közötti különbségek esetén a beszerzési ár különbözete feladásra kerül a rögzített bevételezési ár eredményszámláira. A problémák nem használják a rögzített bevételezési árat. Ehelyett a program a feladáskor mozgóátlagon (amennyiben nem használ jelölést), és a készletzárás futtatásakor kiválasztott heuristic modellnek újraértékelést ad.

### <a name="can-i-use-fefo-reservations-with-standard-costing"></a>Használhatók FEFO foglalások az elszámoló költségszámításhoz?

Igen, a FEFO foglalások használhatók egy cikkmodellcsoportnál az elszámoló költségszámítás kiválasztásakor. A FEFO foglalások a cikkek fizikai kezelésére használt foglalási logikát vezérlik, míg az elszámoló költségszámítás szabályozza a cikkek fizikai és pénzügyi költségeit.

### <a name="can-i-upload-pending-prices"></a>Feltöltheti a függőben lévő árakat?

Igen, az Excel-bővítmény vagy az Adatkezelési keretrendszer használatával függő árat tölthet fel. A következő entitások használatát javasoljuk:

- Függőben lévő cikkárak (V2)
- Függőben lévő útvonalkategória egységköltségek
- Költségszámítási táblázat csomópont-számítási tényezői (V2)

### <a name="how-often-can-i-update-the-standard-cost-for-an-item"></a>Milyen gyakran lehet frissíteni egy cikk elszámoló költségét?

Nincs korlátozva az a gyakoriság, amelynél aktiválni lehet az új elszámolóárat. Ha egy cikkre a legutolsó költség aktiválásának napján aktivál új költséget, akkor a rendszer a legutóbb aktivált költséget fogja használni az új tranzakciókra és frissítésekre (például a meglévő tranzakciók frissítésére).

### <a name="can-i-deactivate-or-delete-an-activated-cost"></a>Inaktiválható vagy törölhető az aktivált költség?

Nem, aktivált költséget nem lehet inaktiválni vagy törölni. Ha egy költséget helytelenül aktivált, akkor a megfelelő költséggel aktiválhatja az új költséget.

### <a name="are-calculation-groups-used-with-standard-costing"></a>Az elszámolószámolószámításhoz számítási csoportok vannak használva?

A számítási csoportok bármely cikkel használhatók, függetlenül a választott cikkmodellcsoporttól. A számítási csoportok a költségösszesítés vagy a költségszámítási folyamat során használatosak annak meghatározására, hogy milyen beállításokat kell alkalmazni azokkal a cikkekkel, amelyekhez a számítást futtatja. További tájékoztatás a számítási csoportokról: anyagjegyzék-számítási [csoportok](bom-calculation-groups.md).

### <a name="when-should-i-use-a-planned-costing-version"></a>Mikor kell tervezett költségszámítási verziót használni?

A költségszámítási verziók típusa elszámoló költség vagy *Tervezett* *költség lehet*. Az *Elszámolóáras* típus a rendszerben aktív költségekhez használatos, és tranzakciókba lesz feladva. A *tervezett költségtípus* a költségek szimulációinak futtatására használható, és nem befolyásolja a tranzakciók költségét.

### <a name="can-the-total-cost-from-one-entity-be-transferred-to-another-entity-as-the-selling-cost"></a>Átvihető egy entitás teljes költsége egy másik entitásba eladási költségként?

A költségek egyik vállalatból a másikba történő másolásának nincs automatikus módja. Ezenkívül a beszerzési árból az eladási árba nem lehet automatizált költségeket másolni. Ha a szervezetnek az alábbi műveletek valamelyikét el kell elvégeznie, fontolja meg, hogy az adatkezelési keretrendszer használatával exportálhatja-e az adatokat a költségszámítási verzióból, és egy másik vállalatba töltheti fel az adatokat, vagy eladási árként a költségszámítási verzióban, vagy kereskedelmi megállapodásként. Szükséges lehet a fájlok kézi beavatkozása.

### <a name="what-is-the-best-way-to-copy-planned-costs-to-a-standard-costing-version"></a>A tervezett költségeknek mi a legjobb módja az elszámolószámolószámítási verzióba való másolásra?

A **Költségszámítási** **verziók** lapon található Másolás gombbal cikkárakat, költségkategória-árakat és közvetett költségeket másolhat egyik költségszámítási verzióból a másikba.
