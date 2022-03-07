---
title: Átlagos és napi árfolyam kiszámítása
description: Ez a témakör azt mutatja be, hogyan lehet kiszámítani a kimenő banki és a készpénzfizetési tranzakciók átlagos árfolyamát.
author: anasyash
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetParameters
audience: Application User
ms.reviewer: kfend
ms.custom: 264684
ms.search.region: Hungary
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 45c919d38b4d3a839606022da0d63cccd2f3313b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815021"
---
# <a name="calculate-average-and-daily-exchange-rates"></a>Átlagos és napi árfolyam kiszámítása

[!include [banner](../includes/banner.md)]

A „számvitelről szóló 2000. évi C. törvény” szerinti külföldi pénznemek szerinti számviteli követelménynek megfelelően a külföldi pénznemben lévő értékpapír-készlet költsége a következőkből áll:

  - a pénznemben kifejezett érték, amelyet a rendszer a külföldi pénznem árfolyamának felhasználásával számít fel, amikor a készleteket beszerezik.
  - az átlagos árfolyam vagy az első által meghatározott árfolyam alapján számított működési pénznem értékét az először bevételezve, először kiadva a (FIFO) módszer határozza meg.

Az országos kontextusú magyar jogi személyeknél a kimenő pénzforgalmi és banki tranzakciók átlagos árfolyamának kiszámítására szolgáló funkció érhető el. A kimenő pénzforgalmi és banki tranzakciókkal rendelkező naplósorokban az átlagos átváltási árfolyam kiszámításának algoritmusához a könyvelési pénznem és a külföldi pénznem összesített összegei használatosak a tranzakció megadott időpontja előtt.

Ez a témakör azt mutatja be, hogyan használható a kiszámítás funkció a kimenő banki és a készpénzfizetési tranzakciók átlagos árfolyamához. Azt is bemutatja, hogyan használható a kiszámítás funkció a napi bejövő és kimenő banki és a pénzforgalmi tranzakciók átlagos árfolyamához.

## <a name="daily-exchange-rate"></a>Napi árfolyam

Használja a napi árfolyam kiszámításához szükséges funkciót, ha a banki vagy a pénzforgalmi tranzakciókat tartalmazó főkönyvi naplókat már a napi árfolyamok megadása előtt létrehozta. A naplósorok az előző napon érvényes árfolyammal rendelkeznek. Ezért ezeket újra ki kell számítani az aktuális dátumhoz tartozó új árfolyam megadása után.

Ez a példa végigvezeti a napi árfolyamszámítási funkción a DEMF jogi személyben.

Mielőtt elkezdené, ugorjon az **Adó** \> **Közvetett adók** \> **Áfa** \> **Áfa kiegyenlítési periódusk** lehetőségre. Az **Időszakos időszakok** lapon 2020. március 31-ét követően hozhat létre intervallumokat.

1. Lépjen a **Főkönyv** \> **Pénznemek** \> **Árfolyamok** lehetőségre, majd válassza az **USD-ről EUR-ra** sort.
2. Válassza a **Hozzáadás** lehetőséget, majd állítsa be a mezőket a következő értékekre:

- **Kezdő dátum:** 2020/2/29
- **Árfolyam:** 92

3. Válassza a **Mentés** lehetőséget.
4. Válassza a **Főkönyv** \> **Naplóbejegyzések** \> **Általános naplók** lehetőséget, majd válassza az **Új** opciót.
5. A **Név** mezőben válassza a **GenJrn-t**.
6. Válassza a **Sorok** lehetőséget, majd hozza létre a következő sorokat.

| **Dátum**      | **Számla típusa** | **Számla** | **Tartozik** | **Követel** | **Ellenszámla típusa** | **Ellenszámla** | **Pénznem** | **Árfolyam** |
|---------------|------------------|-------------|-----------|------------|-------------------------|--------------------|--------------|-------------------|
| 2020. március 1. | Vevő         | DE - 010      |           | 100        | Bank                    | DEMF USD           | USD          | 92                |
| 2020. március 1. | Vevő         | DE - 011      |           | 200        | Bank                    | DEMF USD           | USD          | 92                |
| 2020. március 1. | Szállító           | DE - 001      | 150       |            | Bank                    | DEMF USD           | USD          | 92                |
| 2020. március 1. | Szállító           | DE - 01001    | 250       |            | Bank                    | DEMF USD           | USD          | 92                |

7. Válassza a **Mentés** lehetőséget, és ellenőrizze, hogy a sorokban a devizaárfolyam értéke **92**.
8. Lépjen a **Főkönyv \> Pénznemek \> Árfolyamok** lehetőségre, majd válassza az **USD-ről EUR-ra** sort.
9. Válassza a **Hozzáadás** lehetőséget, majd állítsa be a mezőket a következő értékekre:

- **Kezdő dátum:** 2020/3/1
- **Árfolyam:** 91

10. Válassza a **Mentés** lehetőséget.
11. Ugorjon a **Főkönyv** \> **Naplóbejegyzések** \> **Általános naplók** menüpontra.
12. Válassza ki a korábban létrehozott naplót, majd válassza a **Sorok** lehetőséget.
13. Válassza ki a **Funkciók** \> **Arfolyamszámítás** lehetőséget.
14.  Az **Árfolyamszámítás** párbeszédpanelen adja meg a mezőket a következő értékekhez:

- **Kezdő dátum:** 1/3/2020
- **Számítási módszer:** Napi árfolyam

15. Kattintson az **OK** gombra, és tekintse át a következő adatokat.

| **Dátum**      | **Számla típusa** | **Számla** | **Tartozik** | **Követel** | **Ellenszámla típusa** | **Ellenszámla** | **Pénznem** | **Árfolyam** |
|---------------|------------------|-------------|-----------|------------|-------------------------|--------------------|--------------|-------------------|
| 2020. március 1. | Vevő         | DE - 010      |           | 100        | Bank                    | DEMF USD           | USD          | 91                |
| 2020. március 1. | Vevő         | DE - 011      |           | 200        | Bank                    | DEMF USD           | USD          | 91                |
| 2020. március 1. | Szállító           | DE - 001      | 150       |            | Bank                    | DEMF USD           | USD          | 91                |
| 2020. március 1. | Szállító           | DE - 01001    | 250       |            | Bank                    | DEMF USD           | USD          | 91                |

Figyelje meg, hogy az **Árfolyam** oszlop minden sora a **91-es** értékre van beállítva.

## <a name="average-exchange-rate"></a>Átlagárfolyam

Ez a példa végigvezeti az átlagos árfolyamszámítási funkción egy bankszámlához. A program kiszámítja a kimenő banki és a készpénzfizetési tranzakciók átlagos árfolyamát. 

1. Lépjen a **Főkönyv** \> **Pénznemek** \> **Árfolyamok** lehetőségre, majd válassza az **USD-ről EUR-ra** sort.
2. Válassza a **Hozzáadás** lehetőséget, majd hozza létre a következő sorokat.

| **Kezdés dátuma** | **Árfolyam** |
|----------------|-------------------|
| 2020. március 1.  | 91                |
| 2020. március 2.  | 92                |
| 2020. március 3.  | 93                |

3. Válassza a **Főkönyv \> Naplóbejegyzések \> Általános naplók** lehetőséget, majd válassza az **Új** opciót.
4. A **Név** mezőben válassza a **GenJrn-t**.
5. Válassza a **Sorok** lehetőséget, és hozza létre a bejövő banki tranzakciókat tartalmazó következő sorokat.

| **Dátum**      | **Számla típusa** | **Számla** | **Tartozik** | **Követel** | **Ellenszámla típusa** | **Ellenszámla** | **Pénznem** | **Árfolyam** |
|---------------|------------------|-------------|-----------|------------|-------------------------|--------------------|--------------|-------------------|
| 2020. március 1. | Bank             | DEMF USD    | 100       |            | Vevő                | DE - 010             | USD          | 91.0000           |
| 2020. március 2. | Bank             | DEMF USD    | 200       |            | Vevő                | DE - 011             | USD          | 92.0000           |

6. Válassza a **Feladás** parancsot.
7. Válassza a **Főkönyv** \> **Naplóbejegyzések** \> **Általános naplók** lehetőséget, majd válassza az **Új** opciót.
8. A **Név** mezőben válassza a **GenJrn-t**.
9. Válassza a **Sorok** lehetőséget, és hozza létre a bejövő és kimenő banki tranzakciókat tartalmazó következő sorokat.

| **Dátum**      | **Számla típusa** | **Számla** | **Tartozik** | **Követel** | **Ellenszámla típusa** | **Ellenszámla** | **Pénznem** | **Árfolyam** |
|---------------|------------------|-------------|-----------|------------|-------------------------|--------------------|--------------|-------------------|
| 2020. március 3. | Bank             | DEMF USD    | 100       |            | Vevő                | DE - 012             | USD          | 93.0000           |
| 2020. március 3. | Bank             | DEMF USD    |           | 150        | Szállító                  | DE - 001             | USD          | 93.0000           |
| 2020. március 3. | Bank             | DEMF USD    |           | 250        | Szállító                  | DE - 01001           | USD          | 93.0000           |

10. Ellenőrizze, hogy a sorokba automatikusan bevitt devizaárfolyam értéke **93**.
11. Válassza ki a **Funkciók** \> **Arfolyamszámítás** lehetőséget.
12. Az **Árfolyamszámítás** párbeszédpanelen adja meg a mezőket a következő értékekhez:

- **Kezdő dátum:** 1/3/2020
- **Számítási módszer:** Átlagos árfolyam

13. Kattintson az **OK** gombra, és ellenőrizze, hogy a kimenő banki tranzakciók devizaárfolyam-értéke **92-re** módosult-e.

| **Dátum**      | **Számla típusa** | **Számla** | **Tartozik** | **Követel** | **Ellenszámla típusa** | **Ellenszámla** | **Pénznem** | **Árfolyam** |
|---------------|------------------|-------------|-----------|------------|-------------------------|--------------------|--------------|-------------------|
| 2020. március 3. | Bank             | DEMF USD    | 100       |            | Vevő                | DE - 012             | USD          | 93.0000           |
| 2020. március 3. | Bank             | DEMF USD    |           | 150        | Szállító                  | DE - 001             | USD          | 92.0000           |
| 2020. március 3. | Bank             | DEMF USD    |           | 250        | Szállító                  | DE - 01001           | USD          | 92.0000           |

A második sor **92,0000** értékének kiszámítása (100 * 0,91 + 200 * 0,92 + 100 * 0,93)/(100 + 200 + 100). A számítási képlet a következő három korábbi bejövő tranzakciót veszi figyelembe a 100, 200 és 100 esetében.

A harmadik sorhoz tartozó **92,0000** érték számítása (100 * 0,91 + 200 * 0,92 + 100 * 0,93-150 * 0,92)/(100 + 200 + 100-150). Három korábbi bejövő tranzakciót és egy korábbi kimenő tranzakciót vettek figyelembe a képletben.

Az átlagos árfolyam-számítási mód elérhető a kimenő banki tranzakcióhoz. Figyelembe veszi a feladott banki tranzakciókat (az aktuális főkönyvi naplóban feladott és fel nem adott banki tranzakciókat is, amelyek a figyelembe vett banki tranzakció előtt jöttek létre) azon időszakra vonatkozóan, amely a párbeszédpanelen megadott „kezdő dátum” beállításnál kezdődik, és a kimenő banki tranzakció dátumára végződik. Ez a módszer ezeknek a tranzakcióknak az átlagos átváltási árfolyamát úgy számítja ki, hogy az összes korábbi tranzakció teljes összegét a könyvelési pénznemben minden korábbi tranzakció teljes összegével elosztja. A program ezután a létrejövő árfolyamot hozzárendeli a kimenő tranzakcióhoz. Az átlagos átváltási árfolyam kiszámítása olyan dimenzióértékek alapján történik, amelyek aktívak abban a számlastruktúrában, amelyhez a készpénzes vagy banki főkönyvi számla tartozik.

A Napi árfolyamok és az Átlagos árfolyam-módszerek a bizonylatnaplóban (**Készpénz-és banki kezelés** \> **Készpénz-tranzakciók** \> **Bizonylatnaplók**) megadott pénztári tranzakciókra is használhatók. A banki tranzakcióknál használt algoritmus az átlagos arány kiszámítására is szolgál.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]