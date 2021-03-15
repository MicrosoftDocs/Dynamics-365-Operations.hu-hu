---
title: Hipotézis meghatározása és mérőszámok megadása egy kísérlethez
description: Ez a témakör azt mutatja be, hogyan lehet a Dynamics 365 Commerce rendszerben e-kereskedelmi webhelyeken futtatott kísérlethez hipotézist és sikerességi mérőszámokat meghatározni.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 5594b81d09eade263487244a14c0305d589ff94e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009999"
---
# <a name="identify-a-hypothesis-and-determine-success-metrics-for-an-experiment"></a>Hipotézis meghatározása és sikerességi mérőszámok megadása egy kísérlethez
A kísérletezési életciklus első fázisa tartalmazza a kísérlethez tartozó hipotézis, valamint a sikeresség értékeléséhez nyomon követni kívánt mérőszámok meghatározását. A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó [kísérletet lehet létrehozni és futtatni](experimentation-overview.md) a Dynamics 365 Commerce rendszerben. A további lépések külön témákban szerepelnek. 

[ ![Kísérletezés felhasználói interakciósorozata – Azonosítás](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)

A hipotézis egy olyan kijelentés, amelyben megjósolja a kísérlet kimenetelét. Számos tényező befolyásolja a hipotézist, így például a felhasználói magatartásról és a összegyűjtött webhely adatairól folytatott kutatás. A hipotézissel meghatározhatja, hogy milyen feltételezést vagy elméletet szeretne igazolni a kísérletével. Egy példa a kísérlethez meghatározható hipotézisre: „*ha a honlapomon egy fehér póló képe látható, akkor az több kattintást hoz majd, mint egy tengerkék pulóver a nyári hónapokban, mivel az emberek könnyű és világos színű ruhadarabokat viselnek a nyári hónapokban.*” Ebben az esetben a fehér pólót és a tengerkék pulóvert tartalmazó változatokat hoz létre, és ezeket egyszerre közzé is teheti.

A hipotézis igazolásához egy kísérlet sikerességét vagy sikertelenségét közvetlenül a felhasználói műveletekhez kell kötni: például, hogy a webhely felhasználója rákattint-e egy hivatkozásra vagy gombra. Ezeknek a műveleteknek meg kell egyezniük a harmadik fél szolgáltatás által a kísérlet nyomon követésére szolgáló jelentésekbe foglalt eseményekkel. Az idő előhaladásával a műveletet végrehajtó felhasználók százalékát a program mérőszámként összesíti, amelyekről jelentéseket készíthet vagy amelyeken elemzéseket folytathat le. Az összes rendelkezésre álló esemény és attribútum áttekintéséhez lásd a [Commerce-összetevővel kapcsolatos események a diagnosztikához és a hibaelhárításhoz](dev-itpro/retail-component-events-diagnostics-troubleshooting.md) témakört.

## <a name="previous-step"></a>Előző lépés
[Kísérletezés a Dynamics 365 Commerce rendszerben](experimentation-overview.md)


## <a name="next-step"></a>Következő lépés
[Kísérlet beállítása](experimentation-setup.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]