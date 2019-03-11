---
title: Raktári munkairányelvek
description: A raktári munkairányelvek szabályozzák, hogy a gyártási raktári folyamatai létrehoznak-e raktári munkát a munkarendelés-típus, a készlethely és a termék alapján.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 196561
ms.assetid: cbf48ec6-1836-48d5-ad66-a9b534af1786
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 0710eac8daba7f51f6b5d1522476b812a130960d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/29/2019
ms.locfileid: "325595"
---
# <a name="warehouse-work-policies"></a>Raktári munkairányelvek

[!include [banner](../includes/banner.md)]

A raktári munkairányelvek szabályozzák a Microsoft Dynamics 365 for Finance and Operations rendszerben, hogy a gyártási raktári folyamatai létrehoznak-e raktári munkát a munkarendelés-típus, a készlethely és a termék alapján.

Ez a munka-irányelv szabályozza, hogy létrejöjjön-e raktári munka a gyártás raktári folyamataihoz. A munka-irányelvet a **munkarendelési típusok**, egy **készlethely** és egy **termék** kombinációjának segítségével állíthatja be. Például az L0101 termék a jelentés szerint elkészült leszállításra a 001. helyre. A késztermék később egy másik termelési rendelésben kerül felhasználásra a 001. kimeneti helyen. Ebben az esetben beállíthat egy munka-irányelvet annak megakadályozására, hogy munka jöjjön létre a késztermék betárolására, amikor az L0101 termék úgy szerepel a jelentésben, mint amely elkészült leszállításra a 001. helyre. A munka-irányelv egy egyéni entitás, amelyet a következő információk segítségével lehet leírni:

-   **Munka-irányelv neve** (a munka-irányelv egyedi azonosítója)
-   **Munkarendelési típusok** és **A munka létrehozásának módszere**
-   **Készlethelyek**
-   **Termékek**

## <a name="work-order-types"></a>Munkarendelés típusai
A következő munkarendelési típusok közül választhat:

-   Késztermékek betárolása
-   Társ- és melléktermék betárolása
-   Nyersanyag kitárolása

A **Munka létrehozásának módszere** mező értéke **Soha**. Ez az érték azt jelzi, hogy a munka-irányelv megakadályozza, hogy raktárkezelési munka jöjjön létre a kiválasztott munkarendelési típushoz.

## <a name="inventory-locations"></a>Készlethelyek
Kiválaszthatja a helyet, amelyre a munka-irányelv vonatkozik. Ha nincs hely társítva a munka-irányelvhez, a munka-irányelv nem vonatkozik semmilyen folyamatra. A **Helyek** lapon is kiválaszthatja az adott helyre vonatkozó munka-irányelvet, illetve törölheti a kijelölést.

## <a name="products"></a>Termékek
Kiválaszthatja egy terméket, amelyre a munka-irányelv vonatkozik. A munka-irányelv vonatkozhat az összes termékre vagy a kijelölt termékekre.

## <a name="example"></a>Példa
A következő példában két termelési rendelés szerepel: a PRD-001 és a PRD-00*2*. A PRD-001 termelési rendeléshez egy **Összeszerelés** nevű művelet tartozik, ahol az SC1 termék a jelentés szerint elkészült leszállításra az O1 helyre. A PRD-002 termelési rendeléshez egy **Festés** nevű művelet tartozik, ami felhasználja az SC1 terméket a O1 helyről. A PRD-002 termelési rendelés RM1 nyersanyagot is felhasznál az O1 helyről. Az RM1 tárolása a BULK-001 raktári helyszínen történik, és kitárolásra kerül az O1 helyre a nyersanyag-kitárolási raktári munka segítségével. A kitárolási munka akkor jön létre, amikor a PRD-002 termelés kiadásra kerül. 

[![Raktári munkairányelvek](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png) 

Amikor raktári munka-irányelv konfigurálását tervezi ehhez az esethez, vegye figyelembe a következő információkat:

-   A késztermékek betárolására vonatkozó raktári munkára nincs szükség, ha az SC1 terméket úgy szerepelteti a jelentésben, mint amely a PRD-001 termelési rendelésből elkészült, és az O1 helyre került. Ennek oka, hogy a PRD-002 termelési rendelés **Festés** művelete SC1-et használ fel ugyanazon a helyen.
-   A nyersanyag kitárolására vonatkozó raktári munkára szükség van, hogy az RM1 nyersanyagot át lehessen helyezni a BULK-001 raktári helyszínről az O1 helyre.

Íme egy példa a munka-irányelvre, amelyet be lehet beállítani ezen szempontok alapján.


|                                       |                                       |
|---------------------------------------|---------------------------------------|
| <strong>Munkairányelv neve</strong><br> | <strong>Munkarendelés típusai</strong><br> |
|         Nincs betárolás a 01 esetében          |     - Késztermék betárolása<br>      |
|                                       |    <strong>Helyek</strong><br>     |
|                                       |                 - O1                  |
|                                       |    <strong>Termékek</strong> <br>     |
|                                       |                 - SC1                 |

Az alábbi eljárások lépésről lépésre ismertetik, hogyan lehet a raktári munka-irányelvet beállítani ehhez az esethez. Egy beállítási minta is ismertetésre kerül, amely azt mutatja meg, hogyan lehet egy jelentésben egy termelési rendelést készként szerepeltetni, ahol a leszállítás egy olyan helyre történik, amelynek szabályozása nem azonosítótáblán alapul.

## <a name="set-up-a-warehouse-work-policy"></a>Raktári munka-irányelv beállítása
A raktárkezelési folyamatok nem mindig tartalmazzák a raktári munkát. A munka irányelveinek használatával megakadályozhatja a nyersanyag kitárolására és a befejezett termékek betárolására vonatkozó munka létrehozását egy termékkészletre vonatkozóan az adott helyeken. Az USMF bemutatócég adatai kerültek felhasználásra a jelen eljárás létrehozásához. 

LÉPÉS (21)

|     |                                                                            |
|-----|----------------------------------------------------------------------------|
| 1.  | Ugorjon a Raktárkezelés &gt; Beállítás &gt; Munka &gt; Munkairányelvek pontra.        |
| 2.  | Kattintson az Új lehetőségre.                                                                 |
| 3.  | A Munkairányelv neve mezőbe írja be a „Nincs betárolási munka” szöveget.                    |
| 4.  | Kattintson a Mentés gombra.                                                                |
| 5.  | Kattintson a Hozzáadás gombra.                                                                 |
| 6.  | A listában jelölje meg a kiválasztott sort.                                        |
| 7.  | A Munka rendelési típusa mezőben válassza ki a „Késztermékek betárolása” szöveget.            |
| 8.  | Kattintson a Hozzáadás gombra.                                                                 |
| 9.  | A listában jelölje meg a kiválasztott sort.                                        |
| 10. | A Munka rendelés típusa mezőben válassza ki a „Társtermék és melléktermék betárolása” lehetőséget. |
| 11. | Bontsa ki a Készlethelyek szakaszt.                                    |
| 12. | Kattintson a Hozzáadás gombra.                                                                 |
| 13. | A listában jelölje meg a kiválasztott sort.                                        |
| 14. | Írja be az „51” értéket a Raktár listájában.                                         |
| 15. | A Hely mezőben adjon meg vagy válasszon ki a „001” értéket.                              |
| 16. | Bontsa ki a Termékek szakaszt.                                               |
| 17. | A Termékkiválasztás mezőben válassza ki a „Termékaltípus” lehetőséget.                         |
| 18. | Kattintson a Hozzáadás gombra.                                                                 |
| 19. | A listában jelölje meg a kiválasztott sort.                                        |
| 20. | Az Elemszám mezőben adjon meg, vagy válasszon ki „L0101” értéket.                         |
| 21. | Kattintson a Mentés gombra.                                                                |

## <a name="report-a-production-order-as-finished-to-a-location-that-isnt-license-platecontrolled"></a>Termelési megrendelés lejelentése készként egy olyan helyre, amelynek szabályozása nem azonosítótáblán alapul
Ez az eljárás egy olyan példát tartalmaz, amely azt mutatja meg, hogyan lehet egy jelentésben egy rendelést készként és leszállítottként szerepeltetni egy olyan helyen, amelynek szabályozása nem azonosítótáblán alapul. Az alkalmazható munkairányelvek ezen feladat előfeltételei. A korábbi eljárás a munka-irányelvek beállítását mutatja be. 

LÉPÉS (25)

<table>
<tbody>
<tr>
<td colspan="3"><strong>Részfeladat: A kimeneti helyek beállítása.</strong></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td>Ugrás a Szervezet felügyelete &gt; Erőforrások &gt; Erőforráscsoportok részhez.</td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td>Válassza ki a listában az „5102” erőforráscsoportot.</td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td>Kattintson a Szerkesztés lehetőségre.</td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td>Adja meg a Kimeneti raktár mezőben az „51” értéket.</td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td>Adja meg a Kimeneti hely mezőben az „001” értéket.</td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td>A 001 Hely nem egy azonosítótáblás szabályozású hely. A nem azonosítótáblás kimeneti helyet csak akkor állíthatja be, ha a megfelelő munkairányelveket létrehozták a helyre vonatkozóan.</td>
</tr>
<tr>
<td colspan="3"><strong>Részfeladat: A Termelési jelentés létrehozása és készként történő jelentése.</strong></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td>Zárja be a lapot.</td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td>Ugrás a Gyártásvezérlés &gt; Termelési rendelések &gt; Minden termelési rendelésre.</td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td>Kattintson az Új termelési rendelés lehetőségre.</td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td>Adja meg a „L0101” értéket a Cikkszám mezőben.</td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td>Kattintson a Létrehozás lehetőségre.</td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td>A Művelet panelen kattintson a Termelési rendelés elemre.</td>
</tr>
<tr>
<td></td>
<td>7.</td>
<td>Kattintson a Becslés elemre.</td>
</tr>
<tr>
<td></td>
<td>8.</td>
<td>Kattintson az OK gombra.</td>
</tr>
<tr>
<td></td>
<td>9.</td>
<td>Kattintson a Start parancsra.</td>
</tr>
<tr>
<td></td>
<td>10.</td>
<td>Kattintson az Általános fülre.</td>
</tr>
<tr>
<td></td>
<td>11.</td>
<td>Az automatikus BOM-felhasználás mezőben válassza ki a „Soha” értéket.</td>
</tr>
<tr>
<td></td>
<td>12.</td>
<td>Kattintson az OK gombra.</td>
</tr>
<tr>
<td></td>
<td>13.</td>
<td>Kattintson a Jelentés készként lehetőségre.</td>
</tr>
<tr>
<td></td>
<td>14.</td>
<td>Kattintson az Általános fülre.</td>
</tr>
<tr>
<td></td>
<td>15.</td>
<td>Válassza ki az Igen lehetőséget a Hiba elfogadása mezőben.</td>
</tr>
<tr>
<td></td>
<td>16.</td>
<td>Kattintson az OK gombra.</td>
</tr>
<tr>
<td></td>
<td>17.</td>
<td>A Műveleti panelen kattintson a Raktár elemre.</td>
</tr>
<tr>
<td></td>
<td>18.</td>
<td>Kattintson a Munka részletei lehetőségre.</td>
</tr>
<tr>
<td></td>
<td>19.</td>
<td>Amikor a termelési rendelést készként jelentették, a rendszer nem hozott létre munkát a betárolásra. Ennek az az oka, hogy a munkairányelveket úgy határozzák meg, hogy megakadályozza a munka létrehozását, amikor a rendszer készként jelenti a L0101 terméket a 001 helyen.</td>
</tr>
</tbody>
</table>



