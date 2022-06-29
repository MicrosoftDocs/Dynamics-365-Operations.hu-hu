---
title: Munkarendelés elküldése
description: Ez a cikk bemutatja, hogyan lehet munkarendelést kiszállításra az Eszközkezelésben.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetScheduledExecution
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f78e8642715b0c3fd3d01e8072645ccd9c58d685
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016855"
---
# <a name="dispatch-work-order"></a>Munkarendelés elküldése

[!include [banner](../../includes/banner.md)]

 

Az **Elküldés** funkciót használva egy munkarendelést vagy munkarendelési feladatot ütemezhet egy dolgozóra.

1. Kattintson az **Eszközkezelés munkarendelések** > **–** > **Minden munkarendelés vagy** aktív **munkarendelés gombra**.

2. A listában válassza ki a munkarendelést.

3. Az **Általános** lapon kattintson az **Kiszállás** lehetőségre.

4. A **Munkarendelés ütemezése** párbeszédablakban válassza ki a dolgozót a **Dolgozó** mezőben.

5. Az **Ütemezési órák** mezőben be lehet szúrni a várható munkaórákat, ha a várhatót munkaórák eltérnek az előrejelzett óráktól.

6. Az **Ütemezett kezdés** mezőben szükség esetén módosíthatja a kezdő dátumot és időpontot.

7. Ha az ütemezési folyamat figyelembe veszi a más feladatokra már ütemezett erőforrásokra vonatkozó kapacitási korlátozásokat, akkor győződjön meg róla, hogy az **Eszköz**, **Segédeszköz** és **Dolgozó** váltógomb **Igen** értékű. Ha meg szeretné tekinteni az ütemezési folyamat részletes adatait megtekintéséhez válassza az **Igen** beállítást a **Részletes** váltógombnál. Ez azt jelenti, hogy az információs naplóban megjelennek a munkarendelésekhez és a karbantartási dolgozókhoz tartozó számított pontszámokkal kapcsolatos részletes információk.

8. Válassza az **igen** beállítást az **Ütemezés kihagyása** választógombnál, ha a naptárban a lezárt napokat figyelmen kívül szeretné hagyni (a következőkre vonatkozik eszköz, dolgozó és szerszámok). Válassza az **igen** beállítást az **Ütemezett végrehajtás figyelmen kívül hagyása** választógombon, ha figyelmen kívül hagyja azokat a korlátozásokat, amelyek ki lettek választva az ütemezéssel kapcsolatos munkarendelésen. 

    Az ütemezett végrehajtás beállításával kapcsolatos tudnivalókat lásd az [Ütemezett végrehajtás](../setup-for-work-orders/scheduled-execution.md) szakaszban.

9. Kattintson az **OK** gombra. A Munkarendelés életciklusállapotát automatikusan frissíti a program, hogy az **Ütemezett** életciklus állapotra, amely az **Eszközkezelés** > **Beállítás** > **Munkarendelések** > **Életciklus-modellek** helyen van meghatározva.

Az alábbi ábra egy példát mutat be a kiszállási beállításokra az **Ütemezett munkarendelés** párbeszédpanelen.

![1. ábra](media/04-work-order-scheduling.png)

[!NOTE]
Ha törölni szeretné az ütemezést egy munkarendelésen, akkor ezt úgy teheti meg, hogy a **Minden munkarendelés** alatt kijelöli a munkarendelést, majd az **Általános** lapon az **Ütemezés törlése** elemre kattint. Ne felejtse el manuálisan frissíteni a munkarendelés életciklus-állapotát, ha törli az ütemezést.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]