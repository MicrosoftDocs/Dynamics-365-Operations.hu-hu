---
title: Idők hozzárendelése egy feladatköteg feladataihoz
description: A gyártásvégrehajtásban kötegelhetők a feladatok. Egyszerre több feladatot is elkezdhet a feladatlista lapon.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgBundleSlize, JmgProdParameters, JmgRegistration
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 55591
ms.assetid: 358efce7-73c8-4d2a-a7f7-cb99b88ab6ee
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33d6bab9beb28d18e2094d7fb5e670e9425aac39
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/15/2019
ms.locfileid: "1552976"
---
# <a name="allocate-time-to-jobs-in-a-job-bundle"></a>Idők hozzárendelése egy feladatköteg feladataihoz

[!include [banner](../includes/banner.md)]

A gyártásvégrehajtásban kötegelhetők a feladatok. Egyszerre több feladatot is elkezdhet a feladatlista lapon.

Ha kötegeli a feladatokat, meg kell határoznia, hogyan az összes feladathoz regisztrált összidőből mennyit kell hozzárendelni az egyes feladatokhoz. A felosztást az alábbi lehetőségek közül választhatja ki a **Kötegtípus** mezőben, amelyet a **Felosztási kulcsok** lapon talál:

-   **Becslés** – a program a feladatok becsült ideje alapján osztja el az időt.
-   **Feladatok** – a program aszerint osztja el az időt, hogy összesen hány feladat lett kötegelve, és mennyi időt vett igénybe az összes feladat teljesítése.
-   **Nettó idő** – a program mindig egyenlően osztja el az időt a kötegben található feladatok között.
-   **Valós idejű** – a tényleges feladatidőt rendeli hozzá. A költségek kiszámítása a tényleges bérköltség alapján történik. **Megjegyzés:** a **Valós idejű** felosztási kulcs csak akkor áll rendelkezésre, ha a vállalat használja a bérlista-szolgáltatásokat a Munkaidő és jelenlét modulban.

Az alábbi példákon látható a különböző felosztási kulcsok eredménye.

## <a name="example-scenario"></a>Példaforgatókönyv
A feladat-várólistán szereplő három feladatot kell elvégezni. Elkezdi az első feladatot, és miközben ez a feladat még folyamatban van, elkezdi a második és a harmadik feladatot is. Ezzel egy három feladatból álló köteget hoz létre. Az alábbi táblázat bemutatja az egyes feladatokhoz tartozó becsült végrehajtási időket.

| Munka   | Termelés ideje |
|-------|-----------------|
| 1. feladat | 1 óra          |
| 2. feladat | 3 óra         |
| 3. feladat | 4 óra         |
| Összesen | 8 óra         |

Az alábbi táblázat mutatja be az egyes feladatokon ténylegesen ledolgozott munkaórákat.

| Munka    | Kezdés ideje | Befejezés ideje | Kötegidő |
|--------|------------|----------|-------------|
| 1. feladat  | 09:00      | 11:00:00    | 2 óra     |
| 2. feladat  | 10:00      | 13:00:00    | 3 óra     |
| 3. feladat  | 10:00      | 15:00    | 5 óra     |
| Köteg | 09:00      | 15:00    | 6 óra     |

Az alábbi szakaszok bemutatják a kiszámított idők eredményeit minden felosztási kulcshoz.

## <a name="estimation-allocation-key"></a>Becsült foglalási kulcs
Az alábbi táblázat bemutatja a felhasznált idő kiszámításának képletét. A képlet: Feladatonkénti idő = Teljes kötegidő x (Becsült feladatidő ÷ Teljes becsült idő)

| Munka   | Receptúra           | Felhasznált idő |
|-------|-------------------|----------------|
| 1. feladat | 6 × (1 ÷ 8) óra | 0,75 óra      |
| 2. feladat | 6 × (3 ÷ 8) óra | 2,25 óra     |
| 3. feladat | 6 × (4 ÷ 8) óra | 3,00 óra     |

## <a name="jobs-allocation-key"></a>Feladatok foglalási kulcs
Az alábbi táblázat bemutatja a felhasznált idő kiszámításának képletét. A képlet: Feladatonkénti idő = teljes kötegidő ÷ feladatok száma

| Munka   | Receptúra | Felhasznált idő |
|-------|---------|----------------|
| 1. feladat | 6 ÷ 3   | 2 óra        |
| 2. feladat | 6 ÷ 3   | 2 óra        |
| 3. feladat | 6 ÷ 3   | 2 óra        |

## <a name="net-time-allocation-key"></a>Nettó idő foglalási kulcs
Az alábbi táblázat bemutatja a felhasznált idő kiszámításának képletét. A képlet: Jelentésenkénti számított idő = kötegidő ÷ feladatok száma

|                              | 09:00–10:00 (1 óra) | 10:00–11:00 (1 óra) | 11:00–13:00 (2 óra) | 13:00–15:00 (2 óra) | Felhasznált idő |
|------------------------------|----------------------|----------------------|-----------------------|-----------------------|----------------|
| A kötegben található feladatok száma | 1                    | 3                    | 2                     | 1                     | Nem alkalmazható |
| 1. feladat                        | 1 ÷ 1 = 1 óra       | 1 ÷ 3 = 0,33 óra    | Nem alkalmazható        | Nem alkalmazható        | 1,33 óra     |
| 2. feladat                        | Nem alkalmazható       | 1 ÷ 3 = 0,33 óra    | 2 ÷ 2 = 1 óra        | Nem alkalmazható        | 1,33 óra     |
| 3. feladat                        | Nem alkalmazható       | 1 ÷ 3 = 0,33 óra    | 2 ÷ 2 = 1 óra        | 2 ÷ 1 = 2 óra       | 3,33 óra     |

## <a name="real-time-allocation-key"></a>Bérlista-felosztási kulcs
Ha a tényleges költségek alapján szeretné kiszámítani a gyártási költségeket, törölnie kell a jelölést a **Költségkategória** opcióból a **Termelési rendelés alapértelmezései** lapon. Az alábbi táblázat bemutatja a felhasznált idő kiszámításának képletét. A képlet: Feladatonkénti tényleges idő = Tényleges idő a kötegben

| Munka   | Tényleges idő |
|-------|-------------|
| 1. feladat | 2 óra     |
| 2. feladat | 3 óra     |
| 3. feladat | 5 óra     |

Vegyük a három feladatot, amelyet egy 12 dolláros órabérrel dolgozó alkalmazott hajt végre. A feladatokra fordított időre nem vonatkozik túlórapótlék vagy prémium. Az alkalmazott összesen 6 órát dolgozott ezen a 3 kötegelt feladaton. A bérköltség ezért 6 x 12,00 USD = 72,00 USD lesz. A valós idejű felosztás használata esetén az óránkénti költséget a program újraszámítja a Nettó idő képlet tényezőjével. Az egyes feladatokkal töltött tényleges idő ezután továbbítódik, a javított óránkénti önköltségi árral együtt. A példában hat óra telik munkával, annak ellenére, hogy 10 óra került foglalásra. Az alábbi táblázat bemutatja a költség kiszámításának képletét. Képlet: Óránkénti költség = (Feladatonkénti összesített idő (Nettó idő) ÷ Feladatonkénti tényleges idő) × Normál óránkénti önköltségi ár

| Munka   | A javított óránkénti költség kiszámítása | Javított óránkénti költség | Felhasznált idő | Feladat összesített költsége |
|-------|----------------------------------------|-------------------------|----------------|-------------------|
| 1. feladat | (1,33 ÷ 2) × 12,00 USD                 | 8,00 USD                | 2 óra        | 16,00 USD         |
| 2. feladat | (1,33 ÷ 3) × 12,00 USD                 | 5,33 USD                | 3 óra        | 16,00 USD         |
| 3. feladat | (3,33 ÷ 5) × 12,00 USD                 | 8,00 USD                | 5 óra        | 40,00 USD         |

A javított óránkénti költséget és a feladatidőt a termelési naplóba adja fel a program. **Megjegyzés:** Ha bejelöli a **Költségkategória** opciót az **Általános** lapon, amelyet a **Termelési rendelés alapértelmezései** oldalon talál, akkor az egyes feladatok tényleges idejét átmásolja a rendszer a termelési naplóba, ahol a költség az adott feladat költségkategóriájára lesz alkalmazva.



