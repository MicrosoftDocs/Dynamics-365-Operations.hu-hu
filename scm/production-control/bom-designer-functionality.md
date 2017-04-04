---
title: "Az anyagjegyzék-tervező szolgáltatás"
description: "Ez a cikk bemutatja, hogyan alkalmazza az anyagjegyzék tervezőlapot az anyagjegyzékek (BOM) fastruktúráinak tervezésére és az azokkal történő munkára. A Beállítások gombra kattintva különböző konfigurációkat állíthat be, és eldöntheti, hogy milyen információkat kíván megjeleníteni a fa soraiban."
author: YuyuScheller
manager: AnnBe
ms.date: 2015-12-08 21 - 09 - 22
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMDesigner
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 20981
ms.assetid: 2b92eec1-d28c-4965-9086-939c77b3c62b
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 2c98039c9fa8179408394f9f66b9fca0f8cad3fe
ms.lasthandoff: 03/29/2017


---

# <a name="bom-designer-functionality"></a>Az anyagjegyzék-tervező szolgáltatás

Ez a cikk bemutatja, hogyan alkalmazza az anyagjegyzék tervezőlapot az anyagjegyzékek (BOM) fastruktúráinak tervezésére és az azokkal történő munkára. A Beállítások gombra kattintva különböző konfigurációkat állíthat be, és eldöntheti, hogy milyen információkat kíván megjeleníteni a fa soraiban.

Ha megnyitja az **Anyagjegyzék-tervező** oldalt a **Kiadott termékek** oldalon, akkor megjelenik az aktív és a kiválasztott cikkre jóváhagyott anyagjegyzékek (AJ) hierarchiája, a cikk alapértelmezett rendelési helye, és a tényleges dátum.  

Kattintson a **Szűrő** menüpontra a kezdeti kijelölés megadásához a nézetben. Ha a megjelenési elvet **Kiválasztott/Aktív vagy kijelölt** értékre állítja, kiválaszthat egyéni anyagjegyzéket vagy útvonalverziót a nézetben való használathoz. Kiválaszthat nem jóváhagyott és inaktív anyagjegyzék-verziót az Anyagjegyzék-tervezőben való megjelenítéshez és karbantartáshoz.  

**Megjegyzés:** Ha az Anyagjegyzék-tervezőt az **Anyagjegyzékek** listaoldalról nyitja meg, nem jelennek meg az útvonaladatok. Jelenleg az anyagjegyzék vagy útvonalverzió kiválasztása az anyagjegyzék és útvonalverzió egyik tulajdonsága, és minden Anyagjegyzéktervező-példányra vonatkozik.  

Az alábbi szakaszokban az Anyagjegyzék-tervezőben a különböző füleken elérhető funkciók leírása olvasható.

## <a name="analyzing-a-bom-structure-by-using-the-bom-designer"></a>Anyagjegyzék-struktúra elemzése az Anyagjegyzék-tervező segítségével
Az Anyagjegyzék-tervező két részből áll:

-   Az anyagjegyzék-struktúra fanézete
-   A részletek szakasz, amely a kijelölt adatok részleteit jeleníti meg. Ha a fanézetben kijelöl egy csomópontot, a gyorslapok a részletek szakaszban frissülnek a csomópont alapján:
    -   **Anyagjegyzéksor adatai** – A fanézetben kijelölt anyagjegyzéksor adatait mutatja.
    -   **Cikkadatok** – A fő cikk vagy a kiválasztott csomópontban használt cikk adatait mutatja. A kijelölt cikk karbantartásához kattintson a **Kibocsátott termék szerkesztése** menüpontra.
    -   **Anyagjegyzék** – Azt az anyagjegyzéket jeleníti meg, amely a kiválasztott csomóponthoz kapcsolódik.
    -   **Útvonal** – Azt az útvonalat jeleníti meg, amely a kiválasztott csomóponthoz kapcsolódik.
    -   **Útvonalműveletek** – Az útvonalműveletek előnézetét jeleníti meg. Amikor egy bizonyos művelethez hozzárendelt anyagjegyzéksor ki van jelölve, akkor **Műveletekhez szükséges összetevő** megjelölést kap.

## <a name="selecting-a-bom-and-route"></a>Anyagjegyzék és útvonal kijelölése
Az anyagjegyzékre és az útvonalra érvényes szűrő megjelenik az Anyagjegyzék-tervező fejlécében. A **Szűrő** párbeszédpanel használatával megváltoztathatja a szűrőt. Az alábbi táblázat a párbeszédpanel mezőit szemlélteti.

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
<td>Ha a kijelölt késztermék alaptermék, meghatározhatja az aktív termékdimenziókat a fő kiválasztáshoz.<strong>Megjegyzés:</strong> ha olyan termékhez nyitja meg az Anyagjegyzék-tervezőt, amely nem alaptermék, nem lehet kiválasztani cikkdimenziókat a <strong>Szűrő</strong> párbeszédpanelen.</td>
</tr>
<tr class="even">
<td>Hely</td>
<td>Módosítsa a helyet, ahol az anyagjegyzékfa megjelenik. Az alapértelmezett hely a befejezett cikk alapértelmezett készlethelye.</td>
</tr>
<tr class="odd">
<td>Megjelenítési szabály</td>
<td>Válassza ki az aktuális anyagjegyzék-struktúrára és az aktuális útvonalra vonatkozó verziómegjelenítési szabályt:
<ul>
<li>Ha a szabály <strong>Aktív vagy Kijelölt/Aktív</strong> értékre van állítva, megvan az erre a dátumra érvényes anyagjegyzék vagy útvonalverzió.</li>
<li>Ha az elvet értéke <strong>kiválasztott/aktív vagy a kijelölt</strong>, kattintva választhat egy Anyagjegyzék-verziót vagy útvonalverzió <strong>AJ</strong>&gt;<strong>AJ-verziók</strong> vagy <strong>útvonal</strong>&gt;<strong>az útvonalverzió</strong>.</li>
</ul></td>
</tr>
<tr class="even">
<td>Verziószám dátuma</td>
<td>Adja meg az anyagjegyzék és az útvonal verziójának dátumát. A verzió határozza meg, mely anyagjegyzék-verziók vannak használatban egy adott időpontban, mint az anyagjegyzék-verzió beállításainál meghatározott verziódátumok.</td>
</tr>
<tr class="odd">
<td>Forrásmennyiség</td>
<td>A verziók szűrése egy adott forrásmennyiség használatával. Ha megad egy értéket, különböző anyagjegyzék- és útvonalverziókat választ ki.</td>
</tr>
<tr class="even">
<td>Csak az érvényesek jelenjenek meg</td>
<td>Ha be van jelölve a jelölőnégyzet, a fastruktúra csak az érvényes dátummal rendelkező anyagjegyzéksorokat mutatja. Kattintson jobb gombbal vagy duplán az anyagjegyzéksorra az <strong>Anyagjegyzéksor szerkesztése</strong> oldal megnyitásához, ahol az adott anyagjegyzéksorra vonatkozó érvényességi időpontokat láthatja.</td>
</tr>
</tbody>
</table>

Ha az Anyagjegyzék-tervezőt egy- vagy többszintű kitárolási értékkel rendelkező látszólagos típusok áttekintésére vagy szerkesztésére használja, a felső cikkhez rendelt útvonal általában a teljes anyagjegyzék-hierarchiára is kiterjed. Egyszerűsítése érdekében az áttekintése jelenjen meg, zárolhatja a legfelső szintű útvonal megjelenítése kattintva **nézet**&gt;**útvonal zárolása**. Az útvonal zárolásának feloldásához kattintson **nézet**&gt;**Unlock útvonal**.

## <a name="adding-and-editing-boms-and-bom-lines"></a>Anyagjegyzékek és anyagjegyzéksorok hozzáadása és módosítása
Használja a ** anyagjegyzéksorok ** vagy **AJ** funkciók AJ és AJ-sorok módosítására. Ha kiválaszt a fában egy csomópontot, a csomópont típusa határozza meg, milyen funkciók érhetők el.

| Funkció                            | Leírás                                                                                               | Csomóponttípus és feltételek                                                                                                                                                                                                                                                                       |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| AJ-sorok &gt;szerkesztése                 | Párbeszédpanel megnyitása, ahol szerkeszteni lehet az anyagjegyzéksor attribútumait.                                             | Ez a funkció csak akkor érhető el, ha ki van jelölve egy anyagjegyzéksor-csomópont.                                                                                                                                                                                                                                   |
| AJ-sorok &gt;törlése               | Anyagjegyzéksor törlése a kiválasztott anyagjegyzékből.                                                                  | Ez a funkció csak akkor érhető el, ha ki van jelölve egy anyagjegyzéksor-csomópont, és az anyagjegyzék nincs zárolva.                                                                                                                                                                                             |
| AJ-sorok &gt;előtt sor hozzáadása      | Párbeszédpanel megnyitása, ahol kiválaszthatja a kiválasztott anyagjegyzéksor előtt szerepeltetendő termékváltozatot.         | Ez a funkció csak akkor érhető el, ha ki van jelölve egy anyagjegyzéksor-csomópont.                                                                                                                                                                                                                                   |
| AJ-sorok &gt;AJ összetevő hozzáadása | Párbeszédpanel megnyitása, ahol kiválaszthatja a kiválasztott anyagjegyzék végén szerepeltetendő termékváltozatot.       | Ez a funkció csak akkor érhető el, ha a kijelölt csomópont rendelkezik kijelölt anyagjegyzékkel. Ha ez a funkció nem elérhető, egy anyagjegyzék-verzió hiányozhat a kiválasztott cikkváltozathoz. Ebben az esetben, ha rákattint **AJ**&gt;**létrehozása verzió** a kijelölt csomópont hiányzó verzió létrehozásához. |
| AJ-sorok &gt;sor hozzáadása       | Párbeszédpanel megnyitása, ahol kiválaszthatja a kiválasztott anyagjegyzéksor után szerepeltetendő termékváltozatot.          | Ez a funkció csak akkor érhető el, ha ki van jelölve egy anyagjegyzéksor-csomópont.                                                                                                                                                                                                                                   |
| AJ &gt;verzió létrehozása             | Új anyagjegyzék-verzió vagy anyagjegyzék létrehozása a kiválasztott csomópont termékváltozatához.                             | Ez a funkció akkor érhető el, ha a kiválasztott anyagjegyzéksor-csomópont össze van kapcsolva egy cikkel, amelynek a termelési típusa **Anyagjegyzék** vagy **Receptúra**.                                                                                                                                                  |
| AJ &gt;kiszámítása                | Párbeszédpanel megnyitása, ahol a költség- vagy eladásiár-számítást futtathatja a kiválasztott termékváltozatnál. | Ez a funkció akkor érhető el, ha a kijelölt csomópont kapcsolódik egy anyagjegyzék-verzióhoz.                                                                                                                                                                                                         |
| AJ &gt;ellenőrzése                      | A kiválasztott anyagjegyzék érvényesítése és ellenőrzése.                                                                      | Ez a funkció akkor érhető el, ha a kijelölt csomópont kapcsolódik egy anyagjegyzék-verzióhoz.                                                                                                                                                                                                         |

## <a name="configuring-the-tree-view"></a>A fa nézet beállítása
Kattintson a **Beállítás** menüpontra az Anyagjegyzék-tervező fanézetében megjelenő információk testreszabásához.

| Mezőcsoport | Leírás                                                                                                                                                  |
|-------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Anyagjegyzék         | A jelölőnégyzetek segítségével válassza ki a feltételeket, amelyek a faszerkezetben jelennek meg. Az Anyagjegyzék-tervező a kiválasztott kritériumokat mindkét lap alján megjeleníti. |
| Útvonal       | A jelölőnégyzetek segítségével válassza ki a feltételeket, amelyek az útvonalak között megjelennek.                                                                                    |




