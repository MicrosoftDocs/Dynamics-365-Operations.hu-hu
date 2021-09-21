---
title: Hiba történt egy beszerzési rendelés munkafolyamatba való újbóli elküldése során egy módosítás után
description: Hiba történt egy beszerzési rendelés munkafolyamatba való újbóli elküldése során egy módosítás után
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4b8465d198c440f27a4b3cc4268445e0aa450f5b
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476599"
---
# <a name="error-on-resubmitting-a-purchase-order-to-a-workflow-after-a-change"></a>Hiba történt egy beszerzési rendelés munkafolyamatba való újbóli elküldése során egy módosítás után


## <a name="symptoms"></a>Tünetek

A következő hiba történik a munkafolyamatban, amikor egy módosítást követően újra beküld egy beszerzési rendelést:

> Leállítva (hiba): X + + kivétel: A PO 0000569 beszerzési rendelés módosítása csak Vázlat állapotban engedélyezett, ha a változáskezelés aktiválva van<br>
SysWorkflowParticipantProvider-resolve<br>
SysWorkflowParticipantProvider-resolveParticipants<br>
SysWorkflowServiceProvider-resolveParticipant<br>
SysWorkflowQueue-resume

Ez a probléma csak akkor fordul elő, ha a beszerzési rendelés *Visszaigazolt* állapotban volt, mielőtt a változtatásokat kérte. Ha a beszerzési rendelés *Jóváhagyott* állapotú, amikor a módosítást kérelmezi, a munkafolyamat sikeresen feldolgozható.

## <a name="resolution"></a>Megoldás

Ez a hiba a beszerzési rendelések felosztásakor jelentkező ellentmondás miatt fordulhat elő.

A hiba blokkolásának feloldásához és a beszerzési rendelés *Vázlat* állapotra állításához nyissa meg a **Beszerzés és forrás \> Időszakos feladatok \> Tisztítás \> Beszerzési rendelés felosztásának visszaállítása** lehetőséget. A további tudnivalókat lásd a következő blogbejegyzésben: [Beszerzésirendelés-felosztási hibák megoldása a Dynamics 365 Supply Chain Management-alkalmazásban](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

A probléma javítás lehetséges [ezen Microsoft tudásbázis (KB) cikk](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138) alapján.
