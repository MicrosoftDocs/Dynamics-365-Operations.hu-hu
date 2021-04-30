---
title: Lízingnaplónevek beállítása
description: Ez a témakör a lízingnapló-nevek meghatározását ismerteti. A lízingnapló nevei határozzák meg azokat a naplókat, amelyekre az Eszközlízingből származó tételeket könyveli.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: c139df124b249ec9dc5d16096e6f45f22d435456
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 04/13/2021
ms.locfileid: "5880886"
---
# <a name="set-up-lease-journal-names"></a><span data-ttu-id="4d008-104">Lízingnaplónevek beállítása</span><span class="sxs-lookup"><span data-stu-id="4d008-104">Set up lease journal names</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4d008-105">A lízingnapló nevei határozzák meg azokat a naplókat, amelyekre az Eszközlízing-tranzakciókból származó tételeket könyveli.</span><span class="sxs-lookup"><span data-stu-id="4d008-105">Lease journal names specify the journals that Asset leasing transactions are posted to.</span></span> <span data-ttu-id="4d008-106">Csak az **Eszközlízing** naplótípushoz rendelt naplónevek jelennek meg az **Eszközlízing-paraméterek** lap **Kezdeti elszámolás** és **Havi naplónév** mezőiben.</span><span class="sxs-lookup"><span data-stu-id="4d008-106">Only journal names that are assigned to the **Asset leasing** journal type appear in the **Initial Recognition** and **Monthly Journal Name** fields on the **Asset leasing parameters** page.</span></span> <span data-ttu-id="4d008-107">A **Számlanapló neve** mezőhöz csak a **szállítói számla rögzítése** naplótípus rendelhető hozzá.</span><span class="sxs-lookup"><span data-stu-id="4d008-107">Only **vendor invoice recording** journal type can be assigned to the **Invoice journal name** field.</span></span>

<span data-ttu-id="4d008-108">A lízingnapló-nevek konfigurálásához kövesse az alábbi lépéseket.</span><span class="sxs-lookup"><span data-stu-id="4d008-108">To configure lease journal names, follow these steps.</span></span>

1. <span data-ttu-id="4d008-109">Nyissa meg az **Eszközlízing \> Beállítás \> Eszközlízing paraméterei** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="4d008-109">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="4d008-110">Az **Általános** fül **Kezdeti elszámolás naplónév** mezőjében válasszon ki egy naplót.</span><span class="sxs-lookup"><span data-stu-id="4d008-110">On the **General** tab, in the **Initial recognition journal name** field, and select a journal.</span></span> <span data-ttu-id="4d008-111">A program minden kezdeti elszámolási naplótételt erre a naplónévre ad fel.</span><span class="sxs-lookup"><span data-stu-id="4d008-111">All initial recognition journal entries will be posted to this journal name.</span></span>
3. <span data-ttu-id="4d008-112">A **Számlanapló neve** mezőben válassza ki a napló nevét.</span><span class="sxs-lookup"><span data-stu-id="4d008-112">In the **Invoice journal name** field, select a journal.</span></span> <span data-ttu-id="4d008-113">Ha a **Szállítónak fizetés** lehetőség beállítás **Igen** értékre van állítva a lízingkönyvhöz, akkor a lízing- és költségfizetési számlákat a rendszer erre a naplónévre adja fel.</span><span class="sxs-lookup"><span data-stu-id="4d008-113">If the **Pay to vendor** option is set to **Yes** for the lease book, lease and expense payment invoices will be posted to this journal name.</span></span>
4. <span data-ttu-id="4d008-114">A **Lízingnapló neve** mezőben válassza ki a napló nevét.</span><span class="sxs-lookup"><span data-stu-id="4d008-114">In the **Lease journal name** field, select a journal.</span></span> <span data-ttu-id="4d008-115">Minden értékcsökkenési, kamat- és rövid távú átsorolási tétel erre a naplónévre lesz feladva.</span><span class="sxs-lookup"><span data-stu-id="4d008-115">All depreciation, interest, and short-term reclassification entries will be posted to this journal name.</span></span> <span data-ttu-id="4d008-116">Ha a **Szállítónak fizetés** lehetőség beállítás **Nem** értékre van állítva a lízingkönyvhöz, akkor a lízingfizetések és költségfizetési bejegyzéseket a rendszer erre a naplónévre adja fel.</span><span class="sxs-lookup"><span data-stu-id="4d008-116">If the **Pay to vendor** option is set to **No** for the lease book, lease payments and expense payment entries will also be posted to this journal name.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
