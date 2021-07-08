---
title: Global Inventory Accounting kezdőlap
description: Ez a témakör a Global Inventory Accounting bővítményének Microsoft Dynamics 365 Supply Chain Management kezdőlapja.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: f4434afb847104a18a2a2a2f07a7060cf01de816
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273165"
---
# <a name="global-inventory-accounting-home-page"></a><span data-ttu-id="1e3fa-103">Global Inventory Accounting kezdőlap</span><span class="sxs-lookup"><span data-stu-id="1e3fa-103">Global Inventory Accounting home page</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="1e3fa-104">A nemzetközi szervezetekre egyre nagyobb nyomás nehezedik a hatóságok részéről, hogy megfeleljenek a helyi és globális számviteli előírásoknak.</span><span class="sxs-lookup"><span data-stu-id="1e3fa-104">International organizations are under increasing pressure from authorities to comply with local and global accounting standards.</span></span> <span data-ttu-id="1e3fa-105">A készletértékelés fontos szerepet tölt be a megfelelés biztosításában.</span><span class="sxs-lookup"><span data-stu-id="1e3fa-105">The valuation of inventory plays a significant role in ensuring compliance.</span></span> <span data-ttu-id="1e3fa-106">A Global Inventory Accounting bővítménye átfogó megoldást kínál a szervezeteknek (különösen a nemzetközi szervezeteknek) arra, hogy több költségszámítási főkönyvet használjanak a Microsoft Dynamics 365 Supply Chain Management készletkönyvelés során.</span><span class="sxs-lookup"><span data-stu-id="1e3fa-106">The Global Inventory Accounting Add-in for Microsoft Dynamics 365 Supply Chain Management provides a comprehensive solution that enables organizations (especially international organizations) to use multiple costing ledgers to do inventory accounting.</span></span> <span data-ttu-id="1e3fa-107">Emiatt ezek a szervezetek egyszerre több könyvelési szabványoknak és belső vezetésű könyvelésnek is megfelelniük kell.</span><span class="sxs-lookup"><span data-stu-id="1e3fa-107">Therefore, those organizations can comply with multiple accounting standards and internal management accounting at the same time.</span></span>

<span data-ttu-id="1e3fa-108">A Global Inventory Accounting lehetővé teszi a készlet többszöri megjelenítését a megfelelő értékelési módszer (elszámolóár, átlag vagy meghatározott azonosító) és a kiválasztott könyvelési pénznem példányonkénti alkalmazásával.</span><span class="sxs-lookup"><span data-stu-id="1e3fa-108">Global Inventory Accounting lets you account inventory in multiple representations by applying the appropriate valuation method (standard cost, average, or specific identification) and the selected accounting currency per instance.</span></span> <span data-ttu-id="1e3fa-109">A Global Inventory Accounting lehetővé teszi a szervezetek számára, hogy készletkivonatokat és a számba adott könyvelési értékeket (más néven készletegyenleget és eladott áruk költségét) jelentsen a gyakran kettős értékelés és/vagy kettős pénznemben.</span><span class="sxs-lookup"><span data-stu-id="1e3fa-109">Global Inventory Accounting enables organizations to report inventory statements and subledger accounting values (also known as the inventory balance and the cost of goods sold) in what is often referred to as dual valuation and/or dual currency.</span></span>

<span data-ttu-id="1e3fa-110">A készletkönyvelés egyedi főkönyvekben történik.</span><span class="sxs-lookup"><span data-stu-id="1e3fa-110">Inventory accounting is done in individual ledgers.</span></span> <span data-ttu-id="1e3fa-111">A szervezet minden jogi személyéhez szükség esetén több Global Inventory Accounting főkönyv is létre lehet hozva.</span><span class="sxs-lookup"><span data-stu-id="1e3fa-111">Several Global Inventory Accounting ledgers can be created for each legal entity in an organization, as required.</span></span> <span data-ttu-id="1e3fa-112">Ebből következően több készletre való megjelenítés szerezhető be.</span><span class="sxs-lookup"><span data-stu-id="1e3fa-112">Therefore, multiple inventory representations can be obtained.</span></span> <span data-ttu-id="1e3fa-113">A jogi személynél feladott valamennyi dokumentum (például beszerzési rendelések, értékesítési rendelések és áthozott rendelések) minden olyan költségszámítási főkönyvben könyvelésre kerül, amely az adott jogi személyhez tartozik.</span><span class="sxs-lookup"><span data-stu-id="1e3fa-113">All documents that are posted in a legal entity (such as purchase orders, sales orders, and transfer orders) will be accounted in all the costing ledgers that are associated with that legal entity.</span></span>

<span data-ttu-id="1e3fa-114">A Global Inventory Accounting főkönyvet a következő elemek kombinációja határozza meg:</span><span class="sxs-lookup"><span data-stu-id="1e3fa-114">A Global Inventory Accounting ledger is defined by a combination of the following elements:</span></span>

- <span data-ttu-id="1e3fa-115">Naptár</span><span class="sxs-lookup"><span data-stu-id="1e3fa-115">Calendar</span></span>
- <span data-ttu-id="1e3fa-116">Pénznem</span><span class="sxs-lookup"><span data-stu-id="1e3fa-116">Currency</span></span>
- <span data-ttu-id="1e3fa-117">Árfolyamtábla</span><span class="sxs-lookup"><span data-stu-id="1e3fa-117">Exchange rate table</span></span>
- <span data-ttu-id="1e3fa-118">Szabály</span><span class="sxs-lookup"><span data-stu-id="1e3fa-118">Convention</span></span>

<span data-ttu-id="1e3fa-119">A szabályok készletkönyvelési irányelvek gyűjteménye, amelyek egy vagy több főkönyvhöz társíthatóak.</span><span class="sxs-lookup"><span data-stu-id="1e3fa-119">A convention is a collection of inventory accounting policies that can be associated with one or more ledgers.</span></span> <span data-ttu-id="1e3fa-120">A szabályok révén közös házirendeket oszthat meg a szervezeten belül.</span><span class="sxs-lookup"><span data-stu-id="1e3fa-120">Conventions let you share a common set of policies within your organization.</span></span>

## <a name="availability"></a><span data-ttu-id="1e3fa-121">Elérhetőség</span><span class="sxs-lookup"><span data-stu-id="1e3fa-121">Availability</span></span>

<span data-ttu-id="1e3fa-122">A Global Inventory Accounting jelenleg a következő Azure földrajzi régiókban érhető el:</span><span class="sxs-lookup"><span data-stu-id="1e3fa-122">Global Inventory Accounting is currently available in the following Azure geographic regions:</span></span>

- <span data-ttu-id="1e3fa-123">Amerikai Egyesült Államok</span><span class="sxs-lookup"><span data-stu-id="1e3fa-123">United States</span></span>
- <span data-ttu-id="1e3fa-124">Európa</span><span class="sxs-lookup"><span data-stu-id="1e3fa-124">Europe</span></span>
- <span data-ttu-id="1e3fa-125">Egyesült Királyság</span><span class="sxs-lookup"><span data-stu-id="1e3fa-125">United Kingdom</span></span>
- <span data-ttu-id="1e3fa-126">Ausztrália</span><span class="sxs-lookup"><span data-stu-id="1e3fa-126">Australia</span></span>
- <span data-ttu-id="1e3fa-127">Kanada</span><span class="sxs-lookup"><span data-stu-id="1e3fa-127">Canada</span></span>

<span data-ttu-id="1e3fa-128">Ha egy másik földrajzi régióból kísérli meg telepíteni a bővítményt, akkor a Microsoft Dynamics Lifecycle Services (LCS) egy üzenetet jelenít meg, hogy a földrajzi helye nem támogatott.</span><span class="sxs-lookup"><span data-stu-id="1e3fa-128">If you try to install the add-in from another geographic region, Microsoft Dynamics Lifecycle Services (LCS) will show a message that your geographic region isn't supported.</span></span> <span data-ttu-id="1e3fa-129">A Global Inventory Accounting nem támogatja a Supply Chain Management helyszíni üzemelő példányát.</span><span class="sxs-lookup"><span data-stu-id="1e3fa-129">Global Inventory Accounting doesn't support on-premises deployments of Supply Chain Management.</span></span>

## <a name="licensing"></a><span data-ttu-id="1e3fa-130">Licenckezelés</span><span class="sxs-lookup"><span data-stu-id="1e3fa-130">Licensing</span></span>

<span data-ttu-id="1e3fa-131">A Global Inventory Accounting szolgáltatás egy licencben szerepel az Supply Chain Management szolgáltatásban elérhető standard költségkezelési funkciókkal.</span><span class="sxs-lookup"><span data-stu-id="1e3fa-131">Global Inventory Accounting is licensed together with the standard cost management features available for Supply Chain Management.</span></span> <span data-ttu-id="1e3fa-132">Nem kell további licencet vásárolnia a Global Inventory Accounting szolgáltatás használatához.</span><span class="sxs-lookup"><span data-stu-id="1e3fa-132">You don't have to purchase an additional license to use Global Inventory Accounting.</span></span>
