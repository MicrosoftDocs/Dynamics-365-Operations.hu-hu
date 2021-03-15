---
title: Fizetőeszköz-alapú kedvezmények
description: Ez a témakör áttekintést nyújt azokról a funkciókról, amelyekkel a kiskereskedők meghatározott fizetőeszköz-típusokra vonatkozóan engedményeket konfigurálnak.
author: bebeale
manager: AnnBe
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderDiscount
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: Version 10.0.7
ms.openlocfilehash: 9f6747ff9d68c29612346254928e869d6d34d433
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962935"
---
# <a name="tender-based-discounts"></a>Fizetőeszköz-alapú kedvezmények

[!include [banner](includes/banner.md)]


Elterjedt gyakorlat a kiskereskedők között a saját márkás hitelkártyák kiadása. A kiskereskedők számára ez előnyös, mert a bankoktól előnyös díjakat kapnak. Ezenkívül mivel ezek a hitelkártyák arra ösztönözhetik a vevőket, hogy gyakrabban keressék fel azüzletet, javítják a kiskereskedő forgalmát. Ennélfogva a kiskereskedőknek ösztönzik az ügyfeleket, hogy saját márkás hitelkártyáikat használják. Ennek a célnak a elérése érdekében gyakran további kedvezményeket biztosítanak az ezt a hitelkártyát használó vevők számára.

A sajátmárkás hitelkártyát nem alkalmazó kiskereskedők emellett a vevők számára ajánlott egyéb fizetőeszköz-típusokkal , például készpénz, ajándékutalvány vagy hűségpontok használatával történő fizetésre is ösztönözni szeretnék a vevőket. Ily módon segít csökkenteni a hitelkártyadíjakhoz kapcsolódó költségeket. Ennélfogva a kiskereskedők kedvezményeket biztosíthatnak azoknak a vevőknek, akik ezeket az alternatív fizetőeszköz-típusokat használják.

A Microsoft Dynamics 365 Commerce alkalmazásban a kiskereskedők a minősített sorokra alkalmazott engedményszázalékot állíthatnak be, ha a vevő a preferált fizetőeszköz-típussal fizet. A vevő eldöntheti, hogy részleges vagy teljes fizetést hajt-e végre, és a Commerce határozza meg a megfelelő engedmény összegét. Ne feledje, hogy a kedvezmény mindig a jogosult cikkek nettó összegére vonatkozik.

A fizetőeszköz-alapú engedmények nem versengenek a cikkalapú engedményekkel, például az időszakos vagy a manuális engedményekkel. Ezek a cikkek mindig a cikkengedményekre vannak alkalmazva. Ennek megfelelően még akkor is, ha a termékre egy exkluzív időszakos kedvezményt alkalmaznak, a fizetőeszköz-alapú engedményt a program továbbra is a az exkluzív időszaki engedményen túl alkalmazza. Hasonlóképpen, ha küszöbértéket alapú kedvezményt alkalmaznak, és a fizetőeszköz-alapú kedvezmény csökkenti a végösszeget az értékhatár alá akkor a program a tranzakcióra alkalmazza az értékhatár alapú kedvezményt

Bár a fizetőeszköz-alapú engedmények csökkentik a tranzakció részösszegét, a tranzakcióra alkalmazott automatikus díjakat nem érintik. Ha például a szállítási költség számított díja 5 dollár, mert a részösszeg több mint 100 dollár, és a fizetőeszköz-alapú kedvezmény úgy csökkenti az összeget, hogy az 100 dollárnál kisebb legyen, a szállítási költség továbbra is 5 dollár a rendeléshez.


> [!NOTE]
> A tender-alapú kedvezmények arányosan oszlanak el a jogosult értékesítési sorokra, és csökkentik az egyes sorok nettó összegét. Ha több fizetőeszköz-alapú engedmény van beállítva egy fizetőeszköz-típushoz (például készpénz), akkor csak a legkedvezőbb fizetőeszköz-alapú kedvezményt alkalmazza a program.

A fizetőeszköz-alapú kedvezmények csak olyan értékesítési sorokra alkalmazhatók, amelyeknél az árak nem zároltak. Ha új értékesítési sorokat rendel hozzá egy rendeléshez, akkor a program a fizetőeszköz-alapú engedményt csak a fizetés során alkalmazza az új értékesítési sorokhoz. A felvételi vagy kiszállítási vevői rendelés leadásakor a fizetőeszköz-alapú engedmény csak a letéti összegre vonatkozik. Miután a rendelést leadták, a teljesítés során, a program zárolja az értékesítési sorok árait. Ennélfogva nem lesz alkalmazva fizetőeszköz-alapú engedmény minden olyan egyenlegre, amelyet a felvételkor fizettek ki, vagy a szállítás során engedélyeztek. A fizetőeszköz-alapú kedvezmény csak akkor alkalmazható a vevői rendelés teljes összegére, ha a kiskereskedő a teljes összeget előlegként beszedi a rendelés leadásakor.

> [!IMPORTANT]
> A Commerce alkalmazásban, a fizetőeszköz-alapú kedvezmények jelenleg két fizetési típusra vannak korlátozva: hitelkártyák és készpénz.

## <a name="pos-user-experience"></a>Pénztári felhasználói élmény

Ha a fizetőeszköz-alapú engedmények be vannak állítva készpénzhez, és a pénztárnál (POS) a pénztáros kiválasztja a fizetés készpénzben művelethez hozzárendelt gombot, akkor a program automatikusan alkalmazza a fizetőeszköz-alapú engedményt a tranzakcióra. Ezt követően a csökkentett összeg jelenik meg egyenlegként. Ha azonban a pénztáros kiválasztja a **Vissza** gombot a fizetés képernyőjén, akkor a program eltávolítja az engedményt, és az eredeti összeg jelenik meg a tranzakció képernyőjén. A program eltávolítja a fizetőeszköz-alapú kedvezményeket, ha a fizetési sor érvénytelenítve lett.

Kártyás fizetések esetén a kiskereskedők egy vagy több típusú hitelkártyához állíthatják be a fizetőeszköz-alapú engedményt. A rendszer azonban nem tudja ellenőrizni a használt hitelkártyát, hacsak a kártya nincs engedélyezve. Ha az engedményt az engedélyezést követően alkalmazták, akkor a kifizetés engedélyezése nagyobb összegre szól, de a fizetés levonása a kisebb összegre fog vonatkozni.

Ha meg szeretné akadályozni ezt a helyzetet, amikor a vevő hitelkártyával fizet, akkor a pénztáros számára párbeszédpanel jelenik meg, amely felsorolja azokat a hitelkártyákat, amelyek a vevő számára további megtakarítást eredményeznek. A pénztáros ezután megkérdezi, hogy a vevő szeretné-e a preferált kártyák egyikét használni a további engedmények megszerzéséhez. Ha a pénztáros preferált kártyát alkalmaz, a program a fizetőeszköz-alapú kedvezményt alkalmazza a tranzakcióra, és a csökkentett összeg megjelenik a fizetési képernyőn. A rendszer az engedélyezést a csökkentett összeghez rendeli. Ha a vevő olyan kártyát helyez be, amely eltér a pénztáros által kiválasztott kártyától, akkor egy hibaüzenet jelenik meg, és érvénytelenítve van az engedélyezés.


## <a name="call-center-user-experience"></a>Hívásközpont felhasználói élmény

Amikor a felhasználó a hívásközponti rendelése során kiválasztja a **Befejezést**, megjelenik a **Végösszeg** képernyő. Először a képernyőn szereplő összegek nem tartalmazzák a fizetőeszköz-alapú engedményeket, mivel a fizetési mód még nincs kiválasztva. Ha a felhasználó a **Fizetés hozzáadása** képernyőn kiválasztja azt a fizetési módot, amelyre a fizetőeszköz-alapú engedmény be van állítva, akkor a program automatikusan helyesbíti a kifizetési összeget, hogy az tükrözze a kedvezménes összeget. A POS rendszer vevőjéhez hasonlóan a hívásközponti ügyfél eldöntheti, hogy kifizeti-e a teljes összeget vagy csak egy részét. A kifizetett összeg alapján a program alkalmazza a fizetőeszköz-alapú engedményt az értékesítési rendelésre.

> [!NOTE]
> A kártya érvényesítése nem történik meg a hívásközponti rendelések esetében. Ha például a hívásközponti felhasználó kijelöli a Visa hitelkártyát, de a vevő a MasterCard programot használja, akkor a rendszer továbbra is alkalmazza a kedvezményt.

## <a name="exclude-items-from-discounts"></a>Cikkek kizárása a kedvezményekből

A kereskedők gyakran úgy döntenek, hogy a kedvezményekből kizárnak néhány terméket, például az új cikkeket vagy a népszerű cikkeket. Előfordulhat azonban, hogy a fizetőeszköz alapú kedvezményeket mégis alkalmazni szeretné. Például egy kiskereskedő konfigurálja a Commerce alkalmazást úgy, hogy nem engedélyezi a cikkalapú engedményeket vagy a manuális engedményeket. Ha azonban a vevő a preferált fizetőeszközzel fizet, akkor a Commerce továbbra is alkalmazza a fizetőeszköz-alapú engedményt. A Commerce ilyen módú beállítása érdekében a kiskereskedőknek a **Termékinformációk kezelése > Termékek > Kiadott termékek** pontra kell lépniük, kiválasztaniuk a cikket, majd a **Commerce** gyorslapon be kell állítaniuk az **Összes engedmény megakadályozása** és **Fizetőeszköz-alapú engedmények megakadályozása** beállításokat **Nem** értékre, a **Kiskereskedelmi engedmények megakadályozása** és a **Manuális engedmények megakadályozása** beállításokat **Igen** értékre.

> [!NOTE]
> Ha az **Összes engedmény megakadályozása** konfiguráció **Igen** értékre van állítva, akkor a termékre nem alkalmazhatnak engedményeket. A program még a fizetőeszköz-alapú engedményeket sem alkalmazza.


[!INCLUDE[footer-include](../includes/footer-banner.md)]