---
title: A termelési üzem végrehajtási felületének konfigurálása
description: Ez a témakör azt mutatja be, hogyan lehet egy vagy több konfigurációt létrehozni a termelési üzem végrehajtási felületéhez. Amikor megnyitja a termelési üzem végrehajtási felületét, a program automatikusan betölti a kiválasztott konfigurációt és a feladatra vonatkozó szűrőket, amelyek a böngészővel és az eszközzel kapcsolatosak. A konfigurációban be kell állítania azokat a szabályokat, amelyek az adott használathoz szükségesek.
author: johanhoffmann
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgProductionFloorExecutionConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 5a0ead85eaeb6b96b80716614990af8c8e5e70f7
ms.sourcegitcommit: 2e554371f5005ef26f8131ac27eb171f0bb57b4e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/04/2022
ms.locfileid: "8384747"
---
# <a name="configure-the-production-floor-execution-interface"></a>A termelési üzem végrehajtási felületének konfigurálása

[!include [banner](../includes/banner.md)]

A termelési üzem végrehajtási felületét az üzemszinten dolgozók használják a napi munkájuk regisztrálására, például, hogy mikor kezdtek el egy feladatot, a feladatokkal kapcsolatos visszajelzésekhez, a közvetett tevékenységek regisztrálására és a távollétek jelentésére. Ezek a regisztrációk alapot biztosítanak a termelési rendelések előrehaladásának és a költségeinek a nyomon követésére és a dolgozók fizetése kiszámításának alapjául szolgálnak.

Amikor megnyitja a termelési üzem végrehajtási felületét, a program automatikusan betölti a kiválasztott konfigurációt és a feladatra vonatkozó szűrőket, amelyek a böngészővel és az eszközzel kapcsolatosak. A konfigurációban be kell állítania azokat a szabályokat, amelyek az adott használathoz szükségesek. Íme néhány használati példa:

- A vállalati csarnokban lévő eszköznél az alkalmazottak beblokkolnak, mikor megjönnek, és a nap végén távozáskor kiblokkolnak.
- Az üzemi szinten an egy gép, amelyen a gépkezelők rögzítik egy munka megkezdésének és befejezésének idejét. Ezenfelül szüneteket és közvetett tevékenységeket is rögzítenek.

Ez a témakör a telephelyen használt eszközök üzemenenkénti végrehajtási felületének konfigurálásához használható különféle lehetőségeket ismerteti.

## <a name="turn-on-the-production-floor-execution-interface-and-its-related-optional-features"></a>A termelési üzem végrehajtási felületének és a kapcsolódó választható funkcióinak bekapcsolása

A termelési üzem végrehajtási felületét, valamint a jelen témakörben leírt választható számos beállítást is be kell kapcsolni a rendszerben, mielőtt azokat használni lehetne. A [Funkció kezelése](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) lapon bekapcsolhatja a következő alszakaszokban ismertetett funkciók egyikét vagy mindegyikét szükség szerint.

### <a name="the-production-floor-execution-interface"></a>A termelési üzem végrehajtási felülete

Ez a témakörben ismertetett elsődleges funkció, amely előfeltétele a fejezetben említett összes többi funkciónak. A 10.0.25-ös ellátásilánc-kezelésben kötelező megadni, és nem lehet kikapcsolni. Ha 10.0.25-ösnél régebbi verziót futtat, *·*[akkor](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a rendszergazdák be- vagy kikapcsolhatják ezt a funkciót, ha a Szolgáltatáskezelés munkaterületÉn a Termelésirányítás végrehajtási szolgáltatását keresi.

### <a name="generate-license-plates"></a>Azonosítótáblák előállítása

Ezek a funkciók elérhetővé teszik az azonosítótábla funkciót a termelési üzem végrehajtási felületéhez. Ha használni szeretné őket, kapcsolja be a [funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) modulban a következő szolgáltatásokat (ebben a sorrendben):

1. *A Feladatkártya eszközhöz hozzáadott, készként történő jelentéshez használt azonosítótábla*<br>(Az Ellátásilánc-kezelés 10.0.21-es verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. Az Ellátásilánc-kezelés 10.0.25-ös verziója szerint ez a funkció kötelező.)
1. *Az azonosítótábla-szám automatikus létrehozásának engedélyezése, amikor a feladatkártya eszközében befejezettként jelentik*<br>(Az Ellátásilánc-kezelés 10.0.25-ös verziója szerint ez a funkció kötelező.)

### <a name="print-labels"></a>Címkék nyomtatása

Ezek a funkciók elérhetővé teszik a címkenyomtatás funkciót a termelési üzem végrehajtási felületéhez. Ha használni szeretné őket, kapcsolja be a [funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) modulban a következő szolgáltatásokat (ebben a sorrendben):

1. *A Feladatkártya eszközhöz hozzáadott, készként történő jelentéshez használt azonosítótábla*<br>(Az Ellátásilánc-kezelés 10.0.21-es verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. Az Ellátásilánc-kezelés 10.0.25-ös verziója szerint ez a funkció kötelező.)
1. *Címke nyomtatása a Feladatkártya eszközéből*<br>(Az Ellátásilánc-kezelés 10.0.25-ös verziója szerint ez a funkció kötelező.)

### <a name="allow-locking-the-touch-screen"></a>Az érintőképernyő zárolásának engedélyezése

Ez a funkció lehetővé teszi, hogy a dolgozók zárolják a érintőképernyőt, és így ki tudja imítani.

Az Ellátásilánc-kezelés 10.0.21-es verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. A 10.0.25-ös ellátásilánc-kezelésben ez a funkció kötelező, és nem lehet kikapcsolni. Ha 10,0,25-ösnél régebbi verziót futtat, *·*[akkor](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a rendszergazdák a feladatkártya-eszköz és a feladatkártya terminálok zárolására szolgáló funkció keresésével kapcsolják be és kapcsolják ki ezt a funkciót, hogy a szolgáltatáskezelés munkaterületén ki- és bekapcsolható legyen a szolgáltatás.

### <a name="asset-management-functionality-for-the-production-floor-execution-interface"></a>A termelési üzem végrehajtási felületére vonatkozó eszközkezelési funkció

Ez a funkció egy eszközkezelési lapot ad hozzá a termelési üzem végrehajtási felületéhez. A dolgozók ezen a lapon kiválaszthatják azt az eszközt, amely a feladatlista kiválasztott szűrője alatt álló gépi erőforráshoz kapcsolódik. A kijelölt gépi eszköznél a dolgozó megtekintheti az eszköz állapotát és a számlálóértékek alapján, legfeljebb négy kijelölt számláló esetén. Ha használni szeretné ezt a funkciót, kapcsolja be a következő funkciót a [funkciókezelésben](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *A termelési üzem végrehajtási felületére vonatkozó eszközkezelési funkció*<br>(Az Ellátásilánc-kezelés 10.0.25-ös verziója alapértelmezés szerint be van kapcsolva.)

### <a name="enable-job-search"></a>A feladatkeresés engedélyezése

Ezzel a funkcióval keresőmezőt adhat a feladatok listájához. A dolgozók a feladatazonosító megadásával rákereshetnek egy adott feladatra, vagy a rendelés azonosítójának megadásával megkereshetik egy adott rendelés összes feladatát. A dolgozók a billentyűzettel írhatják be vagy vonalkód beolvasásával adhatják meg az azonosítót. Ha használni szeretné, kapcsolja be a következő funkciót a [funkciókezelésben](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Feladatkeresés a gyártóüzem végrehajtási interfészén*<br>(Az Ellátásilánc-kezelés 10.0.25-ös verziója alapértelmezés szerint be van kapcsolva.)

### <a name="enable-reporting-on-co-products-and-by-products"></a>Társ- és melléktermékek jelentésének engedélyezése

Ez a funkció lehetővé teszi a dolgozók számára a gyártóterületi végrehajtási felület használatát a kötegelt rendelések előrehaladásának jelentéséhez. Ez a jelentésfunkció jelentéseket tartalmaz a társtermékekről és melléktermékekről. Ennek a funkciónak a használatához be kell kapcsolni a Szolgáltatáskezelés következő [szolgáltatását](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *Jelentés a termelési üzem végrehajtási felületéről származó társ- és melléktermékekről*

### <a name="enable-the-display-of-full-serial-batch-and-license-plate-numbers"></a>A teljes sorozat-, köteg- és azonosítótáblák megjelenítésének engedélyezése

Ez a funkció jobb felületet biztosít a termelési üzem végrehajtási felületén a sorozatszám-, köteg- és azonosítótáblák listáinak megtekintéséhez. A megjelenítés egy olyan kártyanézetről változik, amely korlátozott számú karaktert mutat egy olyan listanézetre, amely elegendő helyet biztosít a teljes értékek megjelenítéséhez. A lista adott számok keresésére is lehetőséget biztosít.

Az Ellátásilánc-kezelés 10.0.25-ös verziója szerint ez a funkció alapértelmezés szerint be van kapcsolva. A rendszergazdák úgy kapcsolhatják *be és kapcsolják ki ezt a funkciót, hogy a Szolgáltatáskezelési munkaterület termelési üzemirányítási felületének Teljes sorozat-,*[köteg](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)- és azonosítótáblák megjelenítése parancsát keresi.

### <a name="enable-registering-of-material-consumption"></a>Anyagfelhasználás regisztrálásának engedélyezése

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

Ez a funkció lehetővé teszi a dolgozók számára, hogy a termelési emelet végrehajtási felületével regisztrálják az anyagfelhasználást, a kötegszámokat és a sorozatszámokat. Egyes gyártóknak, különösen a folyamatiparban használt gyártóknak kifejezetten regisztrálniuk kell az egyes köteg- vagy termelési rendelésenként felhasznált anyagok mennyiségét. Például a dolgozók a mérleg segítségével leméneklik a munka közben felhasznált anyagok mennyiségét. A teljes anyagkövetés biztosítása érdekében ezeknek a szervezeteknek az egyes termékek előállításához felhasznált kötegszámokat is regisztrálniuk kell.

A funkciónak két változata van. Az egyik lehetőség olyan cikkeket *támogat,* amelyeknél nincs engedélyezve a speciális raktári folyamatok (WMS) használata. A másik támogatja a *WMS* használatát engedélyező cikkeket. A funkció használatához [a](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) Funkciókezelésben (ebben a sorrendben) bekapcsolhatja az alábbi funkciók egyikét vagy mindkettőt attól függően, hogy vannak-e olyan cikkek, amelyek engedélyezve vannak a WMS számára:

- *(Előzetes verzió) Anyagfelhasználás regisztrálása a termelési üzem végrehajtási felületén (nem WMS)*
- *(Előnézet) Anyagfelhasználás regisztrálása a termelési üzem végrehajtási felületén (WMS-kompatibilis)*

> [!IMPORTANT]
> A nem WMS szolgáltatást csak használni lehet. A WMS használata esetén azonban mindkét funkciót engedélyezni kell.

### <a name="enable-reporting-on-catch-weight-items"></a>A cikkekkel kapcsolatos jelentés engedélyezése

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]
<!-- KFM: preview until further notice -->

A dolgozók a termelés emeletének végrehajtási felületével jelentést tehetnek a cikkekkel, a cikkekkel, a kötegrendelésekkel. A kötegrendelések képletek alapján vannak létrehozva, amelyek definiálhatóak úgy, hogy receptúrás cikkként, társtermékként vagy társtermékként tartalmazzanak egy cikkeket. A receptúra úgy is definiálható, hogy receptúrás sorokat kap az összetevőkből, amelyek meg vannak határozva a catch weight számára. A tényleges stömegű cikkek két mértékegységet használnak a készlet nyomon követésére: a tényleges súly és a készletmennyiség. Például az élelmiszeriparban a dobozolt hús tényleges ssúlyos cikkként definiálható, ahol a tényleges súly mennyiségét használják a dobozok számának nyomon követésére, a készletmennyiséget pedig a dobozok súlyának nyomon követésére.

Ennek a funkciónak a használatához be kell kapcsolni a Szolgáltatáskezelés következő [szolgáltatását](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- *(Előzetes verzió) Jelentés a termelési üzem végrehajtási felületéről származó tényleges súly szerinti cikkekről*

## <a name="work-with-production-floor-execution-configurations"></a>A termelési üzem végrehajtási konfiguációinak használata

A termelés-végrehajtási konfigurációk létrehozásához és karbantartásához **kattintson a Gyártásvezérlés \>\> beállítása – Gyártás-végrehajtási \> konfigurálás a termelési emelet létrehozására.** A **Termelési üzem végrehajtásának konfigurálása** lapon látható a meglévő konfigurációk listája. Ezen az oldalon az alábbi műveleteket végezheti:

- Kiválaszthatja bal oldali oszlopban felsorolt termelésiüzem-konfigurációk bármelyikét, hogy megtekintse és szerkessze azt.
- Ha új **konfigurációt szeretne** hozzáadni a listához, válassza az Új lehetőséget a munkaablakban. Adjon meg egy nevet a **Konfiguráció** mezőben, amely lehetővé teszi az új konfiguráció azonosítását. A beírott névnek egyedinek kell lennie minden konfigurációban, és később nem lesz lehetőség a szerkesztésére.

Ezután állítsa be a kiválasztott konfiguráció különféle beállításait. Az alábbi mezők állnak rendelkezésre:

- **Csak érkezéskori és távozáskori blokkolás** – állítsa ezt a lehetőséget az *Igen* értékre, hogy olyan egyszerűsített inferfészt hozzon létre, amely csak érkezéskori és távozáskori blokkolási funkciót biztosít. Ez letiltja az oldal beállításainak többségét is. A beállítás engedélyezése előtt el kell távolítania minden sort a **Lapkijelölés** gyorslapról.
- **Keresés engedélyezése** – ha a feladatlistánál szeretne keresési mezőt szerepeltetni, adja meg az *Igen* értéket a beállításnál. A dolgozók a feladatazonosító megadásával rákereshetnek egy adott feladatra, vagy a rendelés azonosítójának megadásával megkereshetik egy adott rendelés összes feladatát. A dolgozók a billentyűzettel írhatják be vagy vonalkód beolvasásával adhatják meg az azonosítót.
- **Mennyisége jelentése távozáskori blokkoláskor** – Ezt állítsa *Igen* értékre, és megkérheti a dolgozókat, hogy adjanak visszajelzést a folyamatban lévő munkákról a távozáskori blokkoláskor. Ha *Nem* értékre van állítva, akkor a dolgozókat nem figyelmezteti a rendszer.
- **Alkalmazott zárolása** – Ha a beállítás értéke *Nem*, akkor a program közvetlenül a regisztráció után (például új feladat) kilépteti a dolgozókat. A felület ezután visszatér a bejelentkezési oldalra. Ha ez a beállítás *Igen*, a dolgozók bejelentkezve maradnak a termelési emelet végrehajtási felületére. A dolgozó azonban manuálisan kijelentkezhet, így egy másik dolgozó bejelentkezhet, miközben a termelés-végrehajtási felület ugyanannak a rendszerfióknak a használatával fut. A fiókok típusairól a [Hozzárendelt felhasználók](config-job-card-device.md#assigned-users) című témakörben olvashat bővebben.
- **A regisztráció tényleges időpontjának használata** – Ezt a beállítást *Igen* értékre állíthatja, ha azt szeretné, hogy az egyes új regisztrációk időpontja megegyezzen a dolgozó által benyújtott regisztráció pontos időpontjával. Ha a beállítás értéke *Nem*, akkor a bejelentkezési időt használja a rendszer. Ezt a beállítást általában *Igen* értékre kell állítani, ha *Igen* értékre állította az **Alkalmazott zárolása** és/vagy az **Egy dolgozó** beállítást, aminek következtében a dolgozók általában hosszabb ideig bejelentkezve maradnak.
- **Egy dolgozó** – Igen beállítással *beállíthatja* ezt a beállítást, ha csak egy dolgozó használja a termelési emelet mindegyik végrehajtási felületét, ahol ez a konfiguráció aktív. Ha a beállítás értéke *Igen* akkor az **Alkalmazott zárolása** beállítás automatikusan *Igen* értékre lesz állítva. Ezenkívül ez a beállítás eltávolítja a dolgozónak a belépőkártya-azonosító (vagy hasonló) használatával történő bejelentkezésre vonatkozó követelményét (és képességét). Ehelyett a dolgozó egy olyan rendszerfiók használatával jelentkezik be a Microsoft Dynamics 365 Supply Chain Management rendszerbe, amely egy (a dolgozók táblája által regisztrált) dolgozóhoz van kapcsolva, és ugyanakkor bejelentkezik *a* *termelési* emelet végrehajtási felületére, mint az adott dolgozó.
- **Engedélyezi az** érintőképernyő zárolását – *A* beállítás Igen beállításával engedélyezheti a dolgozóknak, hogy zárolják a termelési emelet végrehajtási felületének képernyőjét, és így el tudják tásítani a felületet. Ha ez a beállítás *Igen*, a bejelentkezési laphoz hozzáadódik a **zárolási** képernyő a sanizáláshoz. Amikor egy dolgozó kiválasztja ezt a gombot, az érintőképernyő ideiglenesen zárolódik a véletlen bevitel elkerülésének céljára. Ezenfelül megjelenik egy időzítő. A dolgozó ezután biztonságosan megtisztíthatja a készüléket és a képernyőt. Amikor a visszaszámlálás befejeződött, az érintőképernyő automatikusan feloldódik.
- **Képernyő zárolásának időtartama** – Ha a **Képernyő zárolásának engedélyezése** beállítást *Igen* értékre állították akkor ezzel a beállítással adja meg, hogy hány másodpercig kell zárolni az érintőképernyőt a fertőtlenítéshez. Az időtartamnak 5 és 120 másodperc között kell lennie.
- **Előállít** egy táblát – *a* beállítás Igen beállítással minden alkalommal új tábla generálható, amikor egy dolgozó a termelési emelet végrehajtási felületét használja a készként jelentésre. Az azonosítótábla a **Raktárkezelési paraméterek** lapon beállított számsorozatból jön létre. Ha a beállítás értéke *Nem*, akkor a dolgozóknak a készként való jelentéskor meg kell határozniuk egy meglévő azonosítótáblát.
- **Címke nyomtatása** – a beállítás Igen *beállítással* nyomtatható meg az tábla címkéje, amikor egy dolgozó a termelés emeletének végrehajtási felületét használja a készként jelentéshez. A címke konfigurációja a dokumentumirányításban van beállítva, a [Dokumentumirányítási elrendezés azonosítótábla-címkékhez](../warehousing/document-routing-layout-for-license-plates.md) részben leírtak szerint.
- **Lap kiválasztása** – A szakasz beállításaival kiválaszthatja, hogy mely lapok jelenjenek meg a termelési üzem végrehajtási felületén, amikor az aktuális konfiguráció aktív. A tetszőleges számú lapot tervezhet meg, és szükség szerint hozzáadhatja és elrendezheti őket. A lapok tervezésével és az itt megadott beállításokkal kapcsolatos további tudnivalókat lásd: [A termelési üzem végrehajtási felületének tervezése](production-floor-execution-tabs.md).

## <a name="clean-up-job-configurations"></a>Feladatkonfigurációk megtisztítása

Amikor az üzemfelügyelő beállítja a termelési üzem végrehajtási felületét, kiválaszta a konfigurációt és a feladatra vonatkozó szűrőket. Ezeket a beállításokat egy hivatkozási táblában tárolja a Supply Chain Management alkalmazásban, és a böngésző egy helyi sütit tartalmazó azonosítót használ a tábla helyes sorának megtalálására. A tábla azt a dátumot és időpontot is bejegyzi, amikor a dolgozó utoljára bejelentkezett az egyes eszközökre.

A kötegelt feladat időszakonként törli a hivatkozásokat tartalmazó tábla azon elemeit, amelyek a legutóbbi 60 napban nem naplóztak tevékenységet. Az alábbi lépések követésével bármikor manuálisan is megtisztíthatja a tételeket.

1. Lépjen a **Gyártásvezérlés \> Beállítás \> Gyártásvégrehajtás \> termelési üzem végrehajtásának konfigurálása** részre.
1. A műveleti ablaktáblán válassza az **Ügyfélkonfigurációk megtisztítása** elemet.
1. Az **Ügyfélkonfigurációk megtisztítása** párbeszédpanelen állítsa be a **Napok száma** mezőt az (aktuális nap előtti) szükséges inaktivitási napok megadásához. A program minden olyan eszköz konfigurációját és bejelentkezési rekordját eltávolítja, amely nem volt aktív a megadott időszakban.
1. A **Napok száma** beállítás alapján megfelelő konfigurációk megtisztításához kattintson az **OK** gombra.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
