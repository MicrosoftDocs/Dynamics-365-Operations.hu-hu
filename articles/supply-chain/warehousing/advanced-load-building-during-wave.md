---
title: Speciális rakomány-összeállítás hullám közben
description: Ez a témakör a speciális hullámrakomány-összeállítással kapcsolatban tartalmaz tájékoztatást, amely összeállítás a hullám-végrehajtás során automatikusan hozzárendeli a szállítmányokat a meglévő hullámokhoz. Ebből következően olyan releváns rakományokat hozhat létre, amelyek a rakománytervezés munkaterületének használata nélkül jelölik a teherautókat.
author: mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPostMethod,WHSWaveTemplateTable,WHSLoadMixGroup,WHSLoadBuildTemplate, WHSWaveTableListPage, TMSLoadBuildTemplateApply, TMSLoadBuildTemplates, TMSLoadBuildTemplateCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 0115d58c059724fddc3d6232d341e10630229fa394e462af96176e75a2a8f86c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773129"
---
# <a name="advanced-load-building-during-wave"></a>Speciális rakomány-összeállítás hullám közben

[!include [banner](../includes/banner.md)]

A speciális hullámrakomány-összeállítás a hullám-végrehajtás során automatikusan hozzárendeli a szállítmányokat a meglévő hullámokhoz. Ebből következően olyan releváns rakományokat hozhat létre, amelyek a rakománytervezés munkaterületének használata nélkül jelölik a teherautókat. Ez a képesség olyan vállalatoknál hasznos, amelyek a rakományok fogalmát a teherautóban/tréleren lévő áruk szállítása céljából szeretnék követni és megtervezni, azonban nem szeretnék mindennap manuálisan létrehozni ezeket a rakományokat.

A hullámfeldolgozás során a rendszer általában új rakományt hoz létre minden olyan szállítmányhoz, amelyhez nincs rakomány hozzárendelve. Ha azonban a speciális hullámrakomány-összeállítás be van kapcsolva, a rendszer minden egyes nem hozzárendelt szállítmányt hozzárendel egy meglévő rakományhoz (ha van megfelelő rakomány), és az új rakományok csak akkor jönnek létre, amikor szükség van rájuk. A speciális hullámrakomány-összeállítás a meghatározott feltételek alapján automatikusan létrehozza az új rakományokat.

A funkció használatához a rendszert a következőképpen kell beállítania:

- Hozzon létre olyan *hullámsablonokat*, amelyek tartalmazzák az új **buildLoads** módszert. Ez a módszer elérhetővé teszi a speciális hullámrakomány-összeállítást a sablonokat használó hullámokhoz.
- Állítsa be a *rakomány-összeállítási sablonokat*, amelyek mindegyike egy adott hullámsablonhoz és metódushoz van hozzákapcsolva. A rakomány-összeállítási sablonok azt irányítják, hogy a hullámhoz rendelt rakománysorok melyik (meglévő vagy új) rakományhoz legyenek hozzáadva. A szállítmányokat olyan feltételek alapján kombinálhatja vagy különítheti el, mint például a rakománysablon, a felszerelések és a rakománysorban szereplő egyéb mezőértékek.
- Határozza meg a *rakománykombinációs csoportokat*, hogy szabályozzák, mely cikkek legyenek és ne legyenek kombinálva egyetlen rakományban. Azt is meg kell adnia, hogy a korlátozásnak figyelmeztetést vagy hibát kell-e jeleznie, és ki kell-e értékelni a rakománysablon térfogatra vonatkozó korlátozását.

## <a name="turn-on-advanced-wave-load-building-in-your-system"></a>A speciális hullámrakomány-összeállítás bekapcsolása a rendszerben

A speciális hullámrakomány-összeállítás használata előtt két funkciót be kell kapcsolni a rendszerben. A rendszergazdák használhatják a [funkciókezelési](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) beállításokat e funkciók állapotának ellenőrzéséhez, és szükség esetén a bekapcsolásához. A **Funkció kezelése** munkaterületen a funkciók a következő módon van listázva:

- Hullámrakomány-összeállítási funkció:

    - **Modul:** *Raktárkezelés*
    - **Funkció neve:** *Hullámrakomány-összeállítási funkció*

- Szervezeti szintű hullámlépéskód:

    - **Modul:** *Raktárkezelés*
    - **Funkció neve:** *Szervezeti szintű hullámlépéskód*

### <a name="make-sample-data-available"></a>A mintaadatok elérhetővé tétele

Ha ezt a bemutatót az itt megadott mintaadatok és értékek alapján kívánja elvégezni, akkor egy olyan rendszert kell használnia amelynél a szokásos [demóadatok](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) telepítve vannak. Emellett az **USMF** jogi személyt is ki kell választani a kezdés előtt.

A bemutatót a gyártási rendszerben végzett munka során a funkció használatához útmutatásként is használhatja. Ebben az esetben azonban a saját értékeit kell helyettesítenie, és előfordulhat, hogy bizonyos típusú kötelező rekordok hiányoznak, amelyeket a szabvány demóadatok biztosítanak.

### <a name="make-sure-that-the-scenario-setup-includes-enough-available-inventory"></a>Győződjön meg róla, hogy a forgatókönyv-beállítás elég elérhető készletet tartalmaz.

Ha az **USMF** bemutató adataival dolgozik, először győződjön meg róla, hogy a rendszer úgy van beállítva, hogy minden fontos helyen elegendő készlet legyen. Ennél a bemutatónál arra lehet számítani, hogy a következő készlet a *62-es* raktárban érhető el:

- **A0001-es cikk:** 10 db
- **A0002-es cikk:** 10 db
- **M9200-as cikk:** 10 ea

Az **M9200-as** cikket hozzá kell adni a raktárhoz. Hajtsa végre a következő alszakaszok eljárásait a cikk-készlet hozzáadásához.

#### <a name="create-a-new-license-plate-id"></a>Új azonosítótábla-azonosító létrehozása

1. Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Raktár** \> **Azonosítótáblák** elemre.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az új sorban az **Azonosítótábla** mezőben adja meg a *LP6203* számsort.
1. Válassza a **Mentés** lehetőséget.

#### <a name="create-a-standard-cost-for-item-m9200-in-site-6"></a>Normál költség létrehozása az M9200-as cikkhez a 6. helyen

1. Kattintson a **Termékinformációk kezelése** \> **Termékek** \> **Kiadott termékek** lehetőségre.
1. Keressen rá a **M9200** cikkre.
1. Válassza ki a cikk sorát, majd kattintson a műveleti ablaktáblán a **Költségkezelés** fülre a **Beállítás** csoportban, és válassza ki a **Cikk ára**  fület.
1. A **Cikk ára** oldalon válassza ki a **Függőben lévő árak** fület.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. Az új sorban állítsa be a következő értékeket:

    - **Költségszámítási típus:** *Tervezett költség*
    - **Ártípus:** *Költség*
    - **Verzió:** *10*
    - **Telephely:** *6*
    - **Ár:** *1,60*

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A műveleti ablaktáblán válassza a **Függő ár(ak) aktiválása** lehetőséget.
1. Válassza ki az **Aktív árak** lapot, és ellenőrizze, hogy a *6.* helyhez az új önköltségi ár hozzá van-e rendelve.

#### <a name="create-inventory-in-warehouse-62"></a>Készlet létrehozása a 62-es raktárban

1. Ugorjon a **Készletkezelés** \> **Naplóbejegyzések** \> **Cikkek** \> **Készletkorrekció** pontra.
1. A Műveleti ablaktáblán kattintson az **Új** elemre.
1. A **Készletnapló létrehozása** párbeszédpanelen az **Áttekintés** gyorslapon a **Raktár** mezőben adja meg a *62-es* értéket. Az összes többi mezőben hagyja meg az alapértelmezett értékeket.
1. Az **OK** gombbal zárja be a párbeszédpanelt.
1. Megnyílik a **Készletkorrekció** lap. A **Naplósorok** gyorslapon válassza ki az **Új** lehetőséget egy sor hozzáadásához.
1. Az új sorban állítsa be a következő értékeket. Az összes többi mezőben hagyja meg az alapértelmezett értékeket.

    - **Cikkszám:** *M9200*
    - **Hely:** *bulk-003*
    - **Mennyiség:** Módosítsa az értéket *10-re*.

1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.
1. A műveleti panelen hibakereséshez válassza ki az **Ellenőrzés** lehetőséget.
1. A **Napló ellenőrzése** párbeszédpanelen kattintson az **OK** gombra az ellenőrzés megkezdéséhez. Üzenet jelenik meg, ha az ellenőrzés befejeződött.
1. A műveleti ablaktáblán válassza a **Feladás** parancsot a készletkorrekció véglegesítéséhez.
1. A **Napló feladása** párbeszédpanelen kattintson az **OK** gombra a feladás megkezdéséhez. Üzenet jelenik meg, ha a feladás befejeződött.

## <a name="set-up-advanced-wave-load-building"></a>Speciális hullámrakomány-összeállítás beállítása

### <a name="regenerate-wave-process-methods"></a>Hullámfeldolgozási metódusok újragenerálása

Előfordulhat, hogy újra kell generálnia a hullámfeldolgozási módszereket, hogy a rakomány-összeállítási módszer (**buildLoads**) elérhető legyen.

1. Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Hullámok** \> **Hullámfeldolgozás metódusai** lehetőségre.
2. Ellenőrizze, hogy a **buildLoads** szerepel-e a listán. Ha nincs megadva, akkor a műveleti ablaktáblán válassza ki a **Metódusok újragenerálása** lehetőséget a hozzáadáshoz.

### <a name="set-up-wave-templates"></a>Hullámsablonok beállítása

Ha ki szeretné használni a hullámrakomány-összeállítás előnyét, akkor mindegyik fontos [hullámsablonban](tasks/configure-wave-processing.md) szerepelnie kell a **buildLoads** metódusnak.

1. Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Hullámok** \> **Hullámsablonok** pontra.
1. Válasszon ki egy hullámsablont.

    Ha az **USMF** bemutatóadatokkal dolgozik, válassza ki a **62-es szállítási alapértelmezett** sablont.

1. A műveleti ablaktáblán válassza ki a **Szerkesztés** parancsot, hogy a lapot szerkesztési módba helyezze.
1. A **Metódusok** gyorslapon, a **Fennmaradó metódusok** rácson válassza ki a **buildLoads** metódust.
1. Válassza ki a jobbra nyíl gombot, hogy a **buildLoads** metódust áthelyezze a **Kiválasztott metódusok** rácsra.
1. Ha hozzá szeretné adni a **Hullámlépés kódja** értéket a **buildLoads** metódushoz, először egy kódot kell létrehoznia a **Hullámlépéskódok** oldalon. Bármilyen érték használható, de ügyeljen arra, hogy jegyezze fel, mert később szüksége lesz rá. Kövesse az alábbi lépéseket a **WSC2112** kód létrehozásához:

    1. A **buildLoads** metódus sorában kattintson jobb gombbal a **Hullámlépés kódja** mező lefelé mutató nyilára, majd válassza ki a **Részletek megtekintése** parancsot.
    1. A **Hullámlépéskódok** lap műveleti paneljén válassza ki az **Új** elemet.
    1. A **Hullámlépés kódja** mezőben adja meg a *WSC2112* értéket.
    1. A **Hullámlépés leírása** mezőben adja meg a *WSC2112* értéket.
    1. A **Hullámlépés típusa** mezőben válassza ki a *Rakomány-összeállítás* elemet.

1. Válassza a **Mentés** gombot, és zárja be az oldalt.
1. A **buildLoads** metódus sorában, a **Hullámlépés kódja** mezőben válassza ki az imént létrehozott kódot (**WSC2112**).
1. A műveleti ablaktáblán válassza a **Mentés** lehetőséget.

> [!NOTE]
> A hullámlépéskódok olyan kódok, amelyeket a felhasználók úgy állíthatnak be és használhatnak, hogy azok a hullámmetódusok meghatározott példányait a megfelelő sablonokhoz kapcsolják. A sablonok tartalmazzák a feltöltéshez, a tárolóra bontáshoz, a címkék nyomtatásához, a rakomány építéséhez és a sorba rendezéshez szükséges sablonokat.
>
> Ha nem használja a hullámlépéskódokat, a felhasználóknak szabad szöveget kell beírniuk ahhoz, hogy a meghatározott sablonra hivatkozzanak a hullámmetódus-példányból. A szabad szövegben előfordulhatnak hibák, mivel a felhasználóknak ellenőrizniük kell, hogy a hullámlépés szövege, amelyet egy meghatározott hullámlépés-metódushoz a hullámsablonban hozzá akarnak adni, megegyezik a hullámlépés szövegével a célsablonban.
>
> Az adott hullámlépéstípus hullámlépéskódjait külön oldalon állítják be. Egy hullámsablon minden hullámlépésmetódus-példányához, amelyhez hullámlépéskód szükséges, egy legördülő listából kell kiválasztani a hullámlépéskódot. A legördülő listában szereplő választék helyettesíti a szabadszöveges bevitelt, így csökkenti az emberi hiba kockázatát és hatását. A beállítási kódok a hullámsablon hullámlépés-metódusának és a metódushoz tartozó célsablon összekapcsolására használatos.

### <a name="set-up-load-mix-groups"></a>Rakománykombinációs csoportok beállítása

A rakománykombinációs csoportok szabályokat határoznak meg az olyan típusú cikkekhez, amelyeket egyetlen rakományon lehet kombinálni. Igény szerint tetszőleges számú rakománykombinációs csoportot beállíthat. A speciális hullámrakomány-összeállítás használatához azonban legalább egyet be kell állítani. Rakománykombinációs csoport létrehozásához kövesse az alábbi lépéseket:

1. Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Rakomány** \> **Rakománykombinációs csoportok** elemre.
1. A rakománycsoport létrehozásához a műveleti ablaktáblán válassza ki az **Új** lehetőséget.
1. A **Rakománykombinációs csoport azonosítója** mezőben adja meg az új csoport nevét.

    Ha az **USMF** bemutatóadatokkal dolgozik, a következő értékeket kell beállítania:

    - **Rakománykombinációs csoport azonosítója:** *TV*
    - **Leírás:** *TV*

1. A műveleti ablaktáblán válassza ki a **Mentés** lehetőséget, ha elérhetővé szeretné tenni a **Rakománykombinációs csoport feltételei** gyorslapot.
1. A **Rakománykombinációs csoport feltételei** gyorslapon válassza ki az **Új** lehetőséget, ha sort szeretne hozzáadni a rácshoz.
1. Az új sorban adja meg a kívánt értékeket az egyes mezőkben. Ezek az értékek határozzák meg, hogy milyen cikkcsoportokat vesznek figyelembe a rakománykombinációhoz.

    Ha az **USMF** bemutatóadatokkal dolgozik, válassza ki a *TV és videó* lehetőséget a **Cikkcsoport** mezőben.

1. A műveleti ablaktáblán válassza ki a **Mentés** lehetőséget, ha elérhetővé szeretné tenni a **Rakománykombinációs csoport megszorításai** gyorslapot.
1. A **Rakománykombinációs csoport megszorításai** gyorslapon válassza ki az **Új** lehetőséget, ha sort szeretne hozzáadni a rácshoz.
1. Az új sorban adja meg a kívánt értékeket az egyes mezőkben.

    Ha az **USMF** bemutatóadatokkal dolgozik, a következő értékeket kell beállítania:

    - **Cikkcsoport:** *CarAudio*
    - **Rakomány-összeállítási művelet:** *Korlátozás* (Ez az érték megakadályozza, hogy azok a cikkek, amelyek a **CarAudio** cikkcsoporthoz tartoznak ugyanabban a rakományban legyenek, mint azok, amelyek a **TV és videó** cikkcsoporthoz tartoznak.)

1. Folytassa a szabályokkal való munkát mindaddig, amíg fel nem vette az összes olyan feltételt és megszorítást, amelyekre a rakománykombinációs csoporthoz szüksége van.

Ha az **USMF** bemutatóadatokkal dolgozik, akkor már befejezte ezt a beállítást.

### <a name="set-up-load-build-templates"></a>Rakomány-összeállítási sablonok beállítása

Igény szerint tetszőleges számú rakomány-összeállítási sablont beállíthat. A speciális hullámrakomány-összeállítás használatához azonban legalább egyet be kell állítani. Rakomány-összeállítási sablon létrehozásához kövesse az alábbi lépéseket:

1. Ugorjon a **Raktárkezelés** \> **Beállítás** \> **Rakomány** \> **Hullámrakomány-összeállítási sablonok** pontra.
1. A műveleti ablakpanelen válassza ki az **Új** lehetőséget, ha hozzá szeretne adni egy sort a rácshoz.
1. Az új sorban állítsa be a következő értékeket:

    | Mező | Leírás | Az USMF bemutatóadatok értéke |
    |---|---|---|
    | Sorszám | Az a rendelés, amelyben a sablon kiértékelése történik. | *1* |
    | Rakomány-összeállítási sablon neve | Adja meg a rakomány-összeállítási sablon egyedi azonosítóját. Adja meg a beállításban korábban létrehozott vagy frissített sablon nevét. | *62-es szállítási alapértelmezett* |
    | Hullámlépés kódja | Adja meg a hullámlépéskódot ahhoz, hogy a sablont hozzákapcsolja egy hullámmetódushoz. A **buildLoads** metódushoz kiválasztott kódot akkor kell megadnia, amikor a hullámsablont ebben a beállításban korábban beállítja. | *WSC2112* |
    | Rakománysablon azonosítója | Válassza ki a rakománysablont az új rakományok létrehozásához és összevetéshez, ha létező rakományokhoz rendelik hozzá őket. A rakománysablon határozza meg, hogy a teljes rakományhoz milyen maximális súlyt és mennyiséget engednek meg. | *Normál rakománysablon* |
    | Berendezés | Berendezés összevetéséhez, amikor létező rakományokhoz rendelnek hozzá értéket, és amikor újonnan létrehozott rakományokat adnak meg. | Ezt a mezőt hagyja üresen. |
    | Rakománykombinációs csoportazonosító | Válassza ki a rakománykombinációs csoportot, amelyet akkor használnak, ha a cikk megengedett a rakományon. A kombinációs csoportok szabályokat határoznak meg az olyan típusú cikkekhez, amelyeket egyetlen rakományon lehet kombinálni. A beállításban korábban létrehozott kombinációs csoportok közül kell egyet kiválasztania. | *TV* |
    | Nyitott rakományok használata | Válassza ki, hogy meglévő nyitott rakományok hozzáadhatók-e. Ehhez a következő lehetőségek állnak rendelkezésre:<ul><li>**Nem** – Nem adható hozzá nyitott rakomány a meglévő rakományokhoz.</li><li>**Bármilyen** – Adjon hozzá nyitott rakományokat bármely meglévő rakományhoz, amely a sor szempontjából érvényes.</li><li>**Hozzárendelt** – Adjon hozzá nyitott rakományokat hullámhoz hozzárendelt rakományhoz.</li></ul> | *Bármely* |
    | Rakományok létrehozása | Határozza meg, hogy kell-e új rakományokat létrehozni, ha a meglévő rakományok nem egyeznek meg a feltételekkel. | Kiválasztva (= *Yes*) |
    | Szállítmánysor megosztásának engedélyezése | Határozza meg, hogy egy rakománysor több rakomány között elosztható-e, ha a teljes sor túllépi a rakománysablon maximális kapacitását. | Törölve (= *Nem*) |
    | Térfogatmérés ellenőrzése | Határozza meg, hogy a rakomány-összeállításnak ellenőriznie kell-e a súlyt és a térfogatot minden rakománysor hozzáadásakor annak biztosítására, hogy a rakománysablon térfogatkorlátozásait ne lépjék túl. | Törölve (= *Nem*) |

1. A műveleti ablaktáblán válassza ki a **Mentés** parancsot, hogy a **Lekérdezés szerkesztése** beállítás elérhető legyen.
1. A műveleti ablaktáblán válassza ki a **Lekérdezés szerkesztése** lehetőséget a lekérdezésszerkesztő párbeszédpanel megnyitásához.
1. A párbeszédpanelen, a **Rendezés** lapon válassza ki a **Hozzáadás** gombot, hogy hozzáadjon egy sort a rácshoz.
1. Az új sorban adja meg a használni kívánt rendezési szabályokat. A következő értékek beállításával például a keresési eredmények növekvő sorrendben rendezhetők a rendelési szám szerint:

    - **Tábla:** *Rakomány részletei*
    - **Származtatott tábla:** *Rakomány részletei*
    - **Mező:** *Rendelés száma*
    - **Keresés iránya:** *Növekvő*

1. Az **OK** gombra kattintva mentse a változtatásokat, és zárja be a párbeszédpanelt.
1. A **Lebontás a következő szerint:** gyorslapon állítsa be a rakományok felosztására vonatkozó szabályokat. Általában a lebontás vonatkozhat a rakománysorra kiterjesztett egyedi mezőkre, ilyen például az **Útvonal**, a **Bemutatás** vagy a **Futtatás**. Ha például rendelésszámonként egy rakományt szeretne létrehozni, válassza ki a **Lebontás a következő szerint:** jelölőnégyzetet a következő értékeket tartalmazó sorban:

    - **Hivatkozási tábla neve:** *Rakomány részletei*
    - **Hivatkozási mező neve:** *Rendelési szám*

## <a name="scenario"></a>Forgatókönyv

Ez a példa azt mutatja be, hogy az ebben a témakörben korábban ismertetett beállítások milyen módon befolyásolják a raktári műveleteket egy értékesítési rendelés feldolgozásakor. Ez a forgatókönyv az **USMF** bemutatóadatokat együtt használja a beállítási útmutatóban megadott egyéb bemutatóértékekkel együtt.

### <a name="create-sales-orders"></a>Értékesítési rendelések létrehozása

1. Ugorjon az **Értékesítés és marketing** \> **Értékesítési rendelések** \> **Minden értékesítési** rendelés pontra.
1. A műveleti ablaktáblán kattintson az **Új** gombra az **Értékesítési rendelés létrehozása** párbeszédpanel megnyitásához.
1. A párbeszédpanelen adja meg a következő értékeket:

    - A **Vevő** gyorslapon adja meg a **Vevőfiók** mezőt az *US-007* számára.
    - Az **Általános** gyorslap **Raktár** mezőjében állítsa be az *62* értéket.

1. Válassza az **OK** gombot a beszerzési rendelés létrehozásához és a párbeszédpanel bezárásához.
1. A program megnyitja az új értékesítési rendelést. Tartalmaznia kell egy új, üres sort az **Értékesítési rendelés sorai** gyorslap rácsán. Az új sorban állítsa be a **Cikkszám** mezőt *A0001* és a **Mennyiség** mezőt *1* értékre.
1. A rács feletti **Készlet** menüben válassza ki a **Foglalás** pontot.
1. A **Foglalás** lap műveleti ablaktáblán válassza ki az **Adag foglalása** elemet.
1. A lap jobb felső sarkában található **Bezárás** gombra (**X**) kattintva térjen vissza az értékesítési rendeléshez.
1. Válassza ki a művelet ablaktáblán a **Raktár** lapon a **Műveletek** csoportjának **Kiadás raktárba** parancsát. A rendszer létrehoz egy szállítmányt, és hozzáadja egy új rakományhoz, mert nincs olyan betöltési sorokat tartalmazó meglévő rakomány, amelyeknek ez a rendelési száma.

    Olyan tájékoztató üzenetek érkeznek, amelyek ehhez az értékesítési rendeléshez létrehozott munkát, hullámot és szállítmányt jelenítik meg.

1. Ha meg szeretné erősíteni a rakományt, a szállítmányt és a munka adatait az értékesítési sorban, válassza ki a sort, majd a rács fölötti **Raktár** menüben válassza ki a **Rakomány részletei**, a **Szállítmány részletei** vagy a **Munka részletei** elemet.
1. A most létrehozott értékesítési rendelésben az **Értékesítési rendelés sorai** gyorslapon válassza ki a **Sor hozzáadása** lehetőséget, ha másik sort szeretne hozzáadni.
1. Ebben az új sorban állítsa be a **Cikkszám** mezőt *A0002* és a **Mennyiség** mezőt *1* értékre.
1. A sorfoglaláshoz és a raktárba történő kiadáshoz ismételje meg a 6–9. sort. A rendszer **új** szállítmányt hoz létre a hozzáadott sorhoz. Mivel azonban speciális hullámrakomány-összeállítást használ, a rendszer hozzáadja azt a szállítmányt és betöltési sort a meglévő hullámhoz. Ha nem speciális hullámrakomány-összeállítást használna, akkor a rendszer új rakományt hozna létre a szállítmányhoz.
1. A most létrehozott értékesítési rendelésben az **Értékesítési rendelés sorai** gyorslapon válassza ki a **Sor hozzáadása** lehetőséget, ha másik sort szeretne hozzáadni.
1. Ebben az új sorban állítsa be a **Cikkszám** mezőt *M9200* és a **Mennyiség** mezőt *1* értékre.
1. A sorfoglaláshoz és a raktárba történő kiadáshoz ismételje meg a 6–9. sort. Mint korábban, a rendszer **új** szállítmányt hoz létre a hozzáadott sorhoz. Mivel azonban a tétel **CarAudio** elemcsoportból származik, **nem továbbítja a rakománykombinációs csoporthoz beállított megszorításokat**. Emiatt a rendszer **egy új rakományhoz adja hozzá**. Ha nem adott meg rakománykombinációs csoportot a rakomány-összeállítási sablonban, akkor ez a szállítmány hozzá lett adva az első rakományhoz.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]