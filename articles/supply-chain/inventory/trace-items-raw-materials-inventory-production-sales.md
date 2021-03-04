---
title: Cikkek és nyersanyagok nyomon követése a készletben, a gyártás során és az értékesítésben
description: Ez a témakör leírja, hogyan használja a cikk-követés azonosítására, amikor cikkeket vagy nyersanyagokat használták, használják vagy vesznek részt a termelési és értékesítési folyamatok.
author: perlynne
manager: tfehr
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 30191
ms.assetid: fdd0939a-855c-430f-a684-94f3baea1df4
ms.search.region: Global
ms.author: pjacobse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fa1be4970f1106bf4b87eeaa428bac07c645b4f5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4429772"
---
# <a name="item-and-raw-material-tracing-in-inventory-production-and-sales"></a>Cikkek és nyersanyagok nyomon követése a készletben, a gyártás során és az értékesítésben

[!include [banner](../includes/banner.md)]

Ez a témakör leírja, hogyan használja a cikk-követés azonosítására, amikor cikkeket vagy nyersanyagokat használták, használják vagy vesznek részt a termelési és értékesítési folyamatok.

A cikk nyomon követési funkció a **cikk nyomon követése** oldalon érhető el. A következő szakaszok leírják, hogyan használható a cikk-követés és az ahhoz tartozó beállításokat és korlátozásokat.

## <a name="what-is-item-tracing"></a>Mi az, hogy a cikk-követés?
A Cikk-követés egy üzleti intelligencia (BI) eszköz, ami egy ellátási lánc nyersanyagainak és cikkeinek forrására és céljára biztosít rálátást. Gyártók nyomon követhetők a cikkekre, a nyersanyag vagy összetevők vissza a szállítónak, és előre a termelés és értékesítés a késztermék keresztül. A cikk-követés segít a gyártóknak megfelelni a szabályozási követelményeknek, valamint segít a minőségellenőröknek és a gyártásvezetőknek elemezni és cselekedni a termékek és anyagok minőségében felmerülő címezési változások esetén. Íme néhány példa arra, hogy a gyártók, hogyan alkalmazhatják a cikk-követést:

-   Adja meg egy jelenleg készleten levő cikk, vagy egy nyersanyag összegét és tárolásának helyét.
-   Határozza meg, hogy a cikkből vagy a nyersanyagból mennyi lett leszállítva és mely vásárlókhoz.
-   Minden olyan tervezett szállítmányok, amelyek tartalmazzák a cikk és a nyersanyag azonosítása.
-   Keresse meg a tervezett, a folyamatban levő vagy a teljesített, a cikket vagy nyersanyagot használó termelési rendeléseket.
-   Ismerje meg, ahol a cikket vagy nyersanyag vásárolta.
-   Vizsgálja meg, ha egy cikket vagy egy alapanyag volt a termelés során felhasznált másik cikk.

## <a name="what-can-i-trace-and-are-there-any-limitations"></a>Mire tudom nyomon követhető, és vannak-e korlátozások?
Nyomon követheti a korábbi készletbeszerzési tranzakciókat a cikkeket és a nyersanyagokat illetően, a cikkszám és a nyomon követési dimenzió alapján például egy sorozatszám, a kötegszám vagy a szállítói köteg száma alapján. Csak akkor követhet le cikket vagy nyersanyagot, ha ahhoz tartozik nyomon követési dimenzió. A cikkek nyomon követésének vannak korlátai, mivel a nyomon követés a készlettranzakciókon alapszik. Például vannak korlátozások, amik a projektek, tárgyi eszközök és a kereskedelem tranzakcióihoz kapcsolódnak. Ezenkívül, míg a társtermékek megjelenítésre kerülnek a nyomon követési adatok között, addig a melléktermékek nem. A nyomon követés tartalmazza az összes egyik helyről a másikra történő raktári tranzakciót. Emiatt a felhasználók számára túl sok lehet a megtalálható információ. A nyomkövetés egyszerre csak egy jogi személy számára jelenik meg. Egy vállalatközi környezetben nincsenek több vállalatot érintő funkciók. Minden olyan vállalat esetében új nyomon követést kell alkalmaznia ahol egy cikket bevételeznek vagy kiadnak.

## <a name="what-criteria-can-i-specify-for-an-item-trace"></a>Milyen feltételek alapján lehet megadni a cikk-követés?
A cikk-követéshez szükséges kritériumok a következők: cikk szám, nyomon követési dimenzió (például kötegszám vagy sorozatszám) és irány. A következő táblázat leírja a feltételeket, amelyek a cikk-követés használható.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Mezőcsoport</th>
<th>Leírás</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Cikkszám</td>
<td>A cikk vagy nyersanyag, amelyhez a nyomkövetési azonosítójának megadása.</td>
</tr>
<tr class="even">
<td>Termékdimenziók</td>
<td>Választható: A termék meghatározásának, a konfiguráció, méret, szín vagy stílus például különleges szempontok nyomon követése.</td>
</tr>
<tr class="odd">
<td>Nyomon követési dimenziók</td>
<td>Adja meg a kötegszámot, a szállítói köteg számot vagy a sorozatszám nyomon követési dimenziót. A kötegszám feltételként történő használatakor a szállítói köteg száma látható akkor is, ha már rögzítette ezt az információt.</td>
</tr>
<tr class="even">
<td>Tárolási dimenziók</td>
<td>Választható: Egy adott helyen tárolt cikkek nyomon követése.</td>
</tr>
<tr class="odd">
<td>Időszak</td>
<td>Nem kötelező: Adja meg a szeretné korlátozni a nyomkövetés a meghatározott időszakra. A nyomon követési részletek csak a dokumentumok és a megadott dátumok között létrehozott tranzakciókat jelenítik meg.</td>
</tr>
<tr class="even">
<td>Előre vagy vissza</td>
<td>Válassza ki a nyomkövetés a irányát. Előre vagy hátra nyomon követhető:
<ul>
<li><strong>Visszafelé</strong> – Kövessen visszafele a forrás megtalálásához, a készleten maradt mennyiséghez és bármely legalább részlegesen befejezettként jelentett termelési rendeléshez.</li>
<li><strong>Előre</strong> – Nyomon-követés felfelé a cél azonosításához. Megtalálhatja az értékesítési rendeléseket, valamint azokat a vevőket akikhez a cikk vagy a nyersanyag, legalább részlegesen le lett szállítva.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="what-information-is-included-in-the-trace-details"></a>Milyen adatokat is tartalmaz a nyomon követési részletek?
A nyomon-követés eredménye időrendi sorrendben jelenik meg a **Részletek** gyorslapon, a **Cikk nyomon követés** oldalon. A rendelés nyomkövetési irányától függően változik. A részletes adatok tartalmazzák az összes tranzakciót a cikk szállítótól való beszerzésétől, a vevőnek történő eladásáig. Követési eredmények is ideiglenes termékek, amelyek a cikk vagy a nyomon követési dimenziót a nyomon követési feltételek között meghatározott kapcsolódnak. A legfelső csomópont jeleníti meg a cikk aktuális készleten maradt mennyiségét készletegységben megadva, a nyomon követési feltételek között megadott tárolási dimenziók alapján. **Megjegyzés:** A nyomon követési részletek a nyomon követést elvégzésekor elkészült információk pillanatképét mutatják. A nyomon követési részletek nem frissülnek, ha módosítja az adatokat a nyomkövetés végrehajtása után.

## <a name="why-dont-some-nodes-contain-any-details"></a>Egyes csomópontok miért nem szerepel a megjeleníthető adatokat?
A nyomkövetési részletek adatok mennyiségének csökkentéséhez csak az első példány a cikk vagy nyersanyag csomópont részletes adatait tartalmazza. Ha a kiválasztott csomópont nem tartalmaz részleteket, akkor megtekintheti a részleteket ténylegesen tartalmazó csomópontot az **Ugrás a követett sorra** gomb segítségével. Ezután visszatérhet az ön által otthagyott csomóra a **Vissza** gombra történő kattintással.

## <a name="can-i-view-only-a-particular-type-of-document-for-example-can-i-view-only-production-orders-customers-or-vendors"></a>Megtekintheti a dokumentum csak egy bizonyos típusú? Például lehet megtekinteni a csak a termelési rendelések, vevőkre vagy szállítókra?
Igen, a nyomon követési adatokból megnyithat olyan lista oldalakat is, amelyek csak egy bizonyos típusú dokumentumot vagy tranzakciót tartalmaznak. Elérheti ezeket a lapokat a **Nyomon követés** menüelem segítségével a Műveleti ablakon a **Cikk**, **Értékesítés**, **Beszerzés**, **Termelés**, és **Minőség** csoportokban. Például ahhoz, hogy megtekintse a szállítók listáját a nyomon követési részletekben, kattintson a **Nyomon követés** &gt; **Beszerzés** &gt; **Szállítók** elemre. A lista lapok összesíti a dokumentumokat vagy a követési adatokból. A **Függőben lévő tranzakciók**, **Függő rendelések** és a **Nem szállított értékesítési rendelések** listalapokon elérhetőek olyan információk is, amelyeket nem tartalmaznak a nyomon-követési részletek. Ezenkívül, mindig megjelenítésre kerülnek a jelenlegi dátumhoz tartozó eredmények, akkor is ha meg lett határozva egy dátumtartomány. A következő táblázat leírja a ezeken a lapokon tartalmazó további részleteket.

| Listák                    | Leírás                                                                                                                                                                                                                                                                                                                   |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nem szállított értékesítési rendelések | Tekintse meg azokat az értékesítési rendeléseket, amelyeket még nem választott ki és ezért nincsenek feltüntetve a nyomon követési adatokban.                                                                                                                                                                                                                        |
| Függő rendelések           | A nyomon követett cikk, függetlenül attól, a nyomon követési dimenziók, a nyomon követési feltételek között használt minden függőben lévő termelési rendelések megjelenítése. Megtekintheti továbbá az olyan függőben levő termelési rendeléseket is, ahol a nyomon követett cikk egy összetevő és nem történtek meg a regisztrációk és egy tranzakció sincs befejezett rendelésként jelentve. |
| Függőben lévő tranzakciók     | Függőben lévő, amely tartalmazza a megadott nyomon követési dimenziók vagy egy üres nyomonkövetésidimenzió a nyomon követett cikk készlettranzakcióinak megjelenítése. Függőben lévő cikkekhez és a nyomon követési cikkdimenzió-kombinációk, vagy egy üres értéket, a nyomon követési részletek a készlettranzakciók is megtekintheti.                                                |

## <a name="how-many-levels-can-i-trace-up-or-down-in-a-bom-or-formula"></a>Hány szintet követhetek fel vagy le anyagjegyzékben vagy receptúrában?
Egy szintet tud föl- vagy lekövetni az anyagjegyzékben vagy a receptúrában. Például ha futtatja a nyomkövetés a nyersanyagok, megtekintheti a késztermék és az esetleges társtermékek. Azonban a társtermék nyomon követésekor, a nyomon követési részletek nem tartalmazzák a kész terméket.

## <a name="how-can-i-view-more-details-about-a-document-or-transaction-in-the-trace-details"></a>Hogyan lehet egy dokumentum vagy a tranzakció részletes adatainak megtekintése a nyomkövetési részletek?
A **Részletek** gyorslapon két féleképpen tekinthet meg információt a kiválasztott dokumentumról vagy tranzakcióról a nyomon-követési részletekben:

-   Amikor kijelöl egy csomópontot a nyomon-követési részletekben a **Részletek** gyorslapon, akkor a lap egyéb gyorslapjai információt szolgáltatnak a csomópontban található dokumentumról vagy tranzakcióról.
-   Nyissa meg a részletek lapot a dokumentumhoz a kiválasztott csomópontban a **Részletek megtekintése** gombra kattintással. Például ha kijelöl egy csomópontot, amely egy termelési rendelést ír le és rákattint a **Részletek megtekintése** elemre, akkor megjelenik a **Termelési rendelés részletei** lap.

Néhány gyorslap engedélyezi a hozzáférést a kiválasztott csomópont további információihoz. Például a **Szabálytalanságok** gyorslapon megvizsgálhatja, hogy van-e szabálytalansági előzmény a **Lekérdezések** elemre kattintva. A **Köteg** gyorslapon rákattinthat az **Aktuális készlet** elemre, hogy megtekintse a jelenlegi tényleges készlet összegét és bármely készlet-tranzakciót, amely érinti a köteget.

## <a name="can-i-run-more-than-one-trace-and-then-compare-the-details"></a>Tudok egynél több nyomon követést futtatni, majd összehasonlítani az adatokat?
Miután futtatta a nyomon-követést, használhatja a következő beállításokat a **Nyomon követés csomópontból** gombon, hogy egy új nyomon-követést futtasson a tranzakción a kijelölt csomópontban:

-   **Vissza** vagy **előre** – Elindít egy új futtatást a kijelölt csomóponthoz és felülírja a jelenlegi nyomon követés részleteit.
-   **Új vissza** vagy **új előre** – Elindít egy új nyomon követést egy új ablakban és megtartja a jelenlegi nyomon követés részleteit.

Ha használni szeretné az **Új vissza** vagy az **Új előre** lehetőséget, akkor használnia kell a **Megnyitása új ablakban** funkciót, hogy az új követés új ablakban jelenjen meg.

## <a name="can-i-save-the-trace-details"></a>Mentheti a nyomon követési részletek?
Elmentheti az adatokat a <strong>Részletek</strong> lapon XML fájlként, a *<strong><em>Nyomon követés</em></strong>* művelet alatti <strong>Exportálás</strong> elemre kattintva a Műveleti ablakban. A nyomon követési adatok mellett az XML fájl tartalmazza a követési feltételeket, a fő csomópontot és a készleten levő mennyiséget is. A nyomon követés részleteinek mentése azért hasznos, mert így például csatolhatja az információkat egy minőségi rendeléshez vagy egyéb megfelelési dokumentumhoz. Megadhatja azt is, hogy hova legyen mentve a fájl. Hogy rögtön megtekintse a fájlt jelölje ki a <strong>Dokumentum megjelenítése</strong> jelölőnégyzetet. <strong>Megjegyzés:</strong> A fájl mentése abban az esetben is megtörténik, ha ön megakarja tekinteni azt. Alapértelmezés szerint az XML-fájl egy böngészőablak megnyitása Rákattinthat azonban a fájlra, kiválaszthatja a <strong>Társítás</strong> funkciót, majd kiválaszthatja a programot amelyben megszeretné jeleníteni a tartalmat.

## <a name="can-i-calculate-a-balance-for-a-particular-item-or-ingredient"></a>Lehet egy adott elemhez vagy összetevő egyenleg kiszámítása?
Az adatokat exportálhatja az összesítő oldalakról Microsoft Excel formátumba. Nyissa meg a kívánt lapot, kattintson a **Megnyitás Microsoft Office**-ban ikonra, majd válassza ki az **Exportálás Microsoft Excel** formátumba opciót. Ez különösen akkor hasznos, amikor ki akarja számolni egy cikk vagy összetevő tömeges egyenlegét a **Tranzakciók összesítése** lapról. A **Tranzakciók összesítése** lapon tetszés szerint szűrhet cikket, alapanyagot és lehetőség szerint köteget, majd exportálhatja az információt Excelbe. Az Excelben képes például elválasztani a készleten lévő mennyiséget, az értékesített mennyiséget és az összeget, amely a termelés során lett felhasználva.

## <a name="can-i-investigate-whether-there-is-a-history-of-issues-with-items-or-raw-materials"></a>Kinyomozhatom, hogy voltak-e a múltban problémák a cikkekkel vagy a nyersanyagokkal?
A nyomon követési részletek a cikkeket vagy a nyersanyagokat érintő minőségi rendelésekről és szabálytalanságokról tartalmaznak információkat. Megtekintheti a minőségi rendelések és a szabálytalanságok összesítését a **Minőségi rendelések** vagy a **Szabálytalanságok** elemre kattintva a Műveleti ablak ablakban. **Megjegyzés:** Romboló minőségi rendelések egynél többször szerepelhetnek a nyomon követési részletekben. Mikor romboló minőségi rendelést hoz létre egy dokumentumhoz (például egy beszerzési rendeléshez), akkor az a tranzakció minden dokumentumánál feltűnik.

## <a name="are-there-any-reporting-capabilities-that-are-related-to-item-tracing"></a>Van bármely a cikk-követéshez kapcsolódó jelentéskészítő lehetőség?
Létrehozhatja a **Vevőknek szállítva** jelentést, hogy azonosítsa a kiszállításra került cikk vagy nyersanyag összegét, és a vevőt, akinek ki lett szállítva. Megfeleltetéshez tartozó lekérdezéshez, készíthet jelentést az összes vevő részére. Vevőszolgálathoz tartozó lekérdezéshez, készíthet jelentést a kiválasztott vevő részére. Ha a terméket a kész cikk előállításához használt nyersanyag volt, a befejezett cikk is szerepel. **Megjegyzés:** Amennyiben a beszerzési rendelések törlése vagy archiválása funkciókat alkalmazza, a jelentés eredményei tartalmazni fogják az összes törölt és archivált értékesítési rendelést.

## <a name="can-i-trace-coproducts-and-byproducts"></a>A társtermékeket és melléktermékeket is nyomon követhetem?
Nyomon követhet társtermékeket, de nem követheti le a melléktermékeket, mivel a nyomon követési dimenziók javarészt, nem a melléktermékekhez vannak hozzárendelve. Egy cikk nyomon követésekor, a nyomon követési részletek minden kapcsolódó társterméket tartalmaznak. Olyan Társtermék tartalmazó csomópont "Társtermék" szó részletes adatait tartalmazza. Megtekintheti továbbá egy társtermék részleteit a csomópont kijelölésével a nyomon-követési részletekben, majd a **Termelés** gyorslap alábontásával.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]