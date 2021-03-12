---
title: Könyvelési felosztások és naplóbejegyzések szabadszöveges számlákhoz
description: A könyvelési felosztások alkalmazásával meg lehet határozni, hogy hogyan legyen az összeg elszámolva, például hogyan lesznek könyvelve a bevételek, adó és költségek a szabadszöveges számlán. Minden olyan összeg, amelyet könyvelni kell a szabadszöveges számla naplózása esetén, egy vagy több könyvelési felosztással rendelkezik.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: roschlom
ms.custom: 3141
ms.assetid: fecd17a2-d7b4-4a20-ac81-eb71abbfa9d1
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f3ee26825ec48a8e8e32401ceaa8c80ecd679d2e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993196"
---
# <a name="accounting-distributions-and-subledger-entries-for-free-text-invoices"></a>Könyvelési felosztások és naplóbejegyzések szabadszöveges számlákhoz

[!include [banner](../includes/banner.md)]

A könyvelési felosztások alkalmazásával meg lehet határozni, hogy hogyan legyen az összeg elszámolva, például hogyan lesznek könyvelve a bevételek, adó és költségek a szabadszöveges számlán. Minden olyan összeg, amelyet könyvelni kell a szabadszöveges számla naplózása esetén, egy vagy több könyvelési felosztással rendelkezik.

<a name="accounting-distributions"></a>Könyvelési felosztások
------------------------

A következő gombokat használhatja a Szabadszöveges számla oldalon a szabadszöveges számlán szereplő minden összeg könyvelési felosztásának megtekintéséhez és lehetséges módosításához.

-   **Összegek felosztása**—Egy bizonyos sorhoz és alsorokhoz, például az adókhoz és díjakhoz tartozó könyvelési felosztások megtekintése és módosítása. Megtekintheti és módosíthatja a könyvelési felosztásokat az alárendelt sorra vonatkozóan a Forgalmi adó tranzakciók vagy a Költségtranzakciók lapon is.
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
<li>Használja az alapértelmezett pénzügyi dimenzió értékeket a főkönyv számlájáról a Számlatükör oldalon.</li>
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
<li>Használja az alapértelmezett pénzügyi dimenzió értékeket a főkönyv számlájáról a Számlatükör oldalon.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Szabadszöveges számla engedmény összege</td>
<td>A vevő fő számlája engedmény a készpénzfizetési engedmények lapján található engedmények mezője.</td>
<td><ol>
<li>Ha a fő számla felosztási számla, akkor használja az alapértelmezett értéket a felosztási számla meghatározásából.</li>
<li>Ha a fő számla nem felosztási számla, használja a szabadszöveges számlasoron a pénzügyi dimenzió alapértelmezett sablonját.</li>
<li>Használja az alapértelmezett pénzügyi dimenzió értékeit a szabaszöveges számlasoron.</li>
<li>Használja az alapértelmezett pénzügyi dimenzió értékeket a főkönyv számlájáról a Számlatükör oldalon.</li>
</ol></td>
</tr>
<tr class="even">
<td>Szabadszöveges számla adó összege</td>
<td>A főkönyvi feladási csoportok lapon található forgalmi adó kötelezettségek mezője.</td>
<td><ol>
<li>Hazsnálja a pénzügyi dimenziókat, amelyeket a költség sor összeg felosztások vagy a szabadszöveges számla sor összegek szerint határozzák meg.</li>
<li>Használja az alapértelmezett pénzügyi dimenzió értékeit a szabaszöveges számlasoron.</li>
<li>Használja az alapértelmezett pénzügyi dimenzió értékeket a főkönyv számlájáról a Számlatükör oldalon.</li>
</ol></td>
</tr>
<tr class="odd">
<td>Szabadszöveges számla kötlség sor összege</td>
<td>A költségek kódlapon található hitel számla mezője.</td>
<td><ol>
<li>Ha a fő számla felosztási számla, akkor használja az alapértelmezett értéket a felosztási számla meghatározásából.</li>
<li>Ha a fő számla nem felosztási számla, használja a szabadszöveges számlasoron a pénzügyi dimenzió alapértelmezett sablonját.</li>
<li>Használja az alapértelmezett pénzügyi dimenzió értékeit a szabaszöveges számlasoron.</li>
<li>Használja az alapértelmezett pénzügyi dimenzió értékeket a főkönyv számlájáról a Számlatükör oldalon.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="distributing-taxes"></a>Adók elosztása
Az adókra vonatkozó könyvelési felosztások nem hozhatók létre, amíg az adókat ki nem számítja. Forgalmi adó kiszámításához fejezzen be egyet a következő feladatok közül a Szabadszöveges számla képernyőjén:
-   Az áfa megtekintése.
-   Számla végösszegének megtekintése.
-   Pénzforgalom megtekintése.
-   Az egész szabadszöveges számla könyvelési felosztásainak megtekintése.
-   Analitikus napló megtekintése.

## <a name="subledger-journals-for-free-text-invoices"></a>A szabadszöveges számlák analitikus naplóinak megtekintése
Szabadszöveges számla feladása előtt meg lehet tekinteni a számla teljes könyvelési bejegyzését, amely tartalmazza a terheléseket és követeléseket, azért, hogy igazolják, hogy a számla a megfelelő számlákra van elküldve. A teljes könyvelési bejegyzésnek ezt a nézetét analitikus naplónak hívják. Ha az analitikus napló bejegyzése helytelen, amikor megtekinti azt a szabadszöveges számla naplózása előtt, az analitikus napló bejegyzése nem módosítható. Ehelyett módosítania kell a könyvelési felosztásokat vagy a feladási profilt. A könyvelési felosztásokat a könyvelési tétel, a tartozás tétel vagy a jóváírás egy részének meghatározására használják. Az beszámítási analitikus naplószámla számlabejegyzése a feladási profilok feladásából, például a vevői számlából vagy az adóból jön létre.



