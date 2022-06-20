---
title: Hipotézis meghatározása és mérőszámok megadása egy kísérlethez
description: Ez a témakör leírja, hogyan lehet azonosítani a kísérlethez szükséges teljesítmény és sikeresség mérőszámát, amelyek egy e-Commerce webhelyen futtatnak a következőben:Dynamics 365 Commerce
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 0b6bdf160522fc93e841ec2f8a4542ff80d8f67f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8852786"
---
# <a name="identify-a-hypothesis-and-determine-success-metrics-for-an-experiment"></a>Hipotézis meghatározása és sikerességi mérőszámok megadása egy kísérlethez
A kísérletezési életciklus első fázisa tartalmazza a kísérlethez tartozó hipotézis, valamint a sikeresség értékeléséhez nyomon követni kívánt mérőszámok meghatározását. A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó [kísérletet lehet létrehozni és futtatni](experimentation-overview.md) a Dynamics 365 Commerce rendszerben. A további lépések külön cikkekbe tartoznak. 

[ ![Kísérletezés felhasználói interakciósorozata – Azonosítás.](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)

A hipotézis egy olyan kijelentés, amelyben megjósolja a kísérlet kimenetelét. Számos tényező befolyásolja a hipotézist, így például a felhasználói magatartásról és a összegyűjtött webhely adatairól folytatott kutatás. A hipotézissel meghatározhatja, hogy milyen feltételezést vagy elméletet szeretne igazolni a kísérletével. Egy példa a kísérlethez meghatározható hipotézisre: „*ha a honlapomon egy fehér póló képe látható, akkor az több kattintást hoz majd, mint egy tengerkék pulóver a nyári hónapokban, mivel az emberek könnyű és világos színű ruhadarabokat viselnek a nyári hónapokban.*” Ebben az esetben a fehér pólót és a tengerkék pulóvert tartalmazó változatokat hoz létre, és ezeket egyszerre közzé is teheti.

A hipotézis igazolásához egy kísérlet sikerességét vagy sikertelenségét közvetlenül a felhasználói műveletekhez kell kötni: például, hogy a webhely felhasználója rákattint-e egy hivatkozásra vagy gombra. Ezeknek a műveleteknek meg kell egyezniük a harmadik fél szolgáltatás által a kísérlet nyomon követésére szolgáló jelentésekbe foglalt eseményekkel. Az idő előhaladásával a műveletet végrehajtó felhasználók százalékát a program mérőszámként összesíti, amelyekről jelentéseket készíthet vagy amelyeken elemzéseket folytathat le. Az összes rendelkezésre álló esemény és attribútum áttekintéséhez lásd a [Commerce-összetevővel kapcsolatos események a diagnosztikához és a hibaelhárításhoz](dev-itpro/retail-component-events-diagnostics-troubleshooting.md) témakört.

## <a name="previous-step"></a>Előző lépés
[Kísérletezés a Dynamics 365 Commerce rendszerben](experimentation-overview.md)


## <a name="next-step"></a>Következő lépés
[Kísérlet beállítása](experimentation-setup.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]