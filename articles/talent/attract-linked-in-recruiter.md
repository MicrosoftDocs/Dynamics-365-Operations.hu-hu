---
title: Forráskeresés LinkedIn Recruiter segítségével
description: Ez a témakör a gépi tanulásnak az állás- és állásjelölti javaslatok beszerzésére való használatával kapcsolatban tartalmaz tájékoztatást.
author: josaw
manager: AnnBe
ms.date: 12/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: josaw
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 9bb323728923ff3b09ff0bfba3849f3c5d84eb34
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "304633"
---
# <a name="sourcing-with-linkedin-recruiter"></a>Forráskeresés LinkedIn Recruiter segítségével
[!include[banner](../includes/banner.md)]

A LinkedIn a világ legnagyobb szaktudás-adatbázisa, és gyakran az elsődleges rendszer, amelyet a toborzók jelöltek megtalálására, a velük való kommunikációra és forráskeresésre használnak az aktuális állásra. A LinkedIn Recruiter és a Dynamics 365 for Talent: Attract integrálása megkönnyíti a felhasználók számára a felvételt, valamint az adatok két rendszer közötti szinkronizálását.

> [!NOTE]
> Az átfogó felvételi bővítmény és LinkedIn Recruiter helyek szükségesek a LinkedIn Recruiter és az Attract integrációjának használatához.

## <a name="set-up-linkedin-recruiter-with-attract"></a>Az Attract és a LinkedIn Recruiter beállítása 

A LinkedIn Recruiter funkciók használata előtt konfigurálnia kell szerződésszintű, vagy a vállalatiszintű hozzáférést az Attract-példánnyal. A konfiguráció befejezéséhez a LinkedIn Recruiter szerződés rendszergazda felhasználójával kell együttműködnie. A következő lépések bemutatják a LinkedIn Recruiter és az Attract beállítását.

1.  Jelentkezzen be rendszergazdaként az Attract rendszerébe, és nyissa meg: **Adminisztratív beállítások**.

2.  A bal panelen kattintson a **LinkedIn integráció** lapra.

[![Attract adminisztrátori nézet a LinkedIn Recruiter integráció indításához](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3.  Kattintson a **Csatlakozás** elemre a telepítő elindításához, és csinálja végig a LinkedIn bejelentkezési folyamatát.

4.  Ha több LinkedIn szerződésben vannak helyei, válassza ki a szerződést, amelyet az Attract rendszerhez szeretne csatolni. Ha csak egy LinkedIn szerződési helye van, ez a lépés nem szükséges.

5.  A LinkedIn widget most betölti a rendszergazdai beállításokat integrációk megjelenített listájával. A **Recruiter rendszer csatlakozás** alatt kattintson a **Kérés** elemre.

[![Attract adminisztrátori nézet, a LinkedIn Recruiter integráció kérése](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)

6.  Az integráció kérelmezése után az Attract rendszertől, megjelenik a **Partner kész** módon, és már be lehet kapcsolni a **Recruiter adminisztratív beállítások** helyről. Ha a **Partner értesítése** megjelenik ezen az oldalon, várjon néhány másodpercet, kattintson a **Partner értesítése** elemre, majd frissítse a lapot. Most meg kell jelennie a **Partner kész** állapotban.

[![Attract adminisztrátori nézet, az Attract oldaláról érkező kérelmet teljesítették](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)

A következő lépésre teljesítéséhez rendszergazdai jogosultság szükséges a LinkedIn Recruiter szerződésen.

7.  A LinkedIn rendszerébe a rendszergazda fiók használatával jelentkezzen be, és nyissa meg a jobb felső sarokban LinkedIn Recruiter elemet. 

8. A **További** menüben a képernyő tetején kattintson az **Adminisztratív beállítások** elemre, majd kattintson az **ATS** lapra.

Az Attract rendszer jelenik meg a néhány beállítással, amelyek bekapcsolhatók.

9. Ha csak az 1 kattintásos exportálást szeretné engedélyezni at **In-ATS jelzőhöz** és az **In-ATS profil widgethez**, jelölje be a **Vállalati szintű hozzáférést**. Ha engedélyezni szeretné az összes vállalati szintű hozzáférési funkciót plusz az InMail előzményeket, a Megjegyzések előzményeit és az InMail csonka profil hozzáférést, jelölje be a **Szerződés szintű hozzáférés** elemet.

10. Kapcsolja be a kívánt hozzáférési szintet a LinkedIn Recruiter **Admin-ATS** beállításaiban.

[![LinkedIn Recruiter adminisztrátori nézet, Attract integráció bekapcsolása](./media/EnableRSC.png)](./media/EnableRSC.png)

12. Térjen vissza az Attract adminisztratív beállításokhoz AttractAdminként, és válassza ki a **LinkedIn integráció** lapot. Azt kell látnia, hogy a LinkedIn widget be van töltődve **Engedélyezett** állapottal, a kijelölt hozzáférési szint pedig be van kapcsolva.

[![LinkedIn Recruiter-integráció kész](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)

## <a name="using-linkedin-recruiter-capabilities"></a>A LinkedIn Recruiter lehetőségeinek használata

Miután LinkedIn Recruiter lehetőségeket az Attract rendszergazda engedélyezte, elérhető a felvételi vezetők és a toborzók számára. A funkciók használatához csatlakoztassa LinkedIn-fiókját itt: **Felhasználói beállítások**. Több képesség lesz elérhető az adminisztrációs és felhasználói beállítások csatlakoztatása után.

### <a name="in-ats-profile-widget"></a>In-ATS profil widget

A jelölt LinkedIn profilját megtekintheti az Attract rendszerében. A LinkedIn widget megjeleníti a pályázó profilját, amikor az ATS adatok megfelelnek a felhasználók LinkedIn adatainak.

Profil megtekintéséhez menjen a jelentkező profiljához az állásból vagy a szaktudáskészletből elindulva. A pályázói profilnál válassz a **LinkedIn** lapot, és betöltődik a profilwidget. A pályázót mentheti is erről a lapról LinkedIn Recruiter projektjeibe.
1. Ha aLinkedIn talált egyezést az e-mail cím és LinkedIn tagazonosító alapján (pontos egyezés) a pályázó profilja megjelenik. A felhasználónak továbbra is lehetősége van a profil kapcsolására/leválasztására.

2. Ha a LinkedIn nem találja a jelentkezőt az e-mail-cím vagy tagazonosító alapján, megjeleníti a lehetségesen egyező jelölteket a jelölt neve alapján, és a felhasználó, kiválaszthatja egyiküket, és hozzákapcsolhatja a profilhoz.  

3. Ha LinkedIn egyetlen jelöltet sem talál a név alapján, azt küldi vissza, hogy nem található egyezés.

### <a name="1-click-export"></a>1 kattintásos exportálás 

A LinkedIn rendszerében pályázók keresésekor 1 kattintással exportálhatja a pályázókat az éppen nyitott állásokhoz. Hajtsa végre a következő lépéseket az 1 kattintásos exportáláshoz. A lépések lezárása előtt ellenőrizze, hogy a hozzárendelt szerepe felvételi vezető vagy toborzó az állás esetében, és hogy az állás a **Jelölt** szakaszban legyen.

1.  Végezze el az állás létrehozását, a megfelelő szerepkörök hozzárendelését, és aktiválja az állást.

2.  Az állás aktiválása után menjen ide: LinkedIn Recruiter.

3.  Keresse meg a keresett jelöltet, és ugorjon a profiljához.

4.  A névjegykártya álláskeresés mezőjével keresse meg az állást az Attract rendszerében aktivált álláscím vagy állásazonosító alapján. Ha nem találja az állást, kattintson az **ATS módosítása** elemre a megfelelő Attract-példány megkereséséhez.

5. Miután kiválasztotta az állást, kattintson az **Exportálás** elemre. A pályázót az Attract most beolvassa.

6.  Menjen az Attract rendszerébe, és nyissa meg a megfelelő állást. Az imént exportált jelöltet megtalálja az állás **Jelölt** állapotában.

### <a name="in-ats-indicator"></a>In-ATS jelölő 

LinkedIn Recruiter használatával nyomon követheti, hogy pályázó jelentkezett-e a szervezeténél más állásokra, megnézheti, hogy hol tart az álláspályázatok különböző szakaszaiban, és LinkedIn Recruiter rendszerében megtekintheti az Attract visszajelzéseit és megjegyzéseit.

1.  Nyissa meg a LinkedIn Recruiter rendszert, és keresse meg a kívánt pályázói profilt.

2.  Görgetés lefelé az **In-ATS** szakaszhoz a jelölt profiljában.

3.  A widget segítségével minden olyan jelöltadat megtekinthető a LinkedIn Recruiter nézetben, amely megtalálható az Attract rendszerében.

4.  Válassza ki az **Állások és állapotok** lapot az állások megtekintéséhez, amelyeknek a részesei, a legutóbbi állapot megtekintéséhez, és hogy hogyan mozogtak az egyes állások esetében.

5.  Válassza ki az **Interjú-visszajelzés** fület az interjúbonyolítók által az Attract rendszerébe beküldött visszajelzések megtekintéséhez.

6.  Válassza ki a **Megjegyzések** lapot a pályázóhoz az Attractban rögzített megjegyzések megtekintéséhez.

> [!NOTE]
> A pályázó- és pályázati adatok nem lesznek szinkronizálva a LinkedIn Recruiter-rel, ha a jelentkező nem lépett túl a potenciális szakaszon.

### <a name="inmail-history"></a>InMail-előzmények

Szerződés szintű hozzáféréssel elérhetők a LinkedIn InMail előzményei a LinkedIn Recruiter szolgáltatásban. Ha engedélyezve van, a pályázó teljes InMail előzményei megjeleníthetők. Megtekintheti, hogy a szervezetből ki váltott InMail üzeneteket a pályázóval, az üzeneteket azonban nem lehet megtekinteni.

Az InMail-előzmények megtekintéséhez ugorjon a jelentkező profiljára, menjen a **LinkedIn** lapra, és görgessen az előzmények megtekintéséhez a lap aljára. Ha a pályázóval beszélgetett, megtekintheti az InMail-előzményeket. Az InMail üzenetei az Attract rendszerével néhány óránként szinkronizálódnak.

### <a name="notes-history"></a>Megjegyzések előzményei 

Szerződés szintű hozzáféréssel elérhetők a LinkedIn megjegyzések előzményei a LinkedIn Recruiterben. Ha engedélyezve van, megtekintheti a szervezet különböző toborzói által a jelölttel kapcsolatosan rögzített megjegyzéseket.

A megjegyzéselőzmények megtekintéséhez ugorjon a jelentkező profiljára, menjen a **LinkedIn** lapra, és görgessen az előzmények megtekintéséhez a lap aljára. A pályázóval kapcsolatosan rögzített összes megjegyzést megtekintheti a LinkedIn Recruiterből.

### <a name="inmail-stub-profile"></a>InMail csonka profil

Szerződés szintű hozzáféréssel elérhetők az InMail csonka profil a LinkedIn Recruiterben. Ha a pályázó elfogadja a LinkedIn-profilja megosztása a szervezet egy felhasználójával, nyomon követheti a jelölteket az Attract rendszerében, és minden egyes jelölthöz létrejön egy új jelentkezőrekord. Ha a pályázó már létezik a rendszerben egy e-mail címmel, vagy úgy döntött, hogy megosztja e-mail-címét a toborzóval, megtekintheti a jelölt e-mail-címét.

A pályázók listájának megtekintéséhez menjen a **Szaktudásgyűjtők** elemhez a rendszer által létrehozott LinkedIn szaktudásgyűjtők ellenőrzéséhez. A szaktudásgyűjtő a LinkedIntől kapott jelöltlistákat és a jelöltek csonka profiljait tartalmazza, a jelölt keresztnevét és vezetéknevét mutatva. A pályázó e-mail-azonosítója fog megjelenni, ha a pályázó az e-mail-címe megosztását választotta.
