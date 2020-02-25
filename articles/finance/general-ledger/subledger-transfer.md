---
title: Részfőkönyv átvitele a főkönyvbe
description: Ez a témakör azt mutatja be, hogy a Microsoft Dynamics 365 Finance milyen funkciókat tartalmaz a részfőkönyv főkönyvbe történő átmozgatási folyamatához kapcsolódóan.
author: roschlom
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 1ae10f406148e213fd0272d1387f15606233be27
ms.sourcegitcommit: 9168621ca9b5061c65f3e05dbc5918b6a11d53d5
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/31/2020
ms.locfileid: "3000447"
---
# <a name="subledger-transfer-to-the-general-ledger"></a><span data-ttu-id="8ded0-103">Részfőkönyv átvitele a főkönyvbe</span><span class="sxs-lookup"><span data-stu-id="8ded0-103">Subledger transfer to the General ledger</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8ded0-104">Ez a témakör a Microsoft Dynamics 365 Finance azon képességeit mutatja be, amelyek a főkönyvi naplóbejegyzések kötegek átviteléhez szükséges szabályokhoz kapcsolódnak.</span><span class="sxs-lookup"><span data-stu-id="8ded0-104">This topic describes capabilities in Microsoft Dynamics 365 Finance that are related to the rules for transferring batches of subledger journal entries.</span></span>

<span data-ttu-id="8ded0-105">A 8.1 verzióban a módosítások lehetővé teszik azon szabályok átmozgatását, amelyek felváltották a szinkron opciót.</span><span class="sxs-lookup"><span data-stu-id="8ded0-105">In version 8.1, changes were made to allow the transfer of rules, which deprecated the Synchronous option.</span></span> <span data-ttu-id="8ded0-106">További információért lásd: [Eltávolított vagy elavult funkciók a Finance and Operations esetében](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features?toc=/dynamics365/finance/toc.json#finance-and-operations-81-with-platform-update-20).</span><span class="sxs-lookup"><span data-stu-id="8ded0-106">For more information, see [Removed or deprecated features for Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features?toc=/dynamics365/finance/toc.json#finance-and-operations-81-with-platform-update-20).</span></span>

<span data-ttu-id="8ded0-107">A következő lehetőségek érhetők el a részfőkönyvi kötegek átviteléhez.</span><span class="sxs-lookup"><span data-stu-id="8ded0-107">The following options are available for transferring subledger batches.</span></span> 

 - <span data-ttu-id="8ded0-108">Aszinkron – ez a beállítás azonnal ütemezni fogja a részfőkönyvi könyvelési tételek átvitelét a főkönyvbe.</span><span class="sxs-lookup"><span data-stu-id="8ded0-108">Asynchronous – This option will immediately schedule the transfer of the subledger accounting entries to the general ledger.</span></span> <span data-ttu-id="8ded0-109">A program rögzíti a főkönyvi bizonylatot, mihelyt az erőforrások szabadon feldolgozhatják ezt a kérelmet a kiszolgálón.</span><span class="sxs-lookup"><span data-stu-id="8ded0-109">The general ledger voucher will be recorded as soon as resources are free to process this request on the server.</span></span> 

- <span data-ttu-id="8ded0-110">Ütemezett köteg – ezzel a beállítással hozzáadja a főkönyv feldolgozási várólistájába átvitt olyan részkönyv-könyvelési tételeket, amelyeknél a program feldolgozza a tételeket a beérkezett sorrendben.</span><span class="sxs-lookup"><span data-stu-id="8ded0-110">Scheduled batch – This option will add the subledger accounting entries that are being transferred to the processing queue in the general ledger, where the entries will be processed in order received.</span></span> <span data-ttu-id="8ded0-111">A program rögzíti a főkönyvi bizonylatot abban az ütemezett időben, amikor az erőforrások szabadon feldolgozhatják ezt a kötegelt feladatot a kiszolgálón.</span><span class="sxs-lookup"><span data-stu-id="8ded0-111">The general ledger voucher will be recorded at the scheduled time if resources are free to process this batch job on the server.</span></span> 
 
<span data-ttu-id="8ded0-112">A 10.0.8-as verzióban az aszinkron beállítás teljesítményének javítását végezték.</span><span class="sxs-lookup"><span data-stu-id="8ded0-112">In version 10.0.8, improvements were made to enhance the performance of the Asynchrounous option.</span></span> <span data-ttu-id="8ded0-113">Ez a funkció engedélyezve van a **Részfőkönyv átvitele a főkönyv teljesítményoptimalizálása érdekében** szolgáltatásnévvel.</span><span class="sxs-lookup"><span data-stu-id="8ded0-113">This feature is enabled under the feature name **Subledger transfer to General Ledger performance optimization**.</span></span> 
 
<span data-ttu-id="8ded0-114">Ez a funkció javítja az adatoknak a részfőkönyvből a főkönyvbe történő átvitelét.</span><span class="sxs-lookup"><span data-stu-id="8ded0-114">This functionality improves the transfer of data from the subledger to the general ledger.</span></span> <span data-ttu-id="8ded0-115">Ez lehetővé teszi a folyamat hatékonyabb kezelését, és az átmozgatásra kisebb tranzakciók halmazait csoportosítja.</span><span class="sxs-lookup"><span data-stu-id="8ded0-115">It allows the process to be more efficient, and it groups together sets of smaller transactions to transfer.</span></span> <span data-ttu-id="8ded0-116">Ez lehetővé teszi a kötegelt kiszolgáló hatékonyabb használatát.</span><span class="sxs-lookup"><span data-stu-id="8ded0-116">This allows for a more efficient use of the batch server.</span></span> <span data-ttu-id="8ded0-117">Ez a funkció megköveteli, hogy a kötegfájlt be legyen állítva, online legyen és működjön ahhoz, hogy az aszinkron átviteli beállítás működjön.</span><span class="sxs-lookup"><span data-stu-id="8ded0-117">This functionality requires that the batch server be set up, online, and functioning in order for the Asynchrounous transfer option to work.</span></span> 
