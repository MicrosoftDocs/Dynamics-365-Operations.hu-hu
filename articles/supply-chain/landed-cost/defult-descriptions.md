---
title: A főkönyv alapértelmezett leírásai
description: Az alapértelmezett leírásokkal lehet frissíteni a főkönyvbe való bizonylatfeladások Leírás mezőjét.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: d5a38af57d614ae2c93b0af74ec4a1c085519d46
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841896"
---
# <a name="default-descriptions-for-the-general-ledger"></a>A főkönyv alapértelmezett leírásai

[!include [banner](../../includes/banner.md)]

Az alapértelmezett leírásokkal lehet frissíteni a főkönyvbe való bizonylatfeladások **Leírás** mezőjét. Ez a funkció továbbfejlesztésre került, hogy működjön a Partraszállítási költséggel.

A főkönyvi feladások alapértelmezett leírásainak beállításához használja a **Szervezeti adminisztráció \> Beállítás \> Alapértelmezett leírások** lehetőséget.

A következő táblázat felsorolja azokat az új értékeket, amelyek az **Alapértelmezett leírás** oldal **Leírás** mezőjéhez hozzáadva a Partraszállítási költséget támogatják.

| Leírás típusa | Jegyzetek |
|---|---|
| Importálás költségszámítása – Költség elhatárolása | Beszerzési rendelés számlájának feladásakor egy költségelhatárolás kerül feldolgozásra a hajóút becsült költségeihez. Az hajóút számának a leíráshoz való hozzáadásához megadhatók alapértelmezett leírások. *%4* használata a szállítmányszámhoz. |
| Importálással kapcsolatos költségszámítás – Úton lévő árukkal kapcsolatos rendelés | Ha szállítás közbeni feldolgozást használ, feladásra kerül a beszerzési rendelés számlája, és az áruk feladása egy úton lévő áruk számlára lesznek feladva. A szállítás alatt lévő rendelés számának a leíráshoz való hozzáadásához megadhatók alapértelmezett leírások. *%4* használata a szállítás alatt lévő rendelés számához. |
| Készlet – zárás – helyesbítés | Ha a kötelezettségek (AP) számlája feldolgozásra kerül egy hajóútköltséghez, akkor a program készlethelyesbítést dolgoz fel a hajóút költségeinek becslésére. Az hajóút számának a leíráshoz való hozzáadásához megadhatók alapértelmezett leírások. *%4* használata a szállítmányszámhoz. |

Az **Alapértelmezett leírások** oldal beállításával kapcsolatos további tudnivalók: [Alapértelmezett leírások beállítása automatikus feladáshoz](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).
