---
title: Engedmények megjelenítése a pénztárban
description: Ez a témakör azt mutatja be, hogy a Microsoft Dynamics 365 Commerce hogyan segíti az értékesítési munkatársak számára megismerni a promóciókkal kapcsolatos tudnivalókat, valamint azt, hogy hogyan használhatók fel a keresztértékesítéshez és a felülértékesítéshez.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 07/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-Commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Commerce
ms.author: asharchw
ms.search.validFrom: 2020-02-28
ms.dyn365.ops.version: Application update 10.0.10
ms.openlocfilehash: 118e7689e5d37aae18d3823b957301ddfa89369a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982641"
---
# <a name="show-discounts-in-pos"></a>Engedmények megjelenítése a pénztárban

[!include [banner](includes/banner.md)]

A promóciók fontos szerepet játszanak a vásárlási döntéseket meghozó vevők motivációjában. Például az ünnepek a kereskedők számára a legnagyobb számú értékesítést hozhatják, mivel az egész kiskereskedelmi piac csábító promóciókkal és kedvezményekkel van elárasztva. Ha az üzlet munkatársai ismerik a rendelkezésre álló promóciókat, és megértik azokat, akkor ezeket a promóciókat egyszerűen ki tudják használni a keresztértékesítéshez és felülértékesítéshez. Ez a témakör azt mutatja be, hogy a Microsoft Dynamics 365 Commerce hogyan segíti az értékesítési munkatársak számára megismerni a promóciókkal kapcsolatos tudnivalókat, valamint azt, hogy hogyan használhatók fel a keresztértékesítéshez és a felülértékesítéshez.

## <a name="learn-about-store-discounts"></a>További információ az üzleti engedményekről

A Commerce egy "„Összes engedmény megtekintése” nevű műveletet tartalmaz. Ez a művelet az üzletben éppen elérhető összes engedményt jeleníti meg. Az „Összes engedmény megtekintése” művelet leképezhető a pénztár (POS) egyik gombjára, és ezt a gombot fel lehet venni **Üdvözlő** oldalra vagy a **Tranzakció** lapra. A következő ábra a megnyitott **Összes kedvezmény** oldalt szemlélteti.

![Minden kedvezmény oldal](./media/View_all_discounts.png "Minden kedvezmény oldal")

A kedvezmények megjelenítéséhez a rendszer minden olyan engedményt megkeres, amely megfelel a következő feltételek valamelyikének:

- Az engedmény árcsoportja megfelel az üzlet árcsoportjának.
- A kedvezményhez tartozó árcsoport hozzá van rendelve egy fiók- vagy hűségprogramhoz.
- Az engedmény árcsoportja az üzlethez társított egy katalógushoz van rendelve.

A **Minden engedmény** lap csak néhány utalvány alapú engedményt mutat, mivel a kiskereskedők általában több ezer kupont és azokhoz kapcsolódó engedményt hoznak létre az egyedi vevők számára, és ez a lap nem a vevőspecifikus engedmények megjelenítésére szolgál. A kuponalapú kedvezmények csak akkor jelennek meg, ha minden egyes kuponfejlécében be van kapcsolva az **Alkalmazás kuponkód nélkül** beállítás. Ebben az esetben a pénztárosok a kuponkód vagy a vonalkód megadása vagy beolvasása nélkül is alkalmazhatják a kupont.

Ha az **Alkalmazás kuponkód nélkül** beállítás engedélyezve van, akkor a különböző forgatókönyvek válnak elérhetővé. Például a pénztárosok további engedményeket adhatnak a vevők számára a vevői békéltetési célokra vagy a termék meghibásodása miatt. A kinyomtatott kuponkódokat vagy vonalkódokat nem kell kiosztani a pénztárosoknak. Helyette a pénztárosok a **Kupon alkalmazása** gombot használhatják. A program ezt követően automatikusan alkalmazza a kupont a tranzakcióra. Ha egy kuponfejlécéhez több kupon is tartozik, akkor a rendszer automatikusan kiválasztja a tranzakció első aktív kuponját.

A **Minden engedmény** oldalon az értékesítő kulcsszavak szerint is kereshet engedményeket. A kulcsszavas keresés az engedmény nevét és az engedmény leírását tartalmazó mezőkben keres. Az értékesítők az engedményeket aszerint is szűrhetik,, hogy az engedményhez szükséges-e kuponkód.

## <a name="cross-sell-and-upsell-by-using-discounts"></a>Keresztértékesítés és felülértékesítés engedmények segítségével

A többsoros engedmények, például mennyiségi kedvezmények, kombinációs engedmények és küszöbérték-kedvezmények kiváló módszerek arra, hogy ösztönözzék a vevőket, hogy több terméket vegyenek vásároljanak a nagyobb engedményekhez. Éppen ezért növelik a vevők kosarát és a kiskereskedelmi bevételek mértékét is. Ezek az engedmények közzétehetők e-commerce weboldalakon, a közösségi médiában és a bolt szalaghirdetésein.

Ha azonban ezek a nyilvános módszerek használva is vannak előfordulhat, hogy a vevők nem használják ki a lehetőséget, hogy igénybe vegyék a promóciókat. Annak érdekében, hogy az értékesítők egyszerűen megtanulhassák a kiválasztott sorra vagy akár a teljes kosárra vonatkozó promóciókat, a kiskereskedők az **„Elérhető engedmények megtekintése”** műveletre vonatkozó gombot a **Tranzakció** oldal gombrács mezőjébe felvehetik. Ennek eredményelént egy értékesítési munkatárs kiválaszthat egy tranzakciósort, majd a gombra kattintva megjelenítheti a kiválasztott sorhoz rendelkezésre álló összes engedményt. Az értékesítési munkatárs másik lapot is kiválaszthat, amelyen láthatók a teljes tranzakcióra vonatkozó kedvezmények. Fontos megjegyezni, hogy az **Elérhető engedmények megtekintése** lehetőség nem jeleníti meg az értékesítési sorban már alkalmazott engedményeket, mivel az engedmény adatai már meg vannak jelenítve az értékesítési sorban. Ennek a forgatókönyvnek az a célja, hogy csak a még nem alkalmazott engedmények jelenjenek meg. Ez alól kivételek az „Alkalmazás kuponkód nélkülként” megjelölt utalvány alapján alkalmazott engedmények. Így az értékesítési társítás egyszerűen eltávolíthatja az általuk alkalmazott kupont.

Az **Összes engedmény** lap csak olyan engedményeket mutat be, amelyek nem ütköznek az alkalmazott kedvezményekkel. Ez a viselkedés segít abban, hogy ha egy értékesítési munkatárs értesíti a vevőt a kedvezményről, és a vevő a szükséges lépést hajtja végre (például a vevő még egy cikket vásárol, hogy 10% kedvezményt kapjon), akkor az engedmény alkalmazva legyen a tranzakcióra. A kuponalapú kedvezmények csak akkor jelennek meg, ha az **Alkalmazás kuponkód nélkül** beállítás be van kapcsolva.

Olyan egyszerű esetben, amikor az összes engedménynek ugyanaz a prioritása, és az engedmény párhuzamosságmódja **Kombinált** és az engedmény párhuzamosságága vezérlőjének beállítása **Legjobb ár és kombináció a prioritáson belül, ne legyen kombinálás prioritások között** a **Minden kedvezmény** oldal megjeleníti a termékhez elérhető összes kedvezményt, mivel az összes kedvezmény kombinálva van, és nem ütköznek egymással.

A következő illusztrációk mutatják be azt a logikát, amely meghatározza, hogy mely engedmények jelenjenek meg a speciális helyzetekben, például egy olyan esetben, amikor az engedmény párhuzamossági módja **Legjobb ár** vagy **Kizárólagos**, és kettő vagy több prioritás van használatban. Ezekben az esetekben a megjelenített kedvezmények tovább vannak befolyásolva attól függően, hogy az engedmény-párhuzamossági vezérlő beállítása **Legjobb ár és kombináció a prioritáson belül, ne legyen kombinálás prioritások között** vagy **Csak a legjobb ár prioritáson belül, mindig legyen párhuzamosság a prioritások között**.

A következő ábra bemutatja azt a logikát, amely akkor használatos, ha az engedmény vezérlőjének beállítása **Legjobb ár és kombináció a prioritáson belül, ne legyen kombinálás prioritások között**.

![A Legjobb ár és kombináció a prioritáson belül, ne legyen kombinálás prioritások között logikája](./media/Model_1.png "A Legjobb ár és kombináció a prioritáson belül, ne legyen kombinálás prioritások között logikája").

A következő ábra bemutatja azt a logikát, amely akkor használatos, ha az engedmény vezérlőjének beállítása **Csak a legjobb ár prioritáson belül, mindig legyen kombinálás prioritások között**.

![A Csak a legjobb ár prioritáson belül, mindig legyen kombinálás prioritások között logikája](./media/Model_2.png "A Csak a legjobb ár prioritáson belül, mindig legyen kombinálás prioritások között logikája").
