---
title: Változat előléptetése és egy kísérlet végrehajtása
description: Ez a témakör ismerteti, hogyan lehet elősegíteni a sikeres változatokat, és végrehajtani a kísérletekkel a következőben:Dynamics 365 Commerce
author: sushma-rao
ms.date: 06/07/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 3e9a978551622bbb14d9213f607d9dfabe42672a
ms.sourcegitcommit: ddcb62bb5fbf26a1178c2bb1aec45a3d2362339e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/07/2022
ms.locfileid: "8942743"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a>Változat előléptetése és egy kísérlet végrehajtása

Ez a témakör ismerteti, hogyan lehet elősegíteni a kísérlet során legjobb eredményt hozó variációt, valamint a kísérlet befejezését. A következő ábra azokat a lépéseket mutatja be, amelyekkel egy e-kereskedelmi webhelyhez tartozó kísérletet lehet létrehozni és futtatni a Dynamics 365 Commerce rendszerben. A további lépések külön cikkekbe tartoznak.

[ ![Kísérletezés felhasználói interakciósorozata – Áttekintés és befejezés.](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)

Miután [elvégezte a kísérletet](experimentation-run-monitor.md), és összegyűjtötte a szükséges adatokat annak meghatározására, hogy melyik változatot szeretné használni az élő webhelyén, előléptetheti a változatot, és befejezheti a kísérletet.

## <a name="promote-a-variation"></a>Változat előléptetése
A harmadik fél szolgáltatásban a kísérlethez kapcsolódó adatok és analitika alapján döntheti el, hogy melyik változat hozta létre a legjobb eredményt. Ezután az aktuális tartalom lecserélésével előléptetheti az élő webhelyen a legjobbnak tartott változattal, hogy a webhely összes felhasználója számára elérhető legyen.

A nyerő változat előléptetéséhez kövesse az alábbi lépéseket. 

1. A Commerce webhelykészítőben lépjen a **Kísérletek** fülre a bal oldali navigációs panelen, majd válassza ki a kísérletet.
1. A parancssávon válassza ki a **Teljes kísérlet** elemet.
1. A **Teljes kísérlet** párbeszédpanel menüjében válassza ki a **Kísérletadatok áttekintése** elemet. A harmadik fél szolgáltatás megnyílik, és Ön ellenőrizheti a mérőszámokat, és meghatározhatja, hogy melyik változat teljesített a legjobban.
1. Válassza ki a legjobbnak tartott változatot a **Teljes kísérlet** párbeszédpanel menüjében, majd válassza a **Következő** lehetőséget.
1. Nyissa meg a harmadik fél szolgáltatást, és állítsa le a kísérletet.
1. A webhelykészítőben válassza ki a **Befejezés** lehetőséget az eredeti élő oldal felülírásához és a legjobbnak tartott változat közzétételéhez úgy, hogy a webhely minden felhasználója számára elérhető legyen. 

> [!NOTE]
> Ha úgy dönt, hogy megtartja az aktuális élő oldalt, és nem tesz közzé egy változatot, jelölje be az **Eredeti oldal ismételt közzététele** jelölőnégyzetet.

## <a name="delete-your-experiment"></a>A kísérlet törlése
A Commerce rendszerből ugyan nem kell kitörölni a befejezett kísérletet, erre azonban lehetőség van tárhely felszabadítása vagy a munkatér megtisztítása érdekében. 

A Commerce Webhelyszerkesztő egy befejezett kísérletének törléséhez kövesse ezeket a lépéseket.

1. Lépjen a **Kísérletek** fülre a bal oldali navigációs panelen, majd válassza ki a kísérletet. 
    > [!NOTE]
    > Ha a kísérlet továbbra is aktív, akkor a továbblépés előtt állítsa le a kísérletet a harmadik fél szolgáltatásban.
1. A parancssoron a **Közzététel megszüntetése** lehetőség kiválasztásával eltávolíthatja a változat tartalmát az élő webhelyről.
1. A kísérlet törléséhez válassza a **törlés** elemet.

## <a name="previous-step"></a>Előző lépés
[Kísérlet futtatása és nyomon követése](experimentation-run-monitor.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
