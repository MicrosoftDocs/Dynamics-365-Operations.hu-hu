---
title: Projektbecslés figyelmen kívül hagyása
description: Ez a témakör a projektbecslésének a befejezése után történő figyelmen kívül hagyással kapcsolatban tartalmaz tájékoztatást.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: eb323bdeb2a4701cdc9383b8da29e05a4cab107c
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410226"
---
# <a name="eliminate-a-project-estimate"></a>Projektbecslés figyelmen kívül hagyása

[!include [banner](../includes/banner.md)]

A projektbecslés nyújtja a projekthez becsült és ütemezett munka pénzügyi nézőpontját. Egy projekt becsléseivel akkor lehet dolgozni, ha társította azt egy becsült projekthez. Egy becsült projekt mindig egy létező projekten alapul, ugyanakkor több projekt is tartozhat egyetlen becsült projekthez. Csak rögzített árú és beruházási projektek csatolhatók becsült projektekhez, és ezeknek a projekteknek ugyanahhoz a projektcsoporthoz kell tartozniuk, mint a becsült projektnek.

Becsült projekt figyelmen kívül hagyásához annak késznek kell lennie. A következő lépések azt mutatják be, hogyan lehet egy becslést figyelmen kívül hagyni.

1. Ugorjon a **Projektvezetés és könyvelés** > **Minden projekt** pontra, és nyissa meg a projektet. 
2. A **Kezelés** lapon válassza ki a **Becsléseket**, és a **Becslés** lapon válassza a **Figyelmen kívül hagyás** elemet.
3. Az **Általános** lap **Becslés figyelmen kívül hagyása** lapján adja meg a következő beállításokat:

   - **Időszakkód**: Válassza ki a kiválasztani kívánt becsült projekteknek megfelelő időszakkódot. 
   - **Becslés dátuma**: Válassza ki az eltávolítás megfelelő becsült dátumát.
   - **Eltávolítás befejezetlen termelés figyelmeztetésekkel**: Engedélyezze ezt a beállítást, ha folyamatban lévő munkához társított becslést szeretne figyelmen kívül hagyni. Ha ez a beállítás nincs engedélyezve, akkor az eltávolítás nem folytatódhat, ha nem becsült tranzakció létezik. 
   > [!NOTE]
   > Ez a beállítás csak akkor érhető el, ha az eltávolítást egy becsült projektre alkalmazza a program. Nem érhető el, ha ismétlődő feladásokat használ. Ez a beállítás a **Projekt paraméterei** oldal **Becslés** lapjának beállításaival működik, az **Eltávolítás engedélyezése, amikor nem becsült tranzakciók léteznek** mezőcsoportban.
   - **Állapot befejezettre állítása**: Engedélyezze ezt a lehetőséget, ha a becslési projektnek az eltávolítás futtatása után **Befejezett** értékre szeretné állítani az állapotát.
   - **Becsléslista nyomtatása**: Válassza ki, hogy mely adatokat nyomtassa ki a program a becsléslista nyomtatásakor.
   - **Információs napló megjelenítése** : Engedélyezze ezt a beállítást az információs napló megjelenítéséhez.
   - **Feladás dátuma** : Válassza ki a becslés főkönyvi feladási dátumát.

4.  Válassza ki az **OK** lehetőséget.
5. Az eltávolítási folyamat befejezése után az eltávolított becsült projekt negatív értékkel jelenik meg. 

Ha nem szándékosan szűntetett meg egy becslést, akkor kiválaszthatja a megszűntetett becslést, majd az **Eltávolítás sztornírozása** lehetőséget.   
