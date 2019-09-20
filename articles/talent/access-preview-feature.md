---
title: Előzetes funkciók elérése a Microsoft Dynamics 365 for Talent alkalmazásban
description: Ez a témakör leírja, hogy a rendszergazda hogyan engedélyezheti az előzetes funkciókat a Microsoft Dynamics 365 for Talent alkalmazásban, és felsorolja azokat a funkciókat, amelyek jelenleg előnézetre engedélyezettek.
author: tracykeya
manager: AnnBe
ms.date: 05/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: trkeya
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2019 update
ms.openlocfilehash: 6a5aa8d6ea72ec3d3910edea291c4340ab607326
ms.sourcegitcommit: 7c49475402632069685df714546770d30804af7f
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/11/2019
ms.locfileid: "1739587"
---
# <a name="manage-preview-features"></a>Előzetes funkciók kezelése

[!include[banner](../includes/banner.md)]

A Microsoft Dynamics 365 for Talent emberierőforrás-menedzsment (HCM) lehetőségeit folyamatosan bővítjük, ennek részeként azt szeretnénk, hogy az ügyfelek a lehető leghamarabb használhassák az új funkciókat. A rendszergazdák láthatják és környezetükben használhatják az előnézeti szolgáltatásokat. Ezek a funkciók majdnem általános rendelkezésre állnak, és kiterjedt tesztelésen mentek keresztül. Az általánosan elérhető kibocsátás előtt egy utolsó visszajelzési és ellenőrzési kört végzünk az ügyfelekkel.

Ez a témakör leírja, hogy hogyan engedélyezheti az előzetes funkciókat, és felsorolja azokat a funkciókat, amelyek előnézet céljára jelenleg rendelkezésre állnak. Ez a lista frissül, ahogy a funkciókat általánosan elérhetővé tesszük, és ahogy új szolgáltatások előzetes kiadása történik meg. Nincsenek értesítések új funkciók előzetes kiadásakor. A felhasználók egyszerűen csak látni fogják a szolgáltatásokat. A Talent új funkcióival kapcsolatos információkért lásd: [Új vagy módosult elemek a Dynamics 365 for Talent szolgáltatásban](./whats-new.md) és [Dynamics 365 és Power Platform kibocsátási megjegyzések](https://docs.microsoft.com/business-applications-release-notes).

## <a name="enable-or-disable-preview-features"></a>Előnézeti szolgáltatások engedélyezése vagy letiltása

Az előzetes funkciók eléréséhez előbb engedélyeznie kell azokat a környezetben. Az előzetes funkciók engedélyezése és letiltása környezetfüggő.

> [!IMPORTANT]
> Az **Előzetes funkciók** beállításá bekapcsolása során a szervezet összes olyan felhasználója számára engedélyezi az előzetes funkciókat, akik az adott környezetben vannak. A beállítás kikapcsolása során letiltja le az előzetes funkciókat, és azok a felhasználók számára nem érhetők el. Az előnézeti funkciók támogatása korlátozott a Talentben. Előfordulhat, hogy ezek kevesebb adatvédelmi és biztonsági intézkedést használnak, és azok nem szerepelnek a Talent szolgáltatásiszint-szerződésében (SLA). Ne használja az előnézeti funkciókat személyes adatok (azaz az Önt bármilyen módon azonosítani képes adatok) feldolgozására, illetve más jogi vagy szabályozási, megfelelési követelmények hatálya alá tartozó adatok feldolgozására.

### <a name="attract"></a>Attract

1. Jelentkezzen be a Microsoft Dynamics 365 for Talent: Attract szolgáltatásba.
2. A jobb felső sarokban a **Beállítás** menüben (fogaskerék szimbólum) válassza ki a **Felügyeleti központ** lehetőséget.
3. A **Funkciókezelés** lapon válassza ki az **Előzetes funkciók** beállítás melletti lehetőséget úgy, hogy az kékre változzon és a **Be** feliratot mutassa.

    ![Az előzetes funkciók engedélyezése az Attract szolgáltatásban](./media/attract-enable-preview-features.png)

4. Jelölje ki vagy törölje a jelölést az egyes előzetes funkcióknál. Ha nem tesz semmit, akkor az összes elérhető előzetes funkció engedélyezve van.
5. Frissítse a böngészőjét, hogy elindítsa el az új szolgáltatások megjelenítését. Bármely, már bejelentkezett felhasználó számára a következő bejelentkezéskor jelenik meg a funkció, illetve frissíthetik a böngészőt a szolgáltatások azonnali megjelenítéséhez.

> [!NOTE]
> Előfordulhat, hogy egyes előzetes funkciók további konfigurációt igényelnek. A beállítás végrehajtásához kövesse az előzetes funkció melletti hivatkozásokat.

### <a name="core-hr"></a>Alapvető HR

1. Jelentkezzen be a Talentbe.
2. Válassza a **Rendszerfelügyelet** elemet, majd a **Hivatkozások** lapot.
3. A **Rendszerfelügyelet** lap **Beállítás** szakaszában válassza a **Rendszerparaméterek**elemet.
4. A **Rendszerparaméterek** lapon válassza az **Előzetes funkciók** fület.
5. Az **Előzetes mód engedélyezése minden felhasználó számára** beállítást állítsa **Igen** értékre az előzetes funkciók elérhetővé tételéhez.

    ![Az előzetes funkciók engedélyezése a Core HR szolgáltatásban](./media/corehr-enable-preview-features.png)

> [!NOTE]
> Az előzetes funkciók letiltásához kövesse ugyanezeket a lépéseket, de az **Előzetes mód engedélyezése minden felhasználó számára** beállítást állítsa **Nem** értékre. Előnézeti funkciók letiltása esetén azok elérhetetlenné válnak a felhasználók számára, és hibák fordulhatnak elő a szolgáltatásokkal kapcsolatos folyamatokban.

### <a name="onboard"></a>Felvétel

Jelenleg nem állnak rendelkezésre előzetes funkciók a Microsoft Dynamics 365 for Talent: Onboard alkalmazáshoz.

## <a name="features-that-are-currently-in-preview"></a>Az előnézetben jelenleg szereplő funkciók.

### <a name="attract"></a>Attract

- [Jelöltek ajánlása](./intelligent-recommendations.md#candidate-recommendations) – Ha tíznél több jelölt rendelkezik önéletrajzzal vagy teljes profillal, azok a jelöltek, akik leginkább megfelelnek az állás követelményeinek, megjelennek a **Figyelembe veendő pályázók** szakaszban az állás lapján.
- [Állások ajánlása](./intelligent-recommendations.md#job-recommendations) – Ha a karrierwebhelyen több mint tíz állást adtak fel, akkor az Attract állásokat javasol a potenciális jelöltek számára.
- [Broadbean-integráció](./posting-jobs-external.md#post-jobs-to-broadbean) – Az Attract alkalmazásból állásokat adhat fel a Broadbean felületésre, amely egy külső álláshirdetési webhely. Miután engedélyezte ezt az előzets funkciót, végre kell hajtania a beállítást a Broadbean felhasználóneve, ügyfélazonosítója és a titkosítási token megadásával.
- [Analitika](./analytic-reports.md) – A felvételért felelős csapatok az Elemzési központban megtekinthetik az egyes állások kulcsfontosságú mutatóit, valamint összesített mutatókat az összes állásra vonatkozóan.
- [EEO](./activities-attract.md) – Új tevékenységtípusok egy előre meghatározott űrlap használatát teszik lehetővé az Egyenlő foglalkoztatási lehetőség (EEO) és a Szövetségi szerződési megfelelőségi programiroda (OFCCP) adatok gyűjtésére a jelölttől. Az előre meghatározott képernyő nem szerkeszthető.
- [Potenciális jelöltek ajánlása](./intelligent-recommendations.md#prospect-recommendations) – Az Attract felülvizsgálja a múltbeli pályázókat és a jelenlegi jelölteket, és egy listát készít az álláshoz leginkább megfelelő potenciális jelöltekről.
- [Relevanciakeresés](./attract-talent-pools.md#search-and-view-candidate-profiles) – A teljes jelölti adatbázisban kereshet megadott szakértelmeket, neveket vagy tanulmányi háttereket. Az Attract a teljes profilban keres, és az összes találatot kiemeli. Az Attract keres minden olyan dokumentumban, amely elérhető a jelöthöz, és intelligens módon osztályozza a keresési eredményeket.
- [Tevékenység célközönsége](./whats-new-talent-march-20.md#setting-the-audience-on-activities) – Beállíthatja a tevékenységek célközönségeit (például Interjú, Ütemezés vagy Visszajelzés) a következőkre: **Összes jelölt**, **Belső jelöltek** vagy **Külső jelöltek**. Ügyféltevékenységeket, például YouTube-videókat, webes tartalmakat és Microsoft Képernyőket eljuttathat az összes jelöltnek, csak a belső jelölteknek, csak a külső jelölteknek vagy a felvételi csapatnak.
- [Jelentkezés a LinkedIn szolgáltatáson keresztül](./career-site.md#enable-applying-for-jobs-with-linkedin-profiles) – Beállíthat egy lehetőséget az Attract karrierwebhelyre, ahol az állás jelöltjei LinkedIn használatával is jelentkezhetnek. Ez a funkció egyszerűsíti a jelöltek pályázati folyamatát, és a LinkedIn profiljukat használva automatikusan kitölti a pályázatukat az Ön karrierwebhelyén.
- [Forrás nyomon követése](./source-tracking.md) – Az Attract nyomon követi a jelölti pályázatok forrásait, amellyel értékes információkat nyújhat a toborzási erőfeszítések összpontosításához. Kiválaszthat egy pályázati forrást, amikor manuálisan hozzáad egy jelöltet egy álláshoz vagy tehetségállományhoz.
- [Ezüstérmes](./whats-new-talent-march-20.md#designate-silver-medalists-to-assign-high-value-applicants-for-future-positions) – Ha valamelyik jelölt jó választás lenne a szervezet számára, de az aktuális pozícióra nem küldött neki ajánlatot, megjelölheti őket ezüstérmesként. Ezzel a funkcióval csökkentheti a felvétel idejét legközelebb, amikor hasonló pozíció válik elérhetővé.

### <a name="core-hr"></a>Alapvető HR

- [Beosztás hierarchiaadatainak ellenőrzése](./whats-new-talent-may-13-2019.md#new-page-to-validate-position-hierarchy-data) – Ellenőrizheti a vezetői hierarchia a véletlenül importált körkörös hivatkozásokhoz.
- [Okkódok megadása a szabadságtípusokon](./whats-new-talent-may-13-2019.md#specify-reason-codes-on-leave-types) – Megadhat okkódokat a szabadságtípusokhoz.
- [Okkódok kötelezővé tétele távollétkérelmeknél](./whats-new-talent-may-13-2019.md#require-reason-codes-for-specific-leave-types-on-time-off-requests) – A szabadságtípusok mellett kötelezővé teheti a távolléti kérelmek okkójainak megadását is.
- [Szabadság- és távollét-tranzakciólista biztosítása a HR-nek](./whats-new-talent-may-13-2019.md#provide-a-leave-and-absence-transaction-list-for-hr)– Megtekintheti a szabadság- és távolléti tranzakciók listáját, így nyújthat betekintést a távollétegyenlegekbe.

### <a name="onboard"></a>Felvétel

Jelenleg nem állnak rendelkezésre előzetes funkciók az Onboard alkalmazáshoz.

## <a name="feedback"></a>Visszajelzés

Szívesen vesszük visszajelzését bármely előzetes funkcióval kapcsolatos tapasztalatairól. Javasoljuk, hogy a rendszeresen küldje el a visszajelzését a következő webhelyeken, amikor ezeket a funkciókat használja vagy bármilyen más funkciót használ:

- [Közösségi](https://community.dynamics.com/enterprise/f/759?pi53869=0&category=Talent) – Ez a webhely remek fórum, ahol a felhasználók megbeszélhetik az eseteket, kérdéseket tehetnek fel és segítséget kaphatnak a közösségtől.
- Tájékoztasson bennünket, hogy mely funkciókat szeretné látni a termékben, illetve milyen változásokat végezzünk a meglévő funkciókon. A következő webhelyeken küldheti el az ötleteit a termékkel kapcsolatban:

    - [Attract ötletek](https://powerusers.microsoft.com/t5/Ideas-for-Attract/idb-p/Attract)
    - [Core HR ötletek](https://powerusers.microsoft.com/t5/Ideas-for-Human-Resources/idb-p/HumanResources)
    - [Onboard ötletek](https://powerusers.microsoft.com/t5/Ideas-for-Onboard/idb-p/Onboard)

Semmiképpen ne adjon meg személyes adatokat (azaz az Önt bármilyen módon azonosítani képes adatokat) a visszajelzésében vagy a termékértékelés benyújtásakor. Előfordulhat, hogy az összegyűjtött információkat tovább elemzik, és azokat nem használjuk fel kérdések megválaszolására az alkalmazandó adatvédelmi törvényekkel összhangban. A programokhoz kapcsolódóan külön gyűjtött személyes adatokra a [Microsoft adatvédelmi nyilatkozat](https://privacy.microsoft.com/privacystatement) vonatkozik.

> [!TIP]
> Tegyen Könyvjelzőt ehhez a témakörhöz, és a jöjjön vissza gyakran, hogy naprakész legyen az előnézeti funkciókkal kapcsolatban, ahogy azok megjelennek.

## <a name="see-also"></a>Lásd még

- [Talent alkalmazások kipróbálása vagy megvásárlása](https://dynamics.microsoft.com/talent/overview/)
- [Újdonságok](./whats-new.md)
- [Programverzióra vonatkozó megjegyzések](https://docs.microsoft.com/business-applications-release-notes/index)
- [Támogatás kérése a Talent alkalmazáshoz](./talent-support.md)
