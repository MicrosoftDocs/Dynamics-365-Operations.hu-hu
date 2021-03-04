---
title: LinkedIn-integráció beállítása az Attract szolgáltatásban
description: Ez a témakör azt mutatja be, hogyan lehet beállítani a LinkedIn integrációját a Microsoft Dynamics 365 Talent – Attract megoldáshoz, hogy egyszerűen feladhassa álláshirdetéseit a LinkedIn felületére az Attract megoldásból, és toborzói szinkronizálhassák toborzói adataikat a jelölt LinkedIn profiljával.
author: andreabichsel
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 4c518fb7036d44aa52c8db859ee3616fc4e58a06
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461423"
---
# <a name="set-up-linkedin-integration-with-attract"></a>LinkedIn-integráció beállítása az Attract szolgáltatásban

[!include [banner](includes/banner.md)]

Segíthet a toborzóknak és a felvételi vezetőknek, hogy bevonzzák a legjobb tehetséget a LinkedIn és a Microsoft Dynamics 365 Talent: Attract integrációjának konfigurálásával. Az Attract lehetővé teszi az állások közvetlen feladását a LinkedIn felületére, amely a legnagyobb szakmai online hálózat.

A LinkedIn felületén keresztül feladott állások Limited Listingek, és a vállalat számára külön költség nélkül érhetők el. Ezek a hirdetések csak a LinkedIn szoftveres partnerein, péládul az Attract alkalmazáson keresztül érhetők el. Nem jelennek meg a vállalat LinkedIn lapján a **Karrier** panelen, mivel csak ott csak a fizetett hirdetések jelennek meg. Azonban megjelennek, ha a potenciális jelöltek az összes elérhető állást megtekintik. A Limited Listingek a LinkedIn álláskeresésekben is megjelennek.

Az Attract kétirányú integrációt kínál a LinkedIn-hez, hogy segítsen jelentkezők keresésében a népszerű karrieroldalon:

- Állások feladása a LinkedIn felületére az Attract szolgáltatásból.
- Jelentkezők keresése LinkedIn felületén az Attract szolgáltatásba.

Az felügyeleti központban konfigurálhatja a **LinkedIn-integráció** lapon mindkét elérhető beállítást. A Felügyeleti központ megnyitása: <https://attract.talent.dynamics.com/adminsettings>.

> [!NOTE]
> A LinkedIn Recruiter integráció használatához az Attract megoldáshoz szükséges az [Átfogó felvételi bővítmény](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring) és [LinkedIn Recruiter licencek](https://business.linkedin.com/talent-solutions/cx/17/08/recruiter-demo-fs2-k18). További információ: [A Microsoft Dynamics 365 Talent – Attract melyik verziója](./attract-comprehensive-hiring.md)?

Ha tud állásokat közzétenni a LinkedIn rendszerbe, tekintse meg a következő cikket: [A LinkedIn és a Microsoft Dynamics 365 Talent – Attract közötti integráció hibaelhárítása](./attract-troubleshoot-linkedin.md).

A feladatok LinkedIn szolgáltatásba más módón történő feladásával kapcsolatos további tudnivalók: [Az Attract és a LinkedIn integrációja – GYIK](./attract-linkedin-faq.md).

## <a name="configure-job-posting-to-linkedin"></a>LinkedIn álláshirdetés konfigurálása

Mielőtt állást tehetne közzé az Attract megoldásból a LinkedIn felületére, szüksége lesz egy [LinkedIn vállalati azonosítóra](https://aka.ms/findID). Az Ön LinkedIn vállalatazonosítója számokból álló karakterlánc, amely egyedileg azonosítja a vállalatot LinkedIn oldalon belül. A további tudnivalókat lásd [A LinkedIn vállalati azonosítójának társítása a LinkedIn Job Boarddal - Gyakran ismételt kérdések](https://aka.ms/findID).

Az Attract elküldi álláshirdetéseit a LinkedIn részére, a LinkedIn pedig naponta egyszer ellenőrzi a hírcsatornát. Az állások feladása az oldalra akár 48 óráig is eltarthat.

A LinkedIn oldalra közzátett állássok az élő LinkedIn webhelyen jelennek meg. Nincs LinkedIn nem rendelkezik tesztelési környezettel állások közzétételéhez. Ezért ügyeljen arra, hogy ne tegyen közzé tesztállásokat. 

1. A jobb felső sarokban a **Beállítás** menüben (fogaskerék szimbólum) válassza ki a **Felügyeleti központ** lehetőséget. Másik lehetőségként válassza az <https://attract.talent.dynamics.com/adminsettings> oldalt.
2. Válassza ki az **LinkedIn integráció** lapot.
3. A **Vállalat neve** alatt írja be a vállalat nevét, a **Vállalat azonosítója** területen pedig adja meg a LinkedIn vállalati azonosítóját. Győződjön meg róla, hogy a vállalat neve megegyezik a vállalat LinkedIn oldalán megjelenő névvel. A LinkedIn vállalati azonosíótval kapcsolatos további tudnivalókat lásd [A LinkedIn vállalati azonosítójának társítása a LinkedIn Job Boarddal - Gyakran ismételt kérdések](https://www.linkedin.com/help/linkedin/answer/98972).

    Ha módosítania kell a szervezethez tartozó adatokat, lásd [A vállalat címének, műszaki kapcsolattartójának stb. módosítása](https://docs.microsoft.com/office365/admin/manage/change-address-contact-and-more). Ha továbbra is problémái vannak, forduljon a [LinkedIn támogatásához](https://www.linkedin.com/help/linkedin).

4. Válassza a **Mentés** lehetőséget.

## <a name="set-up-linkedin-recruiter-with-attract"></a>Állítsa be LinkedIn Recruiter szolgáltatást az Attract alkalmazással 

Ha engedélyezni szeretné, hogy a toborzók állásokat adjanak fel a LinkedIn Recruiter szolgáltatáson keresztül akkor konfigurálnia kell LinkedIn Recruiter integrációját az Attract megoldásban. A konfiguráció befejezéséhez a LinkedIn Recruiter-szerződés rendszergazda felhasználójával kell együttműködnie.

1. A jobb felső sarokban a **Beállítás** menüben (fogaskerék szimbólum) válassza ki a **Felügyeleti központ** lehetőséget. Másik lehetőségként válassza az <https://attract.talent.dynamics.com/adminsettings> oldalt.
2. Válassza ki az **LinkedIn integráció** lapot.

    [![Attract adminisztrátori nézet a LinkedIn Recruiter-integráció indításához](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3. Válassza a **Csatlakozás** parancsot a beállítás elindításához. A program végigvezeti a LinkedIn bejelentkezési folyamatán.
4. Ha több LinkedIn szerződésben vannak helyei, válassza ki a szerződést, amelyet az Attract rendszerhez szeretne csatolni. Ha csak egy LinkedIn szerződési helye van, ez a lépés kihagyható.
5. A **Recruiter rendszer csatlakozás (RSC)** alatt kattintson a **Kérés** elemre.

    [![Attract adminisztrátori nézet a LinkedIn Recruiter-integráció kérelmezéséhez](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)

6. A **toborzó System Connect (RSC)** beállítás most **Partner kész** értékként kell megjelenjen. Ha a **Partner értesítése** megjelenik ezen az oldalon, várjon néhány másodpercet, válasza a **Partner értesítése** elemet, majd frissítse a lapot. A beállítás most már **Partner kész** értékként jelenik meg.

    [![Attract adminisztrátori nézet, az Attract oldaláról érkező kérelmet teljesítették](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)

7. A következő lépések teljesítéséhez rendszergazdai jogosultságok szükségesek a LinkedIn Recruiter-szerződésen.

    1. Jelentkezzen be a LinkedIn webhelyre a rendszergazdai fiók segítségével, majd válassza a **LinkedIn Recruiter** lehetőséget a jobb felső sarokban. 
    2. A **További** menüben az oldal tetején kattintson az **Adminisztratív beállítások** elemre, majd kattintson az **ATS** lapra.
    3. Ha csak egy szerződéshez szeretné engedélyezni az exportálást egy kattintással, akkor kapcsolja be a **Szerződésszintű elérés (ezen szerződés minden licencéhez)** lehetőséget. Ha engedélyezni szeretné az egész vállalathoz, kapcsolja be a **Vállalati szintű hozzáférés (a vállalatminden szerződéséhez)** lehetőséget.

    [![LinkedIn Recruiter adminisztrátori nézet, Attract integráció bekapcsolása](./media/EnableRSC.png)](./media/EnableRSC.png)

8. Az Attract adminisztrációs központban válassza a **LinkedIn integráció** lapot. A **Recruiter System Connect (RSC)** beállításnál most **Engedélyezve** értéknek kell megjelennie.

    [![LinkedIn Recruiter-integráció befejeződött](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)

## <a name="set-up-apply-with-linkedin-in-attract"></a>A jelentekézés beállítása a LinkedIn szolgáltatáshoz az Attract megoldásban

Engedélyezheti, hogy a jelentkezők a LinkedIn profiljaik segítségével is pályázhassanak állásokra. A Jelentkezés LinkedIn-nel fukcióval kapcsolatos további tudnivalókat lásd [A LinkedIn funciói mindenütt. Jelentkezés a LinkedIn-nel](https://blog.linkedin.com/2011/07/24/apply-with-linkedin) blogbejegyzést.

Ez a funkció jelenleg előnézetben van. A következő lépések végrehajtása előtt győződjön meg arról, hogy a Jelentkezés LinkedIn-nel funkció engedélyezve van. Az előnézeti funkciók engedélyezésével kapcsolatos további tudnivalók: [Microsoft Dynamics 365 Talent – az előnézeti funkciók elérése](./access-preview-feature.md).

1. A jobb felső sarokban a **Beállítás** menüben (fogaskerék szimbólum) válassza ki a **Felügyeleti központ** lehetőséget. Másik lehetőségként válassza az <https://attract.talent.dynamics.com/adminsettings> oldalt.
2. Válassza ki az **LinkedIn integráció** lapot.

    [![Attract adminisztrátori nézet a LinkedIn Recruiter-integráció indításához](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3. A **Jelentkezés LinkedIn-nel** elem mellett válassza **Csatlakozás** parancsot a beállítás elindításához. A program végigvezeti a LinkedIn folyamaton.

## <a name="see-also"></a>Lásd még

[Az Attact és a LinkedIn integrációjával kapcsolatos gyakori kérdések](./attract-linkedin-faq.md)

[Állások feladása külső karrierwebhelyekre az Attract szolgáltatásból](./posting-jobs-external.md)

[Jelöltek felkutatása a LinkedIn Recruiter megoldással a Microsoft Dynamics 365 Talent – Attract szolgáltatásban](./attract-linkedin-recruiter.md)

[Állás létrehozása, jóváhagyása és feladása az Attract alkalmazásban](./creating-jobs-attract.md)

[A LinkedIn és a Microsoft Dynamics 365 Talent – Attract közötti integráció hibaelhárítása](./attract-troubleshoot-linkedin.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]