---
title: "Alapértelmezett ellenszámlák szállítóiszámla-naplók és számla-jóváhagyási naplók számára"
description: "A jelent témakör segítségével eldöntheti, hogy hová rendelje hozzá az alapértelmezett számlákat a számlanaplókhoz."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: bf7af869e44a60d07d66e83bfb55bd0cc7edfb91
ms.contentlocale: hu-hu
ms.lasthandoff: 11/03/2017

---

# <a name="default-offset-accounts-for-vendor-invoice-journals-and-invoice-approval-journals"></a>Alapértelmezett ellenszámlák szállítóiszámla-naplók és számla-jóváhagyási naplók számára

[!include[banner](../includes/banner.md)]




Az alapértelmezett ellenszámlák a következő szállítói számla naplóoldalakon használatosak:

-   Számlanapló
-   Számla-jóváhagyási napló

Az alábbi táblázat segítségével eldöntheti, hogy hová rendelje hozzá az alapértelmezett számlákat a számlanaplókhoz.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Alapértelmezett számlák beállítása itt</th>
<th>Hol vannak az alapértelmezett számlák</th>
<th>Hogyan befolyásolja ez a lehetőség a feldolgozást</th>
<th>Mikor kell használni ezt a lehetőséget</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Szállítócsoport</strong> – Állítsa be az alapértelmezett ellenszámlákat a szállítócsoportoknak az <strong>Alapértelmezett számla beállítása</strong> lapon, amelyet a <strong>Szállítócsoportok</strong> oldalról tud megnyitni.</td>
<td><ul>
<li>Szállítói számla</li>
<li>Naplóbejegyzések szállítói számlákhoz a szállítói csoportban, ha az alapértelmezett számlák nincsenek megadva a szállítói számlákhoz</li>
</ul></td>
<td>Az alapértelmezett ellenszámlák szállítócsoportok számára szállítói alapértelmezett ellenszámlákként jelennek meg az <strong>Alapértelmezett számla beállítása</strong> oldalon. Ezt a lapot megnyithatja az <strong>Összes szállító</strong> listaoldaláról.</td>
<td>Ezt a lehetőséget akkor használja, ha általában azonos típusú elemeket szokott fizetni, azonos szállítói csoportok esetében.</td>
</tr>
<tr class="even">
<td><strong>Szállítói számla</strong> – Állítsa be az alapértelmezett számlákat a szállítói számlákhoz az <strong>Alapértelmezett számla beállítása</strong> lapon, amelyet a <strong>Szállítók</strong> oldalról tud megnyitni.</td>
<td>A szállítói számlához tartozó naplóbejegyzések</td>
<td>A szállítói számlák alapértelmezett ellenszámlái alapértelmezett ellenszámlaként jelennek meg a naplóbejegyzésekben a szállítói számlánál.</td>
<td>Ezt a lehetőséget akkor használja, ha általában azonos típusú elemeket szokott fizetni, ugyanazoktól a szállítóktól.</td>
</tr>
<tr class="odd">
<td><strong>Naplónevek</strong> – Állítsa be az alapértelmezett ellenszámlákat a naplókhoz a <strong>Naplónevek</strong> oldalon. Válassza ki a <strong>Rögzített ellenszámla</strong> lehetőséget. Vegye figyelembe, hogy nem adhat meg alapértelmezett ellenszámlákat a naplóneveken, ha a naplónevek naplótípusa <strong>Számlaregiszter</strong> vagy <strong>Jóváhagyás</strong>.</td>
<td><ul>
<li>Naplófejléc, amely a naplónevet használja.</li>
<li>Naplóbejegyzések a naplókban, amelyek a naplónevet használják</li>
</ul></td>
<td>Ha a <strong>Rögzített ellenszámla</strong> opció a <strong>Naplónevek</strong> lapon be van jelölve, a naplónévhez megadott ellenszámla felülbírálja a szállítóhoz vagy szállítócsoporthoz tartozó alapértelmezett ellenszámlát.</td>
<td>Az opció segítségével naplókat állíthat be meghatározott költségekre és kiadásokra, amelyek bizonyos számlákat terhelnek, függetlenül attól, hogy ki a szállító vagy mely szállítói csoporthoz tartozik.</td>
</tr>
<tr class="even">
<td><strong>Naplónevek</strong> – Állítsa be az alapértelmezett ellenszámlákat a naplókhoz a <strong>Naplónevek</strong> oldalon. Törölje a <strong>Rögzített ellenszámla</strong> lehetőséget. Vegye figyelembe, hogy nem adhat meg alapértelmezett ellenszámlákat a naplóneveken, ha a naplónevek naplótípusa <strong>Számlaregiszter</strong> vagy <strong>Jóváhagyás</strong>.</td>
<td><ul>
<li>Napló fejléce</li>
<li>Naplóbejegyzések a naplókban, amelyek a naplónevet használják</li>
</ul></td>
<td>Az alapértelmezett bejegyzések a napló fejlécének oldalain használatosak és az ellenszámla a napló fejlécének oldalán egy alapértelmezett bejegyzésként használatos a napló bizonylat oldalakon. Alapértelmezett számlák a <strong>Naplónevek </strong>oldalon csak akkor használatosak, ha az alapértelmezett számlák nincsenek beállítva a szállítói számlára.</td>
<td>Használja ezt az opciót az alapértelmezett számlák beállításához, amelyeket akkor használ, amikor az alapértelmezett szállítói ellenszámla nincs hozzárendelve.</td>
</tr>
<tr class="odd">
<td><strong>Napló fejléce</strong> – Állítson be alapértelmezett ellenszámlát egy naplóhoz, amelyet alapértelmezett bejegyzésként használhat a napló bizonylat oldalakon. Vegye figyelembe, hogy nem adhat meg alapértelmezett ellenszámlákat a napló fejlécén, ha a naplónevek naplótípusa <strong>Számlaregiszter</strong> vagy <strong>Jóváhagyás</strong>.</td>
<td>A napló naplóbejegyzések a naplóban</td>
<td>Az alapértelmezett ellenszámla egy naplóhoz alapértelmezett bejegyzésként használatos a napló bizonylat oldalakon.</td>
<td>A beállítás segítségével felgyorsítható az adatbevitel, ha a naplóban lévő legtöbb bejegyzés ugyanazzal az ellenszámlával rendelkezik.</td>
</tr>
</tbody>
</table>






