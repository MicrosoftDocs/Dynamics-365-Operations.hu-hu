---
title: Kettős írás beállítása a Lifecycle Services szolgáltatásból
description: Ez a témakör bemutatja, hogyan lehet kettős írású kapcsolatot beállítani a Microsoft Dynamics Lifecycle Services (LCS) szolgáltatásból.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 6971c8e2d5fa03c2991b9a3054c638cff6322c8b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567720"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Kettős írás beállítása a Lifecycle Services szolgáltatásból

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ez a témakör azt mutatja be, hogyan lehet beállítani egy kettős írási kapcsolatot egy új Finance and Operations környezet és egy új Dataverse környezet között a Microsoft Dynamics Lifecycle Services (LCS) megoldásból.

## <a name="prerequisites"></a>Előfeltételek

A kettős írási kapcsolatot csak akkor lehet létrehozni, ha Ön adminisztrátor.

+ Hozzáféréssel kell rendelkeznie a bérlőhöz.
+ Mind a Finance and Operations, mind a Dataverse környezetek esetében adminisztrátornak kell lennie.

## <a name="set-up-a-dual-write-connection"></a>Kettős írási kapcsolat beállítása

A kettős írási kapcsolat beállításához kövesse az alábbi lépéseket.

1. Az LCS_ben lépjen a projektjére.
2. A **Konfigurálás** kiválasztásával új környezetet telepíthet.
3. Válassza ki a verziót. 
4. Válassza ki a topológiát. Ha csak egy topológia érhető el, akkor automatikusan ki van jelölve.
5. Hajtsa végre a **Telepítési beállítások** varázsló első lépéseit.
6. A **Dataverse** lapon tegye a következők egyikét:

    - Ha már egy Dataverse környezet létesítve van a bérlő számára, akkor kiválaszthatja azt.

        1. Állítsa a **Dataverse** konfigurálása beállítást **Igen** értékre.
        2. Az **Elérhető környezetek** oszlopban válassza ki azt a környezetet, amellyel integrálni szeretné a Finance and Operations-adatokat. A lista minden olyan környezetet tartalmaz, amelyen adminisztrátori jogosultságai vannak.
        3. Jelölje be az **Elfogadom** jelölőnégyzetet, annak jelzéséhez, hogy elfogadja-e a feltételeket.

        ![A Dataverse lap, ha már egy Dataverse környezet létesítve van a bérlő számára](../dual-write/media/lcs_setup_1.png)

    - Ha a bérlő még nem rendelkezik Dataverse-környezettel, akkor az új környezet lesz létesítve.

        1. Állítsa a **Dataverse** konfigurálása beállítást **Igen** értékre.
        2. Adja meg egy nevet a Dataverse környezetnek.
        3. Válassza ki azt a régiót, amelybe a környezetet szeretné létesíteni.
        4. Válassza ki a környezetre vonatkozó alapértelmezett nyelvet és pénznemet.

            > [!NOTE]
            > Később nem módosíthatja a nyelvet és a pénznemet.

        5. Jelölje be az **Elfogadom** jelölőnégyzetet, annak jelzéséhez, hogy elfogadja-e a feltételeket.

        ![A Dataverse lap, amikor a bérlő még nem rendelkezik Dataverse-környezettel](../dual-write/media/lcs_setup_2.png)

7. Hajtsa végre a **Telepítési beállítások** varázsló fennmaradó lépéseit.
8. Miután a környezet állapota már **Telepített**, nyissa meg a környezeti részletek lapot. Az **Power Platform Integráció** szakasz az összekapcsolt Finance and Operations környezet és Dataverse környezet nevét jeleníti meg.

    ![Power Platform Integráció szakasz](../dual-write/media/lcs_setup_3.png)

9. A Finance and Operations környezethez tartozó adminisztrátornak be kell jelentkeznie a LCS-be, és ki kell választania a **CDS csatolása alkalmazásokhoz** hivatkozást az összekapcsolása befejezéséhez. A környezeti részletek lap az adminisztrátor kapcsolattartási adatait jeleníti meg.

    Az összekapcsolás befejezését követően a program frissíti a állapotot **Környezet-összekapcsolás sikeresen befejezve** értékre.

10. Az **Adatintegrációs** munkaterület megnyitásához a Finance and Operations környezetben és a rendelkezésre álló sablonok ellenőrzéséhez válassza a **CDS csatolása alkalmazásokhoz** lehetőséget.

    ![A CDS csatolása alkalmazásokhoz gomb az Power Platform Integráció területen](../dual-write/media/lcs_setup_4.png)

> [!NOTE]
> A környezetek nem csatolhatók le az LCS használatával. Egy környezet kapcsolatának megszüntetése érdekében nyissa meg az **Adatintegráció** munkaterületet a Finance and Operations környezetben , majd válassza a **Csatolás megszüntetése** parancsot.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]