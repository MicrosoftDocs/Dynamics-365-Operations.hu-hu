---
title: Korlátozott eltarthatósági időű termékek alaptervezése
description: Ez a témakör azt ismerteti, hogyan lehet olyan tervezési funkciókat beállítani és használni, amelyek figyelembe veszik a ásható termékek eltarthatóságát.
author: t-benebo
ms.date: 08/10/2022
ms.topic: article
ms.search.form: ReqPlanSched, CustTable, EcoResProductDetailsExtended, InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-08-10
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 95c905cbcc3c057dbccf2b7d6e894b1e99ddfba5
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337355"
---
# <a name="master-planning-for-products-with-limited-shelf-life"></a>Korlátozott eltarthatósági időű termékek alaptervezése

[!include [banner](../../includes/banner.md)]

Az eltarthatósági idő az az időtartam, amely alatt a termék tárolható addig, amíg a terméket fel nem lehet használni vagy el nem lehet adni. A korlátozott eltarthatóságú termékek esetén valószínűleg az első lejárati, elsőként ki (FEFO) raktári stratégiát kell használni, amely a hátralévő eltarthatósági idő alapján fontossági sorrendet határoz meg a cikkek felhasználásáról és eladásáról. Ez a raktárstratégia az élelmiszerre, gyógyszerekre és egyéb árukra jellemző, rövid tárolási időre jellemző. A FEFO szerint a raktárban a raktárban található cikkeket például a szupermarketek polcain tárolják: a hosszú eltarthatósági időű termékeket a polcok mélyebbre helyezik, így a rövidebb eltarthatósági időű termékeket előbb szállítják ki.

## <a name="using-shelf-life-in-master-planning"></a>Eltarthatóság használata az alaptervezésben

Ez a szakasz bemutatja, hogy az alaptervezés hogyan javasolja az eltarthatósági idő készletét.

Az alapterv futtatásakor a program olyan javasolt tervezett rendeléseket (készleteket) hoz létre, amelyek kielégítik az igényt, és minimális késedelmet okozhatnak. Ha a terv olyan cikkeket is tartalmaz, amelyekhez korlátozott eltarthatósági idő tartozik, a tervezési számítások összetettebb lesz, mivel a terv nem elég csak minimális késésre, hanem a meglévő készlet használatára is, még a lejárat előtt. A tervnek a lejárati dátumhoz legközelebb eső készletet kell használnia ahhoz, hogy a készlet később lejárjon. Az alaptervezés tehát a következő célokat keresi, ebben a sorrendben:

1. A késések összegének minimálisra csökkentése.
1. A FEFO-készlet teljes összege.
1. A készlet feltöltésének minimálisra csökkentése.

Bizonyos esetekben ütközés áll fenn az első két cél között, és választani kell: késleltetni szeretne egy szállítmányt, vagy olyan készletet szeretne használni, amely később lejár, nem pedig a szállítás hamarabb jár le? Az alaptervezés során fel kell oldania ezt az ütközést, mert a rendszer prioritási sorrendbe ássa a késedelmeket a hamarosan lejáró készlet alkalmazásával. Az ilyen típusú ütközések általában akkor fordulnak elő, ha késés és fedezet időszak szerint alakul ki. Ezért javasoljuk, hogy olyan fedezeti időszakot használjon, amely rövidebb, mint egy cikk eltarthatósági ideje. A fedezet egyéb típusai (például a követelmények) nem valószínű, hogy ilyen típusú ütközéseket észleltek.

## <a name="set-up-shelf-life"></a>Eltarthatóság beállítása

### <a name="configure-each-master-plan-to-consider-shelf-life"></a>Az egyes alaptervek konfigurálása az eltarthatósági idő figyelembe vennie

Alapértelmezés szerint az alaptervek nem veszi figyelembe az eltarthatósági értéket. A következő eljárás szerint engedélyezze az eltarthatósági számításokat minden olyan alaptervhez, amely megköveteli.

1. Ugrás az Alaptervezés **beállítási \> terveihez \>.\>**
1. Válasszon ki egy meglévő tervet a listaablakban, vagy hozzon létre egy újat.
1. Az Általános **gyorsététen állítsa Az eltarthatósági** dátumok használata **lehetőséget Igen beállításra** *.*

### <a name="configure-tracking-dimension-groups-to-track-the-batch-dimension"></a>Nyomon követési dimenziócsoportok konfigurálása a kötegdimenzió nyomon követéséhez

Egy cikk eltarthatósági idő csak akkor követhető nyomon, ha a cikk nyomon követése a kötegdimenziónál történik. Más szóval a köteghivatkozást és a szükséges dátumokat a bevételezéskor vagy a gyártás során, valamint a cikk minden készlettranzakciójával rögzíteni kell. A beállítás kezeléséhez állítson be egy vagy több nyomon követési dimenziócsoportot a szükséges követéshez, majd szükség szerint rendelje a megfelelő cikkeket ezekhez a csoportokhoz.

A következő eljárás szerint állítson be egy nyomon követési dimenziócsoportot a kötegdimenzió nyomon követésére.

1. Ugrás a Termékinformáció-kezelés **beállítási \> dimenziója \> és a Nyomon követési dimenziócsoportok \> változatcsoporthoz**.
1. Tegye a következők egyikét:

    - A műveletpanel új nyomon követési dimenziócsoportjának **létrehozásához válassza az Új** lehetőséget. Írjon be egy nevet és egy leírást, majd válassza a Mentés **a** munkaablakban lehetőséget.
    - A listaablakban válassza ki a létező nyomon követési dimenziócsoportot, amely a kötegdimenzió nyomon követésére van beállítva.

1. A Nyomon követési **dimenzió gyorslap** Kötegszám sorában **jelölje** **be** a jelölőnégyzeteket az Aktív és a Tényleges készlet oszlopban **.**

### <a name="set-up-shelf-life-for-a-product"></a>Eltarthatósági idő beállítása egy termékhez

A következő eljárás szerint lehet beállítani a termékek eltarthatóságát.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Hozza létre vagy nyissa meg a beállítani kívánt terméket.
1. Az eltarthatósági beállítások **alkalmazáshoz** az Általános gyorslapon állítsa a Nyomon követési dimenziócsoport mezőt egy nyomon követési dimenziócsoportra, **amely** be van állítva a kötegdimenzió nyomon követésére. Ez a mező csak akkor állíthatja be, ha először hoz létre terméket. Nem módosíthatja a meglévő termékek értékét.
1. Állítsa be **a** következő mezőket a Készlet gyorsmezők kezelése területen:

    - **Ajánlott eltarthatósági** idő napokban – adja meg azt az időszakot (napokban meg), amellyel ellenőrizni kell a termék egy kötegét annak érdekében, hogy az alkalmas legyen felhasználásra vagy újraértékesítésre. Az ajánlott eltarthatósági dátum meghatározásához a program hozzáadja ennek a mezőnek az értékét *a* *köteg gyártási dátumára.* Beállítható, hogy a rendszer minőségi rendeléseket generáljon, amikor egy köteg az ajánlott eltarthatósági dátumhoz közeledik.
    - **Eltarthatósági idő napokban** – adja meg, hogy hány nap után jár le a termék egy kötege. Ez az érték a gyártási *dátumhoz hozzáadva meghatározható* a lejárati *dátum*. A köteg e dátum után használhatatlannak minősül.
    - **Napokban megadott** legjobb időszak – adja meg azt az időszakot (napokban), amelynek után a termék egy kötege eladhatónak minősül, de az eredeti tulajdonságai egy része már nem tartható vissza. Ez az érték a gyártási *dátumhoz hozzáadva* meghatározható a *lehető legjobb dátum*. A jelentéseket a legjobbnál korábbi dátumú készlet azonosítására futtathatja. 

### <a name="set-a-sellable-days-rule-for-each-customer"></a>Árusítás napjaira vonatkozó szabály beállítása minden vevőre

*Az Árusítás napjai* funkció gondoskodik arról, hogy egy kötegből, amely hamarosan lejár, ne küldi el a rendszer a vevőknek. Ezenfelül gondoskodik arról, hogy a termékeknek a vevőnek történő elszállítás után is megfelelő számú árusítható nap maradjon a szállítás után is.

Az árusítás napjai funkció használatához meg kell határoznia az egyes vevőkre (vagy termékcsoportra) vonatkozó árusítható napok számát. Ezt a folyamatot manuálisan kell végrehajtania, mert nincs hozzá adatentitás.

A következő eljárás szerint állíthatja be az egyes vevőkhöz az egyes termékek árusítható napjait.

1. Lépjen az **Értékesítés és marketing \> Vevők \> Összes vevő** menüpontba.
1. Keresse meg és válassza ki a beállítani kívánt vevőt.
1. A műveletpanel Értékesítés **lapján**, a **Beállítás csoportban** **\> válassza az Árusítási napok beállítását**.
1. A vevői **oldalon található Árusítás napok** lapon a rács felsorolja az egyes termékekre vagy termékcsoportra vonatkozó, az árusítható napokra vonatkozó szabályokat. A munkaablak gombjaival szükség szerint adhat hozzá és szerkeszthet sorokat a rácsban. A **meglévő** sorok megkeresésében szűrő található.
1. Az egyes sorokhoz állítsa be a következő mezőket:

    - **Cikk-kód** – a következő értékek egyikének kiválasztásával adja meg az érintett cikkek hatókörét:

        - *Tábla* – a sor egy adott cikkre vonatkozik.
        - *Csoport* – a sor egy adott cikkcsoportra vonatkozik.
        - *Mind* – a sor az összes cikkre vonatkozik.

    - **Cikk-kapcsolat** – ha Tábla **beállításra** *adja* meg a Cikkkód mezőt, válasszon ki egy cikket. Ha a Cikkkód mező **beállítása** Csoport *·*, válasszon egy cikkcsoportot. Ha a Cikkkód mező **beállítása** Mind *·*, ez a mező nem érhető el.
    - **Árusítás napjai** – adja meg azt a minimális számú napot, amely alatt a vevőnek egyező termékeket kell értékesítenie, mielőtt a köteg lejár. Az árusítás napjainak értéke az értékesítési rendelésben egyeztetett termékek kért kézhezvételi dátumán (vagy a visszaigazolt kézhezvételi dátumon) alapul.
    - *(Egyéb termékdimenziók)* – egy sor hatókörének további korlátozása érdekében szükség szerint adjon meg más dimenzióértékeket is (**·** **például** Méret és Szín). A rácsban megjelenő dimenziók **beállításához válassza a Dimenziók megjelenítése** a munkaablakban lehetőséget.

### <a name="set-up-all-relevant-products-so-that-they-are-fefo-date-controlled"></a>Állítsa be az összes kapcsolódó terméket úgy, hogy FEFO dátumvezéreltek legyen.

Az árusítás napjainak munkához való beállítása esetén minden érintett cikknek egy olyan cikkmodellcsoporthoz kell tartoznie, amelyben be van jelölve a **FEFO** dátumvezérelt jelölőnégyzet.

A következő eljárás szerint lehet beállítani egy cikkmodellcsoportot, hogy az támogatja az Árusítás napok funkcióját.

1. Ugorjon a **Készletkezelés \> Beállítás \> Készlet \> Cikkmodellcsoportok** pontra.
1. Válasszon ki egy meglévő csoportot a listaablakban, vagy hozzon létre egy újat a **munkaablak** Új beállításával.
1. A Készlet házirendek **gyorsában** jelölje be a **FEFO** dátumvezérelt jelölőnégyzetet.
1. Szükség szerint állítsa be a csoport további mezőit.

A következő eljárás szerint lehet megtekinteni vagy beállítani azt a cikkmodellcsoportot, amelyhez a termék tartozik.

1. Kattintson a **Termékinformációk kezelése \> Termékek \> Kiadott termékek** lehetőségre.
1. Nyissa meg a vizsgálni vagy szerkeszteni kívánt terméket.
1. Állítsa a **Cikkmodellcsoport** **mező** beállítását az Általános gyorsgombra, ha a **FEFO** dátumvezérelt jelölőnégyzet be van jelölve.

## <a name="example-1-simple-fefo-10-day-period-zero-days-of-lead-time"></a>1. példa: egyszerű FEFO, 10 napos időszak, nulla nap átfutási idő

A példa az eltarthatóságra egy alapvető példát mutat be, amelyben az ellátási rendelések és a igények közötti igényigény a rendszer következő céljainak kielégítése érdekében történik:

- A késések összegének minimálisra csökkentése.
- A FEFO-készlet teljes összege.
- A készlet feltöltésének minimálisra csökkentése.

A rendszer a következő cikk- és alapterv-beállításokat tartalmazza:

- **Fedezetkód (feltöltési stratégia):** időszak 
- **Fedezeti időszak:** 10 nap (az eltarthatósági időnek megfelelő)
- **Eltarthatósági idő:** 10 nap
- **Árusítás napjai:** 0 nap
- **Átfutási idő:** 0 nap
- **Negatív napok:** 0 nap
- **Tervezett rendelés típusa (a cikk alapértelmezett rendelési beállításai):** Beszerzési rendelés

A rendszerben a cikkhez a következő értékesítési rendelések léteznek:

- **SO1:** Mennyiség (mennyiség) = 2, kért szállítási dátum = ma + 1 nap
- **SO2:** Mennyiség = 1, kért szállítási dátum = ma + 4 nap
- **SO3:** Mennyiség = 1, kért szállítási dátum = ma + 5 nap

Ezek az értékesítési rendelések a cikk iránti igényt hoznak létre.

A cikkből a következő készlet áll rendelkezésre:

- **Aktuális készlet:** mennyiség = 1, lejárati dátum = ma + 5 nap
- **1. beszerzési rendelés (PO1):** Bevételezési dátum = ma + 2 nap, mennyiség = 1, lejárati dátum = ma + 4 nap

A rendszer létrehozza az igénynek megfelelő készletlistát, és a listát lejárati dátum szerint rendezi (FEFO szerint).

Az alaptervezés létrehozza a szükséges igényigényt a készlet és az igény között. Ezenkívül az ellátási lista alapján létrehoz minden szükséges igényt (a FEFO segítségével), és figyelembe veszi az elérhetőség dátumát.

- Az SO1 az aktuális készlet mennyiséggel teljesítható, de az 1. beszerzési rendelésen nem teljesítható, mert az 1. beszerzési rendelés elérhetőségi dátuma egy nappal az SO1 által megköveteltnél egy nappal későbbi. Emiatt az SO1 egy termékegység iránti igényt generál.
- Az SO2 fedezhető az 1. beszerzési rendelésen, mivel az 1. beszerzési rendelés a kért időponttól fog érkezni, és a lejárati dátum továbbra is érvényes lesz. Emiatt az SO2 követelményt teljes egészében az 1. beszerzési rendelés fedezi.
- Az SO3 nincs fedezve, mert az erőforrások nem érhetők el. Emiatt az SO3 egy cikkegységre generálja a igényt.

Ahhoz, hogy minden fennmaradó követelmény fedezve legyen, a rendszernek létre kell hoznia a következő tervezett beszerzési rendelést:

- **PPO1: Bevételezési** dátum = ma, mennyiség = 2, lejárati dátum = ma + 10 nap

A következő táblázat összefoglalja az eredményt.

| Igény | Igénykövetés |
|---|---|
| **SO1: Szállítási** dátum = ma + 1 nap, mennyiség = 2 | <p>**Aktuális mennyiség:** mennyiség = 1, lejárati dátum = ma + 5 nap</p><p>**PPO1: Bevételezési** dátum = ma, mennyiség = 1, lejárati dátum = ma + 10 nap</p> |
| **SO2: Szállítási** dátum = ma + 4 nap, mennyiség = 1 | **1. beszerzési rendelés:** kézhezvételi dátum = ma + 2 nap, 1 mennyiség, lejárati dátum = ma + 4 nap |
| **SO3: Szállítási** dátum = ma + 5 nap, mennyiség = 1 | **PPO1: Bevételezési** dátum = ma, mennyiség = 2, lejárati dátum = ma + 10 nap |

A következő ábra a példában szereplő időrendet mutatja be.

![1. példa: egyszerű FEFO, 10 napos időszak, nulla nap átfutási idő.](media/fefo-example-1.png "1. példa: egyszerű FEFO, 10 napos időszak, nulla nap átfutási idő")

## <a name="example-2-simple-fefo-requirement-three-days-of-lead-time"></a>2. példa: egyszerű FEFO, követelmény, három napos átfutási idő

A példa azt mutatja be, hogy a rendszer hogyan próbálja meg minimálisra csökkenteni a késéseket, ami időnként túlrendelést is okozhat.

A rendszer a következő cikk- és alapterv-beállításokat tartalmazza:

- **Fedezetkód (feltöltési stratégia):** követelmény
- **Eltarthatósági idő:** 10 nap
- **Árusítás napjai:** 0 nap
- **Átfutási idő:** A következő szállítói kereskedelmi megállapodások alapján jött létre:

    - **1. kereskedelmi megállapodás:** Ha a mennyiség = 1, az átfutási idő = 4
    - **2. kereskedelmi megállapodás:** Ha a mennyiség = 2, az átfutási idő = 3

- **Negatív napok:** 0 nap
- **Tervezett rendelés típusa (a cikk alapértelmezett rendelési beállításai):** Beszerzési rendelés

A rendszerben a következő értékesítési rendelés található:

- **SO1:** Mennyiség = 2, kért szállítási dátum = ma + 3 nap

Ezt az igényt a meglévő készlet és egy visszaigazolt beszerzési rendelés fedezi:

- **Aktuális készlet:** Elérhető = ma, mennyiség = 1, lejárati dátum = ma + 2 nap
- **1. beszerzési rendelés:** kézhezvételi dátum = ma + 3 nap, mennyiség = 1, lejárati dátum = ma + 4 nap

Az SO1 nem teljesítható az aktuális készlettel, mert a készlet lejárati dátuma a szállítási dátumnál koros. Az 1. beszerzési rendelés csak az SO1 követelményt tudja fedezni, mennyisége csak 1. Emiatt az SO1 egy termékegység iránti igényt generál. Ennek a követelménynek a fedezéséhez a rendszer létrehoz egy tervezett beszerzési rendelést (PPO1).

A rendszerben két kereskedelmi megállapodás van (egy a mennyiség = 1, az átfutási idő = 4 nap, és egy a mennyiség = 2, az átfutási idő = 3 nap). A rendszer tehát a második kereskedelmi megállapodásnak megfelelő tervezett beszerzési rendelés létrehozásával próbálja minimálisra csökkenteni a késéseket. Az eredmény túlszállítás (mennyiség = 2, lejárati dátum = ma + 10 nap).

A következő táblázat összefoglalja az eredményt.

| Igény | Igénykövetés |
|---|---|
| **SO1: Szállítási** dátum = ma + 3 nap, mennyiség = 2 | <p>**1. beszerzési rendelés:** kézhezvételi dátum = ma + 3 nap, mennyiség = 1, lejárati dátum = ma + 4 nap</p><p>**PPO1: Bevételezési** dátum = ma + 3 nap, mennyiség = 1, lejárati dátum = ma + 10 nap</p> |

A következő ábra a példában szereplő időrendet mutatja be.

![2. példa: egyszerű FEFO, követelmény, három napos átfutási idő.](media/fefo-example-2.png "2. példa: egyszerű FEFO, követelmény, három napos átfutási idő")

## <a name="example-3-simple-fefo-requirement-three-days-of-lead-time-five-sellable-days"></a>3. példa: egyszerű FEFO, követelmény, három napos átfutási idő, öt árusítható nap

Ez a példa azt mutatja be, hogyan működik az eltarthatósági idő az egyes cikkek árusíthatósági napjainak hozzáadásakor.

A rendszer a következő cikk- és alapterv-beállításokat tartalmazza:

- **Fedezetkód (feltöltési stratégia):** követelmény
- **Eltarthatósági idő:** 10 nap
- **Árusítás napjai:** 5 nap
- **Átfutási idő:** 5 nap
- **Negatív napok:** 0 nap
- **Tervezett rendelés típusa (a cikk alapértelmezett rendelési beállításai):** Beszerzési rendelés

A rendszerben a következő értékesítési rendelések léteznek:

- **SO1:** Mennyiség = 2, kért szállítási dátum = ma + 2 nap
- **SO2:** Mennyiség = 1, kért szállítási dátum = ma + 3 nap
- **SO3:** Mennyiség = 1, kért szállítási dátum = ma + 5 nap

Ezt az igényt fedezheti a meglévő készlet és a visszaigazolt beszerzési rendelés:

- **Aktuális készlet:** Elérhető = ma, mennyiség = 1, lejárati dátum = Ma + 6 nap
- **1. beszerzési rendelés:** kézhezvételi dátum = ma + 2 nap, mennyiség = 3, lejárati dátum = ma + 10 nap

A rendszer létrehozza az előkeresési pályázók listáját, a készlet (FEFO) listája és az elérhetőségi dátumok alapján. Emiatt az SO1 nem teljesíthető az aktuális készlettel, mert a készlet a vevő által megkövetelt árusítható napok vége előtt lejár (a kért kézhezvételi dátum + 5 nap). Az 1. PO1 egységgel fedezheti az SO1 követelményt, az SO2 követelményt pedig egy egységben. Emiatt csak az SO3 még mindig fedezetlen igényt fedez egy cikkegységre. A rendszer a következő tervezett beszerzési rendelést hozza létre, hogy fedezze ezt a követelményt:

- **PP01: Kézhezvételi** dátum = ma + 5 nap, mennyiség = 1, lejárati dátum = ma + 10 nap

A következő táblázat összefoglalja az eredményt.

| Igény | Igénykövetés |
|---|---|
| **SO1: Szállítási** dátum = ma + 2 nap, mennyiség = 2 | **1. beszerzési rendelés:** kézhezvételi dátum = ma + 2 nap, mennyiség = 2, lejárati dátum = ma + 10 nap |
| **SO2: Szállítási** dátum = ma + 3 nap, mennyiség = 1 | **1. beszerzési rendelés:** kézhezvételi dátum = ma + 2 nap, mennyiség = 1, lejárati dátum = ma + 10 nap |
| **SO3: Szállítási** dátum = ma + 5 nap, mennyiség = 1 | **PPO1: Bevételezési** dátum = ma + 5 nap, mennyiség = 1, lejárati dátum = ma + 10 nap |

A következő ábra a példában szereplő időrendet mutatja be.

![3. példa: egyszerű FEFO, követelmény, három napos átfutási idő, öt árusítható nap.](media/fefo-example-3.png "3. példa: egyszerű FEFO, követelmény, három napos átfutási idő, öt árusítható nap")

## <a name="example-4-simple-fefo-period-lead-time-depends-on-the-quantity"></a>4. példa: egyszerű FEFO, időszak, átfutási idő a mennyiségtől függ.

A példa azt mutatja be, hogy a rendszer hogyan próbálja meg minimálisra csökkenteni a késéseket, ami időnként túlrendelést is okozhat.

A rendszer a következő cikk- és alapterv-beállításokat tartalmazza:

- **Fedezetkód (feltöltési stratégia):** időszak
- **Fedezeti időszak:** 10 nap (az eltarthatósági időnek megfelelő)
- **Eltarthatósági idő:** 10 nap
- **Árusítás napjai:** 0 nap
- **Átfutási idő:** A következő szállítói kereskedelmi megállapodások alapján jött létre:

    - **1. kereskedelmi megállapodás:** Ha a mennyiség = 1, az átfutási idő = 5
    - **2. kereskedelmi megállapodás:** Ha a mennyiség = 2, az átfutási idő = 0

- **Negatív napok:** 0 nap
- **Tervezett rendelés típusa (a cikk alapértelmezett rendelési beállításai):** Beszerzési rendelés

A rendszerben a következő értékesítési rendelések léteznek:

- **SO1:** mennyiség = 1, kért szállítási dátum = ma
- **SO2:** Mennyiség = 1, kért szállítási dátum = ma + 6 nap

Ezt az igényt részben fedezheti a következő visszaigazolt beszerzési rendelésekből származó készlet:

- **1. beszerzési rendelés:** kézhezvételi dátum = ma + 1 nap, mennyiség = 1, lejárati dátum = ma + 2 nap
- **2. PO2:** Kézhezvételi dátum = ma + 3 nap, mennyiség = 1, lejárati dátum = ma + 7 nap

A rendszernek két kereskedelmi megállapodása van (egy a mennyiség = 1, az átfutási idő = 5 nap, és egy a mennyiség = 2, az átfutási idő = 0 nap). A rendszer tehát minimálisra próbálja csökkenteni a késést azáltal, hogy létrehozza a következő tervezett beszerzési rendelést, amely megfelel a második kereskedelmi megállapodásnak:

- **PP01: Kézhezvételi** dátum = ma, mennyiség = 2, lejárati dátum = ma + 10 nap

Az SO1 a PPO1 egy egységgel lesz fedezve. Az SO2 fedezete a 2. beszerzési rendelés hatálya alá fog esni, mert a 2. beszerzési rendelés hamarabb lejár, mint a PPO1.

A következő táblázat összefoglalja az eredményt.

| Igény | Igénykövetés |
|---|---|
| **SO1: Szállítási** dátum = mai nap, mennyiség = 1 | **PPO1: Bevételezési** dátum = ma, mennyiség = 1, lejárati dátum = ma + 10 nap |
| **SO2: Szállítási** dátum = ma + 6 nap, mennyiség = 1 | **2. PO2:** Kézhezvételi dátum = ma + 3 nap, mennyiség = 1, lejárati dátum = ma + 7 nap |

> [!NOTE]
> Az 1. BESZERZÉSI rendelés nincs használatban, mert túl későn fog érkezni az S01 számára, és az S02 leszálla előtt lejár. A PPO1 egységgel túlrendelést ért el, hogy az átfutási idő 0 (nulla) legyen a 2. kereskedelmi megállapodás szerint.

A következő ábra a példában szereplő időrendet mutatja be.

![4. példa: egyszerű FEFO, időszak, átfutási idő a mennyiségtől függ.](media/fefo-example-4.png "4. példa: egyszerű FEFO, időszak, átfutási idő a mennyiségtől függ.")

## <a name="example-5-simple-fefo-requirement-10-negative-days"></a>5. példa: egyszerű FEFO, követelmény, 10 negatív nap

<!-- KFM: This is more of a negative days example than a shelf life example. We should point out more explicitly how shelf life affects this situation (or maybe otherwise remove this example). -->

Ez a példa azt mutatja be, hogyan működik az eltarthatósági idő, amikor nagy számú negatív napot adnak hozzá egy cikkhez. A negatív napok azon napok számát jelentik, amelyekre a negatív készlettelrendelt cikk feltöltése előtt hajlandó várni. A rendszer csak akkor hoz létre ellátásokat, ha a negatív napok száma meghaladja a megengedettet.

A rendszer a következő cikk- és alapterv-beállításokat tartalmazza:

- **Fedezetkód (feltöltési stratégia):** követelmény
- **Átfutási idő:** 0 nap
- **Negatív napok:** 10 nap
- **Tervezett rendelés típusa (a cikk alapértelmezett rendelési beállításai):** Beszerzési rendelés

A rendszerben a következő értékesítési rendelés található:

- **SO1:** mennyiség = 1, kért szállítási dátum = ma

Ezt az igényt a következő visszaigazolt beszerzési rendelésből származó meglévő készlet fedezheti:

- **1. beszerzési rendelés:** kézhezvételi dátum = ma + 3 nap, mennyiség = 1, lejárati dátum = ma + 5 nap

Mivel a rendszer úgy van beállítva, hogy 10 negatív napot engedélyezzen, az SO1 igényét az 1. BESZERZÉSI rendelés alkalmazásával fedezi, annak ellenére, hogy az eredmény háromnapos késés lesz, mivel az SO1 negatív készletet hoz létre, amíg a PO1 meg nem érkezik. Nem jön létre tervezett beszerzési rendelés annak ellenére, hogy az átfutási idő 0 (nulla), és a tervezett beszerzési rendelés létrehozása csökkenti a késést.

A következő táblázat összefoglalja az eredményt.

| Igény | Igénykövetés |
|---|---|
| **SO1: Szállítási** dátum = mai nap, mennyiség = 1 | **1. beszerzési rendelés:** kézhezvételi dátum = ma + 3 nap, mennyiség = 1, lejárati dátum = ma + 5 nap |

A következő ábra a példában szereplő időrendet mutatja be.

![5. példa: egyszerű FEFO, követelmény, 10 negatív nap.](media/fefo-example-5.png "5. példa: egyszerű FEFO, követelmény, 10 negatív nap")

## <a name="example-6-simple-fefo-requirement-five-negative-days"></a>6. példa: egyszerű FEFO, követelmény, öt negatív nap

Ez a példa azt mutatja be, hogyan működik az eltarthatósági idő, ha a negatív napok száma kisebb, mint az eltarthatósági időszaka.

A rendszer a következő cikk- és alapterv-beállításokat tartalmazza:

- **Fedezetkód (feltöltési stratégia):** követelmény
- **Árusítás napjai:** 0 nap
- **Átfutási idő:** 0 nap
- **Negatív napok:** 5 nap
- **Tervezett rendelés típusa (a cikk alapértelmezett rendelési beállításai):** Beszerzési rendelés

A rendszerben a következő értékesítési rendelés található:

- **SO1:** mennyiség = 2, kért szállítási dátum = ma

Ezt az igényt fedezheti a következő visszaigazolt beszerzési rendelésekből származó meglévő készlet:

- **PO1: Bevételezési** dátum = ma, mennyiség = 1, lejárati dátum = ma + 1 nap
- **2. PO2:** Kézhezvételi dátum = ma + 2 nap, mennyiség = 1, lejárati dátum = ma + 3 nap

A rendszernek ugyanakkor tartsa be azt a korlátozást, hogy a leszállított cikkek a szállításkor nem jár le. Emiatt a PO2 és a PO1 nem használható egyszerre az SO1 rendeléshez, mert a PO1 a 2. po2 érkezése előtt lejár. A rendszer létrehozza a következő tervezett beszerzési rendelést az SO1 iránti igény fedezése érdekében:

- **PPO1: Bevételezési** dátum = ma, mennyiség = 1, lejárati dátum = ma + 10 nap

A rendszer kihasználja az öt negatív napot, és a PO2 és PPO1 használhatja az SO1 fedezetére. Ez a megközelítés azonban a 2. beszerzési rendelés érkezéséig késlelteti a szállítást, és a beszerzési rendelés (PO1) a határidő lejártakor lejár. Emiatt a rendszer a PPO1 és a PO1 használatával tartalmazza az SO1 2002-et.

A következő táblázat összefoglalja az eredményt.

| Igény | Igénykövetés |
|---|---|
| **SO1: Szállítási** dátum = mai nap, mennyiség = 2 | <p>**PO1: Bevételezési** dátum = ma, mennyiség = 1, lejárati dátum = ma + 1 nap</p><p>**PPO1: Bevételezési** dátum = ma, mennyiség = 1, lejárati dátum = ma + 10 nap</p> |

A következő ábra a példában szereplő időrendet mutatja be.

![6. példa: egyszerű FEFO, követelmény, öt negatív nap.](media/fefo-example-6.png "6. példa: egyszerű FEFO, követelmény, öt negatív nap")
