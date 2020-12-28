---
title: Kísérlet futtatása és nyomon követése
description: Ez a témakör azt mutatja be, hogyan indíthat el és követhet nyomon kísérletet egy harmadik fél szolgáltatásban. Ez a témakör azt is leírja, hogy hogyan lehet módosítani a változatokat a kísérlet elindítása után.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
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
ms.openlocfilehash: ee86a6761b27f3c08a65a2e250659cdcfd71db44
ms.sourcegitcommit: cd83f2bc0e52e13071ad306e07e4c255fc65cb03
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/22/2020
ms.locfileid: "4413006"
---
# <a name="run-and-monitor-an-experiment"></a>Kísérlet futtatása és nyomon követése

Ez a témakör azt mutatja be, hogyan futtathatja és követheti nyomon a kísérleteit egy harmadik fél alkalmazásban, továbbá hogyan módosíthatja szükség esetén a változatokat. A témakör lépéseinek végrehajtása előtt először [közzé kell tennie](experimentation-preview-publish.md) a kísérletet a Commerce modulban. 

A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó kísérletet lehet létrehozni és futtatni a Dynamics 365 Commerce rendszerben. A további lépések külön témákban szerepelnek.

[ ![Kísérletezés felhasználói interakciósorozata – Futtatás és nyomon követés](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)

A változatok közzététele után végezze el a kísérletek futtatásához szükséges lépéseket a Commerce modulban. A következő lépés azt határozza meg, hogy melyik változat jelenjen meg az egyes felhasználóknak, amikor egy oldalt hívnak le. A harmadik fél szolgáltatás teszi ezt a meghatározást, de először aktiválni kell a kísérletet a szolgáltatáson belül. Mivel a kísérletek aktiválásának lépései szolgáltatásonként eltérők, a szolgáltatáshoz vagy a szolgáltatóhoz tartozó utasításokat kell követni. Ha a kísérlet nincs aktiválva, a felhasználók csak az oldal alapértelmezett változatát fogják látni – nem fognak megjelenni az eltérések.

Elég hosszú ideig kell futtatnia a kísérletet ahhoz, hogy a statisztikailag érvényes eredményeket hozó adatokat gyűjtsön. A harmadik fél szolgáltatások segítségével nyomon követheti a kísérlethez kapcsolódó adatokat és analitikákat.

## <a name="adjust-your-variations"></a>A változatok szerkesztése
Ha bármilyen oknál fogva módosítania kell a változatokat, az alábbi lépéseket hajtsa végre.

> [!IMPORTANT]
> Ha módosít egy élő kísérletet a Commerce modulban vagy a harmadik fél szolgáltatásban, akkor az jelentős mértékben befolyásolhatja az eredményeket. Esetleg hagyja végigfutni a kísérletet, és aztán a jelentősebb módosításokhoz új kísérletet hozzon létre.

1. A Commerce webhelykészítőben lépjen a **Kísérletek** fülre a bal oldali navigációs panelen, majd válassza ki a kísérletet. 
1. Válassza ki a frissíteni kívánt változatot a legördülő menüből.
1. Végezze el a szükséges módosításokat, majd tekintse meg előnézetben és tegye közzé a változatokat. További tudnivalókért lásd: [Egy kísérlet előnézete és közzététele](experimentation-preview-publish.md).
1. Nyissa meg a harmadik fél szolgáltatást a kísérletezéssel kapcsolatos módosítások elvégzéséhez.
    
## <a name="previous-step"></a>Előző lépés
[Kísérlet előnézetének megtekintése és közzététele](experimentation-preview-publish.md)

## <a name="next-step"></a>Következő lépés
[Változat előléptetése és egy kísérlet végrehajtása](experimentation-review-complete.md)
