---
title: Dynamics 365 Human Resources infrastruktúraegyesítés – GYIK
description: Ez a cikk megválaszolja a Microsoft, a Pénzügy Dynamics 365 Human Resources és a Műveletalkalmazások infrastruktúra-egyesítésével kapcsolatos gyakori kérdéseket.
author: twheeloc
ms.date: 11/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7325231718d7387450391b16b2866f9a2c05bdc4
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779635"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-faq"></a>Dynamics 365 Human Resources infrastruktúraegyesítés – GYIK

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="what-is-dynamics-365-human-resources"></a>Mi az az Dynamics 365 Human Resources?

A Microsoft Dynamics 365 Human Resources olyan eszközöket biztosít, amelyek segítik a HR-csoportokat a szervezeti agitás növelésében, az alkalmazotti tapasztalatok átalakításában és a HR-programok optimalizálásában, hogy olyan munkahelyet hozzanak létre, ahol az alkalmazottak és a vállalkozás növekedhet. További tudnivalók:Dynamics 365 Human Resources [Dynamics 365 Human Resources](https://dynamics.microsoft.com/human-resources/overview/)

- **Alkalmazotti tapasztalatok átalakítása** A fő teljesítmény megőrzése a vezetők és alkalmazottak révén a kapcsolódó önkiszolgáló tapasztalatokkal, amelyek az együttműködés és a növekedés jegyében állnak elő.
- **HR-programok optimalizálása.** A működési költségek csökkentése, valamint a személyek által központú szabadság- és távollétek, idő-, juttatás- és kompenzációkezelési programok létrehozása.
- **Szervezeti agilitység növelése.** A HR számára a vállalat által megkövetelt kézügyesség Dataverse Microsoft Power Platform engedélyezése az adatok használatával és a személyek adatainak központosított kezelésével, valamint az adatok egyszerű kiterjesztésével Dynamics 365 Human Resources.
- **Munkaerő-információkat lehet leásni.** Adatvezérelt döntéseket hoz az olyan, az adatok elemzésére és megjelenítésére való képességen keresztül, amelyek bármilyen eszközön elérhetők a felhasználói irányítópultokon.

## <a name="value-and-benefits-of-the-infrastructure-merge"></a>Az infrastruktúra-egyesítés értékei és előnyei

### <a name="what-is-the-dynamics-365-human-resources-infrastructure-merge"></a>Mit jelent a Dynamics 365 Human Resources egyesítés?

A Dynamics 365 két különböző infrastruktúrája jelenleg két külön HR-képességeket tartalmaz:

- **Dynamics 365 Human Resources**– önálló alkalmazás, amely független infrastruktúrán fut. Az alkalmazás elindításakor az infrastruktúra el lett választva a dynamics 365-ös műveleti alkalmazásoktól. Vevőink ezt az alkalmazást használják a szervezeti agitás növelésére, a HR-programok optimalizálására, az alkalmazotti tapasztalatok átalakítására és a munkaerő-információkra.
- **HR modul** – egy örökölt képességek halmaza, amely korábban része volt az egységesített műveleti licencelés tartásának egysége. A HR modul a pénzügyi és műveleti infrastruktúrán fut, ami minden műveleti alkalmazásnál ugyanúgy működik. Ezek közé tartoznak a Dynamics 365 Pénzügy és Dynamics 365 Project Operations a Dynamics 365 Supply Chain Management. A vevők a Dynamics 365 Pénzügy vagy a <a0/as típusú pénzügyi funkciók részeként kapták meg a HR-képességeket Dynamics 365 Supply Chain Management.

Az elmúlt három év során a Microsoft nem adott hozzá új funkciókat és fejlesztéseket a HR modulhoz. Ehelyett a beruházási beruházásunk az alkalmazásra fókuszált Dynamics 365 Human Resources.

Ha ezt a két képességeket ugyanazon az infrastruktúrán hozza össze, akkor a vevőknek a következő juttatásokat lehet elnyerni:

- Az elmúlt három évhez Dynamics 365 Human Resources hozzáadott fejlesztések, ideértve a továbbfejlesztett távollétet és távollétet, a juttatáskezelést és a jelentést.
- Továbbfejlesztett bővíthetőség a Microsoft Power Platform lapok testreszabására, valamint az üzleti logika kiterjesztésének lehetősége.
- Továbbfejlesztett telepítés, frissítések és karbantartás, amelyek az alkalmazás életciklusának kezelése, az életciklus-szolgáltatások, a földrajzi elérhetőség stb. szempontjából konzisztensek.
- Több példa van arra, hogy a mérnöki csoport megosztott szolgáltatásokat, eszközszolgáltatást és csökkentett platformköltségeket használ.

Ez az átmenet hatással lesz az akár az örökölt HR-modult Dynamics 365 Human Resources használó vevőkre.

## <a name="glossary-of-terms-used-in-this-faq"></a>A gyakran ismételt kérdéseknél használt kifejezések szószedete

- **Dynamics 365 Human Resources**– aktuális és jövőbeli termékünk, amely HR-képességeket kínál a piac számára.
- **HR modul** – az egyesített műveleteket kínáló szolgáltatásokkal korábban licencelt örökölt örökölt képességek halmaza. A funkciók akkor használhatók, ha a vevő a Dynamics 365 Pénzügy Dynamics 365 Supply Chain Management vagy a .<a0/<a2/<a2/.
- **Pénzügyi és műveleti infrastruktúra** – a műveletek által használt fejlesztői architektúra, például a Dynamics 365 Pénzügy, Dynamics 365 Supply Chain Management és Dynamics 365 Project Operations. Ez az infrastruktúra lesz a tovább használva. Ebben a gyakori kérdéseknél az egyesített *infrastruktúra* a pénzügyi és a műveleti környezetre utal.
- **Emberi erőforrások infrastruktúrája** – az alkalmazással kapcsolatban korábban használt fejlesztési architektúra Dynamics 365 Human Resources. Az infrastruktúra-egyesítési projekt a Dynamics 365 Human Resources pénzügyi és a műveleti infrastruktúrát is egyesíti. A különálló infrastruktúra megszűnik.

## <a name="general-questions-about-the-infrastructure-merge"></a>Általános kérdések az infrastruktúra-egyesítésről

### <a name="will-customers-lose-any-features-or-capabilities"></a>Az ügyfelek elvesznek minden funkció vagy képesség?

A cél az, hogy minimálisra csökkentsük az átmenet hatását a vevőkre. Nem távolítjuk el a funkciókat és funkciókat. A HR-modul és a Dynamics 365 Human Resources között funkcionális paritás lesz. Abban az esetben, ha egy funkció mindkét infrastruktúrában létezik, Dynamics 365 Human Resources akkor a rendszer a tapasztalatokat használja.

### <a name="will-the-user-experience-change"></a>Megváltozik a felhasználói felület?

A felhasználói felület összhangban lesz a Dynamics 365 platform szokásos felhasználói felületének használatával. Bár az általános tapasztalat a vezérlőpulton és a menükben is hasonló marad, a Dynamics 365 Pénzügy alkalmazás normál tapasztalatához igazodik. A navigáció modulokat és munkaterületeket is tartalmaz, engedélyezi a kedvencekhez stb. A Dynamics 365 Human Resources munkaterületek, például a **Személyzeti** **kezelés és a Személyek**, összevonják a pénzügyi és a műveleti infrastruktúrát. A funkciókezelés révén a jövőben új funkciók biztosítanak, amelyek segítségével a vevők megtekinthetik az új funkciókat, és eldöntheti, hogy melyik funkciót szeretnék használni. A további tudnivalókat lásd [a Funkciókezelés áttekintése és](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) a Felhasználói [felület dokumentációja témakörben](../fin-ops-core/fin-ops/get-started/user-interface-elements.md?toc=/dynamics365/human-resources/toc.json).

### <a name="when-will-the-dynamics-365-human-resources-infrastructure-merge-be-completed"></a>Mikor történik meg Dynamics 365 Human Resources az infrastruktúra-egyesítés?

Az infrastruktúra-egyesítés fázisok alatt áll, így a vevőknek időt kell adni a tervezéshez és a szükséges lépések fejlesztésére. Elkezdtük ki összegző funkciókat a Dynamics 2021 2. kiadási hullámában. A 2022-es kiadási hullám 2. nap ig tervezve lesz a projekt minden termékfejlesztési műveletének befejezése. Ne feledje, hogy az időrendek változhatnak. A legfrissebb tudnivalókat lásd a kiadási [tervekben](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-finance).

### <a name="what-training-and-resources-will-be-available-to-help-with-the-infrastructure-merge"></a>Milyen képzések és erőforrások lesznek elérhetők az infrastruktúra-egyesítésben?

Dokumentációt nyújtunk, amely részletesen leírja az infrastruktúra-egyesítési folyamat egyes lépését. A program további képzési erőforrásokat, például videók és műhelyeket biztosít, hogy a vevők és partnerek a megfelelő átmenetet segítik.

### <a name="will-there-be-changes-in-development-capabilities-after-the-infrastructure-merge-is-completed"></a>Módosulnak a fejlesztői képességek az infrastruktúra-egyesítés befejezése után?

A fejlesztői képességekről a [Honlap fejlesztés és testreszabás oldalon található további tudnivalók.](../fin-ops-core/dev-itpro/dev-tools/developer-home-page.md)

## <a name="feature-availability-questions"></a>Funkciók elérhetőségére vonatkozó kérdések

### <a name="will-the-linkedin-talent-hub-integration-work-on-the-finance-and-operations-infrastructure"></a>A LinkedIn Talent Hub integráció működik a pénzügyi és a műveleti infrastruktúrán?

Nem, a LinkedIn Talent Hub integráció nem lesz része az egyesített infrastruktúra-integrációnak. Nyilvános alkalmazásprogramozási felületek (API-k) állnak rendelkezésre a toborzási és pályázókövetési megoldásokkal való integráció építéséhez. A LinkedIn Talent Hub használatát tervező vevőknek a megadott API-k használatával együtt kell működniük Microsoft-partnerükkel. A pályázók nyomon követési rendszerével (ATS) integrációs API-król a [Pályázókövetési rendszer integrációs API-ja bevezetőjében található részletes tájékoztatás](./hr-admin-integration-ats-api-introduction.md).

### <a name="will-the-capabilities-that-are-currently-available-only-in-dynamics-365-human-resources-for-example-leave-management-and-benefits-management-be-available-after-the-merge-is-completed"></a>Az egyesítés befejezése Dynamics 365 Human Resources után csak a funkciók érhetők el (például a szabadságkezelés és a juttatások kezelése) terén?

Igen. Minden Dynamics 365 Human Resources alkalmazás-képességeket a pénzügyi és a műveleti infrastruktúrához hoznak. A funkciók a fokozatos megközelítésben érhetők el. Az egyesített infrastruktúra szolgáltatás-elérhetőségével kapcsolatos naprakész információkért rendszeresen tekintse át a kiadási [terveket](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-finance).

### <a name="will-ceridian-integrations-with-dynamics-365-human-resources-be-available-after-the-infrastructure-merge-is-completed"></a>A Ceridian-integráció elérhetővé válik Dynamics 365 Human Resources az infrastruktúra-egyesítés befejezése után?

A Ceridian integráció létrehozása folyamatban van a V2 Dynamics 365 Human Resources integrációban, amely kihasználja a bérlista API-ját. A fájl alapú integrációt, Dynamics 365 Human Resources amely jelenleg létezik, nem lehet áttelepíteni a pénzügyi és műveleti infrastruktúrába. A további tudnivalókat lásd: [Bérszámfejtés API bevezetés](./hr-admin-integration-payroll-api-introduction.md).

### <a name="will-applicant-tracking-or-onboardingoffboarding-of-employees-functionality-be-included"></a>A pályázóknak az alkalmazott funkcióit nyomon kell követnie, illetve a be- vagy külsős funkciókban kell nyomon követnie?

Az előző verziókban létrehozták az ATS integrációs API-t, amely lehetővé teszi a partnerek és a vevők számára, hogy ATS-integrációt hozzanak létre az Emberi erőforrások segítségével. Az ATS-hez kapcsolódó további funkciók elérhetővé váltak 2022-ben, az 1. hullámban. A későbbi verziókban is tovább bővítjük ezeket az API-kokat.

A hr-funkciók, amelyek jelenleg léteznek a pénzügyi és műveleti infrastruktúrában, olyan toborzáskezelési funkciókat is tartalmaznak, amelyek nem léteznek a költségvetésben Dynamics 365 Human Resources. Az infrastruktúra-egyesítés befejezése után ez a funkció minden emberi erőforrás vevő számára elérhető lesz. Ez a funkció egyszerű ATS-funkciókat biztosít. A jövőben azonban nem tervezjük ezt a funkciót kibontni. Azok a vevők, akiknek speciális funkciókra van szükségük, kihasználhatják a partner ATS-integrációt. Az ATS integrációs API-król [a Pályázókövetési rendszer integrációs API-ja nyújt további tájékoztatást](./hr-admin-integration-ats-api-introduction.md).

### <a name="will-the-dynamics-ax-2012-upgrade-tools-be-used-to-upgrade-the-hr-module-in-ax-2012-to-the-dynamics-365-human-resources-app"></a>A Dynamics AX 2012 frissítési eszközeivel lehet frissíteni a HR AX modult 2012-ben az alkalmazásra Dynamics 365 Human Resources?

Igen. Frissítés a Dynamics AX 2012 Dynamics 365 Human Resources verzióról arra, hogy ugyanazt a frissítési útvonalat és eszközt kövesse, mint a dynamics 365-ös műveleti alkalmazások, például a Dynamics 365 Finance Dynamics 365 Supply Chain Management vagy a.

A pénzügyi és műveleti infrastruktúrára való áttelepítéssel kapcsolatos további tudnivalókat lásd [az emberi erőforrásokkal kapcsolatos ügyféláttelepítési gyakori kérdéseknél](./customer-migration.md).
