---
title: Raktárkezelési számítási feladatok felhőalapú és peremhálózati skálázási egységekhez
description: Ez a témakör arról a szolgáltatásról nyújt tájékoztatást, amely lehetővé teszi a skálázási egységek számára a kiválasztott folyamatok futtatását a raktárkezelési számítási feladatából.
author: perlynne
ms.date: 09/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, SysSecRolesEditUsers, SysWorkloadDuplicateRecord
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: c3f703e39e5e9d475dcb4f96dfb400a961ae2dcf
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500427"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Raktérkezelés munkaterhelései felhőalapú és peremhálózat-lépték szerinti egységekhez

[!include [banner](../includes/banner.md)]

> [!WARNING]
> Nem minden raktárkezelési üzleti funkció támogatott teljesen az olyan raktárak esetében, amelyek munkaterhelést futtatnak egy skálázási egységen. Ügyeljen arra, hogy csak azokat a folyamatokat használja, amelyeket ez a témakör kifejezetten támogatottként ír le.

## <a name="warehouse-execution-on-scale-units"></a>Raktári végrehajtás skálázási egységeken

A Warehouse management munkaterhelések lehetővé teszik a felhő- és peremhálózati skálázási egységek számára, hogy a kiválasztott folyamatokat a raktárkezelési kapacitásokból futtassák.

## <a name="prerequisites"></a>Előfeltételek

Rendelkeznie kell egy Dynamics 365 Supply Chain Management-központtal és skálázási egységgel, amely telepítve van a raktárfelügyeleti számítási feladatokkal. Az architektúrával és a telepítési folyamattal kapcsolatos további tudnivalókat lásd: [Skálázási egységek elosztott hibridtopológiában](cloud-edge-landing-page.md).

## <a name="how-the-warehouse-execution-workload-works-on-scale-units"></a>A raktárvégrehajtási feladat működése a skálázási egységeken

A folyamatok a raktárkezelési számítási feladat folyamatai esetében az adatok a központ és a skálázási egység között szinkronizálva vannak.

A skálázási egység csak a tulajdonában lévő adatokat tarthatja karban. A méretezési egységek adattulajdonosi koncepciója segít megelőzni a több főkiszolgálós megoldások ütközéseit. Ezért fontos, hogy tisztában legyen azzal, hogy mely folyamatadatok vannak a központ tulajdonában, és melyek vannak a skálázási egységek tulajdonában.

Az üzleti folyamatoktól függően ugyanaz az adatrekord megváltoztathatja a tulajdonost a központ és a skálázási egységek között. Erre az esetre a következő szakaszban talál példát.

> [!IMPORTANT]
> Néhány adat a központon és a skálázási egységen is létrehozható. Ilyenek például az **Azonosítótáblák** és a **Kötegszámok**. Olyan helyzetekben, amikor ugyanaz az egyedi rekord jön létre a központon és egy skálázási egységen ugyanazon a szinkronizálási cikluson keresztül, dedikált ütközéskezelés áll rendelkezésre. Ilyen esetben a következő szinkronizálás sikertelen lesz, és a **Rendszerfelügyelet > Lekérdezések > Terhelési lekérdezések > Ismétlődő rekordok** menüponthoz kell ugrania, ahol megtekintheti és egyesítheti az adatokat.

## <a name="outbound-process-flow"></a>Kimenő feldolgozási folyamat

A kimenő adatok tulajdonosi folyamata attól függ, hogy használja-e a rakománytervezési folyamatot. A *forrásdokumentumok*, például az értékesítési és átviteli rendelések, valamint a rendelésfelosztási folyamat és a kapcsolódó rendelési tranzakciók adatai minden esetben a központ tulajdonában állnak. A rakománytervezési folyamat használata esetén azonban a rakományok a központon lesznek létrehozva, és ezért kezdetben a központ tulajdonában állnak. A *Raktárba történő kiadás* folyamat részeként a rakományadatok tulajdonosa átkerül a dedikált skálázási egység üzemelő példányába, amely a következő *szállítmányhullám-feldolgozás* tulajdonosa lesz (például a munkafelosztásé, feltöltési munkáé és igénylétrehozásé). Ezért a raktári dolgozók csak egy olyan Warehouse Management mobilalkalmazás segítségével dolgozhatnak fel kimenő értékesítési és átviteli rendelési munkát, amely az adott skálázási egység terhelését futtató üzemelő példányhoz kapcsolódik.

Amint a végső munkafolyamat a végső kiszállítási helyre (raktárajtó) helyezi a készletet, a skálázási egység jelzi a központnak, hogy frissítse a forrásdokumentum készlettranzakcióit *Kitárolva* értékre. Amíg ez a folyamat le nem fut, és nem szinkronizálja őket, addig a skálázási egység terhelésének aktuális készlete fizikailag le lesz foglalva a raktár szintjén, és a kimenő szállítás visszaigazolását azonnal fel lehet feldolgozni anélkül, hogy megvárja a szinkronizálás befejeződését. A későbbi értékesítési szállítólevelet és a rakomány számlázását vagy az átmozgatási megbízás feladását a központ kezeli.

A következő ábra a kimenő folyamatot mutatja be, és jelzi, hogy hol zajlanak az egyes üzleti folyamatok. (Válassza ki a diagramot a nagyításhoz.)

[![Kimenő feldolgozási folyamat.](media/wes_outbound_warehouse_processes-small.png "Kimenő feldolgozási folyamat")](media/wes_outbound_warehouse_processes.png)

### <a name="outbound-processing-with-load-planning"></a>Kimenő rakományok feldolgozása rakománytervezéssel

A rakománytervezési folyamat használata esetén a rakományok és szállítmányok létrejönnek a központnál, és az adatok tulajdonjoga átkerül a skálázási egységbe a *Raktárba való kiadás* folyamat részeként, amint azt az alábbi ábra mutatja.

![Kimenő rakományok feldolgozása rakománytervezéssel.](./media/wes_outbound_processing_with_load_planning.png "Kimenő rakományok feldolgozása rakománytervezéssel")

### <a name="outbound-processing-without-load-planning"></a>Kimenő rakományok feldolgozása rakománytervezés nélkül

Ha nem használja a rakománytervezési folyamatot, akkor a szállítmányok a skálázási egységeknél jönnek létre. A skálázási egységeknél rakományok is létrejönnek a hullámfolyamat részeként.

![Kimenő rakományok feldolgozása rakománytervezés nélkül.](./media/wes_outbound_processing_without_load_planning.png "Kimenő rakományok feldolgozása rakománytervezés nélkül")

## <a name="inbound-process-flow"></a>Bemenő feldolgozási folyamat

A központ a következő adatokat birtokolja:

- Minden forrásdokumentum, például beszerzési és termelési rendelések
- Bejövő terhelésfeldolgozás
- Minden költség- és pénzügyi frissítés

> [!NOTE]
> A bejövő beszerzési rendelési folyamat koncepciójában különbözik a kimenő folyamattól. Ugyanazt a raktárat a mérlegegységen vagy a központon lehet működtetni attól függően, hogy a beszerzési rendelés ki van-e adva raktárba, vagy sem. Miután kiadott egy rendelést a raktárba, akkor csak akkor dolgozhat azzal a rendeléssel, ha bejelentkezett a skálázási egységbe.
>
> Ha a *Kiadás raktárba* folyamatot használja, akkor létrejönnek a [*raktári rendelések*](cloud-edge-warehouse-order.md), és a kapcsolódó bevételezési folyamat tulajdonjoga a skálázási egységhez van rendelve. A központ nem fogja tudni regisztrálni a bejövő bevételezéseket.

Be kell jelentkeznie a központba a *Kiadás raktárba* folyamat használatához. A beszerzési rendelés feldolgozásához lépjen a következő oldalak egyikére a futtatáshoz vagy ütemezéshez:

- **Beszerzés és forrás > Beszerzési rendelések > Összes beszerzési rendelés > Raktár > Műveletek > Kiadás raktárba**
- **Raktárkezelés > Kiadás a raktárba > Értékesítési rendelések automatikus kiadása**

A **Beszerzési rendelések automatikus kiadása** funkció használatakor lekérdezés alapján meghatározott beszerzésirendelés-sorokat választhat ki. Jellemző helyzet lehet egy ismétlődő kötegelt feladat, amely kiadja a következő napon várható összes visszaigazolt beszerzésirendelés-sort.

A dolgozó a skálázási egységhez kapcsolódó Raktárkezelés mobilalkalmazás segítségével futtathatja a bevételezési folyamatot. A skálázási egység ezt követően rögzíti az adatokat, és a bejövő raktári rendeléssel szemben jelenti őket. A következő betárolás létrehozását és feldolgozását a skálázási egység is kezeli.

Ha nem használja a *kiadás raktárba* folyamatot, és így nem használja a *raktári rendeléseket*, akkor a központ a raktári bevételezést és a munka feldolgozását a skálázási egységtől függetlenül feldolgozhatja.

![Bemenő feldolgozási folyamat.](./media/wes-inbound-ga.png "Bemenő feldolgozási folyamat")

Ha egy dolgozó a Warehouse Management mobilalkalmazás bevételezési folyamat segítségével, a skálázási egységre vonatkozóan bejövő regisztrációt ad meg, akkor a rendszer a kapcsolódó raktári rendeléssel szemben rögzíti a nyugtát, amely a skálázási egységben van tárolva. A skálázási egység terhelése ezt követően jelzést küld a központnak, hogy frissítse a kapcsolódó beszerzésirendelés-sortranzakciókat *Regisztrálva* állapotúra. Amint ez befejeződött, a központon futtathatja a beszerzési rendelés termékbevételezését.

A következő ábra a bejövő folyamatot mutatja be, és jelzi, hogy hol zajlanak az egyes üzleti folyamatok. (Válassza ki a diagramot a nagyításhoz.)

[![Bejövő feldolgozási folyamat](media/wes_inbound_warehouse_processes-small.png "Bejövő feldolgozási folyamat")](media/wes_inbound_warehouse_processes.png)

## <a name="supported-processes-and-roles"></a>Támogatott folyamatok és szerepkörök

A program nem minden raktárkezelési folyamatot támogat egy raktárvégrehajtási számítási feladatban egy skálázási egységen. Ezért ajánlott olyan szerepköröket hozzárendelni, amelyek megfelelnek az egyes felhasználók számára elérhető funkcióknak.

Ennek a folyamatnak a megkönnyítésére a program a *Raktárkezelő számítási feladaton* nevű mintaszerepkör megtalálható a **Rendszerfelügyelet \> Biztonság \> Biztonsági beállítások** alatti bemutató adatok között. Ennek a szerepkörnek a célja, hogy a raktárkezelők hozzáférjenek a raktárvégrehajtási számítási feladathoz a skálázási egységen. A szerepkör olyan oldalakhoz való hozzáférést biztosít, amelyek a skálázási egységen szereplő számítási feladatok összefüggésében fontosak.

A skálázási egység felhasználói szerepköreit a program a központ által a skálázási egység történő kezdeti adatszinkronizálás részeként rendeli hozzá.

A felhasználóhoz rendelt szerepkörök módosításához nyissa meg a **Rendszerfelügyelet \> Biztonság \> Felhasználók hozzárendelése szerepekhez** részt. Azokhoz a felhasználókhoz, akik csak a skálázási egységeken tevékenykednek raktárikezelőként csak a *Raktárkezelő számítási feladaton* nevű szerepet kell hozzárendelni. Ez a megközelítés biztosítja, hogy ezek a felhasználók csak a támogatott funkciókhoz férjenek hozzá. Távolítsa el a felhasználókhoz rendelt összes egyéb szerepkört.

Azokhoz a felhasználókhoz, akik mind a központban, mind a skálázási egységeken tevékenykednek raktárikezelőként, a meglévő *Raktárkezelő munkás* nevű szerepet kell hozzárendelni. Ne feledje, hogy ez a szerepkör biztosítja a raktári dolgozók számára a felhasználói felületen (UI) megjelenő funkciókat (például az átmozgatási rendelés bevételezési feldolgozását), amelyek jelenleg nem támogatottak a skálázási egységen.

### <a name="supported-warehouse-execution-processes"></a>Támogatott raktárvégrehajtási folyamatok

A következő raktárvégrehajtási folyamatok engedélyezettek egy raktárvégrehajtási számítási feladat esetében egy skálázási egységen:

- Kiválasztott hullámmetódusok értékesítési és átátviteli rendelésekhez (ellenőrzés, rakománylétrehozás, felosztás, igényfeltöltés, tárolóra készítés, munka létrehozása és hullámcímke-nyomtatás)

- Az értékesítési és átviteli rendelések raktári munkához történő feldolgozása a raktári alkalmazással (a feltöltési munkát is beleértve)
- Aktuális készlet lekérdezése a raktári alkalmazás használatával
- A készlet mozgásának létrehozása és futtatása a raktári alkalmazás használatával
- Ciklikus leltározási munka létrehozása és feldolgozása a raktári alkalmazás segítségével
- Készletkorrekció végrehajtása a raktári alkalmazás használatával
- Beszerzési rendelések regisztrálása és betárolási munka a raktári alkalmazás használatával

A skálázási egységen a következő munkatípusok dolgozhatók fel, ezért a raktárkezelési számítási feladat részeként fel lehet dolgozni:

- **Készletmozgatások** – Manuális mozgatás és mozgatás sablon szerint.
- **Ciklikus leltározás** – Beleértve az egyeztetés-jóváhagyási/-elutasítási folyamatot a leltározási műveletek részeként.
- **Beszerzési rendelések** – Rakodómunka raktári rendelésen keresztül, ha a beszerzési rendelések nincsenek rakományhoz társítva.
- **Értékesítési rendelések** – Egyszerű kitárolási és rakodási munka.
- **Átmozgatási probléma** – Egyszerű kitárolás és rakodás.
- **Feltöltés** – A termelés nyersanyagait nem tartalmazza.
- **Késztermékek betárolása** – A készként jelentés utáni termelési folyamat.
- **Társtermék és melléktermék betárolása** – A készként jelentés utáni termelési folyamat.

A program jelenleg nem támogatja a forrásoldali dokumentumok egyéb típusainak feldolgozását vagy a raktári munkát a skálázási egységekben. Például egy skálázási egységre vonatkozó raktárvégrehajtási számítási feladat esetén nem lehet áthozott rendelés bevételezését (átviteli bevételezést) végrehajtani, ehelyett ezt a központi példánynak kell feldolgoznia.

> [!NOTE]
> A nem támogatott funkciókhoz használható mobileszköz-menüpontok és gombok nem jelennek meg a _Raktárkezelés mobilalkalmazásban_, ha skálázásiegység-telepítéshez kapcsolódik.
> 
> Amikor egy skálázási egységen számítási feladatot alkalmaz, akkor nem futtathat nem támogatott folyamatokat az adott raktár esetében a központban. A témakörben később található táblázatok a támogatott funkciókat dokumentálják.
>
> Kiválasztott raktári munkatípusokat a központon és a skálázási egységeken is létre lehet hozni, de csak a saját központ vagy skálázási egység (az adatokat létrehozó telepítés) tarthatja fenn.
>
> Még ha támogatott is egy adott folyamat a skálázási egység által, ne feledje, hogy az összes szükséges adat nem feltétlenül szinkronizálható a központból a skálázási egységbe, vagy a skálázási egységből a központba, ami a váratlan rendszerfeldolgozást eredményező kockázathoz vezet. Ilyen helyzet lehet például a következő:
> 
> - Ha olyan helylekérdező lekérdezést használ, amely olyan adattáblarekordhoz csatlakozik, amely csak a központ telepítésében létezik.
> - A helyállapot és/vagy a hely rakodási kapacitás funkciók használata esetén. Ezek az adatok nem lesznek szinkronizálva a telepítések között, ezért csak akkor működnek, ha az egyik telepítés aktuális hely készletét frissítik.

A következő raktárkezelési funkciók jelenleg nem támogatottak a skálázásiegység-munkaterhelésekben:

- Rakományhoz rendelt beszerzésirendelés-sorok bejövő feldolgozása.
- Beszerzési rendelések bejövő feldolgozása egy projekthez.
- A kirakodási költség kezelése, hajóút használatával és a szállítás alatt lévő áruk nyomon követése.
- A **Tulajdonos** és/vagy **Sorozatszám** aktív követési dimenziókat tartalmazó cikkek bejövő és kimenő feldolgozása.
- Zároló állapotértékű készlet feldolgozása.
- Készletállapot módosítása bármely munkamozgási folyamat során.
- Rendelésben véglegesített rugalmas raktárszintű dimenziófoglalások.
- A *Raktári helyállapot* funkció használata (az adatok nincsenek szinkronizálva az üzemelő példányok között).
- *Helyazonosító tábla pozicionálása* funkció használata.
- *Termékszűrők* és *Termékszűrő-csoportok* használata, beleértve a **Napok száma a kötegek kombinációjára** beállítást.
- Integráció a minőségirányítással.
- Feldolgozás tényleges súllyal rendelkező cikkekkel.
- Feldolgozás csak szállításkezelésre engedélyezett cikkekkel (TMS).
- Feldolgozás negatív aktuális készlettel.
- Raktári munka feldolgozása szállítmánylevelekkel.
- Raktári munka feldolgozása anyagkezelési/raktárautomatizálással.
- Az alaptermék adatképének használata (például a Warehouse Management mobilalkalmazásban).

> [!WARNING]
> Bizonyos raktári funkciók nem érhetők el az olyan raktáraknál, ahol a raktárkezelési terhelések egy skálázási egységen futnak, és a központ és a skálázási egység munkaterhelés esetén sem támogatott.
> 
> Más funkciók mindkét esetben feldolgozhatók, de bizonyos helyzetekben körültekintő használatot igényelnek, például amikor az aszinkron adatfrissítési folyamat miatt ugyanannak a raktárnak az aktuális készlete frissül ugyanahhoz a raktárhoz és skálázási egységhez.
> 
> A központon és a skálázási egységen egyaránt támogatott funkciók (például a *blokkolt munka*) csak az adatok tulajdonosa számára támogatottak.

### <a name="outbound-supported-only-for-sales-and-transfer-orders"></a>Kimenő (csak értékesítési és átmozgatási rendeléseknél támogatott)

A következő táblázat bemutatja, hogy mely kimenő funkciók, és hol támogatottak, amikor a raktárkezelési számítási feladatok a felhőalapú és a peremhálózati skálázási egységekben használatosak.

| Feldolgozás                                                      | Központ | Raktári végrehajtási számítási feladat skálázási egységeken |
|--------------------------------------------------------------|-----|------------------------------|
| Forrásdokumentum feldolgozása                                   | Igen | Nincs |
| Rakomány és szállításkezelési folyamatok feldolgozása                | Igen, de csak a rakománytervezési folyamatok. A szállításkezelési folyamatok feldolgozása nem támogatott  | Nincs |
| Partraszállási költség és úton lévő áruk fogadása                                         | Igen | Nincs |
| Kiadás raktárba                                         | Igen | Nincs |
| Tervezett áttárolás                                        | Nincs  | Nincs |
| Szállítmánykonszolidáció                                       | Igen, a rakománytervezés használata esetén | Igen |
| Szállítmány hullámfeldolgozása                                     | Nincs  |Igen, a **Rakományok összeállítása és rendezése** kivételével |
| Hullámhoz szállítások karbantartása                                  | Nincs  | Igen|
| Raktári munka feldolgozása (az azonosítótábla nyomtatásával együtt)        | Nincs  | Igen, de csak a korábban említett támogatott funkciókhoz |
| Fürt kitárolása                                              | Nincs  | Igen|
| Manuális csomagolásfeldolgozás, beleértve a „Becsomagolt tároló kitárolása” munkafeldolgozást | Nincs <P>Bizonyos feldolgozás elvégezhető egy skálázási egység által kezelt kezdeti kitárolási folyamat után, de a következő blokkolt műveletek miatt nem ajánlott.</p>  | Nincs |
| Tároló eltávolítása csoportból                                  | Nincs  | Nincs |
| Kimenő rendezés feldolgozása                                  | Nincs  | Nincs |
| Rakományhoz kapcsolódó dokumentumok nyomtatása                           | Igen | Igen|
| Fuvarlevél és ASN-generálás                            | Nincs  | Igen|
| Szállítmány megerősítése                                             | Nincs  | Igen|
| Szállítmány megerősítése a „Megerősítés és áthelyezés” lehetőséggel            | Nincs  | Nincs |
| Szállítólevél és számlázások feldolgozása                        | Igen | Nincs |
| Rövid kitárolás (értékesítési és áttárolási rendelések)                    | Nincs  | Igen, a forrásdokumentumok foglalásának eltávolítása nélkül|
| Előírtnál nagyobb mennyiség kitárolása (értékesítési és áttárolási rendelések)                     | Nincs  | Igen|
| Munkahelyek módosítása (értékesítési és áttárolási rendelések)         | Nincs  | Igen|
| Befejezett munka (értékesítési és áttárolási rendelések)                    | Nincs  | Igen|
| Munka jelentésének nyomtatása                                            | Igen | Igen|
| Hullámcímke                                                   | Nincs  | Igen|
| Felosztott munka                                                   | Nincs  | Igen|
| Munkafeldolgozás – „Szállítási berakodás” irányítja            | Nincs  | Nincs |
| Kitárolt mennyiség csökkentése                                       | Nincs  | Nincs |
| Munka sztornírozása                                                 | Nincs  | Nincs |
| Szállítmány visszaigazolásának sztornírozása                                | Nincs  | Igen|

### <a name="inbound"></a>Bejövő

A következő táblázat bemutatja, hogy mely bejövő funkciók, és hol támogatottak, amikor a raktárkezelési számítási feladatok a felhőalapú és a peremhálózati skálázási egységekben használatosak.

| Feldolgozás                                                          | Központ | Raktári végrehajtási számítási feladat skálázási egységeken<BR>*(Az „Igen” jelölésű cikkek csak raktári rendelésekre vonatkoznak)* |
|------------------------------------------------------------------|-----|----------------------------------------------------------------------------------|
| Forrásdokumentum&nbsp;feldolgozása                             | Igen | Nincs |
| Rakomány és szállításkezelési folyamatok feldolgozása                    | Igen | Nincs |
| Beérkező szállítmány megerősítése                                    | Igen | Nincs |
| Beszerzési rendelés kiadása a raktárba (raktári rendelés feldolgozása) | Igen | Nincs |
| Raktári rendelési sorok visszavonása<p>Ne feledje, hogy ez csak akkor támogatott, ha a sorhoz nem történt regisztráció</p> | Igen | Nincs |
| Beszerzési rendelés – cikk bevételezése és eltárolása                       | <p>Igen,&nbsp;ha&nbsp;nincs&nbsp;raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | <p>Igen, ha a beszerzési rendelés nem része egy <i>rakománynak</i></p> |
| Beszerzésirendelés-sor bevételezése és betárolása                       | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | <p>Igen, ha a beszerzési rendelés nem része egy <i>rakománynak</i></p></p> |
| Visszárurendelés bevételezése és eltárolása                              | Igen | Nincs |
| Vegyes azonosítótábla bevételezése és eltárolása                       | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | Igen |
| Rakomány – cikk bevételezése                                              | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | Nincs |
| Azonosítótábla bevételezése és eltárolása                             | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | Nincs |
| Átmozgatási rendelés – cikk bevételezése és eltárolása                       | Igen | Nincs |
| Átmozgatásirendelés-sor bevételezése és betárolása                       | Igen | Nincs |
| Munka érvénytelenítése (bejövő)                                            | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | <p>Igen, de csak ha a <b>Bevételezés regisztrációjának törlése a munka visszavonásakor</b> beállítás (a <b>Raktárkezelés paraméterei</b> lapon) törölve lett</p> |
| Beszerzési rendelés termékbevételezés feldolgozása                        | Igen | Nincs |
| Beszerzési rendelés bevétele alulszállítással                      | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | Igen, de csak érvénytelenítési kérelem elküldésével a központból |
| Beszerzési rendelés bevétele túlszállítással                       | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | Igen  |
| Fogadás *Áttárolás* munka létrehozásával                 | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | Nincs |
| Fogadás *Minőségi rendelés* munka létrehozásával                  | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | Nincs |
| Fogadás *Minőségi cikk-mintavételezés* munka létrehozásával          | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | Nincs |
| Fogadás *Minőség a minőség-ellenőrzésnél* munka létrehozásával       | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | Nincs |
| Fogadás minőségi rendelés létrehozásával                            | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | Nincs |
| Munkafeldolgozás – *Fürtbetárolás* irányításával                 | Igen | Nincs |
| Munkafeldolgozás *Rövid kitárolással*                               | Igen | Nincs |
| Azonosítótábla rakodása                                           | Igen | Igen |

### <a name="warehouse-operations-and-exception-handing"></a>Raktári műveletek és kivételek kezelése

A következő táblázat bemutatja, hogy mely raktári műveletek és kivételkezelési funkciók, és hol támogatottak, amikor a raktárkezelési számítási feladatok a felhőalapú és a peremhálózati skálázási egységekben használatosak.

| Feldolgozás                                            | Központ | Raktári végrehajtási számítási feladat skálázási egységeken |
|----------------------------------------------------|-----|------------------------------|
| Azonosítótábla lekérdezése                              | Igen | Igen                          |
| Cikklekérdezés                                       | Igen | Igen                          |
| Hely lekérdezése                                   | Igen | Igen                          |
| Raktár módosítása                                   | Igen | Igen                          |
| Mozgás                                           | Igen | Igen                          |
| Mozgás sablon szerint                               | Igen | Igen                          |
| Raktári átmozgatás                                 | Igen | Nincs                           |
| Átmozgatási rendelés létrehozása a raktári alkalmazásból           | Igen | Nincs                           |
| Igazítás ki (be/ki)                                | Igen | Igen, de nem abban a korrekciós helyzetben, ahol a készletfoglalást el kell távolítani a **Foglalások eltávolítása** funkció használatával a készletkorrekció-típusoknál</p>                           |
| Készletállapot-változás                            | Igen | Nincs                           |
| Ciklikus leltározás és számbavételi eltérés feldolgozása | Igen | Igen                           |
| Címke újranyomtatása (azonosítótábla nyomtatása)             | Igen | Igen                          |
| Azonosítótábla felépítése                                | Igen | Nincs                           |
| Azonosítótábla felbontása                                | Igen | Nincs                           |
| Csomagolás beágyazott azonosítótáblákhoz                                | Igen | Nincs                           |
| Járművezető bejelentkezése                                    | Igen | Nincs                           |
| Járművezető kijelentkezése                                   | Igen | Nincs                           |
| Köteg intézkedési kódjának módosítása                      | Igen | Igen                          |
| Nyitott munkalista megjelenítése                             | Igen | Igen                          |
| Azonosítótáblák egyesítése                         | Igen | Nincs                           |
| Min./max. és zónaküszöb feltöltési feldolgozása| Igen <p>Az ajánlás az, hogy ne foglalja bele ugyanazt a helyet a lekérdezésekbe</p>| Igen                          |
| Időközökre bontott feltöltés feldolgozása                  | Igen  | Igen<p>Ne feledje, hogy a beállítást a skálázási egységen kell beállítani</p>                           |
| Munka zárolása és feloldása                             | Igen | Igen                          |
| Felhasználóváltás                                        | Igen | Igen                          |
| Munkagyűjtő módosítása a munkán                           | Igen | Igen                          |
| Munka megszakítása                                        | Igen | Igen                          |

### <a name="production"></a>Termelés

A következő táblázat összefoglalja, hogy mely raktárkezelési termelési helyzetek támogatottak (és nem támogatottak) jelenleg a skálázási egység munkaterheléseken, a következő táblázatban jelzett módon.

| Feldolgozás | Központ | Raktári végrehajtási számítási feladat skálázási egységeken |
|---------|-----|------------------------------|
| Készként jelentés és késztermék betárolása | Igen | Igen |
| Társ- és melléktermék betárolása | Igen | Igen |
| <p>A termeléshez kapcsolódó összes egyéb raktárkezelési folyamat, beleértve:</p><li>Kiadás raktárba</li><li>Termelés hullámfeldolgozása</li><li>Nyersanyag kitárolása</li><li>Kanban betárolás</li><li>Kanban kitárolás</li><li>Termelési rendelés indítása</li><li>Termelési selejt</li><li>Termelés – utolsó raklap</li><li>Anyagfelhasználás regisztrálása</li><li>Üres kanban</li></ul> | Igen | Nincs |
| Nyersanyag feltöltése | Nincs | Nincs |

## <a name="maintaining-scale-units-for-warehouse-execution"></a>A raktárvégrehajtáshoz szükséges skálázási egységek karbantartása

Több kötegelt feladat fut mind a központon, mind a skálázási egységeken.

A központi telepítésben manuálisan karbantarthatja a kötegelt feladatokat. A **Raktárkezelés \> Időszakos feladatok \> Háttérrendszer számítási feladatainak kezelése** részen a következő kötegelt feladatot kezelheti:

- Skálázási egységből a központi üzenetfeldolgozóba
- Rendelésiforrás-nyugták regisztrálása
- Raktári rendelések befejezése

A skálázási egységek számítási feladatában a következő kötegelt feladatot kezelheti a **Raktárkezelés \> Időszakos feladatok \> Számítási feladatok kezelése** részen:

- Hullám táblarekordjainak feldolgozása
- A skálázási egység üzenetfeldolgozójának raktárközpontja
- Raktári rendelési sorok mennyiségfrissítési kéréseinek feldolgozása

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
