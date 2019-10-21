---
title: Készletkötegek egyesítése
description: Ez a cikk a két vagy több készletköteg egyesített köteggé történő összevonásáról nyújt tájékoztatást.
author: pjacobse
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBatchJournalListPage, InventBatchJournalMerge
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 39782
ms.assetid: 07c5e98b-10fd-4f5c-b471-41d2150f47b0
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 83d969fcc59af87da3921225974ebc2ae41d9fa1
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250990"
---
# <a name="merge-inventory-batches"></a>Készletkötegek egyesítése

[!include [banner](../includes/banner.md)]

Ez a cikk a két vagy több készletköteg egyesített köteggé történő összevonásáról nyújt tájékoztatást.

A Kötegek egyesítésekor a számítások segíthetnek optimalizálni az egyesített köteg jellemzőit és kötegattribútumait. Miután kiválasztotta a forráskötegeket, áttekintheti és módosíthatja az egyesített köteget a feladás előtt. A kötegegyesítést átvezetheti egy készletnaplóba is jóváhagyáshoz. Ezután a készletet közvetlenül a készletnaplóból foglalhatja le és adhatja fel. Egyesített köteg feladása esetén a készletet a forrás-kötegekhez és az egyesített köteghez van módosítva.

## <a name="are-there-any-prerequisites"></a>Vannak bármilyen előfeltételek?
Igen, vqan néhány dolog, amelyet be kell állítania a kötegeket egyesítő eszközök használata előtt. Az alábbi táblázatban található ezeknek az előfeltételeknek az ismertetése.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Oldal</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Naplónevek, készlet</td>
<td>Létre kell hoznia egy alapértelmezés szerint használt, anyagjegyzék típusú naplónevet a készletnaplóba történő kötegegyesítés feladásakor. Nem kötelező, de ajánlott: Meghatározhatja, hogy a foglalások automatikusan létrejöjjenek a kötegegyesítés készletnaplóba történő átvitelekor. Ellenkező esetben fennáll annak a veszélye, hogy módosítani lehet az aktuális készletet a kötegegyesítés részleteinek beállítása és a napló feladása után. A naplónévre vonatkozó automatikus foglalás engedélyezéséhez válassza ki az <strong>Automatikus</strong> lehetőséget a <strong><strong>Foglalás</strong></strong> mezőben.</td>
</tr>
<tr class="even">
<td>Készlet- és raktárkezelési paraméterek</td>
<td>Meg kell adnia a készletnapló alapértelmezett naplónevét.</td>
</tr>
<tr class="odd">
<td>Kiadott termékek</td>
<td>Íme a cikkre vonatkozó javasolt beállítások:
<ul>
<li>Az egyesített kötegekre vonatkozó kötegszámok automatikus létrehozásához hozzá kell rendelnie a kiadott terméket a kötegszámcsoportjához. Manuálisan is megadhat egy kötegszámot egyesített köteg létrehozásakor, vagy választhat egy meglévő kötegszámot. Ha egy meglévő kötegszámot választ ki, győződjön meg arról, hogy a kijelölt köteg nem szerepel semmilyen készlettranzakcióban.</li>
<li>Ha az eltarthatósági idő vagy a szavatossági dátum értéket használja a kiadott termékhez, az egyesített köteg dátumát a <strong>Kötegegyesítés dátumának számítása</strong> mezőben történő kiválasztás alapján számítják ki. Az alábbi lehetőségek közül választhat:
<ul>
<li><strong>Legkorábbi</strong> – A számítás azon a legkorábbi dátumon alapszik, amely az egyesített köteghez kiválasztott forráskötegre vonatkozóan van megadva.</li>
<li><strong>Legkésőbbi</strong> – A számítás azon a legkésőbbi dátumon alapszik, amely az egyesített köteghez kiválasztott forráskötegre vonatkozóan van megadva.</li>
<li><strong>Manuális</strong> – Nem történik számítás. Ha a dátum megegyezik az összes forráskötegen, az a dátum a javaslott. Ezt a dátumot meg lehet változtatni. Ha a dátum nem azonos a forráskötegeken, manuálisan is megadhatja a dátumot.</li>
</ul></li>
</ul></td>
</tr>
<tr class="even">
<td>Kötegszámcsoport</td>
<td>Nem kötelező: Kötegszám létrehozásakor egyesített köteg készítésekor kötegszámcsoportot kell rendelnie a kiadott termékhez. Ellenkező esetben a kötegszámot manuálisan is megadhatja.</td>
</tr>
</tbody>
</table>

## <a name="when-might-i-want-to-merge-batches-of-inventory"></a>Mikor lehet egyesíteni a készlet kötegeit?
Íme néhány példa azokra az esetekre, amikor ajánlatos egyesíteni a kötegeket:

-   Mivel Sanyi átnézte a raktárját, észrevette, hogy ugyanabból a cikkből számos köteg alacsony mennyiséget tartalmaz. Több új szállítmányt is vár és rájön, hogy területet szabadíthat fel, ha egyesíti a páratlan mennyiségeket egy új kötegben.
-   Sanyi kap egy készletet és kombinálni szeretné az új köteget az egyik meglévővel annak érdekében, hogy a meglévő köteg kötegattribútum értékét feljavítsa. Ha így jár el, új köteget hoz létre.

## <a name="can-i-merge-batches-across-sites-and-legal-entities"></a>Egyesíthet kötegeket más telephelyekről és mása jogi személyektől?
Nem, csak azokat a kötegeket lehet egyesíteni, amelyek ugyanazon a webhelyen vannak és raktár tárolási dimenzióval rendelkeznek egy jogi személyben. Azonban az egyesített köteghez más helyet és raklap-azonosítót is megadhat.

## <a name="can-i-merge-partial-quantities"></a>Egyesíthetem a részleges mennyiségeket?
Ne, csak a kötegek teljes mennyiségét egyesítheti. A kötegegyesítés funkcióit készletfunkcióként alkalmazzák, és nem pedig termelési funkcióként.

## <a name="what-if-the-batches-have-different-batch-attribute-values"></a>Mi történik, ha a kötegek különböző kötegattribútum-értékekkel rendelkeznek?
Amikor kiválasztja a forráskötegeket az egyesített kötegekben történő kombináláshoz, a Supply Chain Management ellenőrzi, hogy az összeg köteg rendelkezik-e jellemzőkkel vagy attribútumértékekkel. Amikor az attribútumértékek megegyeznek, javasolnak egy értéket az egyesített köteghez. Ez az érték módosítható. A nem azonos attribútum értékek az egyesített kötegre vonatkozó üres mezők, és azoknak az értékeit manuálisan lehet megadni. Ha az attribútum értékre vonatkozó kötegattribútum típusa egy egész vagy egy tört szám, és az érték nem azonos az összes forráskötegre vonatkozóan, akkor az értéket egy súlyozott átlagszámítás segítségével számítják ki. A kiszámított értéket felfelé vagy lefelé lesz kerekítve a legközelebbi növekményre. Ha az érték üres a forráskötegben, a köteg és a mennyisége nem szerepel a számításban. **Példa** A következő példa bemutatja az egyesített kötegre vonatkozó súlyozott átlag számítását. A forráskötegek közül kettő rendelkezik üres értékkel egy olyan kötegattribútum típussal, amely egész. A következő attribútum van a forráskötegekhez rendelve.

| Attribútum | Minimum | Növelés | Maximum |
|-----------|---------|-----------|---------|
| Osztály     | 3       | 3         | 30      |

A forráskötegek a következő attribútumértékekkel rendelkeznek az **Osztály köteg** attribútumban.

| Köteg | Mennyiség | Attribútum | Attribútumérték |
|-------|----------|-----------|-----------------|
| B1    | 10       | Osztály     | Üres           |
| B2    | 15.       | Osztály     | 15.              |
| B3    | 20       | Osztály     | 20              |
| B4    | 25       | Osztály     | Üres           |
| B5    | 30       | Osztály     | 25              |

Ha ezeket a kötegeket összeadja forráskötegenként, akkor a következő értékeket az egyesített köteghez rendelik hozzá.

| Köteg | Mennyiség | Attribútum | Attribútumérték |
|-------|----------|-----------|-----------------|
| B6    | 100      | Osztály     | 21              |

A B1 és a B4 kötegek értékei és mennyiségei nem tartoznak bele a súlyozott átlag számításába. Emiatt az egyesített köteg értékeinek kiszámítása a következőképpen történik.

| Érték | Mennyiség (súly)                              | Relatív súly | Relatív súly × Érték                                               |
|-------|------------------------------------------------|-----------------|-----------------------------------------------------------------------|
| 15.    | 15.                                             | 0,230769231     | 3,461538462                                                           |
| 20    | 20                                             | 0,307692308     | 6,153846154                                                           |
| 25    | 30                                             | 0,461538462     | 11,53846154                                                           |
|       | **Összesen:** 65, ami a súlyok összege |                 | **Összesen:** 21.5384615, ami kerekítve 21 (a legközelebbi növekmény) |

## <a name="what-if-the-batches-have-different-batch-dates"></a>Mi történik, ha a kötegek különböző kötegdátumokkal rendelkeznek?
Ha a kötegek különböző kötegdátumokkal rendelkeznek, akkor a dátumok egy részét a **Kötegelt dátumok** csoportban található érték alapján számítják ki a **Köteg egyesítése** lap **Egyesített Köteg** gyorslapján. A rendszer a **Dátumok egyesítése** csoportban lévő mezőkre vonatkozó értékeket számítja ki. Ezek az értékek a gyártási dátumot, a lejárati dátumát, az ajánlott eltarthatósági dátumot, és a szavatosság dátumot tartalmazzák. A dátumok számítása a cikk beállításai alapján történik a **Megjelent termék részletei** lap **Cikk adatai** mezőcsoportban. Módosíthatja vagy manuálisan is megadhatja az értékeket. Semmilyen más dátumra vonatkozóan nem történik számítás. Ez az elv vonatkozik a kötegattribútum-értékekre is. Ha az összes forrásköteg dátuma megegyezik, ezt a dátumot javasolja a rendszer az egyesített köteghez. Ha a dátum nem egyezik meg az összes forráskötegre vonatkozóan, akkor üres a dátum az egyesített kötegben, és manuálisan adhatja meg az értékét.

## <a name="what-if-the-dimensions-are-different-on-the-batches-that-i-want-to-merge"></a>Mi történik, ha az egyesítendő kötegek dimenziói különbözőek?
A következőképpen történik a termékdimenziók, a nyomon követési dimenziók és a tárolási dimenziók kezelése:

-   **Termékdimenziók** – A kijelölt elemhez tartozó összes termékdimenziónak azonosnak kell lennie. Nem egyesítheti a kötegeket a termékdimenziók között.
-   **Nyomon követési dimenziók** – Az új kötegszám automatikusan létrejön, ha kötegszámcsoport meg van adva a cikkre vonatkozóan. Ha nincs kötegszámcsoport hozzárendelve egy cikkhez, kiválaszthat egy meglévő köteget vagy manuálisan adhatja meg a számot. A sorozatszámok a forráskötegből átkerülnek az egyesített köteg készletnaplósoraiba.
-   **Tárolási dimenziók** – A webhelynek és a raktár tárolási dimenzióinak meg kell egyeznie az összes forráskötegre és az egyesített kötegre vonatkozóan. Azonban az egyesített köteghez új helyet és raklap-azonosítót is megadhat.

## <a name="how-does-posting-work"></a>Hogyan működik a feladás?
A feladási folyamat kétféleképpen történik, attól függően, hogy használja-e a jóváhagyási folyamatot a naplókhoz. Az **Átvezetés naplóba** és a **A kötegegyesítés feladása** műveletek segítségével a kötegegyesítést továbbíthatja a naplóra, ahol ellenőrizhető és feladható, vagy közvetlenül feladható kötegegyesítés. A két művelet közötti fő különbség az, hogy a naplóba való átvitel nem adja fel a kötegegyesítést. Mindkét művelet egy új köteget hoz létre, ha nincs kiválasztva egy meglévő köteg, frissíti az összes kötegadatot és kötegattribútum-értéket, és egy készletnaplót hoz létre.

-   **Átvezetés naplóba** – Átvezeti a kötegegyesítés adatait egy új készletnaplóba. Ha beállította az automatikus foglalásokat, a forráskötegek mennyiségei le vannak foglalva. A kötegegyesítés adatait nem lehet módosítani. A kötegegyesítés módosításához törölnie kell a naplót. A naplót olyan feladatként is használhatja, amelyet egy másik alkalmazottnak kell később végrehajtania. A naplósorhoz tartozó kötegmennyiség foglalása védett. Ez a felosztás lehetővé teszi, hogy a minőségi tervező vagy egy raktár vezetője a saját alkalmazottai számára feladatokat hozzon létre.
-   **A készletköteg-egyesítés feladása** – A kötegegyesítés közvetlen feladása. Ez a művelet a tényleges egyesítés megtörténte után hajtható végre.

Jóváhagyhatja a kötegegyesítés készletnaplóját **Az összes kötegegyesítés** listaoldalról. Kattintson a **Napló** &gt; **Feladás** elemre. A napló feladása után az egyesített köteg részletei nem módosíthatók. Miután a kötegegyesítést átadja egy készletnaplóba csak akkor módosíthatja annak részleteit, ha törli a naplót.

## <a name="after-i-merged-a-catchweight-item-why-cant-i-see-the-catchweight-information-in-the-inventory-journal"></a>Miután egyesítettem a tényleges súllyal rendelkező cikkeket, miért nem látszik a tényleges súly adat a készletnaplóban?
Ugyanúgy egyesítheti a tényleges súllyal rendelkező cikkek kötegeit, mint minden más cikket. Azonban a tényleges súly adaton nem jelennek meg a készletnaplóban. Ajánlatos a tényleges súly adatok ellenőrzése a kötegegyesítés készletnaplóba történő átvitele előtt.
