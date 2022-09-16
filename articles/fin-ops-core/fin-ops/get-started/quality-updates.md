---
title: Proaktív minőségi frissítések
description: Ez a cikk a minőségi frissítések proaktív teljesítésével kapcsolatban tartalmaz tájékoztatást.
author: rashmansur
ms.date: 09/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form: ''
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 985800aad3711a1b28613f0f82585b4d592cdf58
ms.sourcegitcommit: de989037d83393bea013cd58c061159765305b4f
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473605"
---
# <a name="proactive-quality-updates"></a>Proaktív minőségi frissítések

[!include[banner](../includes/banner.md)]

Az elmúlt pár évben a Microsoft [folyamatos haladást ért el az Egy verzióként hivatkozunk rá](../../dev-itpro/lifecycle-services/oneversion-overview.md). Az Egy verzió előzetes verziója egyszerű: minél közelebb van az összes vevő azonos szoftververzióhoz, annál magasabb a szállított minőség. A problémákat egyszer megkeresjük és kijavítjuk, és ezeket a megoldásokat gyorsabban rá lehet venni a több vevőre.

Ezt a esetet az eredmények igazolják: a termékek között kisebb események száma. Ha az ügyfelek nem ugyanazon a verzión vannak, konzisztensen látjuk, hogy érintik őket azok a problémák, amelyekre egy megoldás már elérhető. Már nagy haladást ért el a Dynamics 365 Pénzügy, a Dynamics 365 Dynamics 365 Project Operations Dynamics 365 Commerce Ellátási lánc, és – a közelmúltbeli technikai fejlesztéseknek köszönhetően – most már lehetséges a következő lépés. A következő információk bemutatják, hogy mit kell tenni, mit megtettünk a fokozat beállításában, és hogy mikor és hogyan vezetjük be az új lehetőségeket, anélkül, hogy megszakadna a folyamat.

## <a name="focus-on-quality-updates"></a>Fókuszálás a minőségi frissítésekre

Jelenleg évente hét [szolgáltatásfrissítést](public-preview-releases.md) biztosítunk. Például a 10.0.29-es verzió egy szolgáltatásfrissítés. A közelmúltig évente nyolc frissítés volt. A felhasználói visszajelzések alapján azonban egy frissítést dobunk el, amely a naptári év végi változások elkerülésére iránti szándékot tárt fel.

Nem módosítjuk a szolgáltatásfrissítések változásának a változását. Ehelyett az Egyverziós *utazás következő lépése a minőségi frissítésekre fókuszál*. A minőségi frissítések a gyorsjavítások kumulatív összeállításai. Nem tartalmaznak új funkciókat. A vevők teljes közössége egy adott időpontban a három vagy négy legújabb szolgáltatásfrissítés között van elterjesztve. Ugyanakkor egy adott szolgáltatásfrissítésnél a csoporton belül felhasználható a különböző minőségi frissítési verziók 1/10-ére vonatkozó ellenőrzés, a személyek telepítésének dátumától függően. A következő lépéssel proaktívan jukozzák a minőségi frissítéseket. Ezt a modellt már használtuk Dataverse a saját alkalmazásokhoz, és láthatta a jobb minőség és a csökkent támogatási események várható eredményeit.

A hibák csökkentése természetesen csökkentheti vagy teljesen megszüntetheti a minőségi frissítésekre való szükségét. Több kezdeményezésunk van a repülőút során, hogy csökkentse a minőségi frissítéseket igénylő hibákat. Még ha a minőségi frissítés csökkenti is a rakományokat, az ügyfélbázison keresztüli egységesség javítja a támogatottságot, a vevőknek gyorsabban elérhető fejlesztéseket, és csökkenti annak a gyakoriságát, hogy a vevők milyen problémákat tapasztaltak már.

## <a name="making-proactive-distribution-possible"></a>A proaktív elosztás lehetővé teszi

Már több előleget telepítettek, amelyek a minőségi frissítések proaktív szállítását teszik lehetővé:

- **Leállási** idő közeli frissítése – a gyakori környezetek továbbküldése érdekében alapvető fontosságú, hogy a Dynamics 365 szolgáltatásiszint-szerződések (SLAS) megőrzése érdekében csökkentve legyen a környezet elérhetősége. Eredetileg a nulladik leállási idő frissítését vezették be, hogy a havi operációs rendszer javítása érdekében egy fürt-újraelosztás segítségével aktiválják a frissített képet a minimális megszakadás mellett. A frissítések alkalmazásának mechanizmusa továbbfejlesztett, így még kevésbé romboló, és lefedi az operációs rendszer javítása és a minőségi frissítés telepítését is.

    Interaktív felhasználók esetén egy aktív munkamenet megszakadhat, és az újrapróbálkozás a most frissített környezetre kerül. A prioritáson [alapuló](../../dev-itpro/sysadmin/priority-based-batch-scheduling.md) kötegütemezés bevezetésével, amely most elérhető a telepítés után, a kötegelt ütemezés és a feldolgozás közvetlenül a frissítés után áll helyre, és folytatódik. A prioritáson alapuló kötegütemezés akkor lép helyére, ha a vevők még nem vehetnek részt termelési környezeteik minőségi frissítésének proaktív elosztásában.

- **Sötét órák** – az egyes Azure-régiókhoz sötét órákat határoznak meg, és a sötét órákban a közeli nulla leállási idő frissítésekre is sor fog kapni.

## <a name="the-proactive-update-process"></a>A proaktív frissítési folyamat

A proaktív minőségi frissítések telepítése egy biztonságos telepítési folyamatot (SDP) követ. Az SDP adottai változhatnak, de kezdetben a minőségi frissítéseket abox környezetekbe telepítik. A folyamat olyan környezetekkel kezdődik, amelyek a korai telepítés mellett indulnak. A sikeresen telepített mezők százalékos aránya nő, ezért éles környezetekben is elkezdődik a telepítés. A folyamat ismét olyan környezetekkel kezdődik, amelyek a korai telepítést választották. A figyelőrendszerek figyelemmel fogják követni a rendszer és az livesite eseményeket, és leállítja egy adott verzió ki- és begörgetését, ha a rendszer regresszívet észlel. Az ügyfelek így is a proaktív telepítés előtt le tudják húzni a minőségi frissítéseket.

Az aktuális kiadáskezelési adatok azt mutatják, hogy a minőségi frissítésekben a regresszív állapotok kevesebb mint 3 százaléka van bevetve. Ha nagyobb a figyelem a regresszás megszüntetésén és a jobb SDP-n, akkor a regressációk potenciális hatása általában alacsonyabb lesz, mint az olyan minőségi nyereség, amely a vevőknek általában telepített gyors javításokkal érhető el.

## <a name="process-changes"></a>Módosítások feldolgozása

A folyamatok változásainak egy része a proaktív minőségi frissítés aktiválása előtt van megvalósítva:

- **Séma** – az eszköz gondoskodik arról, hogy a minőségi frissítések csak olyan sémákat tartalmazzanak, amelyek a szolgáltatás online állapotban alkalmazhatók. Ezzel a módszersel megőrizheti a nulla leálláshoz közeli leállással elérhető frissítés alkalmazni való képességet.
- **Növelt módosítási változás** - jelenleg már van egy extra folyamatlépés, amely a minőségi frissítésbe való felvétel módosításainak jóváhagyására vonatkozik. Az extra lépésben nagyobb lesz a kockázat, hogy csökkentse a regresszívség potenciális lehetőségeit. A minőségi frissítésekben nem lehet törést módosítani, és a nagyobb változás biztosítja, hogy teljes legyen ez a cél.
- **Láthatóság** – e-mailben és Lifecycle Services (LCS) szolgáltatáson keresztül küldjük az értesítéseket a közelgő proaktív minőségi frissítésekről. Ezen kívül a támogatási csoportok és az események érdeklődői láthatóvá lesznek abban, hogy hol vannak proaktív módon telepítve a minőségi frissítések.
- **Verzió tartaléka** – a járatozás a proaktív minőségi frissítés minden változásának csoportosításére használható. Ha egy proaktív telepítés után tartalékra van szükség, akkor az a repülőrendszeren keresztül is meg lehet tenni.
- **Üzenetkészlet szinkronizálásának megnevezése** – a vevők kevesebb, mint 20 százaléka rendelkezik több mezővel, és egy olyan mező van telepítve, amelyben a verzió megfelel a termelésnek, és így segít a hibaelhárításban. Ha egy vevő a termelésnél újabb verziót használ tesztre, akkor az abox az újabb verzióra vonatkozó minőségi frissítéseket fogja kapni.

## <a name="what-is-the-rollout-roadmap-for-quality-updates"></a>Milyen okkal történik az összesítés javítása a minőségi frissítésekhez?

Az Azure nyilvános felhőt igénybe vevő ügyfeleknél várhatóan szeptember vagy október végén kezdődik a proaktív minőségi frissítések elosztása az üzenetkészlet környezetekben. A próbakörnyezet abban az időpontban elindul a proaktív frissítés telepítésében is. Szeptemberben egy értesítést kap a vevő, amely tájékoztatja őket a környezetük várható ütemezésről. A proaktív, frissített elosztási folyamat alóli kivételek csak az FDA által szabályozott vevők számára lesznek engedélyezve. Még mindig azon dolgozunk, hogy hogyan fogják kezelni a szabályozott környezeteket és az állami felhő vevőket.

A következő hat hónap során fokozatosan növelni kell az olyan környezetek százalékát, amelyek proaktív frissítéseket kapnak, amíg minden erre a célra kijelölt környezetben nem szerepel a frissítés, illetve amíg az összes erre a célra kijelölt környezetben nem haladunk előre a termelési környezet frissítése során. Az időszak során figyelni kell, hogy a telepítési folyamat problémamentes legyen, és újra megszinkonláljuk a nem romboló rakományok célkitűzését.

Mivel a vevők rendszeresen kisebb rakományokat kapnak, arra számítunk, hogy az aktuális helyzetben egyszerűbb lesz a folyamat. A frissítéstelepítés gyakoriságát korrigáljuk, mivel bemutatja a folyamat megszakítás nélküli futtatásának a lehetőségeként. Ez a folyamat már jól működik platformunk Dataverse és alkalmazásaink során, és a szolgáltatás minőségében várható fejlesztéseknek lesz része. Nem tudjuk ugyanezt az lépést előrelépni a pénzügyi és az üzemeltetési pályázatokban.

## <a name="when-will-quality-updates-start-for-production-environments"></a>Mikor indulnak el a minőségi frissítések az éles környezetekben?
Jelenleg a minőségfrissítések csak a mezőket célként célják. A termelési környezetek frissítése 2022 novembere után kezdődik.

## <a name="what-is-the-schedule-for-sandbox-quality-updates"></a>Milyen ütemezést kell ütemezni a minőségi frissítésekre?
További tájékoztatás az egyes régiók sötét óráiról: [Mi a proaktív minőségi frissítések ütemezése](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#what-is-the-schedule-for-proactive-quality-updates)?

## <a name="how-are-the-dark-hours-handled-for-customers-that-have-one-finance-and-operations-apps-instance-but-are-active-in-multiple-time-zones"></a>Hogyan kell kezelni a sötét órákat az olyan vevők esetében, akiknél egy pénzügyi és műveleti alkalmazáspéldány van, de több időzónában aktívak? 
Nincsenek speciális ütemezések azon a sötét órákon kívül, ahol létezik egy pénzügyi és műveletalkalmazás-példány, [mivel úgy tervezjük, hogy az nZDT-t minimálisan megszakító módon frissítik a minőségi frissítéseket](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#what-does-near-zero-downtime-maintenance-mean).

## <a name="how-will-microsoft-ensure-the-quality-of-these-updates"></a>Hogyan fogja biztosítani a Microsoft ezeknek a frissítéseknek a minőségét?
A Microsoft annak érdekében, hogy a kiadási prognózis elég hatékony legyen ahhoz, hogy kis rakományokat szállítson, hogy az ellenőrzési költség alacsony legyen. A minőségfrissítések minden javítása egy biztonságos és megbízható telepítési folyamaton megy keresztül, amely javítja a minőség és a megbízhatóságot, és csökkenti a vevők hatását. A telepítés először abox környezetek, majd a termelés szakaszaiban történik. Az szakaszos telepítések lehetővé teszik a megfelelő figyelés számára annak megállapítását, hogy a további telepítések biztonságosak-e. Leállítjuk az összesítést, ha problémákat észlelnek az egyes telepített vevőcsoportokkal, és biztosítjuk, hogy az összesítés minden lépése elegendő időt biztosít a problémák felületének kiláttatásához. Minden közelgő minőségi frissítésnél a nyilvános dokumentációk és e-mail üzenetek frissítései révén láthatóvá tudjuk tenni az ütemezést, így a vevők előre tervezhetnek.

## <a name="can-customers-delay-reschedule-or-pause-a-quality-update"></a>A vevők elhalaszthat, újraütemezhet vagy felfüggeszthet egy minőségfrissítést?
Nem. A minőségfrissítések fő célja, hogy garantálják a biztonságot, az adatvédelemet, a megbízhatóságot, az elérhetőségt és a teljesítményt, és folyamatos fejlesztéseket eredményeznek a vevői számára. A frissítés késleltetése vagy szüneteltetása kockába fogja kockán a biztonságot, az elérhetőségt és a megbízhatóságot.

## <a name="how-can-one-know-the-set-of-changes-that-went-into-a-quality-update-payload"></a>Honnan lehet tudni a minőségfrissítés rakományába bement módosítások halmazát?
Az LCS Környezeti részletek lapján található minőségi frissítésben az összes tudásbáziscikket megnyitva navigálhet a **Minőség** frissítése szakaszra **.** 

## <a name="what-is-the-process-if-a-critical-issue-is-found-after-a-quality-update"></a>Mi a folyamat, ha kritikus probléma van a minőségi frissítés után?
A kritikus probléma vagy regressáció olyan esemény, amely jellemzően több vevőnek csökken a tapasztalata egy vagy több szolgáltatásunk esetén. Ezek a problémák váratlan leállást okozhatnak, például elérhetetlenséget, teljesítménycsökkenést és a szolgáltatáskezelésbe való beavatkozást. Ha az ilyen regresszív problémák széles körben befolyásolják a vevőket, akkor leállítjuk a minőségi frissítés kigörgetését addig, amíg nem lehet kommunikálni és kijavítani a problémát. Általában a következő minőségi frissítéshez szükséges javítás szükséges a kigörgetés folytatásához.

Ha egyetlen ügyfélkörnyezetet érint, lépjen kapcsolatba a Microsoft terméktámogatással, hogy nyisson meg egy jegyet. Az indoklás alapján a probléma enyhítésáig leállítjuk a minőségi frissítés minden más környezetbe való kiadását.

## <a name="can-customers-still-manually-apply-hotfix-updates-from-lcs"></a>A vevők továbbra is alkalmazhatják manuálisan az LCS-ről származó gyorsjavítás-frissítéseket?
Igen. A gyorsjavítások munkakörnyezetének folyamatos biztosítása érdekében a gyorsjavítások frissítései továbbra is alkalmazhatók az LCS-környezetekben lévő ügyfélkörnyezetre. Fontos azonban megjegyezni, hogy a minőségi frissítés részeként telepített gyorsjavítások a frissítés telepítése előtt végigmennek a szokásos SDP-frissítésen. Ez csökkenti a magasabb minőségből következő regresszívség kockázatát. Javasoljuk, hogy a nagyobb megbízhatóság érdekében manuálisan alkalmazza a minőségi frissítéseket.

## <a name="can-customers-self-install-a-quality-update-build-by-themselves-ahead-of-the-schedule"></a>Az ügyfelek saját maguk telepíthetik a minőségi frissítéseket az ütemezésnél előre?
Igen. A minőségi frissítéseket proaktív módon telepítheti. A Microsoft kihagyja a frissítést, ha a környezet aktuális buildverziója megegyezik vagy magasabb, mint a kérdéses minőségfrissítés.

## <a name="if-an-environment-has-an-upcoming-scheduled-monthly-service-update-within-a-week-will-it-still-receive-quality-updates"></a>Ha egy környezetben várható havi szolgáltatási frissítés van egy héten belül, akkor is fognak minőségi frissítéseket kapni?
- A minőségi frissítések nem alkalmazhatók, ha egy héten belül ütemezve van egy függőben lévő szolgáltatásfrissítés, amelytől a minőségi frissítés ütemezése bekövetkezik.
- Ha abox környezetben ugyanaz vagy magasabb a buildverzió, mint a függőben lévő minőségi frissítés, akkor a program kihagyja.
- Ha egy termelési környezetnek ugyanaz vagy magasabb a buildverziója, mint a függő minőségi frissítésnek, akkor a rendszer kihagyja.
- Ha a minőségi frissítés vagy a termelés manuális frissítése miatt a műhely ugyanaz vagy magasabb buildverzióval rendelkezik, a termelés akkor is a havi szolgáltatási frissítés ütemezett verzióját fogja kapni. Ha nem szeretné, hogy az ütemezett termelési környezet frissítve legyen a szolgáltatásfrissítési verzióra, szüneteltetheti a szolgáltatás frissítését az LCS-ről. 
- Javasoljuk, hogy a legújabb minőségi frissítéssel tesztelje a várható szolgáltatásfrissítések változásait a jobb stabilság és az eredmények érdekében.

## <a name="can-an-environment-be-brought-back-to-its-previous-state-if-there-are-issues-after-a-quality-update-is-applied"></a>Vissza lehet hozni a környezetet az előző állapotba, ha problémák vannak a minőségi frissítés alkalmazása után?
A minőségi frissítés alkalmazása után semmilyen körülmények között nem kerül sor visszaállításra. Csak a problémák enyhítése érdekében vannak előre javító lehetőségek.

## <a name="what-about-fda-regulation-and-gpx"></a>Mi a helyzet az FDA szabályozásával és a FDA-szabályozásokkal?
Az FDA-ellenőrzésen és szabályozáson áteső vevőknek szóló tervek még mindig nem teljesek. Várható további frissítések ebben a területben. Jelenleg minden ilyen vevő mentesül a minőségi frissítések alól.

## <a name="what-versions-of-service-updates-are-supported-for-these-quality-updates"></a>A szolgáltatásfrissítések melyik verziói támogatottak ezekhez a minőségi frissítésekhez?
A vevőnél alacsonyabb verziójú N-2 nem fognak minőségi frissítéseket kapni. 

## <a name="finance-and-operations-apps-deployments-with-retail-components-typically-require-additional-work-in-addition-to-having-to-redeploy-mpos-how-will-these-quality-updates-impact-the-retailsdk"></a>A kiskereskedelmi összetevőkből telepített pénzügyi és műveleti alkalmazások általában további munkát igényelnek az MPOS újratelepítésén kívül. Hogyan lesznek hatással ezek a minőségi frissítések a RetailSDK szolgáltatásra? 
Mivel a gyorsjavítások jellege nem változik meg a minőségi frissítések rakományában, jelenleg nem várható további hatás a kiskereskedelmi összetevőkre nézve.

## <a name="is-there-any-impact-to-cloud-hosted-environments-che-"></a>Van hatása a felhőben tárolt környezetre (CHE)? ? 
Nem.

## <a name="are-there-any-integration-issues-with-microsoft-dataverse"></a>Vannak integrációs problémák?Microsoft Dataverse 
Nem.

