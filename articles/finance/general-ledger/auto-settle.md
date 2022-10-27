---
title: Főkönyvi kiegyenlítések automatizálása
description: Ez a cikk a főkönyvi kiegyenlítések automatizálási folyamatával kapcsolatban tartalmaz tájékoztatást.
author: abruer
ms.date: 9/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: b43eeeefa581b5d8b40dc2cf0187c7c781b18be3
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/20/2022
ms.locfileid: "9707760"
---
# <a name="automate-ledger-settlements"></a>Főkönyvi kiegyenlítések automatizálása

[!include [banner](../includes/banner.md)]

A Microsoft Dynamics 365 Pénzügyi modul 10.0.31-es **** **verziójában a Főkönyvi kiegyenlítések automatizálása funkció elérhető a Funkciókezelés munkaterületen.**  A főkönyvi **kiegyenlítési** **folyamat** automatizálása funkció csak akkor engedélyezhető, ha engedélyezve van a Főkönyvi kiegyenlítés és az év végi lezárás közötti tájékoztatás funkció.

A főkönyvi kiegyenlítés a tartozik és követel tranzakciók egyeztetésének folyamata a főkönyvben. Az ismétlődő ütemezésben főkönyvi kiegyenlítési tevékenységeket végző szervezetek ezzel automatizálhatja a folyamatot. Az automatikus főkönyvi kiegyenlítési folyamat során a tartozik és a követel tranzakciókat csak akkor lehet automatikusan megfeleltetni, ha azok összegei a könyvelési pénznemben egyenlők.Például az összeg tartozik $1.00 automatikusan megfeleltethet egy követel összegnek $1.00. A tartozás értéke nem $1.00 egymáshoz automatikusan két követel értékkel, amelyek mindegyikének értéke $0.50. A főkönyvi tranzakcióösszegek részleges egyeztetése nem támogatott.

A főkönyvi kiegyenlítés automatizálása a következő részleteket határozza meg:

- Főkönyvi kiegyenlítések futtatásakor
- Milyen feltételek segítségével lehet megfeleltetni az automatikusan kiegyenlítható tartozik és követel tételeket?
- Milyen sorrendben történik a főkönyvi kiegyenlítési adatok feldolgozása

## <a name="define-the-occurrence-of-ledger-settlements"></a>A főkönyvi kiegyenlítések előfordulásának meghatározása

A főkönyvi kiegyenlítés automatizálása a Folyamatautomatizálási keretrendszert használja. A különböző üzleti folyamatok ezt a keretrendszert használják egy kiválasztott folyamatok ismétlődésének meghatározásához. Főkönyvi kiegyenlítések: Rendszerfelügyelet – Beállítási  **\>\> folyamat automatizálása** **vagy Főkönyv \> beállítási \> folyamatautomatizálása.**

Először válassza az Új folyamatautomatizálás **létrehozása** lehetőséget, majd válassza a Főkönyvi **kiegyenlítések lehetőséget**. Ezután egy varázsló végigvezeti az automatizálás beállítási folyamatán.

## <a name="general-page"></a>Általános lap

A varázsló **Általános** lapján adja meg a létrehozott főkönyvi kiegyenlítési előfordulás nevét. Ha például az egyező tartozik és követel tételeket a hétfői nap főkönyvi számláján egyenlítik ki, **akkor egy jól leíró nevet adjon meg, például LedgerSettle\_ Könyv**. A beírott név megjelenik a **Főkönyvi** **kiegyenlítések lap Automatizálási szabály oszlopában** .

A lapon fennmaradó beállítások általánosak, és meghatározzák a főkönyvi kiegyenlítések ezen verziójának előfordulási mintáját. Ha például a hétfőre történik az esemény, akkor be lehet meghatározni, hogy hetente futzon, és a hét napjaként a hét megfelelő napjaként lehet kiválasztani a hétfőt. Megadhatja egy korai ütemezési időpontot is (például 2:00), hogy a folyamatautomatizálás a következő munkanap kezdete előtt befejeződjön. Javasoljuk, hogy ütemezi a folyamat automatizálását úgy, hogy a normál munkaidőn kívülre legyen hajtva. Ily módon csökkentheti a könyvelői munkatársakra gyakorolt hatást a munkanapok során.

Az Általános lap többi mezőjével kapcsolatos további **tudnivalókat** lásd a folyamatautomatizálási dokumentációban.

## <a name="ledger-settlements-match-criteria-page"></a>Főkönyvi kiegyenlítések egyeztetési feltételeinek lapja

A varázsló következő lapja a Főkönyvi **kiegyenlítések egyeztetési feltételek lapja** . Megadja azokat a fő számlákat, amelyek részt használnak a folyamatautomatizálás előfordulásában, valamint a terhelések és a jóváírások egyeztetését meghatározó feltételek meghatározásában.

### <a name="account-selection"></a>Számla kiválasztása

A jogi személy főkönyvi kiegyenlítési számláiként korábban megadott fő számlák jelennek meg. (A fő számlákat főkönyvi kiegyenlítési számlaként a következőnél adhatja meg: **Főkönyv beállítása \> Főkönyvi \> paraméterek Főkönyvi \> kiegyenlítések**.)

### <a name="main-account-and-posting-layer"></a>Fő számla és feladási réteg

A  **fő számla és** a feladási **réteg** értékeihez egyeztetési feltételek szükségesek. A **főkönyvi tartozik** tranzakció **és** a követel tranzakció fő számla és feladási réteg értékeinek egyezniük kell az automatikus főkönyvi kiegyenlítési folyamat során.

### <a name="posting-type"></a>Feladás típusa

Akkor válassza **a Feladás típust**, ha a főkönyvi tartozik és követel tranzakciók feladási típusának azonos típusúnak kell lennie ahhoz, hogy az automatikus főkönyvi kiegyenlítési folyamat során egyezniük kell.

### <a name="financial-dimensions"></a>Pénzügyi dimenziók

Válassza a Pénzügyi **dimenziók** lehetőséget, ha a főkönyvi tartozik és követel tranzakciók pénzügyi dimenzióinak azonos pénzügyi dimenziókkal kell megfeleltetve lenniük az automatikus főkönyvi kiegyenlítési folyamat során. Ha ez a beállítás be van jelölve, a pénzügyi dimenzióértékek kritériumait ki **kell választani a Rendelkezésre álló pénzügyi dimenziók listában**. A **Rendelkezésre álló pénzügyi dimenziók** listája nem tartalmazza a fő számla dimenzióját, mert az az egyeztetési feltételek részeként automatikusan szükséges.

## <a name="view-the-results-of-a-ledger-settlement-automation"></a>Főkönyvi kiegyenlítés-automatizálás eredményeinek megtekintése

A főkönyvi kiegyenlítés-automatizálási sorozat létrehozása után az egyes főkönyvi kiegyenlítések előfordulásai a folyamatautomatizálás heti nézetében jelennek meg. Ezenkívül megjelenik az egyes előfordulások állapota is. A következő állapotok használatosak:

- **Ütemezve**  – az automatizálás ütemezve van, de még nem futott le.
- **Végrehajtás** – az automatizálás jelenleg fut.
- **Hiba**  – az automatizálás lefutott, de hiba történt. A hibákat az Eredmények megtekintése gomb használatával **lehet** megtekinteni.
- **·** Kész – az automatizálás sikeresen lefutott. A kiegyenlítés eredményeit a Főkönyvi **kiegyenlítések lapon lehet** megtekinteni.

Az egyeztetési eredmények megtekintéséhez menjen a Főkönyv **\> időszakos feladatai – \> Főkönyvi kiegyenlítések modulba**. A Főkönyvi **kiegyenlítések** **lap** Automatizálási szabály mezőjében a tranzakció kiegyenlítésére használt automatikus főkönyvi kiegyenlítési ütemezett feladat neve látható. A sikertelen kiegyenlítési kísérletek nem frissítik az automatizálási **szabály** értékét. Ha manuálisan sztorníroz egy olyan tranzakciót, amelyet korábban sikeresen kiegyenlített az automatizálási folyamat, **a rendszer eltávolítja az automatizálási** szabály értékét.

Az **egyeztetési rekordok** Kiegyenlített dátum mezőjében az automatizációs folyamat hajtható végre.

## <a name="editing-a-ledger-settlement-automation"></a>Főkönyvi kiegyenlítés automatizálásának szerkesztése

A Folyamatautomatizálási keretrendszer lehetővé teszi a főkönyvi kiegyenlítéshez létrehozott sorozatok és előfordulások szerkesztését. A sorozat a Folyamatautomatizálás lapról **** vagy a folyamatautomatizálás heti nézetből szerkeszthető. Ha például a vezető úgy dönt, hogy a hétfő helyett szerdai nap helyett főkönyvi kiegyenlítést hajt végre, akkor talál egy előfordulást a **heti nézetben, és kiválasztja a Nézet/Szerkesztés – Sorozat lehetőséget**.

Ha szerkeszt egy sorozatot, a program megkérdezi, hogy a módosítás az összes vagy csak az új előfordulásokban történik-e. Az olyan korábbi **előfordulások**, amelyek már Befejeződött állapotúak vagy **** Hiba állapottal fejeződtek be, nem módosíthatók.

Lehetőség van új előfordulás hozzáadására vagy meglévő előfordulás módosítására is. A következő főkönyvi kiegyenlítési eseményre például a január 1-jén, szerdai futtatáskor van ütemezve, de ez munkaszüneti nap. Az előfordulást a Folyamatautomatizálás lapról **** vagy a folyamatautomatizálás heti nézetről módosíthatja. Megnyílik egy lap, amely megjeleníti az ütemezés részleteit és az egyeztetési feltételeket. Itt szerkesztheti az ütemezett időt és dátumot. Szükség esetén az egyeztetési feltételek módosíthatók is. 

Egy előfordulást vagy egy sorozatot le is lehet tiltani. Ha le szeretné tiltani az előfordulást, és fel szeretné függeszteni a feldolgozását, válassza ki azt a folyamatautomatizálás heti nézetében, majd válassza a Letiltás **lehetőséget**. A sorozatokat a Folyamatautomatizálás lapon **tilthatja** le.

## <a name="security-for-ledger-settlement-automation"></a>Főkönyvi kiegyenlítés automatizálásának biztonsága

**A főkönyvi** kiegyenlítések automatizálási sorozatbeállítási feladatának karbantartása hozzáadva a főkönyvi vezető és a könyvelési felügyelő szerepkörhöz, **valamint** a főkönyvi kiegyenlítés automatizálási sorozatbeállítási beállításainak megtekintése feladat hozzáadva a főkönyvi könyvelés, a főkönyvi vezető és a főkönyvi felettes szerepkörhöz a főkönyvi kiegyenlítés automatizálása számára. Ezek a feladatok az alapértelmezett biztonsági beállítások, de a szervezet követelményeinek megfelelően módosíthatók.

## <a name="general-ledger-parameters-for-ledger-settlement-automation"></a>Főkönyvi paraméterek a főkönyvi kiegyenlítés automatizálásához

A **Kiegyenlítés jellemző egyenlege** mező azt a sorrendet jelzi, hogy az automatikus főkönyvi kiegyenlítés feldolgozása történik-e. A Kiegyenlítés tipikus egyenlegértékének **beállításához** vagy megtekintéséhez kattintson a Főkönyv **\>\>** beállítása főkönyvi paraméterek lapra, és válassza a Főkönyvi **kiegyenlítések** lapot.

Ha **a Tartozik** beállítás van kiválasztva, akkor a program a tartozik oldalon elindítja az automatikus főkönyvi kiegyenlítési folyamatot, és megkeresi a megfelelő követel tételeket. Ha a **Követel** beállítást választja, akkor a program a követel oldalon elindítja az automatikus főkönyvi kiegyenlítési folyamatot, és megkeresi a megfelelő tartozik tételeket. Ennek a beállításnak tükröznie kell a fő számla tipikus egyenlegét.

## <a name="processing-a-ledger-settlement-automation"></a>Főkönyvi kiegyenlítés automatizálásának feldolgozása

Az automatizálás futtatásakor a rendszer kiválasztja a folyamatautomatizálási sorozathoz meghatározott fő számlák főkönyvi tranzakcióit. A tranzakciókat dátum szerint rendeli meg, a pénzügyi év kezdettől a folyamat automatizálásának futtatásáig dátumtartomány alkalmazásával. Megfelel a megadott egyeztetési feltételeknek. A tartozik és a követel könyvelési pénznemben szereplő abszolút értékeknek meg kell egyezniük ahhoz, hogy ki legyen egyenlítve.

Miközben a fő számlát egy főkönyvi kiegyenlítés automatizálásának egy előfordulása feldolgozhatja, **nem tudja megjeleníteni azt a Főkönyvi kiegyenlítések** lapon. Meg kell várnia, amíg az automatizálási folyamat befejeződik. Az ütközések elkerülése érdekében ajánlott a folyamatautomatizálást a munkaidőn kívülre ütemezni.

Az automatizálási folyamat tartalmazni fogja a feltételeknek megfelelő összes tranzakciót, kivéve azokat a tranzakciókat, **amelyek manuálisan vannak megjelölve kiegyenlítésre a Főkönyvi kiegyenlítések** lapon.

## <a name="reversal-of-transactions-that-are-settled-by-the-automation-process"></a>Az automatizálási folyamattal kiegyenlített tranzakciók újraszedása

Az automatizált főkönyvi kiegyenlítési folyamat során készített kiegyenlítést sztornírozhatja. Az automatizálási folyamattal **kiegyenlített** tranzakció sztornírozásakor a rendszer eltávolítja az automatizálási szabály értékét.
