---
title: Változat előléptetése és egy kísérlet végrehajtása
description: Ez a témakör azt mutatja be, hogyan lehet egy sikeres változatot előléptetni és egy kísérletet végrehajtani a Dynamics 365 Commerce rendszerben.
author: sushma-rao
manager: AnnBe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 2e011f10e908d6a2efe2e928fc5e0abc7659cb8b
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930208"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a>Változat előléptetése és egy kísérlet végrehajtása

Ez a témakör azt mutatja be, hogyan lehet előléptetni a kísérletek legjobb eredményeit hozó változatokat, valamint a kísérleteket végrehajtani. A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó kísérletet lehet létrehozni és futtatni a Dynamics 365 Commerce rendszerben. A további lépések külön témákban szerepelnek.

[ ![Kísérletezés felhasználói interakciósorozata – Áttekintés és befejezés](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)

Miután [elvégezte a kísérletet](experimentation-run-monitor.md), és összegyűjtötte a szükséges adatokat annak meghatározására, hogy melyik változatot szeretné használni az élő webhelyén, előléptetheti a változatot, és befejezheti a kísérletet.

## <a name="promote-a-variation"></a>Változat előléptetése
A harmadik fél szolgáltatásban a kísérlethez kapcsolódó adatok és analitika alapján döntheti el, hogy melyik változat hozta létre a legjobb eredményt. Ha az aktuális tartalmat a legjobbnak tartott változattal szeretné helyettesíteni a webhely összes felhasználója számára, akkor tegye a következőket. 

1. Lépjen a webhelykészítő **Kísérletek** fülére, és válassza ki a kísérletet.
1. Válassza ki a felső sávon lévő **Teljes kísérlet** elemet.
1. A **Teljes kísérlet** párbeszédpanel menüjében válassza ki a **Kísérletadatok áttekintése** elemet. A harmadik fél szolgáltatás megnyílik, és Ön ellenőrizheti a mérőszámokat, és meghatározhatja, hogy melyik változat teljesített a legjobban.
1. Válassza ki a legjobbnak tartott változatot a webhelykészítő **Teljes kísérlet** párbeszédpanel menüjében, majd válassza a **Következő** lehetőséget.
1. Nyissa meg a harmadik fél szolgáltatást, és állítsa le a kísérletet.
1. A webhelykészítőben válassza ki a **Befejezés** lehetőséget az eredeti élő oldal felülírásához és a legjobbnak tartott változat közzétételéhez úgy, hogy a webhely minden felhasználója számára elérhető legyen. 

> [!NOTE]
> Ha úgy dönt, hogy megtartja az aktuális élő oldalt, és nem tesz közzé egy változatot, jelölje be az **Eredeti oldal ismételt közzététele** jelölőnégyzetet.

## <a name="delete-your-experiment"></a>A kísérlet törlése
A Commerce rendszerből ugyan nem kell kitörölni a befejezett kísérletet, erre azonban lehetőség van tárhely felszabadítása vagy a munkatér megtisztítása érdekében. Egy kísérlet törléséhez a következő műveleteket hajtsa végre.

1. Lépjen a webhelykészítő **Kísérletek** fülére, és válassza ki a kísérletet. 
    > [!NOTE]
    > Ha a kísérlet továbbra is aktív, akkor a továbblépés előtt állítsa le a kísérletet a harmadik fél szolgáltatásban.
1. A parancssoron található **Közzététel megszüntetése** lehetőség kiválasztásával eltávolíthatja a változat tartalmát az élő webhelyről.
1. A parancssoron található **Törlés** lehetőség kiválasztásával törölheti a kísérletet.

## <a name="previous-step"></a>Előző lépés
[Kísérlet futtatása és nyomon követése](experimentation-run-monitor.md)
