---
title: Képletszerkesztő
description: Ez a témakör azt ismerteti, hogy a képletszerkesztő segítségével hogyan elemezhetők és tarthatók karban a receptúrák a fanézetben
author: cvocph
manager: tfehr
ms.date: 06/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PlanActivity, ReqSupplyDemandSchedule
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8778d6a4d834af2151e0bced0b0f27d98f088a34
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429455"
---
# <a name="formula-designer"></a>Képletszerkesztő

[!include [banner](../includes/banner.md)]

Ez a témakör azt ismerteti, hogy a képletszerkesztő segítségével hogyan elemezhetők és tarthatók karban a receptúrák a fanézetben

Amikor megnyitja a **Képletszerkesztő** oldalt a **Kiadott termékek** oldalon, a fában a bal oldali ablakban megjelenik a társtermékek listája, és a kiadott termékhez tartozó összetevők hierarchiája. A szerkezet alapja a kiválasztott cikkre és összetevőire vonatkozó aktív és jóváhagyott receptúrahierarchia, a cikk alapértelmezett rendelési webhelye és a tényleges dátum.

A **Beállítások** gombra kattintva különböző konfigurációkat állíthat be, és eldöntheti, hogy milyen információkat kíván megjeleníteni a fa soraiban.

Kattintson a **Szűrő** menüpontra a kezdeti kijelölés megadásához a nézetben. Ha a megjelenési elvet **Kiválasztott/Aktív** vagy **Kijelölt** értékre állítja, kiválaszthat egyéni receptúrát vagy útvonalverziót a nézetben való használathoz. Kiválaszthat nem jóváhagyott és inaktív receptúraverziót a képletszerkesztőben való megjelenítéshez és karbantartáshoz.  

> [!NOTE]
> Ha a **Képletszerkesztőt** az **Anyagjegyzékek** listaoldalról nyitja meg, nem jelennek meg az útvonaladatok. A receptúra vagy útvonal verziójának kiválasztása jelenleg a képletszerkesztő összes példányára vonatkozik.  

Az alábbi szakaszokban az Anyagjegyzék-tervezőben elérhető funkciók leírása olvasható.

## <a name="analyze-a-formula-structure-by-using-the-formula-designer"></a>A receptúrastruktúra a képletszerkesztővel elemezhető
A képlettervező két részből áll:

-   A receptúrastruktúra fanézete.
-   A részletek szakasz, amely a kijelölt adatok részleteit jeleníti meg. Ha a fanézetben kijelöl egy csomópontot, a gyorslapok a részletek szakaszban frissülnek a csomópont alapján:
    -   **Receptúrasor adatai** – A fanézetben kijelölt receptúrasor adatait mutatja.
    -   **Cikkadatok** – A fő cikk vagy a kiválasztott csomópontban használt cikk adatait mutatja. A kijelölt cikk karbantartásához kattintson a **Kibocsátott termék szerkesztése** menüpontra.
    -   **Receptúra** – Annak a receptúrának a fejlécét jeleníti meg, amely a kiválasztott csomóponthoz kapcsolódik.
    -   **Útvonal** – Annak az útvonalnak a fejlécét jeleníti meg, amely a kiválasztott csomóponthoz kapcsolódik.
    -   **Útvonalműveletek** – Az útvonalműveletek előnézetét jeleníti meg. Amikor egy bizonyos művelethez hozzárendelt anyagjegyzéksor (BOM-sor) ki van jelölve, akkor **Műveletekhez szükséges összetevő** megjelölést kap.

## <a name="select-a-formula-and-route"></a>Válassza ki a receptúrát és az útvonalat
A receptúrára és az útvonalra érvényes szűrő megjelenik a képlettervező fejlécében. A **Szűrő** párbeszédpanel használatával megváltoztathatja a szűrőt. Az alábbi táblázat a párbeszédpanel mezőit szemlélteti.

<table>
<thead>
<tr class="header">
<th>Mező</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Termékdimenziók</td>
<td>Ha a kijelölt késztermék alaptermék, meghatározhatja az aktív termékdimenziókat a fő kiválasztásra. Megjegyzendő, hogy ha nem alaptermék termék esetében nyitja meg a képletszerkesztőt, termékdimenziókat nem lehet kiválasztani a <strong>Szűrő</strong> párbeszédpanelen.</p></td>
</tr>
<tr class="even">
<td>Telephely</td>
<td>Módosítsa a helyet, ahol a receptúrafa megjelenik. Az alapértelmezett hely a befejezett cikk alapértelmezett készlethelye.</td>
</tr>
<tr class="odd">
<td>Megjelenítési szabály</td>
<td><p>Válassza ki az aktuális receptúrastruktúrára és az aktuális útvonalra vonatkozó verziómegjelenítési szabályt:</p>
<ul>
<li>Ha a szabály <strong>Aktív</strong> vagy <strong>Kijelölt/Aktív</strong> értékre van állítva, megvan az erre a dátumra érvényes receptúra- vagy útvonalverzió.</li>
<li>Ha a szabály <strong>Kijelölt/Aktív</strong> vagy <strong>Kijelölt</strong> értékre van állítva, kiválaszthat egy receptúra- vagy útvonalverziót, ha a <strong>Receptúra</strong> &gt; <strong>Receptúraverziók</strong> vagy az <strong>Útvonal</strong> &gt; <strong>Útvonalverziók</strong> menüpontra kattint.</li>
</ul></td>
</tr>
<tr class="even">
<td>Verziószám dátuma</td>
<td>Adja meg a receptúra és az útvonal verziójának dátumát. A verzió határozza meg, mely receptúraverziók vannak használatban egy adott időpontban, a receptúraverzió beállításainál meghatározott verziódátumok alapján.</td>
</tr>
<tr class="odd">
<td>Forrásmennyiség</td>
<td>A verziók szűrése egy adott &quot;forrás&quot; mennyiség használatával. Ha megad egy értéket, különböző receptúra- és útvonalverziókat választ ki.</td>
</tr>
<tr class="even">
<td>Csak az érvényesek jelenjenek meg</td>
<td>Ha be van jelölve a jelölőnégyzet, a fastruktúra csak az érvényes dátummal rendelkező receptúrasorokat mutatja. Kattintson jobb gombbal vagy duplán a receptúrasorra a <strong>Receptúrasor szerkesztése</strong> oldal megnyitásához, ahol az adott receptúrasorra vonatkozó érvényességi időpontokat láthatja.</td>
</tr>
</tbody>
</table>

Ha a képletszerkesztőt egy- vagy többszintű kitárolási értékkel rendelkező látszólagos típusok áttekintésére vagy szerkesztésére használja, a felső cikkhez rendelt útvonal általában a teljes receptúrahierarchiára is kiterjed. Az áttekintés egyszerűsítéséhez zárolhatja a felső szintű útvonalat a nézetben, ha a **Megtekintés** &gt; **Útvonal zárolása** menüpontra kattint. Az útvonal zárolásának feloldásához kattintson a **Megtekintés** &gt; **Útvonal feloldása** menüpontra.

## <a name="add-and-edit-formulas-and-formula-lines"></a>Receptúrák és receptúrasorok hozzáadása és szerkesztése
Használja az **Anyagjegyzéksorok** vagy a **Receptúra** funkciókat receptúrasorok és receptúrák módosítására. Ha kiválaszt a fában egy csomópontot, a csomópont típusa határozza meg, milyen funkciók érhetők el.

| Funkció                            | Leírás                                                                                               | Csomóponttípus és feltételek |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------|--------------------------|
| Anyagjegyzéksorok &gt; Szerkesztés                 | Párbeszédpanel megnyitása, ahol szerkeszteni lehet a receptúrasor attribútumait.                                         | Ez a funkció csak akkor érhető el, ha ki van jelölve egy receptúrasor-csomópont. |
| Anyagjegyzéksorok &gt; Törlés               | Receptúrasor törlése a kiválasztott receptúrából.                                                          | Ez a funkció csak akkor érhető el, ha ki van jelölve egy receptúrasor-csomópont, és a receptúra nincs zárolva. |
| Anyagjegyzéksorok &gt; Hozzáadás a sor előtt      | Párbeszédpanel megnyitása, ahol kiválaszthatja a kiválasztott receptúrasor előtt szerepeltetendő termékváltozatot.     | Ez a funkció csak akkor érhető el, ha ki van jelölve egy receptúrasor-csomópont. |
| Anyagjegyzéksorok &gt; Hozzáadás anyagjegyzék-összetevőhöz | Párbeszédpanel megnyitása, ahol kiválaszthatja a kiválasztott receptúra végén szerepeltetendő termékváltozatot.   | Ez a funkció csak akkor érhető el, ha a kijelölt csomópont rendelkezik kijelölt receptúrával. Ha ez a funkció nem elérhető, egy receptúraverzió hiányozhat a kiválasztott cikkváltozathoz. Ebben az esetben kattintson a **Receptúra** &gt; **Verzió létrehozása** menüpontra a hiányzó verzió létrehozásához a kiválasztott csomópontban. |
| Anyagjegyzéksorok &gt; Hozzáadás a sor után       | Párbeszédpanel megnyitása, ahol kiválaszthatja a kiválasztott receptúrasor után szerepeltetendő termékváltozatot.      | Ez a funkció csak akkor érhető el, ha ki van jelölve egy receptúrasor-csomópont. |
| Receptúra &gt; Verzió létrehozása         | Új receptúraverzió vagy receptúra létrehozása a kiválasztott csomópont termékváltozatához.                     | Ez a funkció akkor érhető el, ha a kiválasztott receptúrasor-csomópont össze van kapcsolva egy cikkel, amelynek a termelési típusa **Anyagjegyzék** vagy **Receptúra**. |
| Receptúra &gt; Számítás            | Párbeszédpanel megnyitása, ahol a költség- vagy eladásiár-számítást futtathatja a kiválasztott termékváltozatnál. | Ez a funkció akkor érhető el, ha a kijelölt csomópont kapcsolódik egy receptúraverzióhoz. |
| Receptúra &gt; Ellenőrzés                  | A kiválasztott receptúra érvényesítése és ellenőrzése.                                                                  | Ez a funkció akkor érhető el, ha a kijelölt csomópont kapcsolódik egy receptúraverzióhoz. |

## <a name="configuring-the-tree-view"></a>A fa nézet beállítása
Kattintson a **Beállítás** menüpontra a képletszerkesztő fanézetében megjelenő információk testreszabásához.


| Mezőcsoport |                                                                          Leírás                                                                          |
|-------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     Anyagjegyzék     | A jelölőnégyzetek segítségével válassza ki a feltételeket, amelyek a faszerkezetben jelennek meg. A képletszerkesztő mindkét lap alján megjeleníti a kiválasztott kritériumokat. |
|    Útvonal    |                                           A jelölőnégyzetek segítségével válassza ki a feltételeket, amelyek az útvonalak között megjelennek.                                           |

