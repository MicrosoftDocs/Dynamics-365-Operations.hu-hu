---
title: Költségvetési javaslatok engedélyezése (előzetes verzió)
description: Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a Költségvetési javaslat funkcióját a pénzügyi elemzésekben.
author: ShivamPandey-msft
ms.date: 07/24/2020
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
ms.openlocfilehash: 7e90a1a2f2a8e7808f03ce9a6ee58c027bd48d8d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818704"
---
# <a name="enable-budget-proposals-preview"></a>Költségvetési javaslatok engedélyezése (előzetes verzió)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a Költségvetési javaslat funkcióját a pénzügyi elemzésekben.

1. A Microsoft Dynamics Lifecycle Services (LCS) környezet lapjáról származó információk használatával csatlakozhat az Azure SQL elsődleges példányához az adott környezetben. Futtassa a következő Transact-SQL (T-SQL) parancsot a tesztkörnyezetben a teszteléshez kiadás bekapcsolásához. (Előfordulhat, hogy az LCS-ben be kell kapcsolnia az IP-cím hez való hozzáférést, mielőtt távolról csatlakozhatna az Application Object Server szolgáltatáshoz \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > Ha a Microsoft Dynamics 365 Finance központi telepítése egy Service Fabric üzemelő példány, kihagyhatja ezt a lépést. A pénzügyi elemzési csoportnak már be kellett kapcsolnia a tesztelés kiadását az Ön számára. Ha nem jelenik meg a funkció a **Funkciókezelési** munkaterületen, vagy ha problémát észlel, akkor küldjön e-mailt a [Pénzügyi elemzés alkalmazás előzetes verzió csoportnak](mailto:fiap@microsoft.com).

2. Nyissa meg a **Funkciókezelés** munkaterületet, és kövesse az alábbi lépéseket:

    1. Válassza a **Frissítések keresése** elemet.
    2. Keresse meg a **Költségvetési javaslat** lehetőséget, majd kapcsolja be a funkciót.

3. Nyissa meg a **Költségvetés \> Beállítás \> alapszintű költségvetés \> Költségvetési javaslat (előzetes verzió)**, és válassza a **Funkció engedélyezése** lehetőséget.

#### <a name="privacy-notice"></a>Adatvédelmi nyilatkozat
Az előzetes verziók (1) kevesebb adatvédelmi és biztonsági intézkedést alkalmazhatnak, mint a Dynamics 365 Finance and Operations szolgáltatás (2) és nem vonatkozik a szolgáltatásiszint-szerződés (SLA) ehhez a szolgáltatáshoz, (3) nem használhatók olyan személyes adatok vagy más adatok feldolgozásához, melyekhez törvényi vagy jogszabályi megfelelési követelmények tartoznak, és (4) korlátozott támogatás tartozik hozzá.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]