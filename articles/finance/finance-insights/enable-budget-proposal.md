---
title: Költségvetési javaslatok engedélyezése (előzetes verzió)
description: Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a Költségvetési javaslat funkcióját a pénzügyi elemzésekben.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 59cf40e8bf69734c5f3645997ff0b07c29d4f40e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995140"
---
# <a name="enable-budget-proposals-preview"></a><span data-ttu-id="e0e41-103">Költségvetési javaslatok engedélyezése (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="e0e41-103">Enable budget proposals (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="e0e41-104">Ez a témakör azt mutatja be, hogyan lehet bekapcsolni a Költségvetési javaslat funkcióját a pénzügyi elemzésekben.</span><span class="sxs-lookup"><span data-stu-id="e0e41-104">This topic explains how to turn on the Budget proposal feature in Finance Insights.</span></span>

1. <span data-ttu-id="e0e41-105">A Microsoft Dynamics Lifecycle Services (LCS) környezet lapjáról származó információk használatával csatlakozhat az Azure SQL elsődleges példányához az adott környezetben.</span><span class="sxs-lookup"><span data-stu-id="e0e41-105">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="e0e41-106">Futtassa a következő Transact-SQL (T-SQL) parancsot a tesztkörnyezetben a teszteléshez kiadás bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="e0e41-106">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="e0e41-107">(Előfordulhat, hogy az LCS-ben be kell kapcsolnia az IP-cím hez való hozzáférést, mielőtt távolról csatlakozhatna az Application Object Server szolgáltatáshoz \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="e0e41-107">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="e0e41-108">Ha a Microsoft Dynamics 365 Finance központi telepítése egy Service Fabric üzemelő példány, kihagyhatja ezt a lépést.</span><span class="sxs-lookup"><span data-stu-id="e0e41-108">If your deployment of Microsoft Dynamics 365 Finance is a Service Fabric deployment, you can skip this step.</span></span> <span data-ttu-id="e0e41-109">A pénzügyi elemzési csoportnak már be kellett kapcsolnia a tesztelés kiadását az Ön számára.</span><span class="sxs-lookup"><span data-stu-id="e0e41-109">The Finance Insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="e0e41-110">Ha nem jelenik meg a funkció a **Funkciókezelési** munkaterületen, vagy ha problémát észlel, akkor küldjön e-mailt a [Pénzügyi elemzés alkalmazás előzetes verzió csoportnak](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e0e41-110">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, send email to the [Finance Insights App Preview team](mailto:fiap@microsoft.com).</span></span>

2. <span data-ttu-id="e0e41-111">Nyissa meg a **Funkciókezelés** munkaterületet, és kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="e0e41-111">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="e0e41-112">Válassza a **Frissítések keresése** elemet.</span><span class="sxs-lookup"><span data-stu-id="e0e41-112">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="e0e41-113">Keresse meg a **Költségvetési javaslat** lehetőséget, majd kapcsolja be a funkciót.</span><span class="sxs-lookup"><span data-stu-id="e0e41-113">Search for **Budget proposal**, and turn on that feature.</span></span>

3. <span data-ttu-id="e0e41-114">Nyissa meg a **Költségvetés \> Beállítás \> alapszintű költségvetés \> Költségvetési javaslat (előzetes verzió)**, és válassza a **Funkció engedélyezése** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="e0e41-114">Go to **Budgeting \> Setup \> basic Budgeting \> Budget proposal (preview)**, and select **Enable feature**.</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="e0e41-115">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="e0e41-115">Privacy notice</span></span>
<span data-ttu-id="e0e41-116">Az előzetes verziók (1) kevesebb adatvédelmi és biztonsági intézkedést alkalmazhatnak, mint a Dynamics 365 Finance and Operations szolgáltatás (2) és nem vonatkozik a szolgáltatásiszint-szerződés (SLA) ehhez a szolgáltatáshoz, (3) nem használhatók olyan személyes adatok vagy más adatok feldolgozásához, melyekhez törvényi vagy jogszabályi megfelelési követelmények tartoznak, és (4) korlátozott támogatás tartozik hozzá.</span><span class="sxs-lookup"><span data-stu-id="e0e41-116">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>
