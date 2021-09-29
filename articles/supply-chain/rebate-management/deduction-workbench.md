---
title: A levonások kezelése a levonás munkaterületről
description: Ez a témakör ismerteti, hogyan használja a levonás munkaterületről lehet levonások tartalmazó vevői kifizetések feldolgozása.
author: sherry-zheng
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: bf98529176fbed368708ea925f542a70f2936037
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500402"
---
# <a name="manage-deductions-using-the-deduction-workbench"></a>A levonások kezelése a levonás munkaterületről

[!include [banner](../includes/banner.md)]

Ez a témakör ismerteti, hogyan használja a levonás munkaterületről lehet levonások tartalmazó vevői kifizetések feldolgozása.

Olyan vevő, aki a visszatérítés tartozik eldöntheti, hogy ne várja meg a visszatérítési kifizetés. Feladhat olyan vevői fizetéseket is, amelyek visszatérítés miatti levonást tartalmaznak. A levonás munkaterületet használja a levonások és a nyitott hitelkártyatranzakciók párosításához, levonások megosztásához, levonások megtagadásához, és levonások leírásához.

> [!NOTE]
> A levonás munkaterület már hosszú ideje része a Microsoft Dynamics 365 Supply Chain Management értékesítési és marketing funkcióinak. Azonban tovább lett fejlesztve, hogy működjön az újabb **Visszatérítés-kezelés** modullal is. Ez a témakör azt ismerteti, hogyan lehet a levonás munkaterület régebbi funkciókkal és visszatérítéskezelési funkcióival is használni. Ha azonban [nem bekapcsolta a rendszer **Visszatérítéskezelés** modulját](rebate-management-enable.md), az itt leírt funkciók egy része nem lesz elérhető.

## <a name="prerequisites"></a>Előfeltételek

### <a name="set-up-the-old-deduction-management-system"></a>A régi levonáskezelő rendszer beállítása

A levonás munkaterületet a Supply Chain Management régi levonáskezelő képességeivel együtt használhatja, még akkor is, ha nem használja a **Visszatérítés kezelés** modult. A rendszert azonban előbb elő kell készítenie az ebben a szakaszban leírt módon.

A levonás munkaterület használata előtt el kell elvégeznie a [Levonáskezelés beállítása](/dynamicsax-2012/appuser-itpro/set-up-deduction-management) részben leírt beállítási feladatokat. Valamilyen visszatérítési szerződés beállítása is szükséges az ügyfélhez: vagy ügyfél-visszatérítés az [A vevőknek nyújtott visszatérítések beállítása és karbantartása](/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-customer-rebates) rész szerint vagy egy engedményes visszatérítés.

Ha vevői visszatérítésre levonást alkalmaz, a következő feladatokat kell elvégeznie:

- [Vevői visszatérítések beállítása](/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-customer-rebates).
- A visszatérítés jóváhagyása és feldolgozása, hogy a levonás munkaterület használható legyen.

Ha vevői promóciós engedményre levonást alkalmaz, a következő feladatokat kell elvégeznie:

- Visszaszámlázási visszatérítések beállítása.
- Visszaszámlázási visszatérítések alkalmazása.

### <a name="configure-accounts-receivable-and-deductions"></a><a name="accounts-receivable-deductions"></a>A Kinnlevőségek és levonások konfigurálása

A rendszer egy igénynapló minden levonási eseményét rögzíti. A rendszernek tehát tartalmaznia kell egy naplót, amely használható erre a célra. Ha még nem rendelkezik igénynaplóval, állítsa be most. A naplónak a levonás munkaterületen, a vevői kiegyenlítésen vagy a vevőoldalon a közvetlen levonásokhoz szükséges.

Egy új igénynapló beállításához a levonásokhoz kövesse az alábbi lépéseket.

1. Menjen a **Főkönyv \> Naplóbeállítások \> Naplónevek** pontra.
1. Válassza az **Új** lehetőséget, és állítsa be a következő mezőket az új napló nevéhez:

    - **Név** Az igénynapló egyedi azonosító nevének megadása.
    - **Leírás** – Adja meg az új napló leírását.
    - **Napló típusa** – Válassza a *Napi* lehetőséget.
    - **Bizonylatsorozat** – Meglévő számsorozat hozzárendelése. Másik lehetőségként hozzon létre egy új számsorozatot, amely vállalati hatókörrel rendelkezik, és rendelje hozzá az új naplónévhez.

1. Lépjen a **Kinnlevőségek \> Beállítások \> Kinnlevőségek paraméterei** pontra.
1. Állítsa be a **Levonások** lap **Általános** gyorslapján az **Igénynapló neve** mezőt az előbb létrehozott naplónévre.
1. A **Visszárurendelés** gyorslapon állítsa be a következő mezőket:

    - **Visszárurendelés létrehozása** – Ezzel a beállítással meghatározhatja, hogy a rendszer mit tegyen a mennyiség alapú igény jóváhagyása esetén:

        - *Igen* – Visszárurendelés létrehozása.
        - *Nem* – Negatív értékesítési rendelés létrehozása.

    - **Csatolt számla nélküli létrehozás** – Egy érték kiválasztásával adja meg, hogy mit kell tennie a rendszernek a mennyiségalapú igény jóváhagyásakor, amikor nincs csatolt számla:

        - *Elfogadás* – Visszárurendelés létrehozása.
        - *Figyelmeztetés* – Visszárurendelés létrehozása, de a következő figyelmeztető üzenet megjelenítése: "Az igény nincs csatolva számlához."
        - *Hiba* – Ne hozza létre a visszárurendelést, és jelenítse meg a következő figyelmeztető üzenetet megjelenítése: "Az igény nincs csatolva számlához. A frissítés meg lett szakítva.”

    - **Visszárurendelés létrehozása a levonás jóváhagyása előtt** – akkor állítsa *Igen* beállításra ezt e lehetőséget, ha a visszárurendeléseket az igény jóváhagyása előtt létre lehet hozni. Ez a beállítás csak azokra a mennyiségalapú igényekre vonatkozik, ahol a **Visszárurendelés létrehozása** beállítás *Igen* értékű.

### <a name="configure-general-ledger-parameters"></a>Főkönyv paraméterek konfigurálása

Amikor a rendszer létrehoz egy igénynaplót egy új levonáshoz, két új vevői tranzakciót is létrehoz: egyet az igény eredeti számlával szembeni ellentételezésére, és egyet a vevő tartozásának az igény összegéhez való regisztrálására (mivel az igény még nincs jóváhagyva). Ezért be kell állítani a rendszert, hogy egyetlen bizonylaton több vevősor is lehessen.

Egyetlen bizonylaton több vevősor engedélyezéséhez, kövesse ezeket a lépéseket.

1. Menjen a **Főkönyv \> Főkönyv beállítás \> Főkönyv paraméterei** pontra.
1. A **Főkönyv** lap **Általános** gyorslapján állítsa a **Több tranzakció engedélyezése egy bizonylaton** beállítást *Igen* értékre.
1. Ha figyelmeztető üzenet jelenik meg, a módosítás elfogadásához válassza a **Bezárás** lehetőséget.

### <a name="create-deduction-reasons"></a><a name="deduction-reasons"></a>Levonási okok létrehozása

A rendszer megköveteli, hogy a felhasználók minden olyan levonást megindokoljanak, amely közvetlenül a levonás munkaterületen, a vevői kiegyenlítésben vagy a vevői oldalon van megadva részükről. Az ok határozza meg a levonás kezelésének módját a jóváhagyáskor.

1. Menjen a **Kereskedelem és marketing \> Kereskedelmi kedvezmények \> Levonások \> Levonás okai** menübe.
1. Válassza ismét az **Új** lehetőséget egy sor hozzáadásához a rácshoz, majd állítsa be a következő mezőket hozzá:

    - **Igény oka** Az ok egyedi nevének megadása.
    - **Leírás** – Adja meg az ok leírását, amely további tájékoztatást ad a használat módjáról.
    - **Igény alapja** – Válassza ki az igény alapját az igény okához:

        - *Áralapú* – Szabadszöveges jóváírás létrehozása jóváhagyáskor.
        - *Mennyiségalapú* – Negatív értékesítési rendelés vagy visszárurendelés létrehozása a jóváhagyás után.

    - **Visszaküldés okkódja** – Válasszon egy visszatérítési okkódot, hogy alkalmazhassa **Visszaadási okkód** értékként a visszaküldési rendeléshez.
    - **Típus** – Válasszon ki egy levonási típust. A **Levonási eltolás** érték lesz használva a kijelölt típushoz a **Levonási eltolás** mező beállításához levonás vagy igény létrehozásakor. A levonástípusok meghatározása a **Levonástípusok** oldalon (**Értékesítés és marketing \> Kereskedelmi engedmények \> Levonások \> Levonástípusok**).
    - **Igényfeladási számla** – Ez a mező csak akkor érhető el, ha az **Igény alapja** mező beállítása *Áralapú*. Az áralapú igény jóváhagyása után a rendszer azt a főkönyvi számlát rendeli hozzá, amely itt van kiválasztva **Fő számla** értékként a vázlat szabadszöveges jóváíráshoz.

### <a name="set-up-the-settle-approved-deductions-periodic-task"></a>Jóváhagyott levonások kiegyenlítése időszakos feladat beállítása

Olyan levonások esetén, amelyek a levonás munkaterületén, a vevői kiegyenlítésnél vagy a vevőoldalon az **Új levonás** parancs használatával jönnek létre, beállítható a *Jóváhagyott levonások kiegyenlítése* ismétlődő feladat, amely automatikusan megfelelteti az egyező **Levonás azonosítója** értékkel és összeggel rendelkező levonások és jóváírások számára.

A feladat ütemezéséhez ugorjon az **Értékesítés marketing \> Időszakos feladatok \> Jóváhagyott levonások kiegyenlítése**, és végezze el a beállítások, szűrők és ütemezések megadását, mint az egyéb típusú ismétlődő feladat esetében.

> [!NOTE]
> Ha a **Kinnlevőségek paraméterei** oldal (**Kinnlevőségek \> Beállítás \> Kinnlevőségek paraméterei**) **Kiegyenlítés** lapján az **Automatikus kiegyenlítés** beállítás *Igen* értékre van beállítva, a *Jóváhagyott levonások kiegyenlítése* ismétlődő feladat nem tesz semmit, mivel a jóváírás kiegyenlítése automatikusan megtörténik.

## <a name="create-a-deduction"></a>Levonás létrehozása

### <a name="create-a-deduction-journal-entry-by-using-the-customer-payment-journal"></a>Levonási naplóbejegyzés létrehozása a vevői kifizetési napló használatával

Kövesse az alábbi lépéseket új nyitóegyenleg-napló létrehozásához.

1. Válassza a **Kinnlevőségek \> Kifizetések \> Kifizetési napló** lehetőséget.
1. Válassza az **Új** lehetőséget egy sor a rácshoz való hozzáadásához.
1. Az új sor **Név** mezőjében válassza ki a napló nevét.
1. A Műveleti ablaktáblán válassza a **Sorok** elemet.
1. Adja meg a dátum, a vállalati számla és a vevői számla számát.
1. Az **Számla** mezőben, válassza ki a számlát, amelyhez a levonás társítva van.
1. A **Jóváírás** mezőbe írja be a vevő által fizetett összeget.
1. Kattintson a **OK** lehetőségre annak megerősítéséhez hogy a teljes összeg kevesebb, mint a megjelölt tranzakció összege.
1. Az Ellenszámla típusa mezőben válassza ki az ellenszámlát.
1. A rács feletti eszköztárban válassza a **Levonások** lehetőséget.
1. A **Levonás** oldalon a Művelet panelen válassza az **Új** lehetőséget egy sor rácshoz való hozzáadásához. Az új sorhoz automatikusan be lesz állítva a **Levonás azonosítója** mező.
1. Az **Típus** mezőben válassza ki a levonástípust.
1. A **Mennység** mezőbe írja be a megjelenített összeget a **Levonás** mezőbe a levonás lista alatt. Ez az összeg, amelyet a vevő levonja a kifizetés összegét jelzi.
1. Zárja be a **levonás** oldalt. Visszatér a **Vevői kifizetések** lapra, amelyen a levonáshoz egy új sor jelenik meg.
1. A Művelet panelen válassza ki az **Ellenőrzés \> Ellenőrzés** lehetőséget. Ekkor a következő üzenettel: "A napló rendben."
1. A műveleti ablaktáblán válassza ki a **Feladás** elemet.

### <a name="create-a-deduction-by-using-the-deduction-workbench"></a>A levonások létrehozása a levonás munkaterület használatáról

Új levonás létrehozásához a levonás munkaterületen kövesse az alábbi lépéseket.

1. Menjen a **Kereskedelem és marketing \> Kereskedelmi kedvezmények \> Levonások \> Levonás munkaterület** menübe.
1. Jelölje be a Műveleti ablaktáblán a **Karbantartás \> Új levonás** lehetőséget.

    Az **Új levonás** párbeszédpanelen a **Levonás azonosítója** mező beállítása a **Levonás azonosítója** számsorozat alapján van beállítva, amely a **Promóciós engedmények kezelésének paraméterei** oldalon (**Értékesítés és marketing \> Beállítás \> Promóciós engedmények \> Promóciós engedmények kezelésének paraméterei**) van beállítva.

1. Állítsa be a következő mezőket:

    - **Vevői számla** – Annak a vevőnek a kiválasztása, akire a levonás vonatkozik.
    - **Külső igényszám** – Adja meg a vevő igényhivatkozását.
    - **Igény összege** – Adja meg az adót is tartalmazó igényösszeget. Az értéknek pozitívnak kell lennie.
    - **Pénznem** – A levonás pénznemének kiválasztása. Az alapértelmezett érték a kiválasztott vevőszámlához beállított pénznem.
    - **Igény alapja** – válassza ki az igény alapját. Az igény alapja határozza meg a levonás vagy igény jóváhagyása után létrehozott jóváírási tranzakció típusát.

        - *Áralapú* – Létrejön egy vázlat állapotú szabadszöveges számla.
        - *Mennyiségalapú* – Egy negatív értékesítési rendelés vagy visszárurendelés jön létre.

    - **Igény dátuma** – Az igény dátumának kiválasztása. Az alapértelmezett érték az aktuális dátum.
    - **Igény oka** – Az aktuális levonásra vonatkozó okkód kiválasztása. A kiválasztott igény alapja hatással van az alkalmazandó beállításokra. Az itt kiválasztott igény-okok létrehozásáról és konfigurálásról a témakör korábbi, [Levonási okok létrehozása](#deduction-reasons) című szakasza nyújt további tájékoztatást.
    - **Megjegyzések** – Az esetleges alkalmazandó megjegyzések hozzáadása. Az igény jóváhagyása után a jóváhagyó szerkesztheti vagy hozzáadhatja az igény megjegyzéseit.
    - **Igénynapló létrehozása** – Ezzel a beállítással megadhatja, hogy az igénynapló létre legyen-e hozva az igény vagy a levonás létrehozásakor:

        - *Igen* – a rendszer a **Kinnlevőségek paraméterei** oldalon beállított igénynapló segítségével hoz létre és ad fel általános naplót. (További tájékoztatás: [A kinnlevőségek és levonások konfigurálása](#accounts-receivable-deductions) szakasz a témakör korábbi részében.) Amikor az igényhez számla kapcsolódik, az igénynapló segítségével csökkentjük a vonatkozó számla egyenlegét. Ha az igényt később visszautasítják, akkor a rendszer sztornírozja az igénynaplót és a kiegyenlítéseket (ha csatoltak számlát).
        - *Nem* – Most nem jön létre igénynapló. Az igény jóváhagyásakor jön létre. Annak ellenére csatolható számla az új igényhez, hogy nincs létrehozva igénynapló. Az igénynapló nélkül azonban nem lehet kiegyenlítést végezni.

1. Válassza ki az **OK** lehetőséget.

    Új létrehozás jön létre. Ha *Igen* értékre állítja az **Igénynapló létrehozása** beállítást, a következő tranzakciók feladása történik meg:

    - **Két új vevői tranzakció** – Egy tranzakció ellentételezi az igény összegét az eredeti számlával szemben. A másik tranzakció az igény összegének megfelelő vevői tartozást regisztrálja, mivel az igény még nincs jóváhagyva. A program automatikusan megjelöli az eredeti számlatranzakciót és az ellentételező igénytranzakciót kiegyenlítésre, amikor a számla csatolva van a Műveleti panel **Karbantartás \> Számla csatolása** parancsával.
    - **Két ellentételező tranzakció** – ezek a tranzakciók a **Levonás eltolása** főkönyvi számlára kerülnek fel.
    - **Igénynapló** – a levonás munkaterületen megjelenő egyes levonások igénynaplóját a **Hivatkozások** lapon lehet megtekinteni. Az igénynapló a **Napló kötegszám** mezőben látható. Az igénynapló a **Levonási események** lapon is megtekinthető. Itt a **Frissítés típusa** értéke *Egyeztetés* lesz.

### <a name="create-a-deduction-from-a-customer-settlement"></a>Levonás létrehozása vevői kiegyenlítésből

A vevői kiegyenlítésből történő levonás létrehozásának folyamata hasonlít a levonásnak a levonás munkaterületen keresztüli létrehozásához. A vevő és a számla pénzneme azonban automatikusan be van állítva, és csatolva van a számla. Nem kell kiválasztani a **Karbantartás \> Számla csatolása** műveletet a műveleti panelen, amikor a vevői kiegyenlítési lapon keresztül igény vagy levonást hoz létre.

1. Nyissa meg a **Kinnlevőségek \> Vevők \> Minden vevő** lehetőséget.
1. Válassza ki azt a vásárlót, amelyhez levonást kell létrehozni.
1. A Műveleti ablaktábla **Beszedés** lapján lévő **Kiegyenlítés** csoportban válassza a **Tranzakciók kiegyenlítése** lehetőséget.
1. A **Kiegyenlítő tranzakciók** párbeszédpanel **Áttekintés** lapján válassza ki azt a számlát, amellyel szemben a levonást létrehozza.
1. Válassza az eszköztáron a **Levonások \> Új levonás** lehetőséget.

    Az **Új levonás** párbeszédpanelen a **Levonás azonosítója** mező beállítása a **Levonás azonosítója** számsorozat alapján van beállítva, amely a **Promóciós engedmények kezelésének paraméterei** oldalon (**Értékesítés és marketing \> Beállítás \> Promóciós engedmények \> Promóciós engedmények kezelésének paraméterei**) van beállítva. A **Vevői számla** mező ahhoz az ügyfélszámlához van beállítva, amelyre a levonás vonatkozik.

1. Állítsa be a következő mezőket:

    - **Külső igényszám** – Adja meg a vevő igényhivatkozását.
    - **Igény összege** – Adja meg az adót is tartalmazó igényösszeget. Az értéknek pozitívnak kell lennie.
    - **Pénznem** – A levonás pénznemének kiválasztása. Az alapértelmezett érték a kiválasztott vevőszámlához beállított pénznem.
    - **Igény alapja** – válassza ki az igény alapját. Az igény alapja határozza meg a levonás vagy igény jóváhagyása után létrehozott jóváírási tranzakció típusát.

        - *Áralapú* – Létrejön egy vázlat állapotú szabadszöveges számla.
        - *Mennyiségalapú* – Egy negatív értékesítési rendelés vagy visszárurendelés jön létre.

    - **Igény dátuma** – Az igény dátumának kiválasztása. Az alapértelmezett érték az aktuális dátum.
    - **Igény oka** – Az aktuális levonásra vonatkozó okkód kiválasztása. A kiválasztott igény alapja hatással van az alkalmazandó beállításokra. Az itt kiválasztott igény-okok létrehozásáról és konfigurálásról a témakör korábbi, [Levonási okok létrehozása](#deduction-reasons) című szakasza nyújt további tájékoztatást.
    - **Megjegyzések** – Az esetleges alkalmazandó megjegyzések hozzáadása. Az igény jóváhagyása után a jóváhagyó szerkesztheti vagy hozzáadhatja az igény megjegyzéseit.
    - **Igénynapló létrehozása** – Ezzel a beállítással megadhatja, hogy az igénynapló létre legyen-e hozva az igény vagy a levonás létrehozásakor:

        - *Igen* – a rendszer a **Kinnlevőségek paraméterei** oldalon beállított igénynapló segítségével hoz létre és ad fel általános naplót. (További tájékoztatás: [A kinnlevőségek és levonások konfigurálása](#accounts-receivable-deductions) szakasz a témakör korábbi részében.) Amikor az igényhez számla kapcsolódik, az igénynapló segítségével csökkentjük a vonatkozó számla egyenlegét. Ha az igényt később visszautasítják, akkor a rendszer sztornírozja az igénynaplót és a kiegyenlítéseket (ha csatoltak számlát).
        - *Nem* – Most nem jön létre igénynapló. Az igény jóváhagyásakor jön létre. Annak ellenére csatolható számla az új igényhez, hogy nincs létrehozva igénynapló. Az igénynapló nélkül azonban nem lehet kiegyenlítést végezni.

1. Válassza ki az **OK** lehetőséget.

    Új létrehozás jön létre. Ha *Igen* értékre állítja az **Igénynapló létrehozása** beállítást, a következő tranzakciók feladása történik meg:

    - **Két új vevői tranzakció** – Egy tranzakció ellentételezi az igény összegét az eredeti számlával szemben. A másik tranzakció az igény összegének megfelelő vevői tartozást regisztrálja, mivel az igény még nincs jóváhagyva. A program automatikusan megjelöli az eredeti számlatranzakciót és az ellentételező igénytranzakciót kiegyenlítésre, amikor a számla csatolva van a Műveleti panel **Karbantartás \> Számla csatolása** parancsával.
    - **Két ellentételező tranzakció** – ezek a tranzakciók a **Levonás eltolása** főkönyvi számlára kerülnek fel.
    - **Igénynapló** – a levonás munkaterületen megjelenő egyes levonások igénynaplóját a **Hivatkozások** lapon lehet megtekinteni. Az igénynapló a **Napló kötegszám** mezőben látható. Az igénynapló a **Levonási események** lapon is megtekinthető. Itt a **Frissítés típusa** értéke *Egyeztetés* lesz.

    Visszatér a **Tranzakciók kiegyenlítése** lapra, amelyen a kijelölt számla megjelöltként jelenik meg. A **Feladás** gomb csak akkor érhető el, ha az **Igénynapló létrehozása** lehetőséget *Igen* beállításra állította. Ha rendelkezésre áll, a **Feladás** kiválasztásával csökkentse a számla egyenlegét az **Igény összege** értékével.

### <a name="create-a-deduction-from-a-customer-page"></a>Levonás létrehozása ügyféloldalról

A vevői oldalról történő levonás létrehozásának folyamata hasonlít a levonásnak a levonás munkaterületen keresztüli létrehozásához. A vevő azonban automatikusan be van állítva.

1. Nyissa meg a **Kinnlevőségek \> Vevők \> Minden vevő** lehetőséget.
1. Válassza ki azt a vásárlót, amelyhez levonást kell létrehozni.
1. A műveleti ablakban a **Beszedés** lapon a **Levonások** csoportban válassza a **Levonások létrehozása** lehetőséget.

    Az **Új levonás** párbeszédpanelen a **Levonás azonosítója** mező beállítása a **Levonás azonosítója** számsorozat alapján van beállítva, amely a **Promóciós engedmények kezelésének paraméterei** oldalon (**Értékesítés és marketing \> Beállítás \> Promóciós engedmények \> Promóciós engedmények kezelésének paraméterei**) van beállítva. A **Vevői számla** mező ahhoz az ügyfélszámlához van beállítva, amelyre a levonás vonatkozik.

1. Állítsa be a következő mezőket:

    - **Külső igényszám** – Adja meg a vevő igényhivatkozását.
    - **Igény összege** – Adja meg az adót is tartalmazó igényösszeget. Az értéknek pozitívnak kell lennie.
    - **Pénznem** – A levonás pénznemének kiválasztása. Az alapértelmezett érték a kiválasztott vevőszámlához beállított pénznem.
    - **Igény alapja** – válassza ki az igény alapját. Az igény alapja határozza meg a levonás vagy igény jóváhagyása után létrehozott jóváírási tranzakció típusát.

        - *Áralapú* – Létrejön egy vázlat állapotú szabadszöveges számla.
        - *Mennyiségalapú* – Egy negatív értékesítési rendelés vagy visszárurendelés jön létre.

    - **Igény dátuma** – Az igény dátumának kiválasztása. Az alapértelmezett érték az aktuális dátum.
    - **Igény oka** – Az aktuális levonásra vonatkozó okkód kiválasztása. A kiválasztott igény alapja hatással van az alkalmazandó beállításokra. Az itt kiválasztott igény-okok létrehozásáról és konfigurálásról a témakör korábbi, [Levonási okok létrehozása](#deduction-reasons) című szakasza nyújt további tájékoztatást.
    - **Megjegyzések** – Az esetleges alkalmazandó megjegyzések hozzáadása. Az igény jóváhagyása után a jóváhagyó szerkesztheti vagy hozzáadhatja az igény megjegyzéseit.
    - **Igénynapló létrehozása** – Ezzel a beállítással megadhatja, hogy az igénynapló létre legyen-e hozva az igény vagy a levonás létrehozásakor:

        - *Igen* – a rendszer a **Kinnlevőségek paraméterei** oldalon beállított igénynapló segítségével hoz létre és ad fel általános naplót. (További tájékoztatás: [A kinnlevőségek és levonások konfigurálása](#accounts-receivable-deductions) szakasz a témakör korábbi részében.) Amikor az igényhez számla kapcsolódik, az igénynapló segítségével csökkentjük a vonatkozó számla egyenlegét. Ha az igényt később visszautasítják, akkor a rendszer sztornírozja az igénynaplót és a kiegyenlítéseket (ha csatoltak számlát).
        - *Nem* – Most nem jön létre igénynapló. Az igény jóváhagyásakor jön létre. Annak ellenére csatolható számla az új igényhez, hogy nincs létrehozva igénynapló. Az igénynapló nélkül azonban nem lehet kiegyenlítést végezni.

1. Válassza ki az **OK** lehetőséget.

    Új létrehozás jön létre. Ha *Igen* értékre állítja az **Igénynapló létrehozása** beállítást, a következő tranzakciók feladása történik meg:

    - **Két új vevői tranzakció** – Egy tranzakció ellentételezi az igény összegét az eredeti számlával szemben. A másik tranzakció az igény összegének megfelelő vevői tartozást regisztrálja, mivel az igény még nincs jóváhagyva. A program automatikusan megjelöli az eredeti számlatranzakciót és az ellentételező igénytranzakciót kiegyenlítésre, amikor a számla csatolva van a Műveleti panel **Karbantartás \> Számla csatolása** parancsával.
    - **Két ellentételező tranzakció** – ezek a tranzakciók a **Levonás eltolása** főkönyvi számlára kerülnek fel.
    - **Igénynapló** – a levonás munkaterületen megjelenő egyes levonások igénynaplóját a **Hivatkozások** lapon lehet megtekinteni. Az igénynapló a **Napló kötegszám** mezőben látható. Az igénynapló a **Levonási események** lapon is megtekinthető. Itt a **Frissítés típusa** értéke *Egyeztetés* lesz.

## <a name="create-a-credit-note-for-a-customer"></a>Jóváírás létrehozása vevő számára

Ezután követően a vevő számára egy jóváhagyott visszatérítési esetén létrehozhat egy jóváírást a vevő számlájának a visszatérítés ábrázolásához igény szerint. A jóváírás akkor jelenik meg a levonás munkaterületen ha egyeztethető egy levonással.

Munkafolyamat létrehozásához kövesse az alábbi lépéseket.

1. Lépjen az **Értékesítés és marketing \> Vevők \> Összes vevő** menüpontba.
1. Válassza ki az ügyfelet.
1. A Műveleti ablaktábla **Beszedés** lapján lévő **Kiegyenlítés** csoportban válassza a **Tranzakciók kiegyenlítése** lehetőséget.
1. A **Tranzakciók kiegyenlítése** párbeszédpanelén válassza ki azt a tranzakciót, amelyre a visszatérítést alkalmazták.
1. Az eszköztár **Funkciók** menüjében válassza ki a alkalmazandó visszatérítési program típusát.
1. A **Visszatérítés** lap **Áttekintés** lapján jelölje be a **Megjelölés** jelölőnégyzetet a megfelelő visszatérítési azonosító mellett.
1. A műveleti panelen válassza a **Funkciók \> Jóváírás létrehozása** lehetőséget.

## <a name="process-a-deduction-on-the-deduction-workbench"></a>A levonás munkaterületen a levonások kezelése

A levonás munkaterületet használhatja a levonások és a nyitott hitelkártyatranzakciók párosításához, levonások megosztásához, levonások megtagadásához, és levonások leírásához.

Attól függően, hogy hogyan szeretné feldolgozni a levonás hajtson végre az alábbi eljárásokat közül egyet vagy többet a következő alszakaszokból: Szükség esetén kombinálhatja az eljárásokat. Például levonás felosztására szolgáló két részre, és akkor egyeznie a kijelző egy követel tétel de hagyja meg a munkaterület-másik követelés később egyeztetendő fennmaradó részére. Lehetséges levonás egyeztetése egy követeléshez amely kisebb, mint a levonás összegét, és ezután megtagadása vagy leírása a levonás fennmaradó egyenlegét.

### <a name="match-a-deduction-to-a-credit"></a>Levonás egyeztetést jóváíráshoz

A levonás jóváírással való egyeztetéséhez kövesse az alábbi lépéseket.

1. Menjen a **Kereskedelem és marketing \> Kereskedelmi kedvezmények \> Levonások \> Levonás munkaterület** menübe.
1. Az levonás feldolgozásához jelölje be a **Megjelölés** jelölőnégyzetet.
1. A **Nyitott tranzakciók** területen jelölje be a **Megjelölés** jelölőnégyzetet, hogy egyeztesse a jóváírást a levonással. Több követelés jelenik meg, egynél több jóváírást is választhat a levonás egyeztetéséhez. Ha azt szeretné, hogy a rendszer automatikusan válassza ki a levonás összegének megfelelő jóváírásokat, az eszköztáron válassza ki a megfelelő beállítást a **Levonás összegének kiválasztása** menüben.
1. A Műveletpanelen válasza a **Karbantartás \> Egyeztetés** elemet. A rendszer egyezteti a levonást a jóváírással. Ha marad egyenleg a levonásban, akkor az megjelenik a **Levonások** lap **Fennmaradó összeg** mezőjében.

    > [!NOTE]
    > Olyan levonások esetén, amelyek a levonás munkaterületén, a vevői kiegyenlítésnél vagy a vevőoldalon az **Új levonás parancs** használatával lettek létrehozva, a **Karbantartás \> Egyeztetés** parancs csak akkor érhető el, ha az **Igény állapota** mező beállítása *Elfogadott*. Ezzel a paranccsal lehet manuálisan megfeleltetni az ár alapú vagy mennyiség alapú tranzakciót a **Nyitott tranzakciók** szakasz kapcsolódó jóváírásával. Ez a jóváírás vagy akkor jön létre, amikor a levonást jóváhagyták (a **Karbantartás \> Levonás jóváhagyása** paranccsal), vagy amikor egy meglévő jóváíráshoz csatolták, amint azt a témakör későbbi [A levonás jóváhagyási folyamaton kívül jóváhagyott jóváírások](#credits-outside-approval) szakaszában olvashatja. A *Jóváhagyott levonások kiegyenlítése* időszakos feladat (**Értékesítési és marketing \> Időszakos feladatok \> Jóváhagyott levonások kiegyenlítése**) segítségével automatikusan egyeztetni lehet az azonos **Levonási azonosító** értékekkel és összegekkel rendelkező levonásokkal és jóváírásokkal.

### <a name="split-a-deduction"></a>Levonás felosztása

Kövesse az alábbi lépéseket levonás felosztásához.

1. Menjen a **Kereskedelem és marketing \> Kereskedelmi kedvezmények \> Levonások \> Levonás munkaterület** menübe.
1. Az levonás feldolgozásához jelölje be a **Megjelölés** jelölőnégyzetet.
1. A Műveletpanelen válasza a **Karbantartás \> Felosztás** elemet.
1. Adja meg a **Felosztás** párbeszédpanel **Felosztás összege** mezőjében a fő levonásból felosztani szükséges összeget. Majd kattintson az **OK** lehetőségre.
1. A **Levonások** lapon, figyelje meg, hogy egy új rekord jeleni meg a felosztott összeghez. Az eredeti levonás rekord tartalmazza a levonási egyenleg maradékát. Most már az eredeti visszatérítés két részét külön kezelheti.
1. Válassza ki az eredeti levonási rekordot, majd válassza a **Hivatkozások** lapot. A **Felosztás összege** mezőben az eredeti összegtől leválasztott összeg látható.

### <a name="attach-an-invoice-to-a-deduction"></a>Számla csatolása levonáshoz

Ha a levonást a levonás munkaterület, a vevői kiegyenlítés vagy a vevőoldal **Új levonás** parancsával hozták létre, akkor csatolhat számlát a levonáshoz, és ha jelenleg nincs számla csatolva (vagyis a **Számla** oszlop üres).

A következő lépések szerint csatolhat számlát a levonáshoz.

1. Menjen a **Kereskedelem és marketing \> Kereskedelmi kedvezmények \> Levonások \> Levonás munkaterület** menübe.
1. Az levonás feldolgozásához jelölje be a **Megjelölés** jelölőnégyzetet.
1. Jelölje be a Műveleti ablaktáblán a **Karbantartás \> Számla csatolása** lehetőséget.
1. A **Számla csatolása** párbeszédpanelen válasszon ki egy számlát, majd válassza az **OK** gombot.
1. A **Tranzakciók kiegyenlítése** párbeszédpanelen hajtsa végre az alábbi lépések valamelyikét attól függően, hogy a levonás létrehozásakor fel lett-e adva igénynapló:

    - Igénynapló feladása esetén a kiválasztott számla és az igénynapló vevői jóváírási tranzakciója meg van jelölve a **Megjelölés** oszlopban. Válassza a **Feladás** parancsot. A csatolt számla fennmaradó egyenlege az igény összegével csökken.
    - Ha igénynaplót nem lett feladva, egyetlen tranzakció sincs kipipálva a **Megjelölés** oszlopban. Mivel a levonás jóváhagyása után nem lehet az igénynaplóval szemben ellentételezni választani, válassza a **Mégse** lehetőséget.

### <a name="detach-an-invoice-from-a-deduction"></a>Számla leválasztása levonásról

Ha a levonást a levonás munkaterület, a vevői kiegyenlítés vagy a vevőoldal **Új levonás** parancsával hozták létre, akkor leválaszthatja a számlát a levonásról, ha van jelenleg bármilyen számla csatolva (tehát a **Számla** oszlopban látható egy számlaszám), és az **Igény állapota** mező beállítása *Nyitott*. Előfordulhat, hogy ezt a feladatot azért kell végrehajtania, mert helytelen számla lett csatolva. A program eltávolítja a számlát a levonásból, és ha csökkentve lett a számla csatolásakor, akkor a fennmaradó egyenleg frissül.

Számla leválasztásához kövesse az alábbi lépéseket.

1. Menjen a **Kereskedelem és marketing \> Kereskedelmi kedvezmények \> Levonások \> Levonás munkaterület** menübe.
1. Az levonás feldolgozásához jelölje be a **Megjelölés** jelölőnégyzetet.
1. Jelölje be a Műveleti ablaktáblán a **Karbantartás \> Számla leválasztása** lehetőséget.

### <a name="approve-a-deduction"></a>Levonás jóváhagyása

A levonás munkaterületen, a vevői kiegyenlítésben vagy a vevőoldalon található **Új levonás** paranccsal létrehozott levonásokat lehet jóváhagyni. Csak olyan levonásokat lehet azonban jóváhagyni, amelyekben az **Igény állapota** mező beállítása *Nyitott*.

Kövesse az alábbi lépéseket levonás jóváhagyásához.

1. Menjen a **Kereskedelem és marketing \> Kereskedelmi kedvezmények \> Levonások \> Levonás munkaterület** menübe.
1. Az levonás feldolgozásához jelölje be a **Megjelölés** jelölőnégyzetet.
1. Jelölje be a Műveleti ablaktáblán a **Karbantartás \> Levonás jóváhagyása** lehetőséget.
1. A **Levonás jóváhagyása** párbeszédpanelen szükség szerint módosítsa a **Megjegyzés** értékét, vagy adjon hozzá információkat.
1. Ha a levonás áralapú, és nincs hozzá számla csatolva, válasszon egy cikkáfacsoportot. A számlán általában be van állítva az cikkáfacsoport. Ezért az áfacikk kódját meg kell adni, ha nincs számlához csatolva.
1. Válassza ki az **OK** lehetőséget.

    Ezen a ponton nem lehet további változtatásokat tenni a levonáson. Ha az **Igénynapló létrehozása** lehetőség a levonás létrehozásakor *Nem* értékre volt állítva, az igénynapló akkor jön létre és lesz feladva, amikor a levonást jóváhagyják. A levonás jóváhagyása után a rendszer automatikusan létrehoz és megnyit egy jóváírást. A típus a levonás **Igényének alapja** értékétől függ:

    - *Áralapú* – Ha a levonás áralapú, a vevői számlához szabadszöveges számla jön létre. Hozzáadhat egy leírást, és fel tudja adni a jóváírást. A vázlat létrehozásakor a következő mezőket tölti ki a levonás:

        - **Levonás azonosítója** – A rendszer hozzáadja ezt a mezőt a fejléchez, hogy lehetővé tegye a levonás nyomon követhetőségét.
        - **Fő számla** – Az értéket az **Igényfeladási számla** értéke határozza meg, amely a levonáshoz rendelt levonási okhoz van beállítva.
        - **Cikkáfacsoport** – Az értéket a csatolt számla vagy a levonás jóváhagyásakor kiválasztott érték határozza meg.
        - **Egységár** – Az érték a levonás igényösszegének jóváírása.
        - **Számlaszöveg** – Alapértelmezés szerint ez a mező a levonás **Megjegyzés** értéke.

    - *Mennyiségalapú* – Ha a levonás mennyiségalapú, egy nyitott értékesítési rendelés vagy visszárurendelés jön létre. A **Visszárurendelés létrehozása** beállítás a **[Kinnlevőségek paraméterei](#accounts-receivable-deductions)** lapon határozza meg, hogy a levonás jóváhagyásakor létrejön-e értékesítési rendelés vagy visszárurendelés. Megjelenik a **Rendelések másolása** lap, és a rendszer szűri, hogy megjelenjenek azok a sorok, amelyeknél a **Számlafogadó** mező be van állítva a levonás vevőszámlájára. Tegye a következők egyikét:

        1. A **Számlák** gyorslapon a **Fejlécek** szakasz azokat az értékesítési számlákat mutatja, amelyekben a **Számlafogadó** értéke megegyezik a levonás vevői számlájával. Válasszon ki egy vonatkozó értékesítési számlát.
        1. A **Sorok** szakasz a kiválasztott értékesítési számla sorait jeleníti meg. Jelölje be azoknak a soroknak a **Kijelölés** jelölőnégyzetét, amelyeket másolni szeretne. Másik lehetőségként a **Fejlécek** szakaszban jelölje be az **Összes kijelölése** lehetőséget az értékesítési rendeléshez az összes sora kijelöléséhez.
        1. Módosítsa a **Mennyiség** értékét igény szerint egy vagy több sornál.

            Az eddig kiválasztott összes sor megjelenik a **Másolandó kijelölt sorok és fejléc** gyorslapon.

        1. Ismételje meg az előző két lépést mindaddig, amíg az összes szükséges sor fel nem lesz sorolva a **Másolandó kijelölt sorok vagy fejléc** gyorslapon.
        1. Válassza ki az **OK** lehetőséget.

            Megnyílik az új visszárurendelés, és a következő mezők automatikusan be vannak állítva:

            - **Levonás azonosítója** – A rendszer hozzáadja ezt a mezőt a fejléchez, hogy lehetővé tegye a levonás nyomon követhetőségét.
            - **Visszaküldés okkódja** – alapértelmezés szerint ez a mező a levonáshoz hozzárendelt levonási ok miatt megadott **Visszaküldés okkód** értékre van beállítva.

A jóváírás számlázása után megjelenik a levonás munkaterület **Nyitott tranzakciók** szakaszában a megfelelő **Levonásazonosító** értékével szemben, és az **Igény típusa** mezőjének értéke *Egyéb jóváírás*. A jóváírás mindaddig elérhető lesz, amíg a levonást ki nem egyenlítik a következő módok egyikével:

- Manuálisan kiegyenlíti, ha a műveleti panel **Karbantartás \> Egyeztetés** parancsának kiválasztásával.
- A program automatikusan kiegyenlíti a *Jóváhagyott igények kiegyenlítése* időszakos feladattal (**Értékesítés és marketing \> Időszakos feladatok \> Jóváhagyott igények kiegyenlítése**).
- A program automatikusan kiegyenlíti, mert a **Kinnlevőségek paraméterei** oldal **Kiegyenlítés** lapján az **Automatikus kiegyenlítés** beállítás *Igen* értékre van beállítva.

A levonás jóváhagyásakor létrehozott jóváírás megtekintéséhez használhatja a Levonás munkaterület **Nyitott tranzakciók** szakaszában található **Jóváírás megnyitása** gombot is.

### <a name="create-a-return-order"></a>Visszárurendelés létrehozása

A levonás munkaterületen, a vevői kiegyenlítésben vagy a vevőoldalon található **Új levonás** paranccsal létrehozott levonásokhoz visszárurendelést hozhat létre. Ugyanakkor minden alábbi feltételnek teljesülnie kell:

- Az **Igény alapja** mező beállítása *Mennyiség alapú*.
- Az **Igény állapota** mező *Nyitott* értékre van állítva.
- A **[Kinnlevőségek paraméterei](#accounts-receivable-deductions)** lap **Levonások** lapján a **Visszárurendelés létrehozása** beállítás *Igen* értékre van állítva.
- A **[Kinnlevőségek paraméterei](#accounts-receivable-deductions)** lap **Levonások** lapján a **Visszárurendelés létrehozása a levonás jóváhagyása előtt** *Igen* értékre van állítva.

Visszárurendelés létrehozásához kövesse az alábbi lépéseket.

1. Menjen a **Kereskedelem és marketing \> Kereskedelmi kedvezmények \> Levonások \> Levonás munkaterület** menübe.
1. Az levonás feldolgozásához jelölje be a **Megjelölés** jelölőnégyzetet.
1. Jelölje be a műveleti ablakban a **Karbantartás \> Visszárurendelés létrehozása** lehetőséget.
1. A **Levonás jóváhagyása** párbeszédpanelen szükség szerint módosítsa a meglévő **Megjegyzések** értékét, majd válassza az **OK** lehetőséget.
1. A **Számlák** gyorslapon a **Fejlécek szakasz** **Rendelések másolása** párbeszédpanele azokat az értékesítési számlákat mutatja, amelyekben a **Számlafogadó** értéke megegyezik a levonás vevői számlájával. Válasszon ki egy vonatkozó értékesítési számlát.
1. A **Sorok** szakasz a kiválasztott értékesítési számla sorait jeleníti meg. Jelölje be azoknak a soroknak a **Kijelölés** jelölőnégyzetét, amelyeket másolni szeretne. Másik lehetőségként a **Fejlécek** szakaszban jelölje be az **Összes kijelölése** lehetőséget az értékesítési rendeléshez az összes sora kijelöléséhez.
1. Módosítsa a **Mennyiség** értékét igény szerint egy vagy több sornál.

    Az eddig kiválasztott összes sor megjelenik a **Másolandó kijelölt sorok és fejléc** gyorslapon.

1. Ismételje meg az előző két lépést mindaddig, amíg az összes szükséges sor fel nem lesz sorolva a **Másolandó kijelölt sorok vagy fejléc** gyorslapon.
1. Válassza ki az **OK** lehetőséget.

    Megnyílik az új visszárurendelés, és a következő mezők automatikusan be vannak állítva:

    - **Levonás azonosítója** – A rendszer hozzáadja ezt a mezőt a fejléchez, hogy lehetővé tegye a levonás nyomon követhetőségét.
    - **Visszaküldés okkódja** – alapértelmezés szerint ez a mező a levonáshoz hozzárendelt levonási ok miatt megadott **Visszaküldés okkód** értékre van beállítva.

### <a name="deny-a-deduction"></a>Levonás visszautasítása

Kövesse az alábbi lépéseket levonás visszautasításához.

1. Menjen a **Kereskedelem és marketing \> Kereskedelmi kedvezmények \> Levonások \> Levonás munkaterület** menübe.
1. Az levonás feldolgozásához jelölje be a **Megjelölés** jelölőnégyzetet.
1. A Műveletpanelen válasza a **Karbantartás \> Visszautasítás** elemet.
1. A **Visszautasítás** párbeszédpanelen válassza ki a visszautasítás okkódját, majd válassza az **OK** lehetőséget.
1. Az alábbi **Megjelenítés** mezőben a műveleti ablakban válassza a *Lezárt* értéket.

    A visszautasított levonás fel van tüntetve a **Levonások** fülön, és a **Fennmaradó összeg** levonáson *0,00* értékre van állítva.

    A levonás munkaterületen, a vevői kiegyenlítésben vagy a vevőoldalon található **Új levonás** paranccsal létrehozott levonásokhoz a következő események következnek be:

    - A **Hivatkozások** lapon a **Visszautasítás** szakasz mezői frissülnek.
    - Ha azt választotta, hogy létrehozza az igénynaplót a levonás létrehozásakor, és ha a számla egyenlegét csökkentő levonáshoz számla van csatolva, akkor a számla leválasztásra került, és a korábban csatolt számla fennmaradó egyenlege az elutasított igény összegével nő.
    - A levonás **Állapota** mező *Lezárt* állapotúra van állítva.
    - A levonás **Igény állapota** mezője *Elutasított* állapotúra van állítva.

Kövesse az alábbi lépéseket levonás sztornírozásához.

1. A **Levonások** lapon válasszon ki egy elutasított levonást.
1. A Művelet ablaktáblán válassza ki a **Levonás elutasítása** lehetőséget.

    A levonás munkaterületen, a vevői kiegyenlítésben vagy a vevőoldalon található **Új levonás** paranccsal létrehozott levonásokhoz a következő események következnek be:

    - A **Hivatkozások** lapon a **Visszautasítás** szakasz mezői frissülnek.
    - A levonás **Állapota** mező *Nyitott* állapotúra van állítva.
    - A levonás **Igény állapota** mezője *Nyitott* állapotúra van állítva.

### <a name="write-off-a-deduction"></a>Levonás leírása

Kövesse az alábbi lépéseket levonás leírásához.

1. Menjen a **Kereskedelem és marketing \> Kereskedelmi kedvezmények \> Levonások \> Levonás munkaterület** menübe.
1. Az levonás feldolgozásához jelölje be a **Megjelölés** jelölőnégyzetet.
1. A Műveletpanelen válasza a **Karbantartás \> Leírás** elemet.
1. A **Leírás** párbeszédpanelen válassza ki a leírás okkódját, majd válassza az **OK** lehetőséget.
1. A **Megjelenítés** mezőben válassza a *Lezárt* lehetőséget.

    A leírt levonás fel van tüntetve a **Levonások** fülön, és a **Fennmaradó összeg** levonáson *0,00* értékre van állítva.

    A levonás munkaterületen, a vevői kiegyenlítésben vagy a vevőoldalon található **Új levonás** paranccsal létrehozott levonásokhoz a következő események következnek be:

    - A **Hivatkozások** lapon a **Leírás** szakasz mezői frissülnek.
    - Ha a levonás létrehozásakor létrehozta az igénynaplót, egy igénynaplót ad fel a program a levonás leírási okkódjába. Ezt a bejegyzést a **Levonási események** lapon lehet megtekinteni, ahol **Leírás** *Frissítés típusú* értékkel rendelkezik.
    - A levonás **Állapota** mező *Lezárt* állapotúra van állítva
    - A levonás **Igény állapota** mezője *Leírás* állapotúra van állítva.

Kövesse az alábbi lépéseket levonás sztornírozásához.

1. A **Levonások** lapon válasszon ki egy elutasított levonást.
1. A Műveletpanelen válasza a **Leírás sztornírozása** lehetőséget.

    A levonás munkaterületen, a vevői kiegyenlítésben vagy a vevőoldalon található **Új levonás** paranccsal létrehozott levonásokhoz a következő események következnek be:

    - A **Hivatkozások** lapon a **Leírás** szakasz mezői frissülnek.
    - Ha a levonás létrehozásakor létrehozta az igénynaplót, egy igénynaplót ad fel a program a levonás leírási okkódjába. Ezt a bejegyzést a **Levonási események** lapon lehet megtekinteni, ahol **Leírás sztornírozása** *Frissítés típusú* értékkel rendelkezik.
    - A levonás **Állapota** mező *Nyitott* állapotúra van állítva.
    - A levonás **Igény állapota** mezője *Nyitott* állapotúra van állítva.

## <a name="credits-created-outside-the-approve-deduction-process"></a><a name="credits-outside-approval"></a>A levonás jóváhagyási folyamaton kívül jóváhagyott jóváírások

Ez a szakasz levonás munkaterületen, a vevői kiegyenlítésben vagy a vevőoldalon található **Új levonás** paranccsal létrehozott levonásokra vonatkozik.

Előfordulhat, hogy más felhasználók már létrehoztak egy szabadszöveges számlát, visszárurendelést vagy negatív értékesítési rendelést egy vevőnek az igényére a **Levonás jóváhagyása** folyamaton kívül. Amikor a levonás munkaterületen jóváhagyják a meglévő levonást, a rendszer automatikusan létrehoz egy másik szabadszöveges számlát, visszárurendelést vagy negatív értékesítési rendelést. Ez a szakasz bemutatja, hogyan lehet meglévő jóváírásokat csatolni a levonáshoz a levonás jóváhagyása előtt, hogy megelőzhetők legyenek többszöri jóváírások.

### <a name="attach-a-credit-to-deduction"></a>Jóváírás csatolása levonáshoz

Ez a szakasz azt írja le, hogyan lehet jóváírást csatolni egy levonáshoz a jóváírásból.

Miután a jóváírás csatolva lett a levonáshoz megtekintheti a levonás munkaterület **Nyitott tranzakciók** szakaszában található **Jóváírás megnyitása** gomb használatával is.

A jóváírás számlázása és a levonás jóváhagyása után a jóváírás megjelenik a levonás munkaterület **Nyitott tranzakciók** szakaszában a megfelelő **Levonásazonosító** értékével szemben, és az **Igény típusa** mezőjének értéke *Egyéb jóváírás*.

#### <a name="attach-a-free-text-invoice-to-a-deduction"></a>Szabadszöveges számla csatolása levonáshoz

A következő lépések szerint csatolhat szabadszöveges számlát a levonáshoz.

1. Ugorjon a következőre: **Kinnlévőségek \> Számlák \> Kizárólag szabadszöveges számlák**.
1. Válassza ki a vonatkozó számlát.
1. A Művelet panel **Számla** lapján válassza a **Jóváírás csatolása levonáshoz** menüpontot. Ez a gomb csak akkor használható, ha a szabadszöveges számla **Levonási azonosító** mezője üres. Ha üres a mező, az azt jelenti, hogy a szabadszöveges számla még nincs levonáshoz csatolva.
1. A **Jóváírás csatolása levonáshoz** lapon kiválaszthat *egy* levonást. Csak nyitott *áralapú* levonások érhetők el kiválasztásra.
1. Válassza ki az **OK** lehetőséget. A **Levonás azonosítója** mező a szabadszöveges számla fejlécében van beállítva.

#### <a name="attach-a-return-order-to-a-deduction"></a>Visszárurendelés csatolása levonáshoz

A következő lépések szerint csatolhat visszárurendelést levonáshoz.

1. Ugrás a **Kinnlevőségek \> Rendelések \> Minden visszárurendelés** menüpontba.
1. Válassza ki a megfelelő fogadott vagy nyitott Visszáru szállítása esetére való azonosítót (RMA-szám).
1. A Művelet panel **Visszárurendelés** lapján válassza a **Jóváírás csatolása levonáshoz** menüpontot. Ez a gomb csak akkor használható, ha a visszárurendelés **Levonási azonosító** mezője üres. Ha üres a mező, az azt jelenti, hogy a visszárurendelés még nincs levonáshoz csatolva.
1. A **Jóváírás csatolása levonáshoz** lapon kiválaszthat *egy* levonást. Csak nyitott *mennyiség alapú* levonások érhetők el kiválasztásra.
1. Válassza ki az **OK** lehetőséget. A **Levonás azonosítója** mező a visszárurendelés fejlécében van beállítva.

#### <a name="attach-a-sales-order-to-a-deduction"></a>Értékesítési rendelés csatolása levonáshoz

A következő lépések szerint csatolhat értékesítési rendelést levonáshoz.

1. Ugrás a **Kinnlevőségek \> Rendelések \> Minden értékesítési rendelésre**.
1. A megfelelő nyitott, leszállított vagy számlázott értékesítési rendelést válassza ki.
1. A Művelet panel **Számla** lapján válassza a **Jóváírás csatolása levonáshoz** menüpontot. Ez a gomb csak akkor használható, ha az értékesítési rendelés **Levonási azonosító** mezője üres. Ha üres a mező, az azt jelenti, hogy az értékesítési rendelés még nincs levonáshoz csatolva.
1. A **Levonás csatolása** lapon kiválaszthat *egy* levonást. Csak nyitott *mennyiség alapú* levonások érhetők el kiválasztásra.
1. Válassza ki az **OK** lehetőséget. A **Levonás azonosítója** mező az értékesítési rendelés fejlécében van beállítva.

#### <a name="detach-a-deduction-from-a-credit"></a>Levonás leválasztása jóváírásról

Ha a hibás levonás van csatolva, akkor le lehet leválasztani a jóváírásról. Ugyanakkor minden alábbi feltételnek teljesülnie kell:

- A levonáshoz jóváírás tartozik.
- Az **Igény állapota** mező *Nyitott* értékre van állítva.

Ha le kell leválasztani egy levonást egy jóváírásról, hajtsa végre az alábbi lépéseket a jóváírás típusától függően:

- **Szabadszöveges számlák**: Válasszon ki egy számlát a **Szabadszöveges számlák** lapon. A Műveleti panel **Számla** lapján válassza a **Jóváírás leválasztása levonásról** menüpontot.
- **Visszárurendelések:** Válasszon ki egy rendelést a **Minden visszárurendelés** lapon. A Műveleti panel **Visszárurendelés** lapján válassza a **Jóváírás leválasztása levonásról** menüpontot.
- **Értékeítési rendelések:** Válasszon ki egy rendelést a **Minden értékesítési rendelés** lapon. A Műveleti panel **Számla** lapján válassza a **Jóváírás leválasztása levonásról** menüpontot.

### <a name="attach-a-deduction-to-a-credit"></a>Levonás csatolása jóváíráshoz

Ez a szakasz azt írja le, hogyan lehet levonást csatolni jóváíráshoz a levonásból.

#### <a name="attach-a-deduction-to-a-free-text-return-order-or-sales-order-credit"></a>Levonás csatolása szabadszöveges visszárurendelés vagy értékesítési rendelés jóváíráshoz

Levonás csatolásához szabadszöveges visszárurendelés vagy értékesítési rendelés jóváíráshoz kövesse az alábbi lépéseket.

1. Menjen a **Kereskedelem és marketing \> Kereskedelmi kedvezmények \> Levonások \> Levonás munkaterület** menübe.
1. Válassza ki a megfelelő nyitott levonást.
1. Jelölje be a Műveleti ablaktáblán a **Karbantartás \> Levonás csatolása jóváíráshoz** lehetőséget. Ez a gomb csak akkor érhető el, ha az **Igény állapota** mező *Nyitott* állapotra van beállítva.
1. A **Jóváírás csatolása** lapon kiválaszthat *egy* jóváírást. A megjelenő jóváírástípus a levonás **Igény alapja** értékétől függ:

    - *Áralapú* –A lapon a vevői számlához tartozó szabadszöveges számlák jelennek meg ahol a **Levonás azonosítója** mező üres. A vevői igénylések is megjelennek, mert lehet, hogy a szabadszöveges számla még nem volt feladva. Emiatt lehet, hogy nincs olyan száma, amelyre hivatkozni lehet.
    - *Mennyiségalapú* – A megjelenő jóváírástípus a **iVsszárurendelés létrehozása** paraméter beállításától függ a **[Kinnlevőségek paraméterei](#accounts-receivable-deductions)** oldalon:

        - *Igen* – A lapon az ügyfélszálához tartozó visszárurendelések jelennek meg ahol a **Levonás azonosítója** mező üres.
        - *Nem* – A lapon az ügyfélszámlához tartozó értékesítési rendelések jelennek meg ahol a **Levonás azonosítója** mező üres.

1. Válassza ki az **OK** lehetőséget. A **Levonás azonosítója** mező az értékesítési jóváírás fejlécében van beállítva.

Miután a jóváírás csatolva lett a levonáshoz megtekintheti a levonás munkaterület **Nyitott tranzakciók** szakaszában található **Jóváírás megnyitása** gomb használatával is.

A jóváírás számlázása és a levonás jóváhagyása után a jóváírás megjelenik a levonás munkaterület **Nyitott tranzakciók** szakaszában a megfelelő **Levonásazonosító** értékével szemben, és az **Igény típusa** mezőjének értéke *Egyéb jóváírás*.

#### <a name="detach-a-credit-from-the-deduction"></a>Jóváírás leválasztása a levonásról

Ha a hibás jóváírás van csatolva, akkor le lehet leválasztani a levonásról. A Műveleti panel **Karbantartás** csoportjában válassza a **Levonás leválasztása jóváírásról** menüpontot. A **Levonás azonosítója** érték el lett távolítva a jóváírásból.

A **Levonás leválasztása a jóváírásról** gomb csak akkor érhető el, ha teljesülnek a következő feltételek:

- A levonáshoz jóváírás tartozik.
- Az **Igény állapota** mező *Nyitott* értékre van állítva.

## <a name="create-a-one-time-promotion"></a>Egyszeri promóció létrehozása

Előfordul, lehet, hogy nincs egy jóváhagyott visszatérítése, amelyhez egyeztetni lehet a levonást. Ebben az esetben használható az *egyszeri promóció* szolgáltatás, amellyel egyeztethető a levonás a promócióhoz, amely társítva van az ügyfélhez. Az *egyezeri promóció* létrehoz egy új promóciós engedménymegállapodás és az egyösszegű árusítási eseményt. Majd az egyösszegű fizetést a levonás összegéhez egyezteti, és elkészíti a feladásokat, amelyek szükségesek a levonást lezárásához.

Ez a funkció akkor hasznos, ha a promóciós engedményeket használ. A promóciókkal kapcsolatos további tudnivalókat lásd: [Promóciós engedmények kezelése](../sales-marketing/trade-allowance.md).

Először be kell állítania egy sablont az új promóciós engedménymegállapodás létrehozására használható. A sablon beállításához kövesse az alábbi lépéseket:

1. Ugrás az **Értékesítés és marketing \> Promóciós engedmények \> Sablonok** helyre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A mezőkben adja meg az adatokat, amelyek jelenjenek meg a sablon alapján létrejövő megállapodásokon.
1. Válasszon egy hierarchiaszintet a **Vevők** gyorslapon a **Hierarchia** mezőben.
1. Válassza ki a hierarchialistában azt a vevőt, akinél nem egyeztetett levonás szerepel, majd válassza a jobbra nyíl gombot (**\>**). A vevő felkerül a **Promóciós engedmény megállapodással rendelkező vevők** listájára.
1. Állítsa be a szükséges további mezőket, majd zárja be az oldalt.
1. Ugrás az **Értékesítés és marketing \> Beállítása \> Promóciós engedmények \> Promóciós engedmények kezelési paraméterei** menüpontba.
1. Az **Áttekintés** lap **Egyszeri promóciósablon mezőjében** válassza ki annak a sablonnak a nevét, amely az egyszeri promóciók létrehozásához használna.

Ezt követően hozzon létre egy egyszeri promóciót a levonási munkaterületen. Egyszeri promóció létrehozásához tegye a következőket.

1. Menjen a **Kereskedelem és marketing \> Kereskedelmi kedvezmények \> Levonások \> Levonás munkaterület** menübe.
1. Az levonás feldolgozásához jelölje be a **Megjelölés** jelölőnégyzetet mellette.
1. A műveletpanelen válassza a **Karbantartás \> Levonás kiegyenlítése egyszeri promócióként** lehetőséget.
1. Az **Egyszeres promóció** párbeszédpanelen a következő lépésekkel lehet a levonást egy vagy több alaphoz társítani:

    1. Válassza az **Új** elemre, és az **Alap azonosítója** mezőben válasszon ki egy alapazonosítót. Ismételje meg ezt a lépést szüksége az igény szerinti számú alap hozzáadásához.
    1. Az egyes alapazonosítók melletti **Százalék** mezőbe adja meg a levonás százalékát az alap hozzárendeléséhez. A **Százalék** mezőkben megadott mennyiségek összegének 100 százaléknak kell lennie.

1. Válassza ki az **OK** lehetőséget. A rendszer létrehoz egy új promóciós engedménymegállapodást, amely egyösszegű árusítási eseménnyel rendelkezik és az egyösszegű fizetést a levonásnak megfelelteti.

## <a name="do-a-mass-update-of-deductions"></a>Végezzen tömeges frissítési levonást

Ha több levonásnál kell módosításokat eszközölnie, kijelölheti azokat a levonásokat és tömegesen frissítheti a mezőiket.

A tömeges frissítés végrehajtásához kövesse az alábbi lépéseket.

1. Menjen a **Kereskedelem és marketing \> Kereskedelmi kedvezmények \> Levonások \> Levonás munkaterület** menübe.
1. A műveleti ablak alatti **Megjelenítés** mezőben, tekintheti meg a levonás típusait.
1. Az egyes frissíteni kívánt levonások mellett jelölje be a jelölőnégyzetet. Majd válassza a Műveleti ablaktáblán a **Karbantartás \> Tömeges frissítés** lehetőséget.
1. A **Tömeges frissítés** párbeszédpanel megjeleníti a kiválasztott levonásokat. Szükség szerint frissítse a mezőket, majd a módosítások elfogadásához kattintson az **OK** gombra.
