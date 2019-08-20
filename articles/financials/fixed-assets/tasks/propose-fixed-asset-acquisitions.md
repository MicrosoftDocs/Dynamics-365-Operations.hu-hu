---
title: Javaslat tárgyieszköz-beszerzésekre
description: Ez a témakör leírja, hogyan szerezhető be tárgyi eszköz a Tárgyi eszközök naplójában található Beszerzési javaslat segítségével.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b35b13dc266fd5bccde437526400832d394b9aa
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839905"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="11c47-103">Javaslat tárgyieszköz-beszerzésekre</span><span class="sxs-lookup"><span data-stu-id="11c47-103">Propose fixed asset acquisitions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="11c47-104">Ez a témakör leírja, hogyan szerezhető be tárgyi eszköz a Tárgyi eszközök naplójában található Beszerzési javaslat segítségével.</span><span class="sxs-lookup"><span data-stu-id="11c47-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="11c47-105">Ez a könyvelői szerepkört és a bemutató adatokat használja a USMF jogi személyhez.</span><span class="sxs-lookup"><span data-stu-id="11c47-105">It uses the accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="11c47-106">A navigációs ablaktáblán nyissa meg a **Modulok > Tárgyi eszközök > Naplóbejegyzések > Befektetett eszközök naplója** elemet.</span><span class="sxs-lookup"><span data-stu-id="11c47-106">In the Navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="11c47-107">Válassza az **Új** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="11c47-107">Select **New**.</span></span>
3. <span data-ttu-id="11c47-108">A **Név** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="11c47-108">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="11c47-109">A Műveleti ablaktáblán válassza a **Sorok** elemet.</span><span class="sxs-lookup"><span data-stu-id="11c47-109">In the action pane, select **Lines**.</span></span>
5. <span data-ttu-id="11c47-110">Válassza a **Javaslatok** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="11c47-110">Select **Proposals**.</span></span>
6. <span data-ttu-id="11c47-111">Válassza a **Beszerzési javaslat** lehetőséget.</span><span class="sxs-lookup"><span data-stu-id="11c47-111">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="11c47-112">Válassza a **Szűrő** elemet.</span><span class="sxs-lookup"><span data-stu-id="11c47-112">Select **Filter**.</span></span> <span data-ttu-id="11c47-113">A korábbi értékek törléséhez kattintson az **Alaphelyzetbe állítás** pontra.</span><span class="sxs-lookup"><span data-stu-id="11c47-113">Select **Reset** to clear out previous values.</span></span>
8. <span data-ttu-id="11c47-114">Válassza ki a **Tárgyieszköz-szám** elnevezésű sort.</span><span class="sxs-lookup"><span data-stu-id="11c47-114">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="11c47-115">A **Feltétel** mezőben adjon meg vagy válasszon ki egy értéket.</span><span class="sxs-lookup"><span data-stu-id="11c47-115">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="11c47-116">Állítsa be a javaslat kapcsán beszerezni kívánt tárgyi eszközökre vonatkozó további feltételeket.</span><span class="sxs-lookup"><span data-stu-id="11c47-116">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="11c47-117">A panelből való kilépéshez nyomja meg kétszer az **OK** gombot.</span><span class="sxs-lookup"><span data-stu-id="11c47-117">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="11c47-118">Erősítse meg a létrehozott tranzakciós sorokat.</span><span class="sxs-lookup"><span data-stu-id="11c47-118">Verify the transaction lines created.</span></span>  
- <span data-ttu-id="11c47-119">A beszerzési javaslat kizárólag az értékmodellben beállított beszerzési dátummal és beszerzési árral rendelkező tárgyi eszközöket veszi figyelembe.</span><span class="sxs-lookup"><span data-stu-id="11c47-119">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="11c47-120">Az oldalon válassza a **Könyvek** lapot.</span><span class="sxs-lookup"><span data-stu-id="11c47-120">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="11c47-121">Válassza a **Feladás** parancsot.</span><span class="sxs-lookup"><span data-stu-id="11c47-121">Select **Post**.</span></span>

