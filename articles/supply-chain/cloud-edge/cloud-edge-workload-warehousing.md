---
title: Raktárkezelési számítási feladatok felhőalapú és peremhálózati skálázási egységekhez
description: Ez a témakör arról a szolgáltatásról nyújt tájékoztatást, amely lehetővé teszi a skálázási egységek számára a kiválasztott folyamatok futtatását a raktárkezelési számítási feladatából.
author: perlynne
manager: tfeyr
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, SysSecRolesEditUsers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 4ac76ad5cd88c35ac312b8e73d942a692f35c8aa
ms.sourcegitcommit: 8eefb4e14ae0ea27769ab2cecca747755560efa3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/13/2020
ms.locfileid: "4516798"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Raktárkezelési számítási feladatok felhőalapú és peremhálózati skálázási egységekhez

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> Nem minden üzleti funkció teljes mértékben támogatott a nyilvános előzetes verzióban, ha számítási feladatok skálázási egységeit használja. Ügyeljen arra, hogy csak azokat a folyamatokat használja, amelyeket ez a témakör kifejezetten támogatottként ír le.

## <a name="warehouse-execution-on-scale-units"></a>Raktári végrehajtás skálázási egységeken

Ez a szolgáltatás lehetővé teszi a skálázási egységek számára a kiválasztott folyamatok futtatását a raktárkezelési képességekből. A felhőalapú skálázási egységek a felhőben futtatják a számítási feladatokat a kiválasztott Microsoft Azure-régió dedikált feldolgozási kapacitásának használatával. A peremhálózati skálázási egységek esetében, egyes számítási feladatok futtathatók egymástól függetlenül a helyszínen, még akkor is, ha a skálázási egységek ideiglenesen le vannak választva a felhőből.

Ebben a témakörben a skálázási egységként definiált raktárban történő raktárkezelési végrehajtásokat *Raktárvégrehajtási rendszernek* (*WES*) nevezzük.

## <a name="prerequisites"></a>Előfeltételek

Rendelkeznie kell egy Dynamics 365 Supply Chain Management-központtal és skálázási egységgel, amely telepítve van a raktárfelügyeleti számítási feladatokkal. Az architektúráról és a telepítési folyamatról további információt a [Felhőalapú és peremhálózat-lépték szerinti egységkezelés a gyártás és raktári végrehajtás munkaterheléseivel](cloud-edge-landing-page.md) talál.

## <a name="how-the-wes-workload-works-on-scale-units"></a>A WES-számítási feladat működése a skálázási egységeken

A folyamatok a raktárkezelési számítási feladat folyamatai esetében az adatok a központ és a skálázási egység között szinkronizálva vannak.

A skálázási egység csak a tulajdonában lévő adatokat tarthatja karban. A méretezési egységek adattulajdonosi koncepciója segít megelőzni a több főkiszolgálós megoldások ütközéseit. Ezért fontos, hogy tisztában legyen azzal, hogy mely folyamatok vannak a központ tulajdonában, és melyek vannak a skálázási egységek tulajdonában.

A skálázási egységek a következő adatokat birtokolják:

- **Hullámfeldolgozási adatok** – A kiválasztott hullámfeldolgozási módszerek a skálázási egység hullámfeldolgozásának részeként kerülnek kezelésre.
- **Munkafeldolgozási adatok** – A munkarendelés-feldolgozás következő típusai támogatottak:

    - Készletmozgatások (manuális mozgatás és mozgatás sablon szerint)
    - Beszerzési rendelések ( betárolási munka a raktári rendelésen keresztül)
    - Értékesítési rendelések (egyszerű kitárolási és rakodási munka )

- **Raktári rendelés bevételezési adatai** – ezeket az adatokat csak olyan beszerzési rendelésekhez használja a program, amelyek manuálisan kerülnek kiadásra a raktárba.
- **Azonosítótábla-adatok** – a központon és a skálázási egységen azonosítótáblák hozhatók létre. Dedikált ütközés-kezelés van megadva. Ne feledje, hogy ez az adat nem a raktárra jellemző.

## <a name="outbound-process-flow"></a>Kimenő feldolgozási folyamat

A központ a következő adatokat birtokolja:

- Minden forrásdokumentum, például értékesítési rendelések és átmozgatási rendelések
- Rendelés felosztása és kimenő terhelés feldolgozása
- A raktárba történő kiadás, a szállítmány létrehozása és a hullámlétrehozási folyamatok

A skálázási egységek birtokolják a hullám kibocsátása után a tényleges hullámfeldolgozási egységeket (például a munka felosztását, a feltöltési munkát és a munkaszükségletek létrehozását). Ennélfogva a raktári dolgozók a kimenő munkát a skálázási egységhez kapcsolódó raktári alkalmazás segítségével dolgozzák fel.

![Hullámfeldolgozási folyamat](./media/wes_wave_processing_flow.png "Hullámfeldolgozási folyamat")

## <a name="inbound-process-flow"></a>Bemenő feldolgozási folyamat

A központ a következő adatokat birtokolja:

- Minden forrásdokumentum, például beszerzési rendelések és értékesítési visszárurendelések
- Bejövő terhelésfeldolgozás

> [!NOTE]
> A bejövő beszerzési rendelés folyamata fogalmilag eltér a kimenő folyamattól, ahol a feldolgozást elvégző skálázási egységet az határozza meg, hogy a rendelést a raktárba adták-e ki.

Ha a *kiadás raktárba* folyamatot használja, akkor létrejönnek a raktári rendelések, és a kapcsolódó bevételezési folyamat tulajdonjoga a skálázási egységhez van rendelve. A központ nem fogja tudni regisztrálni a bejövő bevételezéseket.

A dolgozó a skálázási egységhez kapcsolódó raktári alkalmazás segítségével futtathatja a bevételezési folyamatot. A skálázási egység ezt követően rögzíti az adatokat, és a bejövő raktári rendeléssel szemben jelenti őket. A következő betárolás létrehozását és feldolgozását a skálázási egység is kezeli.

Ha nem használja a *kiadás raktárba* folyamatot, és így nem használja a *raktári rendeléseket*, akkor a központ a raktári bevételezést és a munka feldolgozását a skálázási egységtől függetlenül feldolgozhatja.

![Bemenő feldolgozási folyamat](./media/wes_Inbound_flow.png "Bemenő feldolgozási folyamat")

## <a name="supported-processes-and-roles"></a>Támogatott folyamatok és szerepkörök

A program nem minden raktárkezelési folyamatot támogat egy WES-számítási feladatban egy skálázási egységen. Ezért ajánlott olyan szerepköröket hozzárendelni, amelyek megfelelnek az egyes felhasználók számára elérhető funkcióknak.

Ennek a folyamatnak a megkönnyítésére a program a *Raktárkezelő számítási feladaton* nevű mintaszerepkör megtalálható a **Rendszerfelügyelet \> Biztonság \> Biztonsági beállítások** alatti bemutató adatok között. Ennek a szerepkörnek a célja, hogy a raktárkezelők hozzáférjenek a WES-hez a skálázási egységen. A szerepkör olyan oldalakhoz való hozzáférést biztosít, amelyek a skálázási egységen szereplő számítási feladatok összefüggésében fontosak.

A skálázási egység felhasználói szerepköreit a program a központ által a skálázási egység történő kezdeti adatszinkronizálás részeként rendeli hozzá.

A felhasználóhoz rendelt szerepkörök módosításához nyissa meg a **Rendszerfelügyelet \> Biztonság \> Felhasználók hozzárendelése szerepekhez** részt a skálázási egységen. Azokhoz a felhasználókhoz, akik csak a skálázási egységeken tevékenykednek raktárikezelőként csak a *Raktárkezelő számítási feladaton* nevű szerepet kell hozzárendelni. Ez a megközelítés biztosítja, hogy ezek a felhasználók csak a támogatott funkciókhoz férjenek hozzá. Távolítsa el a felhasználókhoz rendelt összes egyéb szerepkört.

Azokhoz a felhasználókhoz, akik mind a központban, mind a skálázási egységeken tevékenykednek raktárikezelőként, a meglévő *Raktárkezelő munkás* nevű szerepet kell hozzárendelni. Ne feledje, hogy ez a szerepkör biztosítja a raktári dolgozók számára a felhasználói felületen (UI) megjelenő funkciókat (például az átmozgatási rendelés feldolgozását), amelyek jelenleg nem támogatottak a skálázási egységen.

## <a name="supported-wes-processes"></a>Támogatott WES-folyamatok

A következő raktári végrehajtási folyamatok engedélyezettek egy WES-számítási feladat esetében egy skálázási egységen:

- Az értékesítési rendelésekhez és a szükségletek feltöltéséhez kiválasztott hullámos módszerek
- Munkarendelések futtatása értékesítési rendelésekből és igényfeltöltésből a raktári alkalmazás használatával
- Aktuális készlet lekérdezése a raktári alkalmazás használatával
- A készlet mozgásának létrehozása és futtatása a raktári alkalmazás használatával
- Beszerzési rendelések regisztrálása és betárolási munka a raktári alkalmazás használatával

A következő munkarendelés-típusok jelenleg támogatottak a WES számítási feladatok esetében a skálázási egység telepítésein:

- Értékesítési rendelés
- Feltöltés
- Készletmozgás
- A raktári rendelésekhez kapcsolódó beszerzési rendelések

A program jelenleg nem támogatja a forrásoldali dokumentumok egyéb feldolgozását a skálázási egységekben. Például egy skálázási egységnél a WES számítási feladat esetében nem hajthatók végre a következő műveletek:

- Átmozgatási rendelés kiadása.
- A kimenő raktári kitárolási és szállítási műveletek feldolgozása.

> [!IMPORTANT]
> Ha egy skálázási egységen számítási feladatot alkalmaz, akkor nem futtathat nem támogatott folyamatokat az adott raktár esetében a központban.

A következő raktárkezelési funkciók jelenleg nem támogatottak skálázási egységekben:

- Az aktív követési dimenziókat (például köteg- vagy sorozatszám-dimenziókat) tartalmazó cikkek bejövő és kimenő feldolgozása
- A készlet állapotával kapcsolatos módosítások feldolgozása
- Zároló állapotértékű készlet feldolgozása
- Integráció a minőségirányítással
- Integráció a gyártással
- Tényleges súllyal rendelkező cikkek feldolgozása
- Túlszállítás és szállítási hiány feldolgozása
- Negatív aktuális készlet feldolgozása

### <a name="outbound-supported-only-for-sales-orders-and-demand-replenishment"></a>Kimenő (csak értékesítési rendeléseknél és igény szerinti feltöltésnél támogatott)

A következő táblázat bemutatja, hogy mely kimenő funkciók, és hol támogatottak, amikor a raktárkezelési számítási feladatok a felhőalapú és a peremhálózati skálázási egységekben használatosak.

> [!WARNING]
> Mivel csak az értékesítési rendelés feldolgozását támogatja a program, a kimenő raktárkezelési feldolgozás nem használható átmozgatási rendelésekhez.
>
> Néhány raktári funkció nem érhető el olyan raktárakban, amelyeknél a raktárkezelési számítási feladatok egy skálázási egységben futnak.

| Feldolgozás                                                      | Központ | WES számítási feladat egy skálázási egységben |
|--------------------------------------------------------------|-----|------------------------------|
| Forrásdokumentum feldolgozása                                   | Igen | Nincs |
| Rakomány és szállításkezelési folyamatok feldolgozása                | Igen | Nincs |
| Kiadás raktárba                                         | Igen | Nincs |
| Szállítmánykonszolidáció                                       | Nincs  | Nincs |
| Áttárolási (kitárolási munka)                                 | Nincs  | Nincs |
| Szállítmány hullámfeldolgozása                                     | Nem, de a hullám állapotának véglegesítése a központban történik |<p>Igen, de a következő lehetőségeket nem támogatja a rendszer:</p><ul><li>Párhuzamos munkalétrehozás</li><li>Rakományok összeállítása és rendezése</li><li>Tárolóra bontás</li><li>Hullámcímke nyomtatása</li></li></ul><p><b>Megjegyzés:</b> A központhoz való hozzáféréshez szükséges a hullám állapotának véglegesítése a hullám feldolgozásának részeként.</p> |
| Raktári munka feldolgozása (az azonosítótábla nyomtatásával együtt)     | Nincs  | <p>Igen, de csak a következő képességekhez:</p><ul><li>Értékesítési kitárolás (az aktív követési dimenziók használata nélkül)</li><li>Értékesítési rakodás (az aktív követési dimenziók használata nélkül)</li></ul> |
| Fürt kitárolása                                              | Nincs  | Nincs |
| Csomagolás feldolgozása                                           | Nincs  | Nincs |
| Kimenő rendezés feldolgozása                                  | Nincs  | Nincs |
| Rakományhoz kapcsolódó dokumentumok nyomtatása                           | Igen | Nincs |
| Fuvarlevél és ASN-generálás                            | Igen | Nincs |
| Szállítás visszaigazolása és csomagjegyzék feldolgozása                | Igen | Nincs |
| Rövid kitárolás (értékesítési rendelések)                                 | Nincs  | Nincs |
| Munka visszavonása                                            | Nincs  | Nincs |
| Munkahelyek módosítása (értékesítési rendelések)                      | Nincs  | Nincs |
| Teljes munka (értékesítési rendelések)                                 | Nincs  | Nincs |
| Munka zárolása és feloldása                                       | Nincs  | Nincs |
| Felhasználóváltás                                                  | Nincs  | Nincs |
| Munka jelentésének nyomtatása                                            | Nincs  | Nincs |
| Hullámcímke                                                   | Nincs  | Nincs |
| Munka sztornírozása                                                 | Nincs  | Nincs |

### <a name="inbound"></a>Bejövő

A következő táblázat bemutatja, hogy mely bejövő funkciók, és hol támogatottak, amikor a raktárkezelési számítási feladatok a felhőalapú és a peremhálózati skálázási egységekben használatosak.

| Feldolgozás                                                          | Központ | WES számítási feladat egy skálázási egységben |
|------------------------------------------------------------------|-----|------------------------------|
| Forrásdokumentum feldolgozása                                       | Igen | Nincs |
| Rakomány és szállításkezelési folyamatok feldolgozása                    | Igen | Nincs |
| Szállítmány visszaigazolása                                            | Igen | Nincs |
| Beszerzési rendelés kiadása a raktárba (raktári rendelés feldolgozása) | Igen | Nincs |
| Beszerzési rendelés – cikk bevételezése és eltárolása                        | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | <p>Igen, mikor van raktári rendelés, és amikor egy beszerzési rendelés nem része egy <i>rakománynak</i>. A betárolás feldolgozásához azonban két mobileszköz menüelemet kell használni, egyet a bevételezéshez (<i>Beszerzési rendelési cikk bevételezése</i>) és egyet engedélyezett <b>Meglévő munka használata</b> beállítással.</p><p>Nem, ha nincs raktári rendelés.</p> |
| Beszerzésirendelés-sor bevételezése és betárolása                        | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | Nincs |
| Visszárurendelés bevételezése és eltárolása                               | Igen | Nincs |
| Vegyes azonosítótábla bevételezése és eltárolása                        | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | Nincs |
| Rakomány – cikk bevételezése                                              | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | Nincs |
| Azonosítótábla bevételezése és eltárolása                              | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | Nincs |
| Átmozgatási rendelés – cikk bevételezése és eltárolása                        | Igen | Nincs |
| Átmozgatásirendelés-sor bevételezése és betárolása                        | Igen | Nincs |
| Munka visszavonása                                                | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | <p>Igen, de a <b>Bevételezés regisztrációjának törlése a munka visszavonásakor</b> beállítás (a <b>Raktárkezelés paraméterei</b> lapon) nem támogatott.</p> |
| Beszerzési rendelés termékbevételezés feldolgozása                        | Igen | Nincs |
| Áttárolási munka létrehozása a bevételezés részeként                 | <p>Igen, ha nincs raktári rendelés</p><p>Nem, ha van raktári rendelés</p> | Nincs |

### <a name="warehouse-operations-and-exception-handing"></a>Raktári műveletek és kivételek kezelése

A következő táblázat bemutatja, hogy mely raktári műveletek és kivételkezelési funkciók, és hol támogatottak, amikor a raktárkezelési számítási feladatok a felhőalapú és a peremhálózati skálázási egységekben használatosak.

| Feldolgozás                                            | Központ | WES számítási feladat egy skálázási egységben |
|----------------------------------------------------|-----|------------------------------|
| Azonosítótábla lekérdezése                              | Igen | Igen                          |
| Cikklekérdezés                                       | Igen | Igen                          |
| Hely lekérdezése                                   | Igen | Igen                          |
| Raktár módosítása                                   | Igen | Igen                          |
| Mozgás                                           | Nincs  | Igen                          |
| Mozgás sablon szerint                               | Nincs  | Igen                          |
| Igazítás ki (be/ki)                                | Igen | Nincs                           |
| Ciklikus leltározás és számbavételi eltérés feldolgozása | Igen | Nincs                           |
| Címke újranyomtatása (azonosítótábla nyomtatása)             | Igen | Nincs                           |
| Azonosítótábla felépítése                                | Igen | Nincs                           |
| Azonosítótábla felbontása                                | Igen | Nincs                           |
| Járművezető bejelentkezése                                    | Igen | Nincs                           |
| Járművezető kijelentkezése                                   | Igen | Nincs                           |
| Köteg intézkedési kódjának módosítása                      | Igen | Nincs                           |
| Nyitott munkalista megjelenítése                             | Igen | Nincs                           |
| Azonosítótáblák egyesítése                         | Nincs  | Nincs                           |
| Tároló eltávolítása csoportból                        | Nincs  | Nincs                           |
| Munka megszakítása                                        | Nincs  | Nincs                           |
| Minimum/maximum feltöltés feldolgozása                   | Nincs  | Nincs                           |
| Időközökre bontott feltöltés feldolgozása                  | Nincs  | Nincs                           |

### <a name="production"></a>Termelés

A termelési helyzetek raktárkezelési integrációja jelenleg nem támogatott a következő táblázatban jelzett módon.

| Feldolgozás | Központ | WES számítási feladat egy skálázási egységben |
|---------|-----|------------------------------|
| <p>A termeléshez kapcsolódó összes raktárkezelési folyamat. Íme néhány példa:</p><li>Kiadás raktárba</li><li>Termelés hullámfeldolgozása</li><li>Nyersanyag kitárolása</li><li>Késztermékek betárolása</li><li>Társ- és melléktermék betárolása</li><li>Kanban betárolás</li><li>Kanban kitárolás</li><li>Termelési rendelés indítása</li><li>Termelési selejt</li><li>Termelés – utolsó raklap</li><li>Anyagfelhasználás regisztrálása</li><li>Üres kanban</li></ul> | Nincs | Nincs |

## <a name="maintaining-scale-units-for-wes"></a>A WES skálázási egységeinek karbantartása

Több kötegelt feladat fut mind a központon, mind a skálázási egységeken.

A központi telepítésben manuálisan karbantarthatja a kötegelt feladatokat. A **Raktárkezelés \> Időszakos feladatok \> Háttérrendszer számítási feladatainak kezelése** részen a következő három feladatot kezelheti:

- Munkaállapot frissítési eseményeinek feldolgozása
- Hullám-végrehajtási vezérlésátviteli események feldolgozása
- Rendelésiforrás-nyugták regisztrálása

A skálázási egységek számítási feladatában a következő két kötegelt feladatot kezelheti a **Raktárkezelés \> Időszakos feladatok \> Számítási feladatok kezelése** részen:

- Hullám táblarekordjainak feldolgozása
- Hullám-végrehajtási vezérlésátviteli események feldolgozása
