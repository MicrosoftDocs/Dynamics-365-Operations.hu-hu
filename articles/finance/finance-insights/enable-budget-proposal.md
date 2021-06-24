---
title: Költségvetési javaslatok engedélyezése (előzetes verzió)
description: Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a Költségvetési javaslat funkcióját a pénzügyi elemzésekben.
author: ShivamPandey-msft
ms.date: 06/03/2021
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
ms.openlocfilehash: 948a3e051e5964c5c773cefd90c8587cf833a450
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222534"
---
# <a name="enable-budget-proposals-preview"></a><span data-ttu-id="0abc8-103">Költségvetési javaslatok engedélyezése (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="0abc8-103">Enable budget proposals (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="0abc8-104">Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a Költségvetési javaslat funkcióját a pénzügyi elemzésekben.</span><span class="sxs-lookup"><span data-stu-id="0abc8-104">This topic explains how to turn on the Budget proposal feature in Finance Insights.</span></span>

1. <span data-ttu-id="0abc8-105">A Microsoft Dynamics Lifecycle Services (LCS) környezet lapjáról származó információk használatával csatlakozhat az Azure SQL elsődleges példányához az adott környezetben.</span><span class="sxs-lookup"><span data-stu-id="0abc8-105">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="0abc8-106">Futtassa a következő Transact-SQL (T-SQL) parancsot a tesztkörnyezetben a teszteléshez kiadás bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="0abc8-106">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="0abc8-107">(Előfordulhat, hogy az LCS-ben be kell kapcsolnia az IP-cím hez való hozzáférést, mielőtt távolról csatlakozhatna az Application Object Server szolgáltatáshoz \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="0abc8-107">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="0abc8-108">Hagyja ki ezt a lépést, ha a 10.0.20-as vagy újabb verziót használja, vagy ha Service Fabric-telepítést használ.</span><span class="sxs-lookup"><span data-stu-id="0abc8-108">Skip this step if you're using version 10.0.20 or later, or if you're using a Service Fabric deployment.</span></span> <span data-ttu-id="0abc8-109">A pénzügyi elemzési csoportnak már be kellett kapcsolnia a tesztelés kiadását az Ön számára.</span><span class="sxs-lookup"><span data-stu-id="0abc8-109">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="0abc8-110">Ha nem látja a funkciót a **Funkciókezelés** munkaterületen, vagy ha problémákat tapasztal, amikor megpróbálja bekapcsolni, keressen fel minket: <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="0abc8-110">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span>

2. <span data-ttu-id="0abc8-111">Nyissa meg a **Funkciókezelés** munkaterületet, és kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="0abc8-111">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="0abc8-112">Válassza a **Frissítések keresése** elemet.</span><span class="sxs-lookup"><span data-stu-id="0abc8-112">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="0abc8-113">Keresse meg a **Költségvetési javaslat** lehetőséget, majd kapcsolja be a funkciót.</span><span class="sxs-lookup"><span data-stu-id="0abc8-113">Search for **Budget proposal**, and turn on that feature.</span></span>

3. <span data-ttu-id="0abc8-114">Nyissa meg a **Költségvetés \> Beállítás \> alapszintű költségvetés \> Költségvetési javaslat (előzetes verzió)**, és válassza a **Funkció engedélyezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0abc8-114">Go to **Budgeting \> Setup \> basic Budgeting \> Budget proposal (preview)**, and select **Enable feature**.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
