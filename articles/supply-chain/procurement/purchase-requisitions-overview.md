---
title: Beszerzési igénylések áttekintése
description: Ez a témakör a beszerzési igénylési munkafolyamatot, valamint a beszerzési igénylés különböző állapotait írja le.
author: mkirknel
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqConsolidation, PurchReqCreate, PurchReqCreatePurchDetails, PurchReqCreatePurchListPage, PurchReqTable, PurchReqTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2174
ms.assetid: 77d07119-4d9f-4c0e-acbe-d319203571ab
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f279474d4a1e2f76e810b0df80c8d91171352c17
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572025"
---
# <a name="purchase-requisition-overview"></a>Beszerzési igénylések áttekintése

[!include [banner](../includes/banner.md)]

Ez a témakör a beszerzési igénylési munkafolyamatot, valamint a beszerzési igénylés különböző állapotait írja le.

Szervezete működésének beállításaitól függően lehetősége van a szervezete által használt anyagokhoz beszerzési igénylések létrehozására és elküldésére. A beszerzési igénylés olyan belső dokumentum, amely feljogosítja a Beszerzési részleget az elemek vagy szolgáltatások megvásárlására.  

A jóváhagyott beszerzési igénylés felhasználható a beszerzési rendelés létrehozására. Beszerzési rendelések olyan külső dokumentumok, amelyeket a Beszerzési részleg küld ki a beszállítóknak.

## <a name="creating-purchase-requisitions"></a>Beszerzési igénylés létrehozása
Létrehozhat egy beszerzési igénylést a **Beszerzési rendeléseim** oldalon, és kiválaszthatja a szükséges cikkeket és szolgáltatásokat. A termékeket kiválaszthatja a szervezete által létrehozott beszerzési katalógusból, vagy kiválaszthatja a beszerzési kategóriát és megadhatja a termék részleteit, ha a katalógusban nem szereplő termékeket igényelne.  

Beszerzési igénylés csak a munkafolyamat konfigurálása után nyújtható be ellenőrzésre a Microsoft Dynamics 365 for Finance and Operations rendszerben. A munkafolyamatot a beszerzési igénylés ellenőrzési folyamaton való mozgatásához használja a kiinduló **Piszkozat** állapottól a végső **Jóváhagyott** állapotig.

### <a name="purchase-requisition-statuses"></a>A beszerzési igénylések állapotai

Beszerzési igénylés létrehozása esetén a rendelés állapotát hozzárendeli a program. Minden sorhoz hozzárendel a program egy állapotot, amit a beszerzési igényléshez ad hozzá. Amikor elküld egy beszerzési igénylést egy munkafolyamathoz ellenőrzésre, akkor a beszerzési igénylés állapota és a sorok állapota frissül, ahogy a sorok áthaladnak a munkafolyamaton.  

Konfigurálhatja a beszerzési igénylés munkafolyamatot, hogy egyetlen dokumentumként továbbítsa a beszerzési igénylést az ellenőrzési folyamatba. Másik lehetőségként egy beszerzési igénylés sorai egyenként is továbbíthatók a megfelelő ellenőröknek. Ha a beszerzési igénylés sorok ellenőrzése egyenként történik, akkor a beszerzési igénylések sorai frissíthetők, ahogy a sorok átesnek az ellenőrzési folyamaton. Amikor minden sor befejeződött, az ellenőrzési folyamat és nincsen hátra ellenőrzési lépés a beszerzési igényléshez, akkor a teljes beszerzési igénylés állapota frissül.

### <a name="purchase-requisition-workflow"></a>Beszerzési igénylési munkafolyamat

Az alábbi diagrammon a beszerzési igénylés állapotai és a beszerzési igénylések sorai láthatók, amint áthaladnak a munkafolyamaton.  

[![A beszerzési igénylési sor fejléce és sorok állapota](./media/purchasereq_headerline_statuses.jpg)](./media/purchasereq_headerline_statuses.jpg)

### <a name="purchase-requisition-header-and-line-status-relationships"></a>A beszerzési igénylési sor fejléce és sorok állapotainak kapcsolatai

Egy beszerzési igénylés általános állapotát a beszerzési igénylési sorok állapota határozza meg. Ezért az ellenőrzést mindegyik beszerzési igénylés sornál el kell végezni a teljes beszerzési igénylés ellenőrzési folyamatának befejezése előtt. Az alábbi táblázatban láthatók a beszerzési igénylés állapotai és a beszerzési igénylések fejléce és sorai láthatók, amint áthaladnak a munkafolyamaton.

<table>
<thead>
<tr class="header">
<th>Beszerzési igénylés állapota</th>
<th>A beszerzési igénylési sor állapota</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Vázlat</td>
<td>Vázlat</td>
<td>A beszerzési igénylést és a beszerzési igénylés sorai létrejöttek, de nincsenek elküldve ellenőrzésre. A <strong>Vázlat</strong> állapotú beszerzési igénylések és beszerzési igénylés sorok módosíthatók. A beszerzési igény vagy a beszerzési igényre vonatkozó sor szintén <strong>Vázlat</strong> állapotú, ha visszavonták, de még nem küldték be újra ellenőrzésre. <strong>Megjegyzés:</strong> Beszerezheti vagy visszahívhatja a beszerzési igényléseket a dokumentum szintjén. Azonban nem tud elküldeni vagy visszahívni egyes beszerzési igénylés sorokat.</td>
</tr>
<tr class="even">
<td>Ellenőrzés alatt</td>
<td><ul>
<li>Ellenőrzés alatt</li>
<li>Elutasítva</li>
</ul></td>
<td>Ha a munkafolyamat úgy lett konfigurálva, hogy a beszerzési igénylés sorokat egyéni ellenőrökhöz irányítsa, akkor az egyes sorok állapota <strong>Vizsgált</strong> vagy <strong>Elutasítva</strong>. A beszerzési igénylés állapota frissül, ha az összes beszerzési igénylés sor ellenőrzési folyamata befejeződött és nincs hátralévő ellenőrzési lépés a beszerzési igényléshez.
<ul>
<li><strong>Vizsgált</strong> – A beszerzési igénylés sorok ellenőrzésre küldve. Ha egy beszerzési igénylés sorához tartozó munkafolyamat befejeződött, a sor állapota <strong>Vizsgált</strong> marad, amíg a hátralévő beszerzési igénylés sorainak ellenőrzése lefut.</li>
<li><strong>Elutasított</strong> – A beszerzési igénylési sor el lett utasítva. A visszautasított beszerzési igénylési sorok módosíthatók és újraküldhetők.</li>
</ul>
Ha újraküldi a visszautasított beszerzési igénylés sorát, az ellenőrzési folyamat minden ellenőrzés alatt lévő beszerzési igénylés sornál újrakezdődik. <strong>Megjegyzés:</strong> Visszahívhat beszerzési igénylést amelyet már feladott. Ha visszahívja a beszerzési igénylést, az összes beszerzési igénylés is visszahívásra kerül. Visszahívott beszerzési igénylés sorok törölhetők.</td>
</tr>
<tr class="odd">
<td>Elutasítva</td>
<td>Elutasítva</td>
<td>A visszautasított beszerzési igénylés és a beszerzési igénylés sorok. A visszautasított beszerzési igénylések és beszerzési igénylés sorok újraküldhetők.</td>
</tr>
<tr class="even">
<td>Engedélyezve</td>
<td><ul>
<li>Engedélyezve</li>
<li>Érvénytelenítve</li>
<li>Lezárva</li>
</ul></td>
<td>Minden beszerzési igénylés sor befejeződött, az ellenőrzési folyamat és nincsen hátra ellenőrzési lépés a beszerzési igényléshez, akkor a teljes beszerzési igénylés állapota frissül.
<ul>
<li><strong>Jóváhagyva</strong> – A beszerzési igénylés sorához tartozó ellenőrzési folyamat befejeződött, a sort elfogadták.</li>
<li><strong>Érvénytelenítve</strong> – A beszerzési igénylés sorát elfogadták, de érvénytelenítették, mert nincs szükség rá. Csak a visszahívott vagy jóváhagyott beszerzési igénylés sorok.</li>
<li><strong>Lezárt</strong> – A beszerzési igénylés sor jóváhagyva, és a dokumentumok létrejöttek, az igénylés céljától függ.
<ul>
<li>Ha az igénylés célja felhasználás, akkor a beszerzési rendelés a beszerzési igénylés sorában jön létre.</li>
<li>Ha az igénylés célja a feltöltés, akkor egy, vagy több teljesítési dokumentum jön létre.</li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td>Érvénytelenítve</td>
<td>Érvénytelenítve</td>
<td>A kiválasztott beszerzési igénylés és a beszerzési igénylés összes sora visszavonva. <strong>Megjegyzés:</strong> Ha már nincs szüksége egy cikkre, amelyik a beszerzési igénylés sorában szerepel, akkor mondja le a beszerzési igénylés sort, ha már elfogadták. Csak a visszahívott vagy jóváhagyott beszerzési igénylés sorok. Ha bármelyik beszerzési igénylés ellenőrzés alatt áll, akkor a beszerzési igénylés <strong>Vizsgált</strong> állapotú. Ebben az esetben visszahívhatja a beszerzési igénylést, és törölheti a megfelelő beszerzési igénylési sort.</td>
</tr>
<tr class="even">
<td>Lezárva</td>
<td><ul>
<li>Lezárva</li>
<li>Érvénytelenítve</li>
</ul></td>
<td>A beszerzési igénylés lezárt, és egy, vagy több teljesítési dokumentum jött létre.
<ul>
<li><strong>Lezárt</strong> – A beszerzési igénylés sor jóváhagyva, és a dokumentumok létrejöttek, az igénylés céljától függ.
<ul>
<li>Ha az igénylés célja felhasználás, akkor a beszerzési rendelés a beszerzési igénylés sorában jön létre.</li>
<li>Ha az igénylés célja a feltöltés, akkor egy, vagy több teljesítési dokumentum jön létre.</li>
</ul></li>
<li><strong>Érvénytelenítve</strong> – A beszerzési igénylés sorát elfogadták, de érvénytelenítették, mert nincs szükség rá. Csak a visszahívott vagy jóváhagyott beszerzési igénylés sorok.</li>
</ul>
<strong>Megjegyzés:</strong> Ha már nincs szüksége egy cikkre a beszerzési igénylés lezárt sorában, akkor érvényteleníteni kell a sort a teljesítési dokumentumban, ami a beszerzési igény sorához jött létre.</td>
</tr>
</tbody>
</table>

## <a name="distributing-costs-to-multiple-financial-accounts"></a>Költségek felosztása több pénzügyi számlára
Egy beszerzési igényben szereplő termék költségét feloszthatja pénzügyi számlára. Ha a szervezete használ a költséghelyekhez vagy részlegekhez hasonló dimenziókat, akkor fel lehet osztani a termék árát a pénzügyi számlák dimenziói között.

## <a name="requisition-purposes"></a>Igénylési célok
Az igénylési célok a teljesítés igénylési igényét folyamatát rugalmasabbá teszi. Az igénylések létrehozásakor a következő két cél közül választhat: felhasználás vagy feltöltés. Az igénylés céljától és a szervezet beállításaitól függően az igénylési igény teljesíthető beszerzési rendeléssel, átmozgatási rendeléssel, gyártási rendeléssel vagy kanbannal.  

A beszerzési irányelveknél ellenőrizheti az elérhető beszerzési célt a szervezete számára meghatározott igénylések között.

### <a name="requisitions-that-have-a-purpose-of-consumption"></a>Fogyasztási célú igénylések

A fogyasztási célú igénylés olyan termék vagy szolgáltatás iránti keresletet jelent, amelyet a szervezete belső folyamataiban fog felhasználni. Az ilyen típusú igénylés által létrehozott kereslet mindig teljesül egy beszerzési rendeléssel. Ha a Microsoft Dynamics 365 for Finance and Operations beállítása automatikan hoz létre beszerzési igénylést, azok csak a beszerzési igénylés jóváhagyása után valósulnak meg.

### <a name="requisitions-that-have-a-purpose-of-replenishment"></a>Feltöltési célú igénylések

A feltöltési célú igénylés a készlet feltöltésére irányuló igényt jelöl. Létrehozhat például a cikkek feltöltésére vonatkozó igénylést, hogy azok meghatározott kiskereskedelmi helyszínen, meghatározott időben értékesíthetők legyenek. A létrehozott igénylés céljától függően, az igény teljesítése beszerzési rendeléssel, átmozgatási rendeléssel, termelési rendeléssel vagy kanban használatával történhet.  

Amikor az igénylés célja a feltöltés, az igény mennyiségben fejezhető ki, és nem pénzösszegben. Ezért a kötelezettségvállalás-könyvelés, a költségvetés-ellenőrzés, a tárgyi eszközök üzleti szabályai, a projektkönyvelés szabályai és az egyéb kapcsolódó szabályok ebben az esetben nem érvényesek. A feltöltési igénylési igény csak készletezett és a megadott jogi személynek kiadott termékekkel teljesíthető. Ha az igénylési cél feltöltés, akkor adja meg az elérhető termékeket a **Feltöltés kategória hozzáférés irányelvszabály** oldalon.  

A feltöltési célú beszerzési igénylések használatához a rendszer alapütemezését úgy kell beállítani, hogy tartalmazzon igénylési igényt. A feltöltési céllal létrejött igénylés által létrehozott igény teljesítési módja automatikusan meghatározottá válik az ellátási irányelvek által, amelyek a szervezetet segítségével vannak beállítva a cikkekre, és alapütemezés segítségével vannak megtervezve.

## <a name="purchase-requisitions-and-requests-for-quotation"></a>Beszerzési igények és árajánlatkérést szabályozó szabályok
Bizonyos esetekben el kell indítania az ajánlatkérési (RFQ) folyamatot, hogy megadhassa a szállítót és termék árát amelyet a beszerzési igényléssel szeretne beszerezni. Az ajánlatkérés akkor hozható létre, ha a beszerzési igénylés ellenőrzés alatt van. Ha elfogad egy ajánlatot, akkor a szállító, ár és egyéb adatok továbbításra kerülnek az igényléshez.  

A beszerzési igénylések visszatarthatók a **Visszatartott** jelölőnégyzet kiválasztásával a **Beszerzési igénylés részletei** lapon. A beszerzési igénylés feldolgozása csak azt követően folytatódhat, hogy eltávolítja a visszatartást a négyzet bejelölésének törlésével.  

**Megjegyzés:** Az e-beszerzésben, a beszerzési igényléshez az ajánlatkérés lehetővé teszi a szállítóknak alternatív sorok megadását. Ebben az esetben a beszerzési igénylésben a jóváhagyott alternatívák jelennek meg.

## <a name="demand-consolidation"></a>Igényösszesítés
Ha több beszerzési igénylési sort konszolidál több beszerzési igénylésből, a tárgyalási erejét növelheti a szállítókkal szemben a jobb árképzés, valamint az alacsonyabb szállítási, kezelési és járulékos költségek érdekében.  

A beszerzési igénylési sorok csak akkor jogosultak az igényösszesítésre, ha a következő kijelentések teljesülnek:

-   A beszerzési igénylést jóváhagyták.
-   A beszerzési igénylés megfelel a manuális feldolgozás és az igény szerint konszolidáció beszerzési irányelvszabály feltételeinek.

A jóváhagyott beszerzési igénylés sorok, amelyek megfelelnek a manuális feldolgozás követelményeinek a **Jóváhagyott beszerzési igénylések feladása** oldalon vannak listázva. Ha egy beszerzési igénylési sor megfelel az igényösszesítés feltételeinek is, a sort hozzá lehet adni egy összevonási lehetőséghez.  

Az összevonási lehetőség az olyan beszerzési igénylési sorok készlete, amelyek egy csoportba tartoznak, hogy a beszerzési munkatárs a lehető legjobb üzletet érje el a szállítóknál. Az összevonási lehetőséghez kiválasztott beszerzési igénylés sorok a **Beszerzési igénylések összevonása** oldalon jelennek meg. Ezen az oldalon módosíthatja a sorokat, ha változtatások szükségesek. Új sorokat is hozzáadhat, vagy el is távolíthat meglévő sorokat az összevonási lehetőségből.  

Miután az igénylési sorokat hozzáadta az összevonási lehetőséghez és elvégezte a szükséges módosításokat, létrehozhat egy beszerzési rendelést a konszolidált beszerzési igénylési sorokhoz.  

**Megjegyzés:** A beszerzési igénylési soron végrehajtott módosítások a **Beszerzési igénylés összevonása** oldalon jelennek meg a létrehozott beszerzési rendelésen. Ugyanakkor a beszerzési igénylésben szereplő sor változatlan marad, így megmaradnak az előzmények.  

Olyan beszerzési igénylés létrehozásakor, beszerzési rendelésnél, amelyek nem jogosultak az igényösszesítésre vagy nem választotta azokat ki az összevonási lehetőséghez, kézzel kell feldolgozni a beszerzési rendelés létrehozásához.

### <a name="consolidating-purchase-requisition-lines"></a>Beszerzési igénylés sorainak konszolidációja

Az igényösszesítési eljárás akkor indul el, amikor a munkafolyamatban a beszerzési igénylés jóváhagyásra kerül és ha a költségvetés-ellenőrzés a szervezethez lett konfigurálva a költségvetési tartalékok és az előzetes kötelezettségvállalások rögzítésénél. A következő ábrán az igényösszesítés folyamata látható.  

[![Folyamatáramlat igényösszesítéshez](./media/demand-consolidation.gif)](./media/demand-consolidation.gif)  

A jóváhagyott beszerzési igénylési sorok konszolidálásához tegye a következőket:

1.  A manuális feldolgozás céljából várakoztatott és az igényösszesítésre jogosult jóváhagyott igénylési sorokat tekintse át.
2.  Összevonási lehetőség hozzáadásához válasszon ki sorokat.
3.  Hozzon létre új összevonási lehetőséget vagy adjon hozzá igénylési sorokat a meglévő összevonási lehetőséghez.
4.  Tegye meg a kívánt módosításokat az igénylési sorokon és távolítsa el azokat az igénylési sorelemeket, amelyeket nem szeretne szerepeltetni az összevonási lehetőségben.
5.  Hozzon létre beszerzési rendeléseket az összesített igényléssorokhoz vagy beszerzési igényléssorokhoz egy összevonási lehetőségben.


<a name="additional-resources"></a>További erőforrások
--------

[Felhasználási igénylés létrehozása (Feladat-útmutató)](tasks/create-requisition-consumption.md)

[Beszerzési igénylési munkafolyamat](purchase-requisitions-workflow.md)



