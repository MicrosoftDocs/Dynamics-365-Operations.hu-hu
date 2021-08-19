---
title: Eőfizetés eladási árai
description: Amikor előfizetést hoz létre, az eladási ár az Eladási ár (előfizetés) képernyőn létrehozott eladási ár beállításból jön létre.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMASalespriceSubscription
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 59e9084c1b1a2d27ac7a813dd412ebf49011252a199742b31af7c3c328c5ffd2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/05/2021
ms.locfileid: "6712934"
---
# <a name="subscription-sales-prices"></a>Eőfizetés eladási árai   

[!include [banner](../includes/banner.md)]


Amikor előfizetést hoz létre, az eladási ár az **Eladási ár (előfizetés)** képernyőn létrehozott eladási ár beállításból jön létre.

Az **Eladási ár (előfizetés)** képernyőn egy-egy előfizetéshez is készíthet eladási árat, vagy létrehozhat olyan eladási árat, amely általánosabban érvényes. Az eladási ár alkalmazásához az előfizetésre, meg kell egyeznie az előfizetés időszakkódjának és pénznemének az eladási ár időszakkódjával és pénznemével.

Ha az előfizetés és az eladási ár időszakkódja és pénzneme megegyezik, akkor az előfizetés eladási ára az alábbi táblázatban szereplő prioritások alapján választható ki. Az üres cella üres mezőt, az X pedig a előfizetésből létrejött tranzakcióban szereplő értékkel megegyező értéket jelent.

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>. prioritás</p></th>
<th><p><strong>Kategória</strong></p></th>
<th><p><strong>Projektazonosító</strong></p></th>
<th><p><strong>Előfizetés</strong></p></th>
<th><p><strong>Értékesítés pénzneme</strong></p></th>
<th><p><strong>Időszak kódja</strong></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>X</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


Az előfizetési díj létrehozásakor a legnagyobb részletezettségű eladási ár (a fenti táblázatban jelöltek szerint) lesz az előfizetés eladási ára.

## <a name="update-and-index-subscription-sales-prices"></a>Előfizetési árak frissítése és indexelése

Az előfizetés eladási árat az alapár vagy az indexár frissítésével lehet módosítani. Százalékosan vagy új érték megadásával lehet átállítani.

## <a name="subscription-fee-sales-prices"></a>Előfizetési díj eladási árak

Előfizetési díj létrehozásakor az előfizetés eladási árbeállítása a konkrét eladási ár alapja. Használni az előfizetés eladási árbeállításából az alapárat lehet, vagy létre lehet hozni indexelt eladási árakat.

## <a name="example"></a>Példa

Szeretne 500 eurós előfizetés eladási árakat beállítani, egy új, 9030 kódú projekt számra. Az **Eladási ár (előfizetés)** képernyőn létrehoz egy előfizetési eladásiár-sort a következő táblázat szerint.

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Érvényesség kezdete</p></th>
<th><p>Kategória</p></th>
<th><p>Project</p></th>
<th><p>Előfizetés</p></th>
<th><p>Időszak kódja</p></th>
<th><p>Értékesítés pénzneme</p></th>
<th><p>Eladási ár</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2006. 08. 28.</p></td>
<td></td>
<td><p>9030</p></td>
<td></td>
<td><p>Hónap</p></td>
<td><p>HUF</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Ne feledje, hogy a **Kategória** és az **Előfizetés** mező üres.

Ezután a következő előfizetéseket hozza létre.

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Előfizetés szolgáltatásra</p></th>
<th><p>Project</p></th>
<th><p>Előfizetési csoport</p></th>
<th><p>Kategória</p></th>
<th><p>Pénznem</p></th>
<th><p>Időszak kódja</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>Al1</p></td>
<td><p>Alkateg1</p></td>
<td><p>HUF</p></td>
<td><p>Havi</p></td>
</tr>
<tr class="even">
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>Al1</p></td>
<td><p>Alkateg2</p></td>
<td><p>HUF</p></td>
<td><p>Havi</p></td>
</tr>
</tbody>
</table>


Ekkor létre hozza az előfizetési díjakat mindkét előfizetéshez a Al1 előfizetési csoportban:

1.  Kattintson a következőkre: **Szolgáltatáskezelés**\>**Beállítás**\>**Szolgáltatási előfizetések**\>**Előfizetési csoportok**.

2.  Az **Előfizetési csoportok** képernyőn kattintson ide: **Funkció** \> **Előfizetési díj létrehozása**.

3.  Írja be a megfelelő adatokat az **Előfizetési díj létrehozása** képernyő mezőibe. A díjtranzakciókról az [Előfizetési díj tranzakcióinak létrehozása](create-subscription-fee-transactions.md) című témakörben olvashat bővebben.

Előfizetési díjak 500 EURÓS eladási árral rendelkezve mindkét előfizetéséhez, létrejönnek a következő táblázatban látható módon.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Projekt dátuma</p></th>
<th><p>Előfizetés szolgáltatásra</p></th>
<th><p>Project</p></th>
<th><p>Kategória</p></th>
<th><p>Kezdő dátum</p></th>
<th><p>Záró dátum</p></th>
<th><p>Értékesítés pénzneme</p></th>
<th><p>Eladási ár</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2006. 08. 28.</p></td>
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>Alkateg1</p></td>
<td><p>2007. 01. 01.</p></td>
<td><p>2007. 03. 31.</p></td>
<td><p>HUF</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>2006. 08. 28.</p></td>
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>Alkateg2</p></td>
<td><p>2007. 01. 01.</p></td>
<td><p>2007. 03. 31.</p></td>
<td><p>HUF</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Később úgy dönt, hogy a 9030-as projekt Alkateg1 kategóriájához szeretne eladási árakat megadni. Ezért a 9030-as projekt és a Alkateg1 díjkategória kombinációjához létrehoz egy új eladásiár-sort 550 eurós eladási árral. Ezzel már két előfizetés eladásiár-sor szerepel a 9030-as projektnél, a következő táblázatban látható módon:

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Érvényesség kezdete</p></th>
<th><p>Kategória</p></th>
<th><p>Project</p></th>
<th><p>Előfizetés</p></th>
<th><p>Időszak kódja</p></th>
<th><p>Pénznem</p></th>
<th><p>Eladási ár</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2007. 08. 28.</p></td>
<td></td>
<td><p>9030</p></td>
<td></td>
<td><p>Hónap</p></td>
<td><p>HUF</p></td>
<td><p>500</p></td>
</tr>
<tr class="even">
<td><p>2007. 08. 28.</p></td>
<td><p>Alkateg1</p></td>
<td><p>9030</p></td>
<td></td>
<td><p>Hónap</p></td>
<td><p>HUF</p></td>
<td><p>550</p></td>
</tr>
</tbody>
</table>


A fentebb részletezett eljárást ismételve az Alkateg1 előfizetési csoport mindkét előfizetéséhez létrehoz egy előfizetési díjat. A következő tábla megmutatja, hogy két tranzakció jön létre, vagyis előfizetési csoporthoz társított előfizetésenként egy:

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Projekt dátuma</p></th>
<th><p>Előfizetés</p></th>
<th><p>Project</p></th>
<th><p>Kategória</p></th>
<th><p>Kezdő dátum</p></th>
<th><p>Befejezés</p></th>
<th><p>Értékesítés pénzneme</p></th>
<th><p>Eladási ár</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2007. 07. 28.</p></td>
<td><p>00020_135</p></td>
<td><p>9030</p></td>
<td><p>Alkateg1</p></td>
<td><p>2008. 01. 01.</p></td>
<td><p>2008. 03. 31.</p></td>
<td><p>HUF</p></td>
<td><p>550</p></td>
</tr>
<tr class="even">
<td><p>2008. 07. 28.</p></td>
<td><p>00021_135</p></td>
<td><p>9030</p></td>
<td><p>Alkateg2</p></td>
<td><p>2008. 01. 01.</p></td>
<td><p>2008. 03. 31.</p></td>
<td><p>HUF</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


A 00020\_135-ös előfizetéshez tartozó első tranzakcióban az 550 eurós eladási ár egy adott projekt és kategória kombinációjához beállított előfizetés eladási árból származik. A 00021\_135-ös előfizetéshez tartozó második tranzakcióban azért szerepel 500 euró a projekt-előfizetés eladási áraként, mert a 9030-as projekt és az Alkateg2 kategória kombinációjához nincs ár beállítva.

## <a name="see-also"></a>Lásd még

[Előfizetési árak frissítése és indexelése](update-and-index-subscription-sales-prices.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]