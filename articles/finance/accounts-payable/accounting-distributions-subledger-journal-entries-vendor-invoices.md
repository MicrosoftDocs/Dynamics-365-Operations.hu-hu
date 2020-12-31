---
title: Információ a könyvelési felosztásokról és az analitikusnapló-bejegyzéseiről szállítói számlákhoz
description: A könyvelési felosztások használatával lehet meghatározni, hogy hogyan lesz az összeg elszámolva, például hogyan lesznek könyvelve a kiadások, adó és költségek a szállítói számlán. Minden összegnek, amelyet könyvelni kell, amikor a szállítói számla naplózva van egy vagy több könyvelési felosztása van.
author: abruer
manager: AnnBe
ms.date: 08/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendEditInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 26891
ms.assetid: 93dc608a-b5b4-4ec3-83c2-618e3d80a583
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f8e38e6a571bb7f08b32548bcb4af823807a4340
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444122"
---
# <a name="accounting-distributions-and-subledger-journal-entries-for-vendor-invoices"></a>Információ a könyvelési felosztásokról és az analitikusnapló-bejegyzéseiről szállítói számlákhoz

[!include [banner](../includes/banner.md)]

A könyvelési felosztások használatával lehet meghatározni, hogy hogyan lesz az összeg elszámolva, például hogyan lesznek könyvelve a kiadások, adó és költségek a szállítói számlán. Minden összegnek, amelyet könyvelni kell, amikor a szállítói számla naplózva van egy vagy több könyvelési felosztása van. 

<a name="accounting-distributions"></a>Könyvelési felosztások 
-------------------------

A következő gombokat használhatja a Szállítói számla oldalon a szállítói számlán szereplő minden összeg könyvelési felosztásának megtekintéséhez és lehetséges módosításához.
-   **Összegek felosztása** – Egy bizonyos sorhoz és alsorokhoz, például az adókhoz és díjakhoz tartozó könyvelési felosztások megtekintése és módosítása. Megtekintheti és módosíthatja a könyvelési felosztásokat az alárendelt sorra vonatkozóan a Forgalmi adó tranzakciók vagy a Költségtranzakciók lapon is.
    -   Szállítói számla fejléc összegek módosítása, például a költségek vagy a pénznemben megadott kerekítési összegek módosítása.
    -   Szállítói számlasorok összegének módosítása.
-   **Felosztások megtekintése** – A dokumentumban szereplő összes sorhoz tartozó könyvelési felosztás megtekintése. A könyvelési felosztásokat ebből a nézetből nem módosíthatja.
    -   A fejléc és a sorösszegek áttekintése.

Ha a szállítói számla beszerzési rendelésre hivatkozik, a könyvelési felosztások feloszthatók és módosíthatók a nem raktározott cikket tartalmazó sorokra. Ha egy szállítói számlasor nem hivatkozik egy beszerzési rendeléssorra, egy könyvelési felosztást ki is törölhet. Nem oszthat fel vagy törölhet sorokat, költségek, adók, és sorengedmények esetében. Módosíthatja a főkönyvi számlát, de az összegeket vagy százalékokat nem módosíthatja.
> [!NOTE]                                                                                                                                 
> Ha a szülő-sor nem raktározott cikket tartalmaz és a könyvelési felosztások fel vannak osztva, a gyermek sor automatikusan fel lesz osztva, hogy egyezzen a szülő sor pénzügyi dimenzióival. A könyvelési felosztásokat a gyermek sorhoz nem lehet tovább osztani vagy törölni, de a gyermek sor beállításától függően esetleg módosíthatja a főkönyvi számlát a gyermek-sor könyvelési felosztásaihoz.

## <a name="distributing-amounts"></a>Összegek elosztása
Szállítói számla bevitelekor minden összeg felosztása a következőképpen történik.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Szállítói számlasor típusa</th>
<th>Prioritási sorrend, amely meghatározza, hogy honnan jelenjen meg a fő számla</th>
<th>Prioritási sorrend, amely meghatározza, hogy mely alapértelmezett pénzügyi dimenzió jelenik meg</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Raktározott termék</td>
<td><ol>
<li>Könyvelési felosztások a beszerzési rendelési sorhoz.</li>
<li>A Fő számla mezője, a Feladás lap termékre vonatkozó Beszerzési kiadás lehetőségének kijelölésekor.</li>
</ol></td>
<td><ol>
<li>Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</li>
<li>Alapértelmezett pénzügyi dimenzió értékeinek használata a szállítói számlán.</li>
</ol></td>
</tr>
<tr class="even">
<td>Beszerzési kategória vagy termék, amelyet nem tartanak készleten</td>
<td><ol>
<li>A könyvelési felosztás a beszerzési rendelési sorhoz, ha a szállítói számlasor hivatkozik a beszerzési rendelési sorra.</li>
<li>A Fő számla mezője, a Feladás lap kiadásra vonatkozó Beszerzési kiadás lehetőségének kijelölésekor.</li>
</ol></td>
<td><ol>
<li>Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</li>
<li>Ha a fő számla felosztási számla, akkor használja az alapértelmezett értéket a felosztási számla meghatározásából.</li>
<li>Alapértelmezett pénzügyi dimenzió értékeinek használata a szállítói számlán.</li>
<li>Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</li>
<li>Használja az alapértelmezett pénzügyi dimenzió értékeket a fő számláról a Számlatükör oldalon.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Tárgyi eszköz</td>
<td><ol>
<li>A könyvelési felosztás a beszerzési rendelési sorhoz, ha a szállítói számlasor hivatkozik a beszerzési rendelési sorra.</li>
<li>Ha a Beszerzés ki van jelölve a Tranzakció típusa mező a Szállítói számla képernyőn, ha a Fő számla mező, amikor a Tárgyi eszköz feladási profilok lapján a Beszerzés van kiválasztva.</li>
<li>Ha a Beszerzés módosítás ki van jelölve a Tranzakció típusa mezőben, a Fő számla mező, amikor a Tárgyi eszköz feladási profilok lapján a Beszerzés módosítás van kiválasztva.</li>
</ol></td>
<td><ol>
<li>Használja a könyvelési felosztást a beszerzési rendelési sorra, ha a számlasor hivatkozik a beszerzési rendelési sorra.</li>
<li>Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</li>
<li>Használja az alapértelmezett pénzügyi dimenzió értékeket a fő számláról a Számlatükör oldalon.</li>
</ol></td>
</tr>
<tr class="even">
<td>A szállítói számlasoron meghatározott projekt</td>
<td><ol>
<li>Könyvelési felosztás a beszerzési rendelési sorra, ha a számlasor hivatkozik a beszerzési rendelési sorra.</li>
<li>Ha az Egyenleg van megadva a Költségek feladásánál - cikkmező a Projektcsoportok lapon, a Fő számlák mezője, amikor a Költség van megadva a Főkönyvi feladás beállítása oldalon.</li>
<li>Ha az Eredmény van megadva a Költségek feladásánál - cikkmező a Projektcsoportok lapon, a Fő számlák mezője, amikor a Költség - cikk van megadva a Főkönyvi feladás beállítása oldalon.</li>
</ol></td>
<td><ol>
<li>Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Sorengedmény</td>
<td><ol>
<li>Könyvelési felosztás a beszerzési rendelési sorra, ha a számlasor hivatkozik a beszerzési rendelési sorra.</li>
<li>A Fő számlák mezője, amikor Feladás lapján az Engedmény van kijelölve.</li>
<li>Ha a fő számla az engedményhez nincs meghatározva a feladási profilon, a beszerzési rendelési soron a kiterjesztett ár könyvelési felosztását kell megtekinteni.</li>
</ol></td>
<td><ol>
<li>Ha a számlasor hivatkozik a beszerzési rendelés-sorra, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</li>
<li>Használja a pénzügyi dimenziókat a kiterjesztett árhoz tartozó könyvelési felosztásokból a szállítói számlán.</li>
<li>Használja a pénzügyi dimenzió értékeket a szállítói számlasorhoz.</li>
<li>Használja az alapértelmezett pénzügyi dimenzió értékeket a fő számláról a Számlatükör oldalon.</li>
</ol></td>
</tr>
<tr class="even">
<td>Beszerzési költség, amely megjelenik a beszerzési rendelési sor Ár és engedmény lapján</td>
<td><ol>
<li>Könyvelési felosztás a beszerzési rendelési sorra, ha a számlasor hivatkozik a beszerzési rendelési sorra.</li>
<li>A kiterjesztett ár könyvelési felosztása a beszerzési rendelési soron.</li>
</ol></td>
<td><ol>
<li>Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</li>
<li>Használja a pénzügyi dimenziókat a kiterjesztett árhoz tartozó könyvelési felosztásokból a szállítói számlán.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Sorköltség</td>
<td><ol>
<li>Könyvelési felosztás a beszerzési rendelési sorra, ha a számlasor hivatkozik a beszerzési rendelési sorra.</li>
<li>Ha a Főkönyvi számla van megadva a terhelési Típus mezőben a Költségek kód képernyőn, a terhelési Számla mező a Költségkód oldalon.</li>
<li>Ha a Cikk van kiválasztva a tartozási Típus mezőben a Költségkód képernyőn, a könyvelési felosztás a kiterjesztett árra a beszerzési rendeléssoron.</li>
<li>Ha a Vevő/szállító van megadva a terhelési Típus mezőben a Költségek kód képernyőn, a követelési Számla mező a Költségkód oldalon.</li>
</ol></td>
<td><ol>
<li>Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</li>
<li>Használja a pénzügyi dimenziókat a kiterjesztett árhoz tartozó könyvelési felosztásokból a szállítói számlán.</li>
<li>Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</li>
<li>Használja az alapértelmezett pénzügyi dimenzió értékeket a fő számláról a Számlatükör oldalon.</li>
</ol></td>
</tr>
<tr class="even">
<td>Adó, a következő feltétellel:
<ul>
<li>Az Egyesült Államok adózási szabályainak alkalmazása lehetőség beállítása van kiválasztva a Főkönyvi paraméterek lapon.</li>
</ul></td>
<td><ol>
<li>Könyvelési felosztás a beszerzési rendelési sorra, ha a számlasor hivatkozik a beszerzési rendelési sorra.</li>
<li>A kiterjesztett ár vagy a költség könyvelési felosztása.</li>
</ol></td>
<td><ol>
<li>Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</li>
<li>Használja a pénzügyi dimenziókat a kiterjesztett árhoz tartozó könyvelési felosztásokból a szállítói számlán.</li>
<li>Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Adó, a következő feltételekkel:
<ul>
<li>Az Egyesült Államok adózási szabályainak alkalmazása lehetőség ki van törölve a Főkönyvi paraméterek lapon.</li>
<li>Az Importadó mező az áfacsoportnál bejelölve, a Forgalmiadó-csoportok lapon.</li>
</ul></td>
<td><ol>
<li>Visszaigényelhető adó esetén a Visszaigényelhető áfa mező a Főkönyvi feladási csoportok lapon.</li>
<li>Ha az adó összege nem visszatéríthető, a kiterjesztett ár vagy a könyvelési felosztás a költséghez.</li>
</ol></td>
<td><ol>
<li>Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</li>
<li>Használja a pénzügyi dimenziókat a kiterjesztett árból vagy a költséghez tartozó könyvelési felosztásokból a szállítói számlasoron.</li>
<li>Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</li>
<li>Használja az alapértelmezett pénzügyi dimenzió értékeket a fő számláról a Számlatükör oldalon.</li>
</ol></td>
</tr>
<tr class="even">
<td>Adó, a következő feltételekkel:
<ul>
<li>Az Egyesült Államok adózási szabályainak alkalmazása lehetőség ki van törölve a Főkönyvi paraméterek lapon.</li>
<li>Az Importadó mező az áfacsoportnál be van jelölve a Forgalmiadó-csoportok lapon.</li>
</ul></td>
<td><ol>
<li>Visszaigényelhető adó esetén a Visszaigényelhető áfa mező a Főkönyvi feladási csoportok lapon.</li>
<li>Ha az adó nem igényelhető vissza, az Importadó költsége mező így néz ki a Főkönyvi feladási csoportok lapon.</li>
</ol></td>
<td><ol>
<li>Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</li>
<li>Használja a pénzügyi dimenziókat a kiterjesztett árból vagy a költséghez tartozó könyvelési felosztásokból a szállítói számlasoron.</li>
<li>Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</li>
<li>Használja az alapértelmezett pénzügyi dimenzió értékeket a fő számláról a Számlatükör oldalon.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Fejlécdíj</td>
<td><ol>
<li>Ha a Főkönyvi számla van megadva a terhelési Típus mezőben a Költségek kód képernyőn, a terhelési Számla mező a Költségkód oldalon.</li>
<li>Ha a Vevő/szállító van megadva a terhelési Típus mezőben a Költségek kód képernyőn, a követelési Számla mező a Költségkód oldalon.</li>
</ol></td>
<td><ol>
<li>Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</li>
<li>Ha a fő számla felosztási számla, akkor használja az alapértelmezett értéket a felosztási számla meghatározásából.</li>
<li>Használja a pénzügyi dimenzió alapértelmezett sablon értékeket a szállítói számla fejlécéből.</li>
<li>Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</li>
<li>Használja az alapértelmezett pénzügyi dimenzió értékeket a fő számláról a Számlatükör oldalon.</li>
</ol></td>
</tr>
<tr class="even">
<td>Fejléc-engedmény</td>
<td><ol>
<li>A Fő számla mezője a Szállítói számla engedményének feladási típusához a Számlák automatikus tranzakciókhoz lapon.</li>
</ol></td>
<td><ol>
<li>Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</li>
<li>Használja a pénzügyi dimenziókat a kiterjesztett árhoz tartozó könyvelési felosztásokból a szállítói számlán.</li>
<li>Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</li>
<li>Használja az alapértelmezett pénzügyi dimenzió értékeket a fő számláról a Számlatükör oldalon.</li>
</ol></td>
</tr>
</tbody>
</table>


<a name="distributing-taxes"></a>Adó elosztása
------------------

Az adókra vonatkozó könyvelési felosztások nem hozhatók létre, amíg az adókat ki nem számítja. Forgalmi adó kiszámításához fejezzen be egyet a következő feladatok közül a Szállítói számla lapon:
-   Számla végösszegének megtekintése.
-   Az áfa megtekintése.
-   Analitikus napló megtekintése.
-   Könyvelési felosztások megtekintése a teljes szállítói számlához.
-   Helyezze a szállítói számlát várakoztatásra.
-   Szállítói számla feladása.

## <a name="subledger-journals-for-vendor-invoices"></a>Szállítói számlákhoz tartozó analitikus naplók
Szállítói számla feladása előtt meg lehet tekinteni a számla teljes könyvelési bejegyzését, amely tartalmazza a terheléseket és követeléseket, annak igazolására, hogy a számla a megfelelő számlákra van elküldve. A teljes könyvelési bejegyzésnek ezt a nézetét analitikus naplónak hívják. 

Ha az analitikus napló bejegyzése helytelen, amikor megtekinti azt a szállítói számla naplózása előtt, az analitikus napló bejegyzése nem módosítható. Ehelyett módosítania kell a könyvelési felosztásokat vagy a feladási profilt. A könyvelési felosztásokat a könyvelési tétel, a tartozás tétel vagy a jóváírás egy részének meghatározására használják. Az ellentételező analitikus naplószámla bejegyzése a feladási profilok használatával, például a szállítói számlából vagy adóból jön létre.





