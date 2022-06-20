---
title: Áfaszámítás és -kerekítés
description: Ez a cikk áttekintést nyújt az áfaszámításról és a kerekítésről, és bemutatja az áfaszámítás és a kerekítés beállításának paramétereit.
author: wangchen
ms.date: 06/01/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom:
- "13111"
- intro-internal
ms.assetid: fe5fdc7f-9834-49fb-a611-1dd9c289619d
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2022-05-31
ms.dyn365.ops.version: AX 10.0.28
ms.openlocfilehash: aa3564f0fcf4a958637ba4a5cdcc497bffc50000
ms.sourcegitcommit: 8b716849707ec96d1cb4cac85b9e782dc25f5a70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/07/2022
ms.locfileid: "8939233"
---
# <a name="sales-tax-calculation-and-rounding"></a>Áfaszámítás és -kerekítés

[!include [banner](../includes/banner.md)]

Ez a cikk áttekintést nyújt a Microsoft Dynamics Pénzügy 365-ös áfaszámításról és -kerekítésről. Ismerteti az áfaszámítás és -kerekítés beállításában használt paramétereket, valamint a paraméterek együttes működési beállításait is.

## <a name="parameters"></a>Paraméterek

Számos paraméter az áfaszámítást és a kerekítést szabályozhatja:

- **Számítási mód** – ez a paraméter **a** Főkönyvi paraméterek lapon van beállítva, és meghatározza, hogy az adóalap összegét dokumentumonként vagy sorban kell-e számítani. **Ha az áfakód** **számításának** alapparamétere a számlaegyenleg nettó összege, az adóalapösszeg számítása mindig dokumentumonként történik, a paraméter beállításától függetlenül.
- **Kerekítés – ez** a paraméter az áfacsoportra van beállítva, és meghatározza, hogy az áfaösszeg áfakódonként vagy áfakód-kombinációnként legyen kerekített.
- **Eredet** – ez a paraméter az áfakódra vonatkozóan van beállítva, és meghatározza az áfaösszeg kiszámításának módját. A további tudnivalókat lásd [az Eredet mező Áfaszámítási módjai mezőben](sales-tax-calculation-methods-origin-field.md).
- **Számítás alapja** – ez a paraméter **az áfakódra van beállítva, és meghatározza, hogy milyen összeg szükséges a megfelelő áfakulcsok kiválasztásához az Áfakódértékek** lapon. További tájékoztatás: [Az áfaérték a Számítás alapja és a Számítási módszerek alapján](marginal-base-field.md).
- **Áfakerekítési** szabály – ez a paraméter az áfakódra vonatkozik, és meghatározza a meghatározott áfaösszeg kerekítésének módját, a kerekítési pontosságot és a kerekítési módszert is beleértve.

A cikk többi része néhány jellemző példát mutat be az áfaszámításra és a kerekítésre vonatkozóan, amelyek az előző paraméterek kombinációját használják.

## <a name="scenario-for-the-examples"></a>Példa esete

- Az adóköteles bizonylaton két sor található, és az egyes sorok adóalapösszege 42,42.
- Minden sorhoz két áfakód van meghatározva: az 1- és a 2-es áfakódhoz.
- Az 1- és a 2-es adókód adókulcsa 10 százalék.
- Az ár nem tartalmazza az adót.
- A kerekítési pontosság 0,01.
- A kerekítési mód a **Felkerekítés**.

## <a name="example-1"></a>1. példa

### <a name="parameter-values"></a>Paraméterértékek

| Számítási mód | Kerekítés alapja    | Származás                   | Számítás alapja       |
| ------------------ | -------------- | ------------------------ | ------------------- |
| Sor               | Áfakód | A nettó összeg százaléka | Soronkénti nettó összeg |

### <a name="calculation-and-rounding-behavior"></a>Számítás és kerekítés viselkedése

| Sor száma | Áfakód | Eredeti összeg | Áfa összege |
| ------------| ---------------| --------------| -----------------|
| 1           | 1. kód         | 42.42         | 4.25             |
| 1           | 2. kód         | 42.42         | 4.25             |
| 2           | 1. kód         | 42.42         | 4.25             |
| 2           | 2. kód         | 42.42         | 4.25             |

Az adóalapösszeg számítása soronként történik:

- **1. sor:** 42,42
- **2. sor:** 42,42

Az adóösszeg számítása áfakódonként történik:

- **1. sor:**

    - 1. áfakódhoz adóösszeg = 42,42 &times; 10 százalék = 4,242
    - 2. áfakódhoz adóösszeg = 42,42 &times; 10 százalék = 4,242

- **2. sor:**

    - 1. áfakódhoz adóösszeg = 42,42 &times; 10 százalék = 4,242
    - 2. áfakódhoz adóösszeg = 42,42 &times; 10 százalék = 4,242

Az adóösszeg áfakódonként kerekített:

- **1. sor:**

    - 1-es áfakódhoz kerekített adóösszeg = 4,25
    - 2-es áfakódhoz kerekített adóösszeg = 4,25

- **2. sor:**

    - 1-es áfakódhoz kerekített adóösszeg = 4,25
    - 2-es áfakódhoz kerekített adóösszeg = 4,25

## <a name="example-2"></a>2. példa

### <a name="parameter-values"></a>Paraméterértékek

| Számítási mód | Kerekítés alapja    | Származás                   | Számítás alapja                 |
| ------------------ | -------------- | ------------------------ | ----------------------------- |
| Sor/összeg         | Áfakód | A nettó összeg százaléka | Számlaegyenleg nettó összege |

### <a name="calculation-and-rounding-behavior"></a>Számítás és kerekítés viselkedése

| Sor száma | Áfakód | Eredeti összeg | Áfa összege |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | 1. kód         | 42.42         | 4.25             |
| 1           | 2. kód         | 42.42         | 4.25             |
| 2           | 1. kód         | 42.42         | 4.24             |
| 2           | 2. kód         | 42.42         | 4.24             |

Az adóalapösszeg számítása dokumentumonként történik:

- Adóalap összege = 42,42 + 42,42 = 84,84

Az adóösszeg számítása áfakódonként történik:

- 1. áfakódhoz adóösszeg = 84,84 &times; 10 százalék = 8,484
- 2. áfakódhoz adóösszeg = 84,84 &times; 10 százalék = 8,484

Az adóösszeg áfakódonként kerekített:

- 1- es áfakódhoz kerekített adóösszeg = 8,49
- Kerekített adóösszeg a 2. áfakódhoz = 8,49

A kerekített áfaösszeg áfakódonként minden sorhoz hozzá van rendelve:

- Az 1-es áfakódhoz (8,49) hozzárendelt kerekített adóösszeg az 1. sorhoz (4,25) és a 2. sorhoz (4.24.)
- A 2-es áfakódhoz (8,49) hozzárendelt kerekített adóösszeg az 1. sorhoz (4,25) és a 2. sorhoz (4.24.)

## <a name="example-3"></a>3. példa

### <a name="parameter-values"></a>Paraméterértékek

| Számítási mód | Kerekítés alapja    | Származás                              | Számítás alapja       |
| ------------------ | -------------- | ----------------------------------- | ------------------- |
| Sor               | Áfakód | Nettó összeg számított százalékos értéke | Soronkénti nettó összeg |

### <a name="calculation-and-rounding-behavior"></a>Számítás és kerekítés viselkedése

| Sor száma | Áfakód | Eredeti összeg | Áfa összege |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | 1. kód         | 42.42         | 4.72             |
| 1           | 2. kód         | 42.42         | 4.72             |
| 2           | 1. kód         | 42.42         | 4.72             |
| 2           | 2. kód         | 42.42         | 4.72             |

Az adóalapösszeg számítása soronként történik:

- **1. sor:** 42,42
- **2. sor:** 42,42

Az adóösszeg számítása áfakódonként történik:

- **1. sor:**

    - 1. áfakódhoz adóösszeg = 42,42 &times; 10 százalék &divide; (1 – 10 százalék) = 4,7133
    - 2. áfakódhoz adóösszeg = 42,42 &times; 10 százalék &divide; (1 – 10 százalék) = 4,7133

- **2. sor:**

    - 1. áfakódhoz adóösszeg = 42,42 &times; 10 százalék &divide; (1 – 10 százalék) = 4,7133
    - 2. áfakódhoz adóösszeg = 42,42 &times; 10 százalék &divide; (1 – 10 százalék) = 4,7133

Az adóösszeg áfakódonként kerekített:

- **1. sor:**

    - 1- es áfakódhoz kerekített adóösszeg = 4,72
    - 2-es áfakódhoz kerekített adóösszeg = 4,72

- **2. sor:**

    - 1- es áfakódhoz kerekített adóösszeg = 4,72
    - 2-es áfakódhoz kerekített adóösszeg = 4,72

## <a name="example-4"></a>4. példa

### <a name="parameter-values"></a>Paraméterértékek

| Számítási mód | Kerekítés alapja    | Származás                              | Számítás alapja                 |
| ------------------ | -------------- | ----------------------------------- | ----------------------------- |
| Sor/összeg         | Áfakód | Nettó összeg számított százalékos értéke | Számlaegyenleg nettó összege |

### <a name="calculation-and-rounding-behavior"></a>Számítás és kerekítés viselkedése

| Sor száma | Áfakód | Eredeti összeg | Áfa összege |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | 1. kód         | 42.42         | 4.72             |
| 1           | 2. kód         | 42.42         | 4.72             |
| 2           | 1. kód         | 42.42         | 4.71             |
| 2           | 2. kód         | 42.42         | 4.71             |

Az adóalapösszeg számítása dokumentumonként történik:

- Adóalap összege = 42,42 + 42,42 = 84,84

Az adóösszeg számítása áfakódonként történik:

- 1. áfakódhoz adóösszeg = 84,84 &times; 10 százalék &divide; (1 – 10 százalék) = 9,4267
- 2. áfakódhoz adóösszeg = 84,84 &times; 10 százalék &divide; (1 – 10 százalék) = 9,4267

Az adóösszeg áfakódonként kerekített:

- 1- es áfakódhoz kerekített adóösszeg = 9,43
- 2-es áfakódhoz kerekített adóösszeg = 9,43

A kerekített áfaösszeg áfakódonként minden sorhoz hozzá van rendelve:

- Az 1-es (9,43-as) áfakódhoz az 1. sorhoz (4.72.) és a 2. sorhoz (4,71) kell hozzárendelni az adóösszeget.
- A 2-es áfakódhoz (9,43) hozzárendelt adóösszeg az 1. sorhoz (4.72.) és a 2. sorhoz (4.71.)

## <a name="example-5"></a>5. példa

### <a name="parameter-values"></a>Paraméterértékek

| Számítási mód | Kerekítés alapja                | Származás                   | Számítás alapja       |
| ------------------ | -------------------------- | ------------------------ | ------------------- |
| Sor               | Áfakód-kombináció | A nettó összeg százaléka | Soronkénti nettó összeg |

### <a name="calculation-and-rounding-behavior"></a>Számítás és kerekítés viselkedése

| Sor száma | Áfakód | Eredeti összeg | Áfa összege |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | 1. kód         | 42.42         | 4.25             |
| 1           | 2. kód         | 42.42         | 4.24             |
| 2           | 1. kód         | 42.42         | 4.24             |
| 2           | 2. kód         | 42.42         | 4.24             |

Az adóalapösszeg számítása soronként történik:

- **1. sor:** 42,42
- **2. sor:** 42,42

Az adóösszeg számítása áfakódonként történik:

- **1. sor:**

    - 1. áfakódhoz adóösszeg = 42,42 &times; 10 százalék = 4,242
    - 2. áfakód adóösszege = 42,42 &times; 10 százalék = 4,242

- **2. sor:**

    - 1. áfakódhoz adóösszeg = 42,42 &times; 10 százalék = 4,242
    - 2. áfakódhoz adóösszeg = 42,42 &times; 10 százalék = 4,242

Az adóösszeg áfakód-kombinációnként kerekített:

- Teljes áfaösszeg = 4,242 + 4,242 + 4,242 + 4,242 = 16,968, kerekítéssel 16,97-re

A kerekített áfaösszeg áfakódonként minden sorhoz hozzá van rendelve:

- Az áfaösszeg (16,97) felosztása az 1. és a 2. sorhoz:

    - **1. sor:**

        - 1- es áfakód adóösszege = 4,25
        - 2- es áfakód adóösszege = 4,24

    - **2. sor:**

        - 1- es áfakód adóösszege = 4,24
        - 2- es áfakód adóösszege = 4,24

## <a name="example-6"></a>6. példa

### <a name="parameter-values"></a>Paraméterértékek

| Számítási mód | Kerekítés alapja                | Származás                   | Számítás alapja                 |
| ------------------ | -------------------------- | ------------------------ | ----------------------------- |
| Sor/összeg         | Áfakód-kombináció | A nettó összeg százaléka | Számlaegyenleg nettó összege |

### <a name="calculation-and-rounding-behavior"></a>Számítás és kerekítés viselkedése

| Sor száma | Áfakód | Eredeti összeg | Áfa összege |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | 1. kód         | 42.42         | 4.25             |
| 1           | 2. kód         | 42.42         | 4.24             |
| 2           | 1. kód         | 42.42         | 4.24             |
| 2           | 2. kód         | 42.42         | 4.24             |

Az adóalapösszeg számítása dokumentumonként történik:

- Adóalap összege = 42,42 + 42,42 = 84,84

Az adóösszeg számítása áfakódonként történik:

- 1. áfakódhoz adóösszeg = 84,84 &times; 10 százalék = 8,484
- 2. áfakódhoz adóösszeg = 84,84 &times; 10 százalék = 8,484

Az adóösszeg áfakód-kombinációnként kerekített:

- Áfa végösszege = 8,484 + 8,484 = 16,968, amelyet felkerekített értékként 16,97-re

A kerekített áfaösszeg áfakódonként minden sorhoz hozzá van rendelve:

- Az áfaösszeg (16,97) felosztása az 1. és a 2. sorhoz:

    - **1. sor:**

        - 1- es áfakód adóösszege = 4,25
        - 2- es áfakód adóösszege = 4,24

    - **2. sor:**

        - 1- es áfakód adóösszege = 4,24
        - 2- es áfakód adóösszege = 4,24

## <a name="example-7"></a>7. példa

### <a name="parameter-values"></a>Paraméterértékek

| Számítási mód | Kerekítés alapja                | Származás                              | Számítás alapja       |
| ------------------ | -------------------------- | ----------------------------------- | ------------------- |
| Sor               | Áfakód-kombináció | Nettó összeg számított százalékos értéke | Soronkénti nettó összeg |

### <a name="calculation-and-rounding-behavior"></a>Számítás és kerekítés viselkedése

| Sor száma | Áfakód | Eredeti összeg | Áfa összege |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | 1. kód         | 42.42         | 4.72             |
| 1           | 2. kód         | 42.42         | 4.71             |
| 2           | 1. kód         | 42.42         | 4.71             |
| 2           | 2. kód         | 42.42         | 4.72             |

Az adóalapösszeg számítása soronként történik:

- **1. sor:** 42,42
- **2. sor:** 42,42

Az adóösszeg számítása áfakódonként történik:

- **1. sor:**

    - 1. áfakódhoz adóösszeg = 42,42 &times; 10 százalék &divide; (1 – 10 százalék) = 4,7133
    - 2. áfakódhoz adóösszeg = 42,42 &times; 10 százalék &divide; (1 – 10 százalék) = 4,7133

- **2. sor:**

    - 1. áfakódhoz adóösszeg = 42,42 &times; 10 százalék &divide; (1 – 10 százalék) = 4,7133
    - 2. áfakódhoz adóösszeg = 42,42 &times; 10 százalék &divide; (1 – 10 százalék) = 4,7133

Az adóösszeg áfakód-kombinációnként kerekített:

- Teljes áfaösszeg = 4,7133 + 4,7133 + 4,7133 + 4,7133 = 18,8532, felkerekítéssel 18,86-ra

A kerekített áfaösszeg áfakódonként minden sorhoz hozzá van rendelve:

- Az áfaösszeg (18,86) felosztása az 1. és a 2. sorhoz:

    - **1. sor:**

        - 1. áfakódhoz adóösszeg = 4,72
        - 2. áfakódhoz adóösszeg = 4,71

    - **2. sor:**

        - 1. áfakódhoz adóösszeg = 4,71
        - 2. áfakódhoz adóösszeg = 4,72

## <a name="example-8"></a>8. példa

### <a name="parameter-values"></a>Paraméterértékek

| Számítási mód | Kerekítés alapja                | Származás                              | Számítás alapja                 |
| ------------------ | -------------------------- | ----------------------------------- | ----------------------------- |
| Sor/összeg         | Áfakód-kombináció | Nettó összeg számított százalékos értéke | Számlaegyenleg nettó összege |

### <a name="calculation-and-rounding-behavior"></a>Számítás és kerekítés viselkedése

| Sor száma | Áfakód | Eredeti összeg | Áfa összege |
| ----------- | -------------- | ------------- | ---------------- |
| 1           | 1. kód         | 42.42         | 4.72             |
| 1           | 2. kód         | 42.42         | 4.71             |
| 2           | 1. kód         | 42.42         | 4.71             |
| 2           | 2. kód         | 42.42         | 4.72             |

Az adóalapösszeg számítása dokumentumonként történik:

- Adóalap összege = 42,42 + 42,42 = 84,84

Az adóösszeg számítása áfakódonként történik:

- 1. áfakódhoz adóösszeg = 84,84 &times; 10 százalék &divide; (1 – 10 százalék) = 9,4267
- 2. áfakódhoz adóösszeg = 84,84 &times; 10 százalék &divide; (1 – 10 százalék) = 9,4267

Az adóösszeg áfakód-kombinációnként kerekített:

- Áfa végösszege = 9,4267 + 9,4267 = 18,8534, kerekítéssel 18,86-ra

A kerekített áfaösszeg áfakódonként minden sorhoz hozzá van rendelve:

- Az áfaösszeg (18,86) felosztása az 1. és a 2. sorhoz:

    - **1. sor:**

        - 1. áfakódhoz adóösszeg = 4,72
        - 2. áfakódhoz adóösszeg = 4,71

    - **2. sor:**

        - 1. áfakódhoz adóösszeg = 4,71
        - 2. áfakódhoz adóösszeg = 4,72

## <a name="additional-resources"></a>További erőforrások

- [Áfaszámítási módok a Kiindulás mezőben](sales-tax-calculation-methods-origin-field.md)
- [Áfaérték a Számítás alapja és a Számítási módszerek lapján](marginal-base-field.md)
- [Teljesösszeg- és intervallumszámítási opciók áfakódokhoz](whole-amount-interval-options-sales-tax-codes.md)
