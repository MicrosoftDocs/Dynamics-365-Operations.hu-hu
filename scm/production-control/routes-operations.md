---
title: "Útvonalak és a műveletek"
description: "Ez a témakör információt az útvonalak és a műveletek. Útvonal határozza meg a folyamat, a termék vagy a termék változat készítésére. A gyártási folyamat és a megadott sorrendben az alábbi lépéseket kell végrehajtani minden egyes lépés (művelet) írja le. Minden egyes lépés az útvonal is meghatározza a szükséges műveletek erőforrásokat, a szükséges beállítási és futási idő, és hogyan kell kiszámolni a költséget."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMDesigner, BOMDesignerRouteVersion, Route, RouteInventProd, RouteOpr, RouteOprTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 268124
ms.assetid: f78d5836-3e71-42b7-a5d1-41f19228d9d2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 556b9859d0b162b11f0bcbfc6552f6fd9a900596
ms.lasthandoff: 03/31/2017


---

# <a name="routes-and-operations"></a>Útvonalak és a műveletek

Ez a témakör információt az útvonalak és a műveletek. Útvonal határozza meg a folyamat, a termék vagy a termék változat készítésére. A gyártási folyamat és a megadott sorrendben az alábbi lépéseket kell végrehajtani minden egyes lépés (művelet) írja le. Minden egyes lépés az útvonal is meghatározza a szükséges műveletek erőforrásokat, a szükséges beállítási és futási idő, és hogyan kell kiszámolni a költséget.

<a name="overview"></a>Áttekintés
--------

Útvonal írja le, amely egy termék vagy változat termék előállításához szükséges műveletek sorrendje. Minden művelet az útvonal is van szükség, az idő beállítása, és hogyan kell kiszámolni a költséget, és a művelet végrehajtásához szükséges műveletek erőforrások határozza meg. Az ugyanazon útvonal segítségével több termék előállításához, vagy minden egyes termék vagy termékváltozat egyedi útvonalat definiálhat. Még akkor is több útvonal ugyanarra a termékre. Ebben az esetben az útvonal használt függ tényezők, mint például a mennyiség, amelyet be kell mutatni. A Microsoft Dynamics 365 műveletek útvonal meghatározása négy különböző elemeinek leíró, együtt, a gyártási folyamat áll:

-   **Útvonal** – egy útvonalat a gyártási folyamat szerkezete határozza meg. Más szóval azt határozza meg a műveleteket.
-   **A művelet** – műveletet azonosítja egy elnevezett lépés egy útvonal, például a **szerelvény**. Azonos művelet több útvonal is előfordulhatnak, és lehet különböző műveleti számok.
-   **Kapcsolat** – műveleti kapcsolat határozza meg, például a beállítási idő, Üzemidő, költségkategóriák, fogyasztási paraméterek és erőforrásigények művelet működési tulajdonságait. A kapcsolat lehetővé teszi, hogy a művelet típusától függ, az útvonalat, amely a művelet szerepel, vagy éppen előállított termékek működési jellemzői.
-   **Útvonalverzió** – egy útvonalverziót, amely egy termék vagy változat termék előállításához használt útvonalat határozza meg. Útvonalverziók engedélyezze ismételten termékek vagy idővel megváltozott útvonalakat. Is lehetővé teszik a különböző útvonalakon kell felhasználni az ugyanarra a termékre. Ebben az esetben az útvonal használt tényezők, mint például a helyet vagy a gyártandó mennyiség függ.

## <a name="routes"></a>Útvonalak
Egy útvonal egy termék vagy változat termék előállításához használt műveletek sorrendjét ismerteti. Minden egyes művelet a jogutód művelet műveletszámot van rendelve. Műveletek sorrendje is képviselteti magát, amelynek egy vagy több kiindulási pontokat és záró egypontos irányított diagram útvonal hálózat alkotja. Műveletek 365 Dynamics, a szerkezet típusa alapján különböztethetők meg útvonalak. Az útvonalak kétféle egyszerű útvonalak és útvonal hálózatok. A termelési paraméterek megadhatja, hogy csak egyszerű útvonalak is használhatók, vagy hogy az összetettebb útvonalhálózatokkal használható.

### <a name="simple-routes"></a>Egyszerű útvonalak

Egy egyszerű útvonal szekvenciális, és az útvonal csak egy kiindulási pont.  

[![Egyszerű útvonal](./media/routes-and-operations-1-simple-route.png)](./media/routes-and-operations-1-simple-route.png)  

Ha engedélyezi a termelési paraméterek csak egyszerű útvonalak, Dynamics 365 műveletek automatikusan létrehozza a műveletszámok (10, 20, 30 és így tovább) amikor az útvonal határozza meg.

### <a name="route-networks"></a>Útvonal-hálózatok

Ha engedélyezi a termelési paraméterek a bonyolultabb útvonal hálózatok, útvonalak, amelyek több kiindulási pontokat és párhuzamosan futó műveletek határozhatja meg.  

[![Route network](./media/routes-and-operations-2-route-network.png)](./media/routes-and-operations-2-route-network.png)  

**Megjegyzések:**

-   Minden egyes művelet lehet csak egy követő műveletet, és egyetlen művelettel az egész útvonalat kell végződnie.
-   Nem biztos, hogy azonos követő művelet (például műveletek 30 és 40 az előző ábrán) rendelkező több műveletet ténylegesen futnak párhuzamosan van. A rendelkezésre állás és az erőforrások kapacitásának korlátai a módját, hogy a műveletek ütemezése helyezhet.
-   A műveleti szám 0 (nulla) nem használható. Ez a szám foglalt, segítségével megadhatja, hogy az útvonal utolsó művelete nem követő művelet van.

### <a name="parallel-operations"></a>Párhuzamos műveletek

Néha több, különböző tulajdonságokkal rendelkező műveletek erőforrások kombinációját egy művelet végrehajtásához szükséges. Az összeszerelési művelet például szükség lehet egy gép, eszköz és minden két gép egy munkavállaló felügyelik a működését. Ebben a példában a párhuzamos műveletek, ahol egy művelet az elsődleges művelet minősítenek, és a többi másodlagos lehet modellezni.  

[![Elsődleges és másodlagos műveleteket tartalmazó útvonal](./media/routes-and-operations-3-parallel-operations.png)](./media/routes-and-operations-3-parallel-operations.png)  

Az elsődleges műveletnek általában jelzi a szűk keresztmetszetű erőforrás, és szabja meg a másodlagos műveletek esetében az üzemidő. Azonban az ütemezés során, amely magában foglalja a véges kapacitás, erőforrások ütemezése az elsődleges művelet, mind a másodlagos műveletek érhetők el és szabad kapacitással rendelkezik egy időben kell.  

Az elsődleges műveletnek, mind a másodlagos műveletek (az előző ábrán 30) azonos műveletszámmal kell rendelkeznie.  

Az előző példában az elsődleges művelethez (30) az erőforrás követelmény a gép, mivel a másodlagos műveletek (30' és 30'') erőforrás-szükségleteit az eszköz és a munkavállaló. Ötven százalékos terhelés segít garantálni, hogy az ütemezett munkavégző két gép ellenőrizhető egy időben.

### <a name="approval-of-routes"></a>Útvonalak jóváhagyása

Útvonal jóvá kell hagyni, mielőtt fel lehetne használni a tervezési vagy gyártási folyamatban. Jóváhagyási azt jelzi, hogy az útvonal-tervezési befejeződött. Ugyanaz, amely a termék vagy a kiadott termékváltozat jóváhagyott több útvonal is. Egy útvonal jóváhagyása általában akkor jelentkezik, ha az első megfelelő útvonal-verzió jóvá van hagyva. Azonban az egyes üzleti forgatókönyvek, az útvonal és az útvonalverzió jóváhagyását is külön tevékenységeket foglalhat magában, más folyamat tulajdonosok.  

Minden egyes útvonal jóváhagyott vagy nem jóváhagyott külön-külön is lehet. Azonban ne feledje, hogy, ha az útvonal jóvá nem hagyott, kapcsolódó Útvonalverziók is jóvá nem hagyott. A termelési paraméterek megadhatja, hogy az útvonalak lehetnek jóvá nem hagyott, és e jóváhagyott útvonalak módosítható.  

A napló a rekordokat minden egyes útvonal jóváhagyó kell tartani, ha az elektronikus aláírások előírhatja a útvonal jóváhagyásra. Felhasználók kell majd személyazonosságuk segítségével egy [az elektronikus aláírás](/dynamics365/operations/organization-administration/electronic-signature-overview).

## <a name="operations"></a>Műveletek
Egy művelet a termelési folyamat lépése. Műveletek 365 Dynamics minden egyes művelet Azonosítóját és a egyszerű rendelkezik. Az alábbi táblázatok a gép üzemi műveletei Tipikus példája mutatja.

| Művelet  | Leírás        |
|------------|--------------------|
| PipeCut    | Cső daraboló       |
| TIGweld    | AVI-hegesztőgép        |
| JigAssy    | Koordináta szerelvény       |
| Vizsgálat | Minőség-ellenőrzés |

A művelet a beállítási idő és a futási idő, erőforrás-igényű, költségadatok és felhasználás számítása, például működési tulajdonságok a kapcsolat lehet megadni. (További információt a műveleti kapcsolatok, lásd a következő szakaszt.)

## <a name="operation-relations"></a>Műveleti kapcsolatok
A kapcsolat által támogatott művelet a következő működési tulajdonságok:

-   Költségkategóriák
-   Fogyasztási paraméterek
-   Feldolgozási idők
-   Feldolgozási mennyiséget
-   Erőforrásigények
-   Megjegyzések és utasítások

Az azonos művelet több műveleti kapcsolatok határozhatja meg. Minden művelet kapcsolata azonban egyetlen művelettel adott, és egy útvonalat, kiadott termék vagy egy cikkcsoporthoz kapcsolódó engedélyezett termékek tulajdonságait tárolja. Emiatt több különböző működési tulajdonságokkal rendelkező útvonal azonos művelet használható. Ezen túlmenően, egyszerűbben lehet karbantartani a törzsadatok azonos működési tulajdonságú, függetlenül a használt útvonal és az előállított termék szokásos műveletek használata. A művelet kapcsolatához köre keresztül lehet definiálni a **cikk kódja**, **cikk-kapcsolat**, **kód útvonal** és **útvonal-kapcsolat** az alábbi táblázatban látható tulajdonságai.

| Cikk kódja | Cikk-kapcsolat         | Útvonal kódja | Útvonalkapcsolat   | A művelet kapcsolatához alkalmazási köre                                                                                                                                                                                                                                                                              |
|-----------|-----------------------|------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tábla     | &lt;Cikkazonosító&gt;       | Útvonal      | &lt;Útvonal-azonosító&gt; | Egy művelet az útvonal használatakor működési tulajdonságok ahol **útvonalszám**=&lt;útvonalazonosítót&gt; megjelent termék gyártására hol **cikkszám**=&lt;cikk azonosítója&gt;.                                                                                                                        |
| Tábla     | &lt;Cikkazonosító&gt;       | Mind        |                  | Működési jellemzői egy műveletet, ha a kiadott termék előállítására használják, ahol **cikkszám**=&lt;cikk azonosítója&gt;. Más szóval a működési tulajdonságok alkalmazni, ha nincs kapcsolat a kiadott termékhez tartozó útvonal-specifikus művelet.                                     |
| Csoport     | &lt;Cikkcsoport azonosítója&gt; | Útvonal      | &lt;Útvonal-azonosító&gt; | Egy művelet az útvonal használatakor működési tulajdonságok hol **útvonalszám**=&lt;útvonalazonosítót&gt; társított cikkcsoport kiadott termékek előállításához &lt;Csoportazonosító cikk&gt;, kivéve, ha van egy útvonal-specifikus kapcsolat az engedélyezett termék.                         |
| Csoport     | &lt;Cikkcsoport azonosítója&gt; | Mind        |                  | Egy művelet, ha társított cikkcsoport kiadott termékek előállításához használják alapértelmezett működési tulajdonságok &lt;Csoportazonosító cikk&gt;, kivéve, ha egy adott kapcsolat létezik.                                                                                                  |
| Mind       |                       | Útvonal      | &lt;Útvonal-azonosító&gt; | Működési jellemzői a műveletet, ha az útvonal szerepel, ahol **útvonalszám**=&lt;útvonalazonosítót&gt;. Más szóval a működési tulajdonságok vonatkoznak, amikor nincs művelet kapcsolat vagy adott útvonal a kiadott termék vagy társított cikkcsoport. |
| Mind       |                       | Mind        |                  | Az alapértelmezett működési tulajdonságok művelet. A működési tulajdonságok vonatkoznak, amikor egy adott kapcsolat nem létezik.                                                                                                                                                                |

Megadhatja azt is, hogy adott helyhez-e műveleti kapcsolat. Ezzel a módszerrel egy művelet működési tulajdonságok is függ, a hely (hely), ahol a műveletet végzi. Konfigurált termékek minden egyes termék-konfiguráció különböző működési tulajdonságok is megadhatja.  

Műveleti kapcsolatok ad rugalmasan az útvonal definiálásakor. Ezenkívül határozhatnak meg az alapértelmezett tulajdonságok segítségével csökkentheti a törzsadatok kell állnia. Azonban ez a rugalmasság azt is jelenti, hogy figyelembe kell venni a környezet, amely módosítja a műveleti kapcsolat.  

**Megjegyzés:** útvonalanként műveletenként műveleti kapcsolatok működési tulajdonságok tárolják, mert minden előfordulását ugyanannak a műveletnek (például szerelvény) rendelkezik a ugyanazt a beállítási idő, Üzemidő, erőforrás-igényű, és így tovább. Ezért ha egy művelet két előfordulása kell az ugyanazon útvonalon történik, de eltérő futtatási időt rendelkezik, létre kell hoznia két különböző műveleteket, például Assembly1 és Assembly2.

### <a name="modifying-product-specific-routes"></a>Termékspecifikus útvonal módosítása

Amikor megnyitja a **útvonal** a lap a **megjelent termék részletei** lapon látható a kijelölt kiadott termékhez tartozó útvonal-változatokat. Ebben az összefüggésben az egyes műveletekhez Dynamics 365 műveletek működési tulajdonságainak megjelenítése a művelet kapcsolatához az, amely a legközelebb az útvonalverzió. Megfigyelheti, hogy a műveletek listája tartalmazza a **cikk kódja** és **kód útvonal** a kapcsolat tulajdonságait. Ezért megállapítható, mely művelet a kapcsolatot.  

A a **útvonal** lapon módosíthatja a művelet, például az üzemidő vagy költségkategóriák működési tulajdonságait. A művelet kapcsolatához az útvonalat és az aktuális útvonalverziót hivatkozott kiadott termék adott tárolja a módosításokat. Ha a megjelenő kapcsolat nem az útvonal és az engedélyezett termék, mielőtt a rendszer tárolja a módosításokat, a rendszer létrehoz egy példányát a művelet kapcsolatához. Ez a példány *van* az útvonalat és a kiadott termék-specifikus. Ezért a módosítások nem befolyásolják más útvonalak vagy kiadott termékek. Ellenőrizze, hogy melyik kapcsolat megváltoztatta a a **útvonal** oldal, tekintse meg a **cikk kódja** és **kód útvonal** mezők.  

Egy művelet, amely egy útvonal és a kiadott termékhez adott segítségével kézzel is létrehozhatja a **másolás és kapcsolat szerkesztése** függvény.  

**Megjegyzés:** Ha egy útvonalhoz új művelet hozzáadásához kattintson a **útvonal** lap műveleti kapcsolat jön létre csak a jelenlegi engedélyezett termék. Ezért ha az útvonal más felszabadított termékek gyártásához is felhasználják, nem alkalmazható a művelet kapcsolatához az ilyen engedélyezett termékek létezni fog, és az útvonal már nem használható a kiadott termékek.

### <a name="maintaining-operation-relations-per-route"></a>A művelet kapcsolattartás útvonalanként

Megnyitásakor a **részleteinek útvonal-** a lap a **útvonalak** listáján, amelyekre vonatkoznak a kiválasztott útvonal összes műveleti kapcsolatok listája látható. Így könnyen ellenőrizheti működési tulajdonságok milyen termékeket használnak. Módosíthatja az alapértelmezett tulajdonságértékei, mind a termék-specifikus.  

Ha a művelet új kapcsolatot a **részleteinek útvonal** lapon a **útvonal kódja** mező értéke automatikusan **útvonal**, és a **útvonal-kapcsolat** mező értéke az aktuális útvonal útvonal száma.

### <a name="maintaining-operation-relations-per-operation"></a>Műveletenként műveleti kapcsolatok fenntartása

A a **műveletek** lap, megnyithatja a **műveleti kapcsolatok** oldalon. Ezen a lapon módosíthatja egy adott művelet minden műveleti kapcsolatok. Műveleti kapcsolatok alapértelmezett értékeket tartalmazó is módosíthatja.  

Ha a vállalat szokásos műveleteket, és a működési paraméterek azonosak-az összes olyan termékek és eljárások, a **műveleti kapcsolatok** lap itt kényelmesen működési jellemzői, ezek a műveletek karbantartása.

### <a name="applying-operation-relations"></a>Műveleti kapcsolatok alkalmazása

Bizonyos esetekben Dynamics 365 műveletek esetében meg kell keresnie a működési tulajdonságok egy művelethez. Például egy beszerzési rendelés létrehozásakor minden egyes művelet működési tulajdonságok kell másolja a műveleti kapcsolatok, a termelési útvonalon. Ezekben az esetekben Dynamics 365 műveletek keresi a megfelelő művelet kapcsolatok a leginkább specifikus kombináció legalább egyedi kombinációja.  

Amikor műveletek megkeresi a leginkább megfelelő kapcsolat engedélyezett termék, műveleti kapcsolat, amely a kiadott termék azonosítója megegyezik a Dynamics 365 előnyben műveleti kapcsolat keresztül, hogy megfelel a cikk-csoport azonosítója. Viszont, amely megfelel a csoport azonosítója műveleti kapcsolat ajánlott keresztül az alapértelmezett művelet kapcsolatához. A Keresés a következő sorrendben történik:

1.  **Cikk kódja**=**tábla** és **cikk-kapcsolat**=&lt;elem azonosítója&gt;
2.  **Cikk kódja**=**csoport** és **cikk-kapcsolat**=&lt;cikk-csoport azonosítója&gt;
3.  **Cikk kódja**=**minden**
4.  **Útvonal-kód**=**útvonal** és **kapcsolat Route**=&lt;útvonal-azonosító&gt;
5.  **Útvonal-kód**=**minden**
6.  **Konfigurációs**=&lt;konfiguráció azonosítója&gt;
7.  **Configuration**=
8.  **Hely**=&lt;a webhely-azonosító&gt;
9.  **Site**=

Ezért egy művelet csak egyszer minden útvonal kell használni. A művelet az ugyanazon útvonal többször fordul elő, ha a művelet összes előfordulását ugyanazon művelet kapcsolat lesz, és nem fogunk tudni szeretné, hogy a különböző tulajdonságokat (például időket) minden egyes.

## <a name="route-versions"></a>Útvonalverziók
Az Útvonalverziók termékek előállításában fennálló különbségek kezelését, illetve a termelési folyamat jobban szabályozhatja. Meghatározzák, hogy melyik útvonalat kell használni, amikor egy adott termék, amely vagy kiadott termékváltozat állították elő. Az alábbi megszorítások segítségével megadhatja, mely útvonalat használja a kiadott termékhez tartozó:

-   Cikkdimenziók (méret, szín, stílus vagy konfiguráció)
-   Termelési mennyiség
-   Gyártási hely
-   Gyártási dátum

Ha meg vagyunk egy adott helyen egy adott mennyiségű terméket előállító, vagy egy adott időszakban kijelölhet egy adott útvonalverzión az alapértelmezett útvonal verzió. Megjegyzendő azonban, hogy csak egyetlen aktív útvonal engedélyezett egy adott kiadott termék és korlátozások egy adott készletét.  

A termelési paramétereit előírhatja, hogy az érvényességi időtartam egy útvonalverziót, mindig meg kell adni.

### <a name="approval-of-route-versions"></a>Útvonalverziók jóváhagyása

Mielőtt egy útvonalverziót is használható a tervezési vagy gyártási folyamat, jóvá kell hagyni. Amikor jóváhagy egy útvonalverziót, akkor hagyhatja jóvá a kapcsolt útvonal is. Megjegyzendő azonban, hogy egy útvonalverziót jóváhagyott, csak akkor, ha a kapcsolt útvonal is jóváhagyja.

### <a name="activating-the-default-route-version"></a>Az alapértelmezett útvonal verzió aktiválása

Amikor aktivál egy útvonalverziót, kijelölhet azt használja az alapértelmezett útvonal verzió, amely a fő tervezési vagy gyártási rendelések létrehozását, amely lesz. Akkor is csak egy aktív útvonalverzió megkötések (időszak, hely vagy mennyiség) egy adott készletét. Ha a verziót, hogy próbált ütközik egy verzió aktiválása, amely már aktív, hibaüzenetet kap. Nem egyértelmű aktiválás elkerülésére kell majd inaktívvá tétele az ütköző verziójú vagy módosítható az útvonalverzió korlátait (általában az időszak).

### <a name="electronic-signatures"></a>Az elektronikus aláírások

Adott rekordok, aki hagyja jóvá, és minden egyes útvonalverzió aktiválása naplót kell vezessen, ha ezen tevékenységek előírhatja az elektronikus aláírások. Felhasználók jóváhagyása és útvonalverzió aktiválása a személyazonosságuk majd lesz egy [az elektronikus aláírás](/dynamics365/operations/organization-administration/electronic-signature-overview).

### <a name="product-change-that-uses-case-management"></a>Esetkezelési használó termék módosítása

A termék esetében a jóváhagyás módosítása és új vagy módosított útvonal- és útvonalverzió aktiválása egyszerűen áttekintheti az útvonal verzió korlátozások lehetővé teszi. Jóváhagyása és aktiválása adott módosítását egyetlen művelettel kapcsolatos, és az eredményeket a termék Kisbetű-nagybetű dokumentum összes útvonalat is.

## <a name="maintaining-routes"></a>Útvonalak karbantartása
Üzleti szükségletektől függően előfordulhat, amely szükséges annak érdekében, hogy a folyamat meghatározása az erőkifejtés csökkentése érdekében.

### <a name="making-routes-independent-of-resources"></a>Így erőforrások független útvonalak

Számos rendszer a műveletek erőforrás vagy erőforrás csoport, amelyek műveletet hajtanak végre meg kell adni az útvonal. Műveletek 365 Dynamics, meghatározhatja az üzemi erőforrás teljesítenie kell a művelethez alkalmazandó követelmények együttese. Ezért a konkrét műveletek erőforrás vagy erőforrás csoport használandó nem kell addig, amíg a művelet éppenséggel korábbra kell meghatározni. Ez a szolgáltatás akkor különösen hasznos, ha sok a munkavállalók vagy gépek, amelyek ugyanazt a műveletet lehet végrehajtani.  

Például megadhatja a egy művelethez egy műveletek erőforrás, a **gép** típusú, amelynek a **Stamping** képességének 20 tonna. Az ütemezési motor majd megoldja ezeket a követelményeket, a konkrét műveletek erőforrás vagy erőforrás csoport ütemezése a művelet során. Most adhatja meg ezeket a követelményeket nem kötelező a művelet egy adott gép, mert akkor sokkal nagyobb rugalmasságot. Továbbá karbantartás akkor könnyebb, ha erőforrásokat helyez át, és az új erőforrások hozzáadása.  

A különféle erőforrás-igényű, és használatukkal kapcsolatos további tudnivalókért lásd: erőforrás-igényű műveleteket és [erőforrás-képességek](resource-capabilities.md).

### <a name="sharing-routes-across-sites"></a>Útvonalak-helyeken keresztül történő megosztása

Ha egynél több termelési helyszínen azonos termék előállításában, és ha a terméket előállító lépéseket minden azonos telephelyen, gyakran használt összes termelési hely megosztott útvonalat tervezhet. Megosztott útvonal létrehozása nem adja meg a hely maga az útvonal. Azonban továbbra is létre kell hoznia egy útvonalverziót, amely összekapcsolja a megosztott útvonal a termék minden telephelyen.  

Is győződjön meg arról, hogy az útvonal minden művelete erőforrás-szükségleteit nem igényelnek különleges tevékenységek, erőforrások vagy erőforráscsoportok, de ehelyett a szükséges erőforrások jellemzői vannak kifejezve. Az ütemezési motor a megfelelő erőforrásokhoz rendelni a termelés ütemezése a webhely képes lesz. Például ha a futási idő alatt kis különbségek vannak, vagy ha egy bizonyos művelet beállítási ideje helyspecifikus, megadhatja ezt az információt, hogy a webhely további műveleti kapcsolat hozzáadásával.  

A megosztott útvonalak előnyeit teljes mértékben is erőforrás-felhasználás kell válasszuk a megfelelő anyagjegyzék (AJ). Az erőforrás-felhasználás jelzőt az anyagjegyzéksor beállításakor a raktár és a nyersanyagok kell a felhasznált hely van következtetni a művelet ütemezett műveletek erőforrásból. Ezért a raktározási és a helyet nem kell mindaddig, amíg a termelés ütemezése ténylegesen kell meghatározni. Ily módon hogy mind az Anyagjegyzék és az útvonal független a fizikai hely, ahol a termék előállítása.

### <a name="standard-operation-relations"></a>Standard műveleti kapcsolatok

Ha a vállalat termelési egész szabványosított műveleti, és ha alig vagy egyáltalán nem változása a beállítási idő, Üzemidő, felhasználás számításhoz, költségszámítás, és stb akkor előnyt jelenthet az alapértelmezett minden műveletre vonatkozóan műveleti kapcsolatok létrehozása. Ebben az esetben ne jellemző bármely útvonalon vagy termék, amely a műveleti kapcsolatok létrehozása.  

Ha is express erőforrás-igényű készségek és képességek, és az útvonalak hely független legyen, segíthet az üzleti folyamatok folyamatos fenntartását folyamatosan legalább.  

Ez a módszer használata esetén a **műveleti kapcsolatok** oldal lesz az elsődleges cél fenntartásához a Lefutási idő és egyéb tulajdonságokat.

### <a name="resource-specific-process-times"></a>Erőforrás-specifikus feldolgozási időt

Egy műveletek erőforrás vagy erőforrás csoport nem adja meg az erőforrás-igényű művelet részeként, a megfelelő erőforrások eltérő sebességgel is működnek. Ezért a művelet feldolgozásához szükséges idő változhat. A probléma megoldásához használja a **képlet** mezőjében adja meg a feldolgozási idő kiszámítási módját a művelet kapcsolatához. Az alábbi lehetőségek közül választhat:

-   **Szabványos** – (alapértelmezett beállítás) a számítás csak azokat a mezőket a művelet kapcsolatához az használ, és a megadott Lefutási idő szerint a rendelési mennyiség szorzata.
-   **Kapacitás** – a számítás a **kapacitás** a műveletek erőforrás mezőben. Ezért az idő az erőforrás-függő. A tevékenységek erőforrás megadott érték óránkénti kapacitása. Ezt az értéket megszorozza a rendelési mennyiség és a **tényező** értéket a művelet kapcsolatához.
-   **Kötegelt** – A kötegelt kapacitás a kapcsolat adatainak használatával számítható. Kötegek, és ezért a feldolgozási idő száma majd alapján számítható be a rendelési mennyiség.
-   **Erőforrás kötegelt** – Ez a beállítás akkor alapvetően ugyanaz, mint a **kötegelt** lehetőséget. A számítás azonban a **kötegelt kapacitás** a műveletek erőforrás mezőben. Ezért az idő az erőforrás-függő.


<a name="see-also"></a>Lásd még
--------

[Bills of materials and formulas](bill-of-material-bom.md)

[Cost categories used in production routing](../cost-management/cost-categories-used-production-routings.md)

[Resource capabilities](resource-capabilities.md)

[Electronic signature overview](/dynamics365/operations/organization-administration/electronic-signature-overview)


