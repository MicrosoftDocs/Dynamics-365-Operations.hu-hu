---
title: "Fuvarlevél létrehozása"
description: "Ez a témakör ismerteti, hogy hogyan hozhat létre fuvarlevelet a raktárkezelési folyamatok használata közben."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b274ff572d2be9a71b91d533023b95be98591e4f
ms.contentlocale: hu-hu
ms.lasthandoff: 09/29/2017

---

# <a name="create-a-bill-of-lading"></a><span data-ttu-id="f844b-103">Fuvarlevél létrehozása</span><span class="sxs-lookup"><span data-stu-id="f844b-103">Create a bill of lading</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f844b-104">Ez a témakör ismerteti, hogy hogyan hozhat létre fuvarlevelet a raktárkezelési folyamatok használata közben.</span><span class="sxs-lookup"><span data-stu-id="f844b-104">This topic describes how to create a bill of lading when using warehouse management processes.</span></span>  

<span data-ttu-id="f844b-105">A fuvarlevél egy jogi dokumentum a cikkeket leszállító vállalat és a szállítmányozó között.</span><span class="sxs-lookup"><span data-stu-id="f844b-105">A bill of lading is a legal document between the company that ships the items and the carrier.</span></span> <span data-ttu-id="f844b-106">A dokumentum a szállított cikkeket kíséri, és a cikkek célhelyen történő megérkezésekor a kiszáLlítás bizonylataként szolgál.</span><span class="sxs-lookup"><span data-stu-id="f844b-106">The document accompanies the shipped items, and it serves as a receipt of shipment when the items are delivered at the destination.</span></span> <span data-ttu-id="f844b-107">Raktárkezelés használatakor kétféleképpen lehet fuvarlevelet létrehozni:</span><span class="sxs-lookup"><span data-stu-id="f844b-107">If you're using warehouse management, there are two ways to generate a bill of lading:</span></span>

  -   <span data-ttu-id="f844b-108">A jelentés létrehozása manuálisan, a **fuvarlevél** oldalon.</span><span class="sxs-lookup"><span data-stu-id="f844b-108">Create the report manually, using the **Bill of lading** page.</span></span>
  -   <span data-ttu-id="f844b-109">Jelentés készítése a **Rakománytervező munkaterületről**.</span><span class="sxs-lookup"><span data-stu-id="f844b-109">Generate the report from the **Load planning workbench**.</span></span>

<span data-ttu-id="f844b-110">Ha a fuvarlevelet a **rakománytervező munkaterületről** hozza létre, a rakomány állapota legyen: **kiszállítva.**</span><span class="sxs-lookup"><span data-stu-id="f844b-110">If you generate the bill of lading from the **Load planning workbench**, the load status must be **Shipped.**</span></span> <span data-ttu-id="f844b-111">Ha egynél több szállítmány szerepel a rakományban, a fuvarlevél minden egyes szállítmányhoz létrejön.</span><span class="sxs-lookup"><span data-stu-id="f844b-111">If there's more than one shipment in the load, a bill of lading is created for each shipment.</span></span> <span data-ttu-id="f844b-112">Fuvarlevél létrehozását követően módosíthatja azt a **Fuvarlevél** oldalon.</span><span class="sxs-lookup"><span data-stu-id="f844b-112">After a bill of lading has been created you can make changes to it on the **Bill of lading** page.</span></span>

## <a name="master-bill-of-lading"></a><span data-ttu-id="f844b-113">Fő fuvarlevél</span><span class="sxs-lookup"><span data-stu-id="f844b-113">Master bill of lading</span></span>
<span data-ttu-id="f844b-114">Ha egynél több szállítmány tartozik a rakományhoz, akkor létrehozhat egy fő fuvarlevelet.</span><span class="sxs-lookup"><span data-stu-id="f844b-114">If there's more than one shipment in the load, you can generate a master bill of lading.</span></span> <span data-ttu-id="f844b-115">Ennek elrendezése és a rajta szereplő információ megegyezik a fuvarlevéllel, de tartalmazza az összes szállítás összesített tartalmát.</span><span class="sxs-lookup"><span data-stu-id="f844b-115">This has the same layout and information as a bill of lading, but contains the summarized content for all the shipments.</span></span> <span data-ttu-id="f844b-116">Ha a **Hozzon létre fő fuvarlevelet, ha egynél több szállítmány van a rakományban** lehetőség **Igenre** van állítva a **Szállításkezelési paraméterek** lapon, és egynél több szállítmány van, akkor a fő fuvarlevél a fuvarlevél létrehozásakor automatikusan létrejön a **Rakománytervező munkaterületről**.</span><span class="sxs-lookup"><span data-stu-id="f844b-116">If the **Create a master bill of lading when there's more than one shipment on a load** option is set to **Yes** on the **Transportation management parameters** page, a master bill of lading is automatically generated if you create a bill of lading from the **Load planning workbench**, and there's more than one shipment.</span></span> <span data-ttu-id="f844b-117">Elérheti a fuvarlevelek listáját a következő lehetőségekre kattintva: **Kapcsolódó információk** &gt; **Fuvarlevél**.</span><span class="sxs-lookup"><span data-stu-id="f844b-117">You can also get a list of the bills of lading by clicking **Related information** &gt; **Bill of lading**.</span></span> <span data-ttu-id="f844b-118">Ha a fuvarleveleket manuálisan hozza létre, létrehozhat egy fő fuvarlevelet a **Fuvarlevél** oldalon.</span><span class="sxs-lookup"><span data-stu-id="f844b-118">If you're creating bills of lading manually, you can create a master bill of lading on the **Bill of lading** page.</span></span>



