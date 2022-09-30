---
title: Véges kapacitástervezés és ütemezés
description: A véges kapacitástervezés és ütemezés segítségével meg lehet érteni, hogy mennyi munkát lehet termelni egy adott időszakban, amikor figyelembe veszi a különböző erőforrásokra vonatkozó korlátozásokat.
author: t-benebo
ms.date: 09/19/2022
ms.topic: article
ms.search.form: ReqParameters, ReqPlanSched, WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-19
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: c5eebe9ef6258b43daa7c7007ee28b0278fe5b09
ms.sourcegitcommit: 1a7729a6ce4f3fcf68bdc4cfdad746a5553da3c5
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573148"
---
# <a name="finite-capacity-planning-and-scheduling"></a>Véges kapacitástervezés és ütemezés

[!include [banner](../../includes/banner.md)]

A véges kapacitás olyan megközelítés, amely segít megérteni, hogy mennyi munkát lehet termelni egy adott időszakban, amikor figyelembe veszi a különböző erőforrásokra vonatkozó korlátozásokat. A véges kapacitásütemezés célja annak biztosítása, hogy a munka folytatódjon az üzemben egyenletes és hatékony idő alatt.

A véges kapacitástervezés és ütemezés pontosabb ütemezést hoz létre a termelési folyamatokhoz, mint a végtelen terhelési megközelítés. Ha nincs elég kapacitás az erőforrásokon, akkor a szállítási dátum ki lesz tolva, és a feladat ütemezése akkor történik meg, amikor a kapacitás elegendő.

## <a name="planning-optimization-support-for-finite-capacity-planning"></a>Tervezési optimalizálás támogatása véges kapacitástervezéshez

A véges kapacitástervezés és ütemezés ugyanúgy működik, függetlenül attól, hogy a tervezésoptimalizálást vagy a beépített tervezőmotort használja. A tervezési optimalizálás azonban nem használja **a Szűk keresztmetszet időkorlát paraméterét**. A tervezési optimalizálás használata esetén a szűk keresztmetszetű erőforrások ütemezése mindig ugyanazokkal az időkorlátokkal történik, mint a nem szűk keresztmetszetű erőforrások (ezt jelzi a véges kapacitás időkorlátja).

## <a name="set-up-finite-capacity-functionality"></a>Véges kapacitási funkciók beállítása

A véges kapacitási funkciók használatához globálisan engedélyezni kell a kapacitástervezést, valamint véges kapacitástervezést is engedélyezni kell mind az alaptervhez, mind minden olyan erőforráshoz, ahol használatban van. Olyan tervek és erőforrások esetén, amelyekben engedélyezve van a véges kapacitás, a tervezett termelési rendelések ütemezése figyelembe veszi a már foglalt kapacitást. A tervezett termelési rendelések ütemezése a szükségletdátumtól visszafelé történt. Ha nem áll rendelkezésre kapacitás az optimális ütemezés érdekében, a rendszer megpróbálja korábbi dátumra kötelezővé tenni az összetevő cikkeket. Ha a kapacitás a követelmények változásával együtt is változhat (például műszakokban dolgozik), akkor nem érdemes véges kapacitási funkciókat használni, mivel a számított feldolgozási idő nem lesz helyes. Az ütemezés csak olyan erőforrások kapacitását veszi figyelembe, amelyek már le vannak foglalva véges kapacitással. Ha engedélyezi egy erőforrás véges kapacitását, akkor lehetőség van a véges kapacitás időkorlátja módosítására.

### <a name="activate-master-planning-parameters"></a>Alaptervezési paraméterek aktiválása

A véges kapacitási funkciók használatához engedélyeznie kell a kapacitástervezést az Alaptervezés **paraméterei oldalon**.

1. Ugorjon az **Alaptervezés \> Beállítás \> Alaptervezés paraméterei** pontra.
1. A Kapacitástervezés **szakasz Tervezett rendelések** **·** **lapján** állítsa Igen beállításra a Termelés *beállítást.*

### <a name="activate-a-master-plan"></a>Alapterv aktiválása

Engedélyeznie kell a véges kapacitástervezést és ütemezést minden olyan alaptervhez, ahol használni szeretné.

1. Válassz az **Alaptervezés \> Beállítás \> Tervek \> Alaptervezések** lehetőséget.
1. A listaablakban válasszon ki egy olyan alaptervet, amelynél véges kapacitástervezést és ütemezést szeretne használni.
1. A Tervezett termelési **rendelések** **·** **szakasz Általános gyorswebhelyének Igen beállítására van beállítva a Véges** kapacitás *beállítás.*
1. Ismételje meg a 2. és 3. lépést a beállítani kívánt további alaptervekkel.

### <a name="activate-resources"></a>Erőforrások aktiválása

Engedélyeznie kell a véges kapacitástervezést és ütemezést minden olyan erőforráshoz, ahol használni szeretné.

1. Válassza a **Gyártásvezérlés \> Beállítás \> Erőforrások \> Erőforrások** menüpontot.
1. A listaablakban válasszon ki egy erőforrást, amely véges kapacitástervezés és -ütemezés használatára van beállítva.
1. A Művelet **gyorsgombbal** a **Kapacitás gomb** szakaszban **állítsa a Véges kapacitás** beállítást Igen *beállításra*.
1. Ismételje meg a 2. és 3. lépést minden további erőforrásra, amit be szeretne állítani.

## <a name="examples"></a>Példák

Ez a szakasz a következő példákkal mutatja be, hogyan működik a korlátlan és véges kapacitástervezés és ütemezés:

- 1. példa – Korlátlan kapacitástervezés
- 2. példa – véges kapacitástervezés egy napos időkorláttal
- 3. példa – véges kapacitástervezés két napos időkorláttal

### <a name="preconditions"></a>Előfeltételek

Mind a három példa az ebben a szakaszban ismertetett előfeltételeket feltételezi.

A *Termék1 termékhez* a következő műveleteket tartalmazó útvonal található.

| Műveletsz. | Művelet neve | Erőforrás        | Lefutási idő | Feldolgozott menny. | Tovább |
|---------------|----------------|-----------------|----------|--------------|------|
| 10            | Hegesztés        | Sorok    | 1        | 2            | 20   |
| 20            | Összeállítás     | Sor összeállítása | 1        | 4            |      |

A vállalat dolgozói egy műszakban dolgoznak 8 órát (8:00–16:00).

Az 1. termékből *24 részes* *, ütemezett termelési rendelés van.* A szállítási dátuma Ma *+ 3 nap*.

A tervezés eredményeként a rendszer a következő módon betölti az erőforrásokat:

- **Vezetéksor: az erőforrást** ma 8:00-tól a mai nap + 1-től 12:00-ig *kell* betölteni *.*
- **Sor összeállítása: Ez** az erőforrás be *van töltve a Mai nap + 1 1-ről 12:00-ig* *+ 2-ig, 10:00-kor*.

A következő ábra a kapott Gantt-diagramot mutatja be (nagyobb nézethez válassza ki).

[![Az előfeltételeket megjelenítő Gantt-diagram](media/finite-examples-conditions-small.png "Gantt-diagram az előfeltételek megjelenítése")](media/finite-examples-conditions.png)

### <a name="example-1--infinite-capacity-planning"></a>1. példa – Korlátlan kapacitástervezés

Ez a példa a tervezés eredményeit mutatja be, ha a véges kapacitástervezés helyett végtelen kapacitástervezést használ.

Az alapterv a következő vonatkozó beállítással rendelkezik, amely letiltja a véges kapacitástervezést a tervhez:

- **Véges kapacitás:** *Nem*

A **véges kapacitás beállítása** nemre van *állítva* mindkét vonatkozó erőforrás esetén, hogy tiltsa le a véges kapacitástervezést:

- Sorok
- Sor összeállítása

Most hozzáad egy új értékesítési *rendelést 8 db* *Termék1-hez*, és futtatja a tervet. Emiatt a rendszer a *Mai napon 8:00-tól ma 12:00-ig* *betölti a sorokat*. Miután befejeződött a szerelvénysor műveletei, *a rendszer a Mai napon 12:00-tól a mai napig 14:00-ig* *betölti az összeállítási sort*.

A következő ábra a kapott Gantt-diagramot mutatja be (nagyobb nézethez válassza ki).

[![A Gantt-diagram végtelen kapacitástervezési példát mutat be.](media/finite-examples-example1-small.png "A Gantt-diagram végtelen kapacitástervezési példát mutat")](media/finite-examples-example1.png)

### <a name="example-2--finite-capacity-planning-with-a-time-fence-of-one-day"></a>2. példa – véges kapacitástervezés egy napos időkorláttal

Ez a példa a tervezési eredményeket jeleníti meg véges kapacitástervezés és egy napos időkorlát használata mellett.

Az alapterv a következő vonatkozó beállításokkal rendelkezik, amelyek véges kapacitástervezést teszik lehetővé, és időkorlátot állíthatnak be a tervhez:

- **Véges kapacitás:** *Igen*
- **Véges kapacitási időkorlát:** *1*

A **véges kapacitás beállítása** *igenre* van állítva mindkét vonatkozó erőforrás esetén, hogy véges kapacitástervezést tesz lehetővé számukra:

- Sorok
- Sor összeállítása

Most hozzáad egy új értékesítési *rendelést 8 db* *Termék1-hez*, és futtatja a tervet. Ennek eredményeképpen a *rendszer a Ma + 1 1 20: 00* *00 00 óra 20 perctől a Mai + 1 1 1 00 00 00 óra között betölti a sorokat*. Miután befejeződött a szerelvénysor műveletei, *a rendszer a Mai + 1 összeállítási sort 12:00-tól Ma + 1-től 14:00-ig ( 14:00* *·*) fogja betölteni. A rendszer csak egy napra veszi figyelembe a véges kapacitást.

A következő ábra a kapott Gantt-diagramot mutatja be (nagyobb nézethez válassza ki).

[![A Gantt-diagramon látható a véges kapacitástervezés egy napos időkorláttal.](media/finite-examples-example2-small.png "A Gantt-diagramon látható a véges kapacitástervezés egy napos időkorláttal")](media/finite-examples-example2.png)

### <a name="example-3--finite-capacity-planning-with-a-time-fence-of-two-days"></a>3. példa – véges kapacitástervezés két napos időkorláttal

Ez a példa a tervezési eredményeket mutatja véges kapacitástervezés és két napos időkorlát használata mellett.

Az alapterv a következő vonatkozó beállításokkal rendelkezik, amelyek véges kapacitástervezést teszik lehetővé, és időkorlátot állíthatnak be a tervhez:

- **Véges kapacitás:** *Igen*
- **Véges kapacitási időkorlát:** *2*

A **véges kapacitás beállítása** *igenre* van állítva mindkét vonatkozó erőforrás esetén, hogy véges kapacitástervezést tesz lehetővé számukra:

- Sorok
- Sor összeállítása

Most hozzáad egy új értékesítési *rendelést 8 db* *Termék1-hez*, és futtatja a tervet. Ennek eredményeképpen *a rendszer a Ma + 1 1 22:00 00* *00 00 perctől a Mai + 1 1 1 00 00 00-ig betölti a sorokat*. Miután befejeződött a szerelvénysor műveletei, *a rendszer a Mai + 2 összeállítási sort 8:00-tól* *a Mai + 2 nap 10:00-ig* betölti. A rendszer csak két napig veszi figyelembe a véges kapacitást.

A következő ábra a kapott Gantt-diagramot mutatja be (nagyobb nézethez válassza ki).

[![A Gantt-diagramon látható a véges kapacitástervezés két napos időkorláttal.](media/finite-examples-example3-small.png "A Gantt-diagramon látható a véges kapacitástervezés két napos időkorláttal")](media/finite-examples-example3.png)

> [!IMPORTANT]
> A véges kapacitás időkorlátját mindig az üzleti igényeknek megfelelően kell beállítani. A példában látható példák csupán bemutatják a funkciót. A helyzet az, hogy az egynapos időkorlát valószínűleg túl alacsony ahhoz, hogy a legtöbb gyártó véges kapacitástervezést használjon.
