---
title: Raktárkezelési számítási feladatok felhőalapú és peremhálózati skálázási egységekhez
description: Ez a témakör arról a szolgáltatásról nyújt tájékoztatást, amely lehetővé teszi a skálázási egységek számára a kiválasztott folyamatok futtatását a raktárkezelési számítási feladatából.
author: perlynne
ms.date: 04/22/2021
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
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 30ccdf45d4993e9803f86025f8e789d4f75f64dc
ms.sourcegitcommit: 8d50c905a0c9d4347519549b587bdebab8ffc628
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2021
ms.locfileid: "6184022"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Raktérkezelés munkaterhelései felhőalapú és peremhálózat-lépték szerinti egységekhez

[!include [banner](../includes/banner.md)]

> [!WARNING]
> Nem minden raktárkezelési üzleti funkció támogatott teljesen az olyan raktárak esetében, amelyek munkaterhelést futtatnak egy skálázási egységen. Ügyeljen arra, hogy csak azokat a folyamatokat használja, amelyeket ez a témakör kifejezetten támogatottként ír le.

## <a name="warehouse-execution-on-scale-units"></a>Raktári végrehajtás skálázási egységeken

Ez a szolgáltatás lehetővé teszi a skálázási egységek számára a kiválasztott folyamatok futtatását a raktárkezelési képességekből.

Ebben a témakörben a skálázási egységként definiált raktárban történő raktárkezelési végrehajtásokat *Raktárvégrehajtási rendszernek* (*WES*) nevezzük.

## <a name="prerequisites"></a>Előfeltételek

Rendelkeznie kell egy Dynamics 365 Supply Chain Management-központtal és skálázási egységgel, amely telepítve van a raktárfelügyeleti számítási feladatokkal. Az architektúráról és a telepítési folyamatról további információt a [Skálázási egységek használata a Resilience for Supply Chain Management munkaterheléseivel](cloud-edge-landing-page.md) talál.

## <a name="how-the-wes-workload-works-on-scale-units"></a>A WES-számítási feladat működése a skálázási egységeken

A folyamatok a raktárkezelési számítási feladat folyamatai esetében az adatok a központ és a skálázási egység között szinkronizálva vannak.

A skálázási egység csak a tulajdonában lévő adatokat tarthatja karban. A méretezési egységek adattulajdonosi koncepciója segít megelőzni a több főkiszolgálós megoldások ütközéseit. Ezért fontos, hogy tisztában legyen azzal, hogy mely folyamatok vannak a központ tulajdonában, és melyek vannak a skálázási egységek tulajdonában.

A skálázási egységek a következő adatokat birtokolják:

- **Szállítási hullámfeldolgozási adatok** – A kiválasztott hullámfeldolgozási módszerek a skálázási egység hullámfeldolgozásának részeként kerülnek kezelésre.
- **Munkafeldolgozási adatok** – a skálázási egységen létrehozott raktári munka tulajdonosa ez a megadott skálázási egység lesz. A következő típusú munkarendelések feldolgozása támogatott:

  - **Készletmozgatások** (manuális mozgatás és mozgatás sablon szerint)
  - **Ciklikus leltározás** és a jóváhagyási/elutasítási folyamat a leltározási műveletek részeként
  - **Beszerzési rendelések** (rakodómunka raktári rendelésen keresztül, ha a beszerzési rendelések nincsenek rakományhoz társítva)
  - **Értékesítési rendelések** (egyszerű kitárolási és rakodási munka)
  - **Átmozgatási rendelések** (csak kimenő egyszerű kitárolási és berakodási munka esetén)

- **Raktári rendelés bevételezési adatai** – ezeket az adatokat csak olyan beszerzési rendelésekhez használja a program, amelyeket kiadtak a raktárba.
- **Azonosítótábla-adatok** – a központon és a skálázási egységeken azonosítótáblák hozhatók létre. Dedikált ütközés-kezelés van megadva. 

    > [!IMPORTANT]
    > Az azonosítótábla-adat nem a raktárspecifikus. Ha ugyanaz az azonosítótábla-szám jön létre mind a központban, mind a skálázási egységen ugyanabban a szinkronizálási ciklusban, a következő szinkronizálás sikertelen lesz. Ha ez megtörténik, lépjen a **Rendszerfelügyelet > Lekérdezések > Munkaterhelés lekérdezések > Duplikált rekordok** helyre, ahol megtekintheti és egyesítheti az adatokat.

## <a name="outbound-process-flow"></a>Kimenő feldolgozási folyamat

A központ a következő adatokat birtokolja:

- Minden forrásdokumentum, például értékesítési rendelések és átmozgatási rendelések
- Rendelés felosztása és kimenő terhelés feldolgozása
- A raktárba történő kiadás, a szállítmány létrehozása, a hullámlétrehozás és a hullámvéglegesítés folyamatok

A skálázási egységek birtokolják a hullám kibocsátása után a tényleges hullámfeldolgozási egységeket (például a munka felosztását, a feltöltési munkát és a munkaszükségletek létrehozását). Ennélfogva a raktári dolgozók a kimenő munkát a skálázási egységhez kapcsolódó Raktárkezelés mobilalkalmazás segítségével dolgozzák fel.

![Hullámfeldolgozási folyamat](./media/wes-wave-processing-ga.png "Hullámfeldolgozási folyamat")

### <a name="process-work-and-ship"></a>Munka és szállítás feldolgozása

Amint a végső munkafolyamat a végső kiszállítási helyre (raktárajtó) helyezi a készletet, a skálázási egység jelzi a központnak, hogy frissítse a forrásdokumentum készlettranzakcióit *Kitárolva* értékre. Amíg ez a folyamat fut, és visszaszinkronizálásra kerül, addig a skálázási egység munkaterhelésén található aktuális készlet fizikailag le lesz foglalva a raktár szintjén.

Amint a központ frissítette a tranzakciókat *Kitárolva* értékre, a rendszer feldolgozhatja a kimenő szállítmány megerősítését, valamint a társított értékesítési szállítólevelet vagy a rakományhoz tartozó átmozgatási rendelés szállítmányát.

![Kimenő feldolgozási folyamat](./media/WES-outbound-processing-19.png "Kimenő feldolgozási folyamat")

## <a name="inbound-process-flow"></a>Bemenő feldolgozási folyamat

A központ a következő adatokat birtokolja:

- Minden forrásdokumentum, például beszerzési rendelések és értékesítési visszárurendelések
- Bejövő terhelésfeldolgozás
- Minden költség- és pénzügyi frissítés

> [!NOTE]
> A bejövő beszerzési rendelési folyamat koncepciójában különbözik a kimenő folyamattól. Ugyanazt a raktárat a mérlegegységen vagy a központon lehet működtetni attól függően, hogy a beszerzési rendelés ki van-e adva raktárba. Ha már kiadott egy rendelést a raktárba, akkor csak akkor dolgozhat azzal a rendeléssel, ha bejelentkezett a skálázási egységbe.
>
> Ha a *Kiadás raktárba* folyamatot használja, akkor létrejönnek a [*raktári rendelések*](cloud-edge-warehouse-order.md), és a kapcsolódó bevételezési folyamat tulajdonjoga a skálázási egységhez van rendelve. A központ nem fogja tudni regisztrálni a bejövő bevételezéseket.

Be kell jelentkeznie a központba a *Kiadás raktárba* folyamat használatához. Lépjen a következő oldalak egyikére a futtatáshoz vagy ütemezéshez:

- **Beszerzés és forrás > Beszerzési rendelések > Összes beszerzési rendelés > Raktár > Műveletek > Kiadás raktárba**
- **Raktárkezelés > Kiadás a raktárba > Értékesítési rendelések automatikus kiadása**

A **Beszerzési rendelések automatikus kiadása** funkció használatakor lekérdezés alapján meghatározott beszerzésirendelés-sorokat választhat ki. Jellemző helyzet lehet egy ismétlődő kötegelt feladat, amely kiadja a következő napon várható összes visszaigazolt beszerzésirendelés-sort.

A dolgozó a skálázási egységhez kapcsolódó Raktárkezelés mobilalkalmazás segítségével futtathatja a bevételezési folyamatot. A skálázási egység ezt követően rögzíti az adatokat, és a bejövő raktári rendeléssel szemben jelenti őket. A következő betárolás létrehozását és feldolgozását a skálázási egység is kezeli.

Ha nem használja a *kiadás raktárba* folyamatot, és így nem használja a *raktári rendeléseket*, akkor a központ a raktári bevételezést és a munka feldolgozását a skálázási egységtől függetlenül feldolgozhatja.

![Bemenő feldolgozási folyamat](./media/wes-inbound-ga.png "Bemenő feldolgozási folyamat")

Ha a raktári alkalmazás bevételezési folyamatával végez bejövő regisztrációt a skálázási egység raktári rendelése alapján, a skálázási egység munkaterhelése jelez a központnak, hogy frissítse a kapcsolódó beszerzésirendelés-sor tranzakcióit *Regisztrálva* értékre. Amint ez befejeződött, a központon futtathatja a beszerzési rendelés termékbevételezését.

![Bejövő feldolgozási folyamat](./media/WES-inbound-processing-19.png "Bejövő feldolgozási folyamat")

## <a name="supported-processes-and-roles"></a>Támogatott folyamatok és szerepkörök

A program nem minden raktárkezelési folyamatot támogat egy WES-számítási feladatban egy skálázási egységen. Ezért ajánlott olyan szerepköröket hozzárendelni, amelyek megfelelnek az egyes felhasználók számára elérhető funkcióknak.

Ennek a folyamatnak a megkönnyítésére a program a *Raktárkezelő számítási feladaton* nevű mintaszerepkör megtalálható a **Rendszerfelügyelet \> Biztonság \> Biztonsági beállítások** alatti bemutató adatok között. Ennek a szerepkörnek a célja, hogy a raktárkezelők hozzáférjenek a WES-hez a skálázási egységen. A szerepkör olyan oldalakhoz való hozzáférést biztosít, amelyek a skálázási egységen szereplő számítási feladatok összefüggésében fontosak.

A skálázási egység felhasználói szerepköreit a program a központ által a skálázási egység történő kezdeti adatszinkronizálás részeként rendeli hozzá.

A felhasználóhoz rendelt szerepkörök módosításához nyissa meg a **Rendszerfelügyelet \> Biztonság \> Felhasználók hozzárendelése szerepekhez** részt. Azokhoz a felhasználókhoz, akik csak a skálázási egységeken tevékenykednek raktárikezelőként csak a *Raktárkezelő számítási feladaton* nevű szerepet kell hozzárendelni. Ez a megközelítés biztosítja, hogy ezek a felhasználók csak a támogatott funkciókhoz férjenek hozzá. Távolítsa el a felhasználókhoz rendelt összes egyéb szerepkört.

Azokhoz a felhasználókhoz, akik mind a központban, mind a skálázási egységeken tevékenykednek raktárikezelőként, a meglévő *Raktárkezelő munkás* nevű szerepet kell hozzárendelni. Ne feledje, hogy ez a szerepkör biztosítja a raktári dolgozók számára a felhasználói felületen (UI) megjelenő funkciókat (például az átmozgatási rendelés bevételezési feldolgozását), amelyek jelenleg nem támogatottak a skálázási egységen.

## <a name="supported-wes-processes"></a>Támogatott WES-folyamatok

A következő raktári végrehajtási folyamatok engedélyezettek egy WES-számítási feladat esetében egy skálázási egységen:

- Kiválasztott hullám metódusok értékesítési és átátviteli rendelésekhez (felosztás, igényfeltöltés, tárolóra készítés, munka létrehozása és hullámcímke-nyomtatás)

- Az értékesítési és átviteli rendelések raktári munkához történő feldolgozása a raktári alkalmazással (a feltöltési munkát is beleértve)
- Aktuális készlet lekérdezése a raktári alkalmazás használatával
- A készlet mozgásának létrehozása és futtatása a raktári alkalmazás használatával
- Ciklikus leltározási munka létrehozása és feldolgozása a raktári alkalmazás segítségével
- Készletkorrekció végrehajtása a raktári alkalmazás használatával
- Beszerzési rendelések regisztrálása és betárolási munka a raktári alkalmazás használatával

A következő munkarendelés-típusok jelenleg támogatottak a WES számítási feladatok esetében a skálázási egység telepítésein:

- Értékesítési rendelés
- Átmozgatási probléma
- Feltöltés
- Készletmozgás
- Ciklikus leltározás
- Beszerzési rendelések (raktári rendelésekhez kapcsolódó)

A program jelenleg nem támogatja a forrásoldali dokumentumok egyéb típusainak feldolgozását vagy a raktári munkát a skálázási egységekben. Például egy skálázási egységre vonatkozó WES-munkaterhelés esetén nem lehet áthozott rendelés bevételezését (átviteli bevételezést), ehelyett ezt a központi példánynak kell feldolgoznia.

> [!NOTE]
> A nem támogatott funkciókhoz használható mobileszköz-menüpontok és gombok nem jelennek meg a _Raktárkezelés mobilalkalmazásban_, ha skálázásiegység-telepítéshez kapcsolódik.

> [!WARNING]
> Amikor egy skálázási egységen számítási feladatot alkalmaz, akkor nem futtathat nem támogatott folyamatokat az adott raktár esetében a központban. A témakörben később található táblázatok a támogatott funkciókat dokumentálják.
>
> Kiválasztott raktári munkatípusokat a központon és a skálázási egységeken is létre lehet hozni, de csak a saját központ vagy skálázási egység (az adatokat létrehozó telepítés) tarthatja fenn.
>
> Még ha támogatott is egy adott folyamat a skálázási egység által, ne feledje, hogy az összes szükséges adat nem feltétlenül szinkronizálható a központból a skálázási egységbe, vagy a skálázási egységből a központba, ami a váratlan rendszerfeldolgozást eredményező kockázathoz vezet. Példák erre:
> 
> - Ha olyan helylekérdező lekérdezést használ, amely olyan adattáblarekordhoz csatlakozik, amely csak a központ telepítésében létezik.
> - A helyállapot és/vagy a hely rakodási kapacitás funkciók használata esetén. Ezek az adatok nem lesznek szinkronizálva a telepítések között, ezért csak akkor működnek, ha az egyik telepítés aktuális hely készletét frissítik.

A következő raktárkezelési funkciók jelenleg nem támogatottak a skálázásiegység-munkaterhelésekben:

- Rakományhoz rendelt beszerzésirendelés-sorok bejövő feldolgozása
- Beszerzési rendelések bejövő feldolgozása egy projekthez
- A **Tulajdonos** és/vagy **Sorozatszám** aktív követési dimenziókat tartalmazó cikkek bejövő és kimenő feldolgozása
- Zároló állapotértékű készlet feldolgozása
- Készletállapot módosítása bármely munkamozgási folyamat során
- Rendelésben véglegesített rugalmas raktárszintű dimenziófoglalások
- A *Raktári helyállapot* funkció használata (az adatok nincsenek szinkronizálva a telepítések között)
- *Hely és azonosítótábla pozicionálása* funkció használata
- *Termékszűrők* és *Termékszűrő-csoportok* használata, beleértve a **Napok száma a kötegek kombinációjára** beállítást
- Integráció a minőségirányítással
- Feldolgozás tényleges súllyal rendelkező cikkekkel
- Feldolgozás csak szállításkezelésre engedélyezett cikkekkel (TMS)
- Feldolgozás negatív aktuális készlettel
- Raktári munka feldolgozása egyéni munkatípusokkal
- Raktári munka feldolgozása szállítmánylevelekkel
- Raktári munka feldolgozása anyagkezelési/raktárautomatizálással
- Az alaptermék adatképének használata (például a Raktárkezelés mobilalkalmazásban)

> [!WARNING]
> Bizonyos raktári funkciók nem érhetők el az olyan raktáraknál, ahol a raktárkezelési terhelések egy skálázási egységen futnak, és a központ és a skálázási egység munkaterhelés esetén sem támogatott.
> 
> Más funkciók mindkét esetben feldolgozhatók, de bizonyos helyzetekben körültekintő használatot igényelnek, például amikor az aszinkron adatfrissítési folyamat miatt ugyanannak a raktárnak az aktuális készlete frissül ugyanahhoz a raktárhoz és skálázási egységhez.
> 
> A központon és a skálázási egységen egyaránt támogatott funkciók (például a *blokkolt munka*) csak az adatok tulajdonosa számára támogatottak.

### <a name="outbound-supported-only-for-sales-and-transfer-orders"></a>Kimenő (csak értékesítési és átmozgatási rendeléseknél támogatott)

A következő táblázat bemutatja, hogy mely kimenő funkciók, és hol támogatottak, amikor a raktárkezelési számítási feladatok a felhőalapú és a peremhálózati skálázási egységekben használatosak.

| Feldolgozás                                                      | Központ | WES számítási feladat egy skálázási egységben |
|--------------------------------------------------------------|-----|------------------------------|
| Forrásdokumentum feldolgozása                                   | Igen | Nincs |
| Rakomány és szállításkezelési folyamatok feldolgozása                | Igen | Nincs |
| Kiadás raktárba                                         | Igen | Nincs |
| Tervezett áttárolás                                        | Nincs  | Nincs |
| Szállítmánykonszolidáció                                       | Igen | Nincs |
| Szállítmány hullámfeldolgozása                                     | Igen, de csak a hullám állapotának inicializálása és véglegesítése történik a központban. Ez azt jelenti, hogy a kimenő átvitelt és az értékesítési rendelés feldolgozását csak a skálázási egység intézheti.|<p>Nem, az inicializálást és a véglegesítést a központ intézi, és a **Rakományok összeállítása és rendezése** nem támogatott.<p><b>Megjegyzés:</b> A központhoz való hozzáféréshez szükséges a hullám állapotának véglegesítése a hullám feldolgozásának részeként.</p> |
| Hullámhoz szállítások karbantartása                                  | Igen | Nincs |
| Raktári munka feldolgozása (az azonosítótábla nyomtatásával együtt)        | Nincs  | <p>Igen, de csak a fent említett támogatott funkciókhoz. |
| Fürt kitárolása                                              | Nincs  | Igen|
| Manuális csomagolásfeldolgozás, beleértve a „Becsomagolt tároló kitárolása” munkafeldolgozást | Nincs <P>Bizonyos feldolgozás elvégezhető egy skálázási egység által kezelt kezdeti kitárolási folyamat után, de a következő blokkolt műveletek miatt nem ajánlott.</p>  | Nincs |
| Tároló eltávolítása csoportból                                  | Nincs  | Nincs |
| Kimenő rendezés feldolgozása                                  | Nincs  | Nincs |
| Rakományhoz kapcsolódó dokumentumok nyomtatása                           | Igen | Nincs |
| Fuvarlevél és ASN-generálás                            | Igen | Nincs |
| Szállítmány megerősítése                                             | Igen | Nincs |
| Szállítmány megerősítése a „Megerősítés és áthelyezés” lehetőséggel            | Nincs  | Nincs |
| Szállítólevél és számlázások feldolgozása                        | Igen | Nincs |
| Rövid kitárolás (értékesítési és áttárolási rendelések)                    | Nincs  | Nincs |
| Előírtnál nagyobb mennyiség kitárolása (értékesítési és áttárolási rendelések)                     | Nincs  | Nincs |
| Munkahelyek módosítása (értékesítési és áttárolási rendelések)         | Nincs  | Igen|
| Befejezett munka (értékesítési és áttárolási rendelések)                    | Nincs  | Igen|
| Munka jelentésének nyomtatása                                            | Igen | Nincs |
| Hullámcímke                                                   | Nincs  | Igen|
| Felosztott munka                                                   | Nincs  | Igen|
| Munkafeldolgozás – „Szállítási berakodás” irányítja            | Nincs  | Nincs |
| Kitárolt mennyiség csökkentése                                       | Nincs  | Nincs |
| Munka sztornírozása                                                 | Nincs  | Nincs |
| Szállítmány visszaigazolásának sztornírozása                                | Igen | Nincs |

### <a name="inbound"></a>Bejövő

A következő táblázat bemutatja, hogy mely bejövő funkciók, és hol támogatottak, amikor a raktárkezelési számítási feladatok a felhőalapú és a peremhálózati skálázási egységekben használatosak.

| Feldolgozás                                                          | Központ | WES számítási feladat egy skálázási egységben<BR>*(Az „Igen” jelölésű cikkek csak raktári rendelésekre vonatkoznak)*</p> |
|------------------------------------------------------------------|-----|----------------------------------------------------------------------------------|
| Forrásdokumentum&nbsp;feldolgozása                             | Igen | Nincs |
| Rakomány és szállításkezelési folyamatok feldolgozása                    | Igen | Nincs |
| Beérkező szállítmány megerősítése                                    | Igen | Nincs |
| Beszerzési rendelés kiadása a raktárba (raktári rendelés feldolgozása) | Igen | Nincs |
| Raktári rendelési sorok visszavonása<p>Ne feledje, hogy ez csak akkor támogatott, ha a sorhoz nem történt regisztráció</p> | Igen | Nincs |
| Beszerzési rendelés – cikk bevételezése és eltárolása                       | <p>Igen,&nbsp;ha&nbsp;nincs&nbsp;raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | <p>Igen, ha a beszerzési rendelés nem része egy <i>rakománynak</i></p> |
| Beszerzésirendelés-sor bevételezése és betárolása                       | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | <p>Igen, ha a beszerzési rendelés nem része egy <i>rakománynak</i></p></p> |
| Visszárurendelés bevételezése és eltárolása                              | Igen | Nincs |
| Vegyes azonosítótábla bevételezése és eltárolása                       | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | Nincs |
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

| Feldolgozás                                            | Központ | WES számítási feladat egy skálázási egységben |
|----------------------------------------------------|-----|------------------------------|
| Azonosítótábla lekérdezése                              | Igen | Igen                          |
| Cikklekérdezés                                       | Igen | Igen                          |
| Hely lekérdezése                                   | Igen | Igen                          |
| Raktár módosítása                                   | Igen | Igen                          |
| Mozgás                                           | Igen | Igen                          |
| Mozgás sablon szerint                               | Igen | Igen                          |
| Raktári átmozgatás                                 | Igen | Nincs                           |
| Átmozgatási rendelés létrehozása a raktári alkalmazásból           | Igen | Nincs                           |
| Igazítás ki (be/ki)                                | Igen | Igen, de nem abban a korrekciós helyzetben, ahol a készletfoglalást el kell távolítani a **Foglalások eltávolítása** funkció használatával a készletkorrekció-típusoknál.</p>                           |
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

A következő táblázat összefoglalja, hogy mely raktárkezelési termelési helyzetek (nem) támogatottak jelenleg a skálázási egység munkaterheléseken, a következő táblázatban jelzett módon.

| Feldolgozás | Központ | WES számítási feladat egy skálázási egységben |
|---------|-----|------------------------------|
| Készként jelentés és késztermék betárolása | Igen | Igen |
| Társ- és melléktermék betárolása | Igen | Igen |
| <p>A termeléshez kapcsolódó összes egyéb raktárkezelési folyamat, beleértve:</p><li>Kiadás raktárba</li><li>Termelés hullámfeldolgozása</li><li>Nyersanyag kitárolása</li><li>Kanban betárolás</li><li>Kanban kitárolás</li><li>Termelési rendelés indítása</li><li>Termelési selejt</li><li>Termelés – utolsó raklap</li><li>Anyagfelhasználás regisztrálása</li><li>Üres kanban</li></ul> | Igen | Nincs |

## <a name="maintaining-scale-units-for-wes"></a>A WES skálázási egységeinek karbantartása

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
