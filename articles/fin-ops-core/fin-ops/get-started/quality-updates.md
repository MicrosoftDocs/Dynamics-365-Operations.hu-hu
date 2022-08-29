---
title: Proaktív minőségi frissítések
description: Ez a cikk a minőségi frissítések proaktív teljesítésével kapcsolatban tartalmaz tájékoztatást.
author: rashmansur
ms.date: 08/23/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form: ''
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 9d81cb15e9a127e7bea7ad9b5e0f50a1ee543f71
ms.sourcegitcommit: 78e85ad49634cd31459fdb7325cb273352bf1501
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/23/2022
ms.locfileid: "9338136"
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
- **Üzenetkészlet szinkronizálásának megnevezése** – a vevők kevesebb, mint 20 százaléka rendelkezik több mezővel, és egy olyan mező van telepítve, amelyben a verzió megfelel a termelésnek, és így segít a hibaelhárításban. A közeli jövőben lehetőség van arra, hogy a vevők olyanbox környezetet adjanak meg, amely nem a többi mezővel együtt kapják meg a proaktív minőségfrissítést, hanem később, a termelési környezettel együtt kapják meg. Ne feledje, hogy ha egy vevő üzenetdobozt használ a termelésnél újabb verzió tesztelésére, akkor az abox az újabb verzióra vonatkozó minőségi frissítéseket fogja kapni.
- 
## <a name="when-will-proactive-quality-updates-start"></a>Mikor indítja el a proaktív minőségi frissítéseket?

Az Azure nyilvános felhőt igénybe vevő ügyfeleknél várhatóan szeptember vagy október végén kezdődik a proaktív minőségi frissítések elosztása az üzenetkészlet környezetekben. A próbakörnyezet abban az időpontban elindul a proaktív frissítés telepítésében is. Szeptemberben egy értesítést kap a vevő, amely tájékoztatja őket a környezetük várható ütemezésről. A proaktív, frissített elosztási folyamat alóli kivételek csak az FDA által szabályozott vevők számára lesznek engedélyezve. Még mindig azon dolgozunk, hogy hogyan fogják kezelni a szabályozott környezeteket és az állami felhő vevőket.

A következő hat hónap során fokozatosan növelni kell az olyan környezetek százalékát, amelyek proaktív frissítéseket kapnak, amíg minden erre a célra kijelölt környezetben nem szerepel a frissítés, illetve amíg az összes erre a célra kijelölt környezetben nem haladunk előre a termelési környezet frissítése során. Az időszak során figyelni kell, hogy a telepítési folyamat problémamentes legyen, és újra megszinkonláljuk a nem romboló rakományok célkitűzését.

Mivel a vevők rendszeresen kisebb rakományokat kapnak, arra számítunk, hogy az aktuális helyzetben egyszerűbb lesz a folyamat. A frissítéstelepítés gyakoriságát korrigáljuk, mivel bemutatja a folyamat megszakítás nélküli futtatásának a lehetőségeként. Ez a folyamat már jól működik platformunk Dataverse és alkalmazásaink során, és a szolgáltatás minőségében várható fejlesztéseknek lesz része. Nem tudjuk ugyanezt az lépést előrelépni a pénzügyi és az üzemeltetési pályázatokban.
