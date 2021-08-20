---
title: Kiskereskedelmi csatornák készletelérhetőségének kiszámítása
description: Ez a témakör azt mutatja be, hogyan használhatja a Microsoft Dynamics 365 Commerce szolgáltatást a termékek becsült aktuális elérhetőségét az online és üzleti csatornán.
author: hhainesms
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2020-02-11
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: da79aadace09ad480fa34bc03220831023e469645bb7d53af1647bd2d35af0ea
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741812"
---
# <a name="calculate-inventory-availability-for-retail-channels"></a>Kiskereskedelmi csatornák készletelérhetőségének kiszámítása

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan használhatja a Microsoft Dynamics 365 Commerce szolgáltatást a termékek becsült aktuális elérhetőségét az online és üzleti csatornán.

## <a name="accuracy-of-inventory-availability"></a>Készlet rendelkezésre állásának pontossága

A Commerce több kiszolgálót és adatbázist használ a méretezhetőség és a teljesítmény biztosítására. Ezért fontos, hogy megértse, hogy a pénztár (POS) alkalmazáson keresztül biztosított elérhető készletértékek, az e-kereskedelmi készletelérhetőségi alkalmazásfejlesztői felületek (API-k) és a Kereskedelmi központ aktuális készletre vonatkozó oldalai valós időben nem mindig 100%-os pontosságúak. Ha a termékekhez az online vagy áruházi csatornában létrehozott tranzakciókat még nem szinkronizálták a központtal, a központ aktuális készletre vonatkozó oldalai lehet, hogy nem pontos valós idejű készletértékeket jelenít meg az adott termékekhez. Ha úgy konfigurálta a vállalatot, hogy a központ vagy más integrált alkalmazások felhasználói áruházi vagy online raktárban található készletet értékesíthetnek, fogadhatnak, visszaküldhetnek vagy bármilyen módon módosíthatnak, a pénztár vagy az online csatorna lehet, hogy nem rendelkezik minden adattal, ami a cikkek pontos valós idejű értékének megjelenítéséhez szükséges.

Fontos, hogy megértse, hogy az üzemeltetési nap során megadott összes rendelkezésre álló adatot becsült értéknek tekinti a rendszer. Ezért ha megpróbálja összehasonlítani azokat az aktuális készlet-adatokat, amelyeket az alkalmazás tényleges fizikai készletként ad meg a polcokon, vagy ha megpróbálja összehasonlítani a pénztárban rendszernél megjelenített aktuális értékeket azon aktuális adatokkal, amelyek ugyanarra a raktárra vonatkoznak a központban, az értékek eltérhetnek. Az üzemeltetési nap során ez a különbség várható, és nem tekinthető problémának. Ha ellenőrizni szeretné az adatokat, és biztosítani szeretné, hogy a pénztárban, az API-kban és a központban megadott értékek megegyeznek az áruház vagy raktár polcain található tényleges fizikai egységekkel, akkor ezt akkor végezheti el leghatékonyabban, amikor az adott napon befejeződtek a csatornaműveletek, és az összes tranzakció megfelelően szinkronizálódott a központ és a csatornák között.

## <a name="channel-side-inventory-calculation"></a>Csatornaoldali készletszámítás

A csatornaoldali készletszámítás olyan mechanizmus, amely kiindulási alapként a Kereskedelmi központ utolsó ismert csatornakészlet-adatait veszi figyelembe, majd beleszámítja azokat a további, csatornaoldalon bekövetkezett készletváltozásokat, amelyek nem szerepelnek a kiindulási alapban, és ennek segítségével számítható ki az aktuális készlet szinte valós idejű becsült értéke. 

A csatornaoldali készletszámítási logikában jelenleg a következő készletváltozások vannak figyelembe véve:

- Az üzletben készpénzzel kifizetett és azonnal átvett rendelésekkel értékesített készlet
- Üzletben vagy online csatornán keresztül, vevői rendelések által értékesített készlet
- Az üzletnek visszaküldött készlet
- Az üzlet raktárából teljesített (kitárolt, csomagolt, szállított) készlet

A csatornaoldali készletszámítás alkalmazásához előfeltételként a csatorna-adatbázisoknak el kell küldeni egy időszakos pillanatképet a központból származó, a **Termék elérhetősége** feladat által létrehozott adatokról. A pillanatkép a központ azon adatait jeleníti meg, amelyek a termék vagy a termék változatának és a raktárnak egy meghatározott kombinációját jelentik. Ez csak azokat a készlettranzakciókat tartalmazza, amelyek feldolgozása és feladása a központban a pillanatkép készítésekor történt meg, és elképzelhető, hogy valós időben nem 100%-os pontosságú a felosztott kiszolgálókon történő folyamatos értékesítési feldolgozás miatt.

- Ha a készletet egy üzlet egyik termékeként adták el készpénzzel fizetett, azonnal átvett vagy aszinkron ügyfélmegrendelési értékesítés során a pénztáralkalmazásban, a központ nem rendelkezik majd információval azonnal az értékesítés kapcsolódó készletprobléma-tranzakciójáról. A központ az ilyen típusú üzleti értékesítések során eladott készletekkel kapcsolatban csak azután kap információt, miután a P-feladat feltöltötte a kapcsolódó tranzakciót az üzlet csatorna-adatbázisából a központba, és a kapcsolódó értékesítési rendelések létrejönnek kimutatásfeladás vagy folyamatos apránkénti közzétételi folyamatok során. A rendelések központban történő létrehozási folyamata létrehozza a kapcsolódó készlettranzakciókat. 
- Az e-kereskedelmi csatorna megrendelései esetén a központ csak azután rendelkezik információkkal a készlettranzakciókról, miután a tranzakciókat elküldték a központba a P-feladaton keresztül, és a rendelések szinkronizálási folyamata befejeződött.

Ha a központ alkalmazásban szeretné pillanatképet készíteni a készletről, hajtsa végre az alábbi lépéseket.

1. Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem IT \> Termékek és készlet \> Termékelérhetőség** lehetőségre.
1. Válassza az **OK** gombot a **Termékelérhetőség** feladat futtatásához. Ez a feladat ütemezhető úgy is, hogy egy kötegben fusson.

A **Termék elérhetősége** feladat futásának befejeződése után a rögzített adatokat közzé kell tenni az e-kereskedelmi csatorna-adatbázisokba, hogy a legújabb központból származó készletpillanatképet figyelembe vehessék a becsült tényleges készlet csatornaoldali számításakor.

A központból származó pillanatképadatoknak a csatorna-adatbázisokba való szinkronizálásához kövesse ezeket a lépéseket.

1. Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.
1. Futtassa az **1130** (**Termékelérhetőség**) feladatot a pillanatkép-adatok szinkronizálásához, amelyeket a **Termékelérhetőség** feladat hozott létre a központból a csatorna-adatbázisaiba.

## <a name="inventory-availability-apis-for-e-commerce"></a>Raktárelérhetőségi API-k az e-kereskedelemhez

A Commerce a következő, e-kereskedelmi esetekben használt API-k számára biztosítja a termékkészlet rendelkezésre állásának lekérdezését:

- **GetEstimatedAvailability** - Ezzel az API-val lekérdezhető egy termék vagy termékváltozat készlete az online csatorna raktárában vagy raktáraiban, amelyek az online csatorna teljesítési csoportjához kapcsolódnak.
- **GetEstimatedProductWarehouseAvailability** – Ezzel az API-val lekérhető egy termék vagy termékváltozat készlete egy megadott raktárból.

> [!NOTE]
> Ezek az API-k helyettesítik a **GetProductAvailabilities** és **GetAvailableInventoryNearby** API-kat a Commerce 10.0.7-es és korábbi verzióiban.

Mindkét API belsőleg használja a csatornaoldali számítási logikát, és visszaadja a kért termékre és raktárra vonatkozó becsült **elérhető aktuális** mennyiséget, **elérhető teljes** mennyiséget, **mértékegységet** és **készletszintet**. A visszaadott értékek kívánság szerint megjelenhetnek az e-kereskedelmi webhelyen, vagy felhasználhatók az e-kereskedelmi webhely egyéb üzleti logikájának kiváltására. Meg lehet akadályozni például a „nincs készleten” készletszinttel rendelkező termékek megvásárlását.

Bár más, a Commerce-ben elérhető API-k közvetlenül a központból is lekérhetik a termékek tényleges készletmennyiségeit, nem javasoljuk ezek e-kereskedelmi környezetben való használatát a lehetséges teljesítményproblémák miatt, és a gyakori kérések központi kiszolgálókra tett kapcsolt hatása miatt. Ezenkívül a csatornaoldali számítás során a két fent említett API pontosabb becslést nyújthat a termékek elérhetőségével kapcsolatban, figyelembe véve a csatornákban létrehozott tranzakciókat, amelyek még nem ismertek a központ számára.

A két API-használatához engedélyeznie kell az **Optimalizált termékelérhetőségi számítás** funkciót a **Funkciókezelés** munkaterület segítségével, a központban. Ha az online és üzleti csatornák ugyanazt a teljesítési raktárt használják, akkor a **Továbbfejlesztett e-kereskedelmi csatornaoldali készletszámítási logika** funkciót is engedélyeznie kell, hogy a csatornaoldali számítási logika szerepeljen a két API-ban, amellyel figyelembe vehetők a nem feladott tranzakciók (készpénzzel fizetett, azonnal átvett, vevői rendelések, visszáruk), amelyeket az üzlet csatornájában hoztak létre. A funkciók engedélyezése után le kell futtatnia az **1070**-es (**Csatornakonfiguráció**) feladatot.

A következő lépések szerint adhatja meg, hogyan adja vissza a termékmennyiséget az API kimenete.

1. Lépjen a **Retail és Commerce \> Központ beállítása \> Paraméterek \> Commerce paraméterek** menüpontra.
1. Válassza a **Készlet** lapot, majd a **Készlet elérhetősége API-k az e-kereskedelemhez** gyorslapon konfigurálja a **Mennyiség az API kimenetáben** beállítás értékét.
1. Futtassa az **1070** (**Csatornakonfiguráció**) feladatot a legújabb beállítások csatornákkal való szinkronizálásához.

A **Mennyiség az API kimenetében** beállítás három lehetőséget kínál:

- **Visszadott készletmennyiség** - A kért termék elérhető tényleges és elérhető teljes mennyiségét adja vissza a rendszer az API kimenetében.
- **Visszaadott készletmennyiség mínusz készletpuffer** – Az API kimenetében visszaadott mennyiség, amelyet a készletpuffer értékének levonásával korrigáltak. További információért a készletpufferrel kapcsolatban lásd: [Készletpufferek és készletszintek konfigurálása](inventory-buffers-levels.md).
- **Nincs visszaadott készletmennyiség** – Az API kimenete csak a készletszintet adja vissza. További információért a készletszintekkel kapcsolatban lásd: [Készletpufferek és készletszintek konfigurálása](inventory-buffers-levels.md).

A `QuantityUnitTypeValue` API-paraméter használatával lehet megadni, hogy milyen egységtípusban adja vissza az API a mennyiséget. Ez a paraméter támogatja a **készletegység** (alapértelmezett), a **beszerzési egység** és az **értékesítési egység** beállításait. A rendszer a visszaadott mennyiséget a központ megfelelő mértékegységének meghatározott pontosságára kerekíteni.

A **GetEstimatedAvailability** API a következő bemeneti paramétereket kínálja fel a különböző lekérdezési helyzetek támogatása érdekében:

- `DefaultWarehouseOnly`– Ezzel a paraméterrel az online csatorna alapértelmezett raktárában lekérdezhető egy termék készlete. 
- `FilterByChannelFulfillmentGroup`és `SearchArea` – ennek a két paraméternek a használatával lehet lekérdezni egy termék készletét egy adott keresési terület minden felvételi helyéről a `longitude`, a `latitude` és a `radius` értéke alapján. 
- `FilterByChannelFulfillmentGroup`és `DeliveryModeTypeFilterValue` – ennek a két paraméternek a használatával lehet lekérdezni egy termék készletét olyan megadott raktárakból, amelyek az online csatorna teljesítési csoportjához vannak kapcsolva, és úgy vannak konfigurálva, hogy támogassanak bizonyos szállítási módokat. A `DeliveryModeTypeFilterValue` paraméter támogatja az **összes** (alapértelmezett), **szállítás** és **átvétel** beállítást. Például olyan helyzetekben, amikor egy online rendelés több szállítási raktárból is teljesíthető, e két paraméter használatával lekérdezhető egy termék készletének elérhetősége az összes ilyen szállítási raktárból. Ebben az esetben az API visszaadja a termék aktuális mennyiségét és készletszintjét az egyes szállítási raktárakban, valamint az összesített mennyiségét és összesített készletszintet a lekérdezés hatókörében szereplő összes szállítási raktárból.
 
A Commerce vásárlásmező, áruházválasztó, kívánságlista, kosár és kosárikon moduljai a fentiek szerint használják fel az API-kat és a paramétereket a készletszinttel kapcsolatos üzenetek megjelenítéséhez az e-kereskedelmi webhelyen. A Commerce-webhelykészítő különféle készletbeállításokat biztosít az árusítás és a beszerzés viselkedésének szabályozásához. További információk: [Készletbeállítások alkalmazása](inventory-settings.md).

## <a name="pos-inventory-lookup-with-channel-side-calculation"></a>Pénztár készletkeresése csatornaoldali számítással

A Commerce 10.0.9-es és korábbi kiadásaiban a pénztár **Készletkeresés** művelete valós idejű központba irányuló szolgáltatáshívást használt a kiválasztott termék készletinformációinak lekéréséhez, mind a felhasználó aktuális üzletéhez, mint bármely más, a teljesítési csoporthoz az üzlet csatornakonfigurációjának részeként konfigurált üzletekhez. A Commerce 10.0.10-es és újabb kiadásaiban kikapcsolhatja a központba irányuló valós idejű szolgáltatáshívásokat, és ehelyett csatornaoldali számítást használhat a Commerce kiszolgálón az aktuális, ténylegesen elérhető készlet megállapításához az üzletre és bármely olyan helyre vonatkozóan, amely meg van határozva a teljesítési csoportban. Ez a csatorna által számított készletkonfiguráció olyan helyeknél is hasznos, ahol az internetkapcsolat nem megbízható, mert nem kell online lennie a készletkeresések fogadásához a központból.

Amikor a csatornaoldali számítást helyesen konfigurálták és kezelték, megbízhatóbb becslést biztosíthat az aktuális üzletkészletről, mivel a Kereskedelmi csatorna-adatbázisban található tranzakciós adatokat használ, amelyről a központ még lehet, hogy nem tud. Ha például a pénztár készletkereséseire vonatkozó meglévő valós idejű szolgáltatáshívást használja, a központ valószínűleg még nem rendelkezik az információval a termékkel éppen történt készpénzzel fizetett és azonnal átvett értékesítésről. Így a központ által az adott termékre vonatkozóan visszadatott tényleges készlet értéke valószínűleg meghaladja az üzlet aktuális tényleges készletét egy egységgel. Ha viszont a csatornaoldali számítást használja, akkor a készpénzzel fizetett és azonnal átvett értékesítést a rendszer beleszámítja a számításba, és levonja a megjelenő tényleges értékből. Annak ellenére, hogy a csatornaoldali számítás és a valós idejű szolgáltatáshívások által biztosított értékek is csak a tényleges készlet becslését jelentik, a csatornaoldali számítás által adott érték nagyobb valószínűséggel pontos az aktuális üzletre nézve.

Ha konfigurálni szeretné a pénztári **Készletkeresés** művelet a Commerce Headquarters rendszerében ahhoz, hogy használhassa a csatornaoldali számítási logikát és kikapcsolhassa a valós idejű szolgáltatáshívásokat, először engedélyeznie kell az **Optimalizált termékelérhetőségi számítás** funkciót a **Funkciókezelés** munkaterületen a Commerce Headquartersben, majd követnie kell ezeket a lépéseket.

1. Ugorjon a következő elemre: **Retail és Commerce \>  Csatorna beállítása \> Pénztárbeállítás \>  Pénztárprofilok \> Funkcióprofilok**.
1. Válasszon funkcióprofilt.
1. A **Funkciók** gyorslap **Készletelérhetőségi számítás** szakaszában módpsítsa a **Készletelérhetőségi számítás módja** értékét **Valós idejű szolgáltatásról** **Csatornára**. Alapértelmezés szerint az összes funkcióprofil valós idejű szolgáltatási hívásokat használ. Módosítania kell ennek a mezőnek az értékét, ha csatornaoldali számítási logikát szeretne használni. A módosítás hatással van minden olyan kiskereskedelmi üzletre, amely a kiválasztott funkcióprofilhoz van társítva.

Ezután a következő lépések végrehajtásával szinkronizálni kell a csatornákon végzett módosításokat az elosztási ütemezési folyamaton keresztül a központban.

1. Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.
1. Futtassa a **1070** (**csatornakonfiguráció**) feladatot.

A konfiguráció befejezését követően a fizikailag elérhető készletről kapott adatok már nem használnak valós idejű szolgáltatási hívást, amikor a pénztár alkalmazásban a felhasználó a **Készletkeresés** műveletet használja (normál és mátrix nézet). Helyette az aktuális üzlet, valamint a teljesítési csoportba tartozó összes üzlet ténylegesen rendelkezésre álló készletét a Kereskedelmi központ programból a csatorna-adatbázishoz szállított legutóbbi pillanatkép alapján számítja ki a program. A csatornaoldali számítás tovább finomítja a pillanatfelvétel értékét, hogy a ténylegesen rendelkezésre álló értéket módosítsa a csatorna-adatbázis azon kiválasztott termékéhez tartozó további értékesítési vagy visszáru-tranzakciók alapján, amelyek nem szerepelnek az 1130-as feladat legutóbbi szinkronizált pillanatképén. Ha a csatorna-adatbázis nem tartalmaz tranzakciós adatokat a teljesítési csoportban szereplő bármely raktárakhoz vagy üzletekhez, akkor nem tartalmaz olyan további tranzakciókat, amelyek az érték újraszámításához használhatók fel. Ezért az adott raktáraknál vagy üzleteknél a tényleges készletre vonatkozóan megjelenített legjobb besclés a legutóbb ismert Kereskedelmi központ-pillanatképről származó adat.

A pénztár **Rendelésteljesítés** képernyői szintén a csatornaoldali számítással mutatják a cikkek tényleges készletét, amikor egy rendelésteljesítési sor ki van jelölve, és a felhasználó megtekinti a **Részletek** panelt a kiválasztott cikk tényleges készletéhez.

## <a name="optimize-your-inventory-data"></a>A készlet adatainak optimalizálása

A készlet lehető legjobb becslésének biztosításához fontos, hogy a következő Commerce kötegelt feladatokat használja, és gyakran futtassa azokat:

- **P-feladat** – a P-feladat a **felosztási ütemezések** oldalon található, és gyakran kell futtatni. Ez a feladat az e-kereskedelmi rendeléseket, a pénztár által létrehozott aszinkron vevői rendeléseket, és a csatorna-adatbázisokból létrehozott készpénzzel fizetett és azonnal átvett rendeléseket átviszi a a Kereskedelmi központ rendszerbe, amelyek itt tovább feldolgozhatók. Amíg ez az adat szinkronizálva van a csatornáról a a Kereskedelmi központ rendszerbe, a Kereskedelmi központ nem tartalmaz adatokat a raktárak azon termékeihez, amelyek az adott tranzakciókból erednek.
- **Rendelések szinkronizálása** – ez a feladat a Kereskedelmi központ nyers tranzakciós adatait dolgozza fel, amelyekkel a P-feladat a Kereskedelmi központ értékesítési rendeléseibe az e-kereskedelmi és az aszinkron vevői rendelési tranzakciókat biztosítja és átalakítja. A feladat feldolgozása és az értékesítési rendelések létrehozása előtt nem jönnek létre készlettranzakciók. Ennélfogva a Kereskedelmi központ aktuális készlete nem veszi figyelembe a tranzakciókat.
- **Tranzakciós kimutatások számítása kötegben** – az üzletben létrejövő készpénzzel fizetett és azonnal átvett tranzakciók esetében a folyamatos, apránkénti feladás folyamata biztosítja, hogy a rendszer az értékesítéshez kapcsolódó készletet hatékonyan frissítse. A készpénzzel fizetett, azonnal átvett rendelésekhez tartozó készlettranzakciók leghatékonyabb feldolgozásához győződjön meg arról, hogy a rendszer a [folyamatos apránkénti feladás](./trickle-feed.md) használatára van beállítva.
- **Tranzakciós kimutatások feladása kötegben** – ez a feladat is szükséges a folyamatos, apránkénti feladáshoz. Ez a **Tranzakciós kimutatások kötegelt kiszámítása** feladatot követi. Ez a feladat rendszeresen feladja a kiszámított kimutatásokat, hogy a Kereskedelmi központban jöjjenek létre a készpénzzel fizetett, azonnal átvett értékesítéshez tartozó értékesítési rendelések, és a Kereskedelmi központ így pontosabban mutassa az üzlet készletét.
- **Termék elérhetősége** – ez a feladat létrehozza a Kereskedelmi központ-készletből származó készlet pillanatfelvételét.
- **1130 (termék elérhetősége)** – Ez a feladat az **elosztási ütemezések** oldalon található, és a **termék elérhetősége** feladatát követően azonnal futtatható. Ez a feladat szállítja a készlet-pillanatfelvétel adatait a Kereskedelmi központ rendszerből a csatorna-adatbázisba.

> [!NOTE]
> - Bevált gyakorlat a **Termék elérhetősége** és **1130** feladatok futtatása óránként, és ugyanilyen vagy magasabb gyakorisággal javasolt a P-feladat ütemezése, rendelések szinkronizálása és a feladáshoz kapcsolódó feladatok folyamatos, apránkénti feldolgozása.
> - Teljesítménnyel kapcsolatos okokból, amikor a csatornaoldali készletelérhetőségi számításokkal hoznak létre egy készletelérhetőségi kérést az e-kereskedelmi API-k vagy a pénztári csatornaoldali készletlogika használatával, a számítás gyorsítótárat használt annak meghatározására, hogy elég idő telt-e el, hogy igazolható legyen a számítási logika újbóli futtatása. Az alapértelmezett gyorsítótár értéke 60 másodperc. Például bekapcsolta az üzlet csatorna-oldali számítását, és megtekintette egy termék tényleges készletét a **készletkeresés** oldalán. Ha a termék egy egységét értékesítik, akkor a **készletkeresés** lapja nem jeleníti meg a csökkentett készletet mindaddig, amíg a gyorsítótár ki nem ürül. Miután a felhasználó feladta a tranzakciókat a pénztárban, várnia kell 60 másodpercig, mielőtt ellenőrizheti, hogy a tényleges készlet csökkent.

Ha az üzleti helyzethez kisebb gyorsítótárazási idő szükséges, forduljon a terméktámogatási szolgálat képviselőjéhez.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
