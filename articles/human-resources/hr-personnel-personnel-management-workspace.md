---
title: Személyzetkezelési munkaterület
description: Ez a témakör a Személyzetkezelési munkaterület fogalmi elemeit ismerteti.
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPersonnelManagementWorkspace
audience: Application User
ms.author: twheeloc
ms.reviewer: twheeloc
ms.search.scope: Human Resources
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 4332be972ab3dc81e7e4f3cc297a91cd247e721e
ms.sourcegitcommit: 7e0e2a266d9a9473df72e207554d9bd150e17ce3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/05/2021
ms.locfileid: "7771338"
---
# <a name="personnel-management-workspace"></a>Személyzetkezelési munkaterület

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

A **Személyzetkezelési** munkaterületen nagy mennyiségű tartalom található. Tartalmazza a személyzeti mozgásokat, nyomon követi az alkalmazottak módosításait, a nyitott pozíciókat, a címváltozásokat, a lejáró rekordokat és az analitikát, valamint hivatkozásokat tartalmaz az adott információkra. Ez a témakör részletes információkat tartalmaz a munkaterületével minden egyes részéről.

## <a name="activity-tab"></a>Tevékenység lap

A **Tevékenység** lap olyan szakaszokat tartalmaz, amelyek az alapján csoportosítják a dolgozókat, hogy hol tartanak az alkalmazás folyamatában:

- **Felveendő jelentkezők**
- **Hamarosan indul**
- **Legutóbbi felvételek**
- **Kilépés**
- **Kilépett**

Amikor egy dolgozó az alkalmazási folyamat e fázisainak valamelyikében van, adott műveletek érhetők el gombként a kártyán, illetve a jobb felső sarokban látható hárompontos (**...**) ikon kiválasztásakor megjelenő menüben. Az alábbi alszakaszok a **Tevékenység** lap szakaszait írják le, és felsorolják az elérhető műveleteket.

### <a name="candidates-to-hire"></a>Felveendő jelentkezők

A munkaterület **Felveendő jelentkezők** szakaszát több forrásból tölti ki a rendszer:

- Egy Open Data Protocol (OData) entitás
- LinkedIn-integráció
- A termékben manuálisan megadott adatok

Amikor a **Felveendő jelentkezők** szakaszban megjelennek a jelentkezők, a következő műveleteket végezheti el a kártyáján a hárompontos ikont kiválasztva:

- **Jelölt elutasítása**
- **Nem felveendő**
- **Felvétel**

> [!NOTE]
> Ha a lista feltöltése a Microsoft Dataverse rendszeréből történik, akkor ugyanazok a ek jelennek meg az összes jogi személynél, mivel a höz nincs jogi személy társítva.

### <a name="starting-soon"></a>Hamarosan indul

A **Hamarosan indul** szakaszban olyan dolgozók jelennek meg, akik a jövőben fognak kezdeni. A lista a kezdés dátuma szerint van rendezve. A mai naphoz legközelebb eső kezdő dátum jelenik meg a listában elsőként.

Ha a vezető nem jelenik meg a kártyán, nincs beosztás rendelve a dolgozóhoz.

> [!NOTE] 
> Javasoljuk, hogy feladatlista alkalmazása előtt rendeljen beosztást egy dolgozóhoz. Előfordul, hogy a felvett alkalmazottak vezetőihez a berakodó feladatok vannak hozzárendelve. Ha azonban nincs beosztás hozzárendelve, akkor nem lehet meghatározni az új alkalmazott felettesét. Ebben az esetben a vezetőnek szánt előkészítési feladatokat az ellenőrzőlista tulajdonosához rendeli hozzá a rendszer.

Amikor a dolgozók megjelennek a **Hamarosan indul** szakaszban, a következő műveletek érhetők el hozzájuk:

- Beosztás hozzárendelése
- Foglalkoztatás ellenőrzése
- Fix kompenzáció hozzárendelése
- Változó kompenzáció hozzárendelése
- Megtekintés a hierarchiában
- Ellenőrzőlista alkalmazása\*\*

\*\* Ez az alapértelmezett művelet. Gombként jelenik meg a kártyán.

### <a name="recent-hires"></a>Legutóbbi felvételek

A **Legutóbbi felvételek** szakasz sorolja fel azokat a dolgozókat, akiknek a kezdési dátuma a múltban van. A lista a kezdés dátuma szerint van rendezve. A mai naphoz legközelebb eső kezdő dátum jelenik meg a listában elsőként.

A lista alapértelmezés szerint az elmúlt hét napban felvett dolgozókat jeleníti meg. A beállítás módosításához az **Emberi erőforrások paraméterei** oldal **Általános** lapján adja meg a **Legutóbbi felvételek** időkeretét. A **Legutóbbi felvételek** szakaszban az adatok megadott számú napra, hónapra vagy évre vonatkozóan jeleníthetők meg. Például az elmúlt 14 napban felvett dolgozók listájának megtekintéséhez állítsa az **Időszak** mezőt **14** értékre, az **Egység** mezőben pedig adja meg a **Napok** értéket.

> [!NOTE]
> Az **Emberi erőforrások paraméterei** oldalon szereplő beállítások vállalatspecifikusak. Emiatt a megtekinthető közelmúltbeli felvételek időkerete vállalatonként eltérő lehet. Az USMF vállalatnál például szeretné az elmúlt hét nap minden új felvételét megtekinteni. Az USSI vállalatnál azonban érdemes lehet megtekinteni az összes, az elmúlt 14 napból származó új felvételeket. Ebben az esetben minden vállalatban nyissa meg az Emberi erőforrások paraméterei lapot, és állítsa be **·** a szükséges paramétereket.

Ha a vezető nem jelenik meg a kártyán, nincs beosztás rendelve a dolgozóhoz.

Amikor a dolgozók megjelennek a **Legutóbbi felvételek** szakaszban, a következő műveletek érhetők el számukra:

- Beosztás hozzárendelése
- Foglalkoztatás ellenőrzése
- Fix kompenzáció
- Változó kompenzáció hozzárendelése
- Megtekintés a hierarchiában
- Ellenőrzőlista alkalmazása\*\*

\*\* Ez az alapértelmezett művelet. Gombként jelenik meg a kártyán.

### <a name="exiting"></a>Kilépés

A **Kilépés** szakaszban olyan dolgozók jelennek meg, akiknek a kilépési dátuma a jövőben van. A lista a kilépés dátuma szerint van rendezve. A mai naphoz legközelebb eső kilépési dátum jelenik meg a listában elsőként. 

Alapértelmezés szerint a lista azokat a dolgozókat jeleníti meg, akiknek a következő hét napban van a kilépési dátuma. A beállítás módosításához az **Emberi erőforrások paraméterei** oldal **Általános** lapján adja meg a **Kilépő dolgozók megtekintése** időkeretét. A **Kilépés** szakaszban az adatok megadott számú napra, hónapra vagy évre vonatkozóan jeleníthetők meg. Például az következő 14 napban kilépő dolgozók listájának megtekintéséhez állítsa az **Időszak** mezőt **14** értékre, az **Egység** mezőben pedig adja meg a **Napok** értéket.

Amikor a dolgozók megjelennek a **Kilépés** szakaszban, a következő műveletek érhetők el hozzájuk:

- Ellenőrzőlista alkalmazása\*\*
- Foglalkoztatás ellenőrzése
- Megtekintés a hierarchiában

\*\* Ez az alapértelmezett művelet. Gombként jelenik meg a kártyán.

### <a name="exited"></a>Kilépett

A **Kilépett** szakasz sorolja fel azokat a dolgozókat, akiknek a kilépési dátuma a múltban van. A lista a kilépés dátuma szerint van rendezve. A mai naphoz legközelebb eső kilépési dátum jelenik meg a listában elsőként.

Alapértelmezés szerint a lista azokat a dolgozókat jeleníti meg, akiknek az elmúlt hét napban volt a kilépési dátuma. A beállítás módosításához az **Emberi erőforrások paraméterei** oldal **Általános** lapján adja meg a **Kilépett dolgozók megtekintése** időkeretét. A **Kilépett** szakaszban az adatok megadott számú napra, hónapra vagy évre vonatkozóan jeleníthetők meg. Például az elmúlt 14 napban kilépett dolgozók listájának megtekintéséhez állítsa az **Időszak** mezőt **14** értékre, az **Egység** mezőben pedig adja meg a **Napok** értéket.

Amikor a dolgozó megjelenik a **Kilépett** szakaszban, a következő műveletek érhetők el hozzájuk:

- Ellenőrzőlista alkalmazása\*\*
- Foglalkoztatás ellenőrzése
- Megtekintés a hierarchiában

\*\* Ez az alapértelmezett művelet. Gombként jelenik meg a kártyán.

## <a name="employee-changes-tab"></a>Alkalmazott módosításai lap

Az **Alkalmazott módosításai** lapon látható a dolgozók személyzeti műveleteinek listája. Ez a lista nem érhető el alapértelmezetten. A funkció engedélyezéséhez az **Emberi erőforrások megosztott paraméterei** oldal **Személyzeti műveletek** lapján állítsa be a **Dolgozói műveletek engedélyezése** lehetőség számára az **Igen** értéket.

## <a name="position-changes-tab"></a>Beosztásváltozások lap

A **Beosztásváltozások** lapon látható a dolgozók beosztással kapcsolatos műveleteinek listája. Ez a lista nem érhető el alapértelmezetten. A funkció engedélyezéséhez az **Emberi erőforrások megosztott paraméterei** oldal **Személyzeti műveletek** lapján állítsa be a **Beosztásműveletek engedélyezése** lehetőség számára az **Igen** értéket.

## <a name="open-positions-tab"></a>Nyitott pozíciók lap

A **Nyitott pozíciók** lap felsorolja az összes nyitott pozíciót. Ahhoz, hogy megjelenjen a listában, a pozíciónak mai vagy korábbi aktiválási dátummal kell rendelkeznie, és nem lehet aktuális dolgozói hozzárendelésük.

> [!NOTE]
> A lista a mai dolgozói hozzárendelést veszi figyelembe. A jövőbeli dátumú dolgozói hozzárendeléssel rendelkező pozíciók továbbra is megjelennek a listán. A dolgozói hozzárendelés hatályba lépési dátumának elérése után azonban a rendszer eltávolítja a pozíciót a listából.

## <a name="expiring-records-tab"></a>Lejáró rekordok lap

A **Lejáró rekordok** lap felsorolja az összes olyan elemet, amely lejárt vagy le fog járni annak a vállalatnak a dolgozói esetében, amelybe a felhasználó be van jelentkezve. A listában a következő elemek jelennek meg:

- **Diplomák**
- **Azonosítás**
- **Próbaidők**
- **Szűrések**
- **Tesztek**

Ha meg szeretné adni, hogy a lista a lejárt vagy a lejáró rekordokat jeleníti meg, az **Emberi erőforrások paraméterei** oldal **Általános** lapján határozzon meg időkeretet a **Lejáró rekordok** vagy a **Lejárt rekordok** számára. A **Lejáró rekordok** lapon szereplő adatok a megadott számú napig jeleníthetők meg. Például a következő 14 napban lejáró rekordok listájának megtekintéséhez a **Napok száma** mezőben adja meg a **14** értéket.

> [!NOTE] 
> Ha az **Emberi erőforrások paraméterei** oldalon a **Lejárt rekordok** vagy a **Lejáró rekordok** időkeretét **0** értékre állítja, akkor a listában nem fog megjelenni ilyen rekord.

## <a name="employees-tile"></a>Alkalmazottak csempe

Az **Alkalmazottak** csempe megjeleníti az összes olyan alkalmazott számát, aki abban a vállalatban áll alkalmazásban, amelybe a felhasználó jelenleg be van jelentkezve. Amikor az **Alkalmazottak** csempét választja, egy új lap jelennek meg az alkalmazottak részletes adataival.

## <a name="contractors-tile"></a>Alvállalkozók csempe

Az **Alvállalkozók** csempe megjeleníti az összes olyan alvállalkozó számát, aki abban a vállalatban áll alkalmazásban, amelybe a felhasználó jelenleg be van jelentkezve. Amikor az **Alvállalkozók** csempét választja, egy új lap jelennek meg az alvállalkozók részletes adataival.

## <a name="open-positions-tile"></a>Nyitott pozíciók csempe

A **Nyitott pozíciók** csempén látható a nyitott pozíciók teljes száma. Amikor a **Nyitott pozíciók** csempét választja, egy új lap jelennek meg a nyitott pozíciók részletes adataival. Ahhoz, hogy a rendszer beleszámítsa őket az itt megjelenő számba, a pozícióknak mai vagy korábbi aktiválási dátummal kell rendelkeznie, és nem lehet aktuális dolgozói hozzárendelésük.

> [!NOTE]
> A csempe a mai dolgozói hozzárendelést veszi figyelembe. A jövőbeli dátumú dolgozói hozzárendeléssel rendelkező pozíciók továbbra is beleszámítanak a megjelenő számba. A dolgozói hozzárendelés hatályba lépési dátumának elérése után azonban a rendszer nem számítja be őket a megjelenő számba.

## <a name="approvals-tile"></a>Jóváhagyások csempe

A **Jóváhagyások** csempe az aktuális felhasználó jóváhagyására váró összes munkafolyamat-elem számát tartalmazza. Amikor kiválasztja a **Jóváhagyás** csempét, egy új lapon megjelennek a jóváhagyást igénylő munkafolyamat-elemek részletei.

## <a name="address-changes-tile"></a>Címváltozások csempe

A **Címváltozások** csempe az összes olyan címváltozást számba veszi, amely az **Emberi erőforrások paraméterei** oldalon megadott számú napon belül történt. Amikor kiválasztja a **Címváltozások** csempét, egy új lapon megjelennek a címváltozások részletei. Az oldal jobb felső sarkában kiválaszthatja a **Jövőbeli címváltozásokkal** lehetőséget a jövőbeli dátumú címváltozások megjelenítéséhez.

A címváltozások megtekintésével és kezelésével kapcsolatos további tudnivalókat lásd a [Címváltozások megtekintése és kezelése](hr-personnel-view-address-changes.md) oldalon.
