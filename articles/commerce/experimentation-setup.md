---
title: Kísérlet beállítása
description: Ez a témakör azt mutatja be, hogyan állíthat be kísérletet egy harmadik fél szolgáltatásban.
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
ms.openlocfilehash: 1a60eb459d6d6f710e43ac5418b9375420ca8387
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000784"
---
# <a name="set-up-an-experiment"></a>Kísérlet beállítása

Miután [meghatározott egy hipotézist, valamint a használni kívánt sikerességi mérőszámokat](experimentation-identify.md), be kell állítani a kísérletet a harmadik fél szolgáltatásban. A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó kísérletet lehet létrehozni és futtatni a Dynamics 365 Commerce rendszerben. A további lépések külön témákban szerepelnek.

[ ![Kísérletezés felhasználói interakciósorozata – Beállítás](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)


## <a name="set-up-your-experiment-in-the-third-party-service"></a>A kísérlet beállítása a harmadik szolgáltatásban
Eddigre már eldöntötte, hogy harmadik fél szolgáltatással futtatja és követi nyomon a kísérletet, és beállította a kísérlet-összekötőt. Ezeket az előfeltételeket a [Kísérletezés a Dynamics 365 Commerce rendszerben](experimentation-overview.md) rész sorolja fel.

Kövesse a kísérlet harmadik fél szolgáltatásban való létrehozásához szükséges lépéseket. Ha az összekötőt jól konfigurálta, a harmadik fél szolgáltatásban beállított kísérletek teljes listája mintegy 5 percen belül megjelenik a Commerce webhelykészítőben.

## <a name="set-up-your-success-metrics"></a>A sikerességi mérőszámok beállítása
Minden kísérlethez mérőszámok szükségesek a változatok hatásainak mérésére és a hipotézis ellenőrzésére. Hajtsa végre az alábbi lépéseket, ha engedélyezni szeretné a mérőszámok számítását a harmadik fél szolgáltatásban a Dynamics 365 Commerce rendszerben élő telemetria eseményei segítségével.

A sikermutatók beállításához kövesse az alábbi lépéseket.

1. A Commerce webhelykészítőben a bal oldali navigációs ablakban válassza ki az **Oldalak** fület, majd válassza ki azt az oldalt, amelyhez a mérőszámokat gyűjteni szeretné. 
1. Lépjen a követni kívánt oldal vagy modul jobb oldali tulajdonságok panelján lévő **Követendő eseményazonosítók** szakaszra.
1. Válassza ki a **Nézet** lehetőséget. Megjelenik az összes eseményazonosító listája. Másolja ki a nyomon követni kívánt eseményt, majd illessze be az eseménykulcsot a harmadik fél szolgáltatás által meghatározott helyre. Ha egynél több eseményre van szüksége, akkor egyenként másolja át a kulcsokat. 
    - A rendelkezésre álló események és attribútumok, köztük az oldalmegtekintések és a bevételek nyomon követése megtekintéséhez a következő témakör tartalmaz további tájékoztatást: [Commerce-összetevővel kapcsolatos események a diagnosztikához és a hibaelhárításhoz](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).
1. Hajtsa végre a szükséges lépéseket a mérőszámoknak a harmadik fél szolgáltatásban való nyomon követéséhez.

## <a name="previous-step"></a>Előző lépés
[Hipotézis meghatározása és mérőszámok megadása egy kísérlethez](experimentation-identify.md) 


## <a name="next-step"></a>Következő lépés
[Kísérlet csatlakoztatása és szerkesztése](experimentation-connect-edit.md)
