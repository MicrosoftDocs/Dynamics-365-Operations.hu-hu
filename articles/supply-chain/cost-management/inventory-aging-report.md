---
title: Készletkorosítási jelentés – példák és logika
description: Ez a témakör néhány példát mutat be, amelyek a készletkorosítási jelentés eredményeinek értelmezését mutatják be.
author: RichardLuan
manager: tfehr
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: a6e708e4dc818f20fc8d835053da75c2fe9c98f6
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759544"
---
# <a name="inventory-aging-report-examples-and-logic"></a>Készletkorosítási jelentés – példák és logika

[!include [banner](../includes/banner.md)]

Ez a témakör néhány példát mutat be, amelyek a **Készletkorosítási** jelentés eredményeinek értelmezését mutatják be. Ez a jelentés egy kiválasztott cikk vagy cikkcsoport aktuális mennyiségét és készletérték-adatait több időszakra bontja szét. Ez a témakör a jelentés belső logikáját is bemutatja.

Az ebben a témakörben szereplő példák a standard **Készlet-korosítási** jelentés eredményeinek megjelenítését mutatják be. Általánosságban azonban azt ajánljuk, hogy a jelentés [Készletkorosítási jelentés tárhely](inventory-aging-report-storage.md) változatát használja, különösen, ha sok cikket és raktárat kell feldolgozni. A készlet-korosítási jelentés tárolója menti a létrehozott jelentéseket, az eredményeket interaktív lapként és diagramként jeleníti meg, valamint minden elmentett jelentés exportálását is lehetővé teszi.

## <a name="sample-data-that-is-used-in-these-examples"></a>A példákban használt mintaadatok

Az ebben a témakörben szereplő példák az ebben a szakaszban ismertetett minta tranzakciós adatokon alapulnak.

### <a name="storage-dimension-setup"></a>Tárolásidimenzió beállítása

A példarendszer a tárolási dimenziók következő beállítását tartalmazza.

| Név      | Aktív | Tényleges készlet | Pénzügyi készlet |
|-----------|--------|--------------------|---------------------|
| Webhely      | Igen    | Igen                | Igen                 |
| Raktár | Igen    | Igen                | Nincs                  |

### <a name="inventory-model"></a>Készletmodell

A példarendszer esetében a kiadott termékhez tartozó készletmodell *FIFO*, és a készletmodell-beállítás **Költségár** beállítása *Tartalmazza a fizikai értéket*.

### <a name="inventory-transactions"></a>Készlettranzakciók

A példarendszer a következő készlettranzakciókat tartalmazz a kiadott termékhez, amelynek cikkszáma *1000*.

| Hivatkozás      | Webhely | Raktár | Fogadás   | Kiadás | Tényleges dátum | Pénzügyi dátum | Mennyiség | Költség összege | Tényleges önköltségi érték |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| Beszerzési rendelés | 1    | 11        | Beszerezve |       | március 15.      | március 15.       | 10       | 1000       | 1000                |
| Beszerzési rendelés | 2    | 21        | Beszerezve |       | március 15.      | március 15.       | 10       | 2,000       | 2,000                |
| Beszerzési rendelés | 1    | 11        | Bevételezve  |       | április 15.      |                | 5        |             | 375                  |
| Átmozgatási rendelés | 1    | 11        |           | Eladva  | május 2.         | május 2.          | -5       | -458,33     | -458,33              |
| Átmozgatási rendelés | 1    | 12        | Beszerezve |       | május 2.         | május 2.          | 5        | 458.33      | 458.33               |
| Értékesítési rendelés    | 1    | 12        |           | Eladva  | május 3.         | május 3.          | -1       | -91,67      | -91,67               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a>Hogyan történik mennyiségek és az összegek számítása az egyes időszakokban

Az előző szakaszokban ismertetett mintaadatok használatával a következő beállításokkal rendelkező **Készlet-korosítási** jelentés futtatható:

- **Adott dátumtól:** *2020. május 9.*
- **Hely:** *Megtekintés*
- **Raktár:** *Nem*
- **Cikkszám:** *Összes*
- **Korosítási időszak:** Állítsa be ezt a mezőt havi időszakok generálásához.

Ebben az esetben a létrejövő jelentés tartalma a következő példához hasonlóan fog megjelenni.

<table>
<thead>
<tr>
    <th rowspan="2">Cikkszám</th>
    <th rowspan="2">Webhely</th>
    <th rowspan="2">Aktuális mennyiség</th>
    <th rowspan="2">Aktuális készlet értéke</th>
    <th rowspan="2">Készletérték mennyisége</th>
    <th rowspan="2">Készletérték</th>
    <th rowspan="2">Átlagos egységenkénti költség</th>
    <th colspan="2">2020/8/5 – 2020/1/5</th>
    <th colspan="2">2020/4/30 – 2020/4/1</th>
    <th colspan="2">2020/3/31 – 2020/3/1</th>
</tr>
<tr>
    <th>P1:Mennyiség</th>
    <th>P1:Összeg</th>
    <th>P2:Mennyiség</th>
    <th>P2:Összeg</th>
    <th>P3:Mennyiség</th>
    <th>P3:Összeg</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td></td>
    <td></td>
    <td>5.00</td>
    <td>458.33</td>
    <td>9.00</td>
    <td>825.00</td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10,00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>1000 összegek</strong></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,283.33</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>5.00</strong></td>
    <td><strong>458.33</strong></td>
    <td><strong>19</strong></td>
    <td><strong>2,825.00</strong></td>
</tr>
</tfoot>
</table>

Jegyezze fel a példajelentés következő adatait:

- A jelentésen megjelenő **Készletérték mennyiség**, **Készletérték** és **Átlagos egységköltség** értékei pénzügyi készletdimenzió értékei (**Telephely** ebben az esetben).

    Az 1- telephely esetében például a jelentés a következő adatokat jeleníti meg:

    - A **Készletérték-mennyiség** értéke *14* (= 10 + 5 – 5 + 5 – 1).
    - A **Készletértékérték** értéke *1283,33* (= 1000 + 375 – 458,33 + 458,33 – 91,67).
    - Az **Átlagos egységenkénti költség** *91,67*.
    - Az **Aktuális készlet** értékének és a **Mennyiség** értékét az egyes időszakokban a rendszer az **Átlagos egységenkénti** érték alapján számítja ki a program.

- A jelentés határozza meg az egyes időszakok készleten lévő mennyiségét az egyes időszakok összes bevételezett készletmennyiségének összesítésével. Ezt követően az először be, először ki (FIFO) elv alapján vonja le a teljes kiadott mennyiséget, függetlenül attól, hogy milyen készletmodell van használatban a cikkekhez.

Ha ismét ugyanazt a jelentést futtatja, de ezúttal a **Telephely** és **Raktár** mezőt is *Megtekintés* értékre állítja, akkor az új jelentés a következő példához hasonló lesz.

<table>
<thead>
<tr>
    <th rowspan="2">Cikkszám</th>
    <th rowspan="2">Webhely</th>
    <th rowspan="2">Raktár</th>
    <th rowspan="2">Aktuális mennyiség</th>
    <th rowspan="2">Aktuális készlet értéke</th>
    <th rowspan="2">Készletérték mennyisége</th>
    <th rowspan="2">Készletérték</th>
    <th rowspan="2">Átlagos egységenkénti költség</th>
    <th colspan="2">2020/8/5 – 2020/1/5</th>
    <th colspan="2">2020/4/30 – 2020/4/1</th>
    <th colspan="2">2020/3/31 – 2020/3/1</th>
</tr>
<tr>
    <th>P1:Mennyiség</th>
    <th>P1:Összeg</th>
    <th>P2:Mennyiség</th>
    <th>P2:Összeg</th>
    <th>P3:Mennyiség</th>
    <th>P3:Összeg</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>11</td>
    <td>10</td>
    <td>916.67</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td></td>
    <td></td>
    <td>5.00</td>
    <td>458.33</td>
    <td>5.00</td>
    <td>458.33</td>
</tr>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>12</td>
    <td>4</td>
    <td>366.67</td>
    <td>14</td>
    <td>1,283.33</td>
    <td>91.67</td>
    <td>4.00</td>
    <td>366.67</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td></td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10,00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>1000 összegek</strong></td>
    <td></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,283.33</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>4.00</strong></td>
    <td><strong>366.67</strong></td>
    <td><strong>5.00</strong></td>
    <td><strong>458.33</strong></td>
    <td><strong>15</strong></td>
    <td><strong>2,458.33</strong></td>
</tr>
</tfoot>
</table>

Ez alkalommal az 1. telephely két sorra van osztva, egy a 11-es raktárhoz, egy a 12-es raktárhoz. Ugyanakkor a **Készletérték mennyiség**, **Készletérték** és **Átlagos egységköltség** értékei nem változnak, mert a **Raktár** nem egy készletdimenzió.

Ezenkívül figyelje meg, hogy az 1. telephely mennyiségi felosztása eltérő. A rendszer az elsőként futtatott jelentésben figyelmen kívül hagyta az ugyanazon a telephelyen belül bekövetkezett átmozgatási rendelést, és levonta az értékesítési számla mennyiségét az 1. telephely **2020/3/31 – 2020/3/1** időszakából. Az új jelentésben azonban a rendszer levonja az értékesítési számla mennyiségét a **2020/5/8 – 2020/5/1** időszakra a 12. raktárban.

## <a name="effects-of-inventory-closing"></a>Készletzárás hatásai

Ha májusra futtatja a készletzárást futtatja, majd újra futtatja az előző jelentést, de az **Adott dátumtól** mező értéke *2020 május 31*, a következő eredményeket kapja:

- A program frissíti a **Készletérték** és az **Átlagos egységköltség** értékét.
- A program ennek megfelelően frissíti az **Aktuális készletérték** és az **Összeg** értéket az összes időszakra.

Az új jelentés az alábbi példához hasonlóan jelenik meg.

<table>
<thead>
<tr>
    <th rowspan="2">Cikkszám</th>
    <th rowspan="2">Webhely</th>
    <th rowspan="2">Raktár</th>
    <th rowspan="2">Aktuális mennyiség</th>
    <th rowspan="2">Aktuális készlet értéke</th>
    <th rowspan="2">Készletérték mennyisége</th>
    <th rowspan="2">Készletérték</th>
    <th rowspan="2">Átlagos egységenkénti költség</th>
    <th colspan="2">2020/5/31 – 2020/5/1</th>
    <th colspan="2">2020/4/30 – 2020/4/1</th>
    <th colspan="2">2020/3/31 – 2020/3/1</th>
</tr>
<tr>
    <th>P1:Mennyiség</th>
    <th>P1:Összeg</th>
    <th>P2:Mennyiség</th>
    <th>P2:Összeg</th>
    <th>P3:Mennyiség</th>
    <th>P3:Összeg</th>
</tr>
</thead>
<tbody>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>11</td>
    <td>10</td>
    <td>910.70</td>
    <td>14</td>
    <td>1,275.00</td>
    <td>91.07</td>
    <td>0,00</td>
    <td></td>
    <td>5.00</td>
    <td>455.36</td>
    <td>5.00</td>
    <td>455.36</td>
</tr>
<tr>
    <td>1000</td>
    <td>1</td>
    <td>12</td>
    <td>4</td>
    <td>364.29</td>
    <td>14</td>
    <td>1,275.00</td>
    <td>91.07</td>
    <td>4.00</td>
    <td>364.29</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td>1000</td>
    <td>2</td>
    <td></td>
    <td>10</td>
    <td>2,000.00</td>
    <td>10</td>
    <td>2,000.00</td>
    <td>200.00</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>10,00</td>
    <td>2,000.00</td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><strong>1000 összegek</strong></td>
    <td></td>
    <td></td>
    <td><strong>24.00</strong></td>
    <td><strong>3,275.00</strong></td>
    <td></td>
    <td></td>
    <td></td>
    <td><strong>4.00</strong></td>
    <td><strong>364.29</strong></td>
    <td><strong>5.00</strong></td>
    <td><strong>455.36</strong></td>
    <td><strong>15</strong></td>
    <td><strong>2,455.36</strong></td>
</tr>
</tfoot>
</table>
