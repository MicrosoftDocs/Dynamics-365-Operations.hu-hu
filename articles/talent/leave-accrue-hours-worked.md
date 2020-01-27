---
title: Szabadság elhatárolása a ledolgozott órák alapján
description: Ez a témakör leírja, hogyan állíthatók be a szabadságtervek úgy, hogy a szabadság elhatárolása ledolgozott órák alapján történjen.
author: andreabichsel
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-09-17
ms.dyn365.ops.version: ''
ms.openlocfilehash: 938d2eea7b9e85b19e9c1e3e0930f625224b880d
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898619"
---
# <a name="accrue-time-off-based-on-hours-worked"></a>Szabadság elhatárolása a ledolgozott órák alapján

## <a name="overview"></a>Áttekintés

Az órabéres alkalmazottakkal rendelkező szervezetek a ledolgozott órák alapján adhatnak szabadságot a szervezetnél ledolgozott idő helyett. A ledolgozott munkaórák jellemzően az idő- és megjelenésnyilvántartó rendszerben tárolódnak. A Talent: Core HR szolgáltatásban a rendszeres és túlórázott munkaórák importálhatók és felhasználhatók a munkavállalók szabadságmeghatározásának alapjául.

## <a name="leave-plans"></a>Szabadságtervek

A szabadságterven belül az elhatárolás típusa lehet a munkaviszonyban töltött hónapok vagy a ledolgozott órák száma. A ledolgozott munkaórák kiválasztása esetén kétféle óra számolható el: normál és túlóra.

Kövesse az alábbi lépéseket, ha szabadságtervet szeretne beállítani a ledolgozott órák alapján:

1. A **Szabadság- és távolléti tervek** lapon kattintson az **Új terv létrehozása** elemre.
2. Adja meg a szabadságterv nevét.
3. Válassza ki a terv halmozódási gyakoriságát.
5. A csomag kezdő dátumának megadása.
6. Válassza ki a elhatárolási időszak alapját, illetve az alkalmazottra vonatkozó dátumot, amennyiben van ilyen.
7. Az elhatárolási ütemezésnél válassza a **Ledolgozott órák** elhatárolási típust.
8. Válassza ki az órák elhatárolásnál használandó típusát.
9. Adja meg a munkaórák számát és a kapcsolódó elhatárolási összeget, minimális egyenleget és maximális átvihető vagy támogatott összeget.

Az óránkénti munkavégzéssel kapcsolatos eredményszemléletű elszámolás az eredményszemlélet gyakoriságát és az elhatárolás időszakát használja az elhatárolható órák meghatározásához.

## <a name="annual-accrual-frequency"></a>Az elhatárolás éves gyakorisága

| Elhatárolási jutalmazás dátuma    | Ledolgozott órák szintalapja    | Halmozódás összege        | Ledolgozott órák dátumai   | Ténylegesen ledolgozott órák| Jutalom               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 2018/31/12            | 2080                 | 144                   | 1/1/2018-12/31/2018  | 2085                | 144                 |        
| 2018/31/12            | 2080                 | 144                   | 1/1/2018-12/31/2018  | 2000                | 0                 |


## <a name="monthly-accrual-frequency"></a>Havi elhatárolás gyakorisága

| Elhatárolási jutalmazás dátuma    | Ledolgozott órák szintalapja    | Halmozódás összege        | Ledolgozott órák dátumai   | Ténylegesen ledolgozott órák| Jutalom               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 2018/31/8             | 160                  | 12                    | 8/1/2018-8/31/2018   | 184                 | 12                  |        
| 2018/31/8             | 160                  | 3                     | 8/1/2018-8/31/2018   | 184                 | 3                   |

## <a name="semi-monthly-accrual-frequency"></a>Félhavi elhatárolás gyakorisága

| Elhatárolási jutalmazás dátuma    | Ledolgozott órák szintalapja    | Halmozódás összege        | Ledolgozott órák dátumai   | Ténylegesen ledolgozott órák| Jutalom               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 2018/31/8             | 80                   | 6                     | 8/16/2018-8/31/2018  | 81                  | 6                  |        
| 2018/31/8             | 80                   | 6                     | 8/16/2018-8/31/2018  | 75                  | 0                   |

## <a name="weekly-accrual-frequency"></a>Heti elhatárolás gyakorisága

| Elhatárolási jutalmazás dátuma    | Ledolgozott órák szintalapja    | Halmozódás összege        | Ledolgozott órák dátumai   | Ténylegesen ledolgozott órák| Jutalom               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 2018/31/8             | 40                   | 3                     | 8/27/2018-8/31/2018  | 42                  | 3                  |        
| 2018/31/8             | 40                   | 3                     | 8/27/2018-8/31/2018  | 35                  | 0                   |

## <a name="employee-assigned-leave-plans"></a>Alkalmazotthoz rendelt szabadságtervek

Az alkalmazott hozzárendelt szabadságterveiben a munkaórák számának szintje és típusa látható azoknál a terveknél, ahol a munkaidő meghatározása elhatárolt típusú. Aktív tervek esetén a ténylegesen ledolgozott órák az elhatárolási időszakok szerint is megjelennek tájékoztatásul. 

## <a name="loading-data"></a>Adatok betöltése

A tényleges órák importálhatók a Ledolgozott szabadság- és távolléti órák entitással az adatok kezelésénél. A munkaidőnaptárak használata esetén az importálás ellenőrzi, hogy a normál ledolgozott órák száma nem haladja-e meg a naptárban meghatározott ütemezett órák számát. Az importálás azt is ellenőrzi, hogy egy adott napon ledolgozott órák száma nem haladja-e meg a 24 órát. 

A következő adatok szükségesek a ténylegesen ledolgozott munkaórák importálásához, melyek felhasználhatók a szabadságelhatárolási folyamat során:

+ Személyzeti szám 
+ Munkában töltött nap
+ Típus
+ óra

Egy adott dátum csak egy típushoz társítható.

| SZEMÉLYZETISZÁM       | MUNKÁBAN TÖLTÖTT NAP           | TÍPUS                  | ÓRA                |
| --------------------- | -------------------- | --------------------- | -------------------- |
| 000337                | 2018/6/8             | Szabályos               | 8                    |       
| 000337                | 2018/7/8             | Szabályos               | 8                    |
| 000337                | 2018/7/8             | Túlóra              | 3                    |
| 000337                | 2018/8/8             | Szabályos               | 8                    |
| 000337                | 2018/7/8             | Szabályos               | 8                    |
| 000337                | 2018/9/8             | Szabályos               | 8                    |
