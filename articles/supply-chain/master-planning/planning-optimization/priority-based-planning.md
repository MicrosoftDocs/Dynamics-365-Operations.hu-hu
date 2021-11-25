---
title: Prioritásokon alapuló tervezés
description: Ez a témakör a Microsoft prioritáson alapuló tervezési funkcióját ismerteti Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 10/15/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 41c4f3e9bd41735b213743bd8b4cdd8d9657a073
ms.sourcegitcommit: 8cb031501a2b2505443599aabffcfece50e01263
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/09/2021
ms.locfileid: "7777889"
---
# <a name="priority-based-planning"></a>Prioritásokon alapuló tervezés

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

Ez a témakör a Microsoft prioritáson alapuló tervezési funkcióját ismerteti Dynamics 365 Supply Chain Management. A funkció támogatja az igényvezérelt tervezést, amely az igényvezérelt anyagigény-tervezés (DDMRP) egyik lépése. A prioritáson alapuló tervezés lehetővé teszi a tervezési optimalizálás számára, hogy a szükségletdátások helyett tervezési prioritások által vezérelt tervezett rendeléseket generáljon.

A prioritáson alapuló tervezés segítségével fontosság szerint rangsorolhatja a feltöltési rendeléseket, hogy a sürgős igényeket a kevésbé fontos igényekhez igazítja. Például egy készletfeltöltési rendelés prioritása egy normál újratölti feltöltési rendeléshez lesz rendelve. A rendszer automatikusan kisebb rendelésekre bonthatja a nagyobb rendeléseket, ahol a rendeléssorok prioritás szerint vannak csoportosítva. Ezután az összes sürgős rendelést feldolgozhatja előbb.

A funkció gyors áttekintését a következő témakörben talál: A prioritáson alapuló tervezés optimalizálási támogatása a [következőben:Dynamics 365 Supply Chain Management](https://youtu.be/GmMHzFETTQc)

## <a name="turn-on-priority-based-planning-in-your-system"></a>A prioritáson alapuló tervezés bekapcsolása a rendszerben

A funkció használata előtt be kell azt kapcsolnia saját rendszerében. A rendszergazdák használhatják a [funkciókezelési](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat a funkció állapotának ellenőrzéséhez, és bekapcsolásához. A **Funkció kezelése** munkaterületen a funkció a következő módon van listázva:

- **Modul:** *Alaptervezés modul*
- **Funkció neve: A tervezés optimalizálása során a prioritás által** *vezérelt MRP-támogatás*

## <a name="where-and-how-planning-priorities-are-assigned"></a>A tervezési prioritások hozzárendelésének helye és hogyan

*A tervezés prioritási adatai a prioritáson alapuló tervezés* alapját alkotják. A tervezési prioritás meghatározza az igények vagy ellátási sorok fontosságát. A tervezési optimalizálás akkor használja, ha **a Fedezetkód** mező beállítása *·* Prioritás.

A tervezési prioritás általában 0 (nulla) és 100 közötti szám, amelyben a 0 a legnagyobb fontosság. Megjelenik és be van állítva a Tervezés **prioritás** mezőben. Ez a mező a következő lapokon található: Igény-előrejelzési **·** sorok, Értékesítési **rendelés** részletei, **Beszerzési rendelés** részletei, **Átátviteli** **·** rendelés részletei és Tervezett rendelés részletei.

Ha a megfelelő cikk vagy fedezetcsoport Fedezeti kód mezője prioritásra van állítva, akkor a tervezés optimalizálása az igényalapú megközelítést alkalmazva kezeli a készletet a tervezési prioritás kiszámítása során, és minden egyes kiadott terméknél figyelembe veszi a Cikkfedezeti lap Minimális, Újrarendelési pont és Maximális mező **·** *·* **·** **·** **·** **·** értékeit.

> [!NOTE]
> A Prioritás értéke csak akkor érhető el a Fedezeti kód mezőben, ha engedélyezve van *·* a Tervezési **·** optimalizálás funkció.

A kapcsolódó tervezési prioritási modellek a tervezési prioritást és a tervezett rendelések *·* felosztását szabják prioritástartomány szerint. Ezenkívül beállíthatók az egyes ellátási és igénytípusú alapértelmezett tervezési prioritási értékek, valamint beállítható a prioritás számítási módja.

## <a name="types-of-priority-calculation-methods"></a>Prioritásszámítási módok típusai

Minden tervezési prioritási modellhez egy Prioritás számítási mód beállítása van meg adni, amely meghatározza, hogy az alaptervezés hogyan alkalmazza a prioritást a **·** tervezett rendelésekre. A rendelkezésre álló értékek a *maximális készletmennyiség százaléka és* a *prioritási tartományok* százaléka. *A prioritástartományok a maximális készletmennyiség* százalékának módszerének egy speciális *verzióját* képviselik.

### <a name="percent-of-maximum-inventory-quantity"></a>A maximális készletmennyiség százaléka

A maximális készletmennyiség százalékának számítási módszerében az ellátási prioritás számítása az aktuális teljes rendelkezésre álló *·* *·* készletet (nettó folyamot) a cikkhez beállított maximális készletmennyiség százalékos értékeként **·** találja meg. A program ekkor cikkenként és szállítónként egyetlen tervezett rendelést hoz létre (kivéve ha a maximális rendelési mennyiség alapján a felosztást kényszerítik). A rendelés tervezési prioritásának számítása a maximális érték százalékos értékeként történik.

A konvertálás az alábbi képlet alapján történik:

*Maximum százaléka* = (nettó áramlási pozíció × *·* 100) ÷ maximális készletmennyiség-érték a *cikkfedezetből*

Ebben a képletben *a nettó áramlási pozíció* számítása a következőképpen történik:

*Nettó áramlási* = *pozíció -* + *megrendelt* - minősített *igény*

- *A* megrendelt készlet a várt készlet.
- *A minősített igény a tervezési időkorláton belüli szükségletdátummal* rendelkező nettó követelményeket jelöli.

Az alaptervezés futtatása során új tervezett rendelések létrejönnek, ha a nettó áramlási pozíció kisebb, mint a cikk újrarendelési pontjának mennyisége. A tervezett rendelési mennyiség a cikkszinten beállított maximális készletmennyiség és a nettó **·** áramlási pozíció közötti különbség. A tervezett rendelés prioritásának számítása a maximális készletmennyiség százalékos nettó áramlási *·* **pozíciója** alapján történik.

> [!NOTE]
> A számított prioritás nem lehet negatív, még akkor sem, ha az igény meghaladja a teljes készletet. Ha az igény meghaladja a teljes készletet, a számított prioritás 0 (nulla) lesz.

### <a name="priority-ranges"></a>Prioritási tartományok

A Prioritástartományok számítási módja speciálisabb, mint a maximális készletmennyiség százaléka módszer, és a tervezési prioritási modell *·* szintjén van *·* konfigurálva. Több új tervezett ellátási rendelés is létre lehet hozva a cikkenkénti igény kielégítése érdekében. A tervezett ellátás prioritásai a Tervezési prioritási modellek lap Tervezési prioritástartományok rácsában megadott értékeken vannak **·** **·** megadva.

A következő további szabályok lépnek hatályba, ha a Prioritás számítási mód mező **·** beállítása *·* Prioritástartományok:

- Ha a tervezett prioritási modell Igény prioritásának figyelembe veése beállítás Igen, az egyes igénysorok prioritása a prioritástartomány-korhatárt **·** *·* korlátozza. Az új tervezett rendelések prioritása nem lesz kisebb az igény prioritásában. A tartomány felső értéke az igény prioritási értékének összevetése során meghatározott küszöbértéknek számít. Ha az igény prioritása pontosan a két tartomány felső küszöbértéke közé esik, akkor a legmagasabb prioritású (azaz a legalacsonyabb prioritású) tartomány lesz kiválasztva.
- Ha a tervezett prioritási modell Tervezett rendelés létrehozása mezőjének beállítása Egyszeres ellátás, a legfontosabb prioritással, akkor csak egy ellátás jön létre, hogy az összeset a maximális értékig teljesíteni **·** *·* kell. A prioritás az ellátás indítóját indító első tartomány prioritása lesz.
- Ha nincs aktuális készlet, nincs készlet és nincs igény, akkor a Rendszer a Tervezési prioritástartományok rácsának nulla értéket ad meg, ahol a Forrásmennyiség mezőben a Nulla érték **·** van **·** *·* beállítva.
- Ha van igény, de nincs aktuális készlet vagy várható készlet, akkor a Rendszer a Tervezési prioritástartományok rácsának nulla vagy annál kisebb értéket ad **·** **·** *·* meg.
- Amikor a rendszer kiértékeli az igény részét képezi tartományt, az Igény prioritásának figyelembe venni beállításának hatása akkor is **·** lesz.

## <a name="differences-between-traditional-timeline-calculations-and-priority-based-planning"></a>A hagyományos idősorszámítások és a prioritáson alapuló tervezés közötti különbségek

A prioritáson alapuló tervezés a következőképpen különbözik a hagyományos idősorszámítástól:

- Még mindig érvényben van minden normál előzetes feldolgozó. Az előfeldolgozók közé tartozik a jóváhagyott tervezett rendeléseknek az értékesítési igényekkel, a beszerzési igénylések megfeleltetésével és a foglalási logikával szembeni igénykeresése. A rendszer csak olyan igényt feldolgoz, amelyet ezek az előfeldolgozók nem elégít ki.
- Az előkeresés során minden készletet figyelembe kell venni, függetlenül attól, hogy mi a prioritása. Ez a készlet tartalmazza az aktuális készletet, a kiadott készletet és a jóváhagyott tervezett rendelések nem tervezett részét.
- A "negatív napok" igényt nem lehet a teljes fedezeti idő alatt a készlethez ellenében visszaigénylni.
- Ha a készletet igény szerint kezelik, akkor a legmagasabb prioritású készletet (azaz a legalacsonyabb prioritású értéket) használja fel a rendszer. Az készlet prioritási értéke 0 (nulla). Ebből következően ez lesz az első forrás.
- Az új tervezett ellátási sorok a minimális rendelési méretre, maximális rendelési méretre, mennyiség többszörösére stb. vonatkozó rendszeres szabályok szerint lesznek létrehozva.

## <a name="planning-priority-models"></a>Tervezési prioritási modellek

*A tervezési prioritási* modellek fedezetcsoportokhoz vannak rendelve, és a tervezett rendelések tervezési prioritását szabályozják. Ezek határozzák meg azt a logikát, amely meghatározza a tervezési prioritás értékének számítását az egyes tervezett rendeléseknél, valamint azt, hogy hogyan kell hozzárendelni a prioritást a tervezett rendelésekhez, ellátási sorokhoz és igénysorokhoz.

A tervezési prioritási modellekkel való munkához menjen az Alaptervezés – Beállítástervezés **\>\> prioritási modelljeihez.** Mint korábban már említettük, a modellek egyik legfontosabb beállítása a **Prioritásszámítási módszer** értéke. Ez a beállítás szabályozza azt a számítási módszert, amely akkor használatos, amikor az alaptervezés prioritási értéket rendel a tervezett rendelésekhez.

> [!NOTE]
> A tervezési prioritási modellek az egész szervezetre érvényesek minden jogi személynél.

### <a name="coverage-group"></a>Fedezeti csoport

Állítson be egy új fedezetcsoportot, amely a prioritáson alapuló tervezéshez használható, a cikkek fedezeti szabályainak [definiálása leírtak](../tasks/define-coverage-rules-items.md) szerint. Miután létrehozta a fedezeti csoportot, állítsa be a következő további mezőket:

- **Fedezeti kód – akkor válassza a Prioritás lehetőséget, ha a fedezeti csoport** *·* prioritáson alapuló tervezést használ.
- **Tervezési prioritási** modell – válasszon ki minden szervezeti szintű tervezési prioritási modellt.

### <a name="item-coverage"></a>Cikk fedezete

A cikkfedezeti beállítások megadása a Fedezeti [beállításoknál leírtak](../coverage-settings.md) szerint. Alapértelmezés szerint a fedezeti csoporthoz kiválasztott fedezeti kód értékét másolja a rendszer **·** a cikkfedezeti beállításokba. Szükség esetén azonban felülbírálhatja az alapértelmezett értéket. Bizonyos esetekben egy cikkfedezeti rekord Fedezeti kód mezője a Tervezés beállításra van állítva, de a kapcsolódó fedezeti csoporthoz nincs megadva tervezési **·** *·* prioritási modell. Ebben az esetben minden olyan modell, ahol a Prioritásszámítási módszer mező beállítása a maximális készletmennyiség százaléka, és a Tervezett rendelés létrehozása mezőben az Egy ellátás a legfontosabb prioritással van beállítva, alapértelmezés szerint az Egyedi készlet beállítás **·** van *·* **·** *·* beállítva.

A **Fedezetkód mező prioritásának beállítása, hogy a cikkfedezeti beállítások között elérhetővé tegye az Újrarendelési** *pont* **·** mezőt. Ebben a mezőben adja meg az újrarendelésipont-mennyiséget, amit a rendszernek használnia kell, amikor meghatározza, hogy mikor helyezze el a prioritás fedezeti kódértékkel megadott tervezett **·** *·* rendeléseket.

Az újrarendelésipont-mennyiséget gyakran számítják ki igényként az átfutási idő alatt plusz egy minimális érték (biztonsági készlet). A minimális és a maximális értékek közötti **·** **értéknek kell** lennie.

Például a következő módon állíthatja be a mezőket:

- **Minimum:** *10*
- **Újrarendelési pont:** *45*
- **Maximum:** *60*

Ebben a példában az újrarendelésipont-mennyiség egy hét napos átfutási időn alapul, és az átlagos napi felhasználás 5. Emiatt az átfutási idő alatt az igény 35. A minimális érték (biztonsági készlet) ezután hozzáadódik 45-ös újrarendelési ponthoz. Ha ezt a beállítást használja, a program a készletet javasolja, ha az tervezett készletszint 45 alatti. A rendelés prioritása a tervezési prioritás beállításán fog alapulni.

### <a name="manage-planning-priority-models"></a>Tervezési prioritási modellek kezelése

A tervezési prioritási modellekkel való munka. Hajtsa végre ezeket a lépéseket.

1. Ugrás az **Alaptervezés \>\> beállítástervezésének prioritási modelljeihez.**
1. Válasszon ki egy meglévő modellt a listaablakban, vagy az Új gombra a **·** munkaablakban új modell létrehozásához.
1. A rekord fejlécen állítsa be a következő mezőket:

    - **Név** – adja meg a modell nevét. A névnek egyedinek kell lennie a szervezet összes jogi személyére vonatkozóan.
    - **Leírás** – adja meg a modell leírását.
    - **Prioritásszámítási** módszer – válasszon a következő értékek közül:

        - *Prioritástartományok – ha ezt az* értéket választja, elérhetővé válik a Tervezési **·** prioritástartományok rács. Itt több prioritási tartományt kell létrehozni a tervezési prioritás értékének meghatározásához.
        - *Maximális készletmennyiség százaléka – a tervezési prioritás értékének számítása százalékos hányadként, a maximális készletmennyiségre vonatkozó, tervezett* készletszint alapján.

    - **Tervezett rendelés létrehozása – ez a mező akkor érhető el, ha a Prioritás számítási mód mező** **beállítása** *·* Prioritástartomány. Válasszon a következő értékek közül:

        - *Egyetlen ellátás a legfontosabb prioritással – ne ossza fel a tervezett rendeléseket* a prioritási tartomány alapján. A tervezett rendelés tervezési prioritása a legfontosabb prioritási tartományon alapul (ez a legkisebb tervezési prioritás értéke).
        - *Felosztás prioritási tartományok szerint – az igény felosztása több tervezett rendelésre a tervezési* prioritási tartományok alapján. Az egyes tervezett rendelések tervezési prioritását a kapcsolódó tervezési prioritási tartomány tervezési prioritása határozza meg.

    - **Fontolja meg az igény prioritását – a készlethez létrehozott új tervezett rendelések prioritásának korlátozásához állítsa** *Igen* beállításra ezt a beállítást. (A prioritás nem lesz alacsonyabb, mint a kapcsolódó igény prioritása.) Ha Nem beállításra adja meg ezt a beállítást, az ellátási rendelés prioritásának számítása során a program nem kezeli az igényrendelés *·* prioritását.

1. Ha a Prioritás számítási mód mezőjét Prioritástartományok beállításra adja meg, a Tervezési prioritástartományok gyorsét tartalmazó eszköztár Hozzáadás és eltávolítás gombjaival adja hozzá vagy távolítsa el a prioritási tartományok sorait a kívánt **·** *·* **·** **·** **·** módon. Ha több sor létezik, és új sort szúr be, a tervezési prioritás automatikusan a kijelölt sor átlagára és a sor fölötti sorra lesz állítva. Az egyes sorokhoz állítsa be a következő mezőket:

    - **Tervezési prioritás** – adjon meg egy 0,00 és 100,00 közötti értéket. Ez az érték jelöli a sorhoz használt tervezési prioritást. A legalacsonyabb prioritású érték jelenti a legmagasabb prioritást. A program egy alapértelmezett értéket kap, de szükség esetén módosíthatja. Ugyanannak a tervezési prioritási modellnek több tervezési prioritási tartományában nem használható ugyanaz a **·** Tervezési prioritás értéke.
    - **Leírás – adja meg a tervezési prioritási tartomány** leírását (például Újrarendelési pont a *·* maximumra).
    - **Mennyiség alsó határa – a tervezési prioritás** tartományának alsó határa. Ez az érték csak olvasható, és az előző tervezési prioritástartomány célmennyiségének és Százalékos mennyiségértékének **·** az **·** alapja.
    - **Mennyiség felső határa – jelölje ki a mezőt a cikkfedezetből, amely a tartomány felső** határának meghatározásához szükséges. A következő értékek támogatottak, amelyek befolyásolják a következő tartományból származó **·** mennyiség értékét:

        - *Nulla – ez az érték negatív vagy nulla (nulla vagy nullánál* *·* kisebb) értéket *·* jelent. Olyan sorok esetén, ahol ez az érték be van jelölve, a Mennyiség százaléka mező írásra olvasható, és mindig **·** *100 százalékra* van állítva.
        - *Minimális készletmennyiség – ez az érték a cikk minimális értékét jelenti* **a** Cikkfedezet **·** lapon. Az olyan soroknál, ahol ez az érték be van jelölve, szerkeszthető a Mennyiség százaléka mező, és a következő tartományból származó mennyiség értékének beállításában használatos (például a minimális készletmennyiség **·** **·** *80%-a).*
        - *Újrarendelési pont – ez az érték a cikk cikkfedezeti lapján található újrarendelésipont-értéket* **·** **·** jelöli. Olyan sorok esetén, ahol ez az érték be van jelölve, a Mennyiség százaléka mező szerkeszthető, és a következő tartományból származó mennyiség értékének beállításában használatos (például az Újrarendelési pont **·** **·** *80%-a).*
        - *Maximális készletmennyiség – ez az érték a cikk maximális értékét jelenti* **a** Cikkfedezet **·** oldalon. Az olyan soroknál, ahol ez az érték be van jelölve, a Mennyiség százaléka mező szerkeszthető, és a következő tartományból származó mennyiség beállításában használatos (például a Minimális készletmennyiség **·** **·** *80%-a).*
        - *Végtelen – ez az érték a tartomány végtelen felső szintjét jelöli ( Végtelen vagy* *·* kevesebb, mint *·* Végtelen). Olyan sorok esetén, ahol ez az érték be van jelölve, a Mennyiség százaléka mező írásra olvasható, és mindig **·** *100 százalékra* van állítva.

    - **Mennyiség százaléka – adja meg azt a százalékértéket, amely alapján a rendszer kiszámítja a tervezési prioritási tartomány felső határát, a Cél mennyiség mezőben** **kiválasztott érték** alapján. Ha például a Cél mennyiség mező a Minimális készletmennyiség, és a Mennyiség százaléka mező **·** *·* **·** *50-re van* állítva, akkor a felső határ a kapcsolódó cikkfedezetből származó minimális készletmennyiség 50 százaléka lesz.

1. A Tervezési prioritás alapértelmezései gyorsjelentésben állítsa be a mezőket az egyes ellátás- és igénysorok (értékesítési rendelés, beszerzési rendelés, átátviteli rendelés vagy igény-előrejelzés) alapértelmezett tervezési prioritásainak **·** meghatározásához. Csak pozitív értékeket lehet megadni.

## <a name="view-and-maintain-planning-priority"></a>Tervezési prioritás megtekintése és karbantartása

A tervezési prioritás megjelenik és be van állítva a Tervezés **prioritás** mezőben. Ez a mező az alábbi táblázatban felsorolt lapokon található. A prioritás 0 (nulla) és 100 közötti számként van beállítva, itt a 0 a legnagyobb fontosság.

| Oldal | Mező helye | Érték forrása |
|---|---|---|
| Igény-előrejelzés sorai | <p>**Cikk** lap</p><p>(Válasszon egy sort a felső szakaszban, majd válassza ki a **Cikk** lap.)</p> | Alapértelmezett érték vagy manuálisan beállított érték |
| Értékesítési rendelés részletei | <p>**Szállítás** lap a Sor részletei **·** gyorslapon</p><p>(Válasszon egy sort **a Értékesítésirendelés-sorok gyorslapja, majd a Sor részletei gyorslapon** **válassza a Szállítás** **·** lapot.)</p> | Alapértelmezett érték, vállalatközi érték vagy manuálisan beállított érték |
| Beszerzési rendelés részletei | <p>**Szállítás** lap a Sor részletei **·** gyorslapon</p><p>(Válasszon egy sort **a Beszerzésirendelés-sorok gyorslap, majd a Sor részletei gyorslapon** **válassza a Szállítás** **·** lapot.)</p> | Tervezett rendelésekből, vállalatközi értékből származó értékből vagy manuálisan beállított értékből származó érték |
| Átátviteli rendelés részletei | <p>**Szállítás** lap a Sor részletei **·** gyorslapon</p><p>(Válasszon egy sort **a Átátvitelirendelés-sorok gyorslapja, majd a Sor részletei gyorslapon** **válassza a Szállítás** **·** lapot.)</p> | A tervezett rendelésekből való visszakorrakodás során beállított érték vagy manuálisan beállított érték |
| Tervezett rendelés adatai | **Általános** gyors gyorsab | Az alaptervezés során kiszámított érték vagy a manuálisan beállított érték |

### <a name="intercompany-trade"></a>Vállalatközi kereskedelem

A vállalatközi ellátás- és igénysorok Tervezési prioritás értéke meg van osztva **·** a kapcsolt entitások között. A módosítás mindkét oldalon megjelenik a kapcsolt rendeléssoron.

Íme néhány példa:

- A felhasználó 20-ról 30-ra módosítja egy vállalatközi értékesítési rendelési sor tervezési prioritását. Ez a módosítás megjelenik a kapcsolt vállalatközi beszerzésirendelés-sorban.
- A felhasználó 40-ről 50-re módosítja egy vállalatközi beszerzési rendelési sor tervezési prioritását. Ez a módosítás megjelenik a kapcsolt vállalatközi értékesítésirendelés-sorban.
