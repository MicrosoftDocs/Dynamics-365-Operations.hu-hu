---
title: Felosztott rendeléskezelés (DOM)
description: Ez a témakör a Dynamics 365 Commerce elosztott rendeléskezelés (DOM) funkcióját részletezi.
author: josaw1
ms.date: 02/08/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: f19fbe2a9f768a91c495a6a4bcb0e475adb867ae
ms.sourcegitcommit: 8bea5a0c232ac31dcafddfcc0d715c496d8dd445
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/09/2022
ms.locfileid: "8102009"
---
# <a name="distributed-order-management-dom"></a>Felosztott rendeléskezelés (DOM)

[!include [banner](includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Commerce elosztott rendeléskezelés (DOM) funkcióját részletezi.

A DOM olyan többcsatornás rendelésteljesítés-optimalizálási megoldás, amely segít maximalizálni a rendelések teljesítését az ellátásilánc-hálózatokban. A DOM segítségével biztosíthatja, hogy a termékeket a megfelelő mennyiségben, a megfelelő forrásból és a megfelelő időben szállítsák a vevőknek. Ezen kívül a DOM használatával maximalizálhatja a nyereséget, minimálisra lehet csökkentheti a költségeket, és teljesítheti a szolgáltatásszintű követelményeket.

A DOM vegyes egészértékű programozást (MIP) és prediktív elemzési modelleket használ az optimalizálások kötegszintű és az egyes rendelések szintjén történő végrehajtásához. Ez a lehetőség lehetővé teszi a kiskereskedők számára, hogy meghatározott szabályokkal kiigazítsák az egymással ütköző rendelésteljesítési igényeket. Egy olyan modern ellátási hálózatban, ahol a termékteljesítés több csatornán keresztül is érkezhet, a szervezeteknek gyorsan kell tudniuk alkalmazkodni a rendelések változásához, a szállító elérhetőségével kapcsolatos problémákhoz és a kiugró igényekhez. A DOM segítségével maximalizálhatja a rendelések teljesítését, és megtalálhatja a megfelelő termékszállítási forrásokat az üzleti korlátozások és célkitűzések (például ha költségcsökkentés miatt a legközelebbi forrásból kell teljesíteni a rendelést) alapján. A DOM a termékteljesítési források és a szállítási célok közötti távolság, az optimalizálási célkitűzésekként meghatározott költségtényezők, valamint a korlátozásokként meghatározott szabályok (például készletezés a teljesítési csomópontokon) felhasználásával optimalizálja a rendelések teljesítését. A DOM több profil meghatározását is lehetővé teszi, amelyek az üzleti vagy felhasználói szegmens típusától függően különböző optimalizálási stratégiákat kínálnak a vállalkozások számára. 

A következő ábra bemutatja egy értékesítési rendelés teljes életútját a DOM rendszerben.

![Értékesítési rendelés életciklusa a DOM környezetében.](./media/flow.png "Értékesítési rendelés életciklusa a DOM környezetében")

## <a name="set-up-dom"></a>DOM beállítása

1. Lépjen a **Rendszerfelügyelet \> Beállítás \> Licenckonfiguráció** elemre.
2. A **Konfigurációs kulcsok** lapon bontsa ki a **Kereskedelmi** csomópontot, majd válassza ki az **Felosztott rendeléskezelés** jelölőnégyzetet.
3. Lépjen a **Kiskereskedelem és kereskedelem \> Felosztott rendeléskezelés \> Beállítás \> DOM-paraméterek** lehetőségre.
4. Az **Általános** lapon állítsa be a következő értékeket:

    - **Felosztott rendeléskezelés engedélyezése** – Állítsa a beállítás értékét **Igen** értékre.
    - **Bing Térképek-használat megerősítése a DOM-hoz** – Állítsa a beállítást **Igen** értékre.

        > [!NOTE]
        > Ezt a beállítást csak akkor állíthatja az **Igen** értékre, ha a **Megosztott kereskedelmi paraméterek** oldal **Bing Térképek** lapján a **Bing Térképek engedélyezése** beállítás (**Kiskereskedelem és kereskedelem \> Központ beállítása \> Paraméterek \> Megosztott kereskedelmi paraméterek**) értéke is az **Igen** értékre van állítva, valamint a **Bing Térképek-kulcs** mezőben érvényes kulcsot adtak meg.
        >
        > A [Bing Térképek fejlesztői központ](https://www.bingmapsportal.com/) portál segítségével bizonyos tartományokra korlátozhatja a hozzáférést a Bing Térképek API-kulcsokhoz. Ezzel a funkcióval az ügyfelek meghatározhatják azoknak a hivatkozóérték- vagy IP-címtartományokat a szigorú készletét, amelyek alapján a rendszer hitelesíti a kulcsot. Az engedélyezési listáról származó kérelmeket a rendszer a szokásos módon dolgozza fel, míg a listán kívülről érkező kérelmek esetében „hozzáférés megtagadva” választ ad. A tartományt védő biztonsági beállítások használata az API-kulcsnál opcionális, és a nem módosított kulcsok is működni fognak. A kulcshoz tartozó engedélyezési lista független a többi kulcstól, így külön szabályokat hozhat létre az egyes kulcsokhoz. A Felosztott rendeléskezelés nem támogatja a tartományra hivatkozó tulajdonságok beállítását.

    - **Megőrzési időszak (nap)** – Adja meg, hogy a DOM-futtatások által létrehozott teljesítési terveket a rendszer milyen hosszan őrizze meg. A **DOM teljesítési adatok törlése feladatbeállítás** kötegelt feladat minden olyan teljesítési tervet törölni fog, amely régebbi, mint az itt megadott napok száma.
    - **Elutasítási időszak (napokban)** – Adja meg, mennyi időnek kell eltelnie, mielőtt egy elutasított rendelési sort ugyanahhoz a helyhez lehetne rendelni.

5. A **Feloldás** lapon állítsa be a következő értékeket:

    - **Maximális automatikus teljesítési próbálkozások száma** – Adja meg, hogy a DOM-motor hányszor próbálkozzon egy rendelési sor adott helyhez való közvetítésével. Ha a DOM-motor nem tudja a rendelés sort az adott helyhez közvetíteni a meghatározott számú próbálkozás során, akkor kivételként jelöli meg a rendelési sort. A jövőbeli futások során a rendszer kihagyja majd a sort egészen addig, amíg az állapotát manuálisan vissza nem állítják.
    - **Helyi üzlet régiójának hatósugara** – Adjon meg egy értéket. A mező segítségével megállapíthatja, hogy a helyeket a rendszerek hogyan csoportosítja és értelmezi egyenlőként a távolság tekintetében. Például ha a bevitt érték **100**, akkor a rendszer minden üzletet vagy elosztási központot, amely a teljesítési cím 100 mérföldes körzetében található, egyenlőként fog kezelni a távolság tekintetében.
    - **Feloldás típusa** – Válasszon ki egy értéket. A kereskedelmi szolgáltatásban két feloldási típus áll rendelkezésre: a **Termelési feloldás** és az **Egyszerűsített feloldás**. Az összes, DOM-ot futtató berendezés esetében (ide értendő az összes szerver, amely a DOMBatch csoportba tartozik) a **Termelési feloldás** lehetőséget kell kiválasztani. A Termelési feloldáshoz egy speciális licenckulcsra van szükség, amely alapértelmezett módon a termelési környezetekben licencelt és telepített. Az újabb, kettes vagy magasabb szintű környezetben már engedélyezve van a Production Solver. A nem termelési környezetekben a licenckulcsot manuálisan kell telepíteni. A licenckulcs manuális telepítéséhez kövesse az alábbi lépéseket:

        1. A Microsoft Dynamics Lifecycle Services szolgáltatásban nyissa meg a Közös eszközök tárát, az eszköz típusaként válassza ki a **Modell** lehetőséget, majd töltse le a **DOM-licenc** fájlt.
        1. Indítsa el a Microsoft Internet Information Services (IIS)-kezelő szolgáltatást, jobb gombbal kattintson az **AOSService weboldal** lehetőségre, majd válassza a **Felfedezés** elemet. Ekkor az **\<AOS service root\>\\webroot** helyen megnyílik egy Windows Explorer-ablak. Jegyezze fel az \<AOS Service root\> elérési útvonalát, mert a következő lépésnél szüksége lesz rá.
        1. Másolja a konfigurációs fájlt az **\<AOS Service root\>\\PackagesLocalDirectory\\DOM\\bin** könyvtárába.
        1. Lépjen a Headquarters kliensre, és nyissa meg a **DOM-paraméterek** oldalt. A **Feloldás** lapon található **Feloldás típusa** mezőben válassza a **Termelési feloldás** lehetőséget, és erősítse meg, hogy nem jelentek meg hibaüzenetek.

        > [!NOTE]
        > Az Egyszerűsített feloldás azért áll rendelkezésre, hogy a kiskereskedőknek lehetőségük legyen a DOM funkció kipróbálására anélkül, hogy a speciális licencet telepíteniük kellene. A szervezeteknek nem javasolt az Egyszerűsített feloldás használata termelési környezetekben.
        >
        > A Termelési feloldás javítja a teljesítményt (például az egy futás során kezelhető rendelések és rendelési sorok számát) és az eredmények konvergenciáját (bizonyos esetekben nem biztos, hogy a kötegelt rendeléssel lehet a legjobb eredményt elérni). Egyes szabályok, például a **Részleges rendelés** és a **Helyszínek maximális száma** szabály megkövetelik a Termelési feloldás használatát.

6. Lépjen vissza a **Kiskereskedelem és kereskedelem \> Felosztott rendeléskezelés \> Beállítás \> DOM-paraméterek** lehetőségre.
7. A **Számsorozatok** lapon rendelje hozzá a szükséges számsorozatokat a különböző DOM-entitásokhoz.

    > [!NOTE]
    > A számsorozatok entitásokhoz való hozzárendelése előtt ezeket meg kell határozni a **Számsorozatok** oldalon (**Szervezeti adminisztráció \> Számsorozatok \> Számsorozatok**).

8. A DOM funkció támogatja a különböző típusú DOM-szabályok meghatározását, a szervezetek több szabályt is konfigurálhatnak üzleti igényeiknek megfelelően. A DOM-szabályokat meg lehet határozni helyek csoportjára vagy egyéni helyekre, valamint specifikus termékkategóriára, termékre vagy változatra. A DOM-szabályokban használandó helyek csoportosításának létrehozásához kövesse az alábbi lépéseket:

    1. Lépjen a **Kiskereskedelem és kereskedelem \> Csatorna beállítása \> Teljesítési csoportok** elemre.
    2. Válassza az **Új** lehetőséget, és adja meg az új csoport nevét és leírását.
    3. Válassza a **Mentés** lehetőséget.
    4. Ha egyetlen helyet szeretne a csoporthoz hozzáadni, válassza a **Sor hozzáadása** elemet. Továbbá a **Sorok hozzáadása** elemmel egyszerre több helyet is hozzáadhat.

    > [!NOTE]
    > A 10.0.12-es és újabb Commerce verzióban a **„Szállítás” vagy „Felvétel” helyszíneinek meghatározásához** engedélyezni kell a **Funkciókezelés** munkaterületen a Teljesítési csoportot.
    >
    > Ez a funkció új konfigurációkat ad hozzá a **Teljesítési csoport** oldalához, ezáltal meghatározhatja, hogy a raktár használható-e szállításhoz, vagy ha a raktár/üzlet kombináció használható-e a szállításhoz, felvételhez vagy mindkettőhöz. 
    >
    > Ha engedélyezi a funkciót, akkor a hely kiválasztásához elérhető lehetőségek frissítve lesznek a pénztárban, ha létrehoz egy felvételi vagy szállítási rendelést.
    >
    > A funkció engedélyezése azt is eredményezi, hogy a pénztár oldalait frissítik, amikor az „összes szállítása” vagy a „szállítás kiválasztva” műveleteket választja ki.

9. A szabályok definiálásához ugorjon a **Retail and Commerce \> Felosztott rendeléskezelés \> Beállítás \> Szabályok kezelése** lehetőségre. Jelenleg a következő DOM-szabályok támogatottak:

    - **Minimumkészlet szabálya** – Ez a szabálytípus lehetővé teszi a szervezetnek, hogy elkülönítsék egy termék bizonyos mennyiségét rendelésteljesítéstől eltérő célra. Például előfordulhat, hogy a szervezet nem szeretné, hogy a DOM a teljes készletet figyelembe vegye a rendelésteljesítéshez, ami az üzletben található. Ehelyett szeretnék a készlet egy részét a besétáló vásárlók számára fenntartani. Ilyen típusú szabály használatakor meghatározhatja az adott termékkategóriára, egy egyéni termékre vagy termékváltozatra vonatkozó minimum fenntartandó készlet mennyiségét helyekre vagy helyek csoportjára lebontva. A minimális készletet is meghatározhat kiegészítő kategóriahierarchia segítségével. Ha egy termék több kategóriába is esik, akkor az egyik kiegészítő kategória lesz a legnagyobb fontosságú minden olyan szabály esetén, amelyben kategóriákat lehet használni.
    - **Teljesítés helye prioritási szabály** – Ezzel a szabálytípussal a szervezetek meghatározhatják a helyek hierarchiáját, amelynek megfelelő prioritást vesz a DOM-motor figyelembe, amikor a meghatározott termék teljesítési helyét igyekszik beazonosítani. A prioritások érvényes tartománya 1 és 10 közötti, ahol 1 a legmagasabb, 10 pedig a legalacsonyabb prioritást jelzi. A magasabb prioritással rendelkező helyeket a rendszer előbb veszi figyelembe, mint az alacsonyabb prioritással rendelkezőket. Ha a szabályt szigorú korlátként határozza meg, a rendeléseket csak a meghatározott prioritással rendelkező helyekre közvetíti a rendszer. A DOM előnyben részesíti azokat a szállítási rendeléseket, amely egyetlen helyről érkeznek. Ezért ha egy egész rendelés és annak sorai nem érhetők el egy 1-es prioritású helyről, akkor a DOM egy olyan helyről próbálja teljesíteni a rendelést, amely 2-es prioritással rendelkezik.
    - **Részleges rendelés szabály** – A Retail version 10.0.5-ös verziójában a **Rendelés teljesítése csak egy helyről** paraméter **Maximum teljesítési helyek** paraméterre módosult. A régi paraméter lehetővé teszi a felhasználók számára annak konfigurálását, hogy a rendelések csak egyetlen helyről vagy a lehető legtöbb helyről legyenek teljesítve. Az új paraméter lehetővé teszi a felhasználók számára annak megadását, hogy a teljesítés adott helyek (legfeljebb öt) meghatározott halmazából vagy a lehető legtöbb helyről történjen. Az egy helyről történő teljesítés kivételével minden más lehetőségnél a DOM felosztja a sort, mivel a rendelés feldolgozása sorok szerint történik. Ez a szabály csak a Termelési feloldás segítségével működik.
    - **Offline teljesítési hely szabály** – Ez a szabály lehetővé teszi a szervezeteknek, hogy egy helyet vagy helycsoportot offline vagy a DOM számára nem elérhető jelzéssel lássanak el, így a rendelések nem rendelhetők hozzá teljesítésre az adott helyhez.
    - **Maximum elutasítások szabály** – Ezzel a szabállyal a szervezetek meghatározhatnak egy elutasítási küszöbértéket. Amikor a rendszer eléri a küszöbértéket, a DOM processzor kivételként megjelöli a rendelést vagy rendelési sort, és kizárja a további feldolgozásból. A teljesítmény biztosítása érdekében a DOM nem nézi meg az összes elutasítási előzményt. 

        Miután a rendelési sorokat egy helyhez rendelte a rendszer, a hely elutasíthatja a hozzárendelt rendelési sort, mivel bizonyos okok miatt előfordulhat, hogy nem képes teljesíteni a rendelést. Az elutasított sorokat a rendszer kivételként jelöli meg, és visszakerülnek az állományba, hogy a következő futáskor ismét feldolgozásra kerüljenek. A következő futás során a DOM megpróbálja az elutasított sort egy másik helyhez rendelni. Az új helynek szintén lehetősége van a hozzárendelt rendelési sor elutasítására. A hozzárendelési és elutasítási ciklus akár többször is lejátszódhat. Amikor az elutasítások száma eléri a meghatározott küszöbértéket, a DOM állandó kivételként jelöli meg az adott rendelési sort, és többé nem tárolja ki a sort hozzárendelésre. A DOM csak akkor veszi figyelembe ismét hozzárendelésre a sort, ha egy felhasználó manuálisan módosítja a rendelési sor állapotát.

    - **Maximum távolság szabály** – Ez a szabály lehetővé teszi, hogy a szervezet meghatározza a hely vagy helycsoport maximális távolságát a rendelés teljesítéséhez. Ha egymást fedő maximum távolsági szabályokat határoztak meg egy helyre vonatkozóan, akkor a DOM az adott helyhez megadott legalacsonyabb maximum távolságot alkalmazza majd.
    - **Rendelések maximális számának szabálya** – Ezzel a szabállyal a szervezetek meghatározhatják a rendelések maximális számát, amelyet egy hely vagy helycsoport feldolgozhat. Az optimalizálási folyamat során a rendszer figyelembe veszi az ilyen helyekről még ki nem szállított rendeléseket. Ez az ellenőrzés a profilokon átívelően történik. Ezért ha a rendelések egymást fedő maximum száma több profilra vonatkozóan van meghatározva ugyanahhoz a helyhez, akkor a rendszer figyelembe veszi az összes profilban definiált rendelések maximális számát. 

    Az alábbiakban felsoroltunk néhány olyan közös attribútumot, amelyet a korábban felsorolt szabálytípusra meg lehet határozni:

    - **Kezdő dátum** és **Záró dátum** – Ezekkel a mezőkkel érvényességi dátummal láthat el minden szabályt.
    - **Letiltott** – Csak azokat a szabályokat veszi figyelembe a DOM a futások során, amelyeknél ez a beállítás **Nem** értékkel rendelkezik.
    - **Szigorú korlát** – Egy szabályt lehet szigorú vagy nem szigorú korlátként megadni. Minden DOM-futás két iteráción megy át. Az első iteráció során minden szabályt szigorú korlátként kezel a rendszer, függetlenül a mező beállításától. Azaz a rendszer minden szabályt alkalmaz. Ez alól az egyetlen kivétel a **Hely prioritása** szabály. A második iteráció során a nem szigorú korlátként megadott szabályokat a rendszer eltávolítja, és azok a rendelések vagy rendelési sorok is hozzárendelésre kerülnek, amelyeket az összes szabály alkalmazásakor nem sikerült helyhez hozzárendelni.

10. A teljesítési profilokat a rendszer szabályok, jogi személyek, értékesítésirendelés-források és kiszállítási módok gyűjteményének csoportosítására használja. Minden DOM-futás egy meghatározott teljesítési profilhoz tartozik. Így a szervezetek meghatározhatnak és lefuttathatnak szabályok egy sorozatát jogi személyek egy csoportjára, olyan rendeléseken, amelyek specifikus értékesítésirendelés-forrásokkal vagy szállítási módokkal rendelkeznek. Ezért tehát amennyiben különböző szabálycsoportokat kell lefuttatni a különböző értékesítésirendelés-források vagy kiszállítási módok esetén, a teljesítési profilokat ennek megfelelően lehet megadni. A teljesítési profilok beállításához kövesse az alábbi lépéseket:  

    1. Lépjen a **Kiskereskedelem és kereskedelem \> Felosztott rendeléskezelés \> Beállítás \> Teljesítési profilok** lehetőségre.
    2. Válassza az **Új** lehetőséget.
    3. Adjon meg értékeket a **Profil** és a **Leírás** mezőkben.
    4. Állítsa be az **Eredmények automatikus alkalmazása** lehetőséget. Ha ezt a beállítást **Igen** értékre állítja, akkor a profilhoz tartozó DOM-futás eredményeit a rendszer automatikusan alkalmazza az értékesítési rendelés soraira. Ha **Nem** értékre állítja, akkor az eredményeket csak a teljesítési tervben tudja megtekinteni. Ezeket a rendszer nem alkalmazza az értékesítési rendelés soraira.
    5. Ha szeretné, hogy a Felosztott rendeléskezelés-profil minden olyan rendeléshez lefusson, amelyek az összes értékesítési rendelésforrással rendelkeznek, ideértve azokat is, amelyeknél az értékesítési rendelés forrása nem meghatározott, állítsa a **Üres értékesítési forrással rendelkező rendelések feldolgozása** beállítást **Igen** értékre. Ha profilt csak néhány típusú értékesítésirendelés-forrás esetén szeretné futtatni, akkor azokat a később leírt módon a **Értékesítési források** oldalon teheti meg.

        > [!NOTE]
        > A 10.0.12 kiadású és újabb Commerce verzióban a **Teljesítési csoport Teljesítési profilhoz való hozzárendelése** funkciót engedélyeznie kell a **Funkciókezelés** munkaterületen. Ezzel a funkcióval listát lehet adni azokról a raktárakról, amelyekre a DOM-nak figyelembe kell vennie akkor, amikor az optimalizálás teljesítési profillal fut. Ha nincs megadva ez a raktárlista, a DOM a profilban meghatározott jogi entitások összes raktárát figyelembe veszi.
        >
        > Ez a funkció egy olyan új konfigurációt ad a **Teljesítési profil** oldalhoz, amely egyetlen teljesítési csoporthoz kapcsolható. 
        >
        > Ha kiválasztja a teljesítési csoportot, akkor az adott teljesítési profil Felosztott rendeléskezelés szabályai fognak hatékonyan futni a megfelelési csoportban lévő „szállítási” raktárakkal szemben. 
        > 
        > Ennek a funkciónak a hatékony használatához győződjön meg arról, hogy létezik egy olyan teljesítési csoport, amely tartalmazza az összes szállítási raktárat, majd társítsa a teljesítési csoportot a teljesítési profilhoz.

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

Miután a DOM alkalmazta a szabályokat, a készletkorlátokat és az optimalizációt, kiválasztja a vevő szállítási címéhez legközelebbi helyet. A DOM a **Szállítás** típus címeit földrajzi szélességi és hosszúsági értékekre alakítja át. Ezt követően az értékesítési rendelésen szereplő szállítási címet is földrajzi szélességi és hosszúsági értékekké alakítja, valamint frissíti a cím földrajzi szélességi és hosszúsági értékeit későbbi használatra. A DOM a Bing Térképek rendszerétől függ a pontos földrajzi szélességi és hosszúsági értékek meghatározásánál az utca és házszám, a város és az irányítószám alapján.

A DOM a Bing Térképek API-t használja a légi és szárazföldi úttávolság kiszámítására, a beállításoktól függően. Ezután ezek az adatok alapján határozzák meg a szállítási költséget. Az optimalizálási modell priorizálja a teljes rendelés egy helyről történő teljesítését. Még ha a rendelés egy része ugyanabban a városban vagy irányítószámon is elérhető, a modellt úgy optimalizálták, hogy csökkentse a szállítmányok számát. 

A DOM a rendelkezésre álló készletet a V2 raktári entitások aktuális készletének megtekintésével keresi meg. A DOM minden kötegfuttatás során kötegekre bontja a rendeléseket, a profilban meghatározott feladatok **DOM-feldolgozó** paraméterértékétől függően. Ennek a paraméternek az alapértelmezett értéke **2000**. Ha például 10 000 rendelési sor optimalizálása történik egy futtatás során, és a **DOM-feldolgozó** paraméter értéke az alapértelmezés szerinti **2000**, akkor a DOM öt köteget hoz létre, amelyeket egyszerre dolgoz fel. A teljesítési terveket ezután az optimalizálóból lehet megkapni és alkalmazni a soron. Ha a rendeléssort két hely között kell felosztani, akkor a DOM gondoskodik arról, hogy az árak és az adók megfelelően el legyenek osztva a sorok között.

![Értékesítési rendelés feltételei.](./media/ordercriteria.png "Értékesítési rendelés feltételei")

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
- A Microsoft még nem tesztelte a DOM-ot speciális raktárkezelési funkciókkal. Így tehát a vevőknek és partnereknek óvatosnak kell lenniük, amikor annak megállapítására törekszenek, hogy a DOM kompatibilis-e a számukra releváns speciális raktárkezelési lehetőségekkel és folyamatokkal. A speciális raktárkészlet-nyilvántartás lehetővé teszi a konfigurálható dimenziókat, például a készlet állapotát, amely nem ad pontos képet a rendelkezésre álló készletről. A DOM kiterjeszthető módszert biztosít az elérhető készletek beállításához a speciális raktárkészlet-nyilvántartást használó megvalósítások esetén. Felhasználható a készletállapot és egyéb dimenziók testreszabott értékeivel való munkához.

    A DOM kiterjeszthetősége korlátozott, mert az optimalizálás az előre felépített MIP-modellben történik, amely figyelembe veszi az optimalizálást és a korlátozásait. Már több kiterjeszthető pont is elérhető a készlet beállításához és a feldolgozás utáni optimalizáláshoz. A DOM-profilok értékesítési eredet és szállítási mód szerint eltérőek lehetnek. Az értékesítési rendelés eredetét a rendelési folyamat során lehet beállítani, és ezek az értékek alapján különböző optimalizálási stratégiákat lehet alkalmazni. A DOM olyan egyéni kötegelt feladatok létrehozását is támogatja, amelyek bemenetként a DOM-feldolgozó feladatot is átvehetik, és lehetővé teszik, hogy a profil paraméterként legyen átadva. Így a különböző üzleti forgatókönyvek támogatása érdekében az egyik optimalizálás a másik után futtatható.

- A DOM csak a Commerce felhőalapú verziójában elérhető. A helyszíni telepítésű verziókban nem támogatott.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
