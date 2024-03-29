---
title: Alkalmazotti és vezetői önkiszolgáló rendszer áttekintése
description: Ez a témakör áttekintést nyújt az alkalmazottak és a vezetők önkiszolgáló munkaterületéről.
author: twheeloc
ms.date: 09/12/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.custom:
- "51941"
- intro-internal
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0ecc3f5ae03dda6932dfa111bd4d8b7e6e7b5c7f
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2022
ms.locfileid: "9702156"
---
# <a name="employee-and-manager-self-service-overview"></a>Alkalmazotti és vezetői önkiszolgáló rendszer áttekintése


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ez a témakör áttekintést nyújt az alkalmazottak és a vezetők önkiszolgáló munkaterületéről.

## <a name="edit-personal-details"></a>Személyi részletek szerkesztése

Ha bármilyen személyes információt kell hozzáadnia vagy módosítania, lásd: [Személyes adatok szerkesztése](hr-employee-manager-self-service-edit-personal-information.md).

## <a name="user-not-assigned-to-a-worker-record"></a>Dolgozói rekordhoz nem rendelt felhasználó

Ha a felhasználóját nem rendelte hozzá egy **Dolgozó** rekordhoz a **felhasználók** lapon, a következő üzenet jelenik meg:

**A felhasználóazonosítója nincs társítva az alkalmazotti rekordjához a rendszerben. Ebben a helyzetben nem fogja tudni megtekinteni vagy módosítani az adatait. Segítségért forduljon a feletteséhez vagy a támogatási csapathoz.**

Ha egy felhasználót egy **Dolgozó** rekordhoz szeretne társítani, navigáljon a **Felhasználók** helyre és válassza ki a felhasználót. Válassza a **Szerkesztés** parancsot , adja hozzá a megfelelő dolgozót az oldal **Személy** mezőjében, majd válassza a **Mentés** parancsot. Most már hozzáférhet az **Alkalmazotti önkiszolgálórendszerhez**.

## <a name="security-requirements-for-employee-and-manager-self-service"></a>Az alkalmazotti és a vezetői önkiszolgáló rendszer követelményei

Az alkalmazotti és a vezetői önkiszolgáló rendszer két biztonsági szerepkört kér:

- Az alkalmazottaknak szüksége van az Alkalmazott szerepkörre.
- A vezetőiknek mind az Alkalmazott, mind a Vezető szerepkör szükséges.

>[!NOTE]
>Az alkalmazotti és vezetői önkiszolgáló rendszerhez egyéni szerepkörök is használhatók, feltéve, hogy hozzáférést kaptak az Alkalmazott és a Vezető munkaterületekhez.<br>
>A vezetők hozzáférése az alkalmazotti adatkhoz Emberi erőforrások modulban megadott aktuális sorszerkezet alapján van meghatározva.

## <a name="employee-self-service"></a>Alkalmazotti önkiszolgáló rendszer

A **Saját adatok** lap az **Alkalmazotti önkiszolgáló rendszer** következő adatait jeleníti meg.  

### <a name="summary"></a>Összegzés

A **Hozzám rendelt munkaelemek** az alkalmazotthoz rendelt összes jóváhagyást és munkafolyamatelemet jelenítik meg. A munkafolyamat-elemeket úgy is konfigurálhatja, hogy e-maileket küldjenek a felhasználónak.

A **Hozzám rendelt kérdőívek** az összes olyan ütemezett kérdőívet jeleníti meg, amelyek közvetlenül az alkalmazotthoz vagy a csoporthoz vannak hozzárendelve.

A **vállalati címtárban** az alkalmazottak a szervezeten belüli személyekhez kapcsolódó információkat kereshetnek. A nyilvános kapcsolattartói információk minden alkalmazott számára elérhetők. A vállalat címtára arra a vállalatra van korlátozva, amelybe az alkalmazott be van jelentkezve.

A **Csapatnaptár** a csapata naptárinformációit jeleníti meg. További tájékoztatás: [Csoportos és vállalati naptárak megtekintése](hr-employee-self-service-calendar.md).

### <a name="my-career-information"></a>Saját karrieradatok

Az **Alkalmazotti önkiszolgáló rendszer** **Saját karrieradatok** szakasza a szabadsághoz és a távolléthez, illetve a teljesítménykezeléshez és kompetenciákhoz, juttatásokhoz, feladatokhoz és a mellékletekhez kapcsolódó csempéket jeleníti meg.

A **Szabadságegyenlegek** csempe az összes regisztrált terv egyenlegét jeleníti meg. Ez a csempe a könyvelési módszer alapján előrejelzést készít az egyenlegére. Szabadságkérelmeket lehet megadni és elküldeni, amelyek ezután egy jóváhagyási munkafolyamaton mennek keresztül. A Szabadság és távollét kezelésével kapcsolatos további tudnivalókat lásd: [Szabadság és a távollét áttekintése](hr-leave-and-absence-overview.md).

A **Feladatok** csempe a Önhöz rendelt feladatokat jeleníti meg, és Ön megtekintheti és kezelheti őket.

A **Következő regisztrált tanfolyami** csempe az elkövetkező tanfolyamot jeleníti meg, amelyre Ön regisztrált. Minden nyitott tanfolyamot megtekinthet, és regisztrálhat azokra. Az összes feliratkozáshoz nyitva álló tanfolyam állapota **Elindítva**, és az is megjelenhet, hogy az alkalmazottak számára lehetséges az önálló regisztráció. A szervezet beállításaitól függően előfordulhat, hogy a tanfolyam-regisztráció egy jóváhagyási folyamaton megy keresztül.

A **Tanúsítványok** csempe megjeleníti a tanúsítványt és az aktuális dátumhoz legközelebbi tanúsítványlejárati-dátumot. Lehetőség van tanúsítványok frissítésére, hozzáadására vagy eltávolítására. A szervezet beállításaitól függően előfordulhat, hogy a tanúsítványfrissítések egy jóváhagyási folyamaton mennek keresztül.

A **Következő ütemezett értékelés** csempe az Ön következő teljesítmény-értékelését jeleníti meg. Erről a csempéről új értékelést is lehet indítani. A felettese vagy a személyzeti munkatárs is kezdeményezheti a értékeléseket. A szervezet beállításaitól függően előfordulhat, hogy ezen a csempén kilépő értékeléseket is megtekintheti, frissítheti és elküldhet.

A céljait a **Teljesítménycélok** csempével lehet kezelni. Ez a csempe megjeleníti az egyes állapotokhoz tartozó céljai számát (**Nincs elindítva**, **Rendben van** és **Fejlesztésre szorul**). Az Önhöz rendelt szerepkör-alapú biztonsági beállításoktól függően létrehozhat, frissíthet és el is távolíthat célokat. Ha szeretné, csoportokból vagy sablonokból is hozzáadhat új célokat. A vezetők és a HR az alkalmazottak nevében is létrehozhatnak célokat, és meghatározhatják, hogy milyen részletesek legyenek az egyes célok. A vezetők és az alkalmazottak együttműködhetnek a célokon, valamint módosíthatják a tevékenységeket, mértékeket és az állapotot. Mellékleteket is hozzáadhat.

Az **Összes szakértelem** csempén tekintheti meg a meglévő szakértelmeit. Lehetőség van a szakértelem frissítésére, újak hozzáadására vagy a többé nem relevánsak eltávolítására. A szervezet beállításaitól függően előfordulhat, hogy a szakértelmeinek módosítása egy jóváhagyási folyamaton megy keresztül.

A **Kompenzáció** csempén tekintheti meg az aktuális kompenzációját. Az éves fizetés és az utolsó emelés összegének megtekintéséhez válassza a **Megjelenítés** parancsot. Ha egynél több vállalatnál dolgozik, akkor minden egyes éves összeg megjelenik. A részletes kompenzációs előzmények megtekintéséhez válassza ki az **Éves fizetés** összegét a **Fix és változó kompenzáció előzményei** lap megnyitásához. A jövőbeni kompenzáció nem jelenik meg ezen a lapon. Ha egynél több munkaviszonya van, akkor válthat a lapon belül a vállalatok között, hogy a kompenzációs előzményeket anélkül tekinthesse meg, hogy be kellene jelentkeznie az egyes vállalatokba.

Dokumentumainak megtekintése és kezelése a **Mellékletek** csempével. Minden **Külső** mellékletet kezelhet. A HR és az alkalmazottak egyaránt hozzáadhatnak mellékleteket az **Alkalmazotti önkiszolgáló rendszer** vagy a **Dolgozó** lap használatával. Alapértelmezés szerint a mellékletek beállítása **Külső**.

### <a name="additional-information"></a>További információk

Ez a szakasz az **Alkalmazotti önkiszolgáló rendszer** más területeire mutató hivatkozásokat tartalmaz, hasonlóan a **Saját karrieradatok** szakaszhoz.

A **Juttatások** hivatkozással regisztrálhat a juttatásokra. A juttatások kezelésével kapcsolatos további tudnivalókat lásd a [Juttatások áttekintése témakörben](hr-benefits-management-overview.md).

A **Teljesítmény** területen kiválaszthatja a **Teljesítménynapló** elemet ahol teljesítménnyel kapcsolatos naplóbejegyzéseket hozhat létre, amelyeket a teljesítménycélokhoz és -értékelésekhez is használhat. A **Visszajelzés küldése** lehetőséget választva a szervezeten belüli más alkalmazottaknak is küldhet visszajelzést. A szervezet beállításaitól függően előfordulhat, hogy e-mailek lesznek küldve a címzettnek, a feladónak és a vezetőknek. A szervezeten belül az összes alkalmazottnak lehet visszajelzést küldeni. A visszajelzések küldése nincs vállalatra korlátozva.

A **Kompetenciák** területen módosíthatók a **Tanfolyamok**, **Oktatás**, **Bizalmi beosztások** és **Szakmai tapasztalatok**. A szervezet beállításaitól függően előfordulhat, hogy a kompetenciák frissítései egy jóváhagyási folyamaton mennek keresztül.

A munka részletei a **Szervezetek** területen tekinthetők meg. A munka részletei között szerepel a szakértelem, a tanúsítványok és a felelősségi területek az elsődleges beosztásához. Megtekintheti az Ön által kivett kölcsönzött felszereléseket is. A szervezet beállításaitól függően előfordulhat, hogy a kölcsönzött felszerelések módosítása egy jóváhagyási folyamaton megy keresztül.

A **Kérdőív** területen kitöltött kérdőívek láthatók. Az egész vállalatra kiterjedő kérdőíveket is megtekintheti, amelyek még nem lettek kitöltve. Bármikor úgy dönthet, hogy kitölt egy kérdőívet. A kérdőív szerzője meghatározhatja egy időkeretet, illetve azt, hogy kikre vonatkozik a kérdőív.

A felhasználó által definiált hivatkozásokat az **Emberi erőforrások paraméterei** területen lehet beállítani. Megadhatja például a kifizetési kimutatásokra, az év végi dokumentációra vagy a külső megoldásokra mutató hivatkozásokat. Ezek a hivatkozások ennek a szakasznak az alján jelennek meg, de a személyre szabással ezeket át lehet helyezni.

A Power Apps beágyazásával az **Alkalmazott önkiszolgáló rendszer** munkaterületén további lapokat is létre lehet hozni. Használja a **Beállítások** menüt a lap személyre szabásához bármely Power Apps alkalmazással. A **Beállítások** menüben hozzáadhat egy Power Apps alkalmazást, megadhatja a részleteket, majd beszúrhatja az alkalmazást. Alapértelmezés szerint a Power Apps sorozat első lapjaként jelenik meg. A sorrendet a szabványos személyre szabással lehet módosítani.

## <a name="my-team"></a>Saját csapat

A **Saját csapat** lap a **Vezetői önkiszolgáló rendszer** következő adatait jeleníti meg. Csak a vezetők férhetnek hozzá a **Saját csapat** laphoz.

### <a name="personnel-actions"></a>Személyzeti műveletek

Személyzeti műveletek megjelenítése a konfigurációs beállítások szerint az **Emberi erőforrások megosztott paraméterei** és az **Emberi erőforrások paraméterei** területeken. Ha engedélyezve van a **Dolgozókhoz** a személyzet műveletek új menüket tesznek elérhetővé, többek között:

- **Új alkalmazott kérése**
- **Új alvállalkozó kérése**
- **Dolgozói újbóli hozzárendelésének kérése**
- **Munkaviszony megszüntetésének kérése**
- **Kompenzációs módosítás kérése**

Ezeket a beállításokat konfigurálhatja úgy, hogy egy opcionális ellenőrzési és jóváhagyási munkafolyamaton menjenek át.

A **Beosztásműveletek** engedélyezésével a következő lehetőségek választhatók:

- **Új beosztás kérése**
- **Beosztásrészletek módosításának kérése**

Ezeket a beállításokat úgy is konfigurálhatja, hogy egy opcionális ellenőrzési és jóváhagyási munkafolyamaton menjenek át.

### <a name="summary"></a>Összegzés

Az **Összegzés** szakasz adatai attól függenek, hogy a Személyzeti osztály mit választott ki az **Emberierőforrás-paraméterek** alatt. A **Vezetői önkiszolgáló rendszer** lapon az **Emberierőforrás-paraméterek** alatt megadhatja a lejáró rekordok és a nyitott beosztások megjelenítésének beállításait. A lehetőségek engedélyezése határozza meg, hogy a vezetők mit láthatnak az **Összegzés** szakaszban.

A következő csempéket lehet beállítani a vezetőknek:

- **Csapatom lejáró tanúsítványai**
- **A csapatom lejáró azonosítószámai**
- **A csapatom lejáró próbaidői**
- **A csapatom lejáró szűrései**
- **A csapatom lejáró tesztjei**
- **Nyitott pozíciók a közvetlen és/vagy a közvetett beosztottak számára**
- **A saját csapathoz tartozó szabadságkérelmek**
- **Csapat szakértelmeinek értékelése**
- **Szakértelembeli hiány elemzése**
- **Csapat teljesítménynaplók**
- **Csapat teljesítménycéljai**
- **Csapatteljesítmény-ellenőrzések**
- **Kilépő dolgozók**

A következő beállítások konfigurálhatók a vezetőknek, hogy módosításokat végezhessenek vagy szabadságkérelmeket adhassanak hozzá a közvetlen beosztottjaik nevében:

- Diplomák
- Tanfolyamok
- Kölcsöncikkek
- Szakértelem
- Szabadság- és távolléti kérelmek

### <a name="my-team-information"></a>Saját csapat adatai

A **Saját csapat** adatai lehetővé teszik a vezetőknek a közvetlen és kibővített jelentések megtekintését és frissítését. A közvetett beosztottak eléréséhez válasszon ki egy közvetlen beosztottakkal rendelkező alkalmazottat majd válassza a **Csapat megtekintése** lehetőséget a csempén. Ugyanazok a beállítások vonatkoznak a közvetett beosztottakra, mint a közvetlen beosztottakra. 

#### <a name="summary-tab"></a>Összegzés lap

Az **Összegzás** lap rövid áttekintést nyújt a közvetlen beosztottakról. Ha egy közvetlen beosztotthoz további beosztott dolgozók tartoznak, akkor a kártya a felső részén látható a közvetlen beosztottak száma jeleníti meg, valamint a **Csapat megtekintése** gomb. Az egyes csempék fölötti beállítások vonatkoznak a kiválasztott alkalmazottra. Ha például egy alkalmazott nevében szeretne benyújtani egy szabadságkérelmet válassza ki az alkalmazottat, majd válassza ki a **Szabadságkérelem** lehetőséget. 

Ha kiválasztja a **Részletek** gombot egy alkalmazott kiválasztása után, a következő lehetőségek jelennek meg:

- **Diplomák**
- **Kompenzáció**
- **Tanfolyamok**
- **Ellenőrzések**
- **Szabadságolás**
- **Kölcsönzött cikkek**
- **Teljesítménycélok**
- **Regisztrált tanfolyamok**
- **Szakértelem**
- **Visszajelzés küldése**

A szervezet beállításaitól függően módosíthat vagy csak megtekinthet.

#### <a name="position-tab"></a>Beosztás lap

A **Beosztás** lap egy összesítő nézetet jelenít meg az alkalmazottaknak az elsődleges beosztásukban. A név, a csempe és az osztály az egyes csempék fejlécterületén jelenik meg. Ez a csempe a következőket tartalmazza:

- **Szolgálati idő dátuma** – A **Dolgozó** lap dolgozói összesítő szakasza alapján jelenik meg.
- **Szolgálati évek** – Az alkalmazott munkaviszonyának kezdő dátuma alapján számítva.
- **Előző beosztások száma** – A beosztási előzmények alapján a szám kiválasztása megnyitja a korábban betöltött beosztások részletes nézetét.
- **Születési dátum** – Az alkalmazott születési dátumának hónapja és napja.

A beosztások adatait a közvetlen és a közvetett beosztottakhoz is megtekintheti.

#### <a name="compensation-tab"></a>Kompenzáció lap

A **Kompenzáció** lap az alkalmazott éves fizetését jeleníti meg. A vállalat azonosítója a fizetés összege alatt jelenik meg. Ha egy alkalmazottnak egynél több munkaviszonya van és több jogi személytől is kap fizetést, akkor az alkalmazottnak több kompenzációs terve lesz. A vállalatváltás nélküli, jogi személyeken átívelő kompenzációs tervek megjelenítéséhez engedélyeznie kell a vállalatközi kompenzációt az **Emberi erőforrások > Közös paraméterek > Speciális hozzáférés > Vállalatközi kompenzáció engedélyezése** lehetőségnél.

A kompenzációs előzmények megtekintéséhez válassza ki a **Fizetési összeget** a **Részletek** lap megnyitásához. Csak a jelenlegi és előzmény fix és változó kompenzációs rekordok jelennek meg a **Kompenzáció** lapon. Ha egy alkalmazott egynél több helyen foglalkoztatott, válthat a vállalatok között, és megtekintheti az egyes vállalatok kompenzációs előzményeit, illetve engedélyezheti a vállalatközi kompencáziót az **Emberi erőforrások közös paraméterei** oldalán az összes kompenzációs terv megtekintéséért.

A kompenzáció adatait a közvetlen és a közvetett beosztottakhoz is megtekintheti.

#### <a name="leave-and-absence-tab"></a>Szabadság és távollét lap

A **Szabadság és távollét** lap a tevékenységgel rendelkező alkalmazottak legnagyobb egyenlegét jeleníti meg. A műveletek végrehajtásához vagy a tevékenységek teljes listájának megtekintéséhez válassza ki a **Részletek** lehetőséget, majd válassza ki a **Távollét** lehetőséget. A **Szabadság** lapon megtekintheti az egyenlegeket, a kérelmeket, a jóváhagyott szabadságokat és az előrejelzési egyenlegeket, hogy az alkalmazottaknak megkönnyíthesse a szabadság kezelését. A szervezet beállításaitól függően lehetőség van arra is, hogy szabadságot kérelmezzen közvetlen és közvetett beosztottjai számára.

#### <a name="performance-goals-tab"></a>Teljesítménycélok lap

A **Teljesítménycélok** lap állapot szerint összesíti a teljesítménycélokat. Jelöljön ki egy számot az állapothoz, vagy válassza ki a teljesítmény célokat a **Részletek** elemből, hogy megtekinthesse az összes célt egy alkalmazotthoz. A vezetők és az alkalmazottak igény szerint módosíthatják a célokat a cél időtartama alatt.

A vezetők a csapatuk összes célját láthatják a **Csapat teljesítménycéljai** csempén a **Saját csapat** rész **Összegzés** szakaszában.

#### <a name="reviews-tab"></a>Értékelések lap

Az **Értékelések** lap összegzi azokat az értékeléseket, amelyekkel az alkalmazott rendelkezik az egyes fázisokban: **Folyamatban**, **Értékelésre kész** és **Végső értékelés**. Az alkalmazotti értékelésének eléréséhez válassza a **Részletek** gombot, majd válassza ki az értékeléseket, amelyeken együtt szeretne működni. Attól függően, hogy egy értékelés hol tart a munkafolyamat folyamtában van, megtekintheti, hogy az ellenőrzés elérhető-e frissítésre. 

A csapata értékeléseit a **Csapat teljesítményértékelései** csempén a **Saját csapat** rész **Összegzés** szakaszában tekintheti meg.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
