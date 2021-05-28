---
title: Üzenetfeldolgozó üzenetei
description: Ez a témakör az üzenetfeldolgozó üzenetei funkcióval kapcsolatban tartalmaz tájékoztatást a skálázási egységgekkel kapcsolatos munkaterhelés esetén.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysMessageProcessorMessage, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 03d8cad743ac2b2b1e7b2832b8272ca3dbf5a163
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021055"
---
# <a name="message-processor-messages"></a><span data-ttu-id="68e6e-103">Üzenetfeldolgozó üzenetei</span><span class="sxs-lookup"><span data-stu-id="68e6e-103">Message processor messages</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="68e6e-104">Az üzenetfeldolgozó üzenetei a felhő- és peremalapú skálázási egységek futtatásakor használatosak a [gyártási munkaterhelések](cloud-edge-workload-manufacturing.md) és a [raktárkezelési munkaterhelések](cloud-edge-workload-warehousing.md) során.</span><span class="sxs-lookup"><span data-stu-id="68e6e-104">Message processor messages are used when running cloud and edge scale units for [manufacturing workloads](cloud-edge-workload-manufacturing.md) and [warehouse management workloads](cloud-edge-workload-warehousing.md).</span></span>

<span data-ttu-id="68e6e-105">Nagy mennyiségű adatcsere történik a központ és a skálázási egységek telepítési környezete között, hogy azok szinkronban legyenek, de az *üzenetfeldolgozó* ezek közül csak néhány adatcserét fog feldolgozni.</span><span class="sxs-lookup"><span data-stu-id="68e6e-105">A large amount of data is exchanged between the hub and scale unit deployment environments to keep them in sync, but only a few of these data exchanges will be processed by the *message processor*.</span></span> <span data-ttu-id="68e6e-106">Az üzenetfeldolgozó által feldolgozott üzeneteket a **Rendszerfelügyelet > Üzenetfeldolgozó > Üzenetfeldolgozó üzenetei** között lehet megtekinteni.</span><span class="sxs-lookup"><span data-stu-id="68e6e-106">You can view the messages processed by the message processor by going to **System administration > Message processor > Message processor messages**.</span></span>

## <a name="message-grid-columns-and-filters"></a><span data-ttu-id="68e6e-107">Üzenetrács oszlopai és szűrői</span><span class="sxs-lookup"><span data-stu-id="68e6e-107">Message grid columns and filters</span></span>

<span data-ttu-id="68e6e-108">Az **Üzenetfeldolgozó üzenetei** oldal tetején található mezők segítségével megkeresheti a keresett üzeneteket.</span><span class="sxs-lookup"><span data-stu-id="68e6e-108">You can use the fields at the top of the **Message processor messages** page to help find any particular messages you are looking for.</span></span> <span data-ttu-id="68e6e-109">A szűrők nagy része megfelel az üzenetrács oszlopcímeinek.</span><span class="sxs-lookup"><span data-stu-id="68e6e-109">Most of these filters match the column headings in the message grid.</span></span> <span data-ttu-id="68e6e-110">A következő szűrők és oszlopcímek érhetők el:</span><span class="sxs-lookup"><span data-stu-id="68e6e-110">The following filters and column headings are available:</span></span>

- <span data-ttu-id="68e6e-111">**Üzenettípus** – az üzenet típusát adja meg.</span><span class="sxs-lookup"><span data-stu-id="68e6e-111">**Message type** – Specifies the type of message.</span></span>
- <span data-ttu-id="68e6e-112">**Üzenet feldolgozási sora** – annak a feldolgozási sornak a nevét adja meg, amelyben az üzenetet fel kell feldolgozni.</span><span class="sxs-lookup"><span data-stu-id="68e6e-112">**Message queue** – Specifies the name of the queue in which the message is to be processed.</span></span> <span data-ttu-id="68e6e-113">A következő feldolgozási sorok vannak megadva:</span><span class="sxs-lookup"><span data-stu-id="68e6e-113">The following queues are provided:</span></span>
  - <span data-ttu-id="68e6e-114">*Skálázási egység–központ*</span><span class="sxs-lookup"><span data-stu-id="68e6e-114">*Scale unit to hub*</span></span>
  - <span data-ttu-id="68e6e-115">*Központ a raktárvégrehajtási skálázási egységhez*</span><span class="sxs-lookup"><span data-stu-id="68e6e-115">*Hub to warehouse execution scale unit*</span></span>
  - <span data-ttu-id="68e6e-116">*Központ a gyártásvégrehajtási skálázási egységhez*</span><span class="sxs-lookup"><span data-stu-id="68e6e-116">*Hub to manufacturing execution scale unit*</span></span>
- <span data-ttu-id="68e6e-117">**Üzenet állapota** – az üzenet állapotát adja meg.</span><span class="sxs-lookup"><span data-stu-id="68e6e-117">**Message state** – Specifies the state of the message.</span></span> <span data-ttu-id="68e6e-118">A következő állapotok léteznek:</span><span class="sxs-lookup"><span data-stu-id="68e6e-118">The following states exists:</span></span>
  - <span data-ttu-id="68e6e-119">*Feldolgozási sorban* – az üzenetfeldolgozó készen áll az üzenet feldolgozására.</span><span class="sxs-lookup"><span data-stu-id="68e6e-119">*Queued* – The message is ready to be processed by the message processor.</span></span>
  - <span data-ttu-id="68e6e-120">*Feldolgozva* – az üzenetfeldolgozó sikeresen elvégezte az üzenet feldolgozását.</span><span class="sxs-lookup"><span data-stu-id="68e6e-120">*Processed* – The message was successfully processed by the message processor.</span></span>
  - <span data-ttu-id="68e6e-121">*Megszakítva* – az üzenet feldolgozása megtörtént, de a feldolgozás nem sikerült.</span><span class="sxs-lookup"><span data-stu-id="68e6e-121">*Canceled* – The message was processed, but processing failed.</span></span>
- <span data-ttu-id="68e6e-122">**Üzenet tartalma** – Ezzel a szűrővel az üzenet tartalmának teljes szöveges keresését lehet végrehajtani.</span><span class="sxs-lookup"><span data-stu-id="68e6e-122">**Message content** – This filter does a full-text search of message content.</span></span> <span data-ttu-id="68e6e-123">(Az üzenet tartalma nem jelenik meg a rácsban.) A szűrő a különleges szimbólumokat (például „-”) szóközként kezeli, és az összes szóközkaraktert logikai VAGY operátorként kezeli.</span><span class="sxs-lookup"><span data-stu-id="68e6e-123">(Message content is not shown in the grid.) The filter treats most special symbols (such as "-") as spaces, and treats all space characters as Boolean OR operators.</span></span> <span data-ttu-id="68e6e-124">T=Ez azt jelenti például, hogy ha egy „USMF-123456” értékkel megegyező `journalid` értéket keres, a rendszer minden "USMF" vagy "123456" szövege tartalmazó üzenetet megtalál, amely valószínűleg hosszú lista.</span><span class="sxs-lookup"><span data-stu-id="68e6e-124">T=For example, this means if you search for a specific `journalid` value equal "USMF-123456", the system will find all messages that contain "USMF" or "123456", which is likely to be a long list.</span></span> <span data-ttu-id="68e6e-125">Így jobb, ha csak a "123456" ot adja meg, mivel ez konkrétabb eredményeket ad vissza.</span><span class="sxs-lookup"><span data-stu-id="68e6e-125">Therefore, it would be better to enter just "123456" alone because that will return more specific results.</span></span>

## <a name="example-message-type-request-inventory-adjustment-financial-update"></a><span data-ttu-id="68e6e-126">Példa üzenettípusra: Készletkorrekció pénzügyi frissítésének kérése</span><span class="sxs-lookup"><span data-stu-id="68e6e-126">Example message type: Request inventory adjustment financial update</span></span>

<span data-ttu-id="68e6e-127">Például a *Készletkorrekció pénzügyi frissítésének kérése* **üzenettípussal** lehet leltárnaplót létrehozni és feladni a központban, amikor egy dolgozó a raktári alkalmazás segítségével [készletkorrekciót regisztrál](cloud-edge-warehouse-inventory-adjustment.md) a skálaegység raktárkezelési munkaterhelésén.</span><span class="sxs-lookup"><span data-stu-id="68e6e-127">For example, the **Message type** *Request inventory adjustment financial update* is used to create and post a counting journal on the hub when a worker uses the warehouse app to [register an inventory adjustment](cloud-edge-warehouse-inventory-adjustment.md) on a scale unit warehouse management workload.</span></span> <span data-ttu-id="68e6e-128">Mivel ez a konkrét folyamat egy skálázási egységből származik, az **Üzenetsor** mezőben a megjelenő érték: *Skálázási egységből központba*.</span><span class="sxs-lookup"><span data-stu-id="68e6e-128">Because this specific process originates from a scale unit, the **Message queue** field will show the value *Scale unit to hub*.</span></span>

<span data-ttu-id="68e6e-129">Ehhez az üzenettípushoz a skálázási egység munkaterhelése a raktári alkalmazás készletkorrekciós műveletének részeként rögzíti az üzenetet.</span><span class="sxs-lookup"><span data-stu-id="68e6e-129">For this message type, a scale unit workload records the message as part of a warehouse app inventory adjustment operation.</span></span> <span data-ttu-id="68e6e-130">Az üzenetadatok ezután ugyanannak a folyamatnak a részeként kerülnek a központba, amely a [Commerce Data Exchange-architektúra](../../commerce/commerce-architecture.md) részeként használatos.</span><span class="sxs-lookup"><span data-stu-id="68e6e-130">The message data is then transferred to the hub as part of the same process used for the [Commerce data exchange architecture](../../commerce/commerce-architecture.md).</span></span> <span data-ttu-id="68e6e-131">Az üzenet módosul, és az **üzenet állapot** *Feldolgozási sorban* értékre változik.</span><span class="sxs-lookup"><span data-stu-id="68e6e-131">The message will be updated to show **Message state** as *Queued*.</span></span> <span data-ttu-id="68e6e-132">Az üzenetfeldolgozó ezután feldolgozhatja az üzenetet, és frissíti az **Üzenetállapot** beállítást *Feldolgozva* értékre siker esetén, vagy *Visszavonva* értékre sikertelenség esetén.</span><span class="sxs-lookup"><span data-stu-id="68e6e-132">The message processor then attempts to process the message and updates the **Message state** to *Processed* on success, or *Canceled* on failure.</span></span>

## <a name="view-the-message-log-message-content-and-details"></a><span data-ttu-id="68e6e-133">Az üzenetnaplónak, az üzenet tartalmának és részleteinek megtekintése</span><span class="sxs-lookup"><span data-stu-id="68e6e-133">View the message log, message content, and details</span></span>

<span data-ttu-id="68e6e-134">Az üzenetek részletes adatait úgy találhatja meg, hogy kijelöli azt a rácson, majd megnyitja az üzenetrács alatt található **Napló** vagy **Üzenettartalom** lapot, ahol megtekinthetők az egyes feldolgozási események.</span><span class="sxs-lookup"><span data-stu-id="68e6e-134">You can find detailed information about a message by selecting it in the grid and then opening the **Log** or **Message content** tabs under the message grid, where each processing event is shown.</span></span>

<span data-ttu-id="68e6e-135">Az **Üzenettartalom** az **Üzenettípus** értékétől függ, ezért eltérő szöveghosszúságú lesz.</span><span class="sxs-lookup"><span data-stu-id="68e6e-135">The **Message content** depends on the **Message type** and will therefore have different text length.</span></span> <span data-ttu-id="68e6e-136">Az üzenet egy jellemző szövege egy **{** szimbólummal kezdődik, és **}** szimbólummal végződiki, közte pedig mezőnevek szerepelnek, például `journalId`, majd egy **:**, és olyasmi értékek, mint *USMF-123456*.</span><span class="sxs-lookup"><span data-stu-id="68e6e-136">A typical message content text will start with a **{** and end with a **}** and in between have field names such as `journalId` followed by a **:** and a value such as *USMF-123456*.</span></span>

<span data-ttu-id="68e6e-137">A **Napló** lap eszköztára a következő gombokat tartalmazza:</span><span class="sxs-lookup"><span data-stu-id="68e6e-137">The toolbar on the **Log** tab includes the following buttons:</span></span>

- <span data-ttu-id="68e6e-138">**Napló** – A feldolgozás eredményeinek megjelenítése.</span><span class="sxs-lookup"><span data-stu-id="68e6e-138">**Log** – Displays the processing results.</span></span> <span data-ttu-id="68e6e-139">Ez különösen hasznos a sikertelen feldolgozás okainak megértéséhez, ha az üzenetnél a **Feldolgozás eredménye** *Sikertelen*.</span><span class="sxs-lookup"><span data-stu-id="68e6e-139">This is especially helpful for understanding the reasons for a processing failure for messages having a **Processing result** of *Failed*.</span></span>
- <span data-ttu-id="68e6e-140">**Csomag** – Több üzenetfeldolgozási művelet futhat ugyanazon kötegfolyamat részeként.</span><span class="sxs-lookup"><span data-stu-id="68e6e-140">**Bundle** – Multiple message processing operations can run as part of the same batch process.</span></span> <span data-ttu-id="68e6e-141">A részletes adatok megtekintéséhez kattintson erre a gombra.</span><span class="sxs-lookup"><span data-stu-id="68e6e-141">Select this button to view this detailed data.</span></span> <span data-ttu-id="68e6e-142">Például láthatja, hogy vannak-e függőségek, amelyeknél a rendszernek fel kell feldolgoznia bizonyos üzeneteket egy meghatározott sorrendben.</span><span class="sxs-lookup"><span data-stu-id="68e6e-142">For example, you can see whether dependencies exist that require the system to process certain messages in a specific sequence.</span></span>

## <a name="message-processor-batch-job"></a><span data-ttu-id="68e6e-143">Üzenetfeldolgozó kötegelt feladata</span><span class="sxs-lookup"><span data-stu-id="68e6e-143">Message processor batch job</span></span>

<span data-ttu-id="68e6e-144">Felhő- és peremhálózati telepítés futtatásakor a rendszer automatikusan elindítja az *Üzenetfeldolgozó* kötegelt feladatot, amikor új üzenetet hoznak létre feldolgozásra, így ezt a feladatot nem kell manuálisan ütemezni.</span><span class="sxs-lookup"><span data-stu-id="68e6e-144">When running a cloud and edge deployment, the *Message processor* batch job will automatically be evoked when a new message is created for processing, so you should not need to schedule this job manually.</span></span>

<span data-ttu-id="68e6e-145">Ha szükséges, a kötegelt feladathoz hozzáférhet a **Rendszerfelügyelet > Üzenetfeldolgozó > Üzenetfeldolgozó** pontban.</span><span class="sxs-lookup"><span data-stu-id="68e6e-145">If necessary, you can access the batch job by going to **System administration > Message  processor > Message processor**.</span></span>

## <a name="manually-process-or-cancel-a-message"></a><span data-ttu-id="68e6e-146">Üzenet manuális feldolgozása vagy visszavonása</span><span class="sxs-lookup"><span data-stu-id="68e6e-146">Manually process or cancel a message</span></span>

<span data-ttu-id="68e6e-147">Szükség esetén az üzenetek az aktuális állapottól függően manuálisan feldolgozhatók és visszavonhatók.</span><span class="sxs-lookup"><span data-stu-id="68e6e-147">If needed, you can manually process or cancel a message, depending on its current state.</span></span> <span data-ttu-id="68e6e-148">Ehhez jelölje ki az üzenetet a rácson, majd válassza a **Feldolgozás** vagy a **Mégse** lehetőséget a munkaablakban</span><span class="sxs-lookup"><span data-stu-id="68e6e-148">To do so, select the message in the grid and then select **Process** or **Cancel** on the Action Pane</span></span>

## <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a><span data-ttu-id="68e6e-149">Állítsa be az üzleti eseményeket, hogy sikertelen feldolgozási eredmények esetén riasztásokat küldjenek</span><span class="sxs-lookup"><span data-stu-id="68e6e-149">Set up business events to deliver alerts for failed processing results</span></span>

<span data-ttu-id="68e6e-150">A sikertelen üzenetek lekérdezéséhez az **Üzenetállapot** *Visszavonva* értékére való szűrés mellett beállíthat [Üzleti eseményeket](../../fin-ops-core/dev-itpro/business-events/home-page.md) a központba, hogy értesítést kapjon a sikertelen feldolgozási eredményekről.</span><span class="sxs-lookup"><span data-stu-id="68e6e-150">In addition to filtering on the **Message state** value *Canceled* to inquire for failed messages, you can set up [Business events](../../fin-ops-core/dev-itpro/business-events/home-page.md) on the hub to alert you to failed processing results.</span></span> <span data-ttu-id="68e6e-151">Ehhez aktiválja az *Üzenetfeldolgozói üzenet feldolgozva* üzleti eseményt az **Üzleti események katalógusa** oldalon (**Rendszerfelügyelet > Beállítás > Üzleti események > Üzleti események katalógusa**).</span><span class="sxs-lookup"><span data-stu-id="68e6e-151">To do so, activate the business event named *Message processor message processed*  on the **Business events catalog** page (**System administration > Setup > Business events > Business events catalog**).</span></span>

<span data-ttu-id="68e6e-152">Az aktiválási folyamat részeként a rendszer átirányíthatja, hogy megadja, az esemény csak egy vagy az összes jogi személyre vonatkozik, és megadjon egy **Végpont neve** értéket, amit először meg kell határozni.</span><span class="sxs-lookup"><span data-stu-id="68e6e-152">As part of the activation process, you will be guided to specify whether the event is specific to one or all legal entities and provide an **Endpoint name**, which must be defined first.</span></span>

>[!NOTE]
> <span data-ttu-id="68e6e-153">Ha az **Üzleti esemény bekövetkezésekor** beállítás értéke *Microsoft Power Automate* (nem pedig például *HTTPS*), a **Végpont neve** automatikusan létrejön a Supply Chain Management programban a *Microsoft Power Automate* beállítása alapján.</span><span class="sxs-lookup"><span data-stu-id="68e6e-153">If **When a Business Event occurs** is set to *Microsoft Power Automate* (rather than *HTTPS*, for example), the **Endpoint name** will automatically be created in Supply Chain Management based on the *Microsoft Power Automate* setup.</span></span>

### <a name="microsoft-power-automate-example"></a><span data-ttu-id="68e6e-154">Microsoft Power Automate példa</span><span class="sxs-lookup"><span data-stu-id="68e6e-154">Microsoft Power Automate example</span></span>

<span data-ttu-id="68e6e-155">Ebben a példában az **Üzleti esemény bekövetkezésekor** beállítás használata *Microsoft Power Automate* értékkel olyan e-maileket küld, amelyekben InfoLog-üzenetek szerepelnek, valamint az **Üzenetfeldolgozó üzenetei** oldal megnyitására szolgáló hivatkozással, amely egy megadott sikertelen üzenethez kötődik a központi telepítésen.</span><span class="sxs-lookup"><span data-stu-id="68e6e-155">In this example, use **When a Business Event occurs** with *Microsoft Power Automate* sends emails containing InfoLog messages and hyperlinks to open the **Message processor messages** page for a specific failed message on the hub deployment.</span></span> <span data-ttu-id="68e6e-156">Szükség esetén további logikát adhat hozzá, így az értesítéseket párhuzamosan, különböző csatornák használatával küldheti el, és az eseményadatok alapján szabályozhatja a címzetteket.</span><span class="sxs-lookup"><span data-stu-id="68e6e-156">If needed, you can add extra logic to send the notifications in parallel using different channels and control the recipients based on the event data.</span></span>

1. <span data-ttu-id="68e6e-157">A [Power Automate](https://preview.flow.microsoft.com) szolgáltatásban hozzon létre egy új automatizált felhőfolyamatot az **Üzleti esemény bekövetkezésekor – Fin & Ops alkalmazás (Dynamics 365)** folyamat triggerhez, amelyet a **JSON elemzése** és az **E-mail küldése** lépések követik, ahogy a következő ábrán látható.</span><span class="sxs-lookup"><span data-stu-id="68e6e-157">In [Power Automate](https://preview.flow.microsoft.com), create a new automated cloud flow for the flow trigger **When a Business Event occurs - Fin & Ops App (Dynamics 365)** followed by the **Parse JSON** and **Send an email** steps, as shown in the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example1.png" alt-text="Power Automate automatizált felhőfolyamat":::

1. <span data-ttu-id="68e6e-159">Az **Üzleti esemény bekövetkezésekor** lépésben megkeresheti vagy megadhatja a központ **példányát**, amelyet a **Kategória** követ, majd az *Üzenetfeldolgozó üzenete feldolgozva* **Üzleti esemény**, a következő ábrán látható módon.</span><span class="sxs-lookup"><span data-stu-id="68e6e-159">In the **When a Business Event occurs** step, you can look up or enter the hub **Instance** following the **Category** and then the **Business event** *Message processor message processed*, as shown in the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example2.png" alt-text="Power Automate Üzleti esemény bekövetkezésekor lépés":::

1. <span data-ttu-id="68e6e-161">A **JSON elemzése** lépéshez adjon meg egy **sémát**, amely meghatározza a kiterjesztett mezőket.</span><span class="sxs-lookup"><span data-stu-id="68e6e-161">For the **Parse JSON** step, enter a **Schema** that defines the extended fields.</span></span> <span data-ttu-id="68e6e-162">A *Séma letöltése* lehetőséget használhatja az **Üzleti események katalógusa** oldalon a Supply Chain Management programban, vagy a séma példában használt szövegének beillesztésével kezdheti.</span><span class="sxs-lookup"><span data-stu-id="68e6e-162">You can use the *Download schema* option on the **Business events catalog** page in Supply Chain Management or start by pasting in the example schema text.</span></span> <span data-ttu-id="68e6e-163">A példa szövegét a következő ábra után adhatja meg.</span><span class="sxs-lookup"><span data-stu-id="68e6e-163">This example text is provided after the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example3.png" alt-text="Power Automate JSON elemzése lépés":::

    ```json
    {
        "properties": {
            "BusinessEventId": {
                "type": "string"
            },
            "ControlNumber": {
                "type": "integer"
            },
            "EventId": {
                "type": "string"
            },
            "EventTime": {
                "type": "string"
            },
            "MajorVersion": {
                "type": "integer"
            },
            "MessageContent": {
                "type": "string"
            },
            "MessageDestinationCompanyId": {
                "type": "string"
            },
            "MessageDestinationOperationalSiteId": {
                "type": "string"
            },
            "MessageDestinationWarehouseId": {
                "type": "string"
            },
            "MessageDestinationWorkloadName": {
                "type": "string"
            },
            "MessageInfolog": {
                "type": "string"
            },
            "MessageProcessingResult": {
                "type": "string"
            },
            "MessageProcessingResultLabel": {
                "type": "string"
            },
            "MessageProcessorMessagePageUrl": {
                "type": "string"
            },
            "MessageQueue": {
                "type": "string"
            },
            "MessageQueueLabel": {
                "type": "string"
            },
            "MessageSourceCompanyId": {
                "type": "string"
            },
            "MessageSourceOperationalSiteId": {
                "type": "string"
            },
            "MessageSourceWarehouseId": {
                "type": "string"
            },
            "MessageSourceWorkloadName": {
                "type": "string"
            },
            "MessageState": {
                "type": "string"
            },
            "MessageStateLabel": {
                "type": "string"
            },
            "MessageType": {
                "type": "string"
            },
            "MessageTypeLabel": {
                "type": "string"
            },
            "MinorVersion": {
                "type": "integer"
            }
        },
        "type": "object"
    }
    ```

1. <span data-ttu-id="68e6e-165">Az **E-mail küldése** lépésben kiválaszthatja az egyes mezőket, vagy első lépésként beillesztheti az e-mail szövegtörzsének példáját a **Törzs** mezőbe.</span><span class="sxs-lookup"><span data-stu-id="68e6e-165">In the **Send an email** step, you can select the individual fields or start by pasting the email body example into the **Body** field.</span></span> <span data-ttu-id="68e6e-166">A példát a következő ábra után adhatja meg.</span><span class="sxs-lookup"><span data-stu-id="68e6e-166">This example is provided after the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example4.png" alt-text="Power Automate E-mail küldése lépés":::

    ```plaintext
    Message queue: @{body('Parse_JSON')?['MessageQueue']}
    Message queue label: @{body('Parse_JSON')?['MessageQueueLabel']}
    Message type: @{body('Parse_JSON')?['MessageQueueType']}
    Message type label: @{body('Parse_JSON')?['MessageQueueTypeLabel']}
    Message content: @{body('Parse_JSON')?['MessageContent']}
    Message state: @{body('Parse_JSON')?['MessageState']}
    Message state label: @{body('Parse_JSON')?['MessageStateLabel']}
    Message processing result: @{body('Parse_JSON')?['MessageProcessingResult']}
    Message processing result label: @{body('Parse_JSON')?['MessageProcessingResultLabel']}
    Message infolog: @{body('Parse_JSON')?['MessageInfolog']}
    Message source company ID: @{body('Parse_JSON')?['MessageSourceCompanyId']}
    Message source workload name: @{body('Parse_JSON')?['MessageSourceWorkloadName']}
    Message source site ID: @{body('Parse_JSON')?['MessageSourceOperationalSiteId']}
    Message source warehouse ID: @{body('Parse_JSON')?['MessageSourceWarehouseId']}
    Message destination company ID: @{body('Parse_JSON')?['MessageDestinationCompanyId']}
    Message destination workload name: @{body('Parse_JSON')?['MessageDestinationWorkloadName']}
    Message destination site ID: @{body('Parse_JSON')?['MessageDestinationOperationalSiteId']}
    Message destination warehouse ID: @{body('Parse_JSON')?['MessageDestinationWarehouseId']}
    Message processor message page URL: @{body('Parse_JSON')?['MessageProcessorMessagePageUrl']}
    ```

1. <span data-ttu-id="68e6e-168">Az üzleti esemény mentésekor az esemény automatikusan aktiválódik, és használatra kész a Supply Chain Management részeként.</span><span class="sxs-lookup"><span data-stu-id="68e6e-168">When you save the business event, it will automatically be activated and ready to use as part of Supply Chain Management.</span></span>
