---
title: Sztornókönyvelés
description: A sztornókönyvelés az eredeti naplószámla-bejegyzések sztornírozási gyakorlata negatív számok segítségével.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 1219713
ms.search.region: Czech Republic, Germany, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-semaz
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2cefdbc03b19eebff8141d4f578047de002ace56
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773456"
---
# <a name="storno-accounting"></a>Sztornókönyvelés

[!include [banner](../includes/banner.md)]

A sztornókönyvelés az eredeti naplószámla-bejegyzések sztornírozási gyakorlata negatív számok segítségével.

A *sztornókönyvelés* az eredeti naplószámla-bejegyzések tartozik és követel összegeinek sztornírozási gyakorlata negatív számok segítségével. Mivel a könyvelők tipikusan piros tintával írják a sztornókönyvelési bejegyzéseket, ez a számviteli gyakorlat *piros sztornó* néven is ismert. A sztornókönyvelés használatával törölheti a dokumentumot helytelen összegekkel, de a lemondás után mindig be kell írnia a megfelelő dokumentum összegét.

## <a name="example"></a>Példa
Egy könyvelő feladja egy szállító számláját 120 USD összegről. A fizetési folyamat során kiderült, hogy a könyvelő tévedésből 102 USD helyett 120 USD-t írt be. Most a°könyvelőnek sztorníroznia kell az eredeti dokumentumot, majd létre kell hoznia a helyes számlát 102 USD-ról. További információ: [Szállítói számlák áttekintése](../accounts-payable/vendor-invoices-overview.md). Az alábbi tábla a sztornírozás általános bejegyzését mutatja be.

| **Dokumentumazonosító** | **Számla** | **Tartozik** | **Követel** | **Megjegyzés**                  |
|-----------------|-------------|-----------|------------|------------------------------|
| Invoice0001     | Purch acc   | 120       |            | Eredeti számla (helytelen) |
| Invoice0001     | Vendor acc  |           | 120        | Eredeti számla (helytelen) |
|                 |             |           |            |                              |
| Storno0001      | Purch acc   | -120     |            | Sztornó                       |
| Storno0001      | Vendor acc  |           | -120      | Sztornó                       |
|                 |             |           |            |                              |
| Invoice0002     | Purch acc   | 102       |            | Helyes számla              |
| Invoice0002     | Vendor acc  |           | 102        | Helyes számla              |

Ebben a példában az egyenleg a következőt jeleníti meg.

| Könyvelési számla    | Tartozik | Követel | Egyenleg |
|------------|-------|--------|---------|
| Purch acc  | 102   | 0      | 102     |
| Vendor acc | 0     | 102    | -102    |

## <a name="differences-between-storno-and-reverse-entries"></a>A sztornírozás és a fordított bejegyzések közötti különbségek
Kétféleképpen lehet javítani a bejegyzést – sztornírozással és fordított bejegyzéssel. Fordított bejegyzés használata esetén az eredeti általános bejegyzés egy példányát fordított adós- és hitelszámlával hozza létre, és az összegek ugyanazokkal a jelekkel maradnak. Sztornó használatakor a rendszer létrehoz egy példányt az eredeti főkönyvi bejegyzésből, de negatív előjellel kell elszámolni az összegeket. Az alábbi tábla a sztornírozás általános bejegyzését mutatja be.

| **Dokumentumazonosító** | **Számla** | **Tartozik** | **Követel** | **Megjegyzés**                  |
|-----------------|-------------|-----------|------------|------------------------------|
| Invoice0001     | Purch acc   | 120       |            | Eredeti számla (helytelen) |
| Invoice0001     | Vendor acc  |           | 120        | Eredeti számla (helytelen) |
|                 |             |           |            |                              |
| Reverse0001     | Purch acc   |           | 120        | Megfordítás                      |
| Reverse0001     | Vendor acc  | 120       |            | Megfordítás                      |
|                 |             |           |            |                              |
| Invoice0002     | Purch acc   | 102       |            | Helyes számla              |
| Invoice0002     | Vendor acc  |           | 102        | Helyes számla              |

Ebben a példában az egyenleg a következőt jeleníti meg.

| Könyvelési számla    | Tartozik | Követel | Egyenleg |
|------------|-------|--------|---------|
| Purch acc  | 222   | 120    | 102     |
| Vendor acc | 120   | 222    | -102    |

Ne feledje, hogy az egyenlegek egyenlők a sztornírozottnál és a sztornírozásnál. Különbség van a beszedési forgalom és a hitelforgalom között, mert a fordított bejegyzés felesleges beszedési és hitelforgalmat hoz létre. A sztornírozási bejegyzés, ahol ritkán használja a forgalom országokban/régiókban használatos. Más országok/régiók sztornókönyvelés.

## <a name="partial-storno"></a>Részleges sztornírozás
A *Részleges sztornírozás* olyan könyvelési gyakorlat, ahol a negatív tartozik és követel összegek használatával visszafordítja az eredeti napló számlabejegyzéseket. Egyes országokban/régiókban engedélyezi, hogy használja a részleges sztornírozása. Például egy könyvelő feladja egy szállító számláját 120 USD összegről. A fizetési eljárás során kiderül, hogy a könyvelő véletlenül nem megfelelően adta meg a számsorozatot. Az eredeti, 102 USD-s számlán hiba szerepelt a számsorozatban. Részleges sztornó segítségével a könyvelőnek létre kell hoznia egy sztornót 18 USD-ról. Az alábbi tábla a részleges sztornírozás általános bejegyzését mutatja be.

| **Dokumentumazonosító** | **Számla** | **Tartozik** | **Követel** | **Megjegyzés**                  |
|-----------------|-------------|-----------|------------|------------------------------|
| Invoice0001     | Purch acc   | 120       |            | Eredeti számla (helytelen) |
| Invoice0001     | Vendor acc  |           | 120        | Eredeti számla (helytelen) |
|                 |             |           |            |                              |
| Storno0001      | Purch acc   | \-18.      |            | Részleges sztornírozás               |
| Storno0001      | Vendor acc  |           | \-18.       | Részleges sztornírozás               |

Ebben a példában az egyenleg a következőt jeleníti meg.

| Könyvelési számla    | Tartozik | Követel | Egyenleg |
|------------|-------|--------|---------|
| Purch acc  | 102   | 0      | 102     |
| Vendor acc | 0     | 102    | -102    |

Részleges sztornírozása hibát hoz létre az eredeti példány nyomtatása űrlapon. Az eredeti dokumentum dátuma és a Sztornírozás dátuma közötti eltérés esetén ez megnehezíti a pontos pénznemösszeg beolvasását. Részleges sztornó emiatt csak bizonyos dokumentumok esetén engedélyezett. A Dynamics 365 Finance az engedélyezett dokumentumok és országok/régiók esetén biztosít részleges sztornírozási funkciót.

## <a name="how-to-enter-stornoon-journal-lines"></a>Sztornírozás bejegyzésének módja a naplósorokban
Adja meg a tartozás vagy követelés összegét negatív előjellel a naplósorban a sztornóbejegyzés létrehozásához. A **Javítás** mező értékét a feladási folyamat során állítják be. 

## <a name="how-storno-is-displayed"></a>Hogyan jelenjen meg sztornírozása
A Finance különlegesen kezeli a negatív naplóösszegeket. Általános naplóbejegyzés, a vevői tranzakció, a szállítói tranzakció és a más tranzakciók nyújtanak a sztornírozás funkcióz az alább leírt módon.

<table>
<thead>
<tr class="row-1">
<th class="column-1" rowspan="2">A naplósor felhasználói adatbevitel</th>
<th class="column-2" colspan="2">Tárolási elve</th>
<th class="column-4" colspan="2">Megjelenítési szabály</th>
<th class="column-6" colspan="3">A kivonat jelentés hatása</th>
</tr>
<tr class="row-1">
<th class="column-2">Javítás mező</th>
<th class="column-3">Összeg mező</th>
<th class="column-4">Összeg a tranzakció pénznemében.</th>
<th class="column-5">Összeg</th>
<th class="column-6">Tartozás oszlop</th>
<th class="column-7">Követel oszlophoz</th>
<th class="column-8">Egyenleg oszlop</th>
</tr>
</thead>
<tbody>
<tr class="row-2">
<td class="column-1"> Tartozik</td>
<td class="column-2">Nincs</td>
<td class="column-3">&gt;0.</td>
<td class="column-4" align="right">Összeg</td>
<td class="column-5" align="right">Összeg</td>
<td class="column-6">Növekszik</td>
<td class="column-7"></td>
<td class="column-8">Növekszik</td>
</tr>
<tr class="row-3">
<td class="column-1"> Jóváírás</td>
<td class="column-2">Nincs</td>
<td class="column-3">&lt;0.</td>
<td class="column-4" align="right">-Összeg</td>
<td class="column-5" align="right">Összeg</td>
<td class="column-6"></td>
<td class="column-7">Növekszik</td>
<td class="column-8">Csökken</td>
</tr>
<tr class="row-4">
<td class="column-1">-Terhelés</td>
<td class="column-2">Igen</td>
<td class="column-3">&gt;0.</td>
<td class="column-4" align="right">+Összeg</td>
<td class="column-5" align="right">-Összeg</td>
<td class="column-6">Csökken</td>
<td class="column-7"></td>
<td class="column-8">Növekszik</td>
</tr>
<tr class="row-5">
<td class="column-1">-Jóváírás</td>
<td class="column-2">Igen</td>
<td class="column-3">&lt;0.</td>
<td class="column-4" align="right">-Összeg</td>
<td class="column-5" align="right">-Összeg</td>
<td class="column-6"></td>
<td class="column-7">Csökken</td>
<td class="column-8">Csökken</td>
</tr>
</tbody>
</table>

Testreszabhatja a sztornírozás megjelenítését űrlapokban, rácsokban, oszlopokban és mezőkben. Például kikapcsolhatja az előjel megjelenítését vagy módosíthatja a negatív összegek kitöltését. Használhatja a **Javítás** mezőt minden képernyőbeállítással, ha a **Javítás** mezőben szerepel az "Igen", akkor egy sztornóbejegyzés.

![Naplóösszegekben bejegyzés sztornírozása](./media/journal-storno.png)

## <a name="how-documents-create-storno"></a>Sztornírozási dokumentumok létrehozása
Egyes dokumentumokban lehetséges az érvénytelenítési tranzakciók létrehozása. Például a főkönyvi, a fizetendő számlák és a követelésekre vonatkozó deviza átértékelés megszünteti a nem realizált nyereséget és veszteséget. További részletek: [Főkönyvi devizaátértékelés](../general-ledger/foreign-currency-revaluation-general-ledger.md) vagy [A Kötelezettségek és a Kinnlevőségek modul devizaátértékelései](../cash-bank-management/foreign-currency-revaluation-accounts-payable-accounts-receivable.md). Az érvénytelenítési tranzakció létrehozása után új tranzakciók jönnek létre a nem realizált nyereséggel és veszteséggel. Érvénytelenítési tranzakciók is létrejöhetnek a készlethez. További információ: [Készletzárás](../../supply-chain/cost-management/inventory-close.md). Vannak olyan dokumentumok, amelyek lehetővé teszik a korábban feladott dokumentum visszavonása. Például a felhasználó hozhat létre jóváírást ad fel, hogy egy korábban létrehozott számla érvénytelenítése. A dokumentumok meghatározott paramétereket használnak a fordított vagy sztornótranzakciók létrehozásához. Például a devizaátértékelés fordított vagy sztornótranzakciót hozhat létre a főkönyv javítási paramétere alapján. A vevői jóváírást hoz létre a fordított vagy számlák Kinnlevőségek jóváírás javítás paramétertől függő sztornótranzakciók.

