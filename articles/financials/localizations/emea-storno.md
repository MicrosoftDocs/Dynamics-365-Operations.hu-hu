---
title: "Sztornókönyvelés"
description: "A sztornókönyvelés az eredeti naplószámla-bejegyzések sztornírozási gyakorlata negatív számok segítségével."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 1219713
ms.search.region: Czech Republic, Germany, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-semaz
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: a0d5aa114564e000a2d2b2780996a14d5a41015e
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="storno-accounting"></a>Sztornókönyvelés

A sztornókönyvelés az eredeti naplószámla-bejegyzések sztornírozási gyakorlata negatív számok segítségével.

A *sztornókönyvelés* az eredeti naplószámla-bejegyzések tartozik és követel összegeinek sztornírozási gyakorlata negatív számok segítségével. Mivel a könyvelők tipikusan piros tintával írják a sztornókönyvelési bejegyzéseket, ez a számviteli gyakorlat *piros sztornó* néven is ismert. A sztornókönyvelés használatával törölheti a dokumentumot helytelen összegekkel, de a lemondás után mindig be kell írnia a megfelelő dokumentum összegét.

## <a name="example"></a>Példa
Egy könyvelő feladja egy szállító számláját 120 USD összegről. A fizetési folyamat során kiderült, hogy a könyvelő tévedésből 120 USD helyett 102 USD-t írt be. Most a könyvelőnek sztorníroznia kell az eredeti dokumentumot, majd létre kell hoznia a helyes számlát 102 USD-ért. További tudnivalók: [Számla a szállítótól](../accounts-payable/vendor-invoices-overview.md). Az alábbi tábla a sztornírozás általános bejegyzését mutatja be.

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
Kétféleképpen lehet javítani a bejegyzést – sztornírozással és fordított bejegyzéssel. Fordított bejegyzés használata esetén az eredeti általános bejegyzés egy példányát fordított adós- és hitelszámlával hozza létre, és az összegek ugyanazokkal a jelekkel maradnak. Sztornó használatakor a rendszer létrehoz egy példányt az eredeti főkönyvi bejegyzésből, de negatív előjellel kell elszámolni az összegeket. Az alábbi tábla a sztornírozás általános bejegyzését mutatja be.

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

Ne feledje, hogy az egyenlegek egyenlők a sztornírozottnál és a sztornírozásnál. Különbség van a terhelésforgalom és a hitelforgalom között, mert a fordított bevétel feleslegessé teszi a beszedési és hitelforgalmat. A sztornírozási bejegyzés, ahol ritkán használja a forgalom országokban/régiókban használatos. Más országok/régiók sztornókönyvelés.

## <a name="partial-storno"></a>Részleges sztornírozás
A *Sztornókönyvelés* az eredeti naplószámla-bejegyzések tartozik és követel összegeinek sztornírozási gyakorlata negatív számok segítségével. Egyes országokban/régiókban engedélyezi, hogy használja a részleges sztornírozása. Egy könyvelő feladja egy szállító számláját 120 USD összegről. A fizetési eljárás során kiderül, hogy a könyvelő véletlenül adta meg a megfelelő számsorozatot. 102 USD eredeti számláján hibásan lett volna megfelelő a számsorozatban. Részleges sztornó használ, a könyvelő kell létrehozása sztornó 18 USD. Az alábbi tábla a sztornírozás általános bejegyzését mutatja be.

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

Részleges sztornírozása hibát hoz létre az eredeti példány nyomtatása űrlapon. Az eredeti dokumentum dátuma és a Sztornírozás dátuma közötti eltérés esetén ez megnehezíti egy pontos pénznemösszeg beolvasása. Részleges sztornó emiatt csak bizonyos dokumentumok esetén engedélyezett. A műveletek a Microsoft Dynamics 365 részleges sztornírozása funkció dokumentumokhoz és ahol megengedett országok/régiók tartalmaz.

## <a name="how-to-enter-storno-on-journal-lines"></a>Írja be a sztornírozás a naplósorokban
Adja meg a tartozás vagy követelés összege negatív előjellel sztornó tételt hoz létre a naplósorban. A **Javítás** mező értéke a feladási folyamat során. 

## <a name="how-storno-is-displayed"></a>Hogyan jelenjen meg sztornírozása
Dynamics 365 tartozó műveletek kezelik a speciálisan negatív napló összegeit. Általános naplóbejegyzés, a vevői tranzakció, a szállítói tranzakció és a más tranzakciókkal nyújtanak a sztornírozás funkció alatt leírt módon.

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
<td class="column-1"> Tartozik</td>
<td class="column-2">Nincs</td>
<td class="column-3">&gt;0.</td>
<td class="column-4" align="right">Összeg</td>
<td class="column-5" align="right">Összeg</td>
<td class="column-6">Növekszik</td>
<td class="column-7"></td>
<td class="column-8">Növekszik</td>
</tr>
<tr class="row-3">
<td class="column-1"> Követel</td>
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

Testreszabhatja a sztornírozás megjelenítését űrlapokban, rácsokban, oszlopokban és mezőkben. Például kikapcsolása előjel megjelenítése, vagy a negatív összegek kitöltés módosítása. Használhatja a **Javítás** minden képernyőbeállításokat, a mezőt, ha a **Javítás** mezőben szerepel az "Igen", akkor egy sztornírozás bejegyzés.

![Naplóösszegekben bejegyzés sztornírozása](./media/journal-storno.png)

## <a name="how-documents-create-storno"></a>Sztornírozási dokumentumok létrehozása
Egyes dokumentumok érvénytelenítési tranzakciók létrehozása. Például a főkönyvi, a fizetendő számlák és a követelésekre vonatkozó deviza átértékelés megszünteti a nem realizált nyereséget és veszteséget. További részletekért lásd: [Főkönyvi devizaátértékelés](../general-ledger/foreign-currency-revaluation-general-ledger.md) vagy [A Kötelezettségek és a Kinnlevőségek modul devizaátértékelései](../cash-bank-management/foreign-currency-revaluation-accounts-payable-accounts-receivable.md). A törlési tranzakció létrehozása után új tranzakciók jönnek létre a nem realizált nyereséggel és veszteséggel. Érvénytelenítési tranzakciók is létrejönnek a készlethez. További információ [Készletzárás](../../supply-chain/cost-management/inventory-close.md). Vannak olyan dokumentumok, amelyek lehetővé teszik a korábban feladott dokumentum visszavonása. Például a felhasználó hozhat létre jóváírást ad fel, hogy egy korábban létrehozott számla érvénytelenítése. Dokumentumok létrehozása a fordított meghatározott paraméterek vagy sztornótranzakciók használata Például az árfolyam-korrekció fordított hoz létre, vagy az általános főkönyvi javítás paraméter alapján sztornótranzakciók. A vevői jóváírást hoz létre a fordított vagy számlák Kinnlevőségek jóváírás javítás paramétertől függő sztornótranzakciók.


