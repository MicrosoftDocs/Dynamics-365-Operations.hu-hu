---
title: Fizetőeszköz-alapú kedvezmények
description: Ez a témakör a fizetőeszköz-alapú engedményekkel kapcsolatos funkciókat írja le, amelyek segítségével a kiskereskedők a következőben meghatározott fizetőeszköz-típusokhoz konfigurálják az engedményeket:Microsoft Dynamics 365 Commerce
author: bebeale
ms.date: 08/19/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2018-10-31
ms.openlocfilehash: b11145c0c12f973b437ebf87921a5686d217d327
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473780"
---
# <a name="tender-based-discount"></a>Fizetőeszköz-alapú engedmény

[!include [banner](includes/banner.md)]

Ez a témakör a fizetőeszköz-alapú engedményekkel kapcsolatos funkciókat írja le, amelyek segítségével a kiskereskedők a következőben meghatározott fizetőeszköz-típusokhoz konfigurálják az engedményeket:Microsoft Dynamics 365 Commerce

Elterjedt gyakorlat a kiskereskedők között a saját márkás hitelkártyák kiadása. A kiskereskedők számára ez előnyös, mert a bankoktól előnyös díjakat kapnak. Ezenkívül mivel ezek a hitelkártyák arra ösztönözhetik a vevőket, hogy gyakrabban keressék fel azüzletet, javítják a kiskereskedő forgalmát. Ennélfogva a kiskereskedőknek ösztönzik az ügyfeleket, hogy saját márkás hitelkártyáikat használják. Ennek a célnak a elérése érdekében gyakran további kedvezményeket biztosítanak az ezt a hitelkártyát használó vevők számára.

A sajátmárkás hitelkártyát nem alkalmazó kiskereskedők emellett a vevők számára ajánlott egyéb fizetőeszköz-típusokkal , például készpénz, ajándékutalvány vagy hűségpontok használatával történő fizetésre is ösztönözni szeretnék a vevőket. Ily módon segít csökkenteni a hitelkártyadíjakhoz kapcsolódó költségeket. Ennélfogva a kiskereskedők kedvezményeket biztosíthatnak azoknak a vevőknek, akik ezeket az alternatív fizetőeszköz-típusokat használják.

## <a name="tender-based-discount"></a>Fizetőeszköz-alapú engedmény

A Commerce rendszer támogatja a *fizetőeszköz-alapú* engedményt, amely lehetővé teszi a kiskereskedők számára, hogy a tranzakcióra alkalmazott engedmény százalékos hányadát alkalmazzák, ha a tranzakció végösszege meghaladja a megadott összeget, és a vevő a preferált fizetési típus használatával fizet. A fizetőeszköz-alapú engedmény többszintű, így különböző engedményszázalékok társíthatóak a különböző összeghatárok között. A vevő eldöntheti, hogy részleges vagy teljes kifizetést, és az árképzési motor határozza meg a megfelelő engedmény összegét. A fizetőeszköz-alapú engedmény mindig az értékesítési sorok adózás előtti összegében van megadva.

A fizetőeszköz-alapú engedmény csak olyan értékesítési sorokra alkalmazható, ahol az árak nincsenek zárolva, és arányosan oszlik el a minősített sorok között. Ha új értékesítési sorokat adnak hozzá egy rendeléshez, a fizetőeszköz-alapú engedmény csak az új értékesítési sorokra vonatkozik a fizetés során. Felvételre vagy kiszállításra vevői rendelés esetén a fizetőeszköz-alapú engedmény csak a letét összegre vonatkozik. Miután a rendelést leadták, a teljesítés során, a program zárolja az értékesítési sorok árait. Nem alkalmaz fizetőeszköz-alapú engedményt a rendszer minden olyan egyenlegre, amely a felvétel során kerül kifizetésre, vagy engedélyezve van a szállítás során. A fizetőeszköz-alapú kedvezmény csak akkor alkalmazható a vevői rendelés teljes összegére, ha a kiskereskedő a teljes összeget előlegként beszedi a rendelés leadásakor.

A fizetőeszköz-alapú engedmények nem versenyzők cikk alapú engedményekkel, például egyszerű engedményekkel, mennyiségi engedményekkel, küszöbérték-engedményekkel, kombinációs engedményekkel és kézi engedményekkel. A fizetőeszköz-alapú engedményeket a rendszer mindig a cikk alapú engedményekhez összetételt ad. Így még ha egy cikkre kizárólagos engedmény is vonatkozik, a fizetőeszköz-alapú engedményt akkor is lehet alkalmazni az kizárólagos engedményen felül. Hasonlóképpen, ha küszöbértéket alapú kedvezményt alkalmaznak, és a fizetőeszköz-alapú kedvezmény csökkenti a végösszeget az értékhatár alá akkor a program a tranzakcióra alkalmazza az értékhatár alapú kedvezményt

Bár a fizetőeszköz-alapú engedmények csökkentik a tranzakció részösszegét, a tranzakcióra alkalmazott automatikus költségek nincsenek hatással. Ha például $5 a szállítási költségek számítása $5, mivel a részösszeg több volt, mint $100, és a fizetőeszköz-alapú engedmény csökkenti az összeget, és így kevesebb, mint $100, a szállítási költségek $5 maradnak a rendeléshez.

A fizetőeszköz-alapú kedvezmény jelenleg két fizetési típusra korlátozódik: a hitelkártyákra és a készpénzre. Ha egy fizetési típushoz több fizetőeszköz-alapú engedmény van beállítva, akkor csak a legjobb fizetőeszköz-alapú engedményt alkalmazza a rendszer.

## <a name="pos-user-experience"></a>Pénztári felhasználói élmény

Ha a készpénzhez fizetőeszköz-alapú engedmény van beállítva, és a pénztáros a pénztárnál kiválasztja **a** Készpénzes fizetés gombot a készpénzes és áthozott tranzakciók stb. kiválasztásához, akkor a program automatikusan alkalmazza a fizetőeszköz-alapú engedményt a tranzakcióra. Ezt követően a csökkentett összeg jelenik meg egyenlegként. Ha azonban a pénztáros kiválasztja a **Vissza** gombot a fizetés képernyőjén, akkor a program eltávolítja az engedményt, és az eredeti összeg jelenik meg a tranzakció képernyőjén. A program eltávolítja a fizetőeszköz-alapú kedvezményeket, ha a fizetési sor érvénytelenítve lett.

Hitelkártyás fizetések esetén a kiskereskedők beállíthatják a fizetőeszköz-alapú engedményt egy vagy több hitelkártyára. A rendszer azonban nem tudja ellenőrizni a használt hitelkártyát, hacsak a kártya nincs engedélyezve. Ha az engedményt az engedélyezést követően alkalmazták, akkor a kifizetés engedélyezése nagyobb összegre szól, de a fizetés levonása a kisebb összegre fog vonatkozni. A helyzet megakadályozása érdekében, ha a vevő hitelkártyával fizet, a pénztárostól egy párbeszédpanel jelenik meg, amely felsorolja azokat a preferált hitelkártyákat, amelyek további kedvezményt adnak a vevőnek. A pénztáros ezután megkérdezi, hogy a vevő szeretné-e a preferált kártyák egyikét használni a további engedmények megszerzéséhez. Ha a pénztáros a preferált kártyát választja, a rendszer a fizetőeszköz-alapú engedményt alkalmazza a tranzakcióra, és a csökkentett összeg megjelenik a fizetési képernyőn. A rendszer az engedélyezést a csökkentett összeghez rendeli. Ha a vevő olyan kártyát helyez be, amely eltér a pénztáros által kiválasztott kártyától, akkor egy hibaüzenet jelenik meg, és érvénytelenítve van az engedélyezés.

## <a name="call-center-user-experience"></a>Hívásközpont felhasználói élmény

Ha egy hívásközponti felhasználó **a** Hívásközponti rendelés során a Kész lehetőséget választja, **megjelenik** az Összegek képernyő. Először a képernyőn szereplő összegek nem tartalmazzák a fizetőeszköz-alapú engedményeket, mivel a fizetési mód még nincs kiválasztva. Ha a felhasználó a **Fizetés hozzáadása** képernyőn kiválasztja azt a fizetési módot, amelyre a fizetőeszköz-alapú engedmény be van állítva, akkor a program automatikusan helyesbíti a kifizetési összeget, hogy az tükrözze a kedvezménes összeget. A hívásközpont vevőihez hasonlóan a hívásközponti vevő eldöntheti, hogy a teljes kifizetést vagy csak egy részleges kifizetést fizeti ki. A kifizetett összeg alapján a program alkalmazza a fizetőeszköz-alapú engedményt az értékesítési rendelésre.

> [!NOTE]
> A kártya érvényesítése nem történik meg a hívásközponti rendelések esetében. Ha például a hívásközponti felhasználó kijelöli a Visa hitelkártyát, de a vevő a MasterCard programot használja, akkor a rendszer továbbra is alkalmazza a kedvezményt.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
