---
title: Könyvelési felosztások és naplóbejegyzések szállítói számlákhoz
description: A könyvelési felosztások használatával lehet meghatározni, hogy hogyan lesz az összeg elszámolva, például hogyan lesznek könyvelve a kiadások, adó és költségek a szállítói számlán. Minden összegnek, amelyet könyvelni kell, amikor a szállítói számla naplózva van egy vagy több könyvelési felosztása van.
author: sunfzam
ms.date: 02/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendEditInvoice
audience: Application User
ms.reviewer: twheeloc
ms.custom: 26891
ms.assetid: 93dc608a-b5b4-4ec3-83c2-618e3d80a583
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f10ddf113f59da4800a97a48300ab1310bfb42dd
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/26/2022
ms.locfileid: "8358181"
---
# <a name="accounting-distributions-and-journal-entries-for-vendor-invoices"></a>Könyvelési felosztások és naplóbejegyzések szállítói számlákhoz

[!include [banner](../includes/banner.md)]

A könyvelési felosztások használatával lehet meghatározni, hogy hogyan lesz az összeg elszámolva, például hogyan lesznek könyvelve a kiadások, adó és költségek a szállítói számlán. Minden összegnek, amelyet könyvelni kell, amikor a szállítói számla naplózva van egy vagy több könyvelési felosztása van. 

## <a name="accounting-distributions"></a>Könyvelési felosztások 

A következő gombokat használhatja a Szállítói számla oldalon a szállítói számlán szereplő minden összeg könyvelési felosztásának megtekintéséhez és lehetséges módosításához.
-   **Összegek felosztása** – Egy bizonyos sorhoz és alsorokhoz, például az adókhoz és díjakhoz tartozó könyvelési felosztások megtekintése és módosítása. A gyermeksor **könyvelési** **felosztását közvetlenül az Áfatranzakciók lapon vagy a Költségtranzakciók lapon is megtekintheti és módosíthatja.**
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
<li>A <strong>Fő számla mező</strong>, amikor a Feladás lapon be van jelölve a Termék beszerzési <strong></strong> kiadása beállítás.</li>
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
<li>A <strong>Fő számla mező</strong>, amikor a Kiadás beszerzési kiadása beállítás van kiválasztva a Feladás <strong>lapon</strong>.</li>
</ol></td>
<td><ol>
<li>Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</li>
<li>Ha a fő számla felosztási számla, akkor használja az alapértelmezett értéket a felosztási számla meghatározásából.</li>
<li>Alapértelmezett pénzügyi dimenzió értékeinek használata a szállítói számlán.</li>
<li>Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</li>
<li>A fő számla alapértelmezett pénzügyi dimenzióértékének használata a <strong>Számlatükre </strong> lapon.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Tárgyi eszköz</td>
<td><ol>
<li>A könyvelési felosztás a beszerzési rendelési sorhoz, ha a szállítói számlasor hivatkozik a beszerzési rendelési sorra.</li>
<li>Ha <strong>a Beszerzés</strong> beállítás van <strong></strong><strong></strong> megjelölve a Szállítói számla lap Tranzakciótípus mezőjében, <strong>a Fő számla</strong><strong></strong><strong>mezőben, amikor a Beszerzés beállítást választja a Tárgyi eszköz feladási profilja</strong> lapon.</li>
<li>Ha <strong>a Tranzakciótípus</strong><strong></strong> mezőben be van jelölve a Beszerzés helyesbítése beállítás,<strong></strong><strong></strong><strong></strong> akkor a Fő számla mező, amikor a Tárgyi eszköz feladási profilja lapon be van jelölve a Beszerzés helyesbítése beállítás.</li>
</ol></td>
<td><ol>
<li>Használja a könyvelési felosztást a beszerzési rendelési sorra, ha a számlasor hivatkozik a beszerzési rendelési sorra.</li>
<li>Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</li>
<li>A fő számla alapértelmezett pénzügyi dimenzióértékének használata a <strong>Számlatükre</strong> lapon.</li>
</ol></td>
</tr>
<tr class="even">
<td>A szállítói számlasoron meghatározott projekt</td>
<td><ol>
<li>Könyvelési felosztás a beszerzési rendelési sorra, ha a számlasor hivatkozik a beszerzési rendelési sorra.</li>
<li>Ha az Egyenleg beállítás van <strong>megjelölve a Projektcsoportok lap Költség feladása -</strong><strong></strong> cikk mezőjében, <strong></strong><strong></strong><strong>a Fő számla mezőben, amikor a Költség beállítási lapon a Költség beállítás van megjelölve.</strong><strong></strong></li>
<li>Ha <strong>az Eredmény</strong><strong>beállítás van megjelölve a Projektcsoportok lap Költség feladása -</strong><strong></strong> cikk mezőjében, <strong></strong><strong>akkor a Fő számla mezőben, amikor a Költség - cikk beállítás van</strong><strong>kiválasztva a Főkönyvi feladás beállítása lapon.</strong></li>
</ol></td>
<td><ol>
<li>Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Sorengedmény</td>
<td><ol>
<li>Könyvelési felosztás a beszerzési rendelési sorra, ha a számlasor hivatkozik a beszerzési rendelési sorra.</li>
<li>A <strong>Fő számla mező</strong>, ha <strong>az</strong> engedmény ki van választva a Feladás <strong>lapon</strong>.</li>
<li>Ha a fő számla az engedményhez nincs meghatározva a feladási profilon, a beszerzési rendelési soron a kiterjesztett ár könyvelési felosztását kell megtekinteni.</li>
</ol></td>
<td><ol>
<li>Ha a számlasor hivatkozik a beszerzési rendelés-sorra, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</li>
<li>Használja a pénzügyi dimenziókat a kiterjesztett árhoz tartozó könyvelési felosztásokból a szállítói számlán.</li>
<li>Használja a pénzügyi dimenzió értékeket a szállítói számlasorhoz.</li>
<li>A fő számla alapértelmezett pénzügyi dimenzióértékének használata a <strong>Számlatükre</strong> lapon.</li>
</ol></td>
</tr>
<tr class="even">
<td><strong>A beszerzési rendelési sor</strong> Ár és engedmény lapján megadott beszerzési költség</td>
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
<li>Ha <strong>a Költségkód</strong><strong>lap Tartozik típus</strong><strong></strong> mezőjében a Főkönyvi számla beállítás van megjelölve,<strong></strong><strong>a Költségkód lap Tartozik számla mezője.</strong></li>
<li>Ha <strong>a Költségkód</strong><strong>lap Terheléstípus</strong><strong></strong> mezőjében a Cikk beállítást választotta, a beszerzési rendelés sorának kiterjesztett árára vonatkozó könyvelési felosztás.</li>
<li>Ha <strong>a Költségkód lap Tartozik típus</strong><strong></strong> mezőjében a Vevő/<strong></strong> szállító beállítás van megjelölve, <strong></strong><strong>akkor a Költségkód lap Követel számla mezője.</strong></li>
</ol></td>
<td><ol>
<li>Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</li>
<li>Használja a pénzügyi dimenziókat a kiterjesztett árhoz tartozó könyvelési felosztásokból a szállítói számlán.</li>
<li>Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</li>
<li>A fő számla alapértelmezett pénzügyi dimenzióértékének használata a <strong>Számlatükre</strong> lapon.</li>
</ol></td>
</tr>
<tr class="even">
<td>Adó, a következő feltétellel:
<ul>
<li>A <strong>Főkönyvi</strong><strong>paraméterek lapon be van jelölve az Amerikai Egyesült Államok adózási szabályainak alkalmazása</strong> beállítás.</li>
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
<li>A Főkönyvi <strong>paraméterek lapon törölve van az Amerikai Egyesült</strong><strong>Államok adózási szabályainak alkalmazása</strong> beállítás.</li>
<li>Az <strong>áfacsoporthoz</strong> használt áfa mező üresen van az Áfacsoportok <strong></strong> lapon.</li>
</ul></td>
<td><ol>
<li>Ha vissza lehet állítani az adóösszeget, <strong></strong><strong></strong> akkor a Főkönyvi feladási csoportok lapon található Visszakövetelés mezője használható.</li>
<li>Ha az adó összege nem visszatéríthető, a kiterjesztett ár vagy a könyvelési felosztás a költséghez.</li>
</ol></td>
<td><ol>
<li>Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</li>
<li>Használja a pénzügyi dimenziókat a kiterjesztett árból vagy a költséghez tartozó könyvelési felosztásokból a szállítói számlasoron.</li>
<li>Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</li>
<li>A fő számla alapértelmezett pénzügyi dimenzióértékének használata a <strong>Számlatükre</strong> lapon.</li>
</ol></td>
</tr>
<tr class="even">
<td>Adó, a következő feltételekkel:
<ul>
<li>A Főkönyvi paraméterek lapon törölve van az Amerikai Egyesült <strong>Államok adózási szabályainak alkalmazása</strong> beállítás.</li>
<li>Az <strong>áfacsoporthoz</strong> használt áfa mező be van jelölve az Áfacsoportok <strong>lapon</strong>.</li>
</ul></td>
<td><ol>
<li>Ha vissza lehet állítani az adóösszeget, <strong></strong><strong></strong> akkor a Főkönyvi feladási csoportok lapon található Visszakövetelés mezője használható.</li>
<li>Ha az adóösszeg nem állítható vissza, akkor <strong>a Főkönyvi feladási csoportok oldal Áfaköltség</strong><strong>használata mezője használható</strong>.</li>
</ol></td>
<td><ol>
<li>Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</li>
<li>Használja a pénzügyi dimenziókat a kiterjesztett árból vagy a költséghez tartozó könyvelési felosztásokból a szállítói számlasoron.</li>
<li>Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</li>
<li>A fő számla alapértelmezett pénzügyi dimenzióértékének használata a <strong>Számlatükre</strong> lapon.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Fejlécdíj</td>
<td><ol>
<li>Ha <strong>a</strong> Költségkód <strong>lap Tartozik típus</strong><strong></strong> mezőjében a Főkönyvi számla beállítás van megjelölve,<strong></strong><strong>a Költségkód lap Tartozik számla mezője.</strong></li>
<li>Ha <strong>a Költségkód lap Tartozik típus</strong><strong></strong> mezőjében a Vevő/<strong></strong> szállító beállítás van megjelölve, <strong></strong><strong>akkor a Költségkód lap Követel számla mezője.</strong></li>
</ol></td>
<td><ol>
<li>Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</li>
<li>Ha a fő számla felosztási számla, akkor használja az alapértelmezett értéket a felosztási számla meghatározásából.</li>
<li>Használja a pénzügyi dimenzió alapértelmezett sablon értékeket a szállítói számla fejlécéből.</li>
<li>Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</li>
<li>A fő számla alapértelmezett pénzügyi dimenzióértékének használata a <strong>Számlatükre</strong> lapon.</li>
</ol></td>
</tr>
<tr class="even">
<td>Fejléc-engedmény</td>
<td><ol>
<li>A <strong>Szállítói számla</strong> engedményének <strong>feladási típus</strong> fő számla mezője az automatikus <strong>tranzakciók számlája</strong> lapon.</li>
</ol></td>
<td><ol>
<li>Ha a számlasor beszerzési rendelés-sorra hivatkozik, használja a könyvelési felosztást a beszerzési rendelési sorhoz.</li>
<li>Használja a pénzügyi dimenziókat a kiterjesztett árhoz tartozó könyvelési felosztásokból a szállítói számlán.</li>
<li>Használja a pénzügyi dimenzió értéket a szállítói számlasorból.</li>
<li>A fő számla alapértelmezett pénzügyi dimenzióértékének használata a <strong>Számlatükre</strong> lapon.</li>
</ol></td>
</tr>
</tbody>
</table>


## <a name="distributing-taxes"></a>Adók elosztása

Az adókra vonatkozó könyvelési felosztások nem hozhatók létre, amíg az adókat ki nem számítja. Az áfa kiszámításához **a Szállítói számla lapon a következő műveletek egyikét kell** elvégeznie:
-   Számla végösszegének megtekintése.
-   Az áfa megtekintése.
-   Analitikus napló megtekintése.
-   Könyvelési felosztások megtekintése a teljes szállítói számlához.
-   Helyezze a szállítói számlát várakoztatásra.
-   Szállítói számla feladása.

## <a name="subledger-journals-for-vendor-invoices"></a>Szállítói számlákhoz tartozó analitikus naplók
Szállítói számla feladása előtt meg lehet tekinteni a számla teljes könyvelési bejegyzését, amely tartalmazza a terheléseket és követeléseket, annak igazolására, hogy a számla a megfelelő számlákra van elküldve. A teljes könyvelési bejegyzésnek ezt a nézetét analitikus naplónak hívják. 

Ha az analitikus napló bejegyzése helytelen, amikor megtekinti azt a szállítói számla naplózása előtt, az analitikus napló bejegyzése nem módosítható. Ehelyett módosítania kell a könyvelési felosztásokat vagy a feladási profilt. A könyvelési felosztásokat a könyvelési tétel, a tartozás tétel vagy a jóváírás egy részének meghatározására használják. Az ellentételező analitikus naplószámla bejegyzése a feladási profilok használatával, például a szállítói számlából vagy adóból jön létre.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
