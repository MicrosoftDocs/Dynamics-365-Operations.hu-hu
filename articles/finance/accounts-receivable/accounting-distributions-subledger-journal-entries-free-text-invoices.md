---
title: Könyvelési felosztások és naplóbejegyzések szabadszöveges számlákhoz
description: A könyvelési felosztások alkalmazásával meg lehet határozni, hogy hogyan legyen az összeg elszámolva, például hogyan lesznek könyvelve a bevételek, adó és költségek a szabadszöveges számlán. Minden olyan összeg, amelyet könyvelni kell a szabadszöveges számla naplózása esetén, egy vagy több könyvelési felosztással rendelkezik.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.custom: 3141
ms.assetid: fecd17a2-d7b4-4a20-ac81-eb71abbfa9d1
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5120c4e75e821776201d5add2d498feb94d0297
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778411"
---
# <a name="accounting-distributions-and-subledger-entries-for-free-text-invoices"></a>Könyvelési felosztások és naplóbejegyzések szabadszöveges számlákhoz

[!include [banner](../includes/banner.md)]

A könyvelési felosztások alkalmazásával meg lehet határozni, hogy hogyan legyen az összeg elszámolva, például hogyan lesznek könyvelve a bevételek, adó és költségek a szabadszöveges számlán. Minden olyan összeg, amelyet könyvelni kell a szabadszöveges számla naplózása esetén, egy vagy több könyvelési felosztással rendelkezik.

## <a name="accounting-distributions"></a>Könyvelési felosztások

A Szabadszöveges **számla** lapon a következő gombokkal lehet megtekinteni, esetleg módosítani a szabadszöveges számla egyes összegének könyvelési felosztását.

-   **Összegek felosztása**—Egy bizonyos sorhoz és alsorokhoz, például az adókhoz és díjakhoz tartozó könyvelési felosztások megtekintése és módosítása. A gyermeksor **könyvelési** **felosztását közvetlenül az Áfatranzakciók lapon vagy a Költségtranzakciók lapon is megtekintheti és módosíthatja.**
    -   Módosítsa a szabadszöveges számla fejléc összegeit, például a költség vagy a pénznemben megadott kerekítési összegeket.
    -   Módosítsa a Szabadszöveges számla sor összegeit.
-   **Felosztások megtekintése**—A dokumentumban szereplő összes sorhoz tartozó könyvelési felosztás megtekintése. A könyvelési felosztásokat ebből a nézetből nem módosíthatja.
    -   A fejléc és a sorösszegek áttekintése.

## <a name="distributing-amounts"></a>Összegek elosztása
Szabadszöveges számla bevitelekor minden összeg felosztása a következőképpen történik.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Az pénzösszeg típusa</th>
<th>Ahol a fő számla látható.</th>
<th>Prioritási sorrend, amely meghatározza, hogy mely alapértelmezett pénzügyi dimenzió jelenik meg</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Szabadszöveges számla sora</td>
<td>A főkönyv számlasor a szabadszöveges számlasoron.</td>
<td><ol>
<li>Ha a fő számla felosztási számla, akkor használja az alapértelmezett értéket a felosztási számla meghatározásából.</li>
<li>Ha a fő számla nem felosztási számla, használja a szabadszöveges számlasoron a pénzügyi dimenzió alapértelmezett sablonját.</li>
<li>Használja az alapértelmezett pénzügyi dimenzió értékeit a szabaszöveges számlasoron.</li>
<li>Használja a főkönyvi számla alapértelmezett pénzügyi dimenzióértékét a Számlatükre lapon.</li>
</ol></td>
</tr>
<tr class="even">
<td>A tárgyi eszköz száma és értékmodell kombinációjának szabadszöveges számlasora
<div class="alert">
<table>
<thead>
<tr class="header">
<th><strong>Megjegyzés</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>A szabadszöveges számlasoron található fő számla a tárgyi eszköz kivezetési számlája.</td>
</tr>
</tbody>
</table>
</div></td>
<td>A főkönyv számlasor a szabadszöveges számlasoron.</td>
<td><ol>
<li>Használja az alapértelmezett pénzügyi dimenzió értékeit a szabaszöveges számlasoron.</li>
<li>Használja a főkönyvi számla alapértelmezett pénzügyi dimenzióértékét a Számlatükre lapon.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Szabadszöveges számla engedmény összege</td>
<td>A Készpénzfizetési engedmények lap Vevői engedmények fő számlája mezője.</td>
<td><ol>
<li>Ha a fő számla felosztási számla, akkor használja az alapértelmezett értéket a felosztási számla meghatározásából.</li>
<li>Ha a fő számla nem felosztási számla, használja a szabadszöveges számlasoron a pénzügyi dimenzió alapértelmezett sablonját.</li>
<li>Használja az alapértelmezett pénzügyi dimenzió értékeit a szabaszöveges számlasoron.</li>
<li>Használja a főkönyvi számla alapértelmezett pénzügyi dimenzióértékét a Számlatükre lapon.</li>
</ol></td>
</tr>
<tr class="even">
<td>Szabadszöveges számla adó összege</td>
<td>A Fizetendő áfa mező a Főkönyvi feladási csoportok lapon.</td>
<td><ol>
<li>Hazsnálja a pénzügyi dimenziókat, amelyeket a költség sor összeg felosztások vagy a szabadszöveges számla sor összegek szerint határozzák meg.</li>
<li>Használja az alapértelmezett pénzügyi dimenzió értékeit a szabaszöveges számlasoron.</li>
<li>Használja a főkönyvi számla alapértelmezett pénzügyi dimenzióértékét a Számlatükre lapon.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Szabadszöveges számla kötlség sor összege</td>
<td>A Költségkód oldalon található Követel számla mező.</td>
<td><ol>
<li>Ha a fő számla felosztási számla, akkor használja az alapértelmezett értéket a felosztási számla meghatározásából.</li>
<li>Ha a fő számla nem felosztási számla, használja a szabadszöveges számlasoron a pénzügyi dimenzió alapértelmezett sablonját.</li>
<li>Használja az alapértelmezett pénzügyi dimenzió értékeit a szabaszöveges számlasoron.</li>
<li>Használja a főkönyvi számla alapértelmezett pénzügyi dimenzióértékét a Számlatükre lapon.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="distributing-taxes"></a>Adók elosztása
Az adókra vonatkozó könyvelési felosztások nem hozhatók létre, amíg az adókat ki nem számítja. Az áfa kiszámításához **a** Szabadszöveges számla lapon a következő műveletek egyikét kell elvégeznie:
-   Az áfa megtekintése.
-   Számla végösszegének megtekintése.
-   Pénzforgalom megtekintése.
-   Az egész szabadszöveges számla könyvelési felosztásainak megtekintése.
-   Analitikus napló megtekintése.

## <a name="subledger-journals-for-free-text-invoices"></a>A szabadszöveges számlák analitikus naplóinak megtekintése
Szabadszöveges számla feladása előtt meg lehet tekinteni a számla teljes könyvelési bejegyzését, amely tartalmazza a terheléseket és követeléseket, azért, hogy igazolják, hogy a számla a megfelelő számlákra van elküldve. A teljes könyvelési bejegyzésnek ezt a nézetét analitikus naplónak hívják. Ha az analitikus napló bejegyzése helytelen, amikor megtekinti azt a szabadszöveges számla naplózása előtt, az analitikus napló bejegyzése nem módosítható. Ehelyett módosítania kell a könyvelési felosztásokat vagy a feladási profilt. A könyvelési felosztásokat a könyvelési tétel, a tartozás tétel vagy a jóváírás egy részének meghatározására használják. Az beszámítási analitikus naplószámla számlabejegyzése a feladási profilok feladásából, például a vevői számlából vagy az adóból jön létre.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
