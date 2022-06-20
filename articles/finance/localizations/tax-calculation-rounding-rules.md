---
title: Adószámítás kerekítési szabályai
description: Ez a cikk az adószámítási szolgáltatás adószámítási paramétereiben használt kerekítési szabályokkal kapcsolatban tartalmaz tájékoztatást.
author: kailiang
ms.date: 07/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 0f6182ab18a5a408a6e526feec7014ccdfce8af0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858301"
---
# <a name="tax-calculation-rounding-rules"></a>Adószámítás kerekítési szabályai

[!include [banner](../includes/banner.md)]

Ez a cikk arról nyújt tájékoztatást, hogyan működnek a kerekítési szabályok az adószámítási szolgáltatás adószámítási paramétereiben.

> [!NOTE] 
> Ha az adószámítási szolgáltatás engedélyezve van, a kerekítési szabályok az **Értékesítési adó kód** és az **Értékesítési adócsoport** lapokon nem érvényesek.

Az adószámítási szolgáltatás kerekítési szabályainak konfigurációját az **Adószámítási paraméterek** lap **Általános** lapján található **Számítás** gyorslapon a **Forgalmi adó kerekítési szabály** szakaszában tekintheti meg (**Adó** \> **Beállítás** \> **Adókonfiguráció** \> **Adószámítási paraméterek**).

[![Kerekítési szabály konfigurálása az Adószámítási paraméterek oldalon](./media/tax-calculation-parameters-calculation-1.png)](./media/tax-calculation-parameters-calculation-1.png)

A **Kerekítési pontosság** és a **Kerekítési módszer** mezők határozzák meg, hogy az adószámítási szolgáltatásból származó hasznos teherben lévő számított összegek hogyan kerülnek kerekítésre.

## <a name="rounding-precision"></a>Kerekítési pontosság

A **Kerekítési pontosság** mezők hat tizedesjegyig terjedő értéket támogatnak. Ha például a **Kerekítési pontosság** **mezőt** üresre 0.000000, Microsoft Dynamics a számított összegeket a program hat tizedesjegyre kerekítve küldi el a 365 Pénzügynek. Például, ha a **Normál** kerekítési módszert használja, a **987,1234567-es** összeget **987,123457-re** kerekíti.

> [!NOTE]
> A pénzügyek az összegeket a pénznem kerekítési szabályai szerint kerekíti. Ezért a tranzakciókban feltüntetett és nyilvántartott adóösszegeket mind az adószámítási kerekítési szabályok, mind a devizakerekítési szabályok befolyásolják.

## <a name="rounding-method"></a>Kerekítési mód

Az adószámítás kerekítési módszere jogi személyenként konfigurálható. A **Kerekítési módszer** mezőben három lehetőség közül választhat: **Normál**, **Lefelé** és **Felfelé kerekítés**.

### <a name="rounding-example"></a>Kerekítési példa

A következő táblázatban egy példa mutatja, hogy a **987,345** összeg hogyan kerekíthető a kerekítési pontosság és a kerekítési módszerek különböző kombinációi esetén.

<table>
<thead>
<tr>
<th rowspan="2">Kerekítési mód</th>
<th colspan="8">Kerekítési pontosság</th>
</tr>
<tr>
<th>0,00</th>
<th>0.01</th>
<th>0.10</th>
<th>1.00</th>
<th>10,00</th>
<th>0.02</th>
<th>0.05</th>
<th>0.25</th>
</tr>
</thead>
<tbody>
<tr>
<td>Normál</td>
<td>987.35</td>
<td>987.35</td>
<td>987.30</td>
<td>987.00</td>
<td>990.00</td>
<td>987.34</td>
<td>987.35</td>
<td>987.25</td>
</tr>
<tr>
<td>Lefelé</td>
<td>987.00</td>
<td>987.34</td>
<td>987.30</td>
<td>987.00</td>
<td>980.00</td>
<td>987.34</td>
<td>987.30</td>
<td>987.25</td>
</tr>
<tr>
<td>Felkerekítés</td>
<td>988.00</td>
<td>987.35</td>
<td>987.40</td>
<td>988.00</td>
<td>990.00</td>
<td>987.36</td>
<td>987.35</td>
<td>987.50</td>
</tr>
</tbody>
</table>

Az adóösszegek számítási és kerekítési logikája az adózási szabályoknak megfelelően konfigurálható.

## <a name="rounding-by"></a>Kerekítés alapja 

A **Kerekítés szerint** mezőben válassza ki az adókra vonatkozó kerekítési elvet. Ehhez a következő lehetőségek állnak rendelkezésre:

- **Adókódok** - Kerekítse le az adó összegét az egyes adókódokon belül.
- **Adókód-kombinációk** - Kerekítse le az adó összegét a soron lévő adókód-kombináción belül.

## <a name="calculation-method"></a>Számítási mód

A **Számítási módszer** mezőben válassza ki, hogy a számlákon szereplő adókat soronként vagy az összes sorra számolja-e ki a rendszer. Ehhez a következő lehetőségek állnak rendelkezésre:

- **Sor** - Az adó összegének kiszámítása soronként. Az egyes sorok adóösszegét nem befolyásolja a többi sor adóösszege.
- **Összesen** - Az adó összegének kiszámítása egy dokumentum összes sorában.

### <a name="rounding-calculation-example"></a>Kerekítési számítási példa

Ez a példa az egy számlán elvégezhető különböző számításokat mutatja be a **Kerekítés szerinti** és a **Számítási módszer** értékek különböző kombinációi esetén. Ehhez a példához a következő beállítások vannak érvényben:

- A számla négy sorból áll.
- Két adókód létezik: **HÉA1** (10 százalék) és **HÉA2** (10 százalék).
- A kerekítési pontosság **0,01-re** van beállítva.
- A kerekítési módszer **kerekítésre** van állítva.

#### <a name="rounding-by--tax-codes-and-calculation-method--line"></a>Kerekítés = Adókódok és Számítási módszer = Sor

| Sor száma | Sor nettó összege | Meghatározott adókódok | Adóösszeg kerekítés előtt | Kerekített adóösszeg |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | VAT1                 | 1.111                      | 1.12               |
| 2           | 22.22           | VAT1; VAT2           | 2,222; 2,222               | 2,23; 2,23         |
| 3           | 33.33           | VAT1                 | 3.333                      | 3.34               |
| 4           | 44.44           | VAT1; VAT2           | 4,444; 4,444               | 4,45; 4,45         |

#### <a name="rounding-by--tax-code-combinations-and-calculation-method--line"></a>Kerekítés = Adókódkombinációk és Számítási módszer = Sor

| Sor száma | Sor nettó összege | Meghatározott adókódok | Adóösszeg kerekítés előtt | Kerekített adóösszeg |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | VAT1                 | 1.111                      | 1.12               |
| 2\*         | 22.22           | VAT1; VAT2           | 2,222; 2,222               | 2,23; 2,22         |
| 3           | 33.33           | VAT1                 | 3.333                      | 3.34               |
| 4\*\*       | 44.44           | VAT1; VAT2           | 4,444; 4,444               | 4,45; 4,44         |

\* 2. sor = Kerekítés\[22,22 × (10 százalék + 10 százalék)\] = 2,23 + 2,22

\*\* 4. sor = Kerekítés\[44,44 × (10 százalék + 10 százalék)\] = 4,45 + 4,44

#### <a name="rounding-by--tax-codes-and-calculation-method--total"></a>Kerekítés = Adókódok és számítási módszer = Összesen

| Sor száma | Sor nettó összege | Meghatározott adókódok | Adóösszeg kerekítés előtt | Kerekített adóösszeg |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1           | 11.11           | VAT1\*               | 1.111                      | 1.12               |
| 2           | 22.22           | VAT1\*; VAT2\*\*     | 2,222; 2,222               | 2,22; 2,23         |
| 3           | 33.33           | VAT1\*               | 3.333                      | 3.33               |
| 4           | 44.44           | VAT1\*; VAT2\*\*     | 4,444; 4,444               | 4,44; 4,44         |

\* VAT1(1. sor, 2. sor, 3. sor, 4. sor) = Kerekítés\[(11,11 + 22,22 + 33,33 + 44,44) × 10 százalék\] = 1,12 + 2,22 + 3,33 + 4,44

\*\* VAT2(2. sor, 4. sor) = Kerekítés\[(22,22 + 44,44) × 10 százalék\] = 2,23 + 4,44

#### <a name="rounding-by--tax-code-combinations-and-calculation-method--total"></a>Kerekítés = Adókódkombinációk és számítási módszer = Összesen

| Sor száma | Sor nettó összege | Meghatározott adókódok | Adóösszeg kerekítés előtt | Kerekített adóösszeg |
|-------------|-----------------|----------------------|----------------------------|--------------------|
| 1\*         | 11.11           | VAT1                 | 1.111                      | 1.12               |
| 2\*\*       | 22.22           | VAT1; VAT2           | 2,222; 2,222               | 2,23; 2,22         |
| 3\*         | 33.33           | VAT1                 | 3.333                      | 3.33               |
| 4\*\*       | 44.44           | VAT1; VAT2           | 4,444; 4,444               | 4,44; 4,45         |

\* 1. sor, 3. sor = Kerekítés\[(11,11 + 33,33) × 10 százalék\] = 1,12 + 3,33

\*\* 2. sor, 4. sor = Kerekítés\[(22,22 + 44,44) × (10 százalék + 10 százalék)\] = 2,23 + 2,22 + 4,44 + 4,45

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
