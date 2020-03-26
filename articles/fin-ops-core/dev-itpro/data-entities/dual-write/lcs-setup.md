---
title: Kettős írás beállítása a Lifecycle Services modulból
description: Ez a témakör azt mutatja be, hogyan lehet beállítani egy kettős írási kapcsolatot egy új Finance and Operations környezet és egy új Common Data Service környezet között a Microsoft Dynamics Lifecycle Services (LCS) megoldásból.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 75765c0cc03c64030fac6bc656f57a143828b85b
ms.sourcegitcommit: 48c39c0c0949fe48b3536d9d2d0e451d561ff5c6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2020
ms.locfileid: "3112452"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Kettős írás beállítása a Lifecycle Services modulból

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Ez a témakör azt mutatja be, hogyan lehet beállítani egy kettős írási kapcsolatot egy új Finance and Operations környezet és egy új Common Data Service környezet között a Microsoft Dynamics Lifecycle Services (LCS) megoldásból.

## <a name="prerequisites"></a>Előfeltételek

A kettős írási kapcsolatot csak akkor lehet létrehozni, ha Ön adminisztrátor.

+ Hozzáféréssel kell rendelkeznie a bérlőhöz.
+ Mind a Finance and Operations, mind a Common Data Service környezetek esetében adminisztrátornak kell lennie.

## <a name="set-up-a-dual-write-connection"></a>Kettős írási kapcsolat beállítása

A kettős írási kapcsolat beállításához kövesse az alábbi lépéseket.

1. Az LCS_ben lépjen a projektjére.
2. A **Konfigurálás** kiválasztásával új környezetet telepíthet.
3. Válassza ki a verziót. 
4. Válassza ki a topológiát. Ha csak egy topológia érhető el, akkor automatikusan ki van jelölve.
5. Hajtsa végre a **Telepítési beállítások** varázsló első lépéseit.
6. A **Common Data Service** lapon tegye a következők egyikét:

    - Ha már egy Common Data Service környezet létesítve van a bérlő számára, akkor kiválaszthatja azt.

        1. Állítsa a **Common Data Service** konfigurálása beállítást **Igen** értékre.
        2. Az **Elérhető környezetek** mezőben válassza ki azt a környezetet, amellyel integrálni szeretné a Finance and Operations-adatokat. A lista minden olyan környezetet tartalmaz, amelyen adminisztrátori jogosultságai vannak.
        3. Jelölje be az **Elfogadom** jelölőnégyzetet, annak jelzéséhez, hogy elfogadja-e a feltételeket.

        ![A Common Data Service lap, ha már egy Common Data Service környezet létesítve van a bérlő számára](../dual-write/media/lcs_setup_1.png)

    - Ha a bérlő még nem rendelkezik Common Data Service-környezettel, akkor az új környezet lesz létesítve.

        1. Állítsa a **Common Data Service** konfigurálása beállítást **Igen** értékre.
        2. Adja meg egy nevet a Common Data Service környezetnek.
        3. Válassza ki azt a régiót, amelybe a környezetet szeretné létesíteni.
        4. Válassza ki a környezetre vonatkozó alapértelmezett nyelvet és pénznemet.

            > [!NOTE]
            > Később nem módosíthatja a nyelvet és a pénznemet.

        5. Jelölje be az **Elfogadom** jelölőnégyzetet, annak jelzéséhez, hogy elfogadja-e a feltételeket.

        ![A Common Data Service lap, amikor a bérlő még nem rendelkezik Common Data Service-környezettel](../dual-write/media/lcs_setup_2.png)

7. Hajtsa végre a **Telepítési beállítások** varázsló fennmaradó lépéseit.
8. Miután a környezet állapota már **Telepített**, nyissa meg a környezeti részletek lapot. A **Common Data Service környezeti információ** szakasz az összekapcsolt Finance and Operations környezet és Common Data Service környezet nevét jeleníti meg.

    ![Common Data Service környezeti információ szakasz](../dual-write/media/lcs_setup_3.png)

9. A Finance and Operations környezethez tartozó adminisztrátornak be kell jelentkeznie a LCS-be, és ki kell választania a **CDS csatolása alkalmazásokhoz** hivatkozást az összekapcsolása befejezéséhez. A környezeti részletek lap az adminisztrátor kapcsolattartási adatait jeleníti meg.

    Az összekapcsolás befejezését követően a program frissíti a állapotot **Környezet-összekapcsolás sikeresen befejezve** értékre.

10. Az **Adatintegrációs** munkaterület megnyitásához a Finance and Operations környezetben és a rendelkezésre álló sablonok ellenőrzéséhez válassza a **CDS csatolása alkalmazásokhoz** lehetőséget.

    ![A CDS csatolása alkalmazásokhoz gomb a Common Data Service környezeti információ területen](../dual-write/media/lcs_setup_4.png)

> [!NOTE]
> A környezetek nem csatolhatók le az LCS használatával. Egy környezet kapcsolatának megszüntetése érdekében nyissa meg az **Adatintegráció** munkaterületet a Finance and Operations környezetben , majd válassza a **Csatolás megszüntetése** parancsot.
