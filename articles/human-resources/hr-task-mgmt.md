---
title: Feladatkezelés
description: Ez a témakör a Microsoftban elérhető feladatkezelési funkciókat ismerteti Dynamics 365 Human Resources.
author: twheeloc
ms.date: 12/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-29-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 727e1eb75f807d84f088cf3dd139eb094aa76618
ms.sourcegitcommit: 7893ffb081c36838f110fadf29a183f9bdb72dd3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/02/2022
ms.locfileid: "8087217"
---
# <a name="task-management"></a>Feladatkezelés

[!INCLUDE [PEAP](../includes/peap-1.md)]

A Feladatkezelés lehetővé teszi olyan feladatok létrehozását, amelyeket el kell végezni az alkalmazottak felvételéhez (beépített), felmondásához (offboard) és áthelyezéséhez (átmenet). A feladatkezelés az ellenőrző listák fogalmát használja. Az ellenőrző lista a belépési, kilépési vagy átállási feladatok listája. A feladatkezelés ellenőrzőlisták segítségével csoportosítja a feladatokat, és hozzárendeli azokat egyénekhez vagy csoportokhoz. Az ellenőrzőlista-funkciók a be- és kilépéshez és az átmenetekhez hasonlóak.

## <a name="checklist-overview"></a>Ellenőrzőlista áttekintése

Az ellenőrző lista feladatok csoportja. Az ellenőrzőlisták rugalmas módot kínálnak a feladatok csoportosítására, és újra felhasználhatók (például további alkalmazottak felvételekor). Annyi ellenőrzőlistát hozhat létre, amennyit csak szeretne, és ugyanazokat a feladatokat több ellenőrzőlistához is hozzárendelheti.

### <a name="examples"></a>Példák

A következő példák bemutatják, hogyan használhatók fel az ellenőrző listák a bevezető folyamatban. Mivel azonban az ellenőrzőlista-funkciók a beépítéshez, a kilépéshez és az átmenetekhez hasonlóak, az információ a kilépési és átállási folyamatokra is vonatkozik.

A bevezetési folyamat részeként a humánerőforrás (HR) szakemberei olyan feladatokat hozhatnak létre, amelyek nyomon követhetik a bejövő és nemrég felvett alkalmazottak felvételi folyamatát. Mivel a felvételi folyamat az alkalmazott pozíciójától vagy földrajzi elhelyezkedésétől függően változhat, több felvételi ellenőrzőlistát is létrehozhat a különböző felvételi helyzetekhez.

**1. példa**

Minden egyesült államokbeli alkalmazottnak el kell végeznie olyan feladatokat, mint például az adólevonási űrlapok kitöltése. Előfordulhat azonban, hogy az olyan feladatok, mint például a céges autó kijelölése, csak a vezetői szintű alkalmazottakra vonatkozhatnak. Ebben az esetben két bevezető ellenőrző lista hozható létre: **USA-beli alkalmazottak** és **Csak vezetők**. Aztán amikor az Egyesült Államokban felvesznek egy középszintű menedzsert, a **USA-beli alkalmazottak** ellenőrzőlista van kiválasztva. Amikor azonban egy vezetőt alkalmaznak az Egyesült Államokban, mindkét ellenőrző lista kiválasztásra kerül annak biztosítására, hogy az összes szükséges bevezetői feladatot elvégezzék.

**2. példa**

Egy cégnek szezonális és teljes munkaidős alkalmazottai egyaránt vannak. Bár egyes feladatok (például az új munkavállaló érkezési idejének ellenőrzése) mindkét típusú munkavállalóra vonatkoznak, néhány további feladat csak a normál teljes munkaidős alkalmazottakra vonatkozik. Ebben az esetben két ellenőrző listát hozhat létre. Mindkét ellenőrző lista tartalmazza azokat a feladatokat, amelyek mind a szezonális, mind a normál teljes munkaidős alkalmazottakra vonatkoznak, de csak az egyik ellenőrzőlista tartalmazza azokat a feladatokat, amelyek a normál teljes munkaidős alkalmazottakra vonatkoznak.

## <a name="task-management-workspace"></a>Feladatkezelési munkaterület

A **Feladatkezelés** A munkaterület felsorolja az összes olyan feladatot, amelyet az egyénekhez rendeltek a be-, kilépési és átállási folyamatok során. Egy folyamat feladatainak megtekintéséhez válassza ki a megfelelő lapot a bal felső sarokban: **Beszállás**, **·**, vagy **Átmenetek**. Alapértelmezés szerint csak HR-esek férhetnek hozzá a **Feladatkezelés** munkaterület.

A **Beszállás** lap tartalmazza a **Hamarosan kezdődő** lista, amelyen a bejövő alkalmazottak és a **Legutóbbi bérbeadások** lista, amely a nemrég felvett alkalmazottakat tartalmazza. Mindkét listában csak egy alkalmazottat választhat ki. Amikor kiválaszt egy alkalmazottat, az oldal jobb oldalán megjelenik az összes olyan feladat, amely az alkalmazott felvételével kapcsolatos. A **Beszállás** lap is tartalmaz egy **Minden feladat** lista, amely az összes bejövő vagy nemrég felvett alkalmazott összes feladatát mutatja. Végül tartalmazza a lejárt feladatok listáját és az aktuális felhasználóhoz rendelt feladatok listáját.

A **Offboarding** A lap a vállalattól kilépő alkalmazottak listáját és a cégtől már kilépő alkalmazottak listáját tartalmazza. Mindkét listában csak egy alkalmazottat választhat ki. Amikor kiválaszt egy alkalmazottat, minden olyan feladat megjelenik, amely az adott alkalmazott kilépésével kapcsolatos. A **Offboarding** lap is tartalmaz egy **Minden feladat** lista, amely az összes kilépő vagy kilépő alkalmazott összes feladatát mutatja. Végül tartalmazza a lejárt feladatok listáját és az aktuális felhasználóhoz rendelt feladatok listáját.

A **Átmenetek** lap tartalmaz egy **Minden feladat** lista, amely az összes pozíciót megváltoztató vagy a közelmúltban pozíciót váltott munkavállaló összes feladatát mutatja. Itt található a lejárt feladatok listája és az aktuális felhasználóhoz rendelt feladatok listája is.

A HR-asszisztensek és vezetők mindhárom lapon a következő tevékenységeket hajthatják végre:

- Alkalmazzon ellenőrző listát egy alkalmazottnak.
- Frissítse a feladat állapotát.
- Új feladat hozzárendelése.
- Frissítse egy feladat esedékességi dátumát.

> [!NOTE]
> Alapértelmezés szerint a **Beszállás** lapon az elmúlt hét napban felvett alkalmazottak láthatók. A beállítás módosításához a **Emberi erőforrás paraméterek** oldalon, a **Tábornok** lapon, a **Legutóbbi bérbeadások** mezőben adja meg az időkeretet. Az információ a **Legutóbbi bérbeadások** a lista adott számú napra, hónapra vagy évre vonatkozóan jeleníthető meg. Például az elmúlt 14 napban felvett alkalmazottak listájának megtekintéséhez állítsa be a **Időszak** mezőt **14** és a **Mértékegység** mezőt **Napok**.
>
> A **Emberi erőforrás paraméterek** oldalon frissítheti a kilépő és kilépő alkalmazottak listájának dátumtartományát is **Offboarding** lapon.
>
> Ezek a beállítások a **Személyzeti menedzsment** munkaterület.

## <a name="setting-up-tasks"></a>Feladatok beállítása

A feladatokat egyenként is létrehozhatja, majd több ellenőrzőlistában is felhasználhatja. Feladat létrehozásához a **Bevezetési beállítás** oldalon, a **Feladatok** lapon válassza ki **Új**.

Alternatív megoldásként feladatokat közvetlenül is hozzáadhat egy ellenőrzőlistához. Ha egy tevékenységet ellenőrzőlistához szeretne hozzáadni, a **Bevezetés beállítási** lapján, az **Ellenőrzőlista** lapon hozzon létre egy új ellenőrzőlistát a tevékenység hozzáadásához, vagy adja hozzá a feladatot egy meglévő ellenőrzőlistához.

> [!NOTE]
> Ha egy tevékenységet közvetlenül egy ellenőrzőlistához ad hozzá, azt más ellenőrző listákban nem használhatja fel újra.

Az alábbi táblázat azokat a mezőket ismerteti, amelyek akkor érhetők el, ha egy tevékenységet bármelyik módszerrel hoz létre.

| Mező           | Leírás |
|-----------------|-------------|
| Feladat            | Adja meg a tevékenység nevét. |
| Leírás     | Adja meg a tevékenység leírását. |
| Választható        | Adja meg, hogy a tevékenység nem kötelező-e, és csak tájékoztató-e. |
| Feladathivatkozás       | Adja meg egy külső weblap vagy egy adott oldal URL-címét az alkalmazásban, ahol a felhasználónak végre kell hajtania a feladatot. További információért lásd a [Tevékenységhivatkozások](#task-links) szakaszt. |
| Hozzárendelés típusa | A feladatok hozzárendelhetők egy adott dolgozóhoz, pozícióhoz vagy pozíciócsoporthoz, az érintett alkalmazott vezetőjéhez (azaz a bevezetési, offboarding vagy átmeneti folyamat részét képező alkalmazotthoz) vagy az érintett alkalmazotthoz. Válassza ki a hozzárendelés típusát. További információért lásd a [Hozzárendelés-típusok](#assignment-types) szakaszt. |
| Hozzárendelve a következőhöz:     | Válassza ki azt az adott dolgozót, pozíciót vagy pozíciócsoportot, amelyhez a tevékenységet hozzá szeretné rendelni. |
| Kapcsolattartó  | Adja meg azt a személyt, akivel kapcsolatba kell lépnie, ha kérdése van a feladattal kapcsolatban. |
| Határidő eltolása | Adja meg a tevékenység esedékes be- és bekapcsolási, befejezési vagy átmeneti dátuma előtti vagy utáni napok számát. További információt a [Tevékenység esedékességnapok és a Határidő eltolás mező című szakaszban talál](#task-due-dates-and-the-due-date-offset-field). |
| Utasítások    | Adja meg a feladat elvégzésére vonatkozó utasításokat. További információért lásd az [Utasítások](#instructions) szakaszt. |

### <a name="task-links"></a>Feladathivatkozások

A feladathivatkozás egy külső weblapra vagy lapra mutató hivatkozást tartalmaz a Dynamics 365 alkalmazásban. Megadhatja a tevékenységhivatkozást, ha a tevékenységhez rendelt személynek a Dynamics 365 alkalmazás egy adott weblapjára vagy egy adott lapjára kell mennie a feladat elvégzéséhez. Tevékenységhivatkozás létrehozásakor az alábbi lehetőségek közül választhat:

- **Menüpont** – Ha ezt a lehetőséget választja, megjelenik a Dynamics 365 alkalmazás összes oldalának listája. Jelöljön ki egy oldalt a listában.
- **URL –** Ha ezt a beállítást választja, adja meg annak a weblapnak az URL-címét, amelyhez a feladathoz rendelt személynek mennie kell. A megadott lap lehet olyan lap, amely nem része a Dynamics 365 alkalmazásnak.
- **Dolgozói adatok** – Ha ezt a lehetőséget választja, válasszon az alábbi lehetőségek közül:

    - **Alkalmazotti önkiszolgáló műveletek** – Ez a beállítás az Alkalmazott önkiszolgáló **szolgáltatásában** elérhető oldalak listáját jeleníti meg. Akkor használja, ha a beépített alkalmazotthoz rendelt feladatot az Alkalmazott önkiszolgáló szolgáltatásában **kell** elvégezni. Ha például azt szeretné, hogy az alkalmazott megadja a személyes kapcsolattartási adatait, válassza az **Alkalmazott önkiszolgáló műveletei lehetőséget**, majd válassza a Személyes adatok **személyes adatai&gt; lehetőséget**.
    - **Dolgozókezelési műveletek** – Ez a beállítás azoknak az oldalaknak a listáját jeleníti meg, amelyek a dolgozó rekordjához kapcsolódnak, de amelyek nem érhetők el az alkalmazott számára. Ha például azt szeretné, hogy a tevékenység tulajdonosa olyan adatokat adjon meg, amelyek egy beépített dolgozóra jellemzőek, például kompenzációs információkat, válassza a **Dolgozó felügyeleti műveletei lehetőséget**, majd válassza a CompensationFixed **kompenzáció lehetőséget&gt;**.

### <a name="assignment-types"></a>Hozzárendelés-típusok

Amikor egy alkalmazottat bérelnek, megszüntetnek vagy áthelyeznek, egy vagy több ellenőrzőlista választható ki. Az ellenőrzőlista kiválasztása és a felvételi, megszüntetési vagy átviteli folyamat befejezése után a rendszer feladatokat hoz létre és rendel a felhasználókhoz az előrehaladás nyomon követéséhez.

Amikor egy tevékenységet létrehoznak, az egy adott felhasználóhoz lesz rendelve. Az a felhasználó, akihez egy tevékenység hozzá van rendelve, az adott tevékenységhez kiválasztott hozzárendelés típusától függ. A Hozzárendelés típusa **mezőben a** következő értékek érhetők el:

- **Dolgozó** – Rendelje hozzá a feladatot egy adott dolgozóhoz. Miután kiválasztotta ezt az értéket, jelölje ki a dolgozót a **Hozzárendelve** mezőben.
- **Pozíció** – Rendelje hozzá a tevékenységet egy adott pozícióhoz. Miután kiválasztotta ezt az értéket, jelölje ki a pozíciót a **Hozzárendelt mezőhöz** mezőben.

    Például egy informatikai mérnök mindig felelős egy laptop előkészítéséért egy új alkalmazott számára. Ebben az esetben a laptop konfigurációs feladatának létrehozásakor válassza a Pozíció **hozzárendelési típusként lehetőséget**, majd válassza **az INFORMATIKAI mérnököt** pozícióként. Ezután, amikor egy alkalmazottat bérelnek fel, és az ellenőrzőlista hozzá van rendelve, a laptop konfigurációs feladata hozzá lesz rendelve ahhoz a dolgozóhoz, aki az informatikai mérnök pozícióban van a felvételi művelet megadásakor.

- **Csoport** – A tevékenység hozzárendelése pozíciók csoportjához (hozzárendelési csoport). Miután kiválasztotta ezt az értéket, jelölje ki a csoportot a Hozzárendelve **a** mezőben. További információt a [Hozzárendelés-csoportok beállítása (Nem kötelező)](#setting-up-assignment-groups-optional) című szakaszban talál.
- **Menedzser** – Rendelje hozzá a feladatot a bérelt, megszüntetett vagy áthelyezett alkalmazott vezetőjéhez.

    > [!IMPORTANT]
    > Ellenőrzőlista alkalmazásakor, ha jelenleg nincs hozzárendelve pozíció a bérelt, megszüntetett vagy áthelyezett alkalmazotthoz, a kezelő nem határozható meg. Ebben az esetben a feladat az ellenőrzőlista tulajdonosához van rendelve. További információért lásd az [Ellenőrző listák beállítása szakaszt](#setting-up-checklists).

- **Alkalmazott** – Rendelje hozzá azt az alkalmazottat, akit bérelnek, szüntetnek meg vagy helyeznek át.

### <a name="task-due-dates-and-the-due-date-offset-field"></a>Tevékenység esedékességnapok és a Határidő eltolás mező

A tevékenység esedékességének időpontjai a foglalkoztatás kezdő dátumán, befejezési dátumán vagy átmeneti dátumán alapulnak. Egyes feladatokat az alkalmazott kezdési dátuma előtt kell elvégezni, míg más tevékenységek később is elvégezhetők. Tevékenység definiálásakor a Határidő eltolás **mezőt úgy kell beállítania, hogy a** kezdő dátumhoz, a befejezési dátumhoz vagy az átmenet dátumához viszonyítva adjon meg egy határidőt. Például egy informatikai mérnöknek elő kell készítenie egy laptopot egy új alkalmazott számára két nappal az alkalmazott kezdő dátuma előtt. Ebben az esetben a laptop konfigurációs tevékenységének létrehozásakor állítsa a **Határidő eltolás** mezőt -2-re **·**. Ha a munkavállaló kezdési dátuma május 5., a feladat május 3-án esedékes.

> [!NOTE]
> A határidő a tevékenység létrehozása után módosítható.

A határidők kiszámítása az ellenőrzőlistához társított naptár alapján történik. További információért lásd az [Ellenőrző listák beállítása szakaszt](#setting-up-checklists).

### <a name="instructions"></a>Utasítások

Az összetett tevékenységek több lépést is igényelhetnek, vagy a feladatot végző személynek további információkat kell megadnia. **Az Utasítások** mezőben utasításokat vagy további információkat adhat meg, amelyek segítenek a tevékenységhez rendelt személynek a feladat elvégzésében.

## <a name="setting-up-checklists"></a>Ellenőrző listák beállítása

Az ellenőrző lista feladatok csoportja. Annyi ellenőrzőlistát hozhat létre, amennyit csak szeretne, és ugyanazokat a feladatokat több ellenőrzőlistához is hozzárendelheti. Ellenőrzőlista létrehozásakor meg kell adnia egy tulajdonost és egy naptárat.

**Ha egy tevékenység Hozzárendelés típusa** mező pozíció **,** kezelő **vagy** csoport **mezőben** van beállítva, de a hozzárendelés típusából nem lehet konkrét személy származtatni, a tevékenység az ellenőrzőlista tulajdonosához lesz rendelve. Íme néhány példa arra, hogy olyan helyzetekre, amikor a feladatokat hozzárendelik az ellenőrzőlista tulajdonosához:

- A bérbe vagy megszüntetett alkalmazotthoz nincs beosztás hozzárendelve. Mivel az alkalmazottnak nincs pozíció-hozzárendelése, a menedzserét nem lehet meghatározni.
- A **Hozzárendelés típusa** mező Pozíció **beállításra** van állítva, de a tevékenység létrehozásakor egyetlen alkalmazott sem van hozzárendelve a pozícióhoz. A telepítő laptop **feladat például a** 000876 (**műszaki támogatási szakember)** pozíciószámhoz van rendelve. Abban az időben, amikor egy alkalmazottat bérelnek, egyetlen alkalmazott sem van hozzárendelve a pozícióhoz 000876. Ezért létrejön egy feladat az ellenőrzőlista tulajdonosához.
- A **Hozzárendelés típusa** mező Csoportra **van** állítva, de a tevékenység létrehozásakor egyetlen alkalmazott sem lesz hozzárendelve a csoport pozícióihoz.

Az ellenőrzőlistához megadott naptár az ellenőrzőlista részét képező tevékenységek esedékességének kiszámítására szolgál. A munkanapok és a nem munkanapok a naptár beállítása határozza meg. A munkanapok a tevékenységek esedékességének kiszámításakor is szerepelnek, és a nem munkanapok ki vannak zárva. A nem munkanapok közé tartoznak a hétvégék és az ünnepek. 

A naptár beállítása után egy ellenőrzőlistasablonhoz van társítva. Ily módon az ellenőrzőlista minden tevékenységének esedékessége ugyanúgy kerül kiszámításra. Több naptárat is beállíthat, de minden ellenőrző listához csak egy naptár társítható.

## <a name="setting-up-assignment-groups-optional"></a>Hozzárendelési csoportok beállítása (nem kötelező)

Néha egyének egy csoportja felelős egy feladatért. Például az informatikai dolgozók egy csoportja felelős lehet a laptopok új bérlők számára való előkészítéséért.

Hozzárendelés-csoport beállításához kövesse az alábbi lépéseket.

1. A Csoport hozzárendelés **lapján válassza az** Új **lehetőséget**.
1. Adjon meg egy nevet (például **IT Laptop**) és a csoport leírását.
1. Válassza a **Mentés** lehetőséget.
1. A Tagok **gyorslapon válassza a** Hozzáadás **lehetőséget**.
1. **A Pozíciók** mezőben válassza ki a tevékenységért felelős összes pozíciót.

Hozzárendelés-csoport létrehozása után a tevékenység létrehozásakor kiválasztható. Egy tevékenység adott csoportjának kiválasztásához a Hozzárendelés típusban a Csoport **lehetőséget kell választania**.**·** A létrehozott csoport ezután kijelölhető lesz a Hozzárendelve **a** mezőben.

> [!IMPORTANT]
> Ha egy tevékenységet egy csoporthoz rendelnek, a tevékenység befejezettként **lesz** megjelölve, amikor a csoport egyik tagja befejezi azt. A feladatok a felvétel, a megszüntetés vagy az átmenet idején jönnek létre. A csoportban szereplő pozíciókhoz rendelt felhasználók számára jönnek létre.

## <a name="setting-up-task-groups-optional"></a>Feladatcsoportok beállítása (nem kötelező)

A be- és bevezetési, offboarding vagy átmeneti folyamat számos feladatot tartalmazhat. Annak érdekében, hogy megkönnyítse az összes szükséges tevékenység hozzárendelését egy ellenőrző listához, opcionális feladatcsoportokat hozhat létre a kapcsolódó tevékenységek kategorizálására. Például a HR, az IT és a Bérszámfejtési osztályoknak minden egyes feladatot el kell végezniük egy új alkalmazott felvételéhez. Ezért a következő feladatcsoportokat hozza létre: **HR**, **IT** és **Payroll**. Ezután egy tevékenység létrehozásakor társíthatja az egyik ilyen feladatcsoportot.

Ha egy tevékenységet szeretne hozzáadni egy ellenőrzőlistához, szűrheti a tevékenységek listáját a kívánt tevékenységhez rendelt tevékenységcsoport szerint. Ellenőrzőlistasablon létrehozásakor például szűrheti a listát úgy, hogy csak az informatikai **tevékenységcsoporthoz** rendelt informatikai tevékenységek jelenjenek meg. Ezért biztosíthatja, hogy csak a megfelelő informatikai feladatok legyenek kiválasztva.

## <a name="using-checklists"></a>Ellenőrző listák használata

Ha egy dolgozót bérelnek, megszüntetnek vagy áthelyeznek, egy vagy több ellenőrzőlista választható ki. A tevékenység esedékességnapjai és a munkavégző hozzárendelések a felvételi, végződési vagy átmeneti folyamat befejezése után jönnek létre. Ha például kiválasztja a **Bérlés** vagy **a Bérlés és a Részletek** hozzáadása gombot, a feladatok a hozzárendelés típusa alapján jönnek létre az egyének számára.

A határidőt úgy rendelik hozzá a rendszer az egyes tevékenységekhez, hogy hozzáadják vagy kivonják a határidő eltoltását az alkalmazott kezdő dátumából. További információt a [Tevékenység esedékességnapok és a Határidő eltolás mező című szakaszban talál](#task-due-dates-and-the-due-date-offset-field).

Ha személyzeti műveleteket használ, a feladatok a Befejezés **gomb kijelölésekor vagy a művelet jóváhagyásakor** jönnek létre.

A Feladatkezelés **munkaterületen ellenőrzőlistát alkalmazhat egy alkalmazottra, ha kiválasztja az alkalmazottat az egyszerű listaoldalon vagy a részletek lapon, majd kiválasztja** az Ellenőrzőlista alkalmazása lehetőséget **.** A céldátum **mező értéke a** tevékenységek esedékességének kiszámításához lesz számítva. A céldátumnak általában meg kell egyeznie az alkalmazott felvételi, felmondási vagy átmeneti dátummal.

Ellenőrzőlistát is alkalmazhat egy alkalmazottra, ha megnyitja **a Dolgozó** lapot, és kiválasztja **a menü ellenőrzőlistáját**.

## <a name="completing-tasks"></a>Feladatok elvégzése

Az Alkalmazott önkiszolgáló **oldalán az** alkalmazott megtekintheti a hozzájuk rendelt összes feladatot. Minden hozzárendelt tevékenységnél **megjelenik a Tevékenység**, **a Leírás**, **az Utasítások** és **a Kapcsolattartó személy** értékei. Ezenkívül az alkalmazott minden feladathoz megnyithatja a kapcsolódó külső weblapot vagy a hozzá tartozó oldalt a Dynamics 365 alkalmazásban.

A feladatok meg lehet jelölni folyamatban **lévőként,** megszakítva **vagy** befejezettként **·**. Ha egy tevékenységet egy csoporthoz rendeltek, akkor az befejezettként **lesz** megjelölve, amikor a csoport egyik tagja befejezi azt.

A feladatokat is át lehet írni.
