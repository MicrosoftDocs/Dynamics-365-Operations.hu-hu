---
title: Falhoz helyez – üzletbe helyez
description: Ez a témakör Falhoz helyez – üzletbe helyez funkciót ismerteti. Ez a funkció lehetővé teszi olyan esetek kezelését, amikor konfigurálható feltételek alapján kell konszolidálni egy termékeket egy előrecsomagolt előkészítő területre. Segít csökkenteni a kitárolási időt, mivel ez lehetővé teszi a kitárolást egyetlen cél azonosítótáblára, és a fürtök kitárolásánál több betárolási pozíciót is alkalmazhat.
author: Mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationType, WHSLocationProfile, WHSLocation, WHSPackProfile, WHSWaveStepCode, WHSOutboundSortTemplate, WHSPostMethod, WHSWaveTemplateTable, WHSLocDirTable, WHSWorkClass, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: cf34a61d0b3f784b5a424473588d05bf8703635c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823287"
---
# <a name="put-to-wall---put-to-store"></a>Falhoz helyez – üzletbe helyez

[!include [banner](../includes/banner.md)]

A *Falhoz helyez – üzletbe helyez* funkció lehetővé teszi olyan esetek kezelését, amikor konfigurálható feltételek alapján kell konszolidálni egy termékeket egy előrecsomagolt előkészítő területre. Mivel ez a funkció lehetővé teszi a kitárolást egyetlen cél azonosítótáblára, és több betárolási pozíciót is alkalmazhat, mint a fürtök kitárolása esetén, az üzletekbe szállító vagy kis cikkeket kezelő vállalatok számára előnyös a lecsökkent kitárolási idő.

A funkció munkafolyamata egy rendezési helyre irányítja a kitárolt terméket a különböző típusú tárolókba történő elosztásra. A rendezési helyek általában több különböző rendezési pozíciót is tartalmaznak. Minden rendezési pozíció az üzleti folyamat által meghatározott feltételek szerint van hozzárendelve. A jellemző feltételek a végső rendeltetési hely, szállítmány vagy rakomány. A termék beérkezésekor az el lesz osztva az egyes rendezési pozíciókhoz a rendeléshez társított mennyiség, a célállomás, a szállítmány vagy rakomány alapján. Ha egy tároló megtelt vagy teljes, akkor a program az üzleti folyamattól függően egy előkészítési helyre vagy egy szállítási helyre helyezi át a további kezelésre.

Ezt a raktározási funkciót más néven is említik, például „pu-to-light” vagy „break opens”.

## <a name="turn-on-the-outbound-sorting-feature"></a>A Kimenő rendezés funkció bekapcsolása

A *Falhoz helyez – üzletbe helyez* funkció használata előtt be kell kapcsolni a *Kimenő rendezés* funkciót a rendszerben. A rendszergazdák használhatják a [Funkciókezelés](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) munkaterületet a funkció állapotának ellenőrzéséhez, és szükség esetén bekapcsolásához. A funkció a következő módon jelenik meg:

- **Modul:** *Raktárkezelés*
- **Szolgáltatás neve:** *Kimenő rendezés*

Ha be van kapcsolva, a *Kimenő rendezés* funkció együtt használható a *Szervezeti szintű hullámlépéskód* funkcióval. Akkor is be kell kapcsolnia ezt a funkciót, ha a hullámlépéskódokban található előre meghatározott lépéskódokat fogja használni. A **Funkció kezelése** munkaterületen ez a funkció a következő módon van listázva:

- **Modul:** *Raktárkezelés*
- **Funkció neve:** *Szervezeti szintű hullámlépéskód*

## <a name="setup"></a>Beállítás

Ehhez a demóhoz a szabványos Contoso-adatok és a *62-es* raktár használatos. Néhány később említett kiegészítő is használatban van.

### <a name="location-type"></a>Hely típusa

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helytípusok** pontra.
1. A művelet ablaktáblán válassza az **Új** parancsot a rendezéshez használandó új helytípus létrehozásához.
1. Adja meg az alábbi értékeket:

    - **Hely típusa:** *SORT*
    - **Leírás:** *Rendezés*

1. Válassza a **Mentés** lehetőséget.

### <a name="warehouse-management-parameters"></a>Raktárkezelési paraméterek

1. Lépjen a **Raktárkezelés \> Beállítás \> Raktárkezelési paraméterek** részre.
1. Az **Általános** lap **Helytípusok** gyorslapján állítsa be a **Rendezési hely típusa** mezőt *SORT* értékre.
1. Válassza a **Mentés** lehetőséget.

### <a name="location-profile"></a>Helyprofil

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyprofilok** pontra.
1. A művelet ablaktáblán válassza az **Új** parancsot a rendezési hely új helyprofiljának létrehozásához.
1. A fejlécben állítsa be a következő értékeket:

    - **Helyprofil azonosítója:** *Rendezés*
    - **Név:** *Rendezés*

1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - **Helyformátum:** *PACK*
    - **Hely típusa:** *SORT*
    - **Azonosítótábla-követés használata:** *Igen*
    - **Vegyes cikkek engedélyezése:** *Igen*
    - **Vegyes készletállapotok engedélyezése:** *Igen*

1. Válassza a **Mentés** lehetőséget.

### <a name="locations"></a>Helyek

1. Ugorjon a **Raktárkezelés \> Beállítás \> Raktár \> Helyek pontra**.
1. Törölje a jelet az **Ellenőrző számjegyek létrehozása a helyhez** jelölőnégyzetből.
1. A Művelet panelen válassza az **Új** lehetőséget, majd állítsa be a következő értékeket:

    - **Raktár:** *62*
    - **Hely:** *Rendezés*
    - **Helyprofil azonosítója:** *Rendezés*

1. Válassza a **Mentés** lehetőséget.

### <a name="packing-profiles"></a>Csomagolási profilok

1. Ugorjon a **Raktárkezelés \> Beállítás \> Csomagolás \> Csomagolási profilok** pontra.
1. A Művelet panelen válassza az **Új** lehetőséget, majd állítsa be a következő értékeket:

    - **Csomagolási profil azonosítója:** *Rendezés*
    - **Leírás:** *Rendezés*
    - **Tároló csomagolási házirendje:** Hagyja üresen ezt a mezőt.
    - **Tároló-azonosító mód:** *Automatikus*
    - **Tároló típusa:** *PALLET 48X48*
    - **Tároló automatikus létrehozása a tároló zárásakor:** Hagyja üresen ezt a mezőt.

1. Válassza a **Mentés** lehetőséget.

### <a name="wave-step-codes"></a>Hullámlépéskódok

Ha be van kapcsolva a *Szervezeti szintű hullámlépéskód:* funkció, állítsa be a következő kódot.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámlépéskódok** pontra.
1. A Művelet panelen válassza az **Új** lehetőséget, majd állítsa be a következő értékeket:

    - **Hullámlépés kódja:** *Rendezés*
    - **Hullámlépés leírása:** *Rendezés*
    - **Hullámlépés típusa:** *Rendezési sablon*

1. Válassza a **Mentés** lehetőséget.

### <a name="outbound-sorting-template"></a>Kimenő rendezési sablon

A rendezési sablon határozza meg, hogy a rendezési pozíciók létrejönnek-e, milyen feltételek vannak használatban, valamint a rendezési folyamat egyéb attribútumait.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Csomagolás \> Kimenő rendezési sablonok** helyre.
1. Jelölje be a műveleti ablakban az **Új** lehetőséget a rendezési sablon létrehozásához.
1. Az új sablon fejlécében adja meg a következő értékeket:

    - **Kimenő rendezési sablon azonosítója:** *Hullámrendezés*
    - **Leírás:** *Hullámrendezés*
    - **Rendezési sablon típusa:** *Hullámigény*

        Ez a mező azt a folyamatot határozza meg, amelyhez a rendezési sablon használatban van. A következő értékek állnak rendelkezésre:

        - **Hullámigény** – Ez a rendezési sablon a *Falhoz helyez* folyamathoz használatos. Ez a sablontípus a csomagolási állomás kihagyására szolgál, és közvetlenül a hullámból dolgozza fel a készletet. Ez a típus csak akkor használható, ha a hullámsablonban szerepel a **rendezés** hullámfeldolgozási mód.
        - **Tároló** – A rendezési sablon, amely a *Raklapösszeállítás csomagolás után* folyamathoz használatos. Ezt a sablontípust olyan tárolók feldolgozására használják, amelyek az adott csomagolóhelyen le vannak zárva, és raklapokra kell rendezni őket.

    - **Raktár:** *62*
    - **Hely:** *Rendezés*

1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - **Rendezés ellenőrzés:** *Pozíció beolvasása*

        Ez a mező határozza meg a rendezés során szükséges ellenőrzést. A következő értékek állnak rendelkezésre:

        - None
        - Azonosítótábla beolvasása
        - Pozíció beolvasása

    - **Munka létrehozása a pozíció lezárásakor:** *Igen*

        Ha ennek a beállításnak az értéke *Igen* akkor munka jön létre, amikor a pozíció le van zárva, hogy a készletet a végső szállítási helyre mozgassák. Ha *Nem* értékre van állítva, akkor a készletet azonnal kitárolják a rendeléshez a pozíció lezárásakor.

    - **Pozíció hozzárendelése:** *Manuális*

        Ez a mező a pozíció-hozzárendelés típusát határozza meg. A következő értékek állnak rendelkezésre:

        - **Manuális** – A felhasználónak mindig meg kell adnia, a készlet melyik pozíciójához kell rendezni.
        - **Automatikus** – A rendszer automatikusan egy pozícióhoz irányítja a készletet, ha lehetséges, a rendezési sablontörések alapján.

    - **Rendezésipozíció-feltétel hozzárendelése:** *Csak üres pozíció használata*

        Ez a mező azt szabályozza, hogy a rendezési pozícióknál már meglévő készletet figyelembe kell-e venni egy pozíció igényhez való hozzárendelésekor. A következő értékek állnak rendelkezésre:

        - **Csak üres pozíció használata** – Az olyan pozíciók, amelyekhez már van készlet társítva figyelembe lesznek véve
        - **Ürespozíció feltételezése** – A pozícióban már szereplő összes készletet figyelmen kívül hagyja a rendszer. Minden rendelkezésre álló pozíció használva lesz.

    - **Hullámlépés kódja:** *Rendezés*

        Ha be van kapcsolva a *Szervezeti szintű hullámlépéskód* funkció, akkor a *Rendezés* hullámlépéskódot is be kell állítani.

    - **Rendezési pozíció automatikus lezárása:** *Igen*

        Ha ez a beállítás *Igen* értékre van állítva akkor a program automatikusan lezárja a rendezési pozíciót, amikor a pozícióhoz érkező összes munka be van fejezve.

    - **Rendezési pozíciók száma:** *3*

        Ez a mező határozza meg a rendszer által létrehozott rendezési pozíciók maximális számát.

    - **Rendezési pozíció előtagja:** *SP-*

        Ez a mező határozza meg, hogy melyik előtagot rendeli hozzá a rendszer a pozíció száma elé.

    - **Rendezési pozíció automatikus csomagolása:** *Igen*

        Ha ez a beállítás *Igen* értékre van állítva, akkor a program a rendezési pozíció készletét egy tárolóba csomagolja, amikor a pozíció le van zárva.

    - **Csomagolási profil azonosítója:** *Rendezés*

        Ez a mező határozza meg a csomagolási profilt, amelyet akkor kell használni, amikor a rendezési pozíciót egy tárolóba csomagolják.

1. A művelet ablaktáblán válassza a **Lekérdezés szerkesztése** elemet a rendezési sablonhoz használt feltételek megadásához.
1. A lekérdezés párbeszédpanel **Rendezés** lapján válassza az **Új** parancsot egy sor hozzáadásához, majd állítsa be a következő értékeket:

    - **Tábla:** *Rakomány részletei*
    - **Származtatott tábla:** *Rakomány részletei*
    - **Mező:** *Szállítmány azonosítója*
    - **Keresés iránya:** *Növekvő*

1. Válassza ki az **OK** lehetőséget.
1. A következő üzenet jelenhet meg: „A csoportosítás alaphelyzetbe kerül, folytatja?” Válassza ki az **Igen** lehetőséget.

    Elérhetővé válik a **A kimenő rendezési sablonok szünetei** gomb a műveleti panelen.

1. A műveleti ablaktáblán válassza ki a **Kimenő rendezési sablon szünetekei** lehetőséget.
1. Válassza ki a **Csoportosítás mező szerint** mezőt a csoportosításhoz szállítmányazonosító szerint.

    Ez a beállítás szállítmányként egy rendezési pozíciót hoz létre, amely a hullámban tárolóként jelenik meg.

1. Válassza ki az **OK** lehetőséget.

### <a name="wave-process-methods"></a>Hullámfeldolgozási módok

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámfeldolgozás módszerei** lehetőségre.
1. A Művelet ablaktáblán válassza ki a **Metódusok újragenerálása** elemet.

    A **rendezési** módszert a program hozzáadta a választható metódusok listájához, és *Szállítás* hullámsablontípus van kiválasztva hozzá.

### <a name="wave-templates"></a>Hullámsablonok

A hullámigény rendezéséhez használt hullámsablon szerkesztése.

1. Ugorjon a **Raktárkezelés \> Beállítás \> Hullámok \> Hullámsablonok** pontra.
1. A **Hullámsablontípus** mezőt állítsa *Szállítás* értékre.
1. Válassza ki a meglévő **62 Szállítási alapértelmezett** sablont.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Az **Általános** gyorslapon végezze el a következő módosításokat:

    - Állítsa a **Hullám feldolgozása a raktárba történő kiadáskor** lehetőséget *Nem* értékre.
    - Állítsa a **Hozzárendelés nyitott hullámokhoz** beállítást *Igen* értékre.

1. A **Metódusok** gyorslapon állítsa be a **rendezés** metódust:

    1. A **Fennmaradó metódusok** rácsban válassza a **rendezés** elemet.
    2. Válassza ki a jobbra nyíl gombot, hogy a **rendezés** elemet áthelyezze a **Kiválasztott metódusok** rácsra.
    3. A **Kiválasztott metódusok** rácsban válassza a **rendezés** elemet.
    4. A **Hullámlépéskód** mezőt állítsa *Rendezés* értékre.

1. Válassza a **Mentés** lehetőséget.

### <a name="mobile-device-menu-items"></a>Mobileszköz menüpontjai

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz-menüelemek** részre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A fejlécben állítsa be a következő értékeket:

    - **Menüelem neve:** *Rendezés*
    - **Cím:** *Rendezés*
    - **Mód:** *Közvetett*
    - **Meglévő munka használata:** *Nem*

1. Az **Általános** gyorslapon állítsa be a következő értékeket:

    - **Tevékenységkód:** *Kimenő rendezés*
    - **Feldolgozási útmutató használata:** *Igen* (alapértelmezett érték)
    - **Kimenő rendezési sablon azonosítója:** *Hullámrendezés*

1. Válassza a **Mentés** lehetőséget.

### <a name="mobile-device-menu"></a>Mobileszköz menü

1. Lépjen a **Raktárkezelés \> Beállítás \> Mobileszköz \> Mobileszköz menü** elemre.
1. A menük listáján válassza a **Kimenő** elemet.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. A **Rendelkezésre álló menük és menüelemek** rácsban keresse meg és válassza ki az imént létrehozott **Rendezés** menüelemet.
1. Válassza a jobbra mutató nyilat a **Rendezés** áthelyezéséhez a **Menü struktúra** rácsba. Ily módon hozzáadja az új menüelemet a **Kimenő** menühöz.
1. Válassza a **Mentés** lehetőséget.

### <a name="location-directives"></a>Helyutasítások

Létre kell hoznia egy helyirányelvet a rendezés befejezését követően létrejövő munka irányításához.

1. Ugrás a **Raktárkezelés \> Beállítás \> Helyutasítások** elemre.
1. A **Munkarendelés típusa** mezőben válassza ki a *Rendezett készletkitárolás* elemet.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A fejlécben állítsa be a következő értékeket:

    - **Sorozat:** *1*
    - **Név:** *Kitárolás raktárajtóhoz*

1. A **Helyutasítások** gyorslapon állítsa be a következő értékeket:

    - **Munka típusa:** *Eltárolás*
    - **Telephely:** *6*
    - **Raktár:** *62*
    - **Utasításkód:** Hagyja üresen ezt a mezőt.
    - **Több termékváltozat:** *Nem*

1. A **Mentés** gombra kattintva elérhetővé válik a **Sorok** gyorslap.
1. Válassza a **Sorok** gyorslap **Új** elemét, majd állítsa be a következő értékeket. Az összes többi mezőben hagyja meg az alapértelmezett értékeket.

    - **Sorszám:** *1*
    - **Kezdő mennyiség:** *0*
    - **Záró mennyiség:** *1000000*

1. A **Mentés** gombra kattintva elérhetővé válik a **Helyutasítási műveletek** gyorslap.
1. Válassza a **Helyutasítás-műveletek** gyorslap **Új** elemét, majd állítsa be a következő értékeket. Az összes többi mezőben hagyja meg az alapértelmezett értékeket.

    - **Sorszám:** *1*
    - **Név:** *Baydoor*

1. A **Mentés** gombra kattintva teheti elérhetővé a **Lekérdezés szerkesztése** gombot a **Helyutasítások műveletei** gyorslapon.
1. A **Helyutasítás műveletei** gyorslapon válassza a **Lekérdezés szerkesztése** lehetőséget.
1. A lekérdezési párbeszédpanel **Tartomány** lapján keresse meg azt a sort, amelynél a **Mező** mező értéke *Hely*. Ennek a sornak a **Feltételek** mezőjét állítsa *Baydoor* értékre.
1. A szerkesztés megerősítséséhez kattintson az **OK** lehetőségre.

### <a name="work-classes"></a>Munkaosztályok

1. Ugorjon a **Raktárkezelés \> Beállítás \> Munka \> Munkaosztályok** pontra.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A fejlécben állítsa be a következő értékeket:

    - **Munkaosztály azonosítója:** *Rendezés*
    - **Leírás:** *Rendezés*
    - **Munkarendelés típusa:** *Rendezett készletkitárolás*

1. Válassza a **Mentés** lehetőséget.

### <a name="work-templates"></a>Munkasablonok

1. Lépjen ide: **Raktárkezelés \> Munka \> Munkasablonok**.
1. A **Munkarendelés típusa** mezőben válassza ki az *Értékesítési rendelések* elemet.
1. A rácsban válassza ki a **62 kitárolás csomagoláshoz** munkasablont.
1. A Műveleti ablaktáblán kattintson a **Munkafejléc-törések** elemre.
1. A műveleti ablaktáblán válassza a **Szerkesztés** lehetőséget.
1. Törölje a jelet a **Csoportosítás ezen mező szerint** jelölőnégyzetből abban a sorban, amelyen a **Mezőnév** mező be van állítva a *szállítmány azonosítójára*.
1. Válassza a **Mentés** parancsot , majd zárja be a **Munkafejléc-törések** párbeszédpanelt.
1. A **Munkarendelés típusa** mezőben válassza ki a *Rendezett készletkitárolás* elemet.
1. Válassza az **Új** lehetőséget egy munkasablon létrehozásához.
1. Az **Áttekintés** szakaszban állítsa be a következő értékeket. Az összes többi mezőben hagyja meg az alapértelmezett értékeket.

    - **Munkasablon:** *Rendezett kitárolás*
    - **Munkasablon leírása:** *Rendezett kitárolás*

1. A **Mentés** gombra kattintva elérhetővé válik a **Munkasablon részletei** szakasz.
1. A **Munkasablon részletei** részben két sort fog létrehozni. Válassza az **Új** lehetőséget, majd állítsa be a következő értékeket az 1. sorhoz:

    - **Munka típusa:** *Kitárolás*
    - **Kötelező:** Kiválasztva (= *Igen*)
    - **Munkaosztály azonosítója:** *Rendezés*

1. Válassza ismét az **Új** lehetőséget, majd állítsa be a következő értékeket az 2. sorhoz:

    - **Munka típusa:** *Eltárolás*
    - **Kötelező:** Kiválasztva (= *Igen*)
    - **Munkaosztály azonosítója:** *Rendezés*

1. Válassza a **Mentés** lehetőséget.

## <a name="example-scenario"></a>Példaforgatókönyv

Ez a forgatókönyv szimulálja azt a helyzetet, amikor a raktár kis cikkeket tárol helyeken, és ezeket a csomagolás előtt dobozokba kell csomagolni, és a csomagolási állomás funkciói nem megfelelő. A dolgozók a kitárolási sebesség növelése érdekében egyszerre több vevőhöz és különböző címekhez tartozó rendeléseket vesznek fel. A kitárolás befejezése után a dolgozók megérkeznek a rendezési helyre, ahol a kitárolt cikkek a szükséges feltételek alapján rendezhetők a megfelelő dobozokba. Ebben a példában a szállítmányazonosító a megfelelő mező meghatározására szolgál, mivel minden szállítmányhoz más cím tartozik. Miután a rakomány minden cikkét becsomagolták és szállítmány szerint rendezték, a dobozok átkerülnek az előkészítő területre, majd egy teherautóra rakodják azokat.

A forgatókönyv elkezdése előtt győződjön meg arról, hogy az összes standard raktári funkció helyesen van beállítva a raktárban. Erre a célra a *62-es* szabványos Contoso raktár használatos. A szokásos konfigurációk nem változtak a beállításban ismertetetteken kívül.

### <a name="create-demand"></a>Igény létrehozása

A funkcionalitás bemutatása előtt létre kell hoznia igényt. Ehhez a forgatókönyvhöz három értékesítési rendelést hoz létre három különböző vevő számára, hogy szimulálja a különböző szállítási címeket. Ily módon három külön szállítmányt fog létrehozni.

Az értékesítési rendelések és szállítmányok létrehozása előtt meg kell győződnie arról, hogy a kitárolási helyek elegendő készlettel rendelkeznek az értékelési rendelésekben található minden cikkhez. A helyutasítás beállítás áttekintésével erősítse meg, hogy melyik kitárolási helyeket használja az értékesítési rendelések kitároláshoz. Ha módosítania kell a készletet, akkor manuális mozgásokat hozhat létre, felhasználhatja a feltöltést, vagy bármilyen egyéb folyamatot alkalmazhat. Majd foglalja le a készletet.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Értékesítési rendelés létrehozásához az 1. rendeléshez kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Vevő:** *USA-001*
    - **Raktár:** *62*

1. Válassza ki az **OK** lehetőséget.
1. A program új sort ad hozzá az **Értékesítési rendelés sorai** gyorslaphoz. Adja meg az alábbi értékeket:

    - **Cikkszám:** *A0001*
    - **Mennyiség:** *5*

1. Válassza ki a **Sor hozzáadása** lehetőséget egy második sort hozzáadásához, és állítsa be a következő értékeket:

    - **Cikkszám:** *A0002*
    - **Mennyiség:** *10*

1. A következő lépések ismételje meg a rendelés minden értékesítési sorához, hogy készletet foglaljon azokhoz:

    1. Az **Értékesítési rendelés sorai** gyorslap **Készlet** menüjében válassza a **Foglalás** lehetőséget.
    1. A **Foglalás** lapon válassza ki az **Adag foglalása** elemet, majd zárja be az oldalt.
    1. Válassza a **Mentés** lehetőséget.

1. Értékesítési rendelés létrehozásához az 2. rendeléshez kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Vevő:** *USA-004*
    - **Raktár:** *62*

1. Válassza ki az **OK** lehetőséget.
1. A program új sort ad hozzá az **Értékesítési rendelés sorai** gyorslaphoz. Adja meg az alábbi értékeket:

    - **Cikkszám:** *A0001*
    - **Mennyiség:** *7*

1. Válassza ki a **Sor hozzáadása** lehetőséget egy második sort hozzáadásához, és állítsa be a következő értékeket:

    - **Cikkszám:** *A0002*
    - **Mennyiség:** *3*

1. A következő lépések ismételje meg a rendelés minden értékesítési sorához, hogy készletet foglaljon azokhoz:

    1. Az **Értékesítési rendelés sorai** gyorslap **Készlet** menüjében válassza a **Foglalás** lehetőséget.
    1. A **Foglalás** lapon válassza ki az **Adag foglalása** elemet, majd zárja be az oldalt.
    1. Válassza a **Mentés** lehetőséget.

1. Értékesítési rendelés létrehozásához az 3. rendeléshez kattintson az **Új** elemre.
1. Az **Értékesítési rendelés létrehozása** párbeszédpanelen adja meg a következő értékeket:

    - **Vevő:** *USA-007*
    - **Raktár:** *62*

1. Válassza ki az **OK** lehetőséget.
1. A program új sort ad hozzá az **Értékesítési rendelés sorai** gyorslaphoz. Adja meg az alábbi értékeket:

    - **Cikkszám:** *A0001*
    - **Mennyiség:** *8*

1. Készlet foglalásához értékesítési sorhoz kövesse az alábbi lépéseket:

    1. Az **Értékesítési rendelés sorai** gyorslap **Készlet** menüjében válassza a **Foglalás** lehetőséget.
    1. A **Foglalás** lapon válassza ki az **Adag foglalása** elemet, majd zárja be az oldalt.
    1. Válassza a **Mentés** lehetőséget.

Hajtsa végre a következő eljárást, hogy minden értékesítési rendelést a raktárba bocsásson. Három különböző szállítmány jön létre. Ezt követően mindhárom szállítmányt egy új hullámba fogja hozzáadni.

1. Ugorjon az **Értékesítés és marketing \> Értékesítési rendelések \> Minden értékesítési rendelés** pontra.
1. Válassza ki a rácsban az elsőként létrehozott értékesítési rendelést.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Kiadás raktárba** lehetőséget.

    Olyan tájékoztató üzenet érkezik, amely az adott kiadásból létrehozott hullámazonosítót és szállítási azonosítót jeleníti meg.

1. Ismételje meg a korábbi lépéseket a 2. és 3. értékesítési rendeléseknek a raktárba történő kiadásához. Figyelje meg, hogy a kapott tájékoztató üzenet azt jelzi, hogy a 1. értékesítési rendelés létrehozásakor létrehozott hullámhoz szállítmány lett hozzáadva.
1. Ugorjon a **Raktárkezelés \> Kimenő hullámok \> Szállítmányhullámok \> Minden hullám** menübe.
1. Válassza ki azt a hullámazonosítót, amelyet az értékesítési rendelések kiadásával hoztak létre a **Hullámok** oldal megnyitásához. Ez a lap a hullám részleteit jeleníti meg. A **Hullámsorok** gyorslap a létrehozott szállítmányokat jeleníti meg.

    Most létre kell hoznia azt a munkát, amellyel a cikkeket a kitárolási helyekről a rendezési helyre viszi.

1. A Művelet ablaktáblán válassza ki a **Folyamat** elemet.

    A hullám feldolgozásakor a rendezési metódus a rendezési sablon alapján rendeli hozzá a készletet a rendezési pozíciókhoz. A hullám feldolgozásának befejezését követően egy tájékoztató üzenetet kap, jelezve, hogy a rendszer létrehozta a munkát, és feladta a hullámot.

1. A műveleti ablaktábla **Hullám** lapján a **Kapcsolódó információ** csoportban válassza ki a **Munka** elemet a létrehozott munka megjelenítéséhez. Jegyezze fel a munkaazonosítót
1. Nyissa meg a **Raktárkezelés \> Csomagolás és tárolólétrehozás \> Kimenő rendezésipozíció-hozzárendelések** lehetőséget.
1. A bal oldali oszlopban megtekinthetők az egyes szállítmányokhoz létrehozott kimenő rendezésbeosztások.
1. A **Rendezési pozíció feltételei** gyorslapon megtekintheti a pozícióhoz tartozó szállítmányazonosítót.

Egy munkaazonosító lett létrehozva amely a cikkeket a kitárolási helyekről a rendezési helyre viszi. A munka befejezéséhez szüksége lesz a hullámfeldolgozás során létrehozott munkaazonosítóra.

### <a name="sales-order-picking-to-the-sorting-location"></a>Értékesítési rendelés kitárolása a rendezési helyre

1. Jelentkezzen be a *62*-es raktárba felhasználóként a mobileszközön.
1. Válassza a főmenü **Kimenő** elemét.
1. Válassza a **Kimenő** menü **Értékesítési kitárolás** elemét.
1. Válassza ki az **Azonosító** mezőt, majd írja be a munkaazonosítót a hullámfeldolgozásból.
1. Hagyja jóvá a bejegyzést.

    Ezután a program megkérdezi, hogy meg szeretné-e adni a cél azonosítótáblát (AT). Figyelje meg, hogy az 1. értékesítési rendelés 1. sorát kell kitárolni és hozzáadni a cél azonosítótáblához. Megjelenik a cikkszám, a mennyiség, a cikk leírása és a kitárolási hely.

1. A **Cél AT** mezőben adja meg a cél azonosítótábla-számát.

    A feldolgozott hullámban létrehozott összes sort ugyanarra a cél azonosítótáblára tárolja ki.

1. Hagyja jóvá a bejegyzést.

    A mobilalkalmazás most egy sor olyan **Kitárolási** lapot jelenít meg, amelyek a kitárolási helyre irányítják, és a cikkre és a mennyiségre, amelyet ki kell tárolni. A kitárolt cikk az azonosítótáblához történő hozzáadása után jóváhagyja a kitárolási munkát. Az utolsó oldal az a munka, amellyel a kitárolt elemeket a rendezési helyre helyezi.

1. Erősítse meg az első kitárolási munkát.
1. Megjelenik a következő kitárolási munka. Erősítse meg a kitárolást.
1. Folytassa a hátralévő kitárolási munka jóváhagyásával.
1. Az utolsó lépés a kitárolási munka végrehajtása. Nyugtázza az elraktározást a rendezési helyre.

    A „Munka befejezve” üzenet jelenik meg.

1. Lépjen ki az **Értékesítési kitárolásból** a mobilalkalmazásban.

### <a name="sortingput-to-wall"></a>Rendezés/falra helyezés

Most, hogy az összes készletet áthelyezték a rendezési helyre, azt a helyes rendezési pozícióba kell rendezni.

1. Jelentkezzen be a mobilalkalmazásba.
1. Válassza a főmenü **Kimenő** elemét.
1. Válassza a **Kimenő** menü **Rendezés** parancsát a cikkek rendezésének megkezdéséhez.
1. Az **Azonosítótábla/CON** mezőbe írja be a kitárolt értékesítési rendelési munka cél azonosítótábláját.
1. Hagyja jóvá a bejegyzést.
1. Adja meg az először rendezendő cikkszámot.
1. A rendszer határozza meg a megjelenítendő első rendezési pozíciót. A rendezési pozíció jóváhagyása.
1. A program megkéri, hogy rendeljen-e hozzá egy azonosítótáblát a rendezési pozícióhoz. Válassza ki az **Azonosítótábla** mezőt, adja meg az azonosítótábla számát, majd hagyja jóvá a bevitelt.

    Mivel a rendezési pozíció a szállítmány azonosítójához kapcsolódik, a kitárolt cikkeket a kimenő szállítmányhoz és értékesítési rendeléshez kapcsolódó azonosítótáblára tárolja ki.

    A következő oldalon látható a cikkazonosító, a mennyiség, a rendezési pozíció azonosítója, valamint az „innen” (kitárolás) és a „ide” (rendezés) azonosítótábla azonosítója. A lapon található információk alapján a megadott cikk és mennyiségek rendezhetők a kitárolási azonosítótáblából a rendezési azonosítótáblára.

1. A rendezési pozíció jóváhagyása.
1. Rendezze a cikkeket az első rendezési pozícióba. Ha befejezte a munkát, a rendszer irányítja a következő rendezési pozícióra.
1. Ismételje meg ezt a műveletet a munkarendelésen szereplő összes kitárolt sorhoz. Akkor is ezt a folyamatot kell használni, ha több olyan kitárolási sor van, amelyeknek ugyanaz a cikkszáma.

    Amikor ezt a folyamatot minden cikkre megismétli, a rendszer kiértékeli a feltételt a következő beolvasott cikkből (munkasor), és meghatározza, hogy milyen rendezési pozícióra kell azt eltárolni, A program automatikusan a megfelelő rendezési pozícióba helyezi a cikket. A visszaigazolási beállításoktól függően a rendszer megkéri, hogy hagyja jóvá ezt a műveletet a pozíciószám vagy az azonosítótábla azonosítójának megadásával.

    > [!NOTE]
    > Ha az automatikus rendezés be van kapcsolva, akkor a manuális felülbírálás nem érhető el.

1. Amikor befejezte a munkát, a Microsoft Dynamics 365 Supply Chain Management alkalmazásban nyissa meg a **Kimenő sorba rendezési pozíció-hozzárendelések** lapot a pozíciók állapotának ellenőrzéséhez.

    - Ha a beosztások automatikusan le vannak zárva, akkor a lezárt beosztások megjelenítéséhez válassza a **Lezártak megjelenítése** lehetőséget.
    - Figyelje meg, hogy a rendezési pozíció tranzakciói láthatók. Megjelenik a pozíción keresztül feldolgozott cikk és mennyiség.

    A kimenő rendezési sablon beállítása során, akkor a **Rendezési pozíció automatikus lezárása** beállítást állítsa *Igen* értékre. Ennek megfelelően a program automatikusan lezárja a pozíciót, miután a várt tervezett készletet belehelyezik. A rendezési pozíciók **Lezárt** állapotban vannak, és a rendszer létrehozta a munkát úgy, hogy a rendezett készletet *Raktárajtó* helyre helyezte.

1. Végezze el a rendezett készletkitárolási munkafolyamatot, hogy a készletet a szállítási helyre vigye. Ha a készlet készen áll, akkor a szállítás-visszaigazolja.

> [!NOTE]
> A kiválasztott készlet-kitárolási munka helyes feldolgozásához a mozgatási és berakodási folyamathoz egy olyan mobileszköz-menüelemet kell használni, amely rendelkezik olyan munkaosztály-azonosítóval, amelyben a **Munkarendelés típusa** mező *Kiválasztott készlet kitárolására* értékre van állítva.

### <a name="manually-close-a-position-optional"></a>Pozíció manuális lezárása (nem kötelező)

Ha a rendezési pozíciókat manuálisan kell lezárni, akkor a **Rendezési pozíció automatikus lezárása** beállítást *Nem* értékre kell beállítani , és a zárást végre kell hajtani, mielőtt az árukészletet át lehetne helyezni a raktárajtó területére. A pozíciók a különböző módokon zárhatók le:

- A Raktárkezelés mobilalkalmazáson keresztül:

    - A felhasználó beolvashatja a pozícióban lévő cikkek valamelyikét, majd a beosztást lezárhatja a **Lezárás** lehetőséggel.
    - Ha a felhasználó egy már rendezett tárolót olvas be, akkor egy hibaüzenet jelenik meg. Ugyanakkor a felhasználó továbbra is folytathatja a beosztás lezárását.

- A Microsoft Dynamics 365 Supply Chain Management **Kimenő rendezési pozíció-hozzárendelések** lapján:

    - A felhasználó kiválaszthatja a kimenő rendezési pozíció rekordját, majd kiválaszthatja a **Pozíció lezárása** lehetőséget a műveleti ablaktáblán.

## <a name="tips"></a>Tippek

- A cikkek nem helyezhetők át a pozíciók között, miután hozzárendelték őket egyhez. A rendszer kiértékeli, hogy az egyes cikkekből hány darabnak kell egy adott pozícióhoz kerülnie.
- A rendezési sablon beállítható úgy, hogy a pozíciók lezárása esetén automatikusan létrehozza a tárolókat. Ez a módszer a megadott csomagolási profilon alapuló normál tárolóazonosító-struktúrát fog létrehozni.

> [!IMPORTANT]
> Miután a mozgatási munka létrejött a rendezési helyről, nem szabad érvényteleníteni a munkát. Ellenkező esetben a pozíciót és a konténereket törli a rendszerből, és nem lesznek elérhetők további feldolgozásra. A készletet is eltávolítja a program.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]