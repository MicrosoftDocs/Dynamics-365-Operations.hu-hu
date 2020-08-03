---
title: Forgatókönyv beállítása IoT Intelligencia esetén
description: Ez a témakör azt mutatja be, hogyan lehet beállítani egy forgatókönyvet a Supply Chain Management for IoT Intelligencia alkalmazásban.
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5633741fcd9c04b68e5b174447d7ead3c521ccd7
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597168"
---
# <a name="scenario-setup-for-iot-intelligence"></a><span data-ttu-id="244a0-103">Forgatókönyv beállítása IoT Intelligencia esetén</span><span class="sxs-lookup"><span data-stu-id="244a0-103">Scenario setup for IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="244a0-104">Ez a témakör azt mutatja be, hogyan lehet beállítani egy forgatókönyvet a Supply Chain Management for IoT Intelligencia alkalmazásban.</span><span class="sxs-lookup"><span data-stu-id="244a0-104">This topic describes how to configure a scenario in Supply Chain Management for IoT Intelligence.</span></span> <span data-ttu-id="244a0-105">A forgatókönyvek beállítása előtt [be kell állítania az LCS-t](iot-lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="244a0-105">Before you can setup the scenarios, you must [setup LCS](iot-lcs-setup.md).</span></span>

<span data-ttu-id="244a0-106">Ebben a témakörben konfigurálni fogja a **Berendezés üzemkimaradása** forgatókönyvet, hogy értesítést hozzon létre a Supply Chain Management alkalmazásban, amikor egy gép leáll.</span><span class="sxs-lookup"><span data-stu-id="244a0-106">In this topic, you will configure the **Equipment downtime** scenario to generate a notification in Supply Chain Management when a machine goes down.</span></span>

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a><span data-ttu-id="244a0-107">A **Berendezés üzemkimaradása** forgatókönyv konfigurálása a Supply Chain Management alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="244a0-107">Configure the **Equipment downtime** scenario in Supply Chain Management</span></span>

<span data-ttu-id="244a0-108">A **Berendezés üzemkimaradása** forgatókönyv egy darabkimenet jelet rendel a gép figyelmeztetési küszöbértékéhez.</span><span class="sxs-lookup"><span data-stu-id="244a0-108">The **Equipment downtime** scenario maps a part out signal to a machine alert threshold.</span></span> <span data-ttu-id="244a0-109">A gépet csak akkor figyeli a program, ha a forgatókönyvhöz ki van választva a gép, és a Supply Chain Management alkalmazásban való futtatására van beállítva.</span><span class="sxs-lookup"><span data-stu-id="244a0-109">The machine is monitored only when the machine is selected for the scenario and is set to running in Supply Chain Management.</span></span> <span data-ttu-id="244a0-110">Ha a géptől kapott utolsó darabkimeneti jel óta eltelt idő meghaladja a figyelmeztetési küszöbértéket, akkor a **Gép leállt** értesítés aktiválódik.</span><span class="sxs-lookup"><span data-stu-id="244a0-110">If the time since the machine’s last received Part Out signal is greater than the alert threshold, then a **Machine down** notification is triggered.</span></span> <span data-ttu-id="244a0-111">Ha a gép továbbra is fut, akkor a következő **PartOut** jel fogadásakor a **Gép üzemel** értesítés aktiválódik.</span><span class="sxs-lookup"><span data-stu-id="244a0-111">If the machine is still running, when the next **PartOut** signal is received a **Machine up** notification is triggered.</span></span> <span data-ttu-id="244a0-112">Ha egy gép 30 percen keresztül áll, egy új **Gép leállt** értesítés aktiválódik.</span><span class="sxs-lookup"><span data-stu-id="244a0-112">If a machine stays down for 30 mins a new **Machine down** notification is triggered.</span></span>

<span data-ttu-id="244a0-113">A **Berendezés üzemkimaradása** forgatókönyv az alábbi függőségekkel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="244a0-113">The **Equipment downtime** scenario has these dependencies:</span></span>

+ <span data-ttu-id="244a0-114">Egy termelési rendelésnek futnia kell egy leképezett gépen, hogy a figyelmeztetés aktiválódjon.</span><span class="sxs-lookup"><span data-stu-id="244a0-114">A production order must be running on a mapped machine for an alert to be triggered.</span></span>
+ <span data-ttu-id="244a0-115">A hozzárendelt gép darabkiadási jelét jelképező jelet kell küldeni az IoT-központnak egyedit tulajdonságnévvel.</span><span class="sxs-lookup"><span data-stu-id="244a0-115">A signal representing a mapped machine's part out signal must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="244a0-116">A Unix ezredmásodperces időbélyegnek szerepelnie kell az IoT-központnak küldött üzenetben.</span><span class="sxs-lookup"><span data-stu-id="244a0-116">A Unix milliseconds timestamp property must be present in the IoT hub message.</span></span>

<span data-ttu-id="244a0-117">A forgatókönyv konfigurálásához tegye a következőket:</span><span class="sxs-lookup"><span data-stu-id="244a0-117">To configure the scenario, follow these steps:</span></span>

1. <span data-ttu-id="244a0-118">Jelentkezzen be a Supply Chain Management alkalmazásba.</span><span class="sxs-lookup"><span data-stu-id="244a0-118">Log into Supply Chain Management.</span></span>
2. <span data-ttu-id="244a0-119">Engedélyezze az IoT Intelligencia funkció jelzőjét.</span><span class="sxs-lookup"><span data-stu-id="244a0-119">Enable the IoT Intelligence feature flag.</span></span> <span data-ttu-id="244a0-120">További tájékoztatás: [Funkciókezelés – áttekintés](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="244a0-120">For more information, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
3. <span data-ttu-id="244a0-121">Konfigurálja a mutatókat.</span><span class="sxs-lookup"><span data-stu-id="244a0-121">Configure the metrics.</span></span> <span data-ttu-id="244a0-122">További információ: [Mutatók konfigurálása](iot-metrics-setup.md#configure-metrics).</span><span class="sxs-lookup"><span data-stu-id="244a0-122">For more information, see [How to configure metrics](iot-metrics-setup.md#configure-metrics).</span></span>
4. <span data-ttu-id="244a0-123">Nyissa meg a **Gyártásvezérlés** részt.</span><span class="sxs-lookup"><span data-stu-id="244a0-123">Navigate to **Production control**.</span></span>
5. <span data-ttu-id="244a0-124">Keresse meg a **Beállítás \> IoT Intelligencia \> Forgatókönyvek kezelése** beállítást.</span><span class="sxs-lookup"><span data-stu-id="244a0-124">Navigate to **Setup \> IoT Intelligence \> Scenario management**.</span></span>
6. <span data-ttu-id="244a0-125">Kattintson a **Konfigurálás** lehetőségre a **Berendezés üzemkimaradása** csempe alatt.</span><span class="sxs-lookup"><span data-stu-id="244a0-125">Click **Configure** on the **Equipment downtime** tile.</span></span> <span data-ttu-id="244a0-126">A konfiguráló varázsló a elindítja a **Berendezés érzékelősémájának meghatározása** oldalt.</span><span class="sxs-lookup"><span data-stu-id="244a0-126">The configuration wizard starts with the **Equipment sensor schema definition** page.</span></span> <span data-ttu-id="244a0-127">A cél a Supply Chain Management sémájának beállítása, hogy megfeleljen az IoT-üzenetek JSON-formátumának.</span><span class="sxs-lookup"><span data-stu-id="244a0-127">The goal here is to setup the schema in Supply Chain Management to match the JSON format of the IoT messages.</span></span> <span data-ttu-id="244a0-128">Több üzenetséma is definiálható.</span><span class="sxs-lookup"><span data-stu-id="244a0-128">Multiple message schemas can be defined.</span></span> <span data-ttu-id="244a0-129">További tájékoztatás: [IoT-központ üzenetséma-formátumai](iot-schema-format.md).</span><span class="sxs-lookup"><span data-stu-id="244a0-129">For more information, see [Message schema formats for IoT Hub](iot-schema-format.md).</span></span> <span data-ttu-id="244a0-130">Ebben a példában az üzenet tartalma olyan üzenetköteget tartalmaz, amelyekben ilyen formátumú üzenetek szerepelnek:</span><span class="sxs-lookup"><span data-stu-id="244a0-130">In this example, the message payload contains a batch of messages with this format:</span></span>

    ```json
    {
        "timestamp": 1576016821614,
        "payload": [
            {
                "id": "IoTInt.Machine1225.PartOut",
                "timestamp": 1576016821614,
                "value": True
            },
            {
                "id": "IoTInt.Machine1226.PartOut",
                "timestamp": 1576016991616,
                "value": True
            }
        ]
    }
    ```

7. <span data-ttu-id="244a0-131">Adjon hozzá egy sort a táblához.</span><span class="sxs-lookup"><span data-stu-id="244a0-131">Add a row to the table.</span></span>

    1. <span data-ttu-id="244a0-132">A **Séma neve** beállítást állítsa **Azonosító** értékre.</span><span class="sxs-lookup"><span data-stu-id="244a0-132">Set the **Schema name** to **ID**.</span></span>
    2. <span data-ttu-id="244a0-133">A **Séma útvonala** beállítást állítsa **/payload[\*]/id** értékre.</span><span class="sxs-lookup"><span data-stu-id="244a0-133">Set the **Schema path** to **/payload[\*]/id**.</span></span>
    3. <span data-ttu-id="244a0-134">A **Leírás** számára adja meg az **Üzenet azonosítója** értéket.</span><span class="sxs-lookup"><span data-stu-id="244a0-134">Set the **Description** to **Message ID**.</span></span>

8. <span data-ttu-id="244a0-135">Adjon hozzá egy sort a táblához.</span><span class="sxs-lookup"><span data-stu-id="244a0-135">Add a row to the table.</span></span>

    1. <span data-ttu-id="244a0-136">A **Séma neve** beállítást állítsa **Időbélyeg** értékre.</span><span class="sxs-lookup"><span data-stu-id="244a0-136">Set the **Schema name** to **Timestamp**.</span></span>
    2. <span data-ttu-id="244a0-137">A **Séma útvonala** beállítást állítsa **/payload[\*]/timestamp** értékre.</span><span class="sxs-lookup"><span data-stu-id="244a0-137">Set the **Schema path** to **/payload[\*]/timestamp**.</span></span>
    3. <span data-ttu-id="244a0-138">A **Leírás** számára adja meg az **Üzenet időbélyege** értéket.</span><span class="sxs-lookup"><span data-stu-id="244a0-138">Set the **Description** to **Message timestamp**.</span></span>

9. <span data-ttu-id="244a0-139">Adjon hozzá egy sort a táblához.</span><span class="sxs-lookup"><span data-stu-id="244a0-139">Add a row to the table.</span></span>

    1. <span data-ttu-id="244a0-140">A **Séma neve** beállítást állítsa **Érték** értékre.</span><span class="sxs-lookup"><span data-stu-id="244a0-140">Set the **Schema name** to **Value**.</span></span>
    2. <span data-ttu-id="244a0-141">A **Séma útvonala** beállítást állítsa **/payload[\*]/value** értékre.</span><span class="sxs-lookup"><span data-stu-id="244a0-141">Set the **Schema path** to **/payload[\*]/value**.</span></span>
    3. <span data-ttu-id="244a0-142">A **Leírás** számára adja meg az **Üzenet értéke** értéket.</span><span class="sxs-lookup"><span data-stu-id="244a0-142">Set the **Description** to **Message value**.</span></span>

    <span data-ttu-id="244a0-143">Nem kell megadnia az üzenet összes tulajdonságát, csak a szükségeseket.</span><span class="sxs-lookup"><span data-stu-id="244a0-143">You don't need to define all the properties in the message, only the ones that you need.</span></span> <span data-ttu-id="244a0-144">Ebben a példában nem hozott létre sort a **Gyökér időbélyege** számára.</span><span class="sxs-lookup"><span data-stu-id="244a0-144">In this example, you did not create a row for **Root timestamp**.</span></span> <span data-ttu-id="244a0-145">A **Gyökér időbélyege** útvonala **/timestamp** lenne.</span><span class="sxs-lookup"><span data-stu-id="244a0-145">The path for **Root timestamp** would be **/timestamp**.</span></span>
  
10. <span data-ttu-id="244a0-146">Kattintson a **Következő** gombra a **Berendezés érzékelősémájának leképezése** oldalra lépéshez.</span><span class="sxs-lookup"><span data-stu-id="244a0-146">Click **Next** to go to the **Equipment sensor schema map** page.</span></span>
11. <span data-ttu-id="244a0-147">A **Berendezés erőforrás-azonosítója** sorban állítsa a **Séma neve** beállítást **Azonosító** értékre.</span><span class="sxs-lookup"><span data-stu-id="244a0-147">In the row for **Equipment resource ID** set the **Schema name** to **ID**.</span></span> <span data-ttu-id="244a0-148">Az érvényes értékek a legördülő táblázatban láthatók.</span><span class="sxs-lookup"><span data-stu-id="244a0-148">The valid values are displayed in a dropdown table.</span></span>
12. <span data-ttu-id="244a0-149">Az **UTC idő** sorában állítsa a **Séma neve** beállítást **Időbélyeg** értékre.</span><span class="sxs-lookup"><span data-stu-id="244a0-149">In the row for **UTC time** set the **Schema name** to **Timestamp**.</span></span> <span data-ttu-id="244a0-150">Az érvényes értékek a legördülő táblázatban láthatók.</span><span class="sxs-lookup"><span data-stu-id="244a0-150">The valid values are displayed in a dropdown table.</span></span>
13. <span data-ttu-id="244a0-151">A **Legyártott darab jel** sorban állítsa a **Séma neve** beállítást **Érték** értékre.</span><span class="sxs-lookup"><span data-stu-id="244a0-151">In the row for **Part produced signal** set the **Schema name** to **Value**.</span></span> <span data-ttu-id="244a0-152">Az érvényes értékek a legördülő táblázatban láthatók.</span><span class="sxs-lookup"><span data-stu-id="244a0-152">The valid values are displayed in a dropdown table.</span></span>
14. <span data-ttu-id="244a0-153">Kattintson a **Következő** gombra a **Berendezés erőforrás-azonosítójának konfigurációja** oldalon.</span><span class="sxs-lookup"><span data-stu-id="244a0-153">Click **Next** for the **Equipment resource ID configuration** page.</span></span>
15. <span data-ttu-id="244a0-154">Ebben a lépésben az IoT-központ üzenetének értékeit képezi le a Supply Chain Management erőforrásaira.</span><span class="sxs-lookup"><span data-stu-id="244a0-154">In this step, you map the IoT Hub message values to the Supply Chain Management resources.</span></span>

    1. <span data-ttu-id="244a0-155">A **Jeladatok értékei** táblázatban adjon hozzá egy új sort, és adja meg az **IoTInt.Machine1225.PartOut** értéket az **Érték** oszlopban.</span><span class="sxs-lookup"><span data-stu-id="244a0-155">In the **Signal Data Values** table, add a new row, and enter **IoTInt.Machine1225.PartOut** in the **Value** column.</span></span> <span data-ttu-id="244a0-156">Az **IoTInt.Machine1225.PartOut** érték az IoT-központ üzenetének JSON **azonosító** tulajdonságából származik.</span><span class="sxs-lookup"><span data-stu-id="244a0-156">The value **IoTInt.Machine1225.PartOut** comes from the JSON **id** property in the IoT hub message.</span></span>
    2. <span data-ttu-id="244a0-157">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="244a0-157">Click **Save**.</span></span>
    3. <span data-ttu-id="244a0-158">Az **Üzleti rekord leképezése** táblában kattintson az **Új** elemre.</span><span class="sxs-lookup"><span data-stu-id="244a0-158">In the **Business Record Mapping** table, click **New**.</span></span> <span data-ttu-id="244a0-159">Az **Üzleti rekordtípus** alapértelmezett értéke automatikusan ki van töltve, és nem szükséges módosítani azt.</span><span class="sxs-lookup"><span data-stu-id="244a0-159">The default value for the **Business record type** is autopopulated, and you don't need to change it.</span></span>
    4. <span data-ttu-id="244a0-160">Válassza ki az **Üzleti rekord** oszlopban azt a Supply Chain Management géperőforrást, amelyből ez a jel elküldésre került.</span><span class="sxs-lookup"><span data-stu-id="244a0-160">In the **Business record** column, select the Supple Chain Management machine resource this signal value is being sent from.</span></span>
    5. <span data-ttu-id="244a0-161">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="244a0-161">Click **Save**.</span></span>
    6. <span data-ttu-id="244a0-162">Ismételje meg ezeket a lépéseket, és adjon hozzá egy új üzletirekord-hozzárendelést a **Machine1226** esetében.</span><span class="sxs-lookup"><span data-stu-id="244a0-162">Repeat these steps, adding a new business record mapping for **Machine1226**.</span></span> <span data-ttu-id="244a0-163">A Supply Chain Management egyetlen rekordjához több jeladatértéket rendelhet hozzá.</span><span class="sxs-lookup"><span data-stu-id="244a0-163">You can map multiple signal data values to a single record in Supply Chain Management.</span></span>

16. <span data-ttu-id="244a0-164">A **Kiválasztott** oszlopban kiválaszthatja, hogy melyik gépeket szeretné feldolgozni.</span><span class="sxs-lookup"><span data-stu-id="244a0-164">Use the **Selected** column to choose which machines you want to process.</span></span> <span data-ttu-id="244a0-165">Nem kell minden jelértéket megadni, és nem kell kijelölnie az összes gépet.</span><span class="sxs-lookup"><span data-stu-id="244a0-165">You do not have to define all signal values and you do not have to select all machines.</span></span>
17. <span data-ttu-id="244a0-166">Kattintson a **Következő** gombra a **Legyártott darab jel konfigurációja** oldalon.</span><span class="sxs-lookup"><span data-stu-id="244a0-166">Click **Next** to go to the **Part produced signal configuration** page.</span></span>
18. <span data-ttu-id="244a0-167">A **Jeladatok értékei** táblában adjon hozzá egy sort, és adja meg az **Érték** számára az **Igaz** értéket.</span><span class="sxs-lookup"><span data-stu-id="244a0-167">In the **Signal Data Values** table, add a row, and set **Value** to **True**.</span></span> <span data-ttu-id="244a0-168">Az **Igaz** érték az IoT-központ üzenetének JSON **érték** tulajdonságából származik.</span><span class="sxs-lookup"><span data-stu-id="244a0-168">The value **True** comes from the JSON **value** property in the IoT hub message.</span></span> <span data-ttu-id="244a0-169">A forgatókönyvéhez annyi értéket adhat hozzá, amennyit csak szükséges.</span><span class="sxs-lookup"><span data-stu-id="244a0-169">You can add as many values as you need for your scenario.</span></span>
19. <span data-ttu-id="244a0-170">Kattintson a **Mentés** gombra.</span><span class="sxs-lookup"><span data-stu-id="244a0-170">Click **Save**.</span></span>
20. <span data-ttu-id="244a0-171">Kattintson a **Következő** gombra a **Berendezés üzemkimaradásának küszöbértéke** oldalra lépéshez.</span><span class="sxs-lookup"><span data-stu-id="244a0-171">Click **Next** to go to the **Equipment downtime threshold** page.</span></span> <span data-ttu-id="244a0-172">A felsorolt gépek a korábban a jelértékekre leképezett gépek.</span><span class="sxs-lookup"><span data-stu-id="244a0-172">The machines listed are the machines previously mapped to signal values.</span></span> <span data-ttu-id="244a0-173">Ebben a lépésben meghatároz egy küszöbértéket annak meghatározására, hogy a gép áll-e.</span><span class="sxs-lookup"><span data-stu-id="244a0-173">In this step, you define a threshold to determine if a machine is down.</span></span> <span data-ttu-id="244a0-174">Ha például a küszöb 10 értékre van állítva, akkor a Supply Chain Management egy értesítést generál, ha a gépről 10 percig nem érkezik darabkiadási üzenet.</span><span class="sxs-lookup"><span data-stu-id="244a0-174">For example, if you set the threshold to 10, Supply Chain Management generates a notification if there is no part out message from a machine for 10 minutes.</span></span>
21. <span data-ttu-id="244a0-175">Kattintson a **Következő** lehetőségre a **Forgatókönyv engedélyezése** oldalra lépéshez.</span><span class="sxs-lookup"><span data-stu-id="244a0-175">Click **Next** to go to the **Enable scenario** page.</span></span> <span data-ttu-id="244a0-176">Kapcsolja át a csúszkát a forgatókönyv engedélyezéséhez.</span><span class="sxs-lookup"><span data-stu-id="244a0-176">Toggle the slider to enable the scenario.</span></span>
22. <span data-ttu-id="244a0-177">Kattintson a **Befejezés** gombra.</span><span class="sxs-lookup"><span data-stu-id="244a0-177">Click **Finish**.</span></span>

<span data-ttu-id="244a0-178">A forgatókönyv beállítása befejeződött.</span><span class="sxs-lookup"><span data-stu-id="244a0-178">The scenario setup is complete.</span></span> <span data-ttu-id="244a0-179">Az IoT Intelligencia automatikusan elindítja a IoT-központ üzeneteinek feldolgozását.</span><span class="sxs-lookup"><span data-stu-id="244a0-179">IoT Intelligence will automatically start processing the IoT Hub messages.</span></span>

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a><span data-ttu-id="244a0-180">A **Termékminőség** forgatókönyv konfigurálása a Supply Chain Management alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="244a0-180">Configure the **Product quality** scenario in Supply Chain Management</span></span>

<span data-ttu-id="244a0-181">A **Termékminőség** forgatókönyv értesítést generál, ha egy cikk egyik attribútuma kívül esik a megadott tartományon.</span><span class="sxs-lookup"><span data-stu-id="244a0-181">The **Product quality** scenario generates a notification if an attribute of an item is outside a specified range.</span></span> <span data-ttu-id="244a0-182">Egy érzékelő például elküldheti az egyes cikkek súlyát az IoT-központhoz.</span><span class="sxs-lookup"><span data-stu-id="244a0-182">For example, a sensor could send the weight of each item to IoT Hub.</span></span> <span data-ttu-id="244a0-183">A Supply Chain Management alkalmazásban egy értesítés jön létre, ha a cikk túl nehéz vagy túl könnyű.</span><span class="sxs-lookup"><span data-stu-id="244a0-183">In Supply Chain Management, a notification would be generated if the item was too heavy or too light.</span></span>

<span data-ttu-id="244a0-184">A forgatókönyv a következő függőségekkel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="244a0-184">The scenario has these dependencies:</span></span>

+ <span data-ttu-id="244a0-185">A termelési rendelésnek egy leképezett gépen kell futnia, és egy olyan terméket kell előállítania, amely leképezett kötegattribútummal rendelkezik egy értesítés aktiválásához.</span><span class="sxs-lookup"><span data-stu-id="244a0-185">A Production Order must be running on a mapped machine and producing a product with a mapped batch attribute for an alert to be triggered.</span></span>
+ <span data-ttu-id="244a0-186">A kötegattribútumot jelképező jelet kell küldeni az IoT-központnak egyedit tulajdonságnévvel.</span><span class="sxs-lookup"><span data-stu-id="244a0-186">A signal representing the batch attribute must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="244a0-187">A Unix ezredmásodperces időbélyegnek szerepelnie kell az IoT-központnak küldött üzenetben.</span><span class="sxs-lookup"><span data-stu-id="244a0-187">A Unix milliseconds timestamp property must be present in the IoT Hub message.</span></span>

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a><span data-ttu-id="244a0-188">A **Termelési késések** forgatókönyv konfigurálása a Supply Chain Management alkalmazásban</span><span class="sxs-lookup"><span data-stu-id="244a0-188">Configure the **Production delays** scenario in Supply Chain Management</span></span>

<span data-ttu-id="244a0-189">A **Termelési késések** forgatókönyv értesítést generál, ha a termelési teljesítmény egy küszöbérték alá esik.</span><span class="sxs-lookup"><span data-stu-id="244a0-189">The **Production delays** scenario generates a notification if the production throughput falls below a threshold value.</span></span> <span data-ttu-id="244a0-190">Ebben a forgatókönyvben a **PartOut** jelet a rendszer elküldi az IoT-központhoz minden egyes legyártott tételnél.</span><span class="sxs-lookup"><span data-stu-id="244a0-190">In this scenario, a **PartOut** signal is sent to IoT Hub for each item produced.</span></span> <span data-ttu-id="244a0-191">A Supply Chain Management alkalmazásban a rendelési késés a termelési rendelés ütemezett futási idejének hossza, a termelni kívánt darabszám, a feladat eltelt futásideje és a fogadott **PartOut** jelek száma alapján kerül kiszámításra.</span><span class="sxs-lookup"><span data-stu-id="244a0-191">In Supply Chain Management, the order delay is calculated based on how long the production order is scheduled to run, how many items should be produced, how long the job has been running, and how many **PartOut** signals are received.</span></span> <span data-ttu-id="244a0-192">Ha a feladathoz tartozó **PartOut** jelek száma nem éri el a várt érték küszöbértékét, akkor egy késési értesítés jön létre.</span><span class="sxs-lookup"><span data-stu-id="244a0-192">A delay notification would be generated if the number of the **PartOut** signals for the job falls below the threshold value of the expected value.</span></span>

<span data-ttu-id="244a0-193">A forgatókönyv a következő függőségekkel rendelkezik:</span><span class="sxs-lookup"><span data-stu-id="244a0-193">The scenario has these dependencies:</span></span>

+ <span data-ttu-id="244a0-194">Egy termelési rendelésnek futnia kell egy leképezett gépen, hogy a figyelmeztetés aktiválódjon.</span><span class="sxs-lookup"><span data-stu-id="244a0-194">A Production Order must be running on a mapped machine for an alert to be triggered.</span></span>
+ <span data-ttu-id="244a0-195">A hozzárendelt gép darabkiadási jelét jelképező jelet kell küldeni az IoT-központnak egyedit tulajdonságnévvel.</span><span class="sxs-lookup"><span data-stu-id="244a0-195">A signal representing a mapped machine's part out signal must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="244a0-196">A Unix ezredmásodperces időbélyegnek szerepelnie kell az IoT-központnak küldött üzenetben.</span><span class="sxs-lookup"><span data-stu-id="244a0-196">A Unix milliseconds timestamp property must be present in the IoT Hub message.</span></span>

## <a name="how-to-disable-a-scenario"></a><span data-ttu-id="244a0-197">Forgatókönyv letiltása</span><span class="sxs-lookup"><span data-stu-id="244a0-197">How to disable a scenario</span></span>

<span data-ttu-id="244a0-198">Kövesse az alábbi lépéseket a forgatókönyv letiltásához:</span><span class="sxs-lookup"><span data-stu-id="244a0-198">To disable a scenario, follow these steps:</span></span>

1. <span data-ttu-id="244a0-199">A Supply Chain Management alkalmazásban lépjen a **Gyártásvezérlés \> Beállítás \> IoT Intelligencia \> Forgatókönyvek kezelése** lehetőségre.</span><span class="sxs-lookup"><span data-stu-id="244a0-199">In Supply Chain Management, navigate to **Production control \> Setup \> IoT Intelligence \> Scenario management**.</span></span>
2. <span data-ttu-id="244a0-200">Kattintson a forgatókönyv **Konfigurálás** lehetőségére.</span><span class="sxs-lookup"><span data-stu-id="244a0-200">Click **Configure** on the scenario.</span></span>
3. <span data-ttu-id="244a0-201">Kattintson a **Következő** gombra a varázsló utolsó lapjára lépéshez.</span><span class="sxs-lookup"><span data-stu-id="244a0-201">Click **Next** to get to the last wizard tab.</span></span>
4. <span data-ttu-id="244a0-202">Kapcsolja át a csúszkát a forgatókönyv letiltásához.</span><span class="sxs-lookup"><span data-stu-id="244a0-202">Toggle the slider to disable the scenario.</span></span>
