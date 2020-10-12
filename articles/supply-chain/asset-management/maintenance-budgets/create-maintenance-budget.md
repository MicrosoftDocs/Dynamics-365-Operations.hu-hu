---
title: Karbantartási költségvetések létrehozása
description: Ez a témakör azt mutatja be, hogyan lehet a karbantartási költségvetést létrehozni az Eszközkezelés modulban.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetBudgetLineAdjust, EntAssetBudget, EntAssetBudgetRecalc, EntAssetBudgetCopy, EntAssetBudgetLine, EntAssetBudgetCreate, EntAssetBudgetApprove, EntAssetBudgetCalculateActualCost
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2aaba8794bf0025f0449509752e4f197d3bf3db4
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889697"
---
# <a name="create-maintenance-budgets"></a>Karbantartási költségvetések létrehozása

[!include [banner](../../includes/banner.md)]

 



A karbantartási költségvetések a megelőző karbantartás várható költségeinek áttekintését szolgálják. A költségvetési sorok számítása a karbantartási ütemezési sorok alapján történik, amelyeknek a várható kezdési dátuma a költségvetési időszakra esik.

A karbantartási költségvetések alapját az Eszközkezeléshez használt költségtípusok jelentik: **Megelőző**, **Javító**és **Beruházás**. A beruházás karbantartás költségvetési költségei szerepelnek az olyan aktív eszközöknél, amelyek helyettesítési dátuma a költségvetési időszakban van, és van kapcsolódó helyettesítő értékük. A helyesbítő karbantartás költségvetési költségei akkor szerepelnek, ha a költségvetés-számításban szerepel egy múltbeli helyesbítő dátum. Ebben az esetben a korábbi időszak javító költségét ugyanarra a jövőbeli időszakra számítja ki a rendszer, amelyre a karbantartás költségvetését kiszámította.

## <a name="create-a-maintenance-budget"></a>Karbantartási költségvetés létrehozása

1. Válassza ki: **Eszközkezelés** \> **Lekérdezések** \> **Karbantartási költségvetés** \> **Költségvetés**.
2. Válassza a **Költségvetés létrehozása** elemet.
3. A **Karbantartási költségvetés** mezőbe írja be a költségvetés azonosítóját.
4. Adjon meg egy leírást a **Leírás** mezőben.
4. Az **Időszak** gyorslapon, a **Kezdő dátum** és a **Záró dátum** mezőkben, adja meg a költségvetési időszak kezdő és záró dátumát.
5. Az előző időszak tényleges költségei alapján kiszámított javító költségvetési költségek felvételéhez, a **Helyesbítő kezdő dátum** mezőbe írja be annak az időszaknak a kezdő dátumát, amelyből a költségeket figyelembe kell venni.
6. A költségvetésben szükséges részletességi szinttől függően adja meg a megfelelő beállításokat az öt **Csoport által** gyorslapon.
7. Válassza ki az **OK** lehetőséget.
8. Válassza ki a **Költségvetési sorok** lehetőséget a **Karbantartási költségvetési sorok** lap megnyitásához, amelyen megtekintheti az adott időszakra vonatkozóan létrehozott összes költségvetési sort.
9. A költségvetés jóváhagyásához jelölje ki a **Karbantartási költségvetések** lapon, majd válassza a **Jóváhagyás**parancsot. Ezután kattintson a **Költségvetési jóváhagyása** párbeszédpanelen az **OK**gombra. A név megadása az **Jóváhagyó** mezőben történik a **Karbantartási költségvetések** lapon.

    > [!NOTE]
    > A karbantartási költségvetés jóváhagyása után nem lehet újraszámolni vagy módosítani a kapcsolódó sorokat a **Karbantartás költségvetési sorok** lapon, hacsak nem törli a jóváhagyást. A karbantartási költségvetés jóváhagyásának visszavonásához jelölje ki a **Karbantartási költségvetések** lapon, majd válassza a **Jóváhagyás**parancsot. Ezután kattintson a **Költségvetési jóváhagyása** párbeszédpanelen az **OK**gombra.

![Karbantartási költségvetések](media/01-maintenance-budgets.png)

Új karbantartási költségvetés egy meglévő költségvetés másolásával is létrehozhat. A **Karbantartási költségvetések** lapon válassza ki a másolandó költségvetést, majd válassza a **Másolás**parancsot. Ez a megközelítés akkor lehet hasznos, ha például egy hónapra már létrehoztak egy költségvetést, és át szeretné másolni más hónapokra.

> [!NOTE]
> A karbantartási költségvetés csak a karbantartási ütemezés sorai alapján számítja ki a költségvetési költségeket. Ha ugyanarra az időszakra vonatkozóan szeretné kiszámítani a tényleges költségeket, akkor ezt az **Eszközköltség ellenőrzése** lapon teheti meg. 
