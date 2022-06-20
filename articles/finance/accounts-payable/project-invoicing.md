---
title: 'Projekt számlázása:'
description: Ez a cikk az Idő- és anyagelszámolású projektek, illetve a Rögzített árú projektek projektszámlázásáról nyújt áttekintést. Számlajavaslatokkal (előzetes számlák), számlaellenőrzéssel, részszámlázással, szállítói számlázással és jóváírásokkal kapcsolatos információkat tartalmaz.
author: TaylorVH
ms.date: 07/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjInvoiceCashFlow, ProjInvoiceControl, ProjInvoiceListPage, ProjInvoiceProposalDetail, ProjInvoiceProposalListPage
audience: Application User, IT Pro
ms.reviewer: zezhangzhao
ms.custom: 23111
ms.assetid: 1812d6f2-8b34-4258-8f5f-dcf12281547f
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-07-06
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 4af44127d80c943ed9cebeac21d7e9c8372910f3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861676"
---
# <a name="project-invoicing"></a>Projekt számlázása:

[!include [banner](../includes/banner.md)]

Ez a cikk az Idő- és anyagelszámolású projektek, illetve a Rögzített árú projektek projektszámlázásáról nyújt áttekintést. Számlajavaslatokkal (előzetes számlák), számlaellenőrzéssel, részszámlázással, szállítói számlázással és jóváírásokkal kapcsolatos információkat tartalmaz.

A projekt típusa határozza meg, hogy melyik számlázási eljárást kell alkalmazni. Kizárólag a két külső projekttípus, az Idő- és anyagelszámolású, illetve a Rögzített árú projektek számlázhatók. Az Idő- és anyagelszámolású projektek és a Rögzített árú projektek mindig projektszerződéshez kapcsolódnak.

-   **Rögzített árú projektek** – A vevői számla összege a számlázási ütemezésen alapul. A számlázás egy részszámlázási beállítás szerint történik, amelyet számlázási ütemezésnek is neveznek. A rögzített árú projektekről projektenként vagy projektszerződésenként készíthető számla.
-   **Idő- és anyagelszámolású projektek** – A vevői számla összege a projekteknél megadott tranzakciósorok alapján alakul. A tranzakciók projektenként vagy projektszerződésenként számlázhatók.

Háromféle módon tud idő- és anyagelszámolású projekteket és Rögzített árú projektet társítani számlaprojekthez:

-   **Részszámla készítése** – Az idő- és anyagelszámolású, valamint a Rögzített árú projektekről részszámla is készíthető. A két projekttípus eltérő részszámlázási beállítást tesz szükségessé.
-   **Számla készítése az időszakos szakaszban** – az időszakos szolgáltatásokkal a tranzakciók több projekten keresztül is számlázhatók. Az ismétlési funkciók segítségével áttekintés kapható a számlázandó tranzakciókról.
-   **Jóváírások használata a számlázás során** – Idő és anyagelszámolású és Rögzített árú projektekhez is készíthető jóváírás.

## <a name="invoice-proposals"></a>Számlajavaslatok
Mielőtt létrehozná egy projekt vevői számláját, létrehozhat egy előzetes számlát, más néven számlajavaslatot. A számlajavaslatban tudja kiválasztani, hogy a projektszámlán mely projekttranzakciók szerepeljenek. A projektszámla feladása, illetve a vevő vagy a finanszírozási forrás részére történő megküldése előtt át tudja nézni a számla részletes adatait.

### <a name="creating-invoice-proposals"></a>Számlajavaslatok létrehozása

A számlajavaslatokat manuálisan, az adott projekt tranzakciójának kiválasztásával hozhatja létre az elérhető tranzakciók listájából. Alternatív megoldásként felállíthat olyan számlázási szabályokat, amelyek automatikusan generálnak számlajavaslatot. Például felállíthat egy olyan számlázási szabályt, amely számlajavaslatokat hoz létre, amikor a projekt 25, 50, 75, illetve 100 százaléka elkészült. 

A következő tranzakciókhoz tud létrehozni számlajavaslatot:

-   Órák, kiadások és egyéb projekttranzakciók
-   A vevőktől korábbi projektszámlákon visszatartott összegek
-   Jóváírások
-   Egy vevő által a projekt megkezdése előtt kifizetett összegek

> [!NOTE]
> Az **Erőforrás szerinti rendezés engedélyezése a projektszámla-ajánlat** funkció lehetővé teszi a projekt könyvelője számára, hogy rendezze az erőforrásra a számlázási tranzakcióhoz rendelkezésre álló projekteket, amikor létrehoz egy új projekt-számlázási javaslatot. A rendelkezésre álló projekttranzakciók megjelenítésére szolgáló rács külön mezőket tartalmaz az **Erőforrás-azonosító** és az **Erőforrás** lehetőséghez. Ezekkel a mezőkkel szűrheti és rendezheti az erőforrás nevét. Ez a funkció alapértelmezés szerint ki van kapcsolva. Ez a funkció a **Funkciókezelés** lapon engedélyezhető (**Munkaterületek > Funkciókezelés**). A funkció engedélyezésével kapcsolatos segítségért forduljon a rendszergazdához.

A rendszerben díjtranzakciókat is létre tud hozni egy számlajavaslatban. Lehetőség van az eladási ár, az óra, a költség, a cikk és a díjtranzakciók módosítására is. A számlajavaslat feladásakor a frissített árak és a tranzakciók hozzáadódnak a projektjelentésekhez és a tranzakció előzményeihez. 

Amennyiben egy projekthez több vevői számlát szeretne létrehozni, ezekhez egyesével kell számlajavaslatot generálnia. Például tranzakciótípus alapján is létrehozhat számlákat. Ha órákat kell megadni az egyik vevői számlán, és a cikkeket egy másik számlán, külön számlajavaslatot kell létrehozni az óratranzakciókhoz és a díjtranzakciókhoz. 

Ha egy projekt egynél több finanszírozási forráshoz tartozik, akkor önálló számlajavaslatot hozhat létre az összes finanszírozási forrás részére. A **Finanszírozási szabály felosztásai** lapon meghatározhatja a tranzakciós összeg, az egyes finanszírozási forrásokhoz rendelendő százalékát, valamint a kerekítési különbségek feladásához használatos forrást.

### <a name="creating-customer-invoices-from-invoice-proposals"></a>Vevői számlák létrehozása számlajavaslatokból

Miután létrehozta és feladta a számlajavaslatot, automatikusan ltérejön egy vevői számla a javaslatban szereplő tranzakciókból. 

Számlajavaslat feladása előtt ahhoz tud hozzáadni, illetve abból törölni tranzakciókat. Például eltávolíthatja a projektbe feladott költségtranzakciókat, amelyek nem számlázhatók a vevőnek. 

Ha a szervezet előírja, hogy a számlajavaslatokat feladás előtt ellenőrizni kell, akkor az adott esetben a „Projekt számlajavaslatainak áttekintése” munkafolyamaton keresztül kell jóváhagyni feladás előtt.

### <a name="view-grant-information-on-project-invoice-list-pages"></a>A projekthez tartozó számlalista oldalain szereplő engedélyadatok megtekintése

Az állami szektor felhasználói hozzáadhatják az **Engedélyazonosítót** és az **Engedély nevét** a **Projekt számlajavaslatok** és a **Projekt számlái** lista oldalakhoz. Ezeket az oszlopokat az **Engedélyezési információk hozzáadása a projekthez tartozó számlalista oldalaihoz** funkció segítségével engedélyezheti. Ez a funkció alapértelmezés szerint ki van kapcsolva, és a **Munkaterületeken> Funkciókezelés** modulban engedélyezhető. A funkció engedélyezésével kapcsolatos segítségért forduljon a rendszergazdához.

## <a name="on-account-invoicing"></a>Részszámla készítése
A részszámlán a projekt kapcsán megadott összeg az időzítésen, a projekt előrehaladottságának százalékán és egyéb számlázási feltételeken múlik, amelyek a kapcsolódó projektszerződésben vannak meghatározva. Az összeg nem a projektbe feladott órák, cikkek, kiadások és díjak alapján kerül kiszámításra. 

A rendszerben előbb létre kell hoznia egy részszámlázási tranzakciót az idő- és anyagelszámolású vagy a rögzített árú projekthez, mielőtt a projektszámlához hozzáadhatná az adott részszámlázási tranzakciót. A részszámlázási tranzakcióban adja meg a vevőnek számlázandó összeget. Az összeg projektszámlájának létrehozása előtt hozzon létre egy előzetes számlát (számlajavaslatot). A számlajavaslatban válassza ki a részszámla-tranzakciót. A számlajavaslatban megtekintheti a részszámla információit, mielőtt létrehozza hozzá a projektszámlát. 

### <a name="fixed-price-projects"></a>Rögzített árú projektek
Rögzített árú projektek esetén a részszámlázási tranzakciók alapja lehet közösen meghatározott mérföldkövek, szállítási egység vagy a projektszerződésben meghatározott folyamatalapú számlázás. Külön sor jön létre a projektvevőtől elvárt minden egyes fizetéshez. Nincs szükség levonásokra.

### <a name="time-and-material-projects"></a>Idő- és anyagelszámolású projektek

Az idő- és anyagelszámolású projektek esetén részszámlajavaslattal számlázhat ki egy előleget a vevőnek vagy más finanszírozási forrásnak. A részszámlázási tranzakciókat egy sorként adja meg. Opcionális lehetőségként megadhat további sorokat azoknak a levonásoknak, amelyek ellentételezik a vevő által már esetlegesen kifizetett előlegeket. Levonássorok létrehozásához írja be a mínusz jelet az összeg elé.

## <a name="invoice-control"></a>Számlaellenőrzés
A számlaellenőrzés funkció segítségével tudja nyomon követni mind a számlázott, mind a számlanélküli tranzakciókat, valamint azokat az árajánlatokkal összevetni, annak érdekében, hogy az ajánlatkérési szakasztól a lezárásig végig tudja követni a projektjeit. Megtekintheti, hogy mely tranzakciók kerültek elszámolásra egy adott projekthez, illetve, hogy mely sorok kerültek számlázásra. Megtekintheti az egyes tranzakciókat is, hogy a feladásuk után módosíthassa őket.

## <a name="invoicing-fixed-price-projects"></a>Rögzített árú projektek számlázása
Rögzített árú projektek számlázásához meg kell határoznia egy számlázási ütemezést, illetve be kell fejeznie a számlázási eljárást.

### <a name="billing-schedule"></a>Számlázási ütemezés

A rögzített árú projekteket számlázási ütemezés alapján tudja leszámlázni. A számlázási ütemezés meghatározása a projekt egy vagy több mérföldköve alapján történik. Minden egyes mérföldkő kapcsán tud megadni konkrét dátumot, értékesítési pénznemet, eladási árat és a tevékenységet. 

Beállíthatja például az alábbi számlázási ütemezést:

-   20 százalék a projektszerződés aláírásakor
-   30 százalék az első szállítás alkalmával
-   15 százalék a második szállítás alkalmával
-   35 százalék a végső szállításkor

### <a name="invoicing-procedure"></a>A számlázás folyamata

Ha készen állnak a számlázásra a mérföldkőhöz kapcsolódó kifizetések, a részszámlázott összegek számlázására vonatkozó eljárást kell használnia.

## <a name="vendor-invoicing"></a>Szállítói számlázás
Ha megrendel egy cikket egy szállítótól és a cikket egy projekthez rendeli, a cikk kapcsán a beszerzési rendeléshez kiválasztott sortulajdonság határozza meg, hogy a rendszer kiszámlázza-e a beszerzett cikket egy vevő felé, vagy sem. Ha alapértelmezett sortulajdonságokat állít be, úgy azok a cikk kapcsán megjelennek a beszerzési rendeléssoron (**Soradatok > Projekt > Sortulajdonság összegei**). A sortulajdonságot kétféleképpen tudja módosítani:

-   A projekt vevőjét számlázza a cikkhez. Ehhez állítsa a cikkre vonatkozó sortulajdonságot számlázandó értékre a beszerzési megrendelésben, majd állítsa ki a számlát a vevő felé a helyes projektszámlázási módszer alkalmazásával.
-   A projekt vevőjét ne számlázza a cikkhez. Ezt úgy teheti meg, hogy a tételhez tartozó beszerzési rendeléssorban nem választja ki a **Számlázható** sortulajdonság lehetőséget. Ezután le tudja számlázni a beszerzési rendelést, és nincs további teendője ezzel kapcsolatosan.

> [!NOTE] 
> A feloldott visszatartási sorok alapértelmezés szerint nem számlázhatók. Ez azt jelenti, hogy a feloldott visszatartásokhoz nem engedélyezett Számlajavaslat létrehozása.

## <a name="credit-notes"></a>Jóváírások
Ha egy vevőszámlán negatív összeg szerepel, akkor a program jóváírásként kezeli a számlát. A dokumentum nyomtatásakor az a „Jóváírás” címet viseli. 

Ha egy korábban számlázott összeg visszatérítése céljából jóváírást hoz létre, először ki kell választania a jóváírandó számlázott összeget. Ezután ugyanazokkal a lépésekkel hozhatja létre a jóváírást, amelyeket a rendes vevőszámlák létrehozására használnak. Ki kell választania azokat a tranzakciókat, amelyeket korábban feladott egy vevőszámlára, majd létre kell hoznia és fel kell adnia egy jóváírási javaslatot. 

Egyazon a dokumentumon jóváírásra kijelölt tranzakciókat, jóváírási tranzakciókat, illetve feladott tranzakciókat is szerepeltethet. A dokumentum besorolása számla vagy jóváírás lehet, annak függvényében, hogy a végösszeg pozitív vagy negatív. 

Kiszámlázott összeg jóváírásához először ki kell választania a jóváírandó számlázott összeget, majd létre kell hoznia egy jóváírást. Ezután ugyanazokkal a lépésekkel hozhatja létre a jóváírást, amelyeket a vevői számlák létrehozására használ. 

Létrehozhat negatív összegű számlát, ami így jóváírásnak minősülő számla lesz. Jóváírás létrehozásához és nyomtatásához ki kell választania azokat a tranzakciókat, amelyeket korábban feladott egy vevői számlára, majd módosítania kell a tranzakciókat. Amennyiben a jogi személy elsődleges címe nem Németországban van, úgy a számla neve „Javító számla” lesz.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
