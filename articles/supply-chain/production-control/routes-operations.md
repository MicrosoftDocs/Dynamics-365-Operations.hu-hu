---
title: Útvonalak és műveletek
description: Ez a témakör információkat nyújt az útvonalakkal és a műveletekkel kapcsolatban.
author: sorenva
manager: tfehr
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMDesigner, BOMDesignerRouteVersion, Route, RouteInventProd, RouteOpr, RouteOprTable, ProdRouteJob, ProdRouteTrans, ProdRouteOverview, ProdRouteJobOverview, ProdRouteJobListPagePreviewPane, RouteTable, RouteVersionFeasibility, ProdRouteJobCurrent, RouteGroup, RouteProductionOrder, EngChgCaseRouteTablePart, EcoResProductProdTypeFormulaNoActiveRouteFormPart,
ms.author: sorenand
audience: Application User
ms.reviewer: kamaybac
ms.custom: 268124
ms.assetid: f78d5836-3e71-42b7-a5d1-41f19228d9d2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f95ecf7faa9f3c89b0a5f65961c42e6ebe7d51df
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/15/2021
ms.locfileid: "5262117"
---
# <a name="routes-and-operations"></a>Útvonalak és műveletek

[!include [banner](../includes/banner.md)]

Ez a témakör információkat nyújt az útvonalakkal és a műveletekkel kapcsolatban. Az útvonal határozza meg egy termék vagy termékváltozat előállításának folyamatát. Leírja az termelési folyamat minden egyes lépését (műveletét), valamint meghatározza a lépések végrehajtásának sorrendjét is. Az útvonal minden egyes lépés esetében meghatározza a szükséges üzemi erőforrásokat, beállítási időt és futtatási időt, továbbá azt, hogy miként kell számítani a költséget.

<a name="overview"></a>Áttekintés
--------

Az útvonal leírja azoknak a műveleteknek a sorrendjét, amelyek egy termék vagy termékváltozat előállításához szükségesek. Az útvonal minden egyes műveletnél meghatározza azt is, hogy milyen üzemi erőforrások szükségesek, mennyi idő kell a művelet beállítására és végrehajtására továbbá azt is, hogy miként kell kiszámítani a költséget. Azonos útvonallal több termék is előállítható, de meghatározhat egyedi útvonalat is minden egyes termékhez vagy termékváltozathoz. Akár egyetlen termékhez is létrehozhat több útvonalat. Ebben az esetben az útvonal olyan tényezők alapján váltakozik, mint például az előállítandó mennyiség. Az útvonal meghatározása a Supply Chain Management szolgáltatásban négy olyan különálló elemből áll, amelyek együttesen leírják a termelési folyamatot:

- **Útvonal** – Az útvonal határozza meg az előállítási folyamat szerkezetét. Más szavakkal a műveletek sorrendjét határozza meg.
- **Művelet** – A művelet egy névvel ellátott lépést jelent az útvonalban, mint például **Összeszerelés**. Azonos művelet több útvonalnál is előfordulhat, így a műveleti számok eltérőek lehetnek.
- **Művelet kapcsolata** – Egy művelet kapcsolata a művelet tulajdonságait határozza meg, így például a beállítási és futási időket, a költségkategóriákat, a fogyasztási paramétereket, valamint az erőforrás-szükségletet. A művelet kapcsolata lehetővé teszi a művelet tulajdonságai számára a változtathatóságot, azon útvonaltól függően, amelyet a művelet használ, illetve az előállított termékektől függően.
- **Útvonalverzió** – Az útvonalverzió határozza meg a termék vagy termékváltozat előállításánál használt útvonalat. Az útvonalverziók lehetővé teszik az útvonalak újrahasznosítását a különböző termékekben, és időről időre módosíthatók. Azt is lehetővé teszik, hogy ugyanannál a terméknél más és más útvonalakat használjanak. Ebben az esetben az útvonal olyan tényezők alapján váltakozik, mint például a hely vagy az előállítandó mennyiség.

## <a name="routes"></a>Útvonalak
Az útvonal leírja azoknak a műveleteknek a sorrendjét, amelyek egy termék vagy termékváltozat előállításánál használatosak. Minden egyes művelethez műveletszámot és következő műveletet rendel a rendszer. A műveletek sorrendje olyan útvonalhálózatot alkot, amely olyan irányított diagramon jeleníthető meg, amelyik egy vagy több kezdőponttal és egy végponttal rendelkezik. A Supply Chain Management programban az útvonalak a szerkezettípus alapján különülnek el. A két útvonaltípus az egyszerű útvonal és az útvonalhálózat. A Gyártásvezérlés paramétereinél megadhatja, hogy csak egyszerű útvonalakat lehet használni vagy összetettebb útvonalhálózatokat is.

### <a name="simple-routes"></a>Egyszerű útvonalak

Az egyszerű útvonalak szekvenciálisak, és az útvonal csak egy kezdőponttal rendelkezik.  

[![Egyszerű útvonal](./media/routes-and-operations-1-simple-route.png)](./media/routes-and-operations-1-simple-route.png)  

Ha csak az egyszerű útvonalakat engedélyezi a Gyártásvezérlési paramétereknél, akkor a Supply Chain Management automatikusan generálja a műveletszámokat (10, 20, 30 és így tovább) az útvonal meghatározásakor.

### <a name="route-networks"></a>Útvonalhálózatok

Ha engedélyezi az összetettebb útvonalhálózatokat a Gyártásvezérlési paramétereknél, akkor olyan útvonalakat is megadhat, amelyek több kezdőponttal rendelkeznek, illetve olyan műveleteket is, amelyek párhuzamosan futhatnak.  

[![Útvonalhálózat](./media/routes-and-operations-2-route-network.png)](./media/routes-and-operations-2-route-network.png)  

> [!NOTE]
> - Minden egyes művelethez csak egy következő művelet tartozhat, és a teljes útvonalnak egyetlen művelettel kell befejeződnie.
> - Ez nem biztosítja, hogy több olyan művelet, amelynek azonos a következő művelete (az előző példában a 30-as és 40-es művelet), ténylegesen párhuzamosan fog futni. Az erőforrások rendelkezésre állása és kapacitása korlátokat szabhat a műveletek ütemezésére vonatkozóan.
> - Műveleti számként a 0 (zéró) nem használható. Ez a szám foglalt, és segítségével megadhatja, hogy az útvonal utolsó művelete nem rendelkezik következő művelettel.

### <a name="parallel-operations"></a>Párhuzamos műveletek

Néha több, különböző tulajdonságokkal rendelkező üzemi erőforrás kombinációja szükséges egy művelet elvégzéséhez. Egy összeszerelési művelethez például szükség lehet egy gépre, egy szerszámra, továbbá minden két géphez egy dolgozóra, aki felügyeli a működését. Ez a példa párhuzamos műveletek segítségével modellezhető, ahol egy művelet ki van jelölve elsődleges műveletként, a többi pedig másodlagosként.  

[![Elsődleges és másodlagos műveleteket tartalmazó útvonal](./media/routes-and-operations-3-parallel-operations.png)](./media/routes-and-operations-3-parallel-operations.png)  

Az elsődleges művelet általában a szűk keresztmetszetű erőforrást jelöli ki, és megszabja a másodlagos műveletek futtatási idejét. Azonban az olyan ütemezés során, amely véges kapacitást foglal magába, a mind az elsődleges műveletre, mind a másodlagos műveletekre ütemezett erőforrásoknak egyidejűleg elérhetőnek kell lenniük, illetve szabad kapacitással kell rendelkezniük.  

Az elsődleges műveletnek és a másodlagos műveletnek azonos műveletszámmal kell rendelkeznie (az előző ábrán ez a szám 30).  

Az előző példában az elsődleges művelet erőforrás-szükséglete (30) a gép, míg a másodlagos műveletek erőforrás-szükségletei (30' és 30'') a szerszám és a dolgozó. Az ötven százalékos terhelés segítségével garantálható, hogy az ütemezett dolgozó egy időben két gépet is felügyelni tud.

### <a name="approval-of-routes"></a>Útvonalak jóváhagyása

Ahhoz, hogy egy útvonal használható legyen a tervezési vagy termelési folyamatban, jóvá kell hagyni azt. A jóváhagyás azt jelzi, hogy az útvonaltervezés befejeződött. Egy kiadott termék vagy kiadott termékváltozat több jóváhagyott útvonallal is rendelkezhet. Jellemzően az útvonal jóváhagyása akkor történik, amikor az első a tárgyhoz tartozó útvonalverzió jóváhagyásra kerül. Egyes üzleti forgatókönyvek esetén azonban az útvonal és az útvonalverzió jóváhagyása különálló tevékenységek, melyekhez különböző folyamattulajdonosok tartozhatnak.  

Minden útvonal külön jóváhagyott vagy jóvá nem hagyott lehet. Vegye figyelembe azonban, hogy jóvá nem hagyott útvonalak esetén az összes kapcsolódó útvonalverzió szintén jóvá nem hagyott. A Gyártásvezérlési paramétereknél megadhatja, hogy megszüntethető-e az útvonalak jóváhagyása, illetve, hogy a jóváhagyott útvonalak módosíthatók-e.  

Ha naplót kell vezetnie, amely rögzíti, hogy melyik útvonalat ki hagyta jóvá, akkor elektronikus aláírásokat kell használni az útvonalak jóváhagyásakor. A felhasználóknak ezt követően meg kell erősíteniük személyazonosságukat egy [elektronikus aláírás](../../fin-and-ops/organization-administration/electronic-signature-overview.md) segítségével.

## <a name="operations"></a>Operations
A művelet a termelési folyamat egy lépése. Minden egyes művelethez tartozik egy azonosító és egy egyszerű leírás. A következő táblázatok egy műhely jellemző műveleteit mutatják be.

| Művelet  | Leírás        |
|------------|--------------------|
| PipeCut    | Csővágás       |
| TIGweld    | TIG-hegesztés        |
| JigAssy    | Jig-szerelvény       |
| Vizsgálat | Minőségvizsgálat |

A művelet tulajdonságai a művelet olyan tulajdonságait határozzák meg, mint például a beállítási és futási időket, az erőforrás-szükségletet, a költségadatokat, valamint a fogyasztási számításokat. (További információkért a műveleti kapcsolatokkal kapcsolatban tekintse meg a következő szakaszt.)

## <a name="operation-relations"></a>Műveleti kapcsolatok
A műveletek következő tulajdonságai maradnak meg a műveleti kapcsolatnál:

- Költségkategóriák
- Fogyasztási paraméterek
- Feldolgozási idők
- Feldolgozási mennyiségek
- Erőforrásigények
- Megjegyzések és utasítások

Egy műveletnél több műveleti kapcsolatot is meghatározhat. Azonban minden egyes műveleti kapcsolat egyetlen műveletre jellemző, és olyan tulajdonságokat tárol, amelyek egy cikkcsoporthoz kapcsolódó útvonalhoz, kiadott termékhez vagy kiadott termékek egy készletéhez tartoznak. Emiatt ugyanazt a műveletet több olyan útvonalnál is használni lehet, amelyek különböző műveleti tulajdonságokkal rendelkeznek. Ezen túlmenően egyszerűbben tudja karbantartani az alapadatokat, ha olyan szabványos műveleteket használ, melyeknek azonosak a műveleti tulajdonságai, tekintet nélkül a használt útvonalra és az előállított termékre. A műveleti kapcsolat hatóköre a **Cikk-kód**, a **Cikk-kapcsolat**, az **Útvonalkód** és az **Útvonalkapcsolat** tulajdonságokkal határozható meg, ahogyan az a következő táblázatban is látható.

| Cikk kódja | Cikk-kapcsolat         | Útvonal kódja | Útvonalkapcsolat   | A műveleti kapcsolat hatóköre                                                                                                                                                                                                                                                                              |
|-----------|-----------------------|------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tábla     | &lt;Cikkazonosító&gt;       | Útvonal      | &lt;Útvonal-azonosító&gt; | Egy művelet alapértelmezett műveleti tulajdonságai olyankor, amikor az **Útvonaszám**=&lt;útvonalazonosító&gt; segítségével állítható elő a kiadott termék az adott **cikkszámmal**=&lt;cikkazonosítóval&gt;.                                                                                                                        |
| Tábla     | &lt;Cikkazonosító&gt;       | Mind        |                  | Egy művelet alapértelmezett műveleti tulajdonságai olyankor, amikor segítségével állítható elő a kiadott termék az adott **cikkszámmal**=&lt;cikkazonosítóval&gt;. Más szóval ezek a műveleti tulajdonságok akkor érvényesek, amikor nincs útvonalspecifikus műveleti kapcsolat megadva a kiadott termékhez.                                     |
| Csoport     | &lt;Cikkcsoport-azonosító&gt; | Útvonal      | &lt;Útvonal-azonosító&gt; | Az útvonalnál használt művelet tulajdonságai, ahol az **Útvonalszám**=&lt;útvonal-azonosító&gt;, melynek segítségével olyan kiadott termékek állíthatók elő, amelyek adott &lt;cikkcsoport-azonosítóval&gt; rendelkező cikkcsoporttal rendelkeznek, hacsak nem útvonalspecifikus műveleti kapcsolat van érvényben a kiadott terméknél.                         |
| Csoport     | &lt;Cikkcsoport-azonosító&gt; | Mind        |                  | Egy művelet alapértelmezett tulajdonságai olyankor, amikor segítségével olyan kiadott termékeket állít elő a rendszer, amelyek cikkcsoporthoz &lt;cikkcsoport-azonosítóhoz&gt; kapcsolódnak, kivéve ha létezik pontosabb műveleti kapcsolat.                                                                                                  |
| Mind       |                       | Útvonal      | &lt;Útvonal-azonosító&gt; | A művelet alapértelmezett tulajdonságai az útvonalban történő használat esetén olyankor, amikor az **Útvonalszám**=&lt;útvonalazonosító&gt;. Más szóval ezek a műveleti tulajdonságok akkor érvényesek, amikor nincs olyan műveleti kapcsolat megadva ennél az útvonalnál, amely a kiadott termékre vagy a kapcsolódó cikkcsoportra jellemző. |
| Mind       |                       | Mind        |                  | Egy művelet alapértelmezett tulajdonságai. Ezek a tulajdonságok akkor érvényesek, ha nem létezik pontosabb műveleti kapcsolat.                                                                                                                                                                |

Azt is megadhatja, hogy egy műveleti kapcsolat egy adott helyre érvényes. Ezzel a módszerrel egy művelet tulajdonságai eltérőek lehetnek a művelet elvégzésénak helyszínétől (azaz a telephelytől) függően. Konfigurált termékek esetén minden egyes termékkonfigurációnál különböző műveleti tulajdonságokat is megadhat.  

A műveleti kapcsolatok révén rendkívül rugalmasan határozhatja meg az útvonalait. Továbbá az alapértelmezett tulajdonságok meghatározásának képessége révén csökkenthető azoknak az alapadatoknak a mennyisége, amelyeket fenn kell tartania. Ez a rugalmasság azonban azt is jelenti, hogy figyelembe kell vennie azt a környezetet, amelyben módosítja a műveleti kapcsolatot.  

> [!NOTE]
> Megjegyzés:? Mivel a műveleti tulajdonságok tárolása az egyes útvonalanként és műveletenként történik, az adott művelet minden előfordulásánál (például összeszerelés) azonos a beállítási idő, a futtatási idő, az erőforrás-szükséglet stb. Ezért ha egy műveletnek kétszer kell előfordulnia ugyanazon az útvonalon, de eltérő futtatási időkkel, létre kell hoznia két külön műveletet, például Összeszerelés1 és Összeszerelés2.

### <a name="modifying-product-specific-routes"></a>Termékspecifikus útvonalak módosítása

Amikor megnyitja az **Útvonal** oldalt a **Megjelent termék részletei** oldalról, akkor megjelennek a kiválasztott kiadott termékhez kapcsolódó útvonalverziók. Ebben az összefüggésben a Supply Chain Management az egyes műveleteknél azokat a műveleti tulajdonságokat jeleníti meg, amelyek legjobban megfelelnek az útvonalverziónak. Észreveheti, hogy a műveletek listája tartalmazza a műveleti kapcsolat **Cikk-kód** és **Útvonalkód** tulajdonságait. Ezáltal megállapíthatja, hogy melyik műveleti kapcsolat látható.  

Az **Útvonal** lapon módosíthatja a művelet tulajdonságait, így például a futtatási időt vagy a költségkategóriákat. A változtatások tárolása az útvonalra jellemző műveleti kapcsolatnál, az aktuális útvonal-verzióban hivatkozott kiadott terméknél történik. Ha a megjelenő műveleti kapcsolat nem az útvonalra és a kiadott termékre jellemző, akkor a rendszer a módosítások tárolása előtt létrehoz egy másolatot a műveleti kapcsolatról. Ez a példány *az* útvonalhoz és a kiadott termékhez kapcsolódik. Emiatt a módosítások nem befolyásolnak más útvonalakat vagy kiadott termékeket. Annak ellenőrzéséhez, hogy melyik kapcsolatot módosítja az **Útvonal** oldalon, ellenőrizze a **Cikk-kód** és az **Útvonalkód** mezőket.  

Emellett manuálisan is létrehozhat egy olyan műveletet, amelye egy útvonalhoz és kiadott termékhez kapcsolódik a **Kapcsolat másolása és szerkesztése** funkció segítségével.  

> [!NOTE]
> Ha új műveletet ad egy útvonalhoz az **Útvonal** oldalon, akkor létrejön egy műveleti kapcsolat csak az aktuálisan kiadott termékhez. Ezért, ha az útvonalat más kiadott termékek előállítására is használják, akkor ezeknek a kiadott termékeknek nem lesz megfelelő műveleti kapcsolata, és az útvonalat már nem lehet használni a kiadott termékek esetében.

### <a name="maintaining-operation-relations-per-route"></a>Műveleti kapcsolatok karbantartása útvonalanként

Amikor megnyitja az **Útvonal részletei** oldalt az **Útvonalak** listaoldalról, akkor megjelenik egy lista az összes olyan műveleti kapcsolatról, amely érvényes a kiválasztott útvonalra. Így könnyen ellenőrizheti, hogy mely műveleti tulajdonságok mely termékeknél használatosak. Egyaránt módosíthatja mind az alapértelmezett tulajdonságértékeket, mind a termékspecifikus tulajdonságértékeket.  

Ha új műveleti kapcsolatot ad meg az **Útvonal részletei** lapon, akkor az **Útvonalkód** mező értéke automatikusan **Útvonal** lesz, az **Útvonalkapcsolat** mezőben pedig az aktuális útvonal útszáma látható.

### <a name="maintaining-operation-relations-per-operation"></a>Műveletenkénti műveleti kapcsolatok karbantartása

A **Műveletek** oldalon megnyithatja a **Műveleti kapcsolatok** oldalt. Ezen az oldalon módosíthatja egy adott művelet minden műveleti kapcsolatát. Akár az alapértelmezett értékeket tartalmazó műveleti kapcsolatokat is módosíthatja.  

Ha a vállalat szokásos műveleteket, és a működési paraméterek azonosak-az összes olyan termékek és eljárások, a **műveleti kapcsolatok** lap itt kényelmesen működési jellemzői, ezek a műveletek karbantartása.

### <a name="applying-operation-relations"></a>Műveleti kapcsolatok alkalmazása

A Supply Chain Management programnak bizonyos esetekben meg kell keresnie egy adott művelet tulajdonságait. Amikor például létrejön egy beszerzési rendelés, az egyes műveletek tulajdonságait át kell másolni a műveleti kapcsolatoktól a termelési útvonalhoz. Ezekben az esetekben a Supply Chain Management a legmegfelelőbb kombinációtól a legkevésbé specifikus kombinációig keresi a releváns műveleti kapcsolatokat.  

Amikor műveletek megkeresi a leginkább megfelelő kapcsolat engedélyezett termék, műveleti kapcsolat, amely a kiadott termék azonosítója megegyezik a Supply Chain Management előnyben műveleti kapcsolat keresztül, hogy megfelel a cikk-csoport azonosítója. Ennek megfelelően az olyan műveleti kapcsolat, amelyik megegyezik a cikkcsoport-azonosítóval, előnyt élvez az alapértelmezett műveleti kapcsolattal szemben. A keresés a következő sorrendben történik:

1.  **Cikk kódja**=**Tábla** és **Cikk-kapcsolat**=&lt;cikkazonosító&gt;
2.  **Cikk kódja**=**Tábla** és **Cikk-kapcsolat**=&lt;cikkazonosító&gt;
3.  **Cikk kódja**=**Mind**
4.  **Útvonal kódja**=**Útvonal** és **Útvonalkapcsolat**=&lt;útvonalazonosítót&gt;
5.  **Útvonal kódja**=**Mind**
6.  **Konfigurációs**=&lt;konfiguráció azonosítója&gt;
7.  **Konfiguráció**=
8.  **Hely**=&lt;helyazonosító&gt;
9.  **Telephely**=

Ezért egy műveletet csak egyszer szabad használni minden egyes útvonalnál. Ha a művelet ugyanazon az útvonalon többször is előfordul, akkor az adott művelet mindegyik előfordulásának ugyanaz lesz a műveletkapcsolata, és Ön nem adhat meg különböző tulajdonságokat (például futtatási időket) az egyes előfordulásokhoz.

## <a name="route-versions"></a>Útvonalverziók

Az útvonalverziók az egyes termékek előállításában fennálló különbségek kezelését teszik lehetővé, illetve kiterjedtebb ellenőrzést biztosítanak Önnek a termelési folyamat felett. Meghatározzák, hogy melyik útvonalat kell használni, amikor egy kiadott termék vagy termékváltozat elkészül. Az alábbi megszorítások segítségével megadhatja, hogy melyik útvonalat szeretné használni a kiadott terméknél:

- Termékdimenziók (méret, szín, stílus vagy konfiguráció)
- Termelési mennyiség
- Termelés helye
- Termelés dátuma

Ha meg vagyunk egy adott helyen egy adott mennyiségű terméket előállító, vagy egy adott időszakban kijelölhet egy adott útvonalverzión az alapértelmezett útvonal verzió. Megjegyzendő azonban, hogy csak egyetlen aktív útvonal engedélyezett egy adott kiadott termék és korlátozások egy adott készletét.  

A termelési paramétereit előírhatja, hogy az érvényességi időtartam egy útvonalverziót, mindig meg kell adni.

### <a name="approval-of-route-versions"></a>Útvonalverziók jóváhagyása

Ahhoz, hogy egy útvonal használható legyen a tervezési vagy termelési folyamatban, jóvá kell hagyni azt. Amikor jóváhagy egy útvonalverziót, akkor az útvonalat is automatikusan jóváhagyja a program. Vegye figyelembe azonban, hogy egy útvonalverzió csak akkor hagyható jóvá, ha a kapcsolódó útvonal is jóvá van hagyva.

### <a name="activating-the-default-route-version"></a>Az alapértelmezett útvonalverzió aktiválása

Amikor aktivál egy útvonalverziót, akkor kijelöli azt alapértelmezett útvonalverzióként, amelyet az alaptervezés használni fog, illetve amelyet a rendszer a termelési rendelések létrehozásakor használ majd. Csak egy aktív útvonalverzióval rendelkezhet a korlátozások egy adott készletéhez (például időszak, telephely vagy mennyiség). Hibaüzenetet kap, ha a verzió, amit aktiválni próbál, ütközik egy verzióval, ami már aktív. Ezután vagy hatástalanítania kell az ütköző verziót vagy módosítania kell a verzió megszorításait (jellemzően az időszakot), hogy megakadályozza a kétértelmű aktivációt.

### <a name="electronic-signatures"></a>Elektronikus aláírások

Ha naplót kell vezetnie, amely rögzíti, hogy melyik útvonalverziót ki hagyta jóvá, akkor elektronikus aláírásokat kell használni ezeknél a feladatoknál. Az útvonalverziókat jóváhagyó és aktiváló felhasználóknak ezt követően igazolniuk kell személyazonosságukat egy [elektronikus aláírás](../../fin-and-ops/organization-administration/electronic-signature-overview.md) segítségével.

### <a name="product-change-that-uses-case-management"></a>Termékmódosítás, amely esetkezelést használ.

A termékmódosítási eset új vagy módosított anyagjegyzékek vagy anyagjegyzék verziók jóváhagyása és aktiválása esetén egyszerű módot biztosít, hogy áttekintsük az anyagjegyzék verziók megszorításait. Jóváhagyása és aktiválása adott módosítását egyetlen művelettel kapcsolatos, és az eredményeket a termék Kisbetű-nagybetű dokumentum összes útvonalat is.

## <a name="maintaining-routes"></a>Útvonalak karbantartása

Üzleti szükségletektől függően előfordulhat, amely szükséges annak érdekében, hogy a folyamat meghatározása az erőkifejtés csökkentése érdekében.

### <a name="making-routes-independent-of-resources"></a>Erőforrásoktól független útvonalak készítése

Számos rendszerben meg kell határozni azt a művelet-erőforrást vagy erőforráscsoportot, amelynek el kell végeznie egy műveletet. A Supply Chain Management programban azonban megadhatja a szükségletek egy olyan készletét, amelynek teljesülnie kell a műveletre való alkalmazhatóság érdekében. Ezért a konkrét műveletek erőforrás vagy erőforrás csoport használandó nem kell addig, amíg a művelet éppenséggel korábbra kell meghatározni. Ez a szolgáltatás akkor különösen hasznos, ha sok a munkavállalók vagy gépek, amelyek ugyanazt a műveletet lehet végrehajtani.  

Például megadhatja a egy művelethez egy műveletek erőforrás, a **gép** típusú, amelynek a **Stamping** képességének 20 tonna. Az ütemezési motor majd megoldja ezeket a követelményeket, a konkrét műveletek erőforrás vagy erőforrás csoport ütemezése a művelet során. Most adhatja meg ezeket a követelményeket nem kötelező a művelet egy adott gép, mert akkor sokkal nagyobb rugalmasságot. Továbbá karbantartás akkor könnyebb, ha erőforrásokat helyez át, és az új erőforrások hozzáadása.  

A különféle erőforrás-igényű, és használatukkal kapcsolatos további tudnivalókért lásd: erőforrás-igényű műveleteket és [erőforrás-képességek](resource-capabilities.md).

### <a name="sharing-routes-across-sites"></a>Útvonalak megosztása a helyek között

Ha egynél több termelési helyszínen azonos termék előállításában, és ha a terméket előállító lépéseket minden azonos telephelyen, gyakran használt összes termelési hely megosztott útvonalat tervezhet. Megosztott útvonal létrehozásához ne adjon meg olyan helyet, amely magán az útvonalon található. Azonban továbbra is létre kell hoznia egy olyan útvonalverziót, amelyik hozzárendeli a megosztott útvonalat a termékkel minden egyes hely esetében.  

Biztosítani kell azt is, hogy az útvonalon végrehajtott egyes műveletek erőforrás-követelményei ne írjanak elő konkrét műveleti erőforrásokat vagy erőforráscsoportokat, hanem kifejezésük a szükséges erőforrások jellemzői alapján történjen. Az ütemezőmotor ezután képes lesz a megfelelő üzemi erőforrás hozzárendelésére arról a helyszínről, ahová a gyártást ütemezték. Ha például a futási időben enyhe eltérések vannak, vagy ha egy adott művelet beállítási ideje helyspecifikus, akkor megadhatja ezt az információt egy másik műveleti kapcsolat hozzáadásával az adott webhely számára.  

A megosztott útvonalak előnyeinek teljes kihasználása érdekében a megfelelő anyagjegyzéknél (BOM) is használnia kell az erőforrás-fogyasztást. Amikor beállítja az erőforrás-fogyasztás jelzőjét a BOM soron, a raktár és a hely, ahonnan a nyersanyagokat fogyasztani, kell, abból az üzemi erőforrásból származik, amelynél a művelet ütemezve van. Emiatt a raktárat és a helyszínt nem kell meghatározni addig, amíg a termelés nincs ténylegesen beütemezve. Így mind az anyagjegyzék, mind az útvonal függetleníthető attól a fizikai helytől, ahol a terméket előállítják.

### <a name="standard-operation-relations"></a>Normál műveleti kapcsolatok

Ha a vállalat termelési egész szabványosított műveleti, és ha alig vagy egyáltalán nem változása a beállítási idő, Üzemidő, felhasználás számításhoz, költségszámítás, és stb akkor előnyt jelenthet az alapértelmezett minden műveletre vonatkozóan műveleti kapcsolatok létrehozása. Ebben az esetben ne jellemző bármely útvonalon vagy termék, amely a műveleti kapcsolatok létrehozása.  

Ha is express erőforrás-igényű készségek és képességek, és az útvonalak hely független legyen, segíthet az üzleti folyamatok folyamatos fenntartását folyamatosan legalább.  

Ez a módszer használata esetén a **műveleti kapcsolatok** oldal lesz az elsődleges cél fenntartásához a Lefutási idő és egyéb tulajdonságokat.

### <a name="resource-specific-process-times"></a>Erőforrás-specifikus feldolgozási idők

Ha nem ad meg üzemi erőforrást vagy erőforráscsoportot egy művelet erőforrásigényének részeként, az alkalmazott erőforrások különböző sebességgel működhetnek. Emiatt az egy-egy művelet feldolgozásához szükséges idő változó lehet. A probléma megoldásához használhatja a műveleti kapcsolat **Képlet** mezőjét, ahol megadhatja a feldolgozási idő kiszámításának módját. Az alábbi lehetőségek közül választhat:

- **Szabványos** – (Alapértelmezett beállítás) A számítás csak a műveleti kapcsolat mezőit használja, és megszorozza a megadott futási időt a rendelés mennyiségével.
- **Kapacitás** – A számítás magába foglalja a **Kapacitás** mezőt az üzemi erőforrásból. Ezért az idő erőforrásfüggő. Az üzemi erőforrásnál megadott érték óránkénti kapacitás. A **Feldolgozási időt** úgy számítja ki a rendszer, hogy a **Rendelési mennyiséget** a **Kapacitással** elosztja.
- **Köteg** – A kötegkapacitás kiszámítása a műveleti kapcsolat adatainak felhasználásával történik. Ezt követően a rendelt mennyiség alapján kiszámítható a kötegek száma, és így a feldolgozási idő is.
- **Erőforrásköteg** – Ez a lehetőség gyakorlatilag megegyezik a **Köteg** beállítással. A számítás azonban magába foglalja a **Kötegkapacitás** mezőt a műveletek erőforrás mezőből. Ezért az idő erőforrásfüggő.

### <a name="set-up-route-groups"></a>Útvonalcsoportok beállítása

Meg lehet adni az útvonalcsoportokat és az útvonal vagy feladattípus típusok beállítását a **Gyártásvezérlés > Beállítás > Útvonalak > Útvonal-csoportok** helyen. Minden Útvonal/feladattípushoz az útvonalcsoportban bejölheti vagy törölheti a következőket:

- **Aktiválás** Jelölje be ezt a lehetőséget ahhoz, hogy engedélyezze a számításokat és az ütemezést a kiválasztott feladattípushoz, illetve visszajelzést kapjon a feladatütemezés futtatásakor. Ezzel a beállítással engedélyezheti a feladattípust, és válaszhatja ki a további beállításokat ahhoz a munkatípushoz. Ha az aktiválás nincs bejelölve, az a feladattípus nem lesz engedélyezve, függetlenül a többi beállítás kiválasztásától. 
- **Feladatkezelés** Jelölje be ezt az opciót, hogy a feladattípus szerepeljen feladatkezelésben a feladatütemezés futtatásakor. 
- **Munkaidő** Jelölje be ezt a beállítást, hogy a feladat típusának az üzemi erőforrásoknál meghatározott naptár szerinti ütemezéséhez, máskülönben a Gregorián naptár lesz használva. A munkaidő ütemezése a Gergely-naptár vagy a megadott munkanaptár révén adható meg. Ha ezt a lehetőséget választja, az ütemezés a megadott munkanaptáron alapul. Ezenkívül a feladattípus feladatának ütemezése a projekt kezdő dátumának napján éjféltől van.
- **Kapacitás** – Jelölje be ezt az opciót, hogy a feladattípushoz lefoglalja a kapacitást a feladatütemezés futtatásakor. Ha bejelöli ezt az opciót, hogy a feladattípushoz lefoglalja a kapacitást a kiválasztott feladattípus ütemezésének futtatásakor. Ez lehetővé teszi, hogy áttekintse, hogy mely útvonalcsoportokban mely feladattípusok használják az üzemi erőforrásokat. Például egy olyan esetben, ha szárítási erőforrások szűk keresztmetszetű erőforrások, az erőforrásokról meg kell adni, hogy szűk keresztmetszetűek. A szárítási műveletek, amelyek várakozási idő feladattípusúak, szárítási erőforrásokat fognak lefoglalni. 

A feladattípusok mindegyikéhez először aktiválnia vagy deaktiválnia kell azt. Ha ki van kapcsolva semmilyen más beállítás (feladatkezelés, munkaidő és a kapacitás) nem lesz figyelembe véve, mivel a feladat típusa nem lesz aktív. 

A feladattípusok között megtalálja az Átfedést. Átfedés lehetővé teszi, hogy a különböző feladatok, egyidőben legyenek végrehajtva. Ha a feladatok átfedésben vannak, az erőforrások használhatók, de nem foglalhatók le meghatározott feladatokhoz.
Ezért, ha az Aktiválás van kiválasztva az Átfedéshez a többi beállítás (feladatkezelés, munkaidő és a kapacitás) nem befolyásolják ezt az útvonalcsoportot. 

> [!NOTE]
> Verziók frissítésekor előfordulhat a következő hiba: **„Az ütemezési motor meghívása során CLR-hiba történt.”**. Ha ezt a hibát kapja menjen az **Útvonal-csoportok** lap és minden az útvonalon, ahol aktiválta az **Átfedést**, törölje a jelet a **Feladatkezelés**, **Munkaidő** és **Kapacitás** beállításokból. 

## <a name="additional-resources"></a>További erőforrások

- [Anyagjegyzékek és receptúrák](bill-of-material-bom.md)

- [A termelési útvonaltervezésben használt költségkategóriák](../cost-management/cost-categories-used-production-routings.md)

- [Erőforrás-képességek](resource-capabilities.md)

- [Az elektronikus aláírás áttekintése](../../fin-and-ops/organization-administration/electronic-signature-overview.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]