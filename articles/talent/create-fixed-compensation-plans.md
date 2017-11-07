---
title: "Fix kompenzációs konstrukciók létrehozása"
description: "A fix kompenzáció egy alkalmazott rendszeres bruttó bérét jelenti. A cikk ismerteti az összetevőket, amelyeket be kell állítani, mielőtt létrehozna egy fix kompenzációs tervet és bejegyezné az alkalmazottakat."
author: kherr75
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HRCCompGrid, HRCCompRefPointSetup, HRMCompEligibility, HRMCompEvent, HRMFixedCompPlanTable
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 15991
ms.assetid: ef8cf992-176c-4c98-9dff-6510e1eb9f1c
ms.search.region: Global
ms.author: kherr75
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 399e1fee592c0ab31015e37e87d41c71f9282858
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="create-fixed-compensation-plans"></a>Fix kompenzációs konstrukciók létrehozása

[!include[banner](includes/banner.md)]


A fix kompenzáció egy alkalmazott rendszeres bruttó bérét jelenti. A témakör ismerteti az összetevőket, amelyeket be kell állítani, mielőtt létrehozna egy fix kompenzációs tervet és bejegyezné az alkalmazottakat.

A fix kompenzációs összegek az alkalmazottak számára számíthatók ki, a teljesítmény, a régió és az előirányzott fizetésemelések alapján. A Microsoft Talent támogatja a lépés, az osztály és a sáv szerinti kompenzációtípust.

## <a name="fixed-compensation-components"></a>Fix kompenzációs összetevők
### <a name="compensation-levels"></a>Kompenzációs szintek

**Kompenzációs szintek** megadásával különböző munkákhoz állíthat be kompenzációt, így biztosítva azt, hogy azon alkalmazottak, akik ezeket a feladatokat elvégzik, megfelelően meg legyenek fizetve. A **Kompenzációs szintek** lapon be lehet állítani a lépéses, osztályos és sávos tervekhez tartozó kompenzációs szinteket. Használja a **Fel** és **Le** gombokat a szinteknek a típusok szerint megfelelő sorrendbe helyezéséhez. Egy adott munkához tartozó kompenzációs szintek beállításával biztosítható, hogy az adott munkához kapcsolódó pozíciókat viselő alkalmazottak ugyanazt a fizetséget kapják.

### <a name="reference-points"></a>Hivatkozási pontok

A **Hivatkozási pontok** a rács azon oszlopai, amelyek meghatározzák az egyes szintekhez tartozó kompenzációs tartományokat. A kompenzációs szintet a sorok jelképezik a rácsban. Az osztályzatok típusához tartozó tervek esetében a minimum, a közép és a maximum a tipikus hivatkozási pontok. A hivatkozási pontokat a **Hivatkozási pontok beállítása** oldalon lehet létrehozni.

### <a name="compensation-grids"></a>Kompenzációs rácsok

Miután beállította a szinteket és a hivatkozási pontokat, ezek kombinálásával egy **kompenzációs rácsot** hozhat létre. A **Kompenzációs rácsok** oldalon adja meg a ráccsal kapcsolatos információkat. Például adja meg, hogy a rácsot mire kívánja használni, milyen típusú konstrukcióval lesz alkalmazva, és hogy a rácsban milyen hivatkozási pontokra vagy oszlopokra van szükség. Miután befejezte az információk megadását, kattintson a **Kompenzációs struktúra** lehetőségre, hogy szinteket és összegeket adhasson hozzá a rácshoz. 

**Tipp:** Használja a **Tömeges módosítások** funkciót a kompenzációs struktúra kezdeti összegeinek megadásához, majd százalékos vagy összeg szerinti növekményekkel módosítsa az értékeket szintek és hivatkozási pontok szerint.

### <a name="pay-frequencies"></a>Fizetési gyakoriságok

A **fizetési gyakoriságok** segítségével megadható, hogy egy alkalmazott fizetés vagy bére milyen módon legyen definiálva (például 10$ óránként vagy 50 000$ évente), illetve megadható az óra-, a heti-, a havi- (12 hónapra) és az éves bér közötti konverzió. Például egy vállalat, amely az órabéres dolgozók esetében 38 órás munkahetet alkalmaz, a következő értékeket adja meg fizetési gyakoriságként: órabér – 1; hetibér – 38; havibér – 164,6666666667; éves bér – 1,976. Ezek az átalakítások az alkalmazott fix kompenzációs rekordján megjelenő, különböző fizetési ráták kiszámolásához szükségesek.

## <a name="fixed-compensation-plans"></a>Rögzített kompenzációs konstrukciók
A konfigurált összetevők kombinációjához megtervezhet egy fix kompenzációs tervet. Egy fix kompenzációs konstrukció létrehozásához nyissa meg a **Fix kompenzációs konstrukciók** képernyőt. Itt megadhatja a konstrukció nevét és leírását, kiválaszthatja a konstrukció típusát (lépéses, osztályos vagy sávos), kiválaszthatja az alkalmazott fizetési díjalapjához tartozó fizetési gyakoriságot (órai bér, éves bér stb.), továbbá beállíthat néhány olyan opciót, amelyek a kompenzáció feldolgozását szabályozzák. 

A **Tartományon kívüliség tűréshatára** beállítás segítségével megadhatja, hogy milyen szigorúan kívánja ellenőrizni, hogy a kompenzációs összegek a minimum és a maximum összeg közé esnek-e. A **Kemény** tűréshatár megköveteli, hogy kompenzáció az adott szinthez meghatározott tartományon belül legyen. A **Puha** tűréshatár figyelmeztetést küld, ha a kompenzációs összeg kívül esik a tartományon, de ennek ellenére lehetővé teszi a folytatást. Ha a tűréshatárhoz a **Nincs** opciót választja, anélkül beírhat bármilyen kompenzációs összeget egy alkalmazotthoz, hogy figyelmeztetést vagy hibaüzenetet kapna. 

A **Felvételi szabály** beállításai segítségével megadhatja, hogy minden alkalmazott ugyanazt a fizetésemelést kapja-e, függetlenül felvételük dátumától (**Felvételi szabály** = **Nincs**), vagy az alkalmazottak a jutalom bizonyos százalékát kapják, alkalmazásuk időtartamának függvényében (**Felvételi szabály** = **Százalék**). 

A **Tartomány-kihasználtsági mátrix** akkor hasznos, ha azt szeretné, hogy csökkenjen az időtartam, amely ahhoz szükséges, hogy az alkalmazottak elérjék a tartományuk középpontját, vagy ha növelni szeretné azon időtartamot, amely ahhoz szükséges, hogy az alkalmazottak elérjék a tartományuk maximális hivatkozási pontját. Például azon alkalmazottaknak, akik tartományuk alsó 25%-ában vannak, 110%-os célprémiumot szeretne adni, de azon alkalmazottaknak, akik a tartományuk felső 80%-ban járnak, csak 80%-os célprémiumot kíván adni, így megelőzve azt, hogy a maximális szintet hamar elérjék. 

A fix kompenzációs konstrukció alapjainak meghatározása után beállíthatja a kompenzációs struktúrát a konstrukcióhoz. Kattintson a **Kompenzáció beállítása** lehetőségre. Megnyílik egy párbeszédpaneles csúszka, amely segítségével három lehetőség közül választhat:

-   Új kompenzációs rács létrehozása egy hivatkozásipont-beállítás kijelölésével, és egy rácsnév megadása.
-   Új kompenzációs rács létrehozása egy meglévő, kiindulási pontként is használható rács másolatának létrehozásával.
-   Egy meglévő, korábban már definiált kompenzációs rács használata. Minden kompenzációs konstrukció, amely ugyanazt a rácsot alkalmazza, frissítéseket kap, ha módosul a rács.

Egy lehetőség kiválasztása után megnyílik a **Kompenzációs struktúra** lap, ahol módosíthatja az új vagy a meglévő kompenzációs rácsot.

## <a name="fixed-compensation-enrollment"></a>Fix kompenzációs beléptetés
### <a name="determine-who-is-eligible-for-the-plan"></a>A konstrukcióra jogosultak meghatározása

Ha készen áll az alkalmazottak beléptetésére egy fix kompenzációs tervbe, akkor elsőként meg kell határozni, hogy ki jogosult a tervben meghatározott kompenzációra. A tervet nem lehet hozzárendelni egyetlen alkalmazotthoz sem, amíg nincs meghatározva a jogosultság. A jogosultság beállításához nyissa meg a **Jogosultsági szabályok** oldalt. Itt létrehozhat egy új jogosultsági szabályt a kompenzációs tervhez, és megadhatja a szükséges kritériumokat, amelyek alapján az alkalmazott jogosult a kompenzációs tervre. Korlátozhatja a jogosultságot részleg, szakszervezet, kompenzációs régió (hely), munka, beosztás funkciója, munka típusa vagy kompenzációs szint szerint. Az alkalmazottak csak akkor léptethetők be a kompenzációs tervbe, ha megfelelnek az összes jogosultsági szabályban meghatározott követelménynek. 

**Megjegyzés:** A jogosultsági szabályok meghatározzák a fix és a változó kompenzációs tervhez való jogosultságot. 

A jogosultsági szabályok bizonyos mezőket használnak a Munka, Beosztás és Alkalmazotti rekordokból, hogy meghatározható legyen egy alkalmazott jogosult-e a kompenzációs tervre.

-   A **Munka** lapon az alkalmazhatósági szabály a következő mezőket veszi figyelembe:
    -   A **Munka** mező
    -   A **Munka osztályozás** lapon a **Funkció** és a **Munkatípus** mezőket
    -   A **Szint** mezőt a **Kompenzáció** lapon
-   A **Beosztások** oldalon az alkalmazhatósági szabály a **Részleg** és a **Kompenzációs régió** mezőket veszi figyelembe.

Az alkalmazhatósági szabály figyelembe veszi az alkalmazotthoz rendelt szakszervezeteket is (az **Alkalmazottak** oldalon, a **Dolgozó** lapon kattintson a **Személyes adatok** &gt; **Szakszervezetek** lehetőségre).

### <a name="define-fixed-compensation-actions"></a>Fix kompenzációs műveletek meghatározása

A **Fix kompenzációs műveletek** egy alkalmazott fix kompenzációjának beállítására vagy módosítására használhatók. A fix kompenzációs műveletek lehetővé teszik, hogy a Kompenzáció- és juttatáskezelő által elvégezhető műveletekhez egy jól felismerhető nevet adhasson meg. A különböző művelettípusok mögött speciális logika van, így azok egy adott időpontban használhatók. 

Például ha egy alkalmazotthoz fix kompenzációt állít be, csak **Felvételi/Újrafelvétel** típusú műveletek alkalmazhatók. Ebben az esetben érdemes három különböző műveletet létrehozni a **Felvétel/Újrafelvétel** típushoz, **Felvétel**, **Újrafelvétel**, és **Átvétel** néven. Ezt követően részletesebben is leírhatja, hogy az alkalmazotthoz tartozó fix kompenzáció miért lett hozzáadva vagy módosítva.

### <a name="enroll-the-employee"></a>Alkalmazott beléptetése

Az alkalmazott most már hozzárendelhető egy fix kompenzációs konstrukcióhoz. Nyissa meg az **Alkalmazottak** oldalt, majd válassza ki a kompenzációs konstrukcióhoz hozzáadandó alkalmazottat. A műveleti ablakon kattintson a **Kompenzáció** &gt; **Fix konstrukció** lehetőségre. Most létrehozhat egy fix kompenzációs műveletet ehhez az alkalmazotthoz. 

**Megjegyzés:** A kompenzációs konstrukció mező csak azokat a terveket tartalmazza, amelyre az alkalmazott jogosult az egyes tervekhez beállított alkalmazhatósági szabályok alapján. Ha egy tervhez nincs alkalmazhatósági szabály beállítva,egyetlen alkalmazott sem lesz jogosult az adott tervre. 

A rendszer ellenőrzi, hogy az osztály vagy sáv típusú kompenzációs tervhez megadott kompenzációs összeg a minimális és maximális hivatkozási pont között van az alkalmazott munkájához megadott kompenzációs szint alapján. Amennyiben a kompenzációs összeg a megengedett határokon kívül esik, egy figyelmeztetés vagy egy hibaüzenet jelenik meg a fix kompenzációs konstrukcióhoz megadott tűréshatár függvényében.

<a name="see-also"></a>Lásd még
--------

[Kompenzációs konstrukciók](compensation-plans.md)




