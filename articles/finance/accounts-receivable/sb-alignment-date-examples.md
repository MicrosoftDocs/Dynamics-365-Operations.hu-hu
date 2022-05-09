---
title: Dátum esetek igazítása
description: Ez a témakör példákkal mutatja be, hogyan működnek az igazítási dátumok az előfizetéses számlázásban.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: e80797e8dd532bb4b2ef78422b459487430d83d6
ms.sourcegitcommit: 836695c0e95d366ba993f34eee30f57191f356d8
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/21/2022
ms.locfileid: "8629702"
---
# <a name="alignment-date-scenarios"></a>Dátum esetek igazítása

Ez a témakör példákkal mutatja be, hogyan működnek az igazítási dátumok az előfizetéses számlázásban.

Ilyen példában a számlázási ütemezés számlázási részleteinek 2019. október 31. a dátuma. A sor első számlázási adata 2019. október 31-én ér véget, és annak megfelelően sorra módosul. A sor automatikusan meg újul a november 11-ei megújítás kezdő dátumával.

> [!NOTE]
> Az év azért fontos, mert az igazítás dátuma egy évnél több vagy kevesebb lehet. Ilyen példák esetében **az** **ismétlődő szerződés számlázási paraméterei oldalon a Havi módszer van beállítva.** Ha a napi érték van **beállítva**, akkor bizonyos részösszegek eltérőek.

## <a name="scenario-1-no-alignment"></a>1. eset: Nincs igazítás

A számlázási ütemezés a következő adatokkal van beállítva:

- **Kezdő dátum:** 2019. május 1.
- **Záró dátum:** 2024. december 31.
- **Összeg:** $1,000

| Számlázás kezdő dátuma | Számlázás záró dátuma | Előző olvasás | Aktuális leolvasás | Megadott mennyiség | Szabad mennyiség | Számlázható mennyiség | Egységár |
|---|---|---|---|---|---|---|---|
| 2019/1/5 | 2020.04.30. | | | 1,00 | | 1,00 | 1,000.00 |
| 2020/1/5 | 2021/30/4 | | | 1,00 | | 1,00 | 1,000.00 |
| 2021/1/5 | 2022/30/4 | | | 1,00 | | 1,00 | 1,000.00 |
| 2022/1/5 | 2023/30/4 | | | 1,00 | | 1,00 | 1,000.00 |
| 2023/1/5 | 2024/30/4 | | | 1,00 | | 1,00 | 1,000.00 |
| 2024/1/5 | 2024/31/12 | | | 1,00 | | 1,00 | 666.67 |

## <a name="scenario-2-shortened-alignment"></a>2. eset: Rövid igazítás

A számlázási ütemezés a következő adatokkal van beállítva:

- **Kezdő dátum:** 2019. május 1.
- **Záró dátum:** 2024. december 31.
- **Összeg:** $1,000
- **Igazítás dátuma:** 2019. december 31.

Az első megújítási összeg kevesebb, mint egy év.

| Számlázás kezdő dátuma | Számlázás záró dátuma | Előző olvasás | Aktuális leolvasás | Megadott mennyiség | Szabad mennyiség | Számlázható mennyiség | Egységár |
|---|---|---|---|---|---|---|---|
| 2019/1/5 | 2019/31/12 | | | 1,00 | | 1,00 | 666.67 |
| 2020.01.01. | 2020.12.31. | | | 1,00 | | 1,00 | 1,000.00 |
| 2021/1/1 | 2021/31/12 | | | 1,00 | | 1,00 | 1,000.00 |
| 2022.01.01. | 2022/31/12 | | | 1,00 | | 1,00 | 1,000.00 |
| 2023/1/1 | 2023/31/12 | | | 1,00 | | 1,00 | 1,000.00 |
| 2024/1/1 | 2024/31/12 | | | 1,00 | | 1,00 | 1,000.00 |

## <a name="scenario-3-extended-alignment"></a>3. eset: Kiterjesztett igazítás

A számlázási ütemezés a következő adatokkal van beállítva:

- **Kezdő dátum:** 2019. május 1.
- **Záró dátum:** 2024. december 31.
- **Összeg:** $1,000
- **Igazítás dátuma:** 2020. december 31.

Az első megújítási összeg egy évnél hosszabb.

| Számlázás kezdő dátuma | Számlázás záró dátuma | Előző olvasás | Aktuális leolvasás | Megadott mennyiség | Szabad mennyiség | Számlázható mennyiség | Egységár |
|---|---|---|---|---|---|---|---|
| 2019/1/5 | 2020.12.31. | | | 1,00 | | 1,00 | 1,666.67 |
| 2021/1/1 | 2021/31/12 | | | 1,00 | | 1,00 | 1,000.00 |
| 2022.01.01. | 2022/31/12 | | | 1,00 | | 1,00 | 1,000.00 |
| 2023/1/1 | 2023/31/12 | | | 1,00 | | 1,00 | 1,000.00 |
| 2024/1/1 | 2024/31/12 | | | 1,00 | | 1,00 | 1,000.00 |

## <a name="scenario-4-alignment-with-a-different-end-month"></a>4. eset: Igazítás másik záró hónaphoz

A számlázási ütemezés a következő adatokkal van beállítva:

- **Kezdő dátum:** 2019. május 1.
- **Záró dátum:** 2024. október 31.
- **Összeg:** $1,000
- **Igazítás dátuma:** 2019. december 31.

> [!NOTE]
> Ez az eset nem gyakori.

| Számlázás kezdő dátuma | Számlázás záró dátuma | Előző olvasás | Aktuális leolvasás | Megadott mennyiség | Szabad mennyiség | Számlázható mennyiség | Egységár |
|---|---|---|---|---|---|---|---|
| 2019/1/5 | 2019/31/12 | | | 1,00 | | 1,00 | 666.67 |
| 2020.01.01. | 2020.12.31. | | | 1,00 | | 1,00 | 1,000.00 |
| 2021/1/1 | 2021/31/12 | | | 1,00 | | 1,00 | 1,000.00 |
| 2022.01.01. | 2022/31/12 | | | 1,00 | | 1,00 | 1,000.00 |
| 2023/1/1 | 2023/31/12 | | | 1,00 | | 1,00 | 1,000.00 |
| 2024/1/1 | 2024/31/10 | | | 1,00 | | 1,00 | 833.33 |

## <a name="scenario-5-single-partial-year"></a>5. eset: Egy részév

A számlázási ütemezés a következő adatokkal van beállítva:

- **Kezdő dátum:** 2019. május 1.
- **Záró dátum:** 2019. december 31.
- **Összeg:** $1,000
- **Igazítás dátuma**: 2019. december 31.

Ebben az esetben nem szükséges az igazítás dátuma. Ez a helyzet az automatikus megújítások esetében gyakori.

| Számlázás kezdő dátuma | Számlázás záró dátuma | Előző olvasás | Aktuális leolvasás | Megadott mennyiség | Szabad mennyiség | Számlázható mennyiség | Egységár |
|---|---|---|---|---|---|---|---|
| 2019/1/5 | 2019/31/12 | | | 1,00 | | 1,00 | 666.67 |

## <a name="scenario-6-calculated-dates"></a>6. eset: Számított dátumok

A támogatás és a megújítás a következő adatokkal van beállítva:

- **Felülbírálás kezdő dátuma:** Nem
- **Támogatás és megújítás kezdő dátumai:** A következő hónap elején
- **Számlafeladási dátum:** 2019. június 22.
- **Igazítás dátuma:** 2020. december 31.

| Számlázás kezdő dátuma | Számlázás záró dátuma | Előző olvasás | Aktuális leolvasás | Megadott mennyiség | Szabad mennyiség | Számlázható mennyiség | Egységár |
|---|---|---|---|---|---|---|---|
| 2019/1/7 | 2019/31/7 | | | 1,00 | | 1,00 | 297.60 |
| 2019/1/8 | 2020.12.31. | | | 1,00 | | 1,00 | 6,936.00 |

## <a name="scenario-7-calculated-dates-and-future-posting"></a>7. eset: számított dátumok és jövőbeli feladás

A támogatás és a megújítás a következő adatokkal van beállítva:

- **Felülbírálás kezdő dátuma:** Nem
- **Támogatás és megújítás kezdő dátumai:** A következő hónap elején
- **Számlafeladási dátum:** 2019. június 22.
- **Igazítás dátuma:** 2020. december 31.

Erre az esetre az igazítás dátuma 2021. december 31-re módosul.

| Számlázás kezdő dátuma | Számlázás záró dátuma | Előző olvasás | Aktuális leolvasás | Megadott mennyiség | Szabad mennyiség | Számlázható mennyiség | Egységár |
|---|---|---|---|---|---|---|---|
| 2019/22/6 | 2019/22/6 | | | 1,00 | | 1,00 | 0,00 |
| 2019/1/8 | 2020.12.31. | | | 1,00 | | 1,00 | 4,250.00 |

## <a name="scenario-8-manual-dates-and-multiple-years"></a>8. eset: Manuális dátumok és több év

A támogatás és a megújítás a következő adatokkal van beállítva:

- **Kezdő dátum felülbírálata:** Igen
- **Megújítás kezdő dátuma:** 2020. július 1.
- **Megújítás záró dátuma:** 2024. december 31.
- **Igazítás dátuma:** 2021. december 31.

| Számlázás kezdő dátuma | Számlázás záró dátuma | Előző olvasás | Aktuális leolvasás | Megadott mennyiség | Szabad mennyiség | Számlázható mennyiség | Egységár |
|---|---|---|---|---|---|---|---|
| 2019/22/6 | 2019/22/6 | | | 1,00 | | 1,00 | 0,00 |
| 2020/1/7 | 2021/31/12 | | | 1,00 | | 1,00 | 375.00 |
| 2022.01.01. | 2022/31/12 | | | 1,00 | | 1,00 | 250.00 |
| 2023/1/1 | 2023/31/12 | | | 1,00 | | 1,00 | 250.00 |
| 2024/1/1 | 2024/31/12 | | | 1,00 | | 1,00 | 250.00 |

## <a name="scenario-9-manual-dates-multiple-years-and-a-different-end-month"></a>9. eset: manuális dátumok, több év és egy másik záró hónap

A támogatás és a megújítás a következő adatokkal van beállítva:

- **Kezdő dátum felülbírálata:** Igen
- **Megújítás kezdő dátuma:** 2020. július 1.
- **Megújítás záró dátuma:** 2024. október 31.
- **Igazítás dátuma:** 2021. december 31.

| Számlázás kezdő dátuma | Számlázás záró dátuma | Előző olvasás | Aktuális leolvasás | Megadott mennyiség | Szabad mennyiség | Számlázható mennyiség | Egységár |
|---|---|---|---|---|---|---|---|
| 2019/22/6 | 2019/22/6 | | | 1,00 | | 1,00 | 0,00 |
| 2020/1/7 | 2021/31/12 | | | 1,00 | | 1,00 | 375.00 |
| 2022.01.01. | 2022/31/12 | | | 1,00 | | 1,00 | 250.00 |
| 2023/1/1 | 2023/31/12 | | | 1,00 | | 1,00 | 250.00 |
| 2024/1/1 | 2024/31/10 | | | 1,00 | | 1,00 | 208.33 |

## <a name="scenario-10-alignment-without-proration"></a>10. eset: Igazítás ás nélkül

A támogatás és a megújítás a következő adatokkal van beállítva:

- **Felülbírálás kezdő dátuma:** Nem
- **Számlafeladási dátum:** 2019. június 22.
- **Igazítás dátuma:** 2019. december 31.

A megújítás kezdő dátuma és az igazítás dátuma úgy módosul, hogy mindkét kezdő dátum a feladási dátum utánra ássa.

- **Megújítás kezdő dátuma:** 2020. január 1.
- **Megújítás záró dátuma:** 2020. december 31.
