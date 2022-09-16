---
title: Feladatkezelés
description: Ez a cikk bemutatja a Microsoft által elérhető feladatkezelési funkciókat Dynamics 365 Human Resources.
author: twheeloc
ms.date: 09/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2022-06-09
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 29b547ff4f55b572ab774e7e70949ec8cb53ef42
ms.sourcegitcommit: 167f73a834629752c6b79c312d744e52df7f0927
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/08/2022
ms.locfileid: "9445894"
---
# <a name="task-management"></a>Feladatkezelés

[!INCLUDE [PEAP](../includes/peap-1.md)]

A feladatkezelés segítségével olyan feladatokat hozhat létre, amelyekhez az alkalmazottak felvételéhez (a hajó fedélzetére), felmondásához és az átvitelhez (átálláshoz) szükséges feladatokat kell elvégezni. A feladatkezelés az ellenőrzőlisták fogalmát használja. Az ellenőrzőlista tartalmazza a be- és kijelentkezési, illetve az átállási feladatok listáját. A feladatkezelés az ellenőrzőlisták segítségével csoportosítja a feladatokat, és hozzárendeli azokat az egyes személyekhez és csoportokhoz. Az ellenőrzőlista-funkciók hasonlóak a be- és kijelentkezés, valamint az átmenetek esetéhez.

## <a name="checklist-overview"></a>Ellenőrzőlista áttekintése

Az ellenőrzőlista feladatok egy csoportja. Az ellenőrzőlisták rugalmasan csoportosíthatók a feladatok, és felhasználhatók (például további alkalmazottak felvétele esetén). Annyi ellenőrzőlistát hozhat létre, amennyit csak szeretne, és ugyanazt a feladatot több ellenőrzőlistához rendelheti hozzá.

### <a name="examples"></a>Példák

Az alábbi példák bemutatják, hogy hogyan használhatók az ellenőrzőlisták a berakodási folyamatban. Mivel azonban az ellenőrzőlista a be- és kijelentkezési, valamint az átállási funkciókhoz is hasonló, az adatok a külső és az áttérési folyamatokra is vonatkoznak.

A berakodási folyamat részeként az emberi erőforrások (HR) szakemberek olyan feladatokat hozhatnak létre, amelyek nyomon követik a bejövő és a legutóbb felvett alkalmazottak haladását. Mivel a felvétel folyamata az alkalmazott beosztásától vagy földrajzi helyétől függően eltérő lehet, több, a felvételhez szükséges ellenőrzőlistát is létre lehet hozni a különböző felvételi helyzetek kezelésére.

**1. példa**

Az Egyesült Államokban felvett valamennyi alkalmazottnak el kell elvégeznie bizonyos feladatokat, például az adóelőleg-képernyők kitöltését. Előfordulhat azonban, hogy a céges autó hozzárendelése csak a vezetői szintű munkatársakra vonatkozik. Ebben az esetben két bevezető ellenőrzőlistát lehet létrehozni: **csak az Egyesült Államokon alapuló alkalmazottakat** és **a vezetőket**. Ezt követően, amikor egy középső szintű vezetőt az Egyesült Államokban alkalmaznak, az egyesült **államokbeli** alkalmazottak ellenőrzőlistája lesz kiválasztva. Amikor azonban egy vezetőt az Egyesült Államokban alkalmaznak, mindkét ellenőrzőlista be van jelölve, hogy minden szükséges berakodható feladat be legyen fejezve.

**2. példa**

Egy vállalatnál szezonális alkalmazottak és rendszeres, teljes munkaidős alkalmazottak is vannak. Bár bizonyos feladatok (például az új alkalmazott érkezésének ellenőrzése) mindkét típusú alkalmazottra vonatkoznak, néhány további feladat csak a rendes teljes munkaidős alkalmazottakra vonatkozik. Ebben az esetben két ellenőrzőlistát hozhat létre. Mindkét ellenőrzőlista tartalmazza a szezonális és a rendes teljes munkaidős alkalmazottakra vonatkozó feladatokat, de csak egy ellenőrzőlista tartalmazza a rendes teljes munkaidős alkalmazottakra jellemző feladatokat.

## <a name="task-management-workspace"></a>Feladatkezelési munkaterület

A **Feladatkezelés munkaterülete** felsorolja azokat a feladatokat, amelyek a berakodási, offboarding és áttérési folyamatokban egyes személyekhez vannak rendelve. Egy folyamat feladatainak megtekintéséhez válassza ki a megfelelő lapot a bal felső sarokban: **Beszúrás,** Offboarding **vagy** Transitions **.** Alapértelmezés szerint csak hr-szakemberek férhetnek hozzá a Feladatkezelés **munkaterülethez**.

A **Felvétel lap tartalmaz egy** **Hamarosan** induló listát, amely a bejövő alkalmazottakat és a **legutóbb** felvett alkalmazottakat jeleníti meg. Mindkét listán csak egy alkalmazottat választhat. Amikor kiválaszt egy alkalmazottat, a lap jobb oldalán az adott alkalmazotthoz kapcsolódó összes feladat megjelenik a lap jobb oldalán. A **Berakodva** **lap** tartalmaz egy Minden feladat listát is, amely minden beérkező vagy legutóbb felvett alkalmazott minden feladatát megjeleníti. Végül tartalmazza a lejárt feladatok listáját és az aktuális felhasználóhoz rendelt feladatok listáját.

Az **Offboarding lap** felsorolja azokat az alkalmazottakat, akik kilépnek a vállalatból, és listát tartalmaz azokról az alkalmazottakról, akik már kilépett a vállalatból. Mindkét listán csak egy alkalmazottat választhat. Alkalmazott kiválasztásakor az alkalmazott külső tevékenységével kapcsolatos összes feladat megjelenik. A **Offboarding lap** tartalmaz egy **Minden** feladat listát is, amely minden kilépést vagy kilépést tartalmazó alkalmazott minden feladatát megjeleníti. Végül tartalmazza a lejárt feladatok listáját és az aktuális felhasználóhoz rendelt feladatok listáját.

Az **Átmenetek lap** tartalmaz **egy** Minden feladat listát, amely minden olyan alkalmazott feladatát megjeleníti, aki beosztást fog módosítani, vagy aki legutóbb módosította a beosztásait. Megjelenik a lejárt feladatok listája és az aktuális felhasználóhoz rendelt feladatok listája.

Az HR asszisztensek és vezetők mindhárom lapon a következő tevékenységeket használhatja:
- Ellenőrzőlista alkalmazása alkalmazottra
- Feladat állapotának frissítése
- Feladat ismételt hozzárendelése
- Feladat határidőinek frissítése

> [!NOTE]
> A Berakodva **lap** alapértelmezés szerint az elmúlt hét napban felvett alkalmazottakat jeleníti meg. A beállítás módosítása **érdekében** **·** **adjon meg egy időkeretet az Emberi erőforrások paraméterei lap Általános lapján a Legutóbbi felvétel** mezőben. A közelmúltbeli felvétellista **adatai** adott számú napra, hónapra vagy évre vonatkoznak. Az elmúlt 14 napban felvett alkalmazottak listájának megtekintéséhez például állítsa az Időszak mezőt 14-re **·** **,** **az** Egység mezőben pedig a Napok **mezőt.**
> Az Emberi **erőforrások** **paraméterei lapon frissítheti a kilépési és kilépési alkalmazottak listáinak dátumtartományát is, amelyek az Offboarding lapon jelennek** meg. Ezek a beállítások a Személyzeti kezelés **munkaterületre is vonatkoznak**.

## <a name="setting-up-tasks"></a>Feladatok beállítása

A feladatokat egyenként is létre lehet hozni, majd újra fel lehet használni őket több ellenőrzőlistán. Feladat létrehozásához válassza az Új **lehetőséget** **a** Berakodva beállítási lapon, a Feladatok **lapon.**

Ha egy létrehozott feladatot több ellenőrzőlistához szeretne hozzárendelni, **válassza ki a feladatot, majd válassza az Alkalmazva az ellenőrzőlistákra** parancsot a menüben.

Közvetlenül is hozzá lehet adni feladatokat az ellenőrzőlistához. Feladat **feladatnak** **az ellenőrzőlistához való hozzáadásához hozzon létre egy új ellenőrzőlistát az Ellenőrzőlista** lapon, vagy vegye fel a feladatot egy meglévő ellenőrzőlistához.

A tárban található feladat szerkesztéséhez válassza **a** Feladattár menü Szerkesztés parancsát. Ha a feladat bármilyen ellenőrzőlistához hozzá van társítva, **ezek az ellenőrzőlisták megjelennek a Feladat szerkesztése lapon**. Ha azt szeretné, hogy az ellenőrzőlistákban található feladatok a szerkesztéssel frissüljön, jelölje ki azokat az ellenőrzőlistát az **Alkalmaz az ellenőrzőlistákra szakaszban**.

Ha törölni szeretné a feladatokat a tárból, válassza a Törlés **lehetőséget**. Ha egy feladat bármilyen ellenőrzőlistához hozzá van társítva, ez a művelet nem törli a feladatot az ellenőrzőlistán. A feladatot külön műveletben el kell távolítani az ellenőrzőlistán.

> [!NOTE]
> Ha egy feladatot közvetlenül az ellenőrzőlistához ad hozzá, akkor azt nem használhatja újra más ellenőrzőlistákon.

A következő táblázat leírja azokat a mezőket, amelyek akkor érhetők el, ha valamelyik módszerrel hoz létre feladatot.

| Mező           | Leírás |
|-----------------|-------------|
| Feladat            | Adja meg a feladat nevét. |
| Leírás     | Adja meg a feladat leírását. |
| Választható        | Adja meg, hogy a feladat nem kötelező, és csak tájékoztatásra való. |
| Feladathivatkozás       | Adja meg egy külső weboldal vagy az alkalmazás egy olyan lapja URL-címét, ahol a felhasználónak el kell végrehajtania a feladatot. A további tudnivalókat lásd a Feladathivatkozások [szakaszban](#task-links). |
| Hozzárendelés típusa | A feladatok adott dolgozóhoz, beosztáshoz vagy beosztáscsoporthoz, az érintett alkalmazott (vagyis a be- vagy külsős vagy átmeneti folyamathoz rendelt alkalmazott) vagy az érintett alkalmazott kezelőjébe rendelhetők. A hozzárendelés típusának kiválasztása. A további tudnivalókat lásd a Hozzárendelési [típusok szakaszban](#assignment-types). |
| Hozzárendelve a következőhöz:     | Annak a dolgozónak, beosztásnak vagy beosztáscsoportnak a kiválasztása, akihez a feladatot hozzárendeli. |
| Kapcsolattartó  | Annak a személynek a megadása, akivel kapcsolatba kell lépni, ha kérdések vannak a feladattal kapcsolatban. |
| Határidő eltolása | Adja meg, hogy hány nappal a feladat befejezésének, befejezésének vagy áttérésének dátuma előtt vagy után legyen esedékes a feladat. A további tudnivalókat [lásd a Feladat határidői és a Határidő ellenszámlája mezőben](#task-due-dates-and-the-due-date-offset-field). |
| Útmutatás    | Útmutatások beírása a feladat befejezéséhez. A további tudnivalókat lásd az Utasítások [szakaszban](#instructions). |

### <a name="task-links"></a>Feladathivatkozások

A feladathivatkozás egy külső weboldalra vagy a Dynamics 365 alkalmazás egy lapjára mutató hivatkozást tartalmaz. A feladat hivatkozását megadhatja, ha a feladat végrehajtásához a feladat végrehajtásához a Dynamics 365 alkalmazás egy meghatározott weblapjára vagy lapjára kell ugrást végrehajtania. Feladathivatkozás létrehozásakor a következő lehetőségek közül választhat:

- **Menüelem** – ha ezt a lehetőséget választja, megjelenik a Dynamics 365 alkalmazás összes oldalának listája. Válasszon egy lapot a listából.
- **URL** – ha ezt a lehetőséget választja, adja meg annak a weblapnak az URL-címét, amelybe a feladathoz rendelt személyt el szeretné menni. A megadott lap olyan lap lehet, amely nem része a Dynamics 365 alkalmazásnak.
- **Dolgozó részletei** – ha ezt a lehetőséget választja, válasszon a következő lehetőségek közül:

    - **Alkalmazotti önkiszolgáló műveletek** – ez a beállítás az alkalmazotti **önkiszolgáló szolgáltatásban elérhető lapok listáját jeleníti meg**. Akkor használja, **ha a felvehető alkalmazotthoz rendelt feladatot az Alkalmazott önkiszolgáló szolgáltatásban kell végrehajtani**. Ha például azt szeretné, hogy az alkalmazott adja meg személyes kapcsolattartási adatait, válassza ki **az** alkalmazott önkiszolgáló tevékenységét, majd **válassza a Személyes adatok&gt; adatokat**.
    - **Dolgozókezelési műveletek** – ez a beállítás megjeleníti a dolgozó rekordjához kapcsolódó, de az alkalmazott számára nem elérhető lapok listáját. Ha például azt szeretné, hogy a feladat tulajdonosa adja meg a beépített dolgozóra jellemző adatokat, például a kompenzációs adatokat, **válassza ki a Dolgozókezelési műveleteket,** **majd válassza a Fix kompenzáció kompenzációt&gt;.**

### <a name="assignment-types"></a>Hozzárendelés-típusok

Alkalmazott felvett, felmondási vagy átadási lehetőség esetén egy vagy több ellenőrzőlistát lehet kiválasztani. Az ellenőrzőlista kiválasztása után a felvételi, a felmondási vagy az áthelyezési folyamat befejeződése után létrejönnek a feladatok, és hozzárendelik őket a felhasználókhoz az előrehaladás nyomon követéséhez.

A feladat létrehozása után a feladat egy adott felhasználóhoz lesz hozzárendelve. Az a felhasználó, akihez a feladat hozzá van rendelve, az adott feladathoz kiválasztott hozzárendelés-típustól függ. A Hozzárendelés típusa mezőben a következő **értékek érhetők** el:

- **Dolgozó** – a feladat hozzárendelése egy adott dolgozóhoz. Az érték kiválasztása után válassza ki a dolgozót a Hozzárendelve **a mezőben**.
- **Beosztás** – a feladat hozzárendelése egy adott beosztáshoz. Az érték kiválasztása után válassza ki a pozíciót a Hozzárendelve **a mezőben**.

    Például egy számítógép-mérnöki felelős lesz például egy új alkalmazott hordozható számítógépének elkészítéséért. Ebben az esetben a hordozható **számítógép** konfigurációs feladatának létrehozásakor válassza a Pozíció típust hozzárendelési típusként, **majd válassza ki az It engineer pozíciót**. Ezután amikor egy alkalmazottat felvettek, és az ellenőrzőlistát hozzárendelték, a hordozható számítógép konfigurációs feladatához azt a feladatot rendeli hozzá a program, amelyik a felvételi művelet bevitelekor az it-mérnöki pozícióban van.

- **Csoport** – a feladat hozzárendelése beosztáscsoporthoz (hozzárendelési csoport). Az érték kiválasztása után válassza ki a csoportot a Hozzárendelve **a mezőben**. A további tudnivalókat lásd a Hozzárendelési [csoportok beállítása (Nem kötelező) szakaszban](#setting-up-assignment-groups-optional).
- **Vezető** – a feladat hozzárendelése annak az alkalmazottnak a felettesének, aki jelenleg fel van véve, el lett szüntetve vagy átkerült.

    > [!IMPORTANT]
    > Ellenőrzőlista alkalmazása esetén, ha jelenleg nincs beosztás rendelve a felvett, a kimondott vagy az áthelyezett alkalmazotthoz, akkor a vezető nem határozható meg. Ebben az esetben a feladat az ellenőrzőlista tulajdonosa lesz. További tájékoztatás az [Ellenőrzőlisták beállítása szakaszban](#setting-up-checklists) található.

- **Alkalmazott** – az alkalmazott hozzárendelése, munkaviszonya megszüntetése vagy átvitele folyamatban van.

### <a name="task-due-dates-and-the-due-date-offset-field"></a>Feladat határidői és a határidő ellenszámlája mező

A feladat határidői a foglalkoztatás kezdő dátumán, a munkaviszony megszűnésének dátumán vagy az áttérés dátumán alapulnak. Bizonyos feladatokat még az alkalmazott kezdési dátuma előtt el kell kezdeni, míg az egyéb feladatokat csak ezt követően lehet elvégezni. A feladat definiálása során **be** kell állítani a Határidő eltolása mezőt, hogy a kezdő dátumhoz, a felmondási dátumhoz vagy az áttérési dátumhoz viszonyított határidő legyen meghatározva. Például egy számítógép-mérnöki munkatársnak két nappal az alkalmazott kezdő dátuma előtt egy hordozható számítógépet kell előkészítenie az új alkalmazottak számára. Ebben az esetben a hordozható számítógép konfigurációs feladatának létrehozásakor állítsa **a Határidő ellenszámlája** **mezőt -2-re**. Ezt követően, ha az alkalmazott kezdési dátuma május 5., a feladat május 3-án lesz esedékes.

> [!NOTE]
> A határidő a feladat létrehozása után módosítható.

A határidők számítása az ellenőrzőlistához társított naptár alapján történik. További tájékoztatás az [Ellenőrzőlisták beállítása szakaszban](#setting-up-checklists) található.

### <a name="instructions"></a>Útmutatás

Az összetett feladatok végrehajtása több lépésből is áll, vagy lehet, hogy a feladatot végző személynek további információkat kell adnia. Az Utasítások **mezőben** útmutatásokat vagy további információkat lehet megadni, amelyek segítenek a feladathoz hozzárendelt személy befejezésében.

## <a name="setting-up-checklists"></a>Ellenőrzőlisták beállítása

Az ellenőrzőlista feladatok egy csoportja. Annyi ellenőrzőlistát hozhat létre, amennyit csak szeretne, és ugyanazt a feladatot több ellenőrzőlistához rendelheti hozzá.

Ha új feladatot hoz létre egy ellenőrzőlistán, válassza **a Feladatok** **menü** Új parancsát. Új feladat létrehozásakor választhatja azt, hogy hozzáadja a feladattárhoz, hogy több ellenőrzőlista között meg legyen osztva. A feladatot csak akkor használhatja a tárra, ha **a** Feladat alkalmazása a tárra beállítás Igen beállításra **van állítva**. Ha hozzáadja a feladatot a feladattárhoz, **akkor** azt is hozzáadhatja más ellenőrzőlistákhoz, ha az ellenőrzőlistákra alkalmazza az ellenőrzőlistát. Ha nem adja hozzá a feladatot a tárhoz, akkor az csak az ön által létrehozott ellenőrzőlistán fog létezik.

Az ellenőrzőlista egy feladatának szerkesztéséhez válassza a Szerkesztés **lehetőséget**. Ha a feladat bármilyen ellenőrzőlistához hozzá van társítva, **ezek az ellenőrzőlisták megjelennek a Feladat szerkesztése lapon**. Ha azt szeretné, hogy az egyéb ellenőrzőlistákban található feladatok frissüljön a szerkesztéssel, jelölje ki azokat az ellenőrzőlistát az **Alkalmaz az ellenőrzőlistákra szakaszban**.

Ha el szeretne távolítani feladatokat az ellenőrzőlistán, válassza az Eltávolítás **lehetőséget**. Ez a művelet csak a feladatokat távolítja el az ellenőrzőlistán. Nem törli őket a feladattárból. Ha törölni szeretne egy feladatot a tárból, kattintson a feladattár lapjára, és válassza a Törlés **lehetőséget**.

Ellenőrzőlista létrehozásakor meg kell adnia egy tulajdonost és egy naptárat.

**Ha egy feladat Hozzárendelés típus** mezőjének beállítása Beosztás, **·** **Vezető** vagy Csoport, de konkrét személy nem származhat a hozzárendelés típusból, akkor a **feladat** az ellenőrzőlista tulajdonosa lesz. Íme néhány példa olyan helyzetekre, amikor feladatok rendelhetők az ellenőrzőlista tulajdonosához:

- Nincs beosztás rendelve az alkalmazotthoz, aki jelenleg fel van véve vagy el lett szüntetve. Mivel az alkalmazottnak nincs beosztása, a felettesét nem lehet megállapítani.
- A **Hozzárendelés típusa mező** a Beosztás **értékre van állítva**, de a feladat létrehozásakor nincs alkalmazott hozzárendelve a beosztáshoz. Például a **Laptop** beállítási feladat a technikai támogatási szakértő 000876 rendelve **a beosztásszámhoz**. Az alkalmazott felvettekkor egy alkalmazott sem lesz a beosztáshoz rendelve 000876. Emiatt az ellenőrzőlista tulajdonosa számára létrejön egy feladat.
- A **Hozzárendelés típusa mező** beállítása **Csoport**, de a feladat létrehozásakor a csoport beosztásához nincs alkalmazott hozzárendelve.

Az ellenőrzőlistához megadott naptár alapján számítja ki a rendszer az ellenőrzőlistán található feladatok esedékességét. A munkanapokat és a nem munkavégzési napokat a naptár beállításai határozzák meg. A munkanapokat a feladatok határidőinek kiszámításakor kell figyelembe venni, és a nem munkanapok nem szerepelnek. A nem munkavégzési napok közé tartoznak a hétvégék és a munkaszüneti napok. 

A naptár beállítása után hozzá lesz társítva egy ellenőrzőlista-sablonhoz. Ily módon az ellenőrzőlista minden feladatának esedékességét ugyanúgy számítja ki a program. Több naptár is beállítható, de minden ellenőrzőlistához csak egy naptár társítható.

## <a name="setting-up-assignment-groups-optional"></a>Hozzárendelési csoportok beállítása (nem kötelező)

Esetenként az egyes személyek egy csoportja felelős a feladatért. Például egy csoportja az it-dolgozóknak lehet felelős a hordozható számítógépek új felvételhez való előkészítéséért.

A következő lépések szerint állíthatja be a hozzárendelési csoportokat.

1. A Csoport-hozzárendelés **lapon válassza az Új lehetőséget** **.**
1. Adjon meg egy nevet (például **hordozható** számítógép) és a csoport leírását.
1. Válassza a **Mentés** lehetőséget.
1. Válassza a **Tagok gyorsététi** gombra, és válassza a Hozzáadás **lehetőséget**.
1. A Beosztások **mezőben** válassza ki a feladatért felelős beosztásokat.

A hozzárendelési csoport létrehozása után ki lehet válogatni a feladat létrehozásakor. Egy feladat adott csoportjának kiválasztásához **a** Hozzárendelés típusban a Csoport lehetőséget **kell választania**. A létrehozott csoport ezután elérhető lesz kiválasztásra a Hozzárendelve **a mezőben**.

> [!IMPORTANT]
> Ha egy feladat csoporthoz van rendelve, akkor a feladat **Készként** lesz megjelölve, amikor a csoportban egy személy befejezi a feladatot. A feladatok létrehozása a felvétel, a munkaviszony megszüntetése vagy az átállás során megszabad. Ezek a csoportba foglalt beosztások felhasználóihoz vannak hozzárendelve.

## <a name="setting-up-task-groups-optional"></a>Feladatcsoportok beállítása (nem kötelező)

A berakodási, a külsős vagy az áttérési folyamat több feladatot tartalmazhat. Ha egyszerűbbé szeretne tenni az összes szükséges feladat ellenőrzőlistához való hozzárendelését, létrehozhat feladatcsoportokat a kapcsolódó feladatok kategóriákba sorolása érdekében. Például az emberi erőforrásokkal, az itekkel és a bérszámfejtési részlegekkel kapcsolatos feladatokat kell elvégezniük ahhoz, hogy új alkalmazottat vegyenek fel. Ezért a következő feladatcsoportok hozhatók létre: **HR**, **It** és **Payroll**. Ezután a feladat létrehozásakor társítani lehet a feladatcsoportok valamelyikét.

Ha feladatot szeretne hozzáadni egy ellenőrzőlistához, a feladatok listáját szűrheti azon feladatcsoport szerint, amelybe a kívánt feladat tartozik. Például ellenőrzőlista-sablon létrehozásakor szűrheti a listát, **hogy csak az it-feladatcsoporthoz rendelt it-feladatok** jelennek meg. Így biztos lehet benne, hogy csak a fontos it-it feladatok vannak kiválasztva.

## <a name="using-checklists"></a>Ellenőrzőlisták használata

Dolgozó felvett, felmondási vagy átvitt feladatlistája választható. A feladatok határidői és a dolgozók hozzárendelései a felvételi, a felmondási és az áttérési folyamat befejezése után jön létre. Ha például a Felvétel vagy **felvétel** **gombra** kattint, és hozzáadja a részleteket, a hozzárendelés típusától függően az egyes személyek számára jön létre feladat.

Az egyes feladatokhoz úgy lehet határidőt rendelni, hogy hozzáadják az alkalmazott kezdő dátumát, vagy kivonják az esedékesség dátumát a határidőből. A további tudnivalókat [lásd a Feladat határidői és a Határidő ellenszámlája mezőben](#task-due-dates-and-the-due-date-offset-field).

Személyzeti műveletek használata esetén a feladatok akkor jön létre, **amikor** a Kész gomb be van jelölve, vagy a műveletet jóváhagyják.

A Feladatkezelés **munkaterületen** alkalmazhat ellenőrzőlistát az alkalmazottakhoz úgy, hogy kijelöli az alkalmazottat az egyszerű listaoldalon vagy a részletek lapján, **majd az Ellenőrzőlista alkalmazása adatokat választ.** A feladatok határidőinek **kiszámításához** a Rendszer a Céldátum mező értékét használja. A céldátumnak általában meg kell egyeznie az alkalmazott felvételének, munkaviszonyának vagy átmeneti dátumának.

Az alkalmazottakhoz úgy is **alkalmazhat** **ellenőrzőlistát, hogy megnyitja a Dolgozó lapot, és a menü Ellenőrzőlistája** lehetőséget választják.

## <a name="completing-tasks"></a>Feladatok befejezése

Az Alkalmazott **– önkiszolgáló** oldalon az alkalmazottak megtekinthetik az összes hozzájuk rendelt feladatot. Minden hozzárendelt feladathoz **megjelennek a Feladat**, **Leírás**, Utasítások **és** **Kapcsolattartó értékek**. Ezenkívül minden feladathoz megnyithatja a kapcsolódó külső webhelyet vagy a kapcsolódó lapot a Dynamics 365 alkalmazásban.

A feladatok az alapértelmezett irányítópulton is megjeleníthetőek. A következő műveletek megjelenítése az alapértelmezett irányítópulton:
1. Ugrás a felhasználói **beállításokhoz – Beállítások – Feladatkezelés** 
2. Válassza a **Feladatok megjelenítése az alapértelmezett irányítópulton lehetőséget a** Be **megjelenik beállításra**.  

>[!Note] 
>Ahhoz **, hogy** a Felhasználói beállítások között **meg** legyen jelenítve a Funkciókezelés funkció, be kell kapcsolva lennie a Feladatkezelés **funkciónak**.

A feladatokat megjelölheti Folyamatban **,** **Visszavonva** vagy **Készként**. Ha egy feladatot hozzárendeltek egy csoporthoz, **akkor** Az Készként lesz megjelölve, amikor a csoportban egy személy befejezi a feladatot.

A feladatok újraoszthatóak.
