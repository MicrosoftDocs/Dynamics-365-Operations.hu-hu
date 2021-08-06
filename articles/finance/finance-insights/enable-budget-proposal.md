---
title: Költségvetési javaslatok engedélyezése (előzetes verzió)
description: Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a Költségvetési javaslat funkcióját a pénzügyi elemzésekben.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: d3fac4cbb80493c7cf94e3d9f4a4f544a749fb64
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638609"
---
# <a name="enable-budget-proposals-preview"></a>Költségvetési javaslatok engedélyezése (előzetes verzió)

[!include [banner](../includes/banner.md)]

Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a Költségvetési javaslat funkcióját a pénzügyi elemzésekben.

1. A Microsoft Dynamics Lifecycle Services (LCS) környezet lapjáról származó információk használatával csatlakozhat az Azure SQL elsődleges példányához az adott környezetben. Futtassa a következő Transact-SQL (T-SQL) parancsot a tesztkörnyezetben a teszteléshez kiadás bekapcsolásához. (Előfordulhat, hogy az LCS-ben be kell kapcsolnia az IP-cím hez való hozzáférést, mielőtt távolról csatlakozhatna az Application Object Server szolgáltatáshoz \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > Hagyja ki ezt a lépést, ha a 10.0.20-as vagy újabb verziót használja, vagy ha Service Fabric-telepítést használ. A pénzügyi elemzési csoportnak már be kellett kapcsolnia a tesztelés kiadását az Ön számára. Ha nem látja a funkciót a **Funkciókezelés** munkaterületen, vagy ha problémákat tapasztal, amikor megpróbálja bekapcsolni, keressen fel minket: <fiap@microsoft.com>.

2. Nyissa meg a **Funkciókezelés** munkaterületet, és kövesse az alábbi lépéseket:

    1. Válassza a **Frissítések keresése** elemet.
    2. Keresse meg a **Költségvetési javaslat** lehetőséget, majd kapcsolja be a funkciót.

3. Nyissa meg a **Költségvetés \> Beállítás \> alapszintű költségvetés \> Költségvetési javaslat (előzetes verzió)**, és válassza a **Funkció engedélyezése** lehetőséget.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
