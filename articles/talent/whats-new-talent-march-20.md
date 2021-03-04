---
title: Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. március 20.)
description: Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.
author: Darinkramer
manager: AnnBe
ms.date: 03/20/2019
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
ms.search.validFrom: 2019-03-20
ms.dyn365.ops.version: Talent
ms.openlocfilehash: a7a44e1c9d8dcb4b2cc81a682a044d26cdc1149e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461389"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-march-20-2019"></a>Új vagy módosult elemek a Dynamics 365 Talent szolgáltatásban (2019. március 20.)

[!include [banner](includes/banner.md)]

Ez a témakör a Microsoft Dynamics 365 Talent új vagy módosított szolgáltatásait írja le.

## <a name="changes-in-attract"></a>Változások az Attract-ben

### <a name="setting-the-audience-on-activities"></a>A célközönség beállítása tevékenységekhez
A rendszer tevékenységeihez immár célközönséget is lehet definiálni. Folyamathoz kapcsolódó tevékenységek (például Interjú, Ütemezést, Visszajelzés és EEO) beállíthatók az Össze pályázóhoz, Belső pályázókhoz és Külső pályázókhoz. Egyéni tevékenységek, például a Microsoft Forms, YouTube videók és a webes tartalom eljuttatható valamennyi pályázónak, belső pályázóknak, külső pályázóknak vagy a felvételi csapat számára.  

### <a name="improve-career-site-job-discoverability-search-engine-optimization"></a>Karrierwebhelyen található munka felfedezhetőségének javítása: Keresőmotor optimalizálása
Ez a szolgáltatás lehetővé a keresőmotor-adatbányászok számára, hogy elérjék a és indexeljék az álláshirdetéseket az Attract karrieroldalán. Ez megkönnyíti a jelentkezők számára az Attract karrieroldalán található álláshirdetések megtalálását népszerű keresőmotorok használatával.

### <a name="show-login-hint-to-candidates-who-forgot-their-credentials"></a>Bejelentkezési javaslatait megjelenítése azon jelöltek számára, akik elfelejtették hitelesítő adataikat.
Ha a jelölt elfelejtette különleges hitelesítő adatait, amelyet akkor használtak, amikor jelentkeztek a munkára és megnyitották az elmentett vagy e-mailben küldött hivatkozást, így egy javaslatot látnak a szolgáltató nevével és felhasználónévvel (álcázva). Ennek segítéségével a megfelelő hitelesítő adatok használatával érhetik el pályázatukat.

### <a name="help-internal-candidates-explore-internal-jobs"></a>Segítség a belső pályázóknak belső állások felfedezésében
Egy hiba került javításra, ahol a külső jelentkezők láthatták a munkához tartozó toborzó neve vagy a felvételi vezető nevét. Mostantól csak belső pályázók tekintheti meg az álláshoz tartozó felvételi csapatot. Könnyebb lett a belső jelentkezők számára a belső állások megtekintése és a jelentkezés. Ha egy jelentkező megpróbálni elérni a hivatkozást egy csak belső állás megtekintéséhez vagy a jelentkezéshez akkor hitelesítenie kell magát az Azure Active Directory hitelesítő adataival. A belső pályázók felvehetik a kapcsolatot a felvételi csapattal, hogy kifejezzék érdeklődésüket, vagy tájékozódjanak az állással kapcsolatosan. Ez a lehetőséget az összes álláshoz, és csak belső jelöltek számára érhető el. A további tudnivalókat lásd [Karrierwebhely beállítása a Microsoft Dynamics 365 Talent – Attract szolgáltatásban](./career-site.md).

### <a name="designate-silver-medalists-to-assign-high-value-applicants-for-future-positions"></a>Ezüstérmesek kijelölése, hogy értékes jelentkezőket lehessen hozzárendelni jövőbeni beosztásokhoz.
Felvételi vezetők és toborzók gyakran listát vezetnek azon pályázókról akik a beosztásra alkalmasak, de nem lehetett ajánlatot tenni nekik, mert a beosztás már be volt töltve. Az ilyen pályázók, más néven ezüstérmesek értékesek, hiszen segítségükkel csökkenthető a felvételhez szükséges idő, ha egy hasonló pozíció nyílik meg. Az Attract most lehetővé teszi, hogy a toborzók és felvételi vezetők számára, hogy ezüstérmeseket válasszanak ki a jelentkezők közül, ha a pályázó bejutott az Ajánlati szakaszba. Az ezüstérmes besorolás, megjelenik a pályázók listáján a munkához, illetve a tehetségállomány nézetben is, ha a jelentkező tagja a toborzó vagy a felvételi vezető állományainak. Ezenkívül a kijelölés megjelenik a feladatelőzményekben a jelölt tehetségbázis-profilja részeként. Ezt a funkció úgy tekintheti meg, hogy egy rendszergazda segítségével bekapcsoltatja a [Felügyeleti központ Funkció kezelése](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature) részében.

### <a name="add-applicants-to-talent-pools"></a>Pályázók hozzáadása tehetségállományokhoz
Könnyebé vált a pályázók hozzáadása a tehetségállományokhoz egy új művelet előhozásával a Pályázók listájában. A **Hozzáadás a tehetségállományhoz** ikon kiválasztásával a toborzó vagy humánerőforrás-vezető választhat a tehetségállományából és könnyen hozzáadhat pályázókat a tehetségállományokhoz egy munka Pályázóinak listájából.

### <a name="configure-whether-a-resume-is-required-to-apply-for-a-particular-job"></a>Annak beállítása, hogy önéletrajz szükséges-e egy adott állásjelentkezéshez
Az ügyfelek visszajelzései alapján a toborzók immár beállíthatják, hogy szükséges-e fájlként feltöltött önéletrajz a jelentkezéshez egy adott állásra. Ez a beállítás az Jelentkezés tevékenység része, és elérhető a felvételi folyamat részeként. Ha engedélyezve van, minden lehetséges pályázó fel lesz kérve önéletrajz feltöltésére, amikor erre az állásra jelentkezik. A pályázat nem minősül késznek, csak önéletrajz feltöltése esetén. Ez átláthatóbbá teszi pályázóállományt, biztosítva azt, hogy minden pályázó elég információt adott meg ahhoz, hogy a toborzó besorolja őt.

### <a name="candidates-can-apply-to-a-job-using-their-linkedin-profile"></a>Pályázók LinkedIn profil használatával jelentkezhetnek állásra
Azon pályázók, akik már jelentkeznek naprakész LinkedIn-profillal, egyetlen kattintással jelentkezhetnek az állásra a profil használatával.

### <a name="track-how-a-candidate-profile-originated-in-the-system-and-where-your-applicants-discover-the-jobs-they-applied-for"></a>Annak követése, hogy a jelölt profilja honnan származik a rendszerből, illetve, hogy hol találták meg a az állást a pályázók, amelyre jelentkeztek.
Most megtudhatja honnan származik egy adott jelölt profilja az Attractban, ha megnézi a profil forrását a jelölt adatainál a pályázat vagy tehetségállomány profilja **Profil** részében. Ehhez hasonlóan állapíthatja meg, hogyan fedezte fel a pályázó az állást az pályázat forráskódjának megtekintésével, amelyet a **Pályázat tevékenység** alatt talál meg a pályázat csatornatevékenységében. Ez az információ a feladatelőzményekben is elérhető a tehetségállomány profiljában. Ha a toborzók vagy felvételi vezetők manuálisan adnak hozzá pályázókat, a rendszer kéri, hogy határozzák meg a pályázat vagy a jelentkezői profil forrását. Ha a jelölt első alkalommal pályázik, a profil forrása megegyezik pályázatuk forrásával. Ezt a funkció úgy tekintheti meg, hogy egy rendszergazda segítségével bekapcsoltatja a [Felügyeleti központ Funkció kezelése](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature) részében. Ne feledje, hogy meglévő jelöltek és a pályázók esetében nincsenek forrásadatok. Azonban a toborzók hozzáadhatják ezeket az adatokat manuálisan.

## <a name="changes-in-onboard"></a>Változások az Onboard alkalmazásban

A kiadás a Dynamics 365 Talent: Onboard apró hibáinak javításait is tartalmazza.

## <a name="changes-in-core-hr"></a>A Core HR módosításai

A szakaszban ismertetett módosítások a 8.1.2195-ös buildre vonatkoznak

### <a name="attract-integration-throws-duplicate-record-error-for-applications"></a>Az Attract integráció duplikált rekordokkal kapcsolatos hibát mutat a Pályázatokhoz
Ebben a frissítésben a duplikált rekordokkal kapcsolatos probléma megoldásra került. A probléma akkor jelent meg, amikor megnyitották a **Személyzetkezelési** munkaterületet.

### <a name="unable-to-close-form-when-editing-name-sequence"></a>Névsorrend szerkesztésekor az űrlap bezárása nem volt lehetséges
Módosítások történtek egy probléma megoldása érdekében, amely akkor jelent meg, amikor szerkesztették a névsorrendet a dolgozó űrlapján.

## <a name="coming-soon"></a>Hamarosan

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Haladó kompenzációs biztonsági (fix és változó)
Számos vállalatnál a kompenzációkért és juttatásokért felelős vezetők előfordulhat, hogy csak a bizonyos kompenzációs rekordokhoz férnek hozzá. Ezek a vezetőkhöz és regionális alkalmazottak hoz tartozhatnak. Ez a módosítás lehetővé teszi a HR számára kompenzációs tervek kezelését és karbantartását a szervezet különböző alkalmazottcsoportjaihoz. A fix és változó kompenzációs tervek, amelyeket hozzárendelhet biztonsági szerepkörökhöz, határozzák meg a hozzáférést ezekhez a tervekhez és a hozzájuk kapcsolódó alkalmazotti adatokhoz, például fizetés és bónuszrekordok. Csak a hozzáférést kapott szerepkörök dolgozhatnak fel kompenzációt azokhoz a munkavállalókhoz.

###  <a name="email-support-for-alerts"></a>E-mailek támogatása figyelmeztetésekhez
A Finance and Operations 24-ös platformfrissítésével a felhasználók létrehozhatnak figyelmeztetési szabályokat, amely automatikusan értesítő e-maileket küldenek ki a kapcsolattartóknak, ha egy esemény kezdeményezi azt.

### <a name="duplicate-employee-check-interface-changes"></a>Duplikált alkalmazottak ellenőrzése: Felhasználói felület módosításai
Ez a módosítással az ismétlődések észleli a program, amikor névmezőket ad meg, és egy állapot jelenik meg a talált ismétlődések számával. A hivatkozás kiválasztásával megnyithat egy új lapot, hogy megállapítsa, hogy használja-e az észlelt egyezést. Az adatbevitel megzavarása elkerülése érdekében az ismétlődéseket tartalmazó űrlap nem nyílik meg automatikusan.




[!INCLUDE[footer-include](../includes/footer-banner.md)]