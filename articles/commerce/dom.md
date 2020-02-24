---
title: Felosztott rendeléskezelés (DOM)
description: Ez a témakör a Dynamics 365 Commerce elosztott rendeléskezelés (DOM) funkcióját részletezi.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7a584953b0f4961e25b59bca51aa3928b87b2c7c
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004320"
---
# <a name="distributed-order-management-dom"></a>Felosztott rendeléskezelés (DOM)

[!include [banner](includes/banner.md)]

A kereskedelmi műveletek új paradigmájában a kiskereskedők törekszenek arra, hogy személyre szabott ügyfélkapcsolatokat, többcsatornás élményeket és gördülékeny interakciókat nyújthassanak. Mivel számos választási lehetőségük van, a fogyasztók ott vásárolnak, ahol a legkellemesebb élményben lesz részük. Sok esetben már nem az árak és a termékek a legfontosabb döntési tényezők a fogyasztók szemében.

A vevői élmény javítása érdekében a kiskereskedőknek biztosítaniuk kell a készletük átláthatóságát valós időben, minden csatornán keresztül. Ha egyetlen, átfogó nézetet biztosít a készlethez, azzal optimalizálhatja a rendelések teljesítését, felosztását és terjesztését. Ezért az elosztott rendeléskezelési (DOM) rendszer bevezetése és alkalmazása egyre elengedhetetlenebbé válik a kiskereskedők számára.

A DOM optimalizálja a rendelések teljesítését még a rendszerek és folyamatok bonyolult rendszerén keresztül is. A rendszer a teljes szervezeten keresztül egyetlen, globális készletnézetre támaszkodik a rendelések intelligens kezelése érdekében, így ezeket pontosan lehet teljesíteni, ráadásul sokkal költséghatékonyabb módon. A DOM javítja a kiskereskedő ellátási láncának hatékonyságát, és így segít a kiskereskedőnek a vevői igények megfelelőbb kielégítésében.

A következő ábra bemutatja egy értékesítési rendelés teljes életútját a DOM rendszerben.

![Értékesítési rendelés életciklusa a DOM környezetében](./media/flow.png "Értékesítési rendelés életciklusa a DOM környezetében")

## <a name="set-up-dom"></a>DOM beállítása

1. Lépjen a **Rendszerfelügyelet \> Beállítás \> Licenckonfiguráció** elemre.
2. A **Konfigurációs kulcsok** lapon bontsa ki a **Kereskedelmi** csomópontot, majd válassza ki az **Felosztott rendeléskezelés** jelölőnégyzetet.
3. Lépjen a **Kiskereskedelem és kereskedelem \> Felosztott rendeléskezelés \> Beállítás \> DOM-paraméterek** lehetőségre.
4. Az **Általános** lapon állítsa be a következő értékeket:

    - **Felosztott rendeléskezelés engedélyezése** – Állítsa a beállítás értékét **Igen** értékre.
    - **Bing Térképek-használat megerősítése a DOM-hoz** – Állítsa a beállítást **Igen** értékre.

        > [!NOTE]
        > Ezt a beállítást csak akkor állíthatja **Igen** értékre, ha a **Megosztott kereskedelmi paraméterek** oldal **Bing Térképek** lapján a **Bing Térképek engedélyezése** beállítás (**Kiskereskedelem és kereskedelem \> Központ beállítása \> Paraméterek \> Megosztott kereskedelmi paraméterek**) értéke is **Igen** értékre van állítva, valamint a **Bing Térképek-kulcs** mezőben érvényes kulcsot adtak meg.

    - **Megőrzési időszak (nap)** – Adja meg, hogy a DOM-futtatások által létrehozott teljesítési terveket a rendszer milyen hosszan őrizze meg. A **DOM teljesítési adatok törlése feladatbeállítás** kötegelt feladat minden olyan teljesítési tervet törölni fog, amely régebbi, mint az itt megadott napok száma.
    - **Elutasítási időszak (napokban)** – Adja meg, mennyi időnek kell eltelnie, mielőtt egy elutasított rendelési sort ugyanahhoz a helyhez lehetne rendelni.

5. A **Feloldás** lapon állítsa be a következő értékeket:

    - **Maximális automatikus teljesítési próbálkozások száma** – Adja meg, hogy a DOM-motor hányszor próbálkozzon egy rendelési sor adott helyhez való közvetítésével. Ha a DOM-motor nem tudja a rendelés sort az adott helyhez közvetíteni a meghatározott számú próbálkozás során, akkor kivételként jelöli meg a rendelési sort. A jövőbeli futások során a rendszer kihagyja majd a sort egészen addig, amíg az állapotát manuálisan vissza nem állítják.
    - **Helyi üzlet régiójának hatósugara** – Adjon meg egy értéket. A mező segítségével megállapíthatja, hogy a helyeket a rendszerek hogyan csoportosítja és értelmezi egyenlőként a távolság tekintetében. Például ha a bevitt érték **100**, akkor a rendszer minden üzletet vagy elosztási központot, amely a teljesítési cím 100 mérföldes körzetében található, egyenlőként fog kezelni a távolság tekintetében.
    - **Feloldás típusa** – Válasszon ki egy értéket. A kereskedelmi szolgáltatásban két feloldási típus áll rendelkezésre: a **Termelési feloldás** és az **Egyszerűsített feloldás**. Az összes, DOM-ot futtató berendezés esetében (ide értendő az összes szerver, amely a DOMBatch csoportba tartozik) a **Termelési feloldás** lehetőséget kell kiválasztani. A Termelési feloldáshoz egy speciális licenckulcsra van szükség, amely alapértelmezett módon a termelési környezetekben licencelt és telepített. A nem termelési környezetekben a licenckulcsot manuálisan kell telepíteni. A licenckulcs manuális telepítéséhez kövesse az alábbi lépéseket:

        1. A Microsoft Dynamics Lifecycle Services szolgáltatásban nyissa meg a Közös eszközök tárát, az eszköz típusaként válassza ki a **Modell** lehetőséget, majd töltse le a **DOM-licenc** fájlt.
        2. Indítsa el a Microsoft IIS-kezelő szolgáltatást, jobb gombbal kattintson az **AOSService weboldal** lehetőségre, majd válassza a **Felfedezés** elemet. Ekkor az **\<AOS szolgáltatásgyökér\>\\webes gyökérről** megnyílik egy új Windows Explorer-ablak. Jegyezze fel az \<AOS szolgáltatásgyökér\> elérési útvonalát, mert a következő lépésnél szüksége lesz rá.
        3. Másolja a konfigurációs fájlt az **\<AOS Service root\>\\PackagesLocalDirectory\\DOM\\bin** könyvtárába.
        4. Lépjen a Headquarters kliensre, és nyissa meg a **DOM-paraméterek** oldalt. A **Feloldás** lapon található **Feloldás típusa** mezőben válassza a **Termelési feloldás** lehetőséget, és erősítse meg, hogy nem jelentek meg hibaüzenetek.

        > [!NOTE]
        > Az Egyszerűsített feloldás azért áll rendelkezésre, hogy a kiskereskedőknek lehetőségük legyen a DOM funkció kipróbálására anélkül, hogy a speciális licencet telepíteniük kellene. A szervezeteknek nem javasolt az Egyszerűsített feloldás használata termelési környezetekben.
        >
        > Bár az Egyszerűsített feloldás ugyanolyan képességekkel rendelkezik, mint a Termelési feloldás, különböző korlátai vannak, például a teljesítményben (az egy futás során kezelt rendelések és rendelési sorok száma) és az eredmények konvergenciája (bizonyos esetekben a rendelések kötegével nem a legjobb eredményt lehet elérni).
     
6. Lépjen vissza a **Kiskereskedelem és kereskedelem \> Felosztott rendeléskezelés \> Beállítás \> DOM-paraméterek** lehetőségre.
7. A **Számsorozatok** lapon rendelje hozzá a szükséges számsorozatokat a különböző DOM-entitásokhoz.

    > [!NOTE]
    > A számsorozatok entitásokhoz való hozzárendelése előtt ezeket meg kell határozni a **Számsorozatok** oldalon (**Szervezeti adminisztráció \> Számsorozatok \> Számsorozatok**).

8. A DOM funkció támogatja a különböző típusú DOM-szabályok meghatározását, a szervezetek több szabályt is konfigurálhatnak üzleti igényeiknek megfelelően. A DOM-szabályokat meg lehet határozni helyek csoportjára vagy egyéni helyekre, valamint specifikus termékkategóriára, termékre vagy változatra. A DOM-szabályokban használandó helyek csoportosításának létrehozásához kövesse az alábbi lépéseket:

    1. Lépjen a **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Teljesítési csoportok** elemre.
    2. Válassza az **Új** lehetőséget, és adja meg az új csoport nevét és leírását.
    3. Válassza a **Mentés** lehetőséget.
    4. Ha egyetlen helyet szeretne a csoporthoz hozzáadni, válassza a **Sor hozzáadása** elemet. Továbbá a **Sorok hozzáadása** elemmel egyszerre több helyet is hozzáadhat.

9. A szabályok definiálásához ugorjon a **Kiskereskedelem és kereskedelem \> Felosztott rendeléskezelés \> Beállítás \> Szabályok kezelése** lehetőségre. Jelenleg a következő DOM-szabályok támogatottak:

    - **Minimumkészlet szabálya** – Ez a szabálytípus lehetővé teszi a szervezetnek, hogy elkülönítsék egy termék bizonyos mennyiségét rendelésteljesítéstől eltérő célra. Például előfordulhat, hogy a szervezet nem szeretné, hogy a DOM a teljes készletet figyelembe vegye a rendelésteljesítéshez, ami az üzletben található. Ehelyett szeretnék a készlet egy részét a besétáló vásárlók számára fenntartani. Ilyen típusú szabály használatakor meghatározhatja az adott termékkategóriára, egy egyéni termékre vagy termékváltozatra vonatkozó minimum fenntartandó készlet mennyiségét helyekre vagy helyek csoportjára lebontva.
    - **Teljesítés helye prioritási szabály** – Ezzel a szabálytípussal a szervezetek meghatározhatják a helyek hierarchiáját, amelynek megfelelő prioritást vesz a DOM-motor figyelembe, amikor a meghatározott termék teljesítési helyét igyekszik beazonosítani. A prioritások érvényes tartománya 1 és 10 közötti, ahol 1 a legmagasabb, 10 pedig a legalacsonyabb prioritást jelzi. A magasabb prioritással rendelkező helyeket a rendszer előbb veszi figyelembe, mint az alacsonyabb prioritással rendelkezőket. Ha a szabályt szigorú korlátként határozza meg, a rendeléseket csak a meghatározott prioritással rendelkező helyekre közvetíti a rendszer.
    - **Részleges rendelés szabály** – Ez a szabály azt teszi lehetővé, hogy a szervezetek meghatározzák, hogy egy rendelést vagy rendelési sort lehetséges-e csak részlegesen teljesíteni. A következő paraméterek állnak rendelkezésre:

        - **Részleges rendelések teljesítése?** – Ha ezt a beállítást **Igen** értékre állítja, a DOM képes arra, hogy a rendelési sorban található mennyiségnek csak egy részét teljesíti. A részleges teljesítés a rendelési sor felosztásával valósítható meg.
        - **Részleges sorok teljesítése?** – Ha ezt a beállítást **Igen** értékre állítja, a DOM képes arra, hogy a rendelési sorok mennyiségnek csak egy részét teljesíti. A részleges teljesítés a rendelési sor felosztásával valósítható meg.
        - **Rendelés teljesítése csak egy helyről** – Ha ezt a beállítást **Igen** értékre állítja, a DOM gondoskodik arról, hogy egy rendelés minden sorát csak egyetlen helyről teljesítse.


        Az alábbi táblázat bemutatja, mi történik akkor, ha ezeknek a paramétereknek a kombinációja kerül meghatározásra.

        |      | Részleges rendelések teljesítése | Részleges sorok teljesítése | Rendelés teljesítése csak egy helyről | Leírás |
        |------|------------------------|-----------------------|--------------------------------------|-------------|
        | 1    | Igen                    | Igen                   | Igen                                  | Az adott DOM-futáspéldányban a rendelés néhány sora teljesíthető, valamint az egyes soroknál is lehetséges a részleges teljesítés, azonban minden sort ugyanarról a helyről kell teljesíteni. (Ez a kombináció jelenleg nem támogatott.) |
        | 2    | Igen                    | Nem                    | Igen                                  | Az adott DOM-futáspéldányban a rendelés néhány sora teljesíthető, de az egyes soroknál nem lehetséges a részleges teljesítés, és minden teljesített sor ugyanarról a helyről kell, hogy származzon. (Ez a kombináció jelenleg nem támogatott.) |
        | 3    | Igen                    | Igen                   | Nem                                   | Az adott DOM-futáspéldányban a rendelés néhány sora teljesíthető, és az egyes soroknál lehetséges a részleges teljesítés, valamint minden sort lehet egynél több helyről is teljesíteni. |
        | 4\*  | Nem                     | Nem alkalmazható        | Nem                                   | Minden teljesítési sort teljesíteni kell, az egyes sorokat nem lehet részlegesen teljesíteni, és minden sort lehet különböző helyekről teljesíteni. |
        | 5\*  | Nem                     | Nem alkalmazható        | Igen                                  | Minden teljesítési sort teljesíteni kell, az egyes sorokat nem lehet részlegesen teljesíteni, és az összes rendelési sort egy helyről lehet csak teljesíteni. |
        | 6\*  | Nem                     | Nem alkalmazható        | Nem                                   | Ez a kombináció a 4. kombinációhoz hasonlóan működik, mivel a **Részleges sorok teljesítése** beállítást nem lehet **Igen** értékre állítani, ha a **Részleges rendelések teljesítése** beállítása **Nem** értékre van állítva. |
        | 7\*  | Nem                     | Nem alkalmazható        | Igen                                  | Ez a kombináció a 5. kombinációhoz hasonlóan működik, mivel a **Részleges sorok teljesítése** beállítást nem lehet **Igen** értékre állítani, ha a **Részleges rendelések teljesítése** beállítása **Nem** értékre van állítva. |
        | 8    | Igen                    | Nem                    | Nem                                   | Az adott DOM-futáspéldányban a rendelés néhány sora teljesíthető, de az egyes soroknál nem lehetséges a részleges teljesítés, és a különböző rendelési sorokat egynél több helyről is lehet teljesíteni. |
        | 9\*  | Nem                     | Nem alkalmazható        | Igen                                  | Mindegyik rendelési sort teljesíteni kell, valamint az összes rendelési sort egy helyről kell teljesíteni. |

        \* Ha a **Részleges rendelések teljesítése** beállítás **Nem** értékre van állítva, a **Részleges sorok teljesítése** beállításokat mindig **Nem** értékűnek kell tekinteni, attól függetlenül, hogy valójában mire vannak állítva.

        > [!NOTE]
        > A Retail 10.0.5-ös verziójában a **Rendelés teljesítése csak egy helyről** paraméter **Maximum teljesítési helyek** paraméterre módosult. Annak beállítása helyett, hogy a rendelést csak egy helyről, vagy a lehetséges összes helyről lehessen teljesíteni, mostantól a felhasználók megadhatják, hogy a teljesítést a helyek megadott csoportjából (legfeljebb 5 hely) lehet teljesíteni, vagy a lehetséges összes helyről. Ez több rugalmasságot biztosít a rendelésteljesítés helyeinek számát illetően.

   - **Offline teljesítési hely szabály** – Ez a szabály lehetővé teszi a szervezeteknek, hogy egy helyet vagy helycsoportot offline vagy nem elérhető jelzéssel lássanak el, így a rendelések nem rendelhetők hozzá teljesítésre az adott helyhez.
    - **Maximum elutasítások szabály** – Ezzel a szabállyal a szervezetek meghatározhatnak egy elutasítási küszöbértéket. Amikor a rendszer eléri a küszöbértéket, a DOM processzor kivételként megjelöli a rendelést vagy rendelési sort, és kizárja a további feldolgozásból.

        Miután a rendelési sorokat egy helyhez rendelte a rendszer, a hely elutasíthatja a hozzárendelt rendelési sort, mivel bizonyos okok miatt előfordulhat, hogy nem képes teljesíteni a rendelést. Az elutasított sorokat a rendszer kivételként jelöli meg, és visszakerülnek az állományba, hogy a következő futáskor ismét feldolgozásra kerüljenek. A következő futás során a DOM megpróbálja az elutasított sort egy másik helyhez rendelni. Az új helynek szintén lehetősége van a hozzárendelt rendelési sor elutasítására. A hozzárendelési és elutasítási ciklus akár többször is lejátszódhat. Amikor az elutasítások száma eléri a meghatározott küszöbértéket, a DOM állandó kivételként jelöli meg az adott rendelési sort, és többé nem tárolja ki a sort hozzárendelésre. A DOM csak akkor veszi figyelembe ismét hozzárendelésre a sort, ha egy felhasználó manuálisan módosítja a rendelési sor állapotát.

   - **Maximum távolság szabály** – Ez a szabály lehetővé teszi, hogy a szervezet meghatározza a hely vagy helycsoport maximális távolságát a rendelés teljesítéséhez. Ha egymást fedő maximum távolsági szabályokat határoztak meg egy helyre vonatkozóan, akkor a DOM az adott helyhez megadott legalacsonyabb maximum távolságot alkalmazza majd.
    - **Rendelések maximális számának szabálya** – Ezzel a szabállyal a szervezetek meghatározhatják a rendelések maximális számát, amelyet egy hely vagy helycsoport feldolgozhat egy naptári nap során. Ha adott helyhez vagy helycsoporthoz egy nap folyamán már hozzárendelték a rendelések maximális számát, akkor a DOM a nap további részében már nem rendel a helyhez több rendelést.

   Az alábbiakban felsoroltunk néhány olyan közös attribútumot, amelyet a korábban felsorolt szabálytípusra meg lehet határozni:

   - **Kezdő dátum** és **Záró dátum** – Minden szabályt el lehet látni érvényességi dátummal, ha kitölti ezeket a mezőket.
   - **Letiltott** – Csak azokat a szabályokat veszi figyelembe a DOM a futások során, amelyeknél ez a beállítás **Nem** értékkel rendelkezik.
   - **Szigorú korlát** – Egy szabályt lehet szigorú vagy nem szigorú korlátként megadni. Minden DOM-futás két iteráción megy át. Az első iteráció során minden szabályt szigorú korlátként kezel a rendszer, függetlenül a mező beállításától. Azaz a rendszer minden szabályt alkalmaz. Ez alól az egyetlen kivétel a **Hely prioritása** szabály. A második iteráció során a nem szigorú korlátként megadott szabályokat a rendszer eltávolítja, és azok a rendelések vagy rendelési sorok is hozzárendelésre kerülnek, amelyeket az összes szabály alkalmazásakor nem sikerült helyhez hozzárendelni.

10. A teljesítési profilokat a rendszer szabályok, jogi személyek, értékesítésirendelés-források és kiszállítási módok gyűjteményének csoportosítására használja. Minden DOM-futás egy meghatározott teljesítési profilhoz tartozik. Így a szervezetek meghatározhatnak és lefuttathatnak szabályok egy sorozatát jogi személyek egy csoportjára, olyan rendeléseken, amelyek specifikus értékesítésirendelés-forrásokkal vagy szállítási módokkal rendelkeznek. Ezért tehát amennyiben különböző szabálycsoportokat kell lefuttatni a különböző értékesítésirendelés-források vagy kiszállítási módok esetén, a teljesítési profilokat ennek megfelelően lehet megadni. A teljesítési profilok beállításához kövesse az alábbi lépéseket:  

    1. Lépjen a **Kiskereskedelem és kereskedelem \> Felosztott rendeléskezelés \> Beállítás \> Teljesítési profilok** lehetőségre.
    2. Válassza az **Új** lehetőséget.
    3. Adjon meg értékeket a **Profil** és a **Leírás** mezőkben.
    4. Állítsa be az **Eredmények automatikus alkalmazása** lehetőséget. Ha ezt a beállítást **Igen** értékre állítja, akkor a profilhoz tartozó DOM-futás eredményeit a rendszer automatikusan alkalmazza az értékesítési rendelés soraira. Ha **Nem** értékre állítja, akkor az eredményeket csak a teljesítési tervben tudja megtekinteni. Ezeket a rendszer nem alkalmazza az értékesítési rendelés soraira.
    5. Ha szeretné, hogy a DOM-profil minden olyan rendeléshez lefusson, amelyek az összes értékesítésirendelés-forrással rendelkeznek, még azokra is, amelyeknél az értékesítési rendelés forrása nem meghatározott, állítsa a **Üres értékesítési forrással rendelkező rendelések feldolgozása** beállítást **Igen** értékre. Ha profilt csak néhány típusú értékesítésirendelés-forrás esetén szeretné futtatni, akkor azokat a később leírt módon a **Értékesítési források** oldalon teheti meg.
    6. A **Jogi személyek** gyorslapon válassza a **Hozzáadás** lehetőséget, majd válasszon ki egy jogi személyt.
    7. A **Szabályok** gyorslapon válassza a **Hozzáadás** elemet, majd válassza ki a szabályt, amelyet a profilhoz szeretne kapcsolni.
    8. Ismételje az előző két lépést mindaddig, amíg az összes szükséges szabályt nem társította a profilhoz.
    9. Válassza a **Mentés** lehetőséget.
    10. A Művelet panel **Beállítás** lapján válassza a **Szállítási módok** menüpontot.
    11. A **Szállítási módok** oldalon válassza az **Új** elemet.
    12. A **Vállalat** mezőben válassza ki a jogi személyt. A vállalatok listájában csak azok a jogi személyek találhatók, amelyeket korábban hozzáadott.
    13. A **Szállítás módja** mezőben válassza ki a szállítási módot, amelyet az adott profilhoz kíván társítani. Egy szállítási módot nem lehet több aktív profilhoz társítani.
    14. Ismételje az előző két lépést mindaddig, amíg az összes szükséges szállítási módot nem társította a profilhoz.
    15. Zárja be a **Szállítás módja** oldalt.
    16. A Művelet panel **Beállítás** lapján válassza az **Értékesítési rendelés forrásai** menüpontot.
    17. Az **Értékesítési források** oldalon válassza az **Új** lehetőséget.
    18. A **Vállalat** mezőben válassza ki a jogi személyt. A vállalatok listájában csak azok a jogi személyek találhatók, amelyeket korábban hozzáadott.
    19. Az **Értékesítési forrás** mezőben válassza ki a profilhoz társítani kívánt értékesítési forrást. Egy értékesítési forrást nem lehet több aktív profilhoz társítani.
    20. Ismételje az előző két lépést mindaddig, amíg az összes szükséges értékesítési forrást nem társította a profilhoz.
    21. Zárja be az **Értékesítési források** oldalt.
    22. Állítsa a **Profil engedélyezése** beállítást **Igen** lehetőségre. Amennyiben bármilyen hiba található a beállítások között, figyelmeztető üzenet jelenik meg.

## <a name="dom-processing"></a>DOM-feldolgozás

A DOM csak kötegelt feladatban futtatható. A DOM futásokhoz tartozó kötegelt feladat konfigurálásához kövesse az alábbi lépéseket.

1. Lépjen a **Kiskereskedelem és kereskedelem \> Felosztott rendeléskezelés \> Kötegfeldolgozás \> DOM-feldolgozási feladat beállítása** elemre.
1. A **Paraméterek** gyorslapon található **Teljesítési profil** mezőben válassza ki azt a profilt, amelyhez a DOM-ot futtatni kívánja.
1. A **Futtatás a háttérben** gyorslapon található **Kötegcsoport** mezőben válasszon egy konfigurált kötegcsoportot.
1. A **Feladatleírás** mezőbe írja be a kötegelt feladat nevét.
1. Válassza ki az **Ismétlődés** lehetőséget, és adja meg a kötegelt feladat ismétlődését.
1. Válassza ki az **OK** lehetőséget.

A feldolgozás időpontjában a DOM az alábbiak szerint veszi majd figyelembe a rendelést és a rendelési sorokat:

- A rendelési sorok, amelyek megfelelnek az értékesítési rendelés forrásával, a szállítási móddal és a jogi személlyel kapcsolatos, a DOM-profilban meghatározott feltételeknek, valamint a következő kritériumok egyikének:

    - Kereskedelmi csatornákból hozták létre őket.
    - Korábban még nem közvetítette őket a DOM.
    - A DOM már közvetítette őket, de kivételként vannak megjelölve, és még nem érték el a próbálkozások maximális küszöbértékét.
    - A szállítás módja nem felvétel vagy elektronikus kézbesítés.
    - Nincsenek szállításra megjelölve.
    - Nem zárták ki őket manuális úton.

- Olyan rendelések, amelyek nem várakoztatott állapotúak.

Miután a DOM alkalmazta a szabályokat, a készletkorlátokat és az optimalizációt, kiválasztja a vevő szállítási címéhez legközelebbi helyet.

![Értékesítési rendelés feltételei](./media/ordercriteria.png "Értékesítési rendelés feltételei")

## <a name="results-of-dom-runs"></a>DOM-futások eredményei

Ha a teljesítési profil **Automatikus alkalmazás** típusúra van állítva, akkor a futás eredményeit a rendszer automatikusan alkalmazza az értékesítési rendelés soraira, a teljesítési tervet pedig külön meg lehet tekinteni. Azonban ha a teljesítési profil nem **Automatikus alkalmazás** állapotú, a futás eredményei csak a teljesítési terv nézetben megtekinthetők. 

Az összes létrehozott teljesítési terv megtekintéséhez kövesse az alábbi lépéseket.

1. Lépjen a **Kiskereskedelem és kereskedelmi \> Felosztott rendeléskezelés \> Felosztott rendeléskezelés** elemre.
2. Az **Felosztott rendeléskezelés** munkaterületen válassza a **Teljesítési tervek** csempét.
3. Válassza a releváns rendelés teljesítési tervének azonosítóját a teljesítési terv megtekintéséhez.

    A teljesítési terv rendelési részletek szakaszában láthatók a futás részét képező, eredeti értékesítési rendelési sorok. A megszokott értékesítési rendelési sor mezőkön kívül a rendelési részletek szakasz az alábbi három, DOM-hoz kapcsolódó mezőt is tartalmazza:

    - **Teljesítési típus** – Ez a mező azt jelzi, hogy az értékesítési rendelési sort teljes mértékben közvetítették, részben közvetítették vagy még egyáltalán nem közvetítették egy helyre.
    - **Felosztás** – Ez a mező azt jelzi, hogy egy értékesítési rendelés fel lett-e osztva, és különböző helyekre közvetítve.
    - **Teljesítési helyek száma** – Ez a mező azt jelzi, hogy egy értékesítési rendelési sorból hány teljesítési sort hozott létre a rendszer (annak megfelelően, hogy az eredeti értékesítési sort hány helyre közvetítette).

    A rendelés teljesítésének részletei szakaszban az eredeti értékesítési rendelési sorok különböző helyekhez való hozzárendelése látható, a hozzárendelt mennyiségekkel együtt.

## <a name="order-line-actions-and-statuses"></a>Rendelési sorok műveletei és állapotai

A következő leírásban a rendelési sor beállításait ismerheti meg. A rendelési sor megnyitásához lépjen a **Kiskereskedelem és kereskedelem \> Vevők \> Minden értékesítési rendelés** elemre.
- Ha az értékesítési rendelési sor **Általános** lapján a **Kizárás a DOM-feldolgozásból** beállítást **Igen** értékre állította, a rendelés vagy a rendelési sor kizárásra kerül a DOM-feldolgozásból.
- Az értékesítési rendelési sor **Általános** lapján található **DOM állapot** mezőt az alábbi értékek egyikére állíthatja:

    - **Nincs** – A rendelési sort korábban még nem közvetítették.
    - **Teljesített** – A rendelési sort sikeresen közvetítették, és hozzárendelték egy helyhez.
    - **Kivétel** – A rendelési sort sikeresen közvetítették, de nem lehet hozzárendelni egy helyhez. A kivételeknek több altípusa létezik, amelyeket a DOM-munkaterületről lehet megtekinteni:

        - **Nincs elérhető mennyiség** – Nincs elérhető készlet, amely lehetővé tenné, hogy a rendelést egy helyhez rendeljék.
        - **Maximum elutasítások** – A rendelési sor elérte az elutasítások maximális küszöbértékét.
        - **Adatmódosítási konfliktus** – Az értékesítési rendelési sort a rendelés közvetítése óta módosították. Ez azt eredményezni, hogy a teljesítési tervet nem lehet a rendelésre alkalmazni.
        - **Rendelésisor-specifikus kivétel** – A rendelési soron több kivétel is található.

- Az értékesítési rendelés bevitele során lehetőség van arra, hogy a DOM-ot interaktív módban futtassák. A rendelési sor megadása során, miután a terméket és a mennyiséget meghatározta, kiválaszthatja a **Sor frissítése** lehetőséget, majd a **DOM** menüpont alatt a **Teljesítési hely javaslata** elemet. Ekkor megjelenik a helyek listája, amelyek a DOM-szabályok alapján képesek a rendelési sor mennyiségének teljesítésére. A listán a helyek távolság szerinti sorrendben szerepelnek. Válasszon ki egy helyet, hogy beállíthassa a releváns telephelyet és raktárt az értékesítési rendelési sorban. Ahhoz, hogy ez a funkció megfelelően működjön, léteznie kell egy olyan aktív teljesítési profilnak, amely megfelel az értékesítési soron megadott értékesítési forrásnak és szállítási módnak.
- Ha szeretné egy adott értékesítési rendelési sorhoz tartozó DOM-futásnaplókat megtekinteni, válassza az **Értékesítési rendelési sor** lehetőséget, majd a **DOM** menüpont alatt a **DOM-naplók megtekintése** elemet. A DOM naplók minden olyan eseményt és naplót megjelenítenek, amelyek a DOM-futás hatására jöttek létre. A naplókból megtudhatja, hogy egy meghatározott helyet miért rendelt a rendszer a rendelési sorhoz, valamint hogy milyen szabályokat és korlátokat vett figyelembe a hozzárendelés részeként. A **Kezelés** lapon a DOM-naplókat az értékesítési rendelés fejlécének szintjén is elérheti.

## <a name="run-a-clean-up-job-for-dom-fulfillment-plans"></a>Tisztítási feladat futtatása a DOM teljesítési tervekhez

Amikor lefut egy DOM-feldolgozás, teljesítési tervek jönnek létre. Idővel a rendszer számos teljesítési tervet tárol már. A rendszer által tárolt nagy mennyiségű teljesítési terv kezelése érdekében konfigurálhat egy olyan kötegelt feladatot, amely törli a régebbi teljesítési terveket a **Megőrzési időszak (nap)** értékének megfelelően.

1. Lépjen a **Kiskereskedelem és kereskedelem \> Felosztott rendeléskezelés \> Kötegfeldolgozás \> DOM-teljesítési adatok törlése feladat beállítása** elemre. 
1. A **Kötegcsoport** mezőben válasszon ki egy konfigurált kötegcsoportot.
1. Válassza ki az **Ismétlődés** lehetőséget, és adja meg a kötegelt feladat ismétlődését.
1. Válassza ki az **OK** lehetőséget.

## <a name="more-information"></a>További információ

Alább olyan dolgokat gyűjtöttünk össze, amelyet érdemes a DOM funkció használata során figyelembe vennie:

- Jelenleg a DOM csak olyan rendeléseket tekint át, amelyeket kereskedelmi csatornákból hoztak létre. Az értékesítési rendeléseket a rendszer akkor azonosítja értékesítési rendelésként, ha a **Kereskedelmi értékesítés** beállítás **Igen** értékre van állítva.
- A Microsoft még nem tesztelte a DOM-ot speciális raktárkezelési funkciókkal. A vevőknek és partnereknek óvatosnak kell lenniük, amikor annak megállapítására törekszenek, hogy a DOM kompatibilis-e a számukra releváns speciális raktárkezelési lehetőségekkel és folyamatokkal.
- A DOM csak a kereskedelmi felhőalapú verziójában elérhető. A helyszíni telepítésű verziókban nem támogatott.
