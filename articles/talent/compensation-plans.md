---
title: Kompenzációs konstrukciók
description: A kompenzációkért és juttatásokért felelős vezetők használhatják a Kompenzációkezelést a karbantartáshoz és a szervezet alkalmazottaira vonatkozó fix és változó kompenzáció feldolgozásához.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCompensationLevel, HRCCompGrid, HRMCompFixedAction, HRMCompFixedBudget, HRMCompFixedPlanTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.openlocfilehash: 8e7e41756c3be73937ef62523ff6bf41536405b0
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898850"
---
# <a name="compensation-plans"></a>Kompenzációs konstrukciók

A kompenzációkért és juttatásokért felelős vezetők használhatják a Kompenzációkezelést a karbantartáshoz és a szervezet alkalmazottaira vonatkozó fix és változó kompenzáció feldolgozásához.

### <a name="introduction"></a>Bevezetés

A kompenzációkezeléssel szabályozható az alapfizetés és a jutalmak kifizetése. Egy alkalmazott fix fizetési díjalapja és érdemeken alapuló fizetése kezelhető a fix kompenzációs tervekkel. Az ösztönző díjak kifizetése, például bónuszok, teljesítménydíjak, részvényopciók és kölcsönök, továbbá az egyszeri jutalmak a változó kompenzációs tervekben szabályozhatók. 

Az alkalmazottak mindkét típusú konstrukcióhoz, akár többhöz is társíthatók. Az alkalmazottnak meg kell felelni az alábbi kritériumoknak, hogy hozzárendelhető legyen a kompenzációs tervhez:
-   Az alkalmazottnak aktív pozícióval kell rendelkeznie.
-   Az alkalmazottnak teljesíteni kell a kompenzáció terv jogosultsági szabályaiban meghatározott feltételeket.

## <a name="compensation-setup"></a> Kompenzáció beállítása
Az alábbi táblázat felsorolja azokat a kompenzációs folyamatokat, amelyek aktív részét képezhetik a vállalati kompenzációs terv beállításainak.

<table>
<thead>
<tr class="header">
<th>Összetevő</th>
<th>További információ...</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Fix kompenzációs műveletek</td>
<td>Fix kompenzációs műveletek, amelyeknek két célt teljesítenek:
<ul>
<li>A műveletek megadhatnak olyan információkat amelyeket rögzíteni kell az alkalmazott kompenzációjának változásakor. Például előírhatja ezt előléptetéskor vagy lefokozáskor.</li>
<li>A műveletekkel biztosítható, hogy a számítást alkalmazzák a fix kompenzációs konstrukciók feldolgozásakor.  Például a Saját tőke típusú műveletek összehasonlítják az alkalmazottak fizetését a minimum referenciaponttal az alkalmazott szintjén, és biztosítják, hogy a dolgozó legalább a minimális fizetést megkapja.</li>
</ul></td>
</tr>
<tr class="even">
<td>Szintek</td>
<td>A feladatokhoz szintek és bármelyik beosztás kapcsolódik amelyik a munkahivatkozáshoz kapcsolódik. A kompenzációs tervek következő három típusának különálló szintjei hozhatók létre: Osztály, Sáv és Lépés.</td>
</tr>
<tr class="odd">
<td>Tartomány-kihasználtsági mátrix</td>
<td>A tartomány kihasználtsági mátrix segít az alkalmazottak továbbléptetésében a beosztásukhoz tartozó ellenőrzőpontjuk felé. A tartomány-kihasználtság a kompenzáció vállalaton belüli szabályozására is felhasználható oly módon, hogy az ne függjön az egyes alkalmazottak teljesítményétől vagy a vállalat teljesítményétől összességében. Például a tartományukon belül alacsonyabb fizetést kapó alkalmazottak nagyobb emelést kapnak, mint azok az alkalmazottak, akik magasabb fizetéssel rendelkeznek. Ezzel a módszerrel kiegyenlítheti a saját tőke különbségeit. A tartomány-kihasználtság számítása a következő: (Fix fizetési díjalap – Tartományminimum) ÷ (Tartománymaximum – Tartományminimum).</td>
</tr>
<tr class="even">
<td>Hivatkozásipont-beállítások</td>
<td>A hivatkozásipont-beállítások hivatkozási pontok mátrixba rendezett halmazát tartalmazzák. Minden tartomány egy fizetési díjalaphoz társítható. Például a fokozatos konstrukciójú szervezetek gyakran tartalmaznak Minimum, Közép és Maximum referenciapontokat.</td>
</tr>
<tr class="odd">
<td>Kompenzációs mátrix</td>
<td>A kompenzációs mátrix azon referenciapontok és szintek összessége amelyeket a kompenzációs szerkezet létrehozásához használ.</td>
</tr>
<tr class="even">
<td>Kompenzációs struktúra</td>
<td>A kompenzációs struktúra egy kompenzációs mátrix, amelyben minden szinthez a fizetési díjalapok referenciapontjai vannak társítva.</td>
</tr>
<tr class="odd">
<td>Alkalmazhatósági szabályok</td>
<td>Az alkalmazhatósági szabályok segítségével kikereshetők az adott feladatokban, beosztásban, részlegben, szakszervezetben vagy kompenzációs régiókban lévő alkalmazottak, akikre speciális kompenzációs tervek vonatkoznak. Hogy felvehesse az alkalmazottakat a tervbe létre kell hoznia jogosultsági szabályokat a változó és fix kompenzációs tervekhez. Miután meghatározta a kompenzációs konstrukciókra vonatkozó alkalmazhatósági szabályokat, definiálhatja azokat a munkaköröket, amelyeket a konstrukcióval érintett beosztásokban alkalmazni lehet.</td>
</tr>
<tr class="even">
<td>Fizetési gyakoriságok</td>
<td>A kifizetési gyakoriságokkal meghatározható az időtartam, amelyre a kompenzáció vonatkozik.  Például a kifizetési gyakoriság segít felmérni, hogy a kompenzációs összeget éves fizetés vagy órabér formájában adták-e meg. A kifizetési gyakoriságok továbbá használhatók átváltási tényezők felállításához, ha havi, heti, kétheti és óránkénti kompenzációs összegek kifizetési gyakoriságát akarja átváltani éves kifizetési gyakoriságra.</td>
</tr>
<tr class="odd">
<td>Kompenzációs régiók</td>
<td>A kompenzációs régiók beállítása a munkahelyen alapuló kompenzáció meghatározásához használatos.</td>
</tr>
<tr class="even">
<td>Ellenőrzőpont</td>
<td>A vezérlőpont az alkalmazottaknak adandó ideális fizetést határozza meg, az adott kompenzációs szinten. A fokozatos konstrukciójú szerkezeteknél a vezérlőpontok általában a tartományok felezőpontjai. A sávos szerkezeteknél ritkán alkalmaznak vezérlőpontokat. A Fix kompenzáció tervek képernyőn megadhatja a fix kompenzációs terv vezérlőpontját.</td>
</tr>
<tr class="odd">
<td>Beosztások</td>
<td>A beosztások segítségével osztályozhatók és szűrhetők az adott munkákhoz a kompenzációs tervek.</td>
</tr>
<tr class="even">
<td>Beosztástípusok</td>
<td>A beosztás típusok segítségével osztályozhatók és szűrhetők az adott munkákhoz a kompenzációs tervek.</td>
</tr>
<tr class="odd">
<td>Változó kompenzációtípusok</td>
<td>A változó kompenzációtípusok, például a részvényjutalmak és a készpénzjutalmak a változó kompenzációs konstrukciókon keresztül alkalmazhatók.</td>
</tr>
<tr class="even">
<td>Kompenzációs rácsok</td>
<td>A kompenzációs struktúrát a kompenzációs rácsok tartalmazzák.  A kompenzációs rácsok egy vagy több kompenzációs konstrukcióhoz használhatók.</td>
</tr>
<tr class="odd">
<td>Teljesítménykonstrukciók</td>
<td>Felosztási mátrixszal társítható teljesítménykonstrukciók létrehozása teljesítménybérezési stratégiában történő felhasználás céljából.</td>
</tr>
<tr class="even">
<td>Teljesítményminősítések</td>
<td>A teljesítményminősítéseket a teljesítményjutalmak és az eredményjutalmak meghatározására alkalmazhatja a teljesítménykonstrukciókban.</td>
</tr>
</tbody>
</table>

## <a name="process-events"></a>Feldolgozási események
A feldolgozási esemény egy időszakra vonatkozóan az egyes fix és változó kompenzációs konstrukciókba sorolt alkalmazottak kompenzációit számítják ki. A feldolgozási események többször is futtathatók, például a számított kompenzációs eredmények tesztelése vagy frissítése céljából.

<a name="compensation-events"></a>Kompenzációs események
-------------------

Minden feldolgozási esemény futtatásakor létrejön egy kompenzációs esemény.  A kompenzációs események tartalmazzák az egyes alkalmazottak feldolgozási folyamat során érintett kompenzációs folyamatait.  Ha a számítások helyesek, akkor betöltheti a kompenzációs eseményt a feldolgozási eseményben érintett alkalmazottak kompenzációs rekordjainak frissítéséhez.

## <a name="recommendations"></a> Ajánlások
Miután lefuttatta a feldolgozási eseményt javaslatot tehet az egyes alkalmazottak érdemeken alapuló emelésre vagy a jutalom összegére a feldolgozási esemény irányelvei alapján. Ha szeretne ajánlásokat létrehozni alkalmazottaknak, akkor engedélyeznie kell az ajánlásokat a kompenzációs konstrukciók létrehozásakor vagy amikor létrehozza a feldolgozási eseményt.



