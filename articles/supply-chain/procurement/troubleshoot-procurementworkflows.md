---
title: Beszerzésekkel és forrásokkal kapcsolatos munkafolyamatok hibaelhárítása
description: Ez a témakör azt mutatja be, hogyan lehet javítani a beszerzésekkel és forrásokkal kapcsolatosa munkafolyamatok használata során felmerülő problémákat.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: e8274890c581fffc7330538430c9b2ba060041bc
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999103"
---
# <a name="troubleshoot-procurement-and-sourcing-workflows"></a>Beszerzésekkel és forrásokkal kapcsolatos munkafolyamatok hibaelhárítása

Ez a témakör azt mutatja be, hogyan lehet javítani a beszerzésekkel és forrásokkal kapcsolatosa munkafolyamatok használata során felmerülő problémákat.

## <a name="error-when-re-submitting-a-purchase-order-to-the-workflow-after-a-change-changes-to-purchase-order-x-are-allowed-only-in-a-draft-state-when-change-management-is-activated"></a>Hiba történt egy beszerzési rendelésnek a munkafolyamatba történő ismételt elküldésekor egy módosítás után: „Az X beszerzési rendelés módosításai csak Válzlat állapotban engedélyezettek, ha a változáskezelés aktív”

Ez a probléma csak akkor fordul elő, ha a beszerzési rendelés *Visszaigazolt* állapotban volt, mielőtt a változtatásokat kérte. Ha a beszerzési rendelés *Jóváhagyott* állapotú, amikor a módosítást kérelmezi, a munkafolyamat sikeresen feldolgozható.

### <a name="error-description"></a>Hiba leírása

A következő hiba történik a munkafolyamatban, amikor egy módosítást követően újra beküld egy beszerzési rendelést:

> Leállítva (hiba): X + + kivétel: A PO 0000569 beszerzési rendelés módosítása csak Vázlat állapotban engedélyezett, ha a változáskezelés aktiválva van<br>
SysWorkflowParticipantProvider-resolve<br>
SysWorkflowParticipantProvider-resolveParticipants<br>
SysWorkflowServiceProvider-resolveParticipant<br>
SysWorkflowQueue-resume

### <a name="issue-resolution"></a>Probléma megoldása

Ez a hiba a beszerzési rendelések felosztásakor jelentkező ellentmondás miatt fordulhat elő.

A hiba blokkolásának feloldásához és a beszerzési rendelés *Vázlat* állapotra állításához nyissa meg a **Beszerzés és forrás \> Időszakos feladatok \> Tisztítás \> Beszerzési rendelés felosztásának visszaállítása** lehetőséget. A további tudnivalókat lásd a következő blogbejegyzésben: [Beszerzésirendelés-felosztási hibák megoldása a Dynamics 365 Supply Chain Management-alkalmazásban](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

A probléma javítás lehetséges [ezen Microsoft tudásbázis (KB) cikk](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138) alapján.

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a>Egy vagy több könyvelési felosztás túlzottan fel van osztva, vagy nincsen eléggé felosztva.

Ez a hiba a beszerzési rendelések felosztásakor jelentkező ellentmondás miatt fordulhat elő.

A hiba blokkolásának feloldásához és a beszerzési rendelés *Vázlat* állapotra állításához nyissa meg a **Beszerzés és forrás \> Időszakos feladatok \> Tisztítás \> Beszerzési rendelés felosztásának visszaállítása** lehetőséget. A további tudnivalókat lásd a következő blogbejegyzésben: [Beszerzésirendelés-felosztási hibák megoldása a Dynamics 365 Supply Chain Management-alkalmazásban](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="if-a-delivery-remainder-is-canceled-on-a-purchase-order-where-change-management-is-turned-on-the-purchase-order-goes-to-a-confirmed-state"></a>Ha szállítási maradék visszavonása egy olyan beszerzési rendelésen történik, amelyen a változáskezelés be van kapcsolva, a beszerzési rendelés Visszaigazolt állapotba kerül.

### <a name="issue-description"></a>Probléma leírása

Olyan beszerzési rendelés esetében, amelyre a változáskezelés érvényes, ha az egyetlen kért módosítás a szállítási maradék törlése egy vagy több sorhoz, a beszerzési rendelés automatikusan *Megerősített* állapotba kerül, a jóváhagyást követően, és nem jön létre napló.

### <a name="issue-resolution"></a>Probléma megoldása

A szállítás maradék visszavonása nem befolyásolja a visszaigazolási napló tartalmát. Ezt a funkciót akkor kell használni, ha a sor részlegesen beérkezett, és a fennmaradó minőséget érvényteleníteni kell egy feldolgozási lépésben, miután a beszerzési rendelést a szállító megerősítette.

Ha ennek tükröződnie kell a beszerzési rendelés visszaigazolásán, akkor a mennyiséget helyesbíteni kell a beszerzési rendelés sorában, hogy a visszaigazolást legyen szükséges. Azt is megteheti, hogy ha a sorban nem érkezett be semmi, akkor a mennyiséget eltávolítja. Ebben az esetben visszaigazolás szükséges.

## <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-purchase-order-preparation-workspace"></a>A visszavont beszerzési rendelések megjelennek a Beszerzési rendelés előkészítő munkaterületének vázlatok listájában.

### <a name="issue-description"></a>Probléma leírása

Miután *Jóváhagyott* állapotú beszerzési rendeléseket vont vissza a **Beszerzési rendelések előkészítése** munkaterületen a beszerzési rendelések vázlatainak listáján továbbra is megjelennek a visszavont beszerzési rendelések.

### <a name="issue-resolution"></a>Probléma megoldása

Ez a probléma csak a változáskezelés hatálya alá tartozó beszerzési rendelésekhez fordulhat elő. Ennek oka az, hogy a törlést olyan módosításnak kell tekinteni, amelyet jóvá kell hagyni. A jóváhagyást a rendszer automatikusan elvégezheti. Ennek megfelelően az eljárás a megszüntetett beszerzési rendelés elküldése a jóváhagyási munkafolyamatba, hogy az *Jóváhagyott* állapotba lépjen. Ezen a ponton a **Beszerzési rendelés előkészítése** munkaterületén nem fog megjelenni a beszerzési rendelések vázlatainak listájában.

