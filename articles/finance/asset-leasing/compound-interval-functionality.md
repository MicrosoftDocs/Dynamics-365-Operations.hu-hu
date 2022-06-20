---
title: Összetételi intervallum funkció
description: Ez a cikk segít választani a havi, negyedéves, féléves és éves összetételi időszakok közül.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseDetail
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2de5f1e9d52de41388298031a03fbc487a1b1cde
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886414"
---
# <a name="compounding-interval-functionality"></a>Összetételi intervallum funkció

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a cikk segít választani a havi, negyedéves, féléves és éves összetételi időszakok közül. Az összetételi intervallum funkció az éves lízingfizetési ütemezésben az összetett időszakok számának meghatározására szolgál. A cikk négy példa közül mindegyik azt mutatja be, hogy hogyan fog kinézni a bérlet fizetési ütemezése egy másik időszakra.

Nem választhat olyan összetételi intervallumot, amely ritkábban történik, mint a lízingfizetés gyakorisága. Például egy negyedéves összetételi intervallum nem használható havi fizetési gyakorisággal, és az éves összetételi intervallum nem használható féléves fizetési gyakorisággal. Ha megpróbál olyan összetételi intervallumot választani, amely ritkábban történik, mint a lízingfizetés gyakorisága, akkor hibaüzenetet fog kapni.

> [!NOTE]
> Ebben a példában mind a négy példában az összetételi intervallum megegyezik a fizetési gyakorisággal.

## <a name="examples"></a>Példák

### <a name="setup-for-all-four-leases"></a>Beállítás mind a négy lízinghez

Az alábbi táblázatok a példákban használt négy lízing **Általános** és **Fizetési ütemezési sorai** fülön beállított értékeket mutatják be.

**Általános fül**

| Mező                      | Érték                        |
|----------------------------|------------------------------|
| Járulékos kamatláb | **5%**                       |
| Annuitás típusa               | **Szokásos annuitás**         |
| Összetételi intervallum       | Tekintse meg az egyes példákat. |
| Fizetés gyakorisága          | **Havi**                  |
| Kezdési dátum          | **2020.01.01.**                 |

**Kifizetési lista sorai fül**

| Mező             | Érték                        |
|-------------------|------------------------------|
| Kezdés dátuma        | **2020.01.01.**                 |
| Időszakok           | **120**                      |
| Időszak intervalluma   | **Hónap**                   |
| Befejezés          | **2029.12.31.**               |
| Fizetés gyakorisága | Tekintse meg az egyes példákat. |
| Fizetés összege    | **50,000**                   |

### <a name="lease-1-monthly-compounding-interval-and-monthly-payment-frequency"></a>1. lízing: Havi összetételi intervallum és havi fizetési gyakoriság

Az alábbi tábla a fizetési ütemezés első 12 hónapját sorolja fel. Vegye figyelembe a következőket:

- Az „Időszak” oszlop értéke havonta 1-gyel nő, mert minden hónap egy új összetételi intervallum.
- A „Jelenlegi érték” oszlopban szereplő képletben a sebesség 12-vel van elosztva, mivel évente 12 összetételi időszak van. A kitevő (azaz a felső index száma) megegyezik az „Időszak” oszlop értékével.

| Időszak | Hónap | Dátum       | Fizetés összege | Jelenlegi érték                                       |
|--------|-------|------------|----------------|-----------------------------------------------------|
| 1      | 1     | 2020.01.31  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>1</sup> = 49.792,53  |
| 2      | 2     | 2020.02.29.  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>2</sup> = 49.585,92  |
| 3      | 3     | 2020.03.31.  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>3</sup> = 49.380,17  |
| 4      | 4     | 2020.04.30.  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>4</sup> = 49.175,28  |
| 5      | 5     | 2020.05.31.  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>5</sup> = 48.971,23  |
| 6      | 6     | 2020.06.30.  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>6</sup> = 48.768,03  |
| 7      | 7     | 2020.07.31.  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>7</sup> = 48.565,67  |
| 8      | 8     | 2020.08.31.  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>8</sup> = 48.364,15  |
| 9      | 9     | 2020.09.30.  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>9</sup> = 48.163,47  |
| 10     | 10    | 2020.10.31. | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>10</sup> = 47.963,62 |
| 11     | 11    | 2020.11.30. | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>11</sup> = 47.764,61 |
| 12     | 12    | 2020.12.31. | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 12\])<sup>12</sup> = 47.566,41 |

### <a name="lease-2-quarterly-compounding-interval-and-quarterly-payment-frequency"></a>2. lízing: Negyedéves összetételi intervallum és negyedéves fizetési gyakoriság

Az alábbi tábla a fizetési ütemezés első 12 hónapját sorolja fel. Vegye figyelembe a következőket:

- Az „Időszak” oszlop értéke három havonta 1-gyel nő, mert minden három hónap (azaz minden negyedévben) egy új összetételi intervallum.
- A „Jelenlegi érték” oszlopban szereplő képletben a sebesség 4-gyel van elosztva, mivel évente négy összetételi időszak van. A kitevő megegyezik az „Időszak” oszlopban szereplő értékkel.

| Időszak | Hónap | Dátum       | Fizetés összege | Jelenlegi érték                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 2020.01.31  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>1</sup> = 0           |
| 1      | 2     | 2020.02.29.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>1</sup> = 0           |
| 1      | 3     | 2020.03.31.  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 4\])<sup>1</sup> = 49.382,72 |
| 2      | 4     | 2020.04.30.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>2</sup> = 0           |
| 2      | 5     | 2020.05.31.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>2</sup> = 0           |
| 2      | 6     | 2020.06.30.  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 4\])<sup>2</sup> = 48.773,05 |
| 3      | 7     | 2020.07.31.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>3</sup> = 0           |
| 3      | 8     | 2020.08.31.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>3</sup> = 0           |
| 3      | 9     | 2020.09.30.  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 4\])<sup>3</sup> = 48.170,92 |
| 4      | 10    | 2020.10.31. | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>4</sup> = 0           |
| 4      | 11    | 2020.11.30. | 0,00           | 0,00 ÷ (1 + \[5% ÷ 4\])<sup>4</sup> = 0           |
| 4      | 12    | 2020.12.31. | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 4\])<sup>4</sup> = 47.576,21 |

> [!NOTE]
> Ha az annuitás típusa **Annuitás esedékes** értékre változik, akkor a kifizetés a negyedév vége helyett a negyedév elején lesz.

### <a name="lease-3-semiannual-compounding-interval-and-semiannual-payment-frequency"></a>3. lízing: Féléves összetételi intervallum és féléves fizetési gyakoriság

Az alábbi tábla a fizetési ütemezés első 12 hónapját sorolja fel. Vegye figyelembe a következőket:

- Az „Időszak” oszlop értéke hat havonta 1-gyel nő, mert minden félév (azaz minden félévben) egy új összetételi intervallum.
- A „Jelenlegi érték” oszlopban szereplő képletben a sebesség 2-vel van elosztva, mivel évente két összetételi időszak van. A kitevő megegyezik az „Időszak” oszlopban szereplő értékkel.

| Időszak | Hónap | Dátum       | Fizetés összege | Jelenlegi érték                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 2020.01.31  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 2     | 2020.02.29.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 3     | 2020.03.31.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 4     | 2020.04.30.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 5     | 2020.05.31.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 0           |
| 1      | 6     | 2020.06.30.  | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 2\])<sup>1</sup> = 48.780,49 |
| 2      | 7     | 2020.07.31.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 8     | 2020.08.31.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 9     | 2020.09.30.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 10    | 2020.10.31. | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 11    | 2020.11.30. | 0,00           | 0,00 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 0           |
| 2      | 12    | 2020.12.31. | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 2\])<sup>2</sup> = 47.590,72 |

> [!NOTE]
> Ha az annuitás típusa **Annuitás esedékes** értékre változik, a kifizetés június és december helyett januárban és júliusban lesz.

### <a name="lease-4-annual-compounding-interval-and-annual-payment-frequency"></a>4. lízing: Éves összetételi intervallum és éves fizetési gyakoriság

Az alábbi tábla a fizetési ütemezés első 12 hónapját sorolja fel. Vegye figyelembe a következőket:

- Az „Időszak” oszlop értéke 12 havonta 1-gyel nő, mert minden év (azaz évente) egy új összetételi intervallum.
- A „Jelenlegi érték” oszlopban szereplő képletben a sebesség 1-vel van elosztva, mivel évente egy összetételi időszak van. A kitevő megegyezik az „Időszak” oszlopban szereplő értékkel.

| Időszak | Hónap | Dátum       | Fizetés összege | Jelenlegi érték                                     |
|--------|-------|------------|----------------|---------------------------------------------------|
| 1      | 1     | 2020.01.31  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 2     | 2020.02.29.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 3     | 2020.03.31.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 4     | 2020.04.30.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 5     | 2020.05.31.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 6     | 2020.06.30.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 7     | 2020.07.31.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 8     | 2020.08.31.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 9     | 2020.09.30.  | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 10    | 2020.10.31. | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 11    | 2020.11.30. | 0,00           | 0,00 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 0           |
| 1      | 12    | 2020.12.31. | 50,000.00      | 50.000 ÷ (1 + \[5% ÷ 1\])<sup>1</sup> = 47.619,05 |

> [!NOTE]
> Ha az annuitás típusa **Annuitás esedékes** értékre változik, a kifizetés december helyett januárban lesz.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
