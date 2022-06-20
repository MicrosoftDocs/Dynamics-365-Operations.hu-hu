---
title: Kísérlet futtatása és nyomon követése
description: Ez a témakör azt ismerteti, hogyan lehet futtatni és figyelni egy harmadik fél szolgáltatásában történő kísérleteket. Ez a témakör azt is leírja, hogy hogyan lehet módosítani a változatokat a kísérlet elindítása után.
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
ms.openlocfilehash: c9f62c97b46fa00791de52b2804dad5edde7f625
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909583"
---
# <a name="run-and-monitor-an-experiment"></a>Kísérlet futtatása és nyomon követése

Ez a témakör leírja, hogyan lehet futtatni és figyelni a harmadik fél alkalmazásában történő kísérleteket, és szükség esetén módosítani a variációkat. A cikk lépéseit csak azt megelőzően lehet végrehajtani, [hogy](experimentation-preview-publish.md) közzéteheti a kereskedelmi kísérleteket. 

A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó kísérletet lehet létrehozni és futtatni a Dynamics 365 Commerce rendszerben. A további lépések külön cikkekbe tartoznak.

[ ![Kísérletezés felhasználói interakciósorozata – Futtatás és nyomon követés.](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]