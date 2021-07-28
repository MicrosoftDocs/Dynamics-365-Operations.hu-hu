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
ms.openlocfilehash: 35fd48ef300d46d00c07f3231d780d1ba431d8ef
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 07/06/2021
ms.locfileid: "6350570"
---
# <a name="message-processor-messages"></a>Üzenetfeldolgozó üzenetei

[!include [banner](../includes/banner.md)]

Az üzenetfeldolgozó üzenetei a felhő- és peremalapú skálázási egységek futtatásakor használatosak a [gyártási munkaterhelések](cloud-edge-workload-manufacturing.md) és a [raktárkezelési munkaterhelések](cloud-edge-workload-warehousing.md) során.

Nagy mennyiségű adatcsere történik a központ és a skálázási egységek telepítési környezete között, hogy azok szinkronban legyenek, de az *üzenetfeldolgozó* ezek közül csak néhány adatcserét fog feldolgozni. Az üzenetfeldolgozó által feldolgozott üzeneteket a **Rendszerfelügyelet > Üzenetfeldolgozó > Üzenetfeldolgozó üzenetei** között lehet megtekinteni.

## <a name="message-grid-columns-and-filters"></a>Üzenetrács oszlopai és szűrői

Az **Üzenetfeldolgozó üzenetei** oldal tetején található mezők segítségével megkeresheti a keresett üzeneteket. A szűrők nagy része megfelel az üzenetrács oszlopcímeinek. A következő szűrők és oszlopcímek érhetők el:

- **Üzenettípus** – az üzenet típusát adja meg.
- **Üzenet feldolgozási sora** – annak a feldolgozási sornak a nevét adja meg, amelyben az üzenetet fel kell feldolgozni. A következő feldolgozási sorok vannak megadva:
  - *Skálázási egység–központ*
  - *Központ a raktárvégrehajtási skálázási egységhez*
  - *Központ a gyártásvégrehajtási skálázási egységhez*
- **Üzenet állapota** – az üzenet állapotát adja meg. A következő állapotok léteznek:
  - *Feldolgozási sorban* – az üzenetfeldolgozó készen áll az üzenet feldolgozására.
  - *Feldolgozva* – az üzenetfeldolgozó sikeresen elvégezte az üzenet feldolgozását.
  - *Megszakítva* – az üzenet feldolgozása megtörtént, de a feldolgozás nem sikerült.
- **Üzenet tartalma** – Ezzel a szűrővel az üzenet tartalmának teljes szöveges keresését lehet végrehajtani. (Az üzenet tartalma nem jelenik meg a rácsban.) A szűrő a különleges szimbólumokat (például „-”) szóközként kezeli, és az összes szóközkaraktert logikai VAGY operátorként kezeli. T=Ez azt jelenti például, hogy ha egy „USMF-123456” értékkel megegyező `journalid` értéket keres, a rendszer minden "USMF" vagy "123456" szövege tartalmazó üzenetet megtalál, amely valószínűleg hosszú lista. Így jobb, ha csak a "123456" ot adja meg, mivel ez konkrétabb eredményeket ad vissza.

## <a name="example-message-type-request-inventory-adjustment-financial-update"></a>Példa üzenettípusra: Készletkorrekció pénzügyi frissítésének kérése

Például a *Készletkorrekció pénzügyi frissítésének kérése* **üzenettípussal** lehet leltárnaplót létrehozni és feladni a központban, amikor egy dolgozó a raktári alkalmazás segítségével [készletkorrekciót regisztrál](cloud-edge-warehouse-inventory-adjustment.md) a skálaegység raktárkezelési munkaterhelésén. Mivel ez a konkrét folyamat egy skálázási egységből származik, az **Üzenetsor** mezőben a megjelenő érték: *Skálázási egységből központba*.

Ehhez az üzenettípushoz a skálázási egység munkaterhelése a raktári alkalmazás készletkorrekciós műveletének részeként rögzíti az üzenetet. Az üzenetadatok ezután ugyanannak a folyamatnak a részeként kerülnek a központba, amely a [Commerce Data Exchange-architektúra](../../commerce/commerce-architecture.md) részeként használatos. Az üzenet módosul, és az **üzenet állapot** *Feldolgozási sorban* értékre változik. Az üzenetfeldolgozó ezután feldolgozhatja az üzenetet, és frissíti az **Üzenetállapot** beállítást *Feldolgozva* értékre siker esetén, vagy *Visszavonva* értékre sikertelenség esetén.

## <a name="view-the-message-log-message-content-and-details"></a>Az üzenetnaplónak, az üzenet tartalmának és részleteinek megtekintése

Az üzenetek részletes adatait úgy találhatja meg, hogy kijelöli azt a rácson, majd megnyitja az üzenetrács alatt található **Napló** vagy **Üzenettartalom** lapot, ahol megtekinthetők az egyes feldolgozási események.

Az **Üzenettartalom** az **Üzenettípus** értékétől függ, ezért eltérő szöveghosszúságú lesz. Az üzenet egy jellemző szövege egy **{** szimbólummal kezdődik, és **}** szimbólummal végződiki, közte pedig mezőnevek szerepelnek, például `journalId`, majd egy **:**, és olyasmi értékek, mint *USMF-123456*.

A **Napló** lap eszköztára a következő gombokat tartalmazza:

- **Napló** – A feldolgozás eredményeinek megjelenítése. Ez különösen hasznos a sikertelen feldolgozás okainak megértéséhez, ha az üzenetnél a **Feldolgozás eredménye** *Sikertelen*.
- **Csomag** – Több üzenetfeldolgozási művelet futhat ugyanazon kötegfolyamat részeként. A részletes adatok megtekintéséhez kattintson erre a gombra. Például láthatja, hogy vannak-e függőségek, amelyeknél a rendszernek fel kell feldolgoznia bizonyos üzeneteket egy meghatározott sorrendben.

## <a name="message-processor-batch-job"></a>Üzenetfeldolgozó kötegelt feladata

Felhő- és peremhálózati telepítés futtatásakor a rendszer automatikusan elindítja az *Üzenetfeldolgozó* kötegelt feladatot, amikor új üzenetet hoznak létre feldolgozásra, így ezt a feladatot nem kell manuálisan ütemezni.

Ha szükséges, a kötegelt feladathoz hozzáférhet a **Rendszerfelügyelet > Üzenetfeldolgozó > Üzenetfeldolgozó** pontban.

## <a name="manually-process-or-cancel-a-message"></a>Üzenet manuális feldolgozása vagy visszavonása

Szükség esetén az üzenetek az aktuális állapottól függően manuálisan feldolgozhatók és visszavonhatók. Ehhez jelölje ki az üzenetet a rácson, majd válassza a **Feldolgozás** vagy a **Mégse** lehetőséget a munkaablakban

## <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a>Állítsa be az üzleti eseményeket, hogy sikertelen feldolgozási eredmények esetén riasztásokat küldjenek

A sikertelen üzenetek lekérdezéséhez az **Üzenetállapot** *Visszavonva* értékére való szűrés mellett beállíthat [Üzleti eseményeket](../../fin-ops-core/dev-itpro/business-events/home-page.md) a központba, hogy értesítést kapjon a sikertelen feldolgozási eredményekről. Ehhez aktiválja az *Üzenetfeldolgozói üzenet feldolgozva* üzleti eseményt az **Üzleti események katalógusa** oldalon (**Rendszerfelügyelet > Beállítás > Üzleti események > Üzleti események katalógusa**).

Az aktiválási folyamat részeként a rendszer átirányíthatja, hogy megadja, az esemény csak egy vagy az összes jogi személyre vonatkozik, és megadjon egy **Végpont neve** értéket, amit először meg kell határozni.

>[!NOTE]
> Ha az **Üzleti esemény bekövetkezésekor** beállítás értéke *Microsoft Power Automate* (nem pedig például *HTTPS*), a **Végpont neve** automatikusan létrejön a Supply Chain Management programban a *Microsoft Power Automate* beállítása alapján.

### <a name="microsoft-power-automate-example"></a>Microsoft Power Automate példa

Ebben a példában az **Üzleti esemény bekövetkezésekor** beállítás használata *Microsoft Power Automate* értékkel olyan e-maileket küld, amelyekben InfoLog-üzenetek szerepelnek, valamint az **Üzenetfeldolgozó üzenetei** oldal megnyitására szolgáló hivatkozással, amely egy megadott sikertelen üzenethez kötődik a központi telepítésen. Szükség esetén további logikát adhat hozzá, így az értesítéseket párhuzamosan, különböző csatornák használatával küldheti el, és az eseményadatok alapján szabályozhatja a címzetteket.

1. A [Power Automate](https://preview.flow.microsoft.com) szolgáltatásban hozzon létre egy új automatizált felhőfolyamatot az **Üzleti esemény bekövetkezésekor – Fin & Ops alkalmazás (Dynamics 365)** folyamat triggerhez, amelyet a **JSON elemzése** és az **E-mail küldése** lépések követik, ahogy a következő ábrán látható.

    :::image type="content" source="./media/cloud-edge-power-automate-example1.png" alt-text="Power Automate automatizált felhőfolyamat.":::

1. Az **Üzleti esemény bekövetkezésekor** lépésben megkeresheti vagy megadhatja a központ **példányát**, amelyet a **Kategória** követ, majd az *Üzenetfeldolgozó üzenete feldolgozva* **Üzleti esemény**, a következő ábrán látható módon.

    :::image type="content" source="./media/cloud-edge-power-automate-example2.png" alt-text="Power Automate Üzleti esemény bekövetkezésekor lépés.":::

1. A **JSON elemzése** lépéshez adjon meg egy **sémát**, amely meghatározza a kiterjesztett mezőket. A *Séma letöltése* lehetőséget használhatja az **Üzleti események katalógusa** oldalon a Supply Chain Management programban, vagy a séma példában használt szövegének beillesztésével kezdheti. A példa szövegét a következő ábra után adhatja meg.

    :::image type="content" source="./media/cloud-edge-power-automate-example3.png" alt-text="Power Automate JSON elemzése lépés.":::

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

1. Az **E-mail küldése** lépésben kiválaszthatja az egyes mezőket, vagy első lépésként beillesztheti az e-mail szövegtörzsének példáját a **Törzs** mezőbe. A példát a következő ábra után adhatja meg.

    :::image type="content" source="./media/cloud-edge-power-automate-example4.png" alt-text="Power Automate E-mail küldése lépés.":::

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

1. Az üzleti esemény mentésekor az esemény automatikusan aktiválódik, és használatra kész a Supply Chain Management részeként.
