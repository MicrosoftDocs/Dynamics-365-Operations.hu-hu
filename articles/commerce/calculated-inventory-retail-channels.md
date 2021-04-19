---
title: Kiskereskedelmi csatornák készletelérhetőségének számítása
description: Ez a témakör azt mutatja be, hogy milyen lehetőségek érhetők el az üzlet és az online csatornák aktuális készletének megjelenítéséhez.
author: hhainesms
ms.date: 08/13/2020
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
ms.openlocfilehash: 29efccab017d9dff98872871bfe953fba19d2c30
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799685"
---
# <a name="calculate-inventory-availability-for-retail-channels"></a>Kiskereskedelmi csatornák készletelérhetőségének kiszámítása

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan használhatja a Microsoft Dynamics 365 Commerce szolgáltatást a termékek becsült aktuális elérhetőségét az online és üzleti csatornán.

## <a name="accuracy-of-calculation"></a>Számítás pontossága

A Commerce több kiszolgálót és adatbázist használ a méretezhetőség és a teljesítmény biztosítására. Ezért fontos, hogy megértse, hogy a pénztár (POS) alkalmazáson keresztül biztosított elérhető készletértékek, az e-kereskedelmi készletelérhetőségi alkalmazásfejlesztői felületek (API-k) és a Kereskedelmi központ aktuális készletre vonatkozó oldalai valós időben nem mindig 100%-os pontosságúak. Ha a termékekhez az online vagy áruházi csatornában létrehozott tranzakciókat még nem szinkronizálták a Kereskedelmi központ kiszolgálójával és adatbázisával, a Kereskedelmi központ aktuális készletre vonatkozó oldalai lehet, hogy nem pontos valós idejű készletértékeket jelenít meg az adott termékekhez. Ha úgy konfigurálta a vállalatot, hogy a Kereskedelmi központ vagy más integrált alkalmazások felhasználói áruházi vagy online raktárban található készletet értékesíthetnek, fogadhatnak, visszaküldhetnek vagy bármilyen módon módosíthatnak, a pénztár vagy az online csatorna lehet, hogy nem rendelkezik minden adattal, ami a cikkek pontos valós idejű készlet megjelenítéséhez szükséges.

Ez a témakör azokat az adatszinkronizálási folyamatokat mutatja be, amelyek rendszeres futtatásával korlátozható az adatok késleltetése az alkalmazások vagy csatornák között. Fontos azonban, hogy megértse, hogy az üzemeltetési nap során megadott összes rendelkezésre álló adatot becsült értéknek tekinti a rendszer. Ezért ha megpróbálja összehasonlítani azokat az aktuális készlet-adatokat, amelyeket az alkalmazás tényleges fizikai készletként ad meg a polcokon, vagy ha megpróbálja összehasonlítani a pénztárban rendszernél megjelenített aktuális értékeket azon aktuális adatokkal, amelyek ugyanarra a raktárra vonatkoznak a Kereskedelmi központban, az értékek eltérhetnek. Az üzemeltetési nap során ez a különbség várható, és nem tekinthető problémának. Ha ellenőrizni szeretné az adatokat, és biztosítani szeretné, hogy a készletelérhetőségi API-kban és a Kereskedelmi központban megadott értékek megegyeznek az áruház vagy raktár polcain található tényleges fizikai egységekkel, akkor ezt akkor végezheti el leghatékonyabban, amikor az adott napon befejeződtek a csatornaműveletek, és az összes tranzakció megfelelően szinkronizálódott a Kereskedelmi központ és a csatorna között.

## <a name="use-inventory-lookup-apis-for-e-commerce-inventory-availability-requests"></a>Készletkeresési API-k használata e-kereskedelmi készletelérhetőséggel kapcsolatos kérésekhez

A következő API-k használhatók a termék készletelérhetőségének megjelenítésére, amikor a vevők egy e-kereskedelmi webhelyen vásárolnak.

- **GetEstimatedAvailability** – Használja ezt az API-t, hogy lekérhesse a készlet rendelkezésre állását egy cikkre az eCommerce csatorna raktárában vagy raktáraiban, amik össze vannak kapcsolva az e-Commerce csatorna teljesítése szintjével. Ez az API egy adott keresési területen vagy sugárban található raktárakban is használható, a hosszúsági és a szélességi adatok alapján.
- **GetEstimatedProductWarehouseAvailability** – ezt az API-t használva egy adott raktárból származó cikk készletét kérheti le. Például használhatja a készletelérhetőség megjelenítésére olyan esetekben, amelyben rendelésfelvétel szerepel.

> [!NOTE]
> Ezek az API-k helyettesítik a **GetProductAvailabilities** és **GetAvailableInventoryNearby** API-kat a Dynamics 365 Retail 10.0.7-es és korábbi verzióiban.

Mindkét API az adatokat a Commerce kiszolgálóról kéri le, és becslést nyújt egy termék vagy termékváltozat és egy raktár egyedi kombinációjára vonatkozó tényleges készletről. Bár más, a Commerce-kiszolgálón elérhető API-k közvetlenül a Kereskedelmi központból is lekérhetik a termékek tényleges készletmennyiségeit, nem javasoljuk ezek e-kereskedelmi környezetben való használatát a lehetséges teljesítményproblémák miatt, és a gyakori kérések Kereskedelmi központ-kiszolgálókra tett kapcsolt hatása miatt. Ezenkívül ha a tényleges készletet a Commerce kiszolgálón keresztül számítják, akkor a számítások nagyobb valószínűséggel tartalmaznak olyan készletet, amelyeket közelmúltbéli e-kereskedelmi tranzakciókban értékesítettek, és még nem szinkronizálódtak a Kereskedelmi központtal. Bár előfordulhat, hogy a Kereskedelmi központ nem rendelkezik a tranzakciókkal kapcsolatos adatokkal, a Commerce kiszolgáló és a csatorna adatbázisa igen. Emiatt az adatokat figyelembe veszik, és segítséget nyújthatnak a termék rendelkezésre álló készletének pontosabb becsléséhez.

### <a name="get-started-with-e-commerce-calculated-inventory-availability"></a>Az e-kereskedelmi számított készlet elérhetőségének megismerése

Mielőtt használja a korábban említett két API-t, engedélyeznie kell az **Optimalizált termékelérhetőségi számítás** funkciót a **Funkciókezelés** munkaterület segítségével, a Commerce Headquartersben.

Mielőtt az API-k kiszámolhatnák egy cikk készletelérhetőségének legjobb becslését, először fel kell dolgozni a Kereskedelmi központ készletelérhetőségre vonatkozó időszakos pillanatképét, és elküldeni az e-kereskedelem Commerce Scale Unit modulja által használt csatorna-adatbázishoz. A pillanatkép a Kereskedelmi központ azon adatait jeleníti meg, amelyek a termék vagy a termék változatának és a raktárnak egy meghatározott kombinációját jelentik. Itt szerepelhetnek készletmódosítások vagy -mozgatások, amelyeket készletbevételezések, szállítmányok vagy más olyan folyamatok okoztak, amelyeket a Kereskedelmi központban hajtottak végre, és az e-kereskedelmi csatorna csak a szinkronizálási folyamat révén tud róla.

A **Termékelérhetőség** feladat által létrehozott adatbázis-pillanatkép csak az olyan készlettranzakciókat számítja ki, amelyeket a pillanatkép készítésekor a Kereskedelmi központban feldolgoztak és feladtak. Ha a készletet egy üzletraktár egyik termékeként adták el készpénzzel fizetett, azonnal átvett vagy aszinkron ügyfélmegrendelési értékesítés során a pénztáralkalmazásban, a Kereskedelmi központ nem rendelkezik majd azonnal az értékesítés kapcsolódó készletprobléma-tranzakciójáról. Az ilyen típusú üzleti értékesítések során eladott készletekkel kapcsolatban csak azután kap információt, miután a P-feladat feltöltötte a kapcsolódó tranzakciót az üzlet csatorna-adatbázisából a Kereskedelmi központba, és a kapcsolódó értékesítési rendelés létrejön kimutatásfeladás vagy folyamatos apránkénti közzétételi folyamatok során. A rendelésnek a Kereskedelmi központban történő létrehozási folyamata létrehozza a kapcsolódó készlettranzakciókat. Az e-kereskedelmi csatorna megrendelései esetén a Kereskedelmi központ csak azután rendelkezik információkkal a készlettranzakciókról, miután a tranzakciókat elküldték a Kereskedelmi központba a P-feladaton keresztül, és a rendelések szinkronizálási folyamata befejeződött. Ezért fontos, hogy megértse, hogy a **Termékelérhetőség** feladatban megadott készlet-pillanatkép értéke nem biztos, hogy 100%-ban pontos valós időben a felosztott kiszolgálókon történő folyamatos értékesítésfeldolgozás miatt.

Ha a Kereskedelmi központ alkalmazásban szeretné pillanatképet készíteni a készletről, hajtsa végre az alábbi lépéseket.

1. Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem IT \> Termékek és készlet \> Termékelérhetőség** lehetőségre.
1. Válassza az **OK** gombot a **Termékelérhetőség** feladat futtatásához. Ez a feladat ütemezhető úgy is, hogy egy kötegben fusson.

A **Termékelérhetőség** feladat futásának befejeződése után a rögzített adatokat közzé kell tenni az e-kereskedelmi csatorna-adatbázisokba, hogy a legújabb Kereskedelmi központ-készletpillanatképet figyelembe vehessék a becsült tényleges készlet számításakor.

1. Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.
1. Futtassa az **1130** (**Termékelérhetőség**) feladatot a pillanatkép-adatok szinkronizálásához, amelyeket a **Termékelérhetőség** feladat hozott létre a Kereskedelmi központból a csatorna-adatbázisaiba.

Amikor a készlet rendelkezésre állása a **GetEstimatedAvailabilty** vagy a **ProductWarehouseInventoryAvailabilities** API-kból lekérhető, egy számítás kerül futtatásra, hogy megpróbálja a legpontosabban megbecsülni a termékből rendelkezésre álló készletet. A számítás bármely olyan e-kereskedelmi vevői rendelésre hivatkozik, amelyek a csatorna-adatbázisban találhatók, de nem szerepelnek az 1130 feladat által biztosított pillanatképadatok között. Ezt a logikát követi a rendszer a legutóbbi feldolgozott készlettranzakció Kereskedelmi központból való nyomon követésével, és a csatorna-adatbázis tranzakciójával való összehasonlításával. Alapértéket ad a csatornaoldali számítási logikához, így a további készletmozgásokat, amelyek az e-kereskedelmi csatorna-adatábis vevői rendelkéseivel kapcsolatos értékesítési tranzakcióknál történtek, a rendszer figyelembe veszi az API által biztosított becsült készletértékben.

A csatornaoldali számítási logika becsült ténylegesen elérhető értéket ad vissza, valamint egy teljesen elérhető értéket a kért termékre és raktárra vonatkozóan. Az értékek kívánság szerint megjelenhetnek az e-kereskedelmi webhelyen, vagy felhasználhatók az e-kereskedelmi webhely egyéb üzleti logikájának kiváltására. Megjelenítheti például a "elfogyott" üzenetet, nem pedig a tényleges aktuális készletet, amelyet az API átadott.

A csatornaoldali e-kereskedelmi API-k által a becsült készletértékhez használt számítási logika a készlet értékelésére csak az olyan vevői rendelések alapján képes, amelyeket létrehoztak a csatorna-adatbázisban, de még nem szinkronizálták és adták fel a Kereskedelmi központba. Ha a csatorna-adatbázis készpénzzel fizetett és azonnal átvett értékesítésre vonatkozóan is tartalmaz tranzakciós adatokat az üzletspecifikus raktárnál, a készpénzzel fizetett és azonnal átvett értékesítéseket a rendszer nem számítja bele a csatornaoldali e-kereskedelmi számításnál ezeknél a raktáraknál.

## <a name="configure-the-inventory-lookup-operation-in-the-pos-channel"></a>Készletkeresési művelet konfigurálása a pénztárcsatornában

A Retail 10.0.9-es és korábbi verzióiban a pénztár **Készletkeresés** művelete valós idejű Kereskedelmi központba irányuló szolgáltatáshívást használt a kiválasztott termék készletinformációinak lekéréséhez, mind a felhasználó aktuális üzletéhez, mint bármely más, a teljesítési csoporthoz az üzlet csatornakonfigurációjának részeként konfigurált üzletekhez. A Commerce 10.0.10 és újabb verzióiban kikapcsolhatja a Kereskedelmi központba irányuló valós idejű szolgáltatáshívásokat. Ehelyett használhatja a Commerce kiszolgálón a csatornaoldali számítást a tényleges készlet megállapításához, amely ténylegesen elérhető az üzlet és más helyek számára, amelyeket meghatároztak a teljesítési csoportban. Ez a csatorna által számított készletkonfiguráció olyan helyeknél is hasznos, ahol az internetkapcsolat nem megbízható, mert nem kell online lennie a készletkeresések fogadásához a Kereskedelmi központból.

Amikor a csatornaoldali számítást helyesen konfigurálták és kezelték, megbízhatóbb becslést biztosíthat az aktuális üzletkészletről, mivel a Kereskedelmi csatorna-adatbázisban található tranzakciós adatokat használ, amelyről a Kereskedelmi központ még lehet, hogy nem tud. Ha például a pénztár készletkereséseire vonatkozó meglévő valós idejű szolgáltatáshívást használja, a Kereskedelmi központ valószínűleg még nem rendelkezik az információval a termékkel éppen történt készpénzzel fizetett és azonnal átvett értékesítésről. Így a Kereskedelmi központ által az adott termékre vonatkozóan visszadatott tényleges készlet értéke valószínűleg meghaladja az üzlet aktuális tényleges készletét egy egységgel. Ha viszont a csatornaoldali számítást használja, akkor a készpénzzel fizetett és azonnal átvett értékesítést a rendszer beleszámítja a számításba, és levonja a megjelenő tényleges értékből. Annak ellenére, hogy a csatornaoldali számítás és a valós idejű szolgáltatáshívások által biztosított értékek is csak a tényleges készlet becslését jelentik, a csatornaoldali számítás által adott érték nagyobb valószínűséggel pontos az aktuális üzletre nézve.

### <a name="get-started-with-pos-channel-side-calculated-inventory-availability"></a>A pénztár csatornaoldali számított készlet elérhetőségének megismerése

Hogy használhassa a  csatornaoldali számítási logikát és kikapcsolhassa valós idejű szolgáltatáshívásokat készletkeresésekhez a POS alkalmazásból, először engedélyeznie kell az **Optimalizált termékelérhetőségi számítás** funkciót a **Funkciókezelés** munkaterületen a Commerce Headquartersben. A funkció engedélyezésén kívül módosítania kell a **funkció profilját**.

A **Funkcióprofil** módosításához az alábbi lépéseket hajtsa végre:

1. Ugorjon a következő elemre: **Retail és Commerce \>  Csatorna beállítása \> Pénztárbeállítás \>  Pénztárprofilok \> Funkcióprofilok**.
1. Válasszon funkcióprofilt.
1. A **Funkciók** gyorslap **Készletelérhetőségi számítás** szakaszában módpsítsa a **Készletelérhetőségi számítás módja** mező értékét **Valós idejű szolgáltatásról** **Csatornára**. Alapértelmezés szerint az összes funkcióprofil valós idejű szolgáltatási hívásokat használ. Ennek megfelelően módosítania kell ennek a mezőnek az értékét, ha csatornaoldali számítási logikát szeretne használni. A módosítás hatással van minden olyan kiskereskedelmi üzletre, amely a kiválasztott funkcióprofilhoz van társítva.

Ezután a következő lépések végrehajtásával szinkronizálni kell a csatornán végzett módosításokat az elosztási ütemezési folyamaton keresztül:

1. Ugorjon a **Kiskereskedelem és kereskedelem \> Kiskereskedelem és kereskedelem informatika \> Elosztási ütemezés** pontra.
1. Futtassa a **1070** (**csatornakonfiguráció**) feladatot.

A konfiguráció befejezését követően a fizikailag elérhető készletről kapott adatok már nem használnak valós idejű szolgáltatási hívást, amikor a pénztár alkalmazásban a felhasználó a **Készletkeresés** műveletet használja (normál és mátrix nézet). Helyette az aktuális üzlet, valamint a teljesítési csoportba tartozó összes üzlet ténylegesen rendelkezésre álló készletét a Kereskedelmi központ programból a csatorna-adatbázishoz szállított legutóbbi pillanatkép alapján számítja ki a program. A csatornaoldali számítás tovább finomítja a pillanatfelvétel értékét, hogy a ténylegesen rendelkezésre álló értéket módosítsa a csatorna-adatbázis azon kiválasztott termékéhez tartozó további értékesítési vagy visszáru-tranzakciók alapján, amelyek nem szerepelnek az 1130-as feladat legutóbbi szinkronizált pillanatképén. Ha a csatorna-adatbázis nem tartalmaz tranzakciós adatokat a teljesítési csoportban szereplő bármely raktárakhoz vagy üzletekhez, akkor nem tartalmaz olyan további tranzakciókat, amelyek az érték újraszámításához használhatók fel. Ezért az adott raktáraknál vagy üzleteknél a tényleges készletre vonatkozóan megjelenített legjobb besclés a legutóbb ismert Kereskedelmi központ-pillanatképről származó adat.

A pénztár **Rendelésteljesítés** képernyői szintén a csatornaoldali számítással mutatják a cikkek tényleges készletét, amikor egy rendelésteljesítési sor ki van jelölve, és a felhasználó megtekinti a **Részletek** panelt a kiválasztott cikk tényleges készletéhez.

## <a name="optimize-your-inventory-data"></a>A készlet adatainak optimalizálása

A készlet lehető legjobb becslésének biztosításához fontos, hogy a következő Commerce kötegelt feladatokat használja, és gyakran futtassa azokat:

- **P-feladat** – a P-feladat a **felosztási ütemezések** oldalon található, és gyakran kell futtatni. Ez a feladat az e-kereskedelmi rendeléseket, a pénztár által létrehozott aszinkron vevői rendeléseket, és a csatorna-adatbázisokból létrehozott készpénzzel fizetett és azonnal átvett rendeléseket átviszi a a Kereskedelmi központ rendszerbe, amelyek itt tovább feldolgozhatók. Amíg ez az adat szinkronizálva van a csatornáról a a Kereskedelmi központ rendszerbe, a Kereskedelmi központ nem tartalmaz adatokat a raktárak azon termékeihez, amelyek az adott tranzakciókból erednek.
- **Rendelések szinkronizálása** – ez a feladat a Kereskedelmi központ nyers tranzakciós adatait dolgozza fel, amelyekkel a P-feladat a Kereskedelmi központ értékesítési rendeléseibe az e-kereskedelmi és az aszinkron vevői rendelési tranzakciókat biztosítja és átalakítja. A feladat feldolgozása és az értékesítési rendelések létrehozása előtt nem jönnek létre készlettranzakciók. Ennélfogva a Kereskedelmi központ aktuális készlete nem veszi figyelembe a tranzakciókat.
- **Tranzakciós kimutatások számítása kötegben** – az üzletben létrejövő készpénzzel fizetett és azonnal átvett tranzakciók esetében a folyamatos, apránkénti feladás folyamata biztosítja, hogy a rendszer az értékesítéshez kapcsolódó készletet hatékonyan frissítse. A készpénzzel fizetett, azonnal átvett rendelésekhez tartozó készlettranzakciók leghatékonyabb feldolgozásához győződjön meg arról, hogy a rendszer a [folyamatos apránkénti feladás](https://docs.microsoft.com/dynamics365/commerce/trickle-feed) használatára van beállítva.
- **Tranzakciós kimutatások feladása kötegben** – ez a feladat is szükséges a folyamatos, apránkénti feladáshoz. Ez a **Tranzakciós kimutatások kötegelt kiszámítása** feladatot követi. Ez a feladat rendszeresen feladja a kiszámított kimutatásokat, hogy a Kereskedelmi központban jöjjenek létre a készpénzzel fizetett, azonnal átvett értékesítéshez tartozó értékesítési rendelések, és a Kereskedelmi központ így pontosabban mutassa az üzlet készletét.
- **Termék elérhetősége** – ez a feladat létrehozza a Kereskedelmi központ-készletből származó készlet pillanatfelvételét.
- **1130 (termék elérhetősége)** – Ez a feladat az **elosztási ütemezések** oldalon található, és a **termék elérhetősége** feladatát követően azonnal futtatható. Ez a feladat szállítja a készlet-pillanatfelvétel adatait a Kereskedelmi központ rendszerből a csatorna-adatbázisba.

Javasolt, hogy ne futtassa túl gyakran ezeket a kötegelt feladatokat (néhány percenként). A gyakori futtatás túlterheli a Commerce Headquarters (HQ)-t, és jelentős mértékben hatással van a teljesítményre. Általánosan jó gyakorlat a termék elérhetőségének futtatása és 1130 munka végeztetése órabéren, és a P-feladat rendelések szinkronizálásának ütemezése, és a folyamatos, apránkénti feladású munkák azonos, vagy ennél is nagyobb gyakoriságú végeztetése.

> [!NOTE]
> Teljesítménnyel kapcsolatos okokból, amikor a csatornaoldali készletelérhetőségi számításokkal hoznak létre egy készletelérhetőségi kérést az e-kereskedelmi API-k vagy az új pénztári cstornaoldali készletlogika használatával, a számítás gyorsítótárat használt annak meghatározására, hogy elég idő telt-e el, hogy igazolható legyen a számítási logika újbóli futtatása. Az alapértelmezett gyorsítótár értéke 60 másodperc. Például bekapcsolta az üzlet csatorna-oldali számítását, és megtekintette egy termék tényleges készletét a **készletkeresés** oldalán. Ha a termék egy egységét értékesítik, akkor a **készletkeresés** lapja nem jeleníti meg a csökkentett készletet mindaddig, amíg a gyorsítótár ki nem ürül. Miután a felhasználó feladta a tranzakciókat a pénztárban, várnia kell 60 másodpercig, mielőtt ellenőrizheti, hogy a tényleges készlet csökkent.

Ha az üzleti helyzethez kisebb gyorsítótárazási idő szükséges, forduljon a terméktámogatási szolgálat képviselőjéhez.


[!INCLUDE[footer-include](../includes/footer-banner.md)]