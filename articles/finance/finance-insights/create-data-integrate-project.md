---
title: Adatintegrációs projekt létrehozása (előzetes verzió)
description: Ez a témakör bemutatja, hogyan hozhat létre adatintegrációs projektet.
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
ms.openlocfilehash: 9ecf6ef7b7f052ebbb1201dcd04a7431f5b72ce5
ms.sourcegitcommit: b64c52d85aa6f110f3b1959a5521637dd8631b5b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/07/2021
ms.locfileid: "5867447"
---
# <a name="create-a-data-integrator-project-preview"></a><span data-ttu-id="95b33-103">Adatintegrációs projekt létrehozása (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="95b33-103">Create a data integrator project (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="95b33-104">Ez a témakör bemutatja, hogyan hozhat létre adatintegrációs projektet.</span><span class="sxs-lookup"><span data-stu-id="95b33-104">This topic explains how to create a data integrator project.</span></span>

1. <span data-ttu-id="95b33-105">Jelentkezzen be a Microsoft Dynamics 365 Finance szolgáltatásba.</span><span class="sxs-lookup"><span data-stu-id="95b33-105">Sign in to Microsoft Dynamics 365 Finance.</span></span>
2. <span data-ttu-id="95b33-106">Menjen a **Munkaterületek \> Adatkezelés** pontra, és válassza az **Adatentitások** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95b33-106">Go to **Workspaces \> Data management**, and select **Data entities**.</span></span> <span data-ttu-id="95b33-107">Várja meg, amíg az összes adatentitás frissül, mielőtt továbblépne a következő lépésre.</span><span class="sxs-lookup"><span data-stu-id="95b33-107">Wait until all the data entities have been refreshed before you move on to the next step.</span></span>
3. <span data-ttu-id="95b33-108">Nyissa meg a [Power Apps-portált](https://make.powerapps.com/), és kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="95b33-108">Open the [Power Apps portal](https://make.powerapps.com/), and follow these steps:</span></span>

    1. <span data-ttu-id="95b33-109">Válassza ki a megfelelő környezetet.</span><span class="sxs-lookup"><span data-stu-id="95b33-109">Select the appropriate environment.</span></span>
    2. <span data-ttu-id="95b33-110">A bal oldali navigációs ablakban válassza ki az **Adat \> kapcsolatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95b33-110">In the left navigation pane, select **Data \> Connections**.</span></span>
    3. <span data-ttu-id="95b33-111">Csatlakozzon a következő elemek megfelelő példányaihoz:</span><span class="sxs-lookup"><span data-stu-id="95b33-111">Connect to appropriate instances of the following items:</span></span>

        - <span data-ttu-id="95b33-112">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="95b33-112">Dynamics 365</span></span>
        - <span data-ttu-id="95b33-113">Dynamics 365 for Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="95b33-113">Dynamics 365 for Fin & Ops</span></span>

4. <span data-ttu-id="95b33-114">Nyissa meg a [Power Apps környezetet](https://admin.powerapps.com/environments), és kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="95b33-114">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>

    1. <span data-ttu-id="95b33-115">Válassza az **Adatintegrátor** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95b33-115">Select **Data Integrator**.</span></span>
    2. <span data-ttu-id="95b33-116">Válassza ki a **Csatlakozókészletek** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95b33-116">Select **Connection sets**.</span></span>
    3. <span data-ttu-id="95b33-117">Válassza ki az **Új csatlakozókészlet** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95b33-117">Select **New connection set**.</span></span>
    4. <span data-ttu-id="95b33-118">Adja meg a csatlakozás nevét.</span><span class="sxs-lookup"><span data-stu-id="95b33-118">Enter a name for the connection.</span></span>
    5. <span data-ttu-id="95b33-119">Válassza ki a megfelelő kapcsolatokat a következő elemekhez:</span><span class="sxs-lookup"><span data-stu-id="95b33-119">Select the appropriate connections for the following items:</span></span>

        - <span data-ttu-id="95b33-120">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="95b33-120">Dynamics 365</span></span>
        - <span data-ttu-id="95b33-121">Dynamics 365 for Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="95b33-121">Dynamics 365 for Fin & Ops</span></span>

    6. <span data-ttu-id="95b33-122">Válassza ki a megfelelő szervezeti leképezést.</span><span class="sxs-lookup"><span data-stu-id="95b33-122">Select the appropriate organization mapping.</span></span>
    7. <span data-ttu-id="95b33-123">Válassza a **Létrehozása** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="95b33-123">Select **Create**.</span></span>

5. <span data-ttu-id="95b33-124">Nyissa meg a [Power Apps környezetet](https://admin.powerapps.com/environments), és kövesse az alábbi lépéseket:</span><span class="sxs-lookup"><span data-stu-id="95b33-124">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>  

    1. <span data-ttu-id="95b33-125">Az imént létrehozott kapcsolatkészlet használatával adatintegrációs projekteket hozhat létre a következő sablonokhoz:</span><span class="sxs-lookup"><span data-stu-id="95b33-125">Create data integration projects for the following templates by using the connection set that you just created:</span></span>

        - <span data-ttu-id="95b33-126">Az ügyfelek fizetési információinak eredményei (CDS to Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="95b33-126">Customer payment insights results (CDS to Fin and Ops)</span></span>
            - <span data-ttu-id="95b33-127">Ha a 10.0.17-es vagy újabb verziót használja, akkor az ügyfélkifizetések eredményének megfelelő sablont (CDS to Fin and Ops 10.0.17+) kell használnia.</span><span class="sxs-lookup"><span data-stu-id="95b33-127">If you are using version 10.0.17 or later, you need to use the template named, Customer payment insights result (CDS to Fin and Ops 10.0.17+).</span></span>
        - <span data-ttu-id="95b33-128">Készpénzáramlási idősorozatok eredményei (CDS to Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="95b33-128">Cash flow time series results (CDS to Fin and Ops)</span></span>
        - <span data-ttu-id="95b33-129">Költség idősorozatok eredményei (CDS to Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="95b33-129">Budget time series results (CDS to Fin and Ops)</span></span>

    2. <span data-ttu-id="95b33-130">Állítsa be a megfelelő ütemezést az egyes projektekhez.</span><span class="sxs-lookup"><span data-stu-id="95b33-130">Set the appropriate scheduling for each project.</span></span>

> [!NOTE]
> <span data-ttu-id="95b33-131">Ha nem látja a szükséges entitásokat a CDS-ben, válassza a **Követelések és beszedések > Beállítás > Pénzügyi információk > Pénzügyi információk paraméterei** lehetőséget, engedélyezze az Ügyfélfizetési előrejelzések funkciót, és kattintson az **Előrejelzési modell létrehozása** gombra.</span><span class="sxs-lookup"><span data-stu-id="95b33-131">If you do not see the required entities in CDS, please go to **Credit and collections > Setup > Finance Insights > Finance insights parameters**, enable Customer payment predictions feature and click on **Create prediction model** button.</span></span> <span data-ttu-id="95b33-132">Ha az AI-modell telepítése befejeződött (sikeres vagy sikertelen), az integráció létrehozásához szükséges CDS-entitások a CDS-ben lesznek telepítve.</span><span class="sxs-lookup"><span data-stu-id="95b33-132">When the deployment of AI model is completed (successful or failed), the CDS entities needed to create integration will be deployed in CDS.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="95b33-133">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="95b33-133">Privacy notice</span></span>

<span data-ttu-id="95b33-134">Az előzetes verziók (1) kevesebb adatvédelmi és biztonsági intézkedést alkalmazhatnak, mint a Dynamics 365 Finance and Operations szolgáltatás (2) és nem vonatkozik a szolgáltatásiszint-szerződés (SLA) ehhez a szolgáltatáshoz, (3) nem használhatók olyan személyes adatok vagy más adatok feldolgozásához, melyekhez törvényi vagy jogszabályi megfelelési követelmények tartoznak, és (4) korlátozott támogatás tartozik hozzá.</span><span class="sxs-lookup"><span data-stu-id="95b33-134">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
