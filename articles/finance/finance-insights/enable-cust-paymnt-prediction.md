---
title: Vevői fizetési előrejelzések engedélyezése (előzetes verzió)
description: Ez a témakör azt mutatja be, hogyan lehet bekapcsolni és konfigurálni a Vevői fizetési előrejelzések funkciót a pénzügyi elemzésekben.
author: ShivamPandey-msft
ms.date: 05/27/2020
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
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ecc3851cc91c8fe17a7582f2be06e84cf9bc2d83
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818656"
---
# <a name="enable-customer-payment-predictions-preview"></a><span data-ttu-id="0a7cc-103">Vevői fizetési előrejelzések engedélyezése (előzetes verzió)</span><span class="sxs-lookup"><span data-stu-id="0a7cc-103">Enable customer payment predictions (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="0a7cc-104">Ez a témakör azt mutatja be, hogyan lehet bekapcsolni és konfigurálni a Vevői fizetési előrejelzések funkciót a pénzügyi elemzésekben.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-104">This topic explains how to turn on and configure the Customer payment predictions feature in Finance insights.</span></span> <span data-ttu-id="0a7cc-105">A funkció bekapcsolását a **Funkciókezelés** munkaterületen kapcsolja be, és adja meg a konfigurációs beállításokat a **Pénzügyi elemzési paraméterek** lapon.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-105">You turn on the feature in the **Feature management** workspace and enter configuration settings on the **Financial insights parameters** page.</span></span> <span data-ttu-id="0a7cc-106">Ez a témakör olyan információkat is tartalmaz, amelyek segíthetnek a funkció hatékony használatában.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-106">This topic also includes information that can help you effectively use the feature.</span></span>

> [!NOTE]
> <span data-ttu-id="0a7cc-107">A következő lépések elvégzése előtt mindenképpen hajtsa végre az előfeltételeket a [Pénzügyi elemzések konfigurálása](configure-for-fin-insites.md) témakörben.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-107">Before you complete the following steps, be sure to complete the prerequisite steps in the [Configure for Finance insights](configure-for-fin-insites.md) topic.</span></span>

1. <span data-ttu-id="0a7cc-108">A Microsoft Dynamics Lifecycle Services (LCS) környezet lapjáról származó információk használatával csatlakozhat az Azure SQL elsődleges példányához az adott környezetben.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-108">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="0a7cc-109">Futtassa a következő Transact-SQL (T-SQL) parancsot a tesztkörnyezetben a teszteléshez kiadás bekapcsolásához.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-109">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="0a7cc-110">(Előfordulhat, hogy az LCS-ben be kell kapcsolnia az IP-cím hez való hozzáférést, mielőtt távolról csatlakozhatna az Application Object Server szolgáltatáshoz \[AOS\].)</span><span class="sxs-lookup"><span data-stu-id="0a7cc-110">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED, PARTITION) VALUES ('PayPredEnableFeature', 1, 5637144576)`

    > [!NOTE]
    > <span data-ttu-id="0a7cc-111">Ha a Microsoft Dynamics 365 Finance központi telepítése egy Service Fabric üzemelő példány, kihagyhatja ezt a lépést.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-111">If your deployment of Microsoft Dynamics 365 Finance is a Service Fabric deployment, you can skip this step.</span></span> <span data-ttu-id="0a7cc-112">A pénzügyi elemzési csoportnak már be kellett kapcsolnia a tesztelés kiadását az Ön számára.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-112">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="0a7cc-113">Ha nem látja a funkciót a **Funkciókezelés** munkaterületen, vagy ha problémákat tapasztal, amikor megpróbálja bekapcsolni, keressen fel minket: <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-113">If you don't see the feature in the **Feature management** workspace, or if experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span>

2. <span data-ttu-id="0a7cc-114">Kapcsolja be az Ügyfél fizetési elemzés funkciót:</span><span class="sxs-lookup"><span data-stu-id="0a7cc-114">Turn on the Customer payment insights feature:</span></span>

    1. <span data-ttu-id="0a7cc-115">Lépjen a **Rendszerfelügyelet \> Munkaterületek \> Funkciókezelés** részre.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-115">Go to **System administration \> Workspaces \> Feature management**.</span></span>
    2. <span data-ttu-id="0a7cc-116">Keresse meg az **Ügyfél fizetési elemzés adatai (előzetes verzió)** nevű funkciót.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-116">Find the feature that is named **Customer payment insights (preview)**.</span></span>
    3. <span data-ttu-id="0a7cc-117">Válassza az **Engedélyezés most** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-117">Select **Enable now**.</span></span>

    <span data-ttu-id="0a7cc-118">Az Ügyfél fizetési elemzés funkciója be van kapcsolva, és készen áll a konfigurálásra.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-118">The Customer payment insights feature is now turned on and ready to be configured.</span></span>

3. <span data-ttu-id="0a7cc-119">Konfigurálja az Ügyfél fizetési elemzés funkciót:</span><span class="sxs-lookup"><span data-stu-id="0a7cc-119">Configure the Customer payment insights feature:</span></span>

    1. <span data-ttu-id="0a7cc-120">Nyissa meg a **Jóváírás és gyűjtemények \> Beállítás \> Pénzügyi elemzés \> Pénzügyi elemzés paraméterei** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-120">Go to **Credit and collections \> Setup \> Finance insights \> Finance insights parameters**.</span></span>

        <span data-ttu-id="0a7cc-121">[![A Pénzügyi elemzés paraméterei lap a funkció konfigurálása előtt](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)</span><span class="sxs-lookup"><span data-stu-id="0a7cc-121">[![Financial insights parameters page before the feature is configured](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)</span></span>

    2. <span data-ttu-id="0a7cc-122">A **Pénzügyi elemzési paraméterek** lap **Ügyfélfizetési elemzések** lapján válassza az **Előrejelzési modellhivatkozásban használt adatmezők megtekintése** lehetőséget az **Előrejelzési modell adatai** lap megnyitásához.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-122">On the **Financial insights parameters** page, on the **Customer payment insights** tab, select the **View the data fields used in the prediction model** link to open the **Data fields for prediction model** page.</span></span> <span data-ttu-id="0a7cc-123">Itt megtekintheti a mesterséges intelligencia (AI) előrejelzési modelljének létrehozásához használt mezők alapértelmezett listáját az ügyfelek fizetési előrejelzéseihez.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-123">There, you can view the default list of fields that are used to create the artificial intelligence (AI) prediction model for customer payment predictions.</span></span>

        <span data-ttu-id="0a7cc-124">Ha az előrejelzési modell létrehozásához az alapértelmezett mezőlistát szeretné használni, zárja be az **Előrejelzési modell adatmezői** lehetőséget, majd a **Pénzügyi elemzési paraméterek lapon** állítsa a **Szolgáltatás engedélyezése** beállítást **Igen** értékre.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-124">To use the default list of fields to create the prediction model, close the **Data fields for prediction model** page, and then, on the **Financial insights parameters** page, set the **Enable feature** option to **Yes**.</span></span>

    3. <span data-ttu-id="0a7cc-125">Adja meg a „nagyon későn” tranzakciós időszakot annak meghatározásához, hogy mit jelent a **Nagyon későn** előrejelzési gyűjtő a vállalkozás számára.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-125">Specify the "very late" transaction period to define what the **Very late** prediction bucket means for your business.</span></span>

        <span data-ttu-id="0a7cc-126">Minden nyitott számla esetében a rendszer három gyűjtőben jelzi előre meg a fizetés valószínűségét: **Időben**, **Későn** és **Nagyon későn**.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-126">For each open invoice, the system predicts the probability of payment in three buckets: **On time**, **Late**, and **Very late**.</span></span>

        - <span data-ttu-id="0a7cc-127">**Időben** – Ez a gyűjtő olyan kifizetéseket tartalmaz, amelyek előre jelzett kifizetése a tranzakció esedékességi dátumán vagy előtte történik.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-127">**On time** – This bucket includes payments that are predicted to be paid on or before the transaction due date.</span></span>
        - <span data-ttu-id="0a7cc-128">**Későn** – Ez a gyűjtő olyan kifizetéseket tartalmaz, amelyek a tranzakció esedékességi dátuma után, de a „nagyon késő” tranzakciós időszak kezdete előtt kerülnek kifizetésre.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-128">**Late** – This bucket includes payments that are predicted to be paid after the transaction due date but before the start of the "very late" transaction period.</span></span>
        - <span data-ttu-id="0a7cc-129">**Nagyon későn** – Ez a gyűjtő olyan kifizetéseket tartalmaz, amelyek a „nagyon késő” tranzakciós időszak kezdete után kerülnek kifizetésre.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-129">**Very late** – This bucket includes payments that are predicted to be paid after the start of the "very late" transaction period.</span></span>

        > [!NOTE]
        > <span data-ttu-id="0a7cc-130">Ha módosítja a „nagyon későn” tranzakciós időszakot, és a **Későn küszöbérték módosítása** lehetőséget választja a vevői kifizetések előrejelzési modelljének létrehozása után, a meglévő előrejelzési modell törlődik, és egy új modell jön létre.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-130">If you change the "very late" transaction period and select **Change late threshold** after the AI prediction model for customer payments has been created, the existing prediction model is deleted, and a new model is created.</span></span> <span data-ttu-id="0a7cc-131">Az új előrejelzési modell a tranzakciókat a „nagyon későn” időszakba mozgatja a definiáláshoz megadott beállítások alapján.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-131">The new prediction model will move transactions into the "very late" period, based on the settings that were entered to define it.</span></span>

    4. <span data-ttu-id="0a7cc-132">Miután befejezte a „nagyon későn” tranzakciós időszak definiálását, válassza az **Előrejelzési modell létrehozása** lehetőséget az előrejelzési modell létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-132">After you've finished defining the "very late" transaction period, select **Create prediction model** to create the prediction model.</span></span> <span data-ttu-id="0a7cc-133">Az **Előrejelzési modell** szakasz a **Pénzügyi elemzési paraméterek** lapon az előrejelzési modell állapotát mutatja.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-133">The **Prediction model** section on the **Financial insights parameters** page shows the status of the prediction model.</span></span>

        > [!NOTE]
        > <span data-ttu-id="0a7cc-134">Az előrejelzési modell létrehozása közben bármikor kiválaszthatja a **Modell létrehozásának visszaállítása** lehetőséget a folyamat újraindításához.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-134">At any time while the prediction model is being created, you can select **Reset model creation** to restart the process.</span></span>

    <span data-ttu-id="0a7cc-135">A funkció most már konfigurálva van, és készen áll a használatra.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-135">The feature has now been configured and is ready to be used.</span></span>

<span data-ttu-id="0a7cc-136">Miután a funkció be van kapcsolva és konfigurálva van, és az előrejelzési modell létrejött és működik, a **Pénzügyi elemzések paraméterei** lap **Előrejelzési modell** szakasza a modell pontosságát mutatja, ahogy az az alábbi ábrán is látható.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-136">After the feature has been turned on and configured, and the prediction model has been created and is working, the **Prediction model** section of the **Financial insights parameters** page shows the accuracy of the model, as shown in the following illustration.</span></span>

<span data-ttu-id="0a7cc-137">[![Az előrejelzési modell pontossága a Pénzügyi elemzési paraméterek oldalon](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)</span><span class="sxs-lookup"><span data-stu-id="0a7cc-137">[![Accuracy of the prediction model on the Financial insights parameters page](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)</span></span>

## <a name="release-details"></a><span data-ttu-id="0a7cc-138">Kiadás adatai</span><span class="sxs-lookup"><span data-stu-id="0a7cc-138">Release details</span></span>

<span data-ttu-id="0a7cc-139">A Finance Insights nyilvános előzetes verzió az Amerikai Egyesült Államokban, Európában és az Egyesült Királyságban is elérhető a próbaverzió telepítéshez.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-139">Finance insights public preview is available for trial deployments in the United States of America, Europe, and the United Kingdom.</span></span> <span data-ttu-id="0a7cc-140">A Microsoft fokozatosan adja hozzá a további régiók támogatását.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-140">Microsoft is incrementally adding support for more regions.</span></span>

<span data-ttu-id="0a7cc-141">A nyilvános előzetes verziójú funkciók csak 2. szintű tesztkörnyezetekben szabad bekapcsolni.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-141">Public preview features can and should be turned on only in Tier-2 sandbox environments.</span></span> <span data-ttu-id="0a7cc-142">A tesztkörnyezetben létrehozott telepítési és AI-modellek nem telepíthetők át éles környezetbe.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-142">Setup and AI models that are created in a sandbox environment can't be migrated to a production environment.</span></span> <span data-ttu-id="0a7cc-143">További információ: [A Microsoft Dynamics 365 előzetes verziók kiegészítő használati feltételei](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).</span><span class="sxs-lookup"><span data-stu-id="0a7cc-143">For more information, see [Supplemental Terms of Use for Microsoft Dynamics 365 Previews](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="0a7cc-144">Adatvédelmi nyilatkozat</span><span class="sxs-lookup"><span data-stu-id="0a7cc-144">Privacy notice</span></span>

<span data-ttu-id="0a7cc-145">Az előzetes verziók (1) kevesebb adatvédelmi és biztonsági intézkedést alkalmazhatnak, mint a Dynamics 365 Finance and Operations szolgáltatás (2) és nem vonatkozik a szolgáltatásiszint-szerződés (SLA) ehhez a szolgáltatáshoz, (3) nem használhatók olyan személyes adatok vagy más adatok feldolgozásához, melyekhez törvényi vagy jogszabályi megfelelési követelmények tartoznak, és (4) korlátozott támogatás tartozik hozzá.</span><span class="sxs-lookup"><span data-stu-id="0a7cc-145">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]