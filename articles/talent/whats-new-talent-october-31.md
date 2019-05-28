---
title: Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. október 31.)
description: Ez a témakör a Microsoft Dynamics 365 for Talent Core HR új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 10/31/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d6942f8e4dc86f18a081b347df0567b1358a87ab
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518206"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-31-2018"></a>Új vagy módosult elemek a Dynamics 365 for Talent Core HR szolgáltatásban (2018. október 31.)

[!include [banner](includes/banner.md)]

**Build 8.1.2031**

Ez a témakör a Core HR aktuális verziójában található új vagy módosított szolgáltatásokat írja le.

## <a name="create-links-from-talent-to-finance-and-operations"></a>Hivatkozások létrehozása a Talent és a Finance and Operations között
Ez az új navigációs funkciók lehetővé teszi hivatkozások létrehozását a Talent és a Finance and Operations között, így közvetlen navigációt biztosít a Finance and Operations oldalakhoz. Hivatkozások beállításakor megadhatja a nevét és csoportját a hivatkozának, azt ,hogy hol jelenjen meg a hivatkozás a Talentben illetve a megnyitandó céloldalt a Finance and Operationsben.

#### <a name="coming-soon"></a>Hamarosan
A jövőben mezőkörnyezet is hozzáadásra kerül, amely lehetővé teszi a közvetlen navigációt a kapcsolódó rekordokhoz a Finance and Operations alkalmazásban. Használhatja például a **Hivatkozás mezőhöz** lehetőséget, hogy környezetet adjon a navigáláshoz egy adott munkavállalóhoz vagy pozícióhoz a Finance and Operationsben.

### <a name="configure-target-systems"></a>Célrendszerek konfigurálása

A rendszergazdák a Talentben definiálhatnak linkeket, amelyek a Rendszeradminisztráció munkaterületen keresztül jelennek meg. A konfiguráció része a Finance and Operations környezetekben, hogy szeretne elérni a hivatkozás „céljához”. Ehhez nevet ad a célrendszernek és megadja a Finance and Operations környezet URL-címét. Itt talál egy példát a Finance and Operations URL-címre, amelyet megadna : https://devax00124aos.cloud.test.dynamics.com/. Miután beállította a célrendszereket megadhatja a hivatkozásokat.

### <a name="configure-links"></a>Hivatkozások konfigurálása

A létrehozott hivatkozásokhoz a következő adatok lesznek meghatározva.

- Hivatkozás - A hivatkozás neve, csak azonosításra használt név.

- Adott hivatkozás engedélyezése - állítsa **Igen** értékre, ha meg szeretné jeleníteni a hivatkozást Talent felhasználói számára.

- Megjelenített név – Meghatározza a nevet, amellyel megjelenik a hivatkozás a Finance and Operations alkalmazásban. Ez az adatot jelenleg nincs lefordítva.

- Felületi hivatkozás a képernyőre – Válassza ki, melyik lapon szeretné, hogy a hivatkozás megjelenjen.

- Csoport - A csoportok alkalmazása nem kötelező, de ha szeretné rendezni a hivatkozások csoportokkal, válasszon egy meglévő csoport vagy hozzon létre egy új újat a **Csoport** mező használatával.

- Célrendszer – Válassza ki a célrendszerbe, amely létrejön a **Célrendszer konfigurálása** lehetőséggel. Ez lesz a Finance and Operations környezet ami használva lesz a hivatkozással történő navigáció során.

- Felhasználó jelenlegi vállalatának alkalmazása – válassza sz **Igen** lehetőséget, ha a felhasználó jelenlegi vállalati környezetét szeretné használni a navigációhoz a Finance and Operationsbe. Ha a **Nem** van kiválasztva, kiválaszthatja a használandó vállalatot.

- Célmenüelem - Adja meg a menüelemet a Finance and Operation alkalmazásból, amelyet a hivatkozás használ a navigáláshoz.. Elérhetők menüelemek, amelyekhez közvetlenül el lehet navigálni. A szükséges menüelem megkereséséhez nyissa meg a Finance and Operations alkalmazást, és nyissa meg a lapot, amelyek navigáció célja. Másolja ki a menüelemet az URL-ből. Például, ha azt szeretné, hogy a hivatkozásra kattintva az alkalmazottak listájához jusson a Finance and Operations alkalmazásban azt az értéket adja meg, amely a „&mi” után jelenik meg az URL-ben. https://devax00124aos.cloud.test.dynamics.com/?p=USMF&mi=HcmWorkerListPage_Employees. A menüelemet az alkalmazottak listáját tartalmazó oldal eléréshez ebben a példában: HcmWorkerListPage_Employees.

- Hivatkozás adatforráshoz – Válassza ki az adatforrást, amelyre a hivatkozás hivatkozik. A leggyakoribb adatforrások, mint a **Dolgozó** és a **Beosztás** érhetők el.

- Hivatkozás mezőhöz – (hamarosan) Ez a mezőválasztás lehetővé teszi a navigációt egyetlen rekordtól a Talentben egyetlen rekordhoz a Finance and Operationsben.

### <a name="access-to-links"></a>Hivatkozások elérése

A rendszergazdák az újonnan létrehozott hivatkozásokat látni fogják a meghatározott lapokon még akkor is, ha az **Adott hivatkozás engedélyezése** beállítás értéke **Nem**. Ez a hivatkozások ellenőrzésére használható, mielőtt azok meg lennének jelenítve az alkalmazottaknak. Minden más szerepkörnek csak akkor jelennek meg a beállított hivatkozások, ha az **Adott hivatkozás engedélyezése** beállítás értéke **Igen**. Azon munkavállalók, akik hozzáférnek az oldalakhoz, amelyeken a hivatkozások megjelennek elérhetik a hivatkozásokat.

Felhasználók meghatározott biztonsági jogokkal is rendelkezhetnek a Finance and Operations alkalmazásban, hogy elérjék a Finance and Operations lapjait. Ha nem rendelkeznek ilyennel, egy biztonsági párbeszédpanel jelenik meg a hivatkozás használata esetén.


## <a name="other-changesfixes"></a>Egyéb változtatások/javítások

### <a name="positions-with-a-future-start-date-cannot-be-assigned-to-a-new-employee"></a>A jövőbeli kezdési dátummal rendelkező beosztások nem rendelhetők hozzá egy új alkalmazotthoz

Változások történtek, hogy az alkalmazotti hozzárendelések engedélyezve legyenek jövőbe eső dátumú beosztásokhoz is. A pozíciók amelyeknél a kezdési dátum a jövőben van és az alkalmazotti hozzárendelések a munkafolyamat mentése vagy befejezése során lesznek érvényesítve (ha a munkafolyamat engedélyezve van).

### <a name="new-employee-cannot-be-assigned-existing-position"></a>Új alkalmazott nem rendelhető hozzá egy meglévő beosztáshoz

Módosítások történtek, így az új alkalmazott hozzárendelések most hozzárendelhetők meglévő beosztásokhoz.

### <a name="seniority-dateoffice-location-disappears-when-the-employment-start-date-is-in-the-past-and-the-record-is-saved"></a>A Szolgálati idő dátuma/Iroda helye eltűnik, ha a foglalkoztatás kezdő dátuma a múltban van, és a bejegyzés mentésre kerül.

Módosítások történtek a **Szolgálati idő dátuma** és az **Iroda helye** megfelelő láthatósága érdekében a korábbi alkalmazottak módosításainak mentése során.

### <a name="cant-enter-data-for-future-dated-employments-on-the-worker-page"></a>Nem lehet megadni adatokat a jövőbe eső dátumú munkaviszonyhoz a dolgozó lapon

Foglalkoztatási adatok a jövőbe eső dátumú munkaviszonyokhoz le lett tiltva a fő dolgozó lapon. Foglalkoztatási adatokat a **Dátumkezelő** lapjain lehet megadni. További módosítások történnek a jövőbeli kiadásokban, hogy a foglalkoztatási adatokat közvetlenül a munkafolyamat folyamatánál lehessen megadni.

### <a name="add-validfrom-and-validto-to-hcmpersonalcontactpersonentity"></a>ValidFrom és ValidTo hozzáadása a HcmPersonalContactPersonEntity entitáshoz

Az adatkezelési rendszer (DMF) entitás HcmPersonalContactPersonEntity frissítve lett, hogy tartalmazza az „érvényesség kezdete” és „érvényesség vége” dátumokat bizonyos juttatásintegrációk biztosításához. 

## <a name="known-issue"></a>Ismert probléma
- **Probléma**:Egy új csatolmány hozzáadásakor egy dolgozóhoz az **Új** és **Szerkesztés** gombok szürkén jelennek meg. 
- **Megoldás:** A melléklet lap megnyitása, előtt ellenőrizze, hogy az adatterületek a **Dolgozó** lapon le vannak-e zárva. Ha a ténymezők be vannak zárva, amikor a **Dolgozó** lap be van töltve, akkor a mellékletek gombjai engedélyezettek. (Ezt a problémát kijavítjuk a következő platformfrissítéssel.)
